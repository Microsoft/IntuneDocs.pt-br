---
title: "<span data-ttu-id=\"aa2e5-101\">Encapsular aplicativos Android com a Ferramenta de Disposição do Aplicativo</span><span class=\"sxs-lookup\"><span data-stu-id=\"aa2e5-101\">Wrap Android apps with App Wrapping Tool</span></span>"
description: "<span data-ttu-id=\"aa2e5-102\">Use as informações neste artigo para aprender a encapsular seus aplicativos Android sem alterar o código do aplicativo em si.</span><span class=\"sxs-lookup\"><span data-stu-id=\"aa2e5-102\">Use the information in this article to learn how to wrap your Android apps without changing the code of the app itself.</span></span> <span data-ttu-id=\"aa2e5-103\">Prepare os aplicativos para que você possa aplicar políticas de gerenciamento de aplicativo móvel.</span><span class=\"sxs-lookup\"><span data-stu-id=\"aa2e5-103\">Prepare the apps so you can apply mobile app management policies.</span></span>"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 07/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 299e2ed0a84c7158a582ee874f0711eb3c379532
ms.sourcegitcommit: bee30f4c9e04129d70305fcafc4152c6e062a8b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2017
---
# <a name="prepare-android-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a><span data-ttu-id="aa2e5-104">Preparar aplicativos Android para o gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune</span><span class="sxs-lookup"><span data-stu-id="aa2e5-104">Prepare Android apps for mobile application management with the Intune App Wrapping Tool</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="aa2e5-105">Use a Ferramenta de Disposição do Aplicativo do Microsoft Intune para Android para alterar o comportamento dos aplicativos iOS internos restringindo as funcionalidades do aplicativo sem alterar seu código.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-105">Use the Microsoft Intune App Wrapping Tool for Android to change the behavior of your in-house Android apps by restricting features of the app without changing the code of the app itself.</span></span>

<span data-ttu-id="aa2e5-106">A ferramenta é um aplicativo de linha de comando do Windows que é executado no PowerShell e cria um wrapper em torno de seu aplicativo Android.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-106">The tool is a Windows command-line application that runs in PowerShell and creates a wrapper around your Android app.</span></span> <span data-ttu-id="aa2e5-107">Após o aplicativo ser encapsulado, você pode alterar sua funcionalidade configurando as [políticas de gerenciamento de aplicativo móvel](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) no Intune.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-107">After the app is wrapped, you can change the app’s functionality by configuring [mobile application management policies](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) in Intune.</span></span>


<span data-ttu-id="aa2e5-108">Antes de executar a ferramenta, consulte [Considerações de segurança para executar a Ferramenta de Disposição do Aplicativo](#security-considerations-for-running-the-app-wrapping-tool).</span><span class="sxs-lookup"><span data-stu-id="aa2e5-108">Before running the tool, review [Security considerations for running the App Wrapping Tool](#security-considerations-for-running-the-app-wrapping-tool).</span></span> <span data-ttu-id="aa2e5-109">Para baixar a ferramenta, acesse [Ferramenta de Disposição do Aplicativo do Microsoft Intune para Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) no GitHub.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-109">To download the tool, go to the [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) on GitHub.</span></span>



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a><span data-ttu-id="aa2e5-110">Cumprir os pré-requisitos para usar a Ferramenta de Disposição do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="aa2e5-110">Fulfill the prerequisites for using the App Wrapping Tool</span></span>

-   <span data-ttu-id="aa2e5-111">Você precisa executar a Ferramenta de Disposição do Aplicativo em um computador Windows executando o Windows 7 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-111">You must run the App Wrapping Tool on a Windows computer running Windows 7 or later.</span></span>

-   <span data-ttu-id="aa2e5-112">Seu aplicativo de entrada deve ser um pacote de aplicativo Android válido com a extensão de arquivo .apk e:</span><span class="sxs-lookup"><span data-stu-id="aa2e5-112">Your input app must be a valid Android application package with the file extension .apk and:</span></span>

    -   <span data-ttu-id="aa2e5-113">Ele não pode ser criptografado.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-113">It cannot be encrypted.</span></span>
    -   <span data-ttu-id="aa2e5-114">Ele não pode ter passado por encapsulamento pela Ferramenta de Disposição do Aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-114">It must not have previously been wrapped by the Intune App Wrapping Tool.</span></span>
    -   <span data-ttu-id="aa2e5-115">Ele deve ser escrito para Android 4.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-115">It must be written for Android 4.0 or later.</span></span>

-   <span data-ttu-id="aa2e5-116">O aplicativo deve ser desenvolvido por ou para a sua empresa.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-116">The app must be developed by or for your company.</span></span> <span data-ttu-id="aa2e5-117">Você não pode usar essa ferramenta para processar aplicativos baixados da Google Play Store.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-117">You cannot use this tool on apps downloaded from the Google Play Store.</span></span>

-   <span data-ttu-id="aa2e5-118">Para executar a Ferramenta de Disposição do Aplicativo, você deve instalar a versão mais recente do [Java Runtime Environment](http://java.com/download/) e certificar-se de que a variável de caminho do Java tenha sido definida como C:\ProgramData\Oracle\Java\javapath em suas variáveis de ambiente do Windows.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-118">To run the App Wrapping Tool, you must install the latest version of the [Java Runtime Environment](http://java.com/download/) and then ensure that the Java path variable has been set to C:\ProgramData\Oracle\Java\javapath in your Windows environment variables.</span></span> <span data-ttu-id="aa2e5-119">Para obter mais ajuda, consulte a [documentação do Java](http://java.com/download/help/).</span><span class="sxs-lookup"><span data-stu-id="aa2e5-119">For more help, see the [Java documentation](http://java.com/download/help/).</span></span>

    > [!NOTE]
    > <span data-ttu-id="aa2e5-120">Em alguns casos, a versão de 32 bits do Java pode resultar em problemas de memória.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-120">In some cases, the 32-bit version of Java may result in memory issues.</span></span> <span data-ttu-id="aa2e5-121">É recomendável instalar a versão de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-121">It's a good idea to install the 64-bit version.</span></span>

- <span data-ttu-id="aa2e5-122">O Android exige que todos os pacotes de aplicativo (.apks) sejam assinados.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-122">Android requires all app packages (.apk) to be signed.</span></span> <span data-ttu-id="aa2e5-123">Use a ferramenta de chave do Java para gerar as credenciais necessárias para assinar o aplicativo de saída encapsulado.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-123">Use Java keytool to generate credentials needed to sign the wrapped output app.</span></span> <span data-ttu-id="aa2e5-124">Por exemplo, o comando a seguir usa o executável Java keytool.exe para gerar chaves que podem ser usadas pela Ferramenta de Disposição do Dispositivo para assinar o aplicativo de saída encapsulado.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-124">For example, the following command uses the Java executable keytool.exe to generate keys that can be used by the App Wrapping Tool to sign the wrapped output app.</span></span>

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    <span data-ttu-id="aa2e5-125">Este exemplo gera um par de chaves (uma chave pública e uma chave privada associada de 2.048 bits) usando o algoritmo RSA.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-125">This example generates a key pair (a public key and associated private key of 2,048 bits) by using the RSA algorithm.</span></span> <span data-ttu-id="aa2e5-126">Em seguida, ele encapsula a chave pública em um certificado autoassinado x.509 v3, que é armazenado como uma cadeia de certificados de elemento único.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-126">It then wraps the public key into an X.509 v3 self-signed certificate, which is stored as a single-element certificate chain.</span></span> <span data-ttu-id="aa2e5-127">Esta cadeia de certificados e a chave privada são armazenadas em uma nova entrada do repositório de chaves chamada "mykeystorefile" e identificadas pelo alias "mykeyalias".</span><span class="sxs-lookup"><span data-stu-id="aa2e5-127">This certificate chain and the private key are stored in a new keystore entry named "mykeystorefile" and identified by the alias "mykeyalias."</span></span> <span data-ttu-id="aa2e5-128">A entrada no repositório de chaves é válida por 50.000 dias.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-128">The keystore entry is valid for 50,000 days.</span></span>

    <span data-ttu-id="aa2e5-129">O comando solicitará que você forneça as senhas do repositório de chaves e da chave.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-129">The command will prompt you to provide passwords for the keystore and key.</span></span> <span data-ttu-id="aa2e5-130">Use senhas seguras, mas lembre-se delas porque elas serão necessárias para executar a Ferramenta de Disposição do Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-130">Use passwords that are secure, but make a note of them because they're needed to run the App Wrapping Tool.</span></span>

    <span data-ttu-id="aa2e5-131">Para obter a documentação detalhada, leia mais sobre o Java [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) e Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) no site de documentação do Oracle.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-131">For detailed documentation, read more about the Java [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) and Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) on the Oracle documentation website.</span></span>

## <a name="install-the-app-wrapping-tool"></a><span data-ttu-id="aa2e5-132">Instalar a ferramenta de encapsulamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="aa2e5-132">Install the App Wrapping Tool</span></span>

1.  <span data-ttu-id="aa2e5-133">Do [repositório do GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android), baixe e abra o arquivo de instalação InstallAWT.exe para a Ferramenta de Disposição do Aplicativo do Intune para Android em um computador Windows.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-133">From the [GitHub repository](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android), download the installation file InstallAWT.exe for the Intune App Wrapping Tool for Android to a Windows computer.</span></span> <span data-ttu-id="aa2e5-134">Abra o arquivo de instalação.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-134">Open the installation file.</span></span>

2.  <span data-ttu-id="aa2e5-135">Aceite o contrato de licença e conclua a instalação.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-135">Accept the license agreement, then finish the installation.</span></span>

<span data-ttu-id="aa2e5-136">Anote a pasta na qual você instalou a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-136">Note the folder to which you installed the tool.</span></span> <span data-ttu-id="aa2e5-137">O local padrão é: C:\Arquivos de Programas (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-137">The default location is: C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.</span></span>

## <a name="run-the-app-wrapping-tool"></a><span data-ttu-id="aa2e5-138">Executar a ferramenta de encapsulamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="aa2e5-138">Run the App Wrapping Tool</span></span>

1.  <span data-ttu-id="aa2e5-139">No computador Windows em que você instalou a Ferramenta de Encapsulamento de Aplicativos, abra uma janela do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-139">On the Windows computer where you installed the App Wrapping Tool, open a PowerShell window.</span></span>

2.  <span data-ttu-id="aa2e5-140">Da pasta em que instalou a ferramenta, importe o módulo do PowerShell da Ferramenta de Disposição do Aplicativo:</span><span class="sxs-lookup"><span data-stu-id="aa2e5-140">From the folder where you installed the tool, import the App Wrapping Tool PowerShell module:</span></span>

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  <span data-ttu-id="aa2e5-141">Execute a ferramenta usando o comando **invoke-AppWrappingTool**, que tem a sintaxe de uso abaixo:</span><span class="sxs-lookup"><span data-stu-id="aa2e5-141">Run the tool by using the **invoke-AppWrappingTool** command, which has the following usage syntax:</span></span>
    ```
    Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
    ```

 <span data-ttu-id="aa2e5-142">A tabela a seguir fornece detalhes sobre as propriedades do comando **invoke-AppWrappingTool**:</span><span class="sxs-lookup"><span data-stu-id="aa2e5-142">The following table details the properties of the **invoke-AppWrappingTool** command:</span></span>

|<span data-ttu-id="aa2e5-143">Propriedade</span><span class="sxs-lookup"><span data-stu-id="aa2e5-143">Property</span></span>|<span data-ttu-id="aa2e5-144">Informações do</span><span class="sxs-lookup"><span data-stu-id="aa2e5-144">Information</span></span>|<span data-ttu-id="aa2e5-145">Exemplo</span><span class="sxs-lookup"><span data-stu-id="aa2e5-145">Example</span></span>|
|-------------|--------------------|---------|
|<span data-ttu-id="aa2e5-146">**-InputPath**&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="aa2e5-146">**-InputPath**&lt;String&gt;</span></span>|<span data-ttu-id="aa2e5-147">Caminho do aplicativo Android de origem (.apk).</span><span class="sxs-lookup"><span data-stu-id="aa2e5-147">Path of the source Android app (.apk).</span></span>| |
|<span data-ttu-id="aa2e5-148">**-OutputPath**&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="aa2e5-148">**-OutputPath**&lt;String&gt;</span></span>|<span data-ttu-id="aa2e5-149">Caminho para o aplicativo Android de saída.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-149">Path to the output Android app.</span></span> <span data-ttu-id="aa2e5-150">Se esse for o mesmo caminho do diretório que InputPath, o pacote falhará.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-150">If this is the same directory path as InputPath, the packaging will fail.</span></span>| |
|<span data-ttu-id="aa2e5-151">**-KeyStorePath**&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="aa2e5-151">**-KeyStorePath**&lt;String&gt;</span></span>|<span data-ttu-id="aa2e5-152">Caminho para o arquivo de repositório de chaves que contém o par de chaves pública/privada para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-152">Path to the keystore file that has the public/private key pair for signing.</span></span>|<span data-ttu-id="aa2e5-153">Por padrão, os arquivos do repositório de chaves são armazenados em "C:\Arquivos de Programas (x86)\Java\jreX.X.X_XX\bin."</span><span class="sxs-lookup"><span data-stu-id="aa2e5-153">By default, keystore files are stored in "C:\Program Files (x86)\Java\jreX.X.X_XX\bin."</span></span> |
|<span data-ttu-id="aa2e5-154">**-KeyStorePassword**&lt;SecureString&gt;</span><span class="sxs-lookup"><span data-stu-id="aa2e5-154">**-KeyStorePassword**&lt;SecureString&gt;</span></span>|<span data-ttu-id="aa2e5-155">Senha usada para descriptografar o armazenamento de chave.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-155">Password used to decrypt the keystore.</span></span> <span data-ttu-id="aa2e5-156">O Android requer que todos os pacotes de aplicativos (.apk) sejam assinados.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-156">Android requires all application packages (.apk) to be signed.</span></span> <span data-ttu-id="aa2e5-157">Use o Java keytool para gerar o KeyStorePassword.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-157">Use Java keytool to generate the KeyStorePassword.</span></span> <span data-ttu-id="aa2e5-158">Leia mais sobre o Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) aqui.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-158">Read more about Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) here.</span></span>| |
|<span data-ttu-id="aa2e5-159">**-KeyAlias**&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="aa2e5-159">**-KeyAlias**&lt;String&gt;</span></span>|<span data-ttu-id="aa2e5-160">Nome da chave a ser usada para assinatura.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-160">Name of the key to be used for signing.</span></span>| |
|<span data-ttu-id="aa2e5-161">**-KeyPassword**&lt;SecureString&gt;</span><span class="sxs-lookup"><span data-stu-id="aa2e5-161">**-KeyPassword**&lt;SecureString&gt;</span></span>|<span data-ttu-id="aa2e5-162">Senha usada para descriptografar a chave privada que será usada para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-162">Password used to decrypt the private key that will be used for signing.</span></span>| |
|<span data-ttu-id="aa2e5-163">**-SigAlg**&lt;SecureString&gt;</span><span class="sxs-lookup"><span data-stu-id="aa2e5-163">**-SigAlg**&lt;SecureString&gt;</span></span>| <span data-ttu-id="aa2e5-164">(Opcional) Nome do algoritmo de assinatura a ser usado para assinatura.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-164">(Optional) The name of the signature algorithm to be used for signing.</span></span> <span data-ttu-id="aa2e5-165">O algoritmo deve ser compatível com a chave privada.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-165">The algorithm must be compatible with the private key.</span></span>|<span data-ttu-id="aa2e5-166">Exemplos: SHA256withRSA, SHA1withRSA, MD5withRSA</span><span class="sxs-lookup"><span data-stu-id="aa2e5-166">Examples: SHA256withRSA, SHA1withRSA, MD5withRSA</span></span>|
| <span data-ttu-id="aa2e5-167">**&lt;CommonParameters&gt;**</span><span class="sxs-lookup"><span data-stu-id="aa2e5-167">**&lt;CommonParameters&gt;**</span></span> | <span data-ttu-id="aa2e5-168">(Opcional) O comando dá suporte a parâmetros comuns do PowerShell, como verbose, debug etc.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-168">(Optional) The command supports common PowerShell parameters like verbose and debug.</span></span> |


- <span data-ttu-id="aa2e5-169">Para obter uma lista de parâmetros comuns, consulte o [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).</span><span class="sxs-lookup"><span data-stu-id="aa2e5-169">For a list of common parameters, see the [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).</span></span>

- <span data-ttu-id="aa2e5-170">Para ver informações detalhadas de uso da ferramenta, digite o comando:</span><span class="sxs-lookup"><span data-stu-id="aa2e5-170">To see detailed usage information for the tool, enter the command:</span></span>

    ```
    Help Invoke-AppWrappingTool
    ```

<span data-ttu-id="aa2e5-171">**Exemplo:**</span><span class="sxs-lookup"><span data-stu-id="aa2e5-171">**Example:**</span></span>

<span data-ttu-id="aa2e5-172">Importe o módulo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-172">Import the PowerShell module.</span></span>
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
<span data-ttu-id="aa2e5-173">Execute a Ferramenta de Disposição do Aplicativo no aplicativo nativo HelloWorld.apk.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-173">Run the App Wrapping Tool on the native app HelloWorld.apk.</span></span>
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

<span data-ttu-id="aa2e5-174">Depois, **KeyStorePassword** e **KeyPassword** serão solicitados.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-174">You will then be prompted for **KeyStorePassword** and **KeyPassword**.</span></span> <span data-ttu-id="aa2e5-175">Insira as credenciais usadas para criar o arquivo do repositório de chaves.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-175">Enter the credentials you used to create the key store file.</span></span>

<span data-ttu-id="aa2e5-176">O aplicativo encapsulado e um arquivo de log são gerados e salvos no caminho de saída especificado.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-176">The wrapped app and a log file are generated and saved in the output path you specified.</span></span>

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a><span data-ttu-id="aa2e5-177">Considerações de segurança para executar a Ferramenta de Disposição do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="aa2e5-177">Security considerations for running the App Wrapping Tool</span></span>
<span data-ttu-id="aa2e5-178">Para evitar potenciais falsificações, divulgações de informações e aumento de ataques de privilégio:</span><span class="sxs-lookup"><span data-stu-id="aa2e5-178">To prevent potential spoofing, information disclosure, and elevation of privilege attacks:</span></span>

-   <span data-ttu-id="aa2e5-179">Certifique-se de que o aplicativo de LOB (linha de negócios) de entrada, o aplicativo de saída e o Java KeyStore estejam no mesmo computador Windows em que a Ferramenta de Disposição do Aplicativo está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-179">Ensure that the input line-of-business (LOB) application, output application, and Java KeyStore are on the same Windows computer where the App Wrapping Tool is running.</span></span>

-   <span data-ttu-id="aa2e5-180">Importe o aplicativo de saída para o console do Intune no mesmo computador em que a ferramenta está sendo executada.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-180">Import the output application to the Intune console on the same machine where the tool is running.</span></span> <span data-ttu-id="aa2e5-181">Consulte [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) para saber mais sobre o Java keytool.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-181">See [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) for more about about Java keytool.</span></span>

-   <span data-ttu-id="aa2e5-182">Se o aplicativo de saída e a ferramenta estiverem em um caminho UNC e você não estiver executando a ferramenta e os arquivos de entrada no mesmo computador, configure o ambiente para ser protegido usando [IPsec (Internet Protocol Security)](http://wikipedia.org/wiki/IPsec) ou [Assinatura do Protocolo SMB (Server Message Block)](https://support.microsoft.com/kb/887429).</span><span class="sxs-lookup"><span data-stu-id="aa2e5-182">If the output application and the tool are on a Universal Naming Convention (UNC) path and you are not running the tool and input files on the same computer, set up the environment to be secure by using [Internet Protocol Security (IPsec)](http://wikipedia.org/wiki/IPsec) or [Server Message Block (SMB) signing](https://support.microsoft.com/kb/887429).</span></span>

-   <span data-ttu-id="aa2e5-183">Certifique-se de que o aplicativo é proveniente de uma fonte confiável.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-183">Ensure that the application is coming from a trusted source.</span></span>

-   <span data-ttu-id="aa2e5-184">Proteja o diretório de saída que contém o aplicativo encapsulado.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-184">Secure the output directory that has the wrapped app.</span></span> <span data-ttu-id="aa2e5-185">Considere usar um diretório de nível de usuário para a saída.</span><span class="sxs-lookup"><span data-stu-id="aa2e5-185">Consider using a user-level directory for the output.</span></span>

### <a name="see-also"></a><span data-ttu-id="aa2e5-186">Consulte também</span><span class="sxs-lookup"><span data-stu-id="aa2e5-186">See also</span></span>
- [<span data-ttu-id="aa2e5-187">Decidir como preparar aplicativos para o gerenciamento de aplicativo móvel com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="aa2e5-187">Decide how to prepare apps for mobile application management with Microsoft Intune</span></span>](apps-prepare-mobile-application-management.md)

- [<span data-ttu-id="aa2e5-188">Usar o SDK para habilitar aplicativos para o gerenciamento de aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="aa2e5-188">Use the SDK to enable apps for mobile application management</span></span>](/intune/classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
