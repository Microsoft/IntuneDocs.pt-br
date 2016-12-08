---
title: "Encapsular aplicativos Android com a Ferramenta de Disposição do Aplicativo | Microsoft Intune"
description: "Use as informações neste artigo para aprender a encapsular seus aplicativos Android sem alterar o código do aplicativo em si. Prepare os aplicativos para que você possa aplicar políticas de gerenciamento de aplicativo móvel."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 7c61ad6a3122793ddd66547b7040f978705b540c


---

# <a name="prepare-android-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>Preparar aplicativos Android para o gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune

Use a Ferramenta de Disposição do Aplicativo do Microsoft Intune para Android para alterar o comportamento dos aplicativos iOS internos restringindo as funcionalidades do aplicativo sem alterar seu código.

A ferramenta é um aplicativo de linha de comando do Windows que é executado no PowerShell e cria um wrapper em torno de seu aplicativo Android. Após o aplicativo ser encapsulado, você pode alterar sua funcionalidade configurando as [políticas de gerenciamento de aplicativo móvel](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) no Intune.


Antes de executar a ferramenta, consulte [Considerações de segurança para executar a Ferramenta de Disposição do Aplicativo](#security-considerations-for-running-the-app-wrapping-tool). Para baixar a ferramenta, acesse [Ferramenta de Disposição do Aplicativo do Microsoft Intune para Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) no GitHub.



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Cumprir os pré-requisitos para usar a Ferramenta de Disposição do Aplicativo

-   Você precisa executar a Ferramenta de Disposição do Aplicativo em um computador Windows executando o Windows 7 ou posterior.

-   Seu aplicativo de entrada deve ser um pacote de aplicativo Android válido com a extensão de arquivo .apk e:

    -   Ele não pode ser criptografado.
    -   Ele não pode ter passado por encapsulamento pela Ferramenta de Disposição do Aplicativo do Intune.
    -   Ele deve ser escrito para Android 4.0 ou posterior.

-   O aplicativo deve ser desenvolvido por ou para a sua empresa. Você não pode usar essa ferramenta para processar aplicativos baixados da Google Play Store.

-   Para executar a Ferramenta de Disposição do Aplicativo, você deve instalar a versão mais recente do [Java Runtime Environment](http://java.com/download/) e certificar-se de que a variável de caminho do Java tenha sido definida como C:\ProgramData\Oracle\Java\javapath em suas variáveis de ambiente do Windows. Para obter mais ajuda, consulte a [documentação do Java](http://java.com/download/help/).

    > [!NOTE]
    > Em alguns casos, a versão de 32 bits do Java pode resultar em problemas de memória. É recomendável instalar a versão de 64 bits.

- O Android exige que todos os pacotes de aplicativo (.apks) sejam assinados. Use a ferramenta de chave do Java para gerar as credenciais necessárias para assinar o aplicativo de saída encapsulado. Por exemplo, o comando a seguir usa o executável Java keytool.exe para gerar chaves que podem ser usadas pela Ferramenta de Disposição do Dispositivo para assinar o aplicativo de saída encapsulado.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    Este exemplo gera um par de chaves (uma chave pública e uma chave privada associada de 2.048 bits) usando o algoritmo RSA. Em seguida, ele encapsula a chave pública em um certificado autoassinado x.509 v3, que é armazenado como uma cadeia de certificados de elemento único. Esta cadeia de certificados e a chave privada são armazenadas em uma nova entrada do repositório de chaves chamada "mykeystorefile" e identificadas pelo alias "mykeyalias". A entrada no repositório de chaves é válida por 50.000 dias.

    O comando solicitará que você forneça as senhas do repositório de chaves e da chave. Use senhas seguras, mas lembre-se delas porque elas serão necessárias para executar a Ferramenta de Disposição do Aplicativo.

    Para obter a documentação detalhada, leia mais sobre o Java [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) e Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) no site de documentação do Oracle.

## <a name="install-the-app-wrapping-tool"></a>Instalar a ferramenta de encapsulamento de aplicativos

1.  Do [repositório do GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android), baixe e abra o arquivo de instalação InstallAWT.exe para a Ferramenta de Disposição do Aplicativo do Intune para Android em um computador Windows. Abra o arquivo de instalação.

2.  Aceite o contrato de licença e conclua a instalação.

Anote a pasta na qual você instalou a ferramenta. O local padrão é: C:\Arquivos de Programas (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>Executar a ferramenta de encapsulamento de aplicativos

1.  No computador Windows em que você instalou a Ferramenta de Disposição do Aplicativo, abra uma janela do PowerShell no modo de administrador.

2.  Da pasta em que instalou a ferramenta, importe o módulo do PowerShell da Ferramenta de Disposição do Aplicativo:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Execute a ferramenta usando o comando **invoke-AppWrappingTool**, que tem a sintaxe de uso abaixo:
    ```
    Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
    ```

 A tabela a seguir fornece detalhes sobre as propriedades do comando **invoke-AppWrappingTool**:

|Propriedade|Informações do|Exemplo|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Caminho do aplicativo Android de origem (.apk).| |
|**-OutputPath**&lt;String&gt;|Caminho para o aplicativo Android de saída. Se esse for o mesmo caminho do diretório que InputPath, o pacote falhará.| |
|**-KeyStorePath**&lt;String&gt;|Caminho para o arquivo de repositório de chaves que contém o par de chaves pública/privada para a assinatura.|Por padrão, os arquivos do repositório de chaves são armazenados em "C:\Arquivos de Programas (x86)\Java\jreX.X.X_XX\bin." |
|**-KeyStorePassword**&lt;SecureString&gt;|Senha usada para descriptografar o armazenamento de chave. O Android requer que todos os pacotes de aplicativos (.apk) sejam assinados. Use o Java keytool para gerar o KeyStorePassword. Leia mais sobre o Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) aqui.| |
|**-KeyAlias**&lt;String&gt;|Nome da chave a ser usada para assinatura.| |
|**-KeyPassword**&lt;SecureString&gt;|Senha usada para descriptografar a chave privada que será usada para a assinatura.| |
|**-SigAlg**&lt;SecureString&gt;| (Opcional) Nome do algoritmo de assinatura a ser usado para assinatura. O algoritmo deve ser compatível com a chave privada.|Exemplos: SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | (Opcional) O comando dá suporte a parâmetros comuns do PowerShell, como verbose, debug etc. |


- Para obter uma lista de parâmetros comuns, consulte o [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Para ver informações detalhadas de uso da ferramenta, digite o comando:

    ```
    Help Invoke-AppWrappingTool
    ```

**Exemplo:**

Importe o módulo do PowerShell.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
Execute a Ferramenta de Disposição do Aplicativo no aplicativo nativo HelloWorld.apk.
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Depois, **KeyStorePassword** e **KeyPassword** serão solicitados. Insira as credenciais usadas para criar o arquivo do repositório de chaves.

O aplicativo encapsulado e um arquivo de log são gerados e salvos no caminho de saída especificado.

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Considerações de segurança para executar a Ferramenta de Disposição do Aplicativo
Para evitar potenciais falsificações, divulgações de informações e aumento de ataques de privilégio:

-   Certifique-se de que o aplicativo de LOB (linha de negócios) de entrada, o aplicativo de saída e o Java KeyStore estejam no mesmo computador Windows em que a Ferramenta de Disposição do Aplicativo está sendo executada.

-   Importe o aplicativo de saída para o console do Intune no mesmo computador em que a ferramenta está sendo executada. Consulte [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) para saber mais sobre o Java keytool.

-   Se o aplicativo de saída e a ferramenta estiverem em um caminho UNC e você não estiver executando a ferramenta e os arquivos de entrada no mesmo computador, configure o ambiente para ser protegido usando [IPsec (Internet Protocol Security)](http://en.wikipedia.org/wiki/IPsec) ou [Assinatura do Protocolo SMB (Server Message Block)](https://support.microsoft.com/en-us/kb/887429).

-   Certifique-se de que o aplicativo é proveniente de uma fonte confiável.

-   Proteja o diretório de saída que contém o aplicativo encapsulado. Considere usar um diretório de nível de usuário para a saída.

### <a name="see-also"></a>Consulte também
- [Decidir como preparar aplicativos para o gerenciamento de aplicativo móvel com o Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Usar o SDK para habilitar aplicativos para o gerenciamento de aplicativo móvel](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Nov16_HO1-->


