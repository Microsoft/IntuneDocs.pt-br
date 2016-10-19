---
title: "Encapsular aplicativos Android com a Ferramenta de Disposição do Aplicativo | Microsoft Intune"
description: "Use as informações neste tópico para aprender a encapsular seus aplicativos Android sem modificar o código do aplicativo em si. Prepare os aplicativos para que você possa aplicar políticas de gerenciamento de aplicativo móvel."
keywords: 
author: karthikaraman
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
ms.sourcegitcommit: 45c6622624230e3486d2498b1b023f2efcdc2970
ms.openlocfilehash: ea1a6ef60b6a9cdd64559f67276280a4f491e30e


---

# Preparar aplicativos Android para o gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune
Use a **Ferramenta de encapsulamento de aplicativos do Microsoft Intune para Android** para modificar o comportamento de aplicativos Android internamente e configurar as funcionalidades do aplicativo sem modificar seu código.

A ferramenta é um aplicativo de linha de comando do Windows que é executado no PowerShell e cria um “wrapper” em torno de seu aplicativo. Após o aplicativo ser processado, você pode alterar sua funcionalidade usando [políticas de gerenciamento de aplicativo móvel](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) que você configurar.


Antes de executar a ferramenta, consulte [Security considerations for running the app wrapping tool (Considerações de segurança para executar a ferramenta de encapsulamento de aplicativos)](#security-considerations-for-running-the-app-wrapping-tool). Para baixar a ferramenta, consulte [Microsoft Intune App Wrapping Tool for Android - Português (Brasil)](https://www.microsoft.com/download/details.aspx?id=47267).

>[!IMPORTANT]
>Esta versão da ferramenta de disposição do aplicativo, que dá suporte a dispositivos não registrados no Intune, está disponível para visualização pública. Se desejar participar da visualização pública, você poderá baixar a ferramenta [nesta página do GitHub](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview) para Android.

O cenário está descrito no tópico [Proteger aplicativos de linha de negócios e dados em dispositivos não registrados no Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).


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

3.  Execute a ferramenta usando o comando **invoke-AppWrappingTool** com um ou mais dos parâmetros a seguir.

|Parâmetro|Mais informações|Exemplos|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Caminho do aplicativo Android de origem (.apk).| |
|**-OutputPath**&lt;String&gt;|Caminho para o aplicativo Android de "saída". Se esse for o mesmo caminho do diretório que InputPath, o pacote falhará.| |
|**-KeyStorePath**&lt;String&gt;|Caminho para o arquivo de armazenamento de chaves que contém o par de chaves pública/privada para a assinatura.| |
|**-KeyStorePassword**&lt;SecureString&gt;|Senha usada para descriptografar o armazenamento de chave. O Android requer que todos os pacotes de aplicativos (.apk) sejam assinados. Use a Ferramenta de Chave Java para gerar o KeyStorePassword como mostrado no exemplo. Leia mais sobre [keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html).|keytool.exe -genkey -v -keystore keystorefile -alias ks -keyalg RSA -keysize 2048 -validity 50000 |
|**-KeyAlias**&lt;String&gt;|Nome da chave a ser usada para assinatura.| |
|**-KeyPassword**&lt;SecureString&gt;|Senha usada para descriptografar a chave privada que será usada para a assinatura.| |
|**-SigAlg**&lt;SecureString&gt;|Nome do algoritmo de assinatura a ser usado para assinatura. O algoritmo deve ser compatível com a chave privada.|Exemplos: SHA256withRSA, SHA1withRSA, MD5withRSA|


**&lt;CommonParameters&gt;**
 (opcional – dá suporte a parâmetros comuns do PowerShell como verbose, debug etc.)

- Para obter uma lista de parâmetros comuns, consulte o [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Para ver a ajuda da ferramenta, digite o comando:

    ```
    Help Invoke-AppWrappingTool
    ```

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

-   Certifique-se de que o aplicativo seja proveniente de uma fonte confiável, o que pode permitir que o aplicativo acesse o token do AAD durante o tempo de execução.

-   Proteja o diretório de saída que contém o aplicativo encapsulado. Considere usar um diretório de nível de usuário para a saída.



### Consulte também
- [Decidir como preparar aplicativos para o gerenciamento de aplicativos móveis com o Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Use o SDK para habilitar aplicativos para o gerenciamento de aplicativos móveis](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Sep16_HO2-->


