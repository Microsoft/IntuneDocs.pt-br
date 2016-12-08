---
title: Plug-in Cordova do SDK de Aplicativo do Microsoft Intune | Microsoft Intune
description: 
keywords: sdk, Cordova, intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: karthikaraman
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: af7df3fcf50c3508d495522341bb287c638f40a3
ms.openlocfilehash: 2af369cc44c710789ab65eb25f10602882772019


---
# ﻿<a name="microsoft-intune-app-sdk-cordova-plugin"></a>Plug-in Cordova do SDK de Aplicativo do Microsoft Intune

> [!NOTE]
> Primeiro, leia o artigo [Introdução ao SDK de Aplicativo do Intune](intune-app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.


## <a name="overview"></a>Visão geral

O [Plug-in Cordova do SDK de Aplicativo do Intune](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam) habilita [recursos de gerenciamento de aplicativo móvel do Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) em aplicativos iOS e Android criados com Cordova. O plug-in permite que os desenvolvedores integrem os recursos de proteção de dados e aplicativos do Intune em seu aplicativo baseado no Cordova.

Você descobrirá que é possível habilitar os recursos do SDK sem alterar o comportamento do seu aplicativo. Após você ter incorporado o plug-in em seu aplicativo móvel iOS ou Android, o administrador de TI poderá implantar a política por meio do Microsoft Intune MAM (gerenciamento de aplicativo móvel) para dar suporte a vários recursos de proteção de dados. Nós criamos o plug-in para a maioria das etapas sejam realizadas automaticamente no processo de build do Cordova. Como resultado, você deve ser capaz de habilitar seu aplicativo para gerenciamento rapidamente. Para começar, siga as etapas abaixo com base em sua plataforma de destino.




## <a name="whats-supported"></a>Para que há suporte?

### <a name="developer-machines"></a>Computadores de desenvolvedores
* Windows
* Mac OS


### <a name="mobile-app-platforms"></a>Plataformas de aplicativo móvel
* Android 4.0+
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Cenários de gerenciamento de aplicativo móvel do Intune

* Dispositivos registrados no MDM do Intune
* Dispositivos registrados em EMM de terceiros
* Dispositivos não gerenciados (não registrados com em nenhum MDM)

Aplicativos Cordova criados com o Plug-in Cordova do SDK de Aplicativo do Intune agora podem receber políticas de MAM (gerenciamento de aplicativo móvel) em dispositivos registrados no MDM (gerenciamento de dispositivo móvel) do Intune e em dispositivos não registrados.



## <a name="prerequisites"></a>Pré-requisitos

### <a name="technical-prerequisites"></a>Pré-requisitos técnicos

* **[Somente Android]** O aplicativo de Portal da Empresa do Microsoft Intune mais recente sempre deve estar instalado no dispositivo.


* A versão 0.8.0+ do [plug-in da ADAL (Biblioteca de Autenticação do Azure Active Directory) para Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) é necessária.
  * **Importante:** devido a um bug do Apache Cordova registrado [aqui](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22), os aplicativos que já têm a dependência do plug-in não atualizarão automaticamente o plug-in para a versão solicitada.


### <a name="before-you-install-and-use-microsoft-intune-app-sdk-cordova-plugin-you-must"></a>Antes de instalar e usar o Plug-in Cordova do SDK de Aplicativo do Microsoft Intune, você **precisa**:

* Examinar os [Termos de Licença do Plug-in Cordova do SDK de Aplicativo do Intune](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam/blob/master/Intune_App_SDK_Cordova_plugin_RTM_license.pdf).

* Imprimir e guardar uma cópia dos termos de licença para seus registros. Ao baixar e usar o Plug-in Cordova do SDK de Aplicativo do Intune, você concorda com esses termos de licença.  Se você não aceitá-los, não use o software.


## <a name="quick-start"></a>Início rápido

1. Atualize sua versão da ADAL:

    ```
    cordova plugin remove cordova-plugin-ms-adal
    cordova plugin add cordova-plugin-ms-adal@0.8.x
    ```

2. Adicione o Plug-in Cordova do SDK de Aplicativo do Intune:

    ```
    cordova plugin add cordova-plugin-ms-intune-mam
    ```

## <a name="how-to-build-the-plugin-into-your-ios-app"></a>Como incorporar o plug-in ao seu aplicativo iOS

Você precisará concluir algumas etapas para que seu aplicativo seja habilitado para o MAM do Intune. Por conveniência, essas etapas são executadas automaticamente no processo de compilação do Cordova como um gancho pré-compilação. Como resultado, as etapas automatizadas modificarão seus arquivos `*.pbxproj`, `*-Info.plist` e `*.entitlements` que estão associados a uma configuração do projeto. Se seu projeto não contiver um arquivo de direitos, o plug-in criará um automaticamente.

Essa configuração dá suporte a um único destino e executará a configuração no primeiro destino encontrado se houver vários destinos. Se o processo falhar, verifique se:

1. O projeto Xcode do seu aplicativo é `[name].xcodeproj`, em que `[name]` é o valor definido em `config.xml`
2. O projeto usa a [estrutura de diretório de aplicativos padrão do Cordova](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).

## <a name="how-to-build-the-plugin-into-your-android-app"></a>Como incorporar o plug-in ao seu aplicativo Android

1. Importe esse plug-in com as ferramentas mais recentes do Cordova. Automaticamente, o plug-in será invocado como uma etapa `after_compile`.

2. O plug-in criará uma versão habilitada para MAM de um APK interno (Android API 14+) no final do processo de build. A saída do build conterá um `[Project]-intunewrapped-[Build_Configuration].apk` (por exemplo, `helloWorld-intunewrapped-debug.apk`).

O plug-in somente dá suporte a compilações Gradle.

Devido a um bug do Cordova registrado [aqui](https://issues.apache.org/jira/browse/CB-9434) que faz com que determinados ganchos do Cordova sejam ignorado no `cordova run`, para executar o aplicativo encapsulado na linha de comando, você deve fazer o seguinte:

```
$ cordova build
$ cordova run --nobuild
```


### <a name="signing-your-android-app"></a>Assinatura de seu aplicativo Android
Para adicionar informações de assinatura ao APK encapsulado, modifique `build.json` como faria normalmente para adicionar informações de assinatura. Por exemplo:
```json
{
  "android": {
    "release": {
      "keystore": "your.keystore",
      "storePassword": "yourpassword",
      "alias": "youralias",
      "password" : "yourpassword",
      "keystoreType": ""
    }
  }
}
```

### <a name="build-for-android-test-only"></a>Build somente para teste em Android

1. Adicione `android:testOnly="true"` ao nó do aplicativo no arquivo `AndroidManifest.xml`.


2. **Cordova 6.x.x:** Em `[PROJECT_ROOT]/platforms/android/cordova/lib/Adb.js`, altere a linha 60 de

    ```javascript
    var args = ['-s', target, 'install'];
    ```
    como
    ```javascript
    var args = ['-s', target, 'install', '-t'];
    ```

O efeito disso é executar `adb install` com o sinalizador "-t", uma vez que aplicativos `testOnly` não podem ser instalados sem ele.

### <a name="debugging-from-visual-studio"></a>Depuração do Visual Studio
Após iniciar o aplicativo pela primeira vez, você verá uma caixa de diálogo informando que o aplicativo é gerenciado pelo Intune. Clique em "Não mostrar novamente" e clique no botão depurar/executar novamente do VS para que os pontos de interrupção sejam atingidos.

## <a name="known-limitations"></a>Limitações conhecidas
### <a name="android"></a>Android
* Suporte incompleto para MultiDex.
* O aplicativo deve ter como destino o Android 4.0 (API 14 do Android) ou superior.

### <a name="ios"></a>iOS
* Sempre que modificar a lista de UTI no nó **CFBundleDocumentTypes** do arquivo **plist**, você deve limpar o UTI do Intune na seção de UTIs Importados do mesmo arquivo plist (nó **UTImportedTypeDeclarations**) antes de compilar novamente. Todos os UTIs do Intune começarão com o prefixo `com.microsoft.intune.mam`.

* Se quiser remover o plug-in do Intune do seu projeto do Cordova, você também deverá remover a plataforma iOS e adicioná-la novamente para desfazer parte da configuração do Intune nos arquivos .xcodeproj e .plist.



<!--HONumber=Nov16_HO4-->


