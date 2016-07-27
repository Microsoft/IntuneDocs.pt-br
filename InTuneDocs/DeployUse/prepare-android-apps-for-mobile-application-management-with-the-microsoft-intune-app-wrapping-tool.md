---
title: "Encapsular aplicativos Android com a Ferramenta de Disposição do Aplicativo | Microsoft Intune"
description: "Use as informações neste tópico para aprender a encapsular seus aplicativos Android sem modificar o código do aplicativo em si. Prepare os aplicativos para que você possa aplicar políticas de gerenciamento de aplicativo móvel."
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 07/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: matgates
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c72c8e1a764af73ba4d421ca6637ee91ab7bca0a
ms.openlocfilehash: 76ee04237d54b4c171df74e8c134f003bbc32966


---

# Preparar aplicativos Android para o gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune
Use a **Ferramenta de encapsulamento de aplicativos do Microsoft Intune para Android** para modificar o comportamento de aplicativos Android internamente e configurar as funcionalidades do aplicativo sem modificar seu código.

A ferramenta é um aplicativo de linha de comando do Windows que é executado no PowerShell e cria um “wrapper” em torno de seu aplicativo. Após o aplicativo ser processado, você pode alterar sua funcionalidade usando [políticas de gerenciamento de aplicativo móvel](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) que você configurar.

Se seu aplicativo estiver usando a ADAL (Biblioteca Azure Active Directory), você deverá executar as etapas em [Como encapsular aplicativos que usam a Informações para aplicativos que usam a Biblioteca do Azure Active Directory](#how-to-wrap-apps-that-use-the-azure-active-directory-library) antes de encapsular o aplicativo. Se você não tiver certeza se seu aplicativo usa essa biblioteca, contate o desenvolvedor do aplicativo.

Antes de executar a ferramenta, consulte [Security considerations for running the app wrapping tool (Considerações de segurança para executar a ferramenta de encapsulamento de aplicativos)](#security-considerations-for-running-the-app-wrapping-tool). Para baixar a ferramenta, consulte [Microsoft Intune App Wrapping Tool for Android - Português (Brasil)](https://www.microsoft.com/download/details.aspx?id=47267).

## Etapa 1: Cumprir os pré-requisitos para usar a ferramenta de encapsulamento de aplicativos

-   Você deve executar a ferramenta de encapsulamento de aplicativos em um computador Windows executando o Windows 7 ou posterior.

-   Seu aplicativo de entrada deve ser um pacote de aplicativo Android válido com o arquivo de extensão **.apk** e:

    -   Não pode ser criptografado

    -   Não pode já ter passado pelo encapsulamento pela ferramenta de quebra de texto do aplicativo

    -   Deve ser escrito para o Android 4.0 ou posterior

-   O aplicativo deve ser desenvolvido por ou para a sua empresa. Você não pode usar essa ferramenta para processar aplicativos baixados da Google Play Store.

-   Para executar a ferramenta de encapsulamento de aplicativos, você deve instalar a versão mais recente do [Java Runtime Environment](http://java.com/download/) e certificar-se de que a variável de caminho do Java tenha sido definida como **C:\ProgramData\Oracle\Java\javapath** em suas variáveis de ambiente do Windows. Para obter mais ajuda, consulte sua [documentação do Java](http://java.com/download/help/).

    > [!NOTE]
    > Em alguns casos, a versão de 32 bits do Java pode resultar em problemas de memória. Recomendamos que você instale a versão de 64 bits.

## Etapa 2: Instalar a ferramenta de encapsulamento de aplicativos

1.  No Centro de Download da Microsoft, baixe e abra o arquivo de instalação da ferramenta de encapsulamento de aplicativos em um computador com Windows.

2.  Aceite o contrato de licença e conclua a instalação.

Anote a pasta na qual você instalou a ferramenta. O local padrão é: **C:\Arquivos de Programas (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## Etapa 3: Executar a ferramenta de encapsulamento de aplicativos

1.  No computador Windows em que você instalou a App Wrapping Tool, abra uma janela do PowerShell no modo de administrador.

2.  Da pasta onde instalou a ferramenta, importe o módulo do PowerShell da ferramenta de encapsulamento de aplicativos:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Execute a ferramenta usando o comando **invoke-AppWrappingTool** com um ou mais dos parâmetros a seguir. Parâmetros que são marcados como "opcional" são aplicativos que usam o Azure Active Directory Library (ADAL). Para obter mais informações, consulte [Como encapsular aplicativos que usam a Biblioteca do Azure Active Directory](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

|Parâmetro|Mais informações|Exemplos|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Caminho do aplicativo Android de origem (.apk).| |
|**-OutputPath**&lt;String&gt;|Caminho para o aplicativo Android de "saída". Se esse for o mesmo caminho do diretório que InputPath, o pacote falhará.| |
|**-KeyStorePath**&lt;String&gt;|Caminho para o arquivo de armazenamento de chaves que contém o par de chaves pública/privada para a assinatura.| |
|**-KeyStorePassword**&lt;SecureString&gt;|Senha usada para descriptografar o armazenamento de chave. O Android requer que todos os pacotes de aplicativos (.apk) sejam assinados. Use a Ferramenta de Chave Java para gerar o KeyStorePassword como mostrado no exemplo. Leia mais sobre [keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html).|keytool.exe -genkey -v -keystore keystorefile -alias ks -keyalg RSA -keysize 2048 -validity 50000 |
|**-KeyAlias**&lt;String&gt;|Nome da chave a ser usada para assinatura.| |
|**-KeyPassword**&lt;SecureString&gt;|Senha usada para descriptografar a chave privada que será usada para a assinatura.| |
|**-SigAlg**&lt;SecureString&gt;|Nome do algoritmo de assinatura a ser usado para assinatura. O algoritmo deve ser compatível com a chave privada.|Exemplos: SHA256withRSA, SHA1withRSA, MD5withRSA|
|**-ClientID**&lt;GUID&gt;|ID do Cliente do Active Directory do Azure do aplicativo de entrada (opcional).| |
|**-AuthorityURI**&lt;Uri&gt;|URI de Autoridade do Active Directory do Azure do aplicativo de entrada (opcional).| |
|**-SkipBroker**&lt;Boolean&gt;|Indica se o aplicativo de entrada dá suporte ao logon único agenciado em todo o dispositivo (opcional). |**True** - O aplicativo de entrada não dá suporte ao logon único agenciado em todo o dispositivo. Use o parâmetro NonBrokerRedirectURI. **False** - O aplicativo de entrada dá suporte ao logon único agenciado em todo o dispositivo|
|**-NonBrokerRedirectURI**&lt;URI&gt;|URI de Redirecionamento do Active Directory do Azure para usar se SkipBroker for true (opcional).|  |


**&lt;CommonParameters&gt;**
 (opcional – dá suporte a parâmetros comuns do PowerShell como verbose, debug etc.)

- Para obter uma lista de parâmetros comuns, consulte o [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Para ver a ajuda da ferramenta, digite o comando:

    ```
    Help Invoke-AppWrappingTool
    ```
- Para obter mais informações sobre a integração do AAD (Azure Active Directory), consulte [Como encapsular aplicativos que usam a Biblioteca do Azure Active Directory](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

**Exemplo:**


    Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
    invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app.wrapped\HelloWorld_wrapped2.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\keystorefile" -keyAlias ks -SigAlg SHA1withRSA -Verbose

Serão solicitadas a **KeyStorePassword** e a **KeyPassword**.

O aplicativo encapsulado é gerado e salvo, junto com um arquivo de log, no caminho de saída especificado.

## Considerações de segurança para executar a ferramenta de encapsulamento de aplicativos
Para evitar potenciais falsificações, divulgações de informações e aumento de ataques de privilégio:

-   Certifique-se de que o aplicativo de linha de negócios de entrada, o aplicativo de saída e o Armazenamento de Chaves Java estejam no mesmo computador onde a ferramenta de encapsulamento de aplicativos está sendo executado.

-   Importe o aplicativo de saída para o console do Intune no mesmo computador em que a ferramenta está em execução. Consulte [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) para obter mais informações sobre o keytool Java.

-   Se o aplicativo de saída e a ferramenta estiverem em um caminho de UNC e você não estiver executando a ferramenta e os arquivos de entrada no mesmo computador, configure o ambiente para ser protegido usando [IPsec (Internet Protocol Security)](http://en.wikipedia.org/wiki/IPsec) ou [Assinatura SMB (Server Message Block)](https://support.microsoft.com/en-us/kb/887429).

-   Certifique-se de que o aplicativo seja proveniente de uma fonte confiável, especialmente se você estiver usando o AAD (Azure Active Directory), que pode permitir que o aplicativo acesse o token do AAD durante o tempo de execução.

-   Proteja o diretório de saída que contém o aplicativo encapsulado. Considere usar um diretório de nível de usuário para a saída.

## Como encapsular aplicativos que usam a Informações para aplicativos que usam a Biblioteca do Azure Active Directory
Se seu aplicativo estiver usando a Azure Active Directory Authentication Library (ADAL), você deve executar as etapas em antes de encapsular o aplicativo.

### Etapa 1: Verifique se você atende os requisitos da ADAL
Para aplicativos que usam a ADAL, as afirmações seguir devem ser verdadeiras:

-   O aplicativo deve incorporar uma versão da ADAL maior que ou superior à 1.0.2.

-   O desenvolvedor deve conceder acesso ao aplicativo para o recurso do Gerenciamento de Aplicativo Móvel do Intune, conforme descrito na [Etapa 3: Configurar o acesso ao gerenciamento de aplicativo móvel no AAD](#step-3-configure-access-to-mobile-app-management-in-aad).

### Etapa 2: Examinar os identificadores que você precisa obter ao registrar o aplicativo
Na próxima etapa, você usará o portal de gerenciamento do Azure para registrar seus aplicativos (os quais estão usando a ADAL com o AAD (Active Directory do Azure)) para obter os identificadores exclusivos listados na tabela a seguir. Em seguida, você fornece os identificadores ao desenvolvedor ao integrar a ADAL ao aplicativo.

|Identificador|Mais informações|Valor padrão|
|--------------|--------------------|-----------------|
|**ID do Cliente**|Um identificador GUID exclusivo que é gerado para o aplicativo após ele ser registrado com o AAD.<br /><br />Se você souber a ID do Cliente do aplicativo, especifique esse valor. Caso contrário, use o valor padrão.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**URI de Autoridade**|A valor de URI (Uniform Resource Identifier) para objetos AAD, (por exemplo, usuários e grupos).<br /><br />O parâmetro AuthorityURI é opcional para a ferramenta de disposição do aplicativo. O URI padrão será usado se você não usar o parâmetro.||
|**SkipBroker**|Valor que indica se o portal da empresa será usado como um agente.<br /><br />**True** – O portal da empresa não será usado para autenticação ADAL.<br /><br />**False** – O portal da empresa será usado para autenticação ADAL. O portal da empresa está usando o usuário registrado para fins de Logon Único.||
|**URI de Redirecionamento sem Agente**|URI de logon a ser usado quando a ADAL não usar o aplicativo do agente (portal da empresa do Intune).|urn:ietf:wg:oauth:2.0:oob|
|**ID do Recurso**|Ponteiro para os recursos do AAD do aplicativo.||

### Etapa 3: Configurar o acesso ao gerenciamento de aplicativo móvel no AAD
Antes de usar os valores de registro do AAD do aplicativo na ferramenta de disposição do aplicativo, o desenvolvedor do aplicativo deverá conceder ao aplicativo acesso ao recurso do Gerenciamento de Aplicativo Móvel do Intune seguinte as etapas a seguir:

1.  Faça logon em uma conta existente do AAD no portal de gerenciamento do Azure.

2.  Clique em **existing LOB application registration (registro de aplicativo LOB existente)**.

3.  Na seção para **configurar** , escolha **Configurar o Acesso às APIs da Web em outros aplicativos**.

4.  Na primeira lista suspensa na seção **Permission to other applications (Permissão para outros aplicativos)**, escolha **Gerenciamento de Aplicativo Móvel do Intune**.

Agora você pode usar a ID do Cliente do aplicativo na ferramenta de disposição do aplicativo. Você pode encontrar a ID do Cliente no portal de gerenciamento do Azure Active Directory conforme descrito na tabela na [Etapa 2: Examinar os identificadores que você precisa obter ao registrar o aplicativo](#step-2-review-the-identifiers-you-need-to-get-when-you-register-the-app).

### Etapa 4: Usar os valores do identificador do AAD na ferramenta de encapsulamento de aplicativos
Usando os valores do identificador que você obteve no processo de registro, insira os valores como propriedades de linha de comando na ferramenta de disposição do aplicativo. Você deve especificar todos os valores na tabela para que os usuários finais autentiquem o aplicativo com êxito. Os valores padrão serão usados se você não especificar um valor.

|Identificador|Parâmetro|
|--------------|-------------|
|ID do Cliente|ClientID|
|URI de Autoridade|URI de Autoridade|
|SkipBroker|SkipBroker|
|URI de Redirecionamento sem Agente|NonBrokerRedirectURI|
|ID do Recurso|ResourceID|
Lembre-se dos pontos a seguir ao encapsular seu aplicativo:

-   Para verificar se a autenticação foi bem-sucedida, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] busca o token do AAD associado à ID de recurso do MAM. No entanto, o token não é usado em qualquer chamada que, por sua vez, verificaria a validade do token. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] apenas lê o nome UPN do usuário conectado para determinar o acesso do aplicativo. O token do AAD não é usado para outras chamadas de serviço.

-   Prompts de logon duplo são impedidos se você fornecer a ID do Cliente do aplicativo cliente e o URI de Autoridade. Você precisa registrar esta ID do Cliente para permitir que ela acesse a ID de recursos de MAM do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] publicada no Painel do AAD. Se você não registrar a ID do Cliente, os usuários obterão uma falha de logon quando o aplicativo for executado.


### Consulte também
- [Decidir como preparar aplicativos para o gerenciamento de aplicativos móveis com o Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Use o SDK para habilitar aplicativos para o gerenciamento de aplicativos móveis](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Jul16_HO3-->


