---
title: Autenticação somente no aplicativo Intune Data Warehouse
titleSuffix: Microsoft Intune
description: Este tópico descreve a autenticação somente no aplicativo do Data Warehouse.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d7166563-6bb5-4624-b8c8-6b300a997c3a
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a8e386e2d9b161debf65d3e639a90cb8de313ad2
ms.sourcegitcommit: bea4a81d262607c6e9dd1e26f5cd1a2faf7d051b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45602275"
---
# <a name="intune-data-warehouse-application-only-authentication"></a>Autenticação somente no aplicativo Intune Data Warehouse

Você pode configurar um aplicativo usando o Azure Active Directory (Azure AD) e autenticar para o Intune Data Warehouse. Este processo é útil para sites, aplicativos e processos em segundo plano em que o aplicativo não deve ter acesso às credenciais do usuário. Usando as etapas a seguir, você autoriza seu aplicativo com o Azure AD usando OAuth 2.0.

## <a name="authorization"></a>Authorization

O Azure Active Directory (Azure AD) usa OAuth 2.0 para que você possa autorizar o acesso a aplicativos Web e APIs Web em seu locatário do Azure AD. Este guia mostra como autenticar seu aplicativo usando C#. O fluxo de código de autorização OAuth 2.0 é descrito na seção 4.1 da especificação do OAuth 2.0. Para obter mais informações, consulte [Autorizar o acesso a aplicativos Web usando o OAuth 2.0 e o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).


## <a name="azure-keyvault"></a>Azure KeyVault

O processo a seguir usa um método particular para processar e converter uma chave de aplicativo. Este método particular foi denominado SecureString. Como alternativa, você pode usar o Azure KeyVault para armazenar a chave do aplicativo. Para saber mais, confira [Key Vault](https://azure.microsoft.com/services/key-vault/).

## <a name="create-a-web-app"></a>Criar um aplicativo Web

Nesta seção, você fornece detalhes sobre o aplicativo Web que deseja destacar no Intune. Um aplicativo Web é um aplicativo cliente-servidor. O servidor fornece o aplicativo Web, que inclui a interface do usuário, o conteúdo e a funcionalidade. Este tipo de aplicativo é mantido separadamente na Web. Você usa o Intune para conceder um acesso de aplicativo Web ao Intune. O fluxo de dados é iniciado pelo aplicativo Web. 

1.  Entre no [Portal do Azure](https://portal.azure.com).
2.  Usando o campo **Pesquisar recursos, serviços e documentos** próximo à parte superior do Portal do Azure, procure pelo **Azure Active Directory**.
3.  No menu suspenso, selecione **Azure Active Directory** em **Serviços**.
4.  Selecione **Registros de aplicativo**.
5.  Clique em **Novo Registro do Aplicativo** para exibir a folha **Criar**.
6.  Na folha **Criar**, adicione os detalhes do aplicativo:

    - Um nome de aplicativo, como *Intune App-Only Auth*.
    - O **Tipo de Aplicativo**. Escolha **Aplicativo Web/API** para adicionar um aplicativo que represente um aplicativo Web, uma API da Web ou ambos.
    - A **URL de Entrada** do aplicativo. Este é o local em que os usuários navegam automaticamente durante o processo de autenticação. Eles devem provar que eles são quem eles dizem que são. Para saber mais, confira [O que é acesso ao aplicativo e logon único com o Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)

7.  Clique em **Criar** na parte inferior da folha **Criar**.

    >[!NOTE] 
    > Copie a **ID do Aplicativo** da folha **Aplicativo Registrado** para uso futuro.

## <a name="create-a-key"></a>Criar uma chave

Nesta seção, o Azure AD gera um valor-chave para o seu aplicativo.

1.  Na folha **Registros de Aplicativo**, selecione o aplicativo recém-criado para exibir a folha do aplicativo.
2.  Selecione **Configurações** na parte superior da folha para exibir a folha **Configurações**.
3.  Selecione **Chaves** na folha **Configurações**.
4.  Adicione a **Descrição** da chave, uma duração para **Expira** e o **Valor** para a chave.
5.  Clique em **Salvar** para salvar e atualizar chaves do aplicativo.
6.  Você deve copiar o valor da chave gerada (codificado em base64).

    >[!NOTE] 
    > O valor da chave desaparece depois que você sai da folha **Teclas**. Você não pode recuperar a chave desta folha posteriormente. Copie-a para uso posterior.

## <a name="grant-application-permissions"></a>Adicionar permissões de aplicativo

Nesta seção, você deve conceder permissões para os aplicativos.

1.  Selecione **Permissões necessárias** na folha **Configurações**.
2.  Clique em **Adicionar**.
3.  Selecione **Adicionar uma API** para exibir a folha **Selecionar uma API**.
4.  Selecione **API do Microsoft Intune (MicrosoftIntuneAPI)** e, em seguida, clique em **Selecionar** na folha **Selecionar uma API**. A etapa **Selecionar Permissões** está selecionada e a folha **Habilitar Acesso** é exibida.
5.  Escolha a opção **Obter informações do data warehouse do Microsoft Intune** na seção **Permissões do Aplicativo**.
6.  Clique em **Selecionar** na folha **Habilitar Acesso**.
7.  Clique em **Concluído** na folha **Adicionar acesso à API**.
8.  Clique em **Conceder Permissões** na folha **Permissões Necessárias** e clique em **Sim** quando promovido para atualizar quaisquer permissões existentes deste aplicativo.

## <a name="generate-token"></a>Gerar o token

Usando o Visual Studio, crie um projeto de aplicativo do Console (.NET Framework) que suporte o .NET Framework e usa c# como a linguagem de codificação.

1.  Selecione **Arquivo** > **Novo** > **Projeto** para exibir a caixa de diálogo **Novo Projeto**.
2.  À esquerda, selecione **Visual C#** para exibir todos os projetos .NET Framework.
3.  Selecione **Aplicativo do Console (.NET Framework)**, adicione um nome de aplicativo e, em seguida, clique em **OK** para criar o aplicativo.
4.  No **Gerenciador de Soluções**, selecione **Program.cs** para exibir o código.
5.  No menu pop-up, selecione **Adicionar** > **Novo item**. A caixa de diálogo **Adicionar Novo Item** é exibida.
6.  À esquerda, em **Visual C#**, selecione **Código**.
7.  Selecione **Classe**, altere o nome da classe para *IntuneDataWarehouseClass.cs* e clique em **Adicionar**.
8.  Adicione o seguinte código ao método <code>Main</code>:

    ``` csharp
         var applicationId = ConfigurationManager.AppSettings["appId"].ToString();
         SecureString applicationSecret = ConvertToSecureStr(ConfigurationManager.AppSettings["appKey"].ToString()); // Load as SecureString from configuration file or secret store (i.e. Azure KeyVault)
         var tenantDomain = ConfigurationManager.AppSettings["tenantDomain"].ToString();
         var adalContext = new AuthenticationContext($"https://login.windows.net/" + tenantDomain + "/oauth2/token");
    
         AuthenticationResult authResult = adalContext.AcquireTokenAsync(
             resource: "https://api.manage.microsoft.com/",
             clientCredential: new ClientCredential(
                 applicationId,
                 new SecureClientSecret(applicationSecret))).Result;
    ``` 

9. Insira espaços de nome adicionais adicionando o seguinte código na parte superior do arquivo de código:

    ``` csharp
     using System.Security;
     using Microsoft.IdentityModel.Clients.ActiveDirectory;
     using System.Configuration;
    ``` 

10. Após o método <code>Main</code>, adicione o seguinte método particular para processar e converter a chave do aplicativo:

    ``` csharp
    private static SecureString ConvertToSecureStr(string appkey)
    {
        if (appkey == null)
            throw new ArgumentNullException("AppKey must not be null.");
    
        var secureAppKey = new SecureString();
    
        foreach (char c in appkey)
            secureAppKey.AppendChar(c);
    
        secureAppKey.MakeReadOnly();
        return secureAppKey;
    }
    ```

11. No **Gerenciador de Soluções**, clique com o botão direito em **Referências** e, em seguida, selecione **Gerenciar Pacotes NuGet**.
12. Procure por *Microsoft.IdentityModel.Clients.ActiveDirectory* e instale o pacote Microsoft NuGet relacionado.
13. No **Gerenciador de Soluções**, selecione e abra o arquivo *App.config*.
14. Adicione a seção <code>appSettings</code> para que o xml apareça da seguinte maneira:

    ``` xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup> 
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <appSettings>
          <add key="appId" value="App ID created from 'Create a Web App' procedure"/>
          <add key="appKey" value="Key created from 'Create a key' procedure" />
          <add key="tenantDomain" value="contoso.onmicrosoft.com"/>
        </appSettings>
    </configuration>
    ``` 

15. Atualize os valores <code>appId</code>, <code>appKey</code> e <code>tenantDomain</code> para combinar seus valores exclusivos relacionados ao aplicativo.
16. Compile seu aplicativo.

    >[!NOTE] 
    > Para ver o código de implementação adicional, confira [Exemplo de código Intune-Data-Warehouse](https://github.com/Microsoft/Intune-Data-Warehouse/tree/master/Samples/CSharp ).

## <a name="next-steps"></a>Próximas etapas
Saiba mais sobre o Azure Key Vault conferindo [O que é o Azure Key Vault?](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)

