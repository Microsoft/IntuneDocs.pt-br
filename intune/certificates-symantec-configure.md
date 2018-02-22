---
title: Emitir certificados PKCS do Symantec com o Intune
titlesuffix: Azure portal
description: "Instalar e configurar o Intune Certificate Connector para emitir Certificados PKCS do Serviço Web Symantec PKI Manager para dispositivos gerenciados pelo Intune"
keywords: 
author: MicrosoftGuyJFlo
ms.author: joflore
manager: dougeby
ms.date: 11/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5c02ea2df53b1524933cea72a8bcc3de89772e62
ms.sourcegitcommit: 0a5f424a8f683daa919b13b5c363173040d561c8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/13/2018
---
# <a name="set-up-intune-certificate-connector-for-symantec-pki-manager-web-service"></a>Configurar o Intune Certificate Connector para o Serviço Web Symantec PKI Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este artigo mostra como instalar e configurar o Intune Certificate Connector para emitir Certificados PKCS de um Serviço Web Symantec PKI Manager para dispositivos gerenciados pelo Intune.

O Serviço Web Symantec PKI Manager será chamado de AC Symantec neste artigo. Se você já configurou o Intune Certificate Connector para emitir Certificados SCEP e PKCS da AC (Autoridade de Certificação) da Microsoft, o mesmo Connector poderá ser usado para configurar e emitir Certificados PKCS de uma AC da Symantec. Nesse caso, o Intune Certificate Connector pode emitir os seguintes certificados:

* Certificados PKCS de uma AC da Microsoft
* Certificados SCEP de uma AC da Microsoft
* Certificados PKCS de uma AC da Symantec

Se você quiser usar o Intune Certificate Connector para a AC da Microsoft e da Symantec, conclua primeiro a configuração do Intune Certificate Connector para a AC da Microsoft e execute estas etapas para configurá-lo para a AC da Symantec.  Para obter mais detalhes sobre como configurar o Intune Certificate Connector para uma AC da Microsoft, consulte [Como configurar certificados com o Intune](certificates-configure.md).

## <a name="prepare-to-install-intune-certificate-connector"></a>Preparar-se para a instalação do Intune Certificate Connector

Se você já estiver usando o Intune Certificate Connector para uma AC da Microsoft existente, e quiser adicionar suporte à AC da Symantec, ignore esta etapa e continue com as etapas restantes após a instalação do Intune Certificate Connector mais recente no Portal de Administração do Intune. Esta etapa é necessária somente quando você deseja usar o Intune Certificate Connector para uma AC da Symantec autônoma.

1. Escolha uma das versões do sistema operacional Windows na lista a seguir e instale-o em um computador:
   * Windows Server 2012 R2 Datacenter
   * Windows Server 2012 R2 Standard
   * Windows Server 2016 Datacenter
   * Windows Server 2016 Standard

2. Crie um usuário com privilégios administrativos e use-o para concluir as etapas a seguir.

3. Atualize com as Windows Updates mais recentes e instale-as, se estiverem disponíveis.

   > [!IMPORTANT]
   > Depois de instalar as Windows Updates, reinicie o computador.

4. Instale o .NET Framework 3.5:

    a. Abra **Painel de Controle** > **Programas e Recursos** > **Ativar ou Desativar Recursos do Windows**

    b. Selecione **.NET Framework 3.5** e instale-o.

## <a name="install-the-symantec-registration-authorization-certificate"></a>Instalar o certificado de Autorização de Registro da Symantec

Use as etapas a seguir para obter o certificado de RA (Autorização de Registro) da AC da Symantec. Você deve ter uma assinatura ativa na AC da Symantec para obter o certificado de RA.

1. Salve o seguinte trecho de código como um arquivo chamado **certreq.ini** e atualize conforme o necessário (por exemplo: *Nome da entidade no formato CN*).

   ```
    [Version] 
    Signature="$Windows NT$" 

    [NewRequest] 
    ;Change to your,country code, company name and common name 
    Subject = "Subject Name in CN format"

    KeySpec = 1 
    KeyLength = 2048 
    Exportable = TRUE 
    MachineKeySet = TRUE 
    SMIME = False 
    PrivateKeyArchive = FALSE 
    UserProtected = FALSE 
    UseExistingKeySet = FALSE 
    ProviderName = "Microsoft RSA SChannel Cryptographic Provider" 
    ProviderType = 12 
    RequestType = PKCS10 
    KeyUsage = 0xa0 

    [EnhancedKeyUsageExtension] 
    OID=1.3.6.1.5.5.7.3.2 ; Client Authentication  // Uncomment if you need a mutual TLS authentication

    ;----------------------------------------------- 
   ```

2. Abra um prompt de comandos com privilégios elevados e gere o conteúdo do CSR usando o seguinte comando:

   `Certreq.exe -new certreq.ini request.csr`

3. Abra o arquivo request.csr no Bloco de Notas e copie o conteúdo do CSR, que está no seguinte formato:

    ```
    -----BEGIN NEW CERTIFICATE REQUEST-----
    MIID8TCCAtkCAQAwbTEMMAoGA1UEBhMDVVNBMQswCQYDVQQIDAJXQTEQMA4GA1UE
    …
    …
    fzpeAWo=
    -----END NEW CERTIFICATE REQUEST-----
    ```

4. Faça o logon na AC da Symantec e navegue até **Obter um certificado de RA** nas tarefas.

   a. Fornece o conteúdo do CSR da Etapa 3 na caixa de texto designada.

   b. Forneça o Nome Amigável do Certificado na caixa de texto designada.

   c. Clique em **Continue**.

      Isso mostra um link para download do Certificado de RA.

   d. Baixe o certificado de RA no computador local.

5. Importe o certificado de RA para o repositório de Certificados do Windows:

    a. Abra um console do MMC.

    b. Clique em **Arquivo** > **Adicionar ou Remover Snap-ins** > **Certificado** > e clique em **Adicionar**.

    c. Selecione **Conta do Computador** > e clique em **Avançar**.

    d. Selecione **Computador Local** e clique em **Concluir**.

    e. Clique em **OK** na janela **Adicionar ou Remover Snap-ins**. Expanda **Certificados (Computador Local)** > **Pessoal** > **Certificados**.

    f. Clique com o botão direito no nó **Certificados** e selecione **Todas as Tarefas** > **Importar**.

    g. Selecione o local do Certificado de RA que você baixou da AC da Symantec e clique em **Avançar**.

    h. Selecione **Repositório de Certificados Pessoais** e clique em **Avançar**.

    i. Clique em **Finalizar**. Isso importa o Certificado de RA para o repositório pessoal do computador local junto com sua chave privada.  

6. Exportar e importar o certificado de chave privada:

    a. Expanda **Certificados (Computador Local)** > **Pessoal** > **Certificados**.

    b. Selecione o certificado que foi importado na etapa anterior.

    c. Clique com o botão direito no certificado e escolha **Todas as Tarefas** > **Exportar**.

    d. Clique em **Avançar** e digite a senha.

    e. Selecione o local para exportar e clique em **Concluir**.

    f. Siga o mesmo procedimento na Etapa 5 para importar o certificado de chave privada para o repositório pessoal do computador Local.

7. Copie a impressão digital do Certificado de RA sem espaços.  Veja a seguir um exemplo de impressão digital:

   ```
   RA Cert Thumbprint: “EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5”
   ```


   > [!NOTE]
   > Se houver algum problema com a obtenção do Certificado de RA da AC da Symantec, entre em contato com o Atendimento ao cliente da Symantec.

## <a name="install-intune-certificate-connector"></a>Instalar o Intune Certificate Connector

Se você já estiver usando o Intune Certificate Connector mais recente de uma AC da Microsoft existente e quiser adicionar suporte à AC da Symantec, ignore esta etapa. Caso contrário, baixe o Intune Certificate Connector mais recente do portal de administração do Intune e siga estas instruções.

1. Entre em https://portal.azure.com usando suas credenciais de administrador de locatário do Intune e pesquisa os recursos do Intune.
2. Baixe NDESConnectorSetup.exe em **Microsoft Intune** > **Configuração do Dispositivo** > **Autoridade de Certificação** > **Baixar o link do conector de certificado**
3. Execute NDESConnectorSetup.exe com privilégios elevados.

    a. Na tela **Opções de Instalação**, selecione **Distribuição PFX**, conforme mostra a captura de tela a seguir.  Conclua a instalação restante com as seleções padrão.

   > [!IMPORTANT]
   > Se você quiser configurar o Intune Certificate Connector para emitir certificados de uma CA da Microsoft e de uma AC da Symantec, selecione **Distribuição de Perfil SCEP e PFX**. Conclua a instalação restante com as seleções padrão.

   ![InstallConnector][InstallConnector]
 
## <a name="configure-intune-certificate-connector"></a>Configurar o Intune Certificate Connector

O Intune Certificate Connector é instalado em `%ProgramFiles%\Microsoft Intune` por padrão.

1. Abra o arquivo %ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config no Bloco de Notas.

    a. Atualize o valor da chave RACertThumbprint com o valor de impressão digital do certificado que você copiou na seção anterior.  Veja este exemplo:

   ```
   <add key="RACertThumbprint"
   value="EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5"/>
   ```

    b. Salve e feche o arquivo.

2. Abra services.msc.

    a. Selecione **Serviço do Conector do Intune**.

    b. Interrompa o serviço e, depois, inicie o serviço.

    c. Feche a janela de Serviços.

## <a name="setup-the-intune-administrator-account"></a>Configurar a conta de administrador do Intune

Se você já estiver usando o Intune Certificate Connector de uma AC da Microsoft existente e quiser adicionar suporte à AC da Symantec, ignore esta etapa e continue com as etapas restantes. 

1. Inicie a interface do usuário do Conector NDES do ` %ProgramFiles%\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe `

    a. Clique na guia **Inscrição** e, depois, clique em **Entrar**.

    b. Forneça suas credenciais de administrador de locatário do Intune nas caixas de texto designadas.

    c. Clique em **Entrar**.  Isso exibirá uma caixa de diálogo de confirmação com uma mensagem **Inscrito com êxito**, conforme mostra a captura de tela a seguir.
2. Feche a interface do usuário do Conector do NDES.

![ConfigureConnector][ConfigureConnector]
 
## <a name="create-a-trusted-certificate-profile"></a>Criar um perfil de certificado confiável

Os Certificados PKCS implantados em dispositivos gerenciados pelo Intune devem ser encadeados com um Certificado Raiz Confiável. Isso exige que você crie um Perfil de Certificado Confiável do Intune com o certificado raiz obtido da AC da Symantec.

1. Obter um Certificado Raiz Confiável da AC da Symantec:

    a. Faça logon no Portal de Administração da AC da Symantec.

    b. Clique em Gerenciar ACs em Tarefas:

    c. Selecione a AC apropriada na lista de ACs.

    d. Clique em Baixar certificado de raiz para baixar o Certificado Raiz Confiável.

2. Crie um Perfil de Certificado Confiável no portal de administração do Intune:

    a. Entre no [Portal do Azure](https://portal.azure.com) usando as credenciais de administrador de locatário do Intune e pesquise por recursos do Intune.

    b. Criar um perfil de Certificado Confiável em **Microsoft Intune** > **Configuração do Dispositivo** - **Perfis** > **Criar perfil**

    c. Forneça as informações necessárias nos campos **Nome** e **Descrição**, depois selecione a plataforma de destino. 

    d. Selecione o Perfil de certificado confiável na lista suspensa de Tipo de perfil.

    e. Carregue o Certificado Raiz Confiável que você obteve da AC da Symantec na etapa anterior.

    f. Conclua as etapas restantes na criação do perfil. 

    g. Clique em **Atribuições** e selecione o grupo apropriado.  Pelo menos um usuário ou dispositivo deve fazer parte do grupo atribuído.

## <a name="get-the-certificate-profile-oid"></a>Obter o OID do Perfil de Certificado

O OID do Perfil de Certificado está associado a um modelo de Perfil de Certificado na AC da Symantec.  Para criar um perfil de Certificado PKCS no portal de administração do Intune, o nome do modelo de certificado deve ser fornecido na forma de um OID de Perfil de Certificado que está associado um modelo de Certificado na AC da Symantec.

1. Faça logon no Portal de Administração da AC da Symantec.
2. Clique em Gerenciar Perfis de Certificado.
3. Selecione o Perfil de Certificado que você deseja usar.
4. Copie o OID do Perfil de Certificado. Ele é semelhante ao exemplo a seguir:

   ```
   Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109 
   ```

   > [!NOTE]
   > Se houver algum problema com a obtenção do OID do Perfil de Certificado, entre em contato com o Atendimento ao cliente da Symantec.

## <a name="create-a-pkcs-certificate-profile"></a>Criar um Perfil de Certificado PKCS

1. Entre no [Portal do Azure](https://portal.azure.com) usando suas credenciais de administrador de locatário do Intune e pesquise por recursos do Intune.
2. Criar um perfil de Certificado PKCS em **Microsoft Intune** > **Configuração do Dispositivo - Perfis** > **Criar perfil** > **Certificado PKCS**.

    a. Forneça as informações necessárias nos campos **Nome** e **Descrição**, depois selecione a plataforma de destino.

    b. Selecione o **Perfil de certificado PKCS** na lista suspensa **Tipo de perfil**.  

    c. Conclua as etapas restantes para criar o perfil.

   ![ConfigureProfile][ConfigureProfile]

   > [!IMPORTANT]
   > Os seguintes parâmetros do Perfil de Certificado PKCS devem ser configurados com os valores especificados na tabela a seguir, conforme mostra a captura de imagem, a fim de emitir Certificados PKCS por meio do Intune Certificate Connector da AC da Symantec. 

    |Parâmetro de Certificado PKCS | Valor | Descrição |
    | --- | --- | --- |
    | Autoridade de certificação | pki-ws.symauth.com | Esse valor deve ser um FQDN de serviço base da AC da Symantec sem barras à direita.  Se você não tiver certeza se esse é o FQDN de serviço base correto para sua assinatura de AC da Symantec, contate com o Atendimento ao cliente da Symantec. <br><br> Se este FQDN estiver incorreto, o Intune Certificate Connector não emitirá Certificados PKCS da AC da Symantec.| 
    | Nome da autoridade de certificação | Symantec | Esse valor deve ser a cadeia de caracteres **Symantec**. <br><br> Se houver alguma alteração nesse valor, o Intune Certificate Connector não emitirá Certificados PKCS da AC da Symantec.|
    | Nome do modelo de certificado | OID do Perfil de Certificado da AC da Symantec. <br><br> Por exemplo: `2.16.840.1.113733.1.16.1.2.3.1.1.61904612`| Esse valor deve ser um OID de Perfil de Certificado obtido na seção anterior do modelo do Perfil de Certificado da AC da Symantec. <br><br> Se o Intune Certificate Connector não puder localizar um modelo de certificado associado a esse OID de Perfil de Certificado na AC da Symantec, ele não emitirá certificados PKCS da AC da Symantec.|

   > [!NOTE]
   > Os perfis de Certificado PKCS para plataformas do Windows não precisam ser associados a um perfil de Certificado Confiável. Mas isso é necessário para perfis que não são de plataformas do Windows, como Android.

3. Clique em **Atribuições** e selecione o grupo apropriado.  Pelo menos um usuário ou dispositivo deve fazer parte do grupo atribuído.
 
Depois de concluir as etapas anteriores, o Intune Certificate Connector emitirá certificados PKCS da AC da Symantec para dispositivos gerenciados pelo Intune no grupo atribuído. Esses certificados estarão disponíveis no repositório Pessoal do repositório de certificados do Usuário Atual no dispositivo gerenciado pelo Intune.

### <a name="pkcs-certificate-profile-supported-attributes"></a>Atributos com suporte de Perfil de Certificado PKCS

|Atributo | Formatos com suporte do Intune | Formatos com suporte da AC da Symantec Cloud | Result |
| --- | --- | --- | --- |
| Nome do assunto |O Intune dá suporte ao nome da entidade apenas nos três formatos a seguir: <br><br> 1. Nome comum <br> 2. Nome Comum inclui email <br> 3. Nome comum como email <br><br> Veja este exemplo: <br><br> `CN = IWUser0 <br><br> E = IWUser0@samplendes.onmicrosoft.com` | A AC da Symantec dá suporte a atributos adicionais.  Se você quiser selecionar atributos adicionais, eles deverão ser definidos com valores fixos no modelo de Perfil de Certificado da Symantec.| Usamos o Nome Comum ou email da solicitação de Certificado PKCS. <br><br> Qualquer incompatibilidade na seleção de atributos entre o Perfil de Certificado do Intune e do modelo de Perfil de Certificado da Symantec resulta na não emissão de qualquer certificado da AC da Symantec.|
| SAN | O Intune dá suporte apenas aos seguintes valores de campo de SAN: <br><br> AltNameTypeEmail <br><br> AltNameTypeUpn <br><br> AltNameTypeOtherName (valor codificado) | A AC da Symantec Cloud também dá suporte a esses parâmetros. Se você quiser selecionar atributos adicionais, eles deverão ser definidos com valores fixos no modelo de Perfil de Certificado da Symantec. <br><br> AltNameTypeEmail: se esse tipo não for encontrado no SAN, ele usará o valor de AltNameTypeUpn.  Se AltNameTypeUpn também não for encontrado no SAN, ele usará o valor do Nome da Entidade se estiver no formato de email.  Se ainda não for encontrado, o Intune Certificate Connector não emitirá os certificados. <br><br> Por exemplo: `RFC822 Name=IWUser0@ndesvenkatb.onmicrosoft.com`  <br><br> AltNameTypeUpn: se esse tipo não for encontrado no SAN, ele usará o valor de AltNameTypeEmail. Se AltNameTypeEmail também não for encontrado no SAN, ele usará o valor do Nome da Entidade se estiver no formato de email.  Se ainda não for encontrado, o Intune Certificate Connector não emitirá os certificados.  <br><br> Por exemplo: `Other Name: Principal Name=IWUser0@ndesvenkatb.onmicrosoft.com` <br><br> AltNameTypeOtherName: se esse tipo não for encontrado no SAN, o Intune Certificate Connector não emitirá os certificados. <br><br> Por exemplo: `Other Name: DS Object Guid=04 12 b8 ba 65 41 f2 d4 07 41 a9 f7 47 08 f3 e4 28 5c ef 2c` <br><br>  **Observação importante:** o valor desse campo só tem suporte da AC da Symantec no formato codificado (valor hexadecimal). Portanto, para qualquer valor nesse campo, o Intune Certificate Connector o converte em codificado em base 64 antes de enviar a solicitação de certificado. **O Intune Certificate Connector não valida se este valor já está codificado ou não.** | Nenhum |

## <a name="troubleshooting"></a>Solução de problemas

Os logs do serviço Intune Certificate Connector estão disponíveis em `%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\Logs\Logs` no computador do Conector NDES. Abra os logs no [SvcTraceViewer](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) e procure por mensagens de erro ou exceções.

| Problema/Mensagem de erro | Etapas de resolução |
| --- | --- |
| Não é possível entrar com a conta de administrador de locatário do Intune na interface do usuário do Conector NDES | Isso pode acontecer quando o Certificate Connector local não está habilitado no portal de administração do Intune. Para solucionar o problema, execute as seguintes etapas: <br><br> Da interface do usuário do Silverlight: <br> 1. Faça logon no [portal de administração do Intune](https://admin.manage.microsoft.com) <br> 2. Clique em ADMINISTRADOR <br> 3. Selecione Gerenciamento de Dispositivo Móvel > Certificate Connector <br> 4. Clique em **Configurar Certificate Connector Local** <br> 5. Marque a caixa de seleção **Habilitar Certificate Connector** <br> 6. Clique em **OK**. <br><br>Ou <br><br> Na interface do usuário do Portal do Azure: <br> 1. Entre no [Portal do Azure](https://portal.azure.com) <br> 2. Acesse o Microsoft Intune <br> 3. Selecione **Configuração do Dispositivo** > **Autoridade de Certificação** <br> 4. Clique em **Habilitar**. <br><br> Depois de concluir as etapas anteriores na interface do usuário do Silver Light ou do Portal do Azure, tente entrar com a mesma conta de administrador de locatário do Intune na interface do usuário do Conector NDES. |
| Não foi possível encontrar o certificado do Conector NDES. <br><br> System.ArgumentNullException: o valor não pode ser nulo. | O Intune Certificate Connector mostra esse erro se a conta de administrador de locatário do Intune nunca tiver entrado na interface do usuário do Conector NDES. <br><br> Se esse erro persistir, reinicie o Serviço Intune Connector. <br><br> 1. Abra services.msc <br> 2. Selecione **Serviço do Conector do Intune**. <br> 3. Clique com o botão direito e selecione **Reiniciar**.|
| Conector NDES - IssuePfx -Generic Exception: <br> System.NullReferenceException: a referência de objeto não está definida em uma instância de um objeto. | Esse erro é transitório. Reinicie o Serviço Intune Connector. <br><br> 1. Abra services.msc <br> 2. Selecione **Serviço do Conector do Intune** <br> 3. Clique com o botão direito e selecione **Reiniciar**. |
| Provedor do Symantec - falha ao obter a política da Symantec "A operação expirou" | O Serviço Intune Connector recebeu um erro de tempo limite da operação durante a comunicação com a AC da Symantec. Se esse erro persistir, aumente o valor de tempo limite da conexão e tente novamente. <br><br> Para aumentar o tempo limite da conexão: <br> 1. Acesse o computador do Conector NDES. <br>2. Abra o arquivo `%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config` no Bloco de notas. <br> 3. Aumente o valor de tempo limite para o seguinte parâmetro: <br><br> `CloudCAConnTimeoutInMilliseconds` <br><br> 4. Reinicie o Serviço do Conector do Intune. <br><br> Se o problema persistir, entre em contato com o Atendimento ao cliente da Symantec. |
| Provedor da Symantec - Falha ao obter o certificado de cliente | O Serviço Intune Connector não conseguiu recuperar o Certificado de Autorização de Recurso do repositório de certificados pessoais do computador Local. Para resolver esse problema, instale o Certificado de Autorização de Recursos no repositório de certificados pessoais do computador local junto com sua chave privada. <br><br> **Observação:** o Certificado de Autorização de Recursos deve ser obtido da AC da Symantec. Para obter mais detalhes, entre em contato com o Atendimento ao cliente da Symantec. | 
| Provedor da Symantec - falha ao obter a política da Symantec "A solicitação foi anulada: não foi possível criar o canal seguro de SSL/TLS." | Esse erro ocorre nos seguintes cenários: <br><br> 1. O serviço Intune Certificate Connector não tem permissões suficientes para ler o certificado de Autorização de Recursos junto com sua chave privada do repositório de certificados pessoais do computador Local. Para resolver esse problema, verifique a conta de contexto em execução do serviço Connector em services.msc. O serviço Connector deve ser executado no contexto NT AUTHORITY\SYSTEM. <br><br> 2. O perfil do Certificado PKCS no portal de administração do Intune pode estar configurado com um FQDN do serviço de base da AC da Symantec inválido. O FQDN é semelhante a `pki-ws.symauth.com`. Para resolver esse problema, verifique com o atendimento ao cliente da Symantec se a URL está correta para sua assinatura. <br><br> 3. O Intune Certificate Connector não consegue autenticar com a AC da Symantec usando o certificado de Autorização de Recurso, pois não consegue recuperar sua chave privada. Para resolver esse problema, instale o certificado de Autorização de Recursos, junto com sua chave privada, no repositório de certificados pessoais do computador local. <br><br> Se o problema persistir, entre em contato com o Atendimento ao cliente da Symantec. |
| Provedor da Symantec - falha ao obter a política da Symantec "Um elemento de solicitação não foi compreendido". | O Intune Certificate Connector não conseguiu obter o modelo de Perfil de Certificado da Symantec, pois o OID do Perfil de Cliente não coincide com o Perfil de Certificado do Intune. Em outro caso, o Intune Certificate Connector não consegue localizar o modelo de perfil de certificado que está associado ao OID do Perfil de Cliente fornecido na AC da Symantec. <br><br> Para resolver esse problema, obtenha o OID do Perfil de Cliente correto do modelo de Certificado da Symantec na CA da Symantec. Em seguida, atualize o perfil do Certificado PKCS no portal de administração do Intune. <br><br> Obtenha o OID do Perfil de Cliente da AC da Symantec: <br> 1. Faça logon no Portal de Administração da AC da Symantec. <br> 2. Clique em Gerenciar Perfis de Certificado <br> 3. Selecione o Perfil de Certificado que você pretende usar. <br> 4. Obtenha o OID do Perfil de Certificado. Ele é semelhante ao exemplo a seguir: <br> `Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109` <br><br> Atualize o perfil de Certificado PKCS com OID de Perfil de Certificado correto: <br>1. Faça logon no portal de administração do Intune <br> 2. Acesse o Perfil de Certificado PKCS e clique em **Editar**. <br> 3. Atualize o OID do Perfil de Certificado na atualização no campo de nome do Modelo de Certificado. <br> 4. Salve o Perfil de Certificado PKCS. |
| Provedor da Symantec - falha na verificação da política. <br><br> O atributo não entra na lista de atributos do modelo de certificado com suporte da Symantec | A AC da Symantec mostra esta mensagem quando há discrepância entre o modelo do Perfil de Certificado da Symantec e o Perfil de Certificado do Intune. Esse problema provavelmente ocorreu devido à incompatibilidade do atributo em SubjectName ou SubjectAltName. <br><br> Para resolver esse problema, selecione os atributos com suporte do Intune para SubjectName e SubjectAltName no modelo de Perfil de Certificado da Symantec. Para saber mais, consulte os atributos com suporte do Intune na seção de Parâmetros de Certificado. |
| Alguns dispositivos de usuário não estão recebendo certificados PKCS da AC da Symantec. | Esse problema ocorre quando o UPN do Usuário contém caracteres especiais, como sublinhado (exemplo: `global_admin@intune.onmicrosoft.com`). <br><br> A AC da Symantec não oferece suporte a caracteres especiais em mail_firstname e mail_lastname. <br><br> As etapas a seguir ajudam a resolver esse problema: <br><br> 1.   Faça logon no Portal de Administração da AC da Symantec. <br> 2. Acesse Gerenciar Perfis de Certificado. <br> 3.   Clique no Perfil de Certificado usado para o Intune. <br> 4.  Clique no link Personalizar opções. <br> 5.   Clique no botão Opções avançadas. <br> 6.  Nos campos Certificado – DN do Assunto, adicione o campo Nome Comum (CN) e exclua o campo Nome Comum (CN) existente. A adição e a exclusão devem ser executadas juntas. <br> 7.    Clique em Salvar. <br><br> Com a alteração anterior, o perfil de Certificado da Symantec solicita "CN =<upn>" em vez de mail_firstname e mail_lastname. |
| Usuário excluído manualmente já implantou o certificado do dispositivo. | O Intune reimplanta o mesmo certificado durante o próximo check-in ou imposição da política. Nesse caso, o Conector de NDES não recebe uma solicitação de Certificado PKCS. |

## <a name="next-steps"></a>Próximas etapas

- Use as informações fornecidas neste artigo, além das informações em [O que são perfis de dispositivo do Microsoft Intune?](device-profiles.md) para gerenciar os dispositivos de sua organização e os certificados contidos neles.

[InstallConnector]:  ./media/certificates-symantec-connector-install.png "Instalar o Intune Certificate Connector e selecionar a Distribuição PFX"
[ConfigureConnector]: ./media/certificates-symantec-configure-connector-configure.png "Configurar o Intune Certificate Connector"
[ConfigureProfile]: ./media/certificates-symantec-pkcs-example.png "Criar perfil de Certificado PKCS no Portal do Azure"
