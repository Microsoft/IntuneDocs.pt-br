---
title: Encapsular aplicativos Android com a Ferramenta de Encapsulamento do Aplicativo Intune
description: Saiba como encapsular os aplicativos Android sem alterar o código do aplicativo em si. Prepare os aplicativos para que você possa aplicar políticas de gerenciamento de aplicativo móvel.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 107624ac5d0c5eab423c0d5051ceca45e41de0b9
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72490759"
---
# <a name="prepare-android-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a>Preparar aplicativos Android para políticas de proteção do aplicativo com a Ferramenta de Encapsulamento de Aplicativos do Intune

Use a Ferramenta de Disposição do Aplicativo do Microsoft Intune para Android para alterar o comportamento dos aplicativos iOS internos restringindo as funcionalidades do aplicativo sem alterar seu código.

A ferramenta é um aplicativo de linha de comando do Windows que é executado no PowerShell e cria um wrapper em torno de seu aplicativo Android. Após o aplicativo ser encapsulado, você pode alterar sua funcionalidade configurando as [políticas de gerenciamento de aplicativo móvel](../apps/app-protection-policies.md) no Intune.

Antes de executar a ferramenta, consulte [Considerações de segurança para executar a Ferramenta de Disposição do Aplicativo](#security-considerations-for-running-the-app-wrapping-tool). Para baixar a ferramenta, acesse [Ferramenta de Disposição do Aplicativo do Microsoft Intune para Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) no GitHub.

## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Cumprir os pré-requisitos para usar a Ferramenta de Disposição do Aplicativo

- Você precisa executar a Ferramenta de Disposição do Aplicativo em um computador Windows executando o Windows 7 ou posterior.

- Seu aplicativo de entrada deve ser um pacote de aplicativo Android válido com a extensão de arquivo .apk e:

  - Ele não pode ser criptografado.
  - Ele não pode ter passado por encapsulamento pela Ferramenta de Disposição do Aplicativo do Intune.
  - Ele deve ser escrito para Android 4.0 ou posterior.

- O aplicativo deve ser desenvolvido por ou para a sua empresa. Você não pode usar essa ferramenta para processar aplicativos baixados da Google Play Store.

- Para executar a Ferramenta de Disposição do Aplicativo, você deve instalar a versão mais recente do [Java Runtime Environment](https://java.com/download/) e certificar-se de que a variável de caminho do Java tenha sido definida como C:\ProgramData\Oracle\Java\javapath em suas variáveis de ambiente do Windows. Para obter mais ajuda, consulte a [documentação do Java](https://java.com/download/help/).

    > [!NOTE]
    > Em alguns casos, a versão de 32 bits do Java pode resultar em problemas de memória. É recomendável instalar a versão de 64 bits.

- O Android exige que todos os pacotes de aplicativo (.apks) sejam assinados. Para a **reutilização** de certificados existentes e orientações do certificado de autenticação geral, consulte [Reutilizando certificados de autenticação e encapsulando aplicativos](app-wrapper-prepare-android.md#reusing-signing-certificates-and-wrapping-apps). O executável Java keytool.exe é usado para gerar **novas** credenciais necessárias para assinar o aplicativo de saída encapsulado. Todas as senhas definidas devem ser seguras, mas lembre-se delas porque elas serão necessárias para executar a Ferramenta de Disposição do Aplicativo.

    > [!NOTE]
    > A Ferramenta de Disposição do Aplicativo do Intune não oferece suporte aos esquemas de assinatura v2 e o futuro v3 para autenticação do aplicativo. Depois de ter disposto o arquivo .apk usando a Ferramenta de Disposição do Aplicativo do Intune, a recomendação é usar [a ferramenta Apksigner fornecida pelo Google]( https://developer.android.com/studio/command-line/apksigner). Isso garantirá que, assim que seu aplicativo chegar aos dispositivos dos usuários finais, ele possa ser iniciado corretamente pelos padrões do Android. 

- (Opcional) Às vezes, um aplicativo pode atingir o limite de tamanho do DEX (Dalvik Executable) devido às classes do SDK de MAM do Intune adicionados durante o encapsulamento. Os arquivos DEX fazem parte da compilação de um aplicativo Android. A ferramenta de encapsulamento de aplicativos do Intune manipula automaticamente o estouro de arquivo DEX durante o encapsulamento de aplicativos com um nível de API mínimo de 21 ou superior (a partir de [v. 1.0.2501.1](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android/releases)). Para aplicativos com um nível de API Mín de < 21, a prática recomendada seria aumentar o nível mínimo de API usando o sinalizador de `-UseMinAPILevelForNativeMultiDex` do wrapper. Para os clientes não conseguirem aumentar o nível de API mínimo do aplicativo, as seguintes soluções alternativas de estouro de DEX estão disponíveis. Em determinadas organizações, isso pode exigir trabalhar com quem compila o aplicativo (isto é, a equipe de build do aplicativo):
* Use o ProGuard para eliminar referências de classes não utilizadas do arquivo DEX primário do aplicativo.
* Para clientes que usam o v 3.1.0 ou superior do plug-in Android gradle, desabilite o [dexer D8](https://android-developers.googleblog.com/2018/04/android-studio-switching-to-d8-dexer.html).  

## <a name="install-the-app-wrapping-tool"></a>Instalar a ferramenta de encapsulamento de aplicativos

1. Do [repositório do GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android), baixe e abra o arquivo de instalação InstallAWT.exe para a Ferramenta de Disposição do Aplicativo do Intune para Android em um computador Windows. Abra o arquivo de instalação.

2. Aceite o contrato de licença e conclua a instalação.

Anote a pasta na qual você instalou a ferramenta. O local padrão é: C:\Arquivos de Programas (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>Executar a ferramenta de encapsulamento de aplicativos

1. No computador Windows em que você instalou a Ferramenta de Encapsulamento de Aplicativos, abra uma janela do PowerShell.

2. Da pasta em que instalou a ferramenta, importe o módulo do PowerShell da Ferramenta de Disposição do Aplicativo:

   ```PowerShell
   Import-Module .\IntuneAppWrappingTool.psm1
   ```

3. Execute a ferramenta usando o comando **invoke-AppWrappingTool**, que tem a sintaxe de uso abaixo:

   ```PowerShell
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
|**-SigAlg**&lt;SecureString&gt;| (Opcional) Nome do algoritmo de assinatura a ser usado para assinatura. O algoritmo deve ser compatível com a chave privada.|Exemplos: SHA256withRSA, SHA1withRSA|
|**-UseMinAPILevelForNativeMultiDex**| Adicional Use esse sinalizador para aumentar o nível de API mínimo do aplicativo Android de origem para 21. Esse sinalizador solicitará a confirmação, pois limitará quem pode instalar este aplicativo. Os usuários podem ignorar a caixa de diálogo de confirmação acrescentando o parâmetro "-Confirm: $false" ao comando do PowerShell. O sinalizador só deve ser usado por clientes em aplicativos com a API mínima < 21 que falha ao encapsular com êxito devido a erros de estouro de DEX. | |
| **&lt;CommonParameters&gt;** | (Opcional) O comando dá suporte a parâmetros comuns do PowerShell, como verbose, debug etc. |


- Para obter uma lista de parâmetros comuns, consulte o [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Para ver informações detalhadas de uso da ferramenta, digite o comando:

    ```PowerShell
    Help Invoke-AppWrappingTool
    ```

**Exemplo:**

Importe o módulo do PowerShell.

```PowerShell
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```

Execute a Ferramenta de Disposição do Aplicativo no aplicativo nativo HelloWorld.apk.

```PowerShell
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Depois, **KeyStorePassword** e **KeyPassword** serão solicitados. Insira as credenciais usadas para criar o arquivo do repositório de chaves.

O aplicativo encapsulado e um arquivo de log são gerados e salvos no caminho de saída especificado.

## <a name="how-often-should-i-rewrap-my-android-application-with-the-intune-app-wrapping-tool"></a>Com que frequência eu devo reencapsular o meu aplicativo Android com a ferramenta de encapsulamento de aplicativos do Intune?
Os cenários principais em que você precisa reencapsular os aplicativos são da seguinte maneira:
* O próprio aplicativo lançou uma nova versão. A versão anterior do aplicativo foi encapsulada e carregada no console do Intune.
* A ferramenta de encapsulamento de aplicativo Intune para Android lançou uma nova versão que permite que correções de bugs chave ou recursos novos e específicos de política de proteção de aplicativo Intune. Isso ocorre a cada 6 a 8 semanas por meio do repositório GitHub para a [Ferramenta de Encapsulamento de Aplicativo do Microsoft Intune App](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android).

Algumas práticas recomendadas para reencapsulamento incluem: 
* Manter certificados de autenticação usados durante o processo de build, consulte [Reutilizar certificados de assinatura e encapsulamento de aplicativos](app-wrapper-prepare-android.md#reusing-signing-certificates-and-wrapping-apps)

## <a name="reusing-signing-certificates-and-wrapping-apps"></a>Reutilizando certificados de autenticação e encapsulando aplicativos
O Android exige que todos os aplicativos sejam autenticados por um certificado válido para serem instalados em dispositivos Android.

Os aplicativos encapsulados podem ser autenticados como parte do processo de encapsulamento ou *após* o encapsulamento usando ferramentas de autenticação existentes (toda informação de assinatura no aplicativo antes do encapsulamento é descartada). Se possível, as informações de autenticação já usadas durante o processo de build devem ser usadas durante o encapsulamento. Em determinadas organizações, isso pode exigir trabalhar com quem tenha informações do repositório de chaves (isto é, a equipe do build do aplicativo). 

Se o certificado de autenticação anterior não puder ser usado ou se o aplicativo ainda não tiver sido implantado, você poderá criar um novo certificado de autenticação seguindo as instruções do [Guia do desenvolvedor do Android](https://developer.android.com/studio/publish/app-signing.html#signing-manually).

Se o aplicativo tiver sido implantado anteriormente com um certificado de autenticação diferente, o aplicativo não poderá ser carregado no Intune após a atualização. Os cenários de atualização do aplicativo serão interrompidos se ele for autenticado com um certificado diferente daquele usado na compilação do aplicativo. Dessa forma, todos os novos certificados de autenticação deverão ser mantidos para as atualizações do aplicativo. 

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Considerações de segurança para executar a Ferramenta de Disposição do Aplicativo
Para evitar potenciais falsificações, divulgações de informações e aumento de ataques de privilégio:

- Certifique-se de que o aplicativo de LOB (linha de negócios) de entrada, o aplicativo de saída e o Java KeyStore estejam no mesmo computador Windows em que a Ferramenta de Disposição do Aplicativo está sendo executada.

- Importe o aplicativo de saída para o Intune no mesmo computador em que a ferramenta está sendo executada. Confira [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) para saber mais sobre o Java Keytool.

- Se o aplicativo de saída e a ferramenta estiverem em um caminho UNC e você não estiver executando a ferramenta e os arquivos de entrada no mesmo computador, configure o ambiente para ser protegido usando [IPsec (Internet Protocol Security)](https://wikipedia.org/wiki/IPsec) ou [Assinatura do Protocolo SMB (Server Message Block)](https://support.microsoft.com/kb/887429).

- Certifique-se de que o aplicativo é proveniente de uma fonte confiável.

- Proteja o diretório de saída que contém o aplicativo encapsulado. Considere usar um diretório de nível de usuário para a saída.

## <a name="see-also"></a>Consulte também
- [Decidir como preparar aplicativos para o gerenciamento de aplicativo móvel com o Microsoft Intune](../developer/apps-prepare-mobile-application-management.md)

- [Guia para desenvolvedores do SDK de Aplicativo do Microsoft Intune para Android](../developer/app-sdk-android.md)
