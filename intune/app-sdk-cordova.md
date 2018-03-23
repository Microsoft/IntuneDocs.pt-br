---
title: Plug-in Cordova do SDK de Aplicativo do Microsoft Intune
description: O Plug-in Cordova do SDK de Aplicativo do Intune permite que os desenvolvedores integrem os recursos de proteção de dados e aplicativos do Intune em seu aplicativo baseado no Cordova.
keywords: sdk, Cordova, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 84ff217361108ac3518567f31af8943d0b3032fe
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Plug-in Cordova do SDK de Aplicativo do Microsoft Intune

> [!IMPORTANT]
> O Intune terminará o suporte para o Plug-in do Cordova do SDK de Aplicativo do Microsoft Intune em 1 de maio de 2018. É recomendável que você passe a usar a Ferramenta de Disposição do Aplicativo do Intune. Para obter mais informações sobre a Ferramenta de Disposição do Aplicativo, consulte [Ferramenta de Disposição do Aplicativo para iOS](app-wrapper-prepare-ios.md) e [Ferramenta de Disposição do Aplicativo para Android](app-wrapper-prepare-android.md). Para obter mais informações sobre essa alteração, consulte a seção [Avisos](whats-new.md#notices) em [Novidades no Microsoft Intune](whats-new.md).

## <a name="overview"></a>Visão geral

O [Plug-in Cordova do SDK de Aplicativo do Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) nos aplicativos iOS e Android criados com Cordova. O plug-in permite que os desenvolvedores integrem os recursos de proteção de dados e aplicativos do Intune em seu aplicativo baseado no Cordova.

> [!NOTE]
> Primeiro, leia o artigo [Introdução ao SDK de Aplicativo do Intune](app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.

Você descobrirá que é possível habilitar os recursos do SDK sem alterar o comportamento do seu aplicativo. Depois de compilar o plug-in em seu aplicativo iOS ou Android, o administrador do Microsoft Intune será capaz de implantar a política de proteção de aplicativo do Intune, que é composta por uma vários recursos de proteção de dados. O plug-in é compilado para que a maioria das etapas sejam realizadas automaticamente no processo de build do Cordova. Como resultado, você deve ser capaz de habilitar rapidamente seu aplicativo para proteção de aplicativo do Intune. Para começar, siga as etapas abaixo com base em sua plataforma de destino.

## <a name="supported-platforms"></a>Plataformas suportadas

* O plug-in funciona nos sistemas operacionais Windows, Mac e Linux
* O plug-in funciona para aplicativos Android com `minSdkVersion` >= 14 e `targetSdkVersion` <= 24
* O plug-in funciona para aplicativos iOS direcionados para iOS 9.0 e posterior.

## <a name="intune-mobile-application-management-scenarios"></a>Cenários de gerenciamento de aplicativo móvel do Intune

* Dispositivos registrados no MDM do Intune
* Dispositivos registrados em EMM de terceiros
* Dispositivos não gerenciados (não registrados com em nenhum MDM)

Os aplicativos Cordova criados com o Plug-in Cordova do SDK de Aplicativo do Intune agora podem receber políticas de proteção de aplicativo em dispositivos registrados no MDM (gerenciamento de dispositivo móvel) do Intune e em dispositivos não registrados.

## <a name="prerequisites"></a>Pré-requisitos

### <a name="android"></a>Android

* O aplicativo de Portal da Empresa do Microsoft Intune mais recente sempre deve estar instalado no dispositivo.
* É necessário ter, no mínimo, Java 7 no caminho onde você executará a compilação do Cordova ao usar o plug-in.

### <a name="ios"></a>iOS

* O aplicativo de Portal da Empresa do Microsoft Intune mais recente deve estar instalado no dispositivo para poder contar com os recursos de MDM. Ele *não* é necessário para a política de proteção de aplicativo do Intune sem recursos de registro do dispositivo.

### <a name="both-platforms"></a>As duas plataformas

* A versão 0.8.0+ do [plug-in da ADAL (Biblioteca de Autenticação do Azure Active Directory) para Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) é necessária.

> [!NOTE]
> Devido a um bug do Apache Cordova registrado [aqui](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22), os aplicativos que já têm a dependência do plug-in não farão upgrade automático do plug-in para a versão solicitada.



## <a name="quickstart"></a>quickStart

1. Atualize sua versão da ADAL:

  ```shell
  cordova plugin remove cordova-plugin-ms-adal
  cordova plugin add cordova-plugin-ms-adal@0.8.x
  ```

2. Adicione o Plug-in Cordova do SDK de Aplicativo do Intune:

  ```shell
  cordova plugin add cordova-plugin-ms-intune-mam
  ```

## <a name="build-the-plugin-into-your-ios-app"></a>Compilar o plug-in em seu aplicativo iOS

Você precisará concluir algumas etapas para que seu aplicativo seja habilitado para a política de proteção de aplicativo do Intune. Por conveniência, essas etapas são executadas automaticamente no processo de compilação do Cordova como um gancho pré-compilação. Como resultado, as etapas automatizadas modificarão seus arquivos `*.pbxproj`, `*-Info.plist` e `*.entitlements` que estão associados a uma configuração do projeto. Se seu projeto não contiver um arquivo de direitos, o plug-in criará um automaticamente.

Essa configuração dá suporte a um único destino e executará a configuração no primeiro destino encontrado se houver vários destinos. Se o processo falhar, verifique se:

1. O projeto Xcode do seu aplicativo é `[name].xcodeproj`, em que `[name]` é o valor definido em `config.xml`
2. O projeto usa a [estrutura de diretório de aplicativos padrão do Cordova](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).

## <a name="build-the-plugin-into-your-android-app"></a>Compilar o plug-in em seu aplicativo Android

1. Importe esse plug-in com as ferramentas mais recentes do Cordova. Automaticamente, o plug-in será invocado como uma etapa `after_compile`.

2. O plug-in criará uma versão habilitada para Intune de um APK criado (API do Android 14+) no final do processo de build. A saída do build conterá um `[Project]-intunewrapped-[Build_Configuration].apk` (por exemplo, `helloWorld-intunewrapped-debug.apk`).

> [!NOTE]
> O plug-in somente dá suporte a compilações Gradle.

Devido a um bug do Cordova registrado [aqui](https://issues.apache.org/jira/browse/CB-9434) que faz com que determinados ganchos do Cordova sejam ignorado no `cordova run`, para executar o aplicativo encapsulado na linha de comando, você deve fazer o seguinte:

```shell
$ cordova build
$ cordova run --nobuild
```

## <a name="sign-your-android-app"></a>Assinatura de seu aplicativo Android

O plug-in reconhece automaticamente as informações de assinatura fornecidas para o Cordova nos seguintes locais:

* platforms/android/debug-signing.properties
* platforms/android/release-signing.properties
* res/native/android/ant.properties

Veja as [informações de assinatura gradle do Cordova](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle) para saber mais sobre o formato esperado.

No momento, o Intune não dá suporte para a capacidade de fornecer informações de assinatura em `build.json` ou em locais aleatórios fornecidos via parâmetros à compilação do Cordova.

## <a name="debugging-from-visual-studio"></a>Depuração do Visual Studio

Após iniciar o aplicativo pela primeira vez, você verá uma caixa de diálogo informando que o aplicativo é gerenciado pelo Intune. Clique em "Não mostrar novamente" e clique no botão depurar/executar novamente do VS para que os pontos de interrupção sejam atingidos.

## <a name="known-limitations"></a>Limitações conhecidas

### <a name="android"></a>Android

* Suporte incompleto para MultiDex.
* O aplicativo deve ter um `minSdkVersion` de 14 e um `targetSdkVersion` de 24 ou abaixo. No momento, o Intune não é compatível com aplicativos destinados à API 25
* O Intune não pode assinar novamente aplicativos assinados com o Esquema de assinatura V2. Quando aplicativos assinados por V2 são agrupados com o plug-in, a saída .apk agrupada não é assinada.
*
  * Desabilite a Assinatura V2 padrão do Cordova adicionando o seguinte ao seu arquivo `build-extras.gradle`:

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### <a name="ios"></a>iOS

* Sempre que modificar a lista de UTIs no nó **CFBundleDocumentTypes** do arquivo **Info.plist**, será necessário limpar os UTIs do Intune na seção de UTIs Importados do mesmo arquivo plist (nó **UTImportedTypeDeclarations**) antes de compilar novamente. Todos os UTIs do Intune começarão com o prefixo `com.microsoft.intune.mam`.

* Se quiser remover o plug-in SDK de Aplicativo do Intune para Cordova de seu projeto Cordova, você também deverá remover a plataforma iOS e adicioná-la novamente para desfazer parte da configuração do Intune nos arquivos .xcodeproj e .plist.
