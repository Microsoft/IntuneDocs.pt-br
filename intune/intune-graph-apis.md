---
title: Como usar o Azure AD para acessar APIs do Intune no Microsoft Graph
titlesuffix: Microsoft Intune
description: Descreve as etapas necessárias para que os aplicativos usem o Azure AD para acessar as APIs do Intune no Microsoft Graph.
keywords: funções de permissão PowerShell C# Intune API do Graph
author: dougeby
manager: dougeby
ms.author: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 79A67342-C06D-4D20-A447-678A6CB8D70A
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3ca5b09d415466d2ab6ce2f70a53f7fd8444d28f
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-azure-ad-to-access-the-intune-apis-in-microsoft-graph"></a>Como usar o Azure AD para acessar as APIs do Intune no Microsoft Graph

A [API do Microsoft Graph](https://developer.microsoft.com/graph/) agora dá suporte ao Microsoft Intune com APIs e funções de permissão específicas.  A API do Microsoft Graph usa o Azure Active Directory (Azure AD) para autenticação e controle de acesso.  
O acesso às APIs do Intune no Microsoft Graph requer:

- Uma ID de aplicativo com:

    - Permissão para chamar o Azure AD e as APIs do Microsoft Graph.
    - Escopos de permissões relevantes para as tarefas de aplicativo específicas.

- Credenciais do usuário com:

    - Permissão para acessar o locatário do Azure AD associado ao aplicativo.
    - Permissões de função necessárias para dar suporte aos escopos de permissões do aplicativo.

- O usuário final para conceder permissão ao aplicativo para executar tarefas de aplicativos para seu locatário do Azure.

Este artigo:

- Mostra como registrar um aplicativo com acesso à API do Microsoft Graph e às funções de permissão relevantes.

- Descreve as funções de permissão da API do Intune.

- Fornece exemplos de autenticação da API do Intune para C# e PowerShell.

- Descreve como dar suporte a vários locatários.

Para obter mais informações, consulte:

- [Autorizar o acesso a aplicativos Web usando o OAuth 2.0 e o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code)
- [Introdução à autenticação do Azure AD](https://www.visualstudio.com/docs/integrate/get-started/auth/oauth)
- [Integrando aplicativos ao Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)
- [Entender o OAuth 2.0](https://oauth.net/2/)

## <a name="register-apps-to-use-the-microsoft-graph-api"></a>Registrar aplicativos para usar a API do Microsoft Graph

Para registrar um aplicativo para usar a API do Microsoft Graph:

1.  Entre no [portal do Azure](https://portal.azure.com) usando credenciais administrativas.

    Conforme apropriado, você poderá usar:
    - A conta do administrador de locatários.
    - Uma conta de usuário do locatário com a configuração **Os usuários podem registrar aplicativos** habilitada.

2.  No menu, escolha **Azure Active Directory** &gt; **Registros do Aplicativo**.

    <img src="./media/azure-ad-app-reg.png" width="157" height="170" alt="The App registrations menu command" />

3.  Escolha **Novo registro de aplicativo** para criar um novo aplicativo ou escolha um aplicativo existente.  (Se você escolher um aplicativo existente, pule a próxima etapa).

4.  Na folha **Criar**, especifique o seguinte:

    1.  Um **Nome** para o aplicativo (exibido quando os usuários entram).

    2.  Os valores de **Tipo de aplicativo** e **URI de Redirecionamento**.

        Eles variam de acordo com suas necessidades. Por exemplo, se você estiver usando uma [ADAL](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (Biblioteca de Autenticação) do Azure AD, defina **Tipo de aplicativo** como `Native` e **URI de Redirecionamento** como `urn:ietf:wg:oauth:2.0:oob`.

        <img src="media/azure-ad-app-new.png" width="209" height="140" alt="New app properties and values" />

        Para saber mais, consulte [Cenários de autenticação do Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).

5.  Na folha do aplicativo:

    1.  Anote o valor de **ID do Aplicativo**.

    2.  Escolha **Configurações** &gt; **Acesso à API** &gt; **Permissões Necessárias**.

    <img src="media/azure-ad-req-perm.png" width="483" height="186" alt="The Required permissions setting" />

6.  Na folha **Permissões Necessárias**, escolha **Adicionar** &gt; **Adicionar acesso à API** &gt; **Selecionar uma API**.

    <img src="media/azure-ad-add-graph.png" width="436" height="140" alt="The Microsoft Graph setting" />

7.  Na folha **Selecionar uma API**, escolha **Microsoft Graph** &gt; **Selecionar**.  A folha **Habilitar acesso** é aberta e lista os escopos de permissões disponíveis para o aplicativo.

    <img src="media/azure-ad-perm-scopes.png" width="489" height="248" alt="Intune Graph API permission scopes" />

    Escolha as funções necessárias para o aplicativo colocando uma marca de seleção à esquerda dos nomes de relevantes.  Para saber mais sobre escopos de permissões específicos do Intune, consulte [Escopos de permissões do Intune](#intune-permission-scopes).  Para saber mais sobre outros escopos de permissões da API do Graph, consulte [Referência de permissões do Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).

    Para obter melhores resultados, escolha o menor número de funções necessárias para implementar o aplicativo.

    Quando terminar, escolha **Selecionar** e **Concluído** para salvar as alterações.

Neste ponto, você também poderá:

- Optar por conceder permissão para todas as contas de locatário para usar o aplicativo sem fornecer credenciais.  

    Para fazer isso, escolha **Conceder permissões** e aceite o prompt de confirmação.

    Ao executar o aplicativo pela primeira vez, você deverá conceder a permissão de aplicativo para executar as funções selecionadas.

    <img src="media/azure-ad-grant-perm.png" width="351" height="162" alt="The Grant permissions button" />

- Disponibilize o aplicativo para usuários que estão fora do locatário.  (Normalmente, isso é necessário apenas para parceiros que dão suporte a vários locatários e organizações.)  

    Para fazer isso:

  1. Escolha **Manifesto** na folha do aplicativo, que abrirá a folha **Editar Manifesto**.

     <img src="media/azure-ad-edit-mft.png" width="295" height="114" alt="The Edit manifest blade" />

  2. Altere o valor da configuração `availableToOtherTenants` para `true`.

  3. Salve as alterações.

## <a name="intune-permission-scopes"></a>Escopos de permissões do Intune

O Azure AD e o Microsoft Graph usam escopos de permissão para controlar o acesso aos recursos corporativos.  

Os escopos de permissões (também chamados de _escopos do OAuth_) controlam o acesso a entidades específicas do Intune e suas propriedades. Esta seção resume os escopos de permissão para os recursos da API do Intune.

Para saber mais:
- [Autenticação do Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)
- [Escopos de permissões de aplicativo](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-scopes)

Ao conceder permissão para o Microsoft Graph, você pode especificar os seguintes escopos para controlar o acesso aos recursos do Intune: a tabela a seguir resume os escopos de permissões da API do Intune.  A primeira coluna mostra o nome do recurso, conforme exibido no portal do Azure e a segunda coluna fornece o nome do escopo de permissão.

Configuração _Habilitar o Acesso_ | Nome do escopo
:--|:--
__Executar ações remotas que afetam o usuário em dispositivos Microsoft Intune__ | [DeviceManagementManagedDevices.PrivilegedOperations.All](#mgd-po)
__Ler e gravar dispositivos Microsoft Intune__ | [DeviceManagementManagedDevices.ReadWrite.All](#mgd-rw)
__Ler dispositivos Microsoft Intune__ | [DeviceManagementManagedDevices.Read.All](#mgd-ro)
__Ler e gravar configurações de RBAC do Microsoft Intune__ | [DeviceManagementRBAC.ReadWrite.All](#rac-rw)
__Ler configurações de RBAC do Microsoft Intune__ | [DeviceManagementRBAC.Read.All](#rac=ro)
__Ler e gravar em aplicativos do Microsoft Intune__ | [DeviceManagementApps.ReadWrite.All](#app-rw)
__Ler aplicativos do Microsoft Intune__ | [DeviceManagementApps.Read.All](#app-ro)
__Ler e gravar as Políticas e a Configuração de Dispositivo do Microsoft Intune__ | [DeviceManagementConfiguration.ReadWrite.All](#cfg-rw)
__Ler as Políticas e a Configuração de Dispositivo do Microsoft Intune__ | [DeviceManagementConfiguration.Read.All](#cfg-ro)
__Ler e gravar a configuração do Microsoft Intune__ | [DeviceManagementServiceConfig.ReadWrite.All](#svc-rw)
__Ler a configuração do Microsoft Intune__ | [DeviceManagementServiceConfig.Read.All](#svc-ra)

A tabela lista as configurações na ordem em que são exibidas no Portal do Azure. As próximas seções descrevem os escopos em ordem alfabética.

No momento, todos os escopos de permissões do Intune exigem o acesso de administrador.  Isso significa que você precisa de credenciais correspondentes para executar aplicativos ou scripts que acessam recursos da API do Intune.

### <a name="app-ro"></a>DeviceManagementApps.Read.All

- Configuração **Habilitar o Acesso**: __Ler aplicativos do Microsoft Intune__

- Permite o acesso de leitura às seguintes propriedades e status de entidade:
    - Aplicativos móveis
    - Categorias de aplicativos móveis
    - Políticas de proteção de aplicativo
    - Configurações de aplicativo

### <a name="app-rw"></a>DeviceManagementApps.ReadWrite.All

- Configuração **Habilitar o Acesso**: __Ler e gravar aplicativos do Microsoft Intune__

- Permite as mesmas operações de __DeviceManagementApps.Read.All__

- Também permite alterações às seguintes entidades:

    - Aplicativos móveis
    - Categorias de aplicativos móveis
    - Políticas de proteção de aplicativo
    - Configurações de aplicativo

### <a name="cfg-ro"></a>DeviceManagementConfiguration.Read.All

- Configuração **Habilitar o Acesso**: __Ler as políticas e a configuração de dispositivo do Microsoft Intune__

- Permite o acesso de leitura às seguintes propriedades e status de entidade:
    - Configuração de dispositivo
    - Política de conformidade do dispositivo
    - Mensagens de notificação

### <a name="cfg-ra"></a>DeviceManagementConfiguration.ReadWrite.All

- Configuração **Habilitar o Acesso**: __Ler e gravar as políticas e a configuração de dispositivo do Microsoft Intune__

- Permite as mesmas operações de __DeviceManagementConfiguration.Read.All__

- Os aplicativos também podem criar, atribuir, excluir e alterar as seguintes entidades:
    - Configuração de dispositivo
    - Política de conformidade do dispositivo
    - Mensagens de notificação

### <a name="mgd-po"></a>DeviceManagementManagedDevices.PrivilegedOperations.All

- Configuração **Habilitar o Acesso**: __Executar ações remotas que afetam o usuário em dispositivos Microsoft Intune__

- Permite as seguintes ações remotas em um dispositivo gerenciado:
    - Desativar
    - Apagamento
    - Redefinir/Recuperar Senha
    - Bloqueio remoto
    - Habilitar/Desabilitar Modo Perdido
    - Limpar Computador
    - Reinicialização
    - Excluir Usuário do Dispositivo Compartilhado

### <a name="mgd-ro"></a>DeviceManagementManagedDevices.Read.All

- Configuração **Habilitar o Acesso**: __Ler dispositivos Microsoft Intune__

- Permite o acesso de leitura às seguintes propriedades e status de entidade:
    - Dispositivo gerenciado
    - Categoria de dispositivo
    - Aplicativo detectado
    - Ações remotas
    - Informações sobre malware

### <a name="mgd-rw"></a>DeviceManagementManagedDevices.ReadWrite.All

- Configuração **Habilitar o Acesso**: __Ler e gravar dispositivos Microsoft Intune__

- Permite as mesmas operações de __DeviceManagementManagedDevices.Read.All__

- Os aplicativos também podem criar, excluir e alterar as seguintes entidades:
    - Dispositivo gerenciado
    - Categoria de dispositivo

- As seguintes ações remotas também são permitidas:
    - Localizar dispositivos
    - Ignorar bloqueio de ativação
    - Solicitar assistência remota

### <a name="rac-ro"></a>DeviceManagementRBAC.Read.All

- Configuração **Habilitar o Acesso**: __Ler configurações de RBAC do Microsoft Intune__

- Permite o acesso de leitura às seguintes propriedades e status de entidade:
    - Atribuições de função
    - Definições de função
    - Operações de recursos

### <a name="rac-rw"></a>DeviceManagementRBAC.ReadWrite.All

- Configuração **Habilitar o Acesso**: __Ler e gravar configurações de RBAC do Microsoft Intune__

- Permite as mesmas operações de __DeviceManagementRBAC.Read.All__

- Os aplicativos também podem criar, atribuir, excluir e alterar as seguintes entidades:
    - Atribuições de função
    - Definições de função

### <a name="svc-ro"></a>DeviceManagementServiceConfig.Read.All

- Configuração **Habilitar o Acesso**: __Ler a configuração do Microsoft Intune__

- Permite o acesso de leitura às seguintes propriedades e status de entidade:
    - Registro do dispositivo
    - Certificado de Notificação por Push da Apple
    - Programa de Registro do Dispositivo da Apple
    - Apple Volume Purchase Program
    - Exchange Connector
    - Termos e condições
    - Gerenciamento de Despesas de Telecomunicações
    - PKI de Nuvem
    - Identidade Visual
    - Defesa contra Ameaças Móveis

### <a name="svc-rw"></a>DeviceManagementServiceConfig.ReadWrite.All

- Configuração **Habilitar o Acesso**: __Ler e gravar a configuração do Microsoft Intune__

- Permite as mesmas operações que DeviceManagementServiceConfig.Read.All_

- Os aplicativos também podem configurar os seguintes recursos do Intune:
    - Registro do dispositivo
    - Certificado de Notificação por Push da Apple
    - Programa de Registro do Dispositivo da Apple
    - Apple Volume Purchase Program
    - Exchange Connector
    - Termos e condições
    - Gerenciamento de Despesas de Telecomunicações
    - PKI de Nuvem
    - Identidade Visual
    - Defesa contra Ameaças Móveis

## <a name="azure-ad-authentication-examples"></a>Exemplos de autenticação do Azure AD

Esta seção mostra como incorporar o Azure AD em seus projetos do C# e PowerShell.

Em cada exemplo, você precisará especificar uma ID de aplicativo que tem, pelo menos, o escopo de permissão `DeviceManagementManagedDevices.Read.All` (abordado anteriormente).

Ao testar um dos exemplos, você poderá receber erros de status HTTP 403 (Proibido) semelhantes ao seguinte:

``` javascript
{
  "error": {
    "code": "Forbidden",
    "message": "Application is not authorized to perform this operation - Operation ID " +
       "(for customer support): 00000000-0000-0000-0000-000000000000 - " +
       "Activity ID: cc7fa3b3-bb25-420b-bfb2-1498e598ba43 - " +
       "Url: https://example.manage.microsoft.com/" +
       "Service/Resource/RESTendpoint?" +
       "api-version=2017-03-06 - CustomApiErrorPhrase: ",
    "innerError": {
      "request-id": "00000000-0000-0000-0000-000000000000",
      "date": "1980-01-0112:00:00"
    }
  }
}
```

Se isso acontecer, verifique se:

- Você atualizou a ID do aplicativo para uma ID autorizada a usar a API do Microsoft Graph e o escopo de permissão `DeviceManagementManagedDevices.Read.All`.

- Suas credenciais de locatário dão suporte a funções administrativas.

- O código é semelhante às amostras exibidas.


### <a name="authenticate-azure-ad-in-c"></a>Autenticar o Azure AD no C\#

Este exemplo mostra como usar o C# para recuperar uma lista de dispositivos associados à sua conta do Intune.

1.  Inicie o Visual Studio e, em seguida, crie um novo projeto de aplicativo (.NET Framework) do Console do Visual C#.

2.  Insira um nome para o projeto e forneça outros detalhes, conforme desejado.

    <img src="media/aad-auth-cpp-new-console.png" width="624" height="433" alt="Creating a C# console app project in Visual Studio"  />

3.  Use o Gerenciador de Soluções para adicionar o pacote NuGet da ADAL da Microsoft ao projeto.

    1.  Clique com o botão direito do mouse em Gerenciador de Soluções.
    2.  Escolha **Gerenciar Pacotes NuGet…** &gt; **Procurar**.
    3.  Selecione `Microsoft.IdentityModel.Clients.ActiveDirectory` e, em seguida, escolha **Instalar**.

    <img src="media/aad-auth-cpp-install-package.png" width="624" height="458" alt="Selecting the Azure AD identity model module" />

4.  Adicione as seguintes instruções ao início do **Program.cs**:

    ``` csharp
    using Microsoft.IdentityModel.Clients.ActiveDirectory;</p>
    using System.Net.Http;
    ```

5.  Adicione um método para criar o cabeçalho de autorização:

    ``` csharp
    private static async Task<string> GetAuthorizationHeader()
    {
        string applicationId = "<Your Application ID>";
        string authority = "https://login.microsoftonline.com/common/";
        Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
        AuthenticationContext context = new AuthenticationContext(authority);
        AuthenticationResult result = await context.AcquireTokenAsync(
            "https://graph.microsoft.com",
            applicationId, redirectUri,
            new PlatformParameters(PromptBehavior.Auto));
        return result.CreateAuthorizationHeader();
    ```

    Lembre-se de alterar o valor de `application_ID` para que ele corresponda a um que recebeu, pelo menos, o escopo de permissão `DeviceManagementManagedDevices.Read.All`, conforme descrito anteriormente.

6. Adicione um método para recuperar a lista de dispositivos:

    ``` csharp
    private static async Task<string> GetMyManagedDevices()
    {
        string authHeader = await GetAuthorizationHeader();
        HttpClient graphClient = new HttpClient();
        graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
        return await graphClient.GetStringAsync(
            "https://graph.microsoft.com/beta/me/managedDevices");
    }
    ```

7.  Atualize **Principal** para chamar **GetMyManagedDevices**:

    ``` csharp
    string devices = GetMyManagedDevices().GetAwaiter().GetResult();
    Console.WriteLine(devices);
    ```

8.  Compile e execute o programa.  

Ao executar o programa pela primeira vez, você deverá receber dois prompts.  O primeiro solicita suas credenciais e o segundo concede permissões para a solicitação `managedDevices`.  

Para referência, este é o programa concluído:

``` csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System;
using System.Net.Http;
using System.Threading.Tasks;

namespace IntuneGraphExample
{
    class Program
    {
        static void Main(string[] args)
        {
            string devices = GetMyManagedDevices().GetAwaiter().GetResult();
            Console.WriteLine(devices);
        }

        private static async Task<string> GetAuthorizationHeader()
        {
            string applicationId = "<Your Application ID>";
            string authority = "https://login.microsoftonline.com/common/";
            Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
            AuthenticationContext context = new AuthenticationContext(authority);
            AuthenticationResult result = await context.AcquireTokenAsync("https://graph.microsoft.com", applicationId, redirectUri, new PlatformParameters(PromptBehavior.Auto));
            return result.CreateAuthorizationHeader();
        }

        private static async Task<string> GetMyManagedDevices()
        {
            string authHeader = await GetAuthorizationHeader();
            HttpClient graphClient = new HttpClient();
            graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
            return await graphClient.GetStringAsync("https://graph.microsoft.com/beta/me/managedDevices");
        }
    }
}
```

### <a name="authenticate-azure-ad-powershell"></a>Autenticar o Azure AD (PowerShell)

O script do PowerShell a seguir usa o módulo Azure AD PowerShell para autenticação.  Para saber mais, consulte [Azure Active Directory PowerShell Versão 2](https://docs.microsoft.com/powershell/azure/install-adv2?view=azureadps-2.0) e os [exemplos do Intune PowerShell](https://github.com/microsoftgraph/powershell-intune-samples).

Neste exemplo, atualize o valor de `$clientID` para que ele corresponda a uma ID de aplicativo válida.

``` powershell
function Get-AuthToken {
    [cmdletbinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        $User
    )

    $userUpn = New-Object "System.Net.Mail.MailAddress" -ArgumentList $User
    $tenant = $userUpn.Host

    Write-Host "Checking for AzureAD module..."

    $AadModule = Get-Module -Name "AzureAD" -ListAvailable
    if ($AadModule -eq $null) {
        Write-Host "AzureAD PowerShell module not found, looking for AzureADPreview"
        $AadModule = Get-Module -Name "AzureADPreview" -ListAvailable
    }

    if ($AadModule -eq $null) {
        write-host
        write-host "AzureAD Powershell module not installed..." -f Red
        write-host "Install by running 'Install-Module AzureAD' or 'Install-Module AzureADPreview' from an elevated PowerShell prompt" -f Yellow
        write-host "Script can't continue..." -f Red
        write-host
        exit
    }

    # Getting path to ActiveDirectory Assemblies
    # If the module count is greater than 1 find the latest version

    if ($AadModule.count -gt 1) {
        $Latest_Version = ($AadModule | select version | Sort-Object)[-1]
        $aadModule = $AadModule | ? { $_.version -eq $Latest_Version.version }
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    else {
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    [System.Reflection.Assembly]::LoadFrom($adal) | Out-Null
    [System.Reflection.Assembly]::LoadFrom($adalforms) | Out-Null

    $clientId = "<Your Application ID>"
    $redirectUri = "urn:ietf:wg:oauth:2.0:oob"
    $resourceAppIdURI = "https://graph.microsoft.com"
    $authority = "https://login.microsoftonline.com/$Tenant"

    try {
        $authContext = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext" -ArgumentList $authority
        # https://msdn.microsoft.com/library/azure/microsoft.identitymodel.clients.activedirectory.promptbehavior.aspx
        # Change the prompt behaviour to force credentials each time: Auto, Always, Never, RefreshSession
        $platformParameters = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.PlatformParameters" -ArgumentList "Auto"
        $userId = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.UserIdentifier" -ArgumentList ($User, "OptionalDisplayableId")
        $authResult = $authContext.AcquireTokenAsync($resourceAppIdURI, $clientId, $redirectUri, $platformParameters, $userId).Result
        # If the accesstoken is valid then create the authentication header
        if ($authResult.AccessToken) {
            # Creating header for Authorization token
            $authHeader = @{
                'Content-Type' = 'application/json'
                'Authorization' = "Bearer " + $authResult.AccessToken
                'ExpiresOn' = $authResult.ExpiresOn
            }
            return $authHeader
        }
        else {
            Write-Host
            Write-Host "Authorization Access Token is null, please re-run authentication..." -ForegroundColor Red
            Write-Host
            break
        }
    }
    catch {
        write-host $_.Exception.Message -f Red
        write-host $_.Exception.ItemName -f Red
        write-host
        break
    }   
}

$authToken = Get-AuthToken -User "<Your AAD Username>"

try {
    $uri = "https://graph.microsoft.com/beta/me/managedDevices"
    Write-Verbose $uri
    (Invoke-RestMethod -Uri $uri –Headers $authToken –Method Get).Value
}
catch {
    $ex = $_.Exception
    $errorResponse = $ex.Response.GetResponseStream()
    $reader = New-Object System.IO.StreamReader($errorResponse)
    $reader.BaseStream.Position = 0
    $reader.DiscardBufferedData()
    $responseBody = $reader.ReadToEnd();
    Write-Host "Response content:`n$responseBody" -f Red
    Write-Error "Request to $Uri failed with HTTP Status $($ex.Response.StatusCode) $($ex.Response.StatusDescription)"
    write-host
    break
}
```

## <a name="support-multiple-tenants-and-partners"></a>Dar suporte a vários locatários e parceiros

Caso sua organização dê suporte a organizações com seus próprios locatários do Azure AD, é recomendável permitir que os clientes usem seu aplicativo com os respectivos locatários deles.

Para fazer isso:

1.  Verifique se a conta do cliente existe no locatário de destino do Azure AD.

2.  Verifique se sua conta de locatário permite aos usuários registrar aplicativos (consulte **Configurações do usuário**).

3.  Estabeleça uma relação entre cada locatário.  

    Para fazer isso:

    a. Use o [Microsoft Partner Center](https://partnercenter.microsoft.com/) para definir uma relação com o cliente e seu endereço de email.

    b. Convide o usuário para se tornar um convidado de seu locatário.

Para convidar o usuário para ser um convidado de seu locatário:

1.  Escolha **Adicionar um usuário convidado** no painel **Tarefas rápidas**.

    <img src="media/azure-ad-add-guest.png" width="448" height="138" alt="Use Quick Tasks to add a guest user" />

2.  Insira o endereço de email do cliente e (opcionalmente) adicione uma mensagem personalizada ao convite.

    <img src="media/azure-ad-guest-invite.png" width="203" height="106" alt="Inviting an external user as a guest" />

3.  Escolha **Convidar**.

Isso envia um convite para o usuário.

   <img src="media/aad-multiple-tenant-invitation.png" width="624" height="523" alt="A sample guest invitation" />

   O usuário precisa escolher o link **Introdução** para aceitar o convite.

Quando a relação é estabelecida (ou seu convite foi aceito), adicione a conta de usuário à **Função do diretório**.

Lembre-se de adicionar o usuário a outras funções, conforme necessário. Por exemplo, para permitir que o usuário gerencie as configurações do Intune, ele precisa ser um **Administrador Global** ou um **Administrador de Serviços do Intune**.

Também:

- Use https://portal.office.com para atribuir uma licença do Intune à sua conta de usuário.

- Atualize o código do aplicativo para autenticação no domínio de locatário do Azure AD do cliente, em vez de em seu próprio.

    Por exemplo, suponha que seu domínio de locatário seja `contosopartner.onmicrosoft.com` e que o domínio de locatário do cliente seja `northwind.onmicrosoft.com`. Assim, você deverá atualizar o código para autenticação no locatário do cliente.

    Para fazer isso em um aplicativo C# com base no exemplo anterior, altere o valor da variável `authority`:

    ``` csharp
    string authority = "https://login.microsoftonline.com/common/";
    ```

    como

    ``` csharp
    string authority = "https://login.microsoftonline.com/northwind.onmicrosoft.com/";
    ```
