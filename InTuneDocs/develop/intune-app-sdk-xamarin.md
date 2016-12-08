---
title: Componente Xamarin do SDK de Aplicativo do Microsoft Intune | Microsoft Intune
description: 
keywords: sdk, Xamarin, intune
author: oydang
manager: karthikaraman
ms.author: oydang
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: karthikaraman
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: af7df3fcf50c3508d495522341bb287c638f40a3
ms.openlocfilehash: 2ea1763881a7d10ae8bc21c98754d2767b2fc954


---

# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Componente Xamarin do SDK de Aplicativo do Microsoft Intune

> [!NOTE]
> Primeiro, leia o artigo [Introdução ao SDK de Aplicativo do Intune](intune-app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.



## <a name="overview"></a>Visão geral
O [Componente Xamarin do SDK de Aplicativo do Intune](https://components.xamarin.com/view/microsoft.intune.mam) habilita [recursos de gerenciamento de aplicativo móvel do Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) em aplicativos iOS e Android criados com Xamarin. O componente permite que os desenvolvedores incorporem facilmente recursos de proteção de aplicativo do Intune em seus aplicativos baseados em Xamarin.

Você descobrirá que é possível habilitar os recursos do SDK sem alterar o comportamento do seu aplicativo. Após você ter incorporado o componente em seu aplicativo móvel iOS ou Android, o administrador de TI poderá implantar a política por meio do Microsoft Intune MAM (gerenciamento de aplicativo móvel) para dar suporte a vários recursos de proteção de dados.

## <a name="whats-supported"></a>Para que há suporte?

### <a name="developer-machines"></a>Computadores de desenvolvedores
* Windows


### <a name="mobile-app-platforms"></a>Plataformas de aplicativo móvel
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Cenários de gerenciamento de aplicativo móvel do Intune

* Dispositivos registrados no MDM do Intune
* Dispositivos registrados em EMM de terceiros
* Dispositivos não gerenciados (não registrados com em nenhum MDM)

Aplicativos Xamarin criados com o Componente Xamarin do SDK de Aplicativo do Intune agora podem receber políticas de MAM (gerenciamento de aplicativo móvel) em dispositivos registrados no MDM (gerenciamento de dispositivo móvel) do Intune e em dispositivos não registrados.

## <a name="prerequisites"></a>Pré-requisitos

* **[Somente Android]** O aplicativo de Portal da Empresa do Microsoft Intune mais recente sempre deve estar instalado no dispositivo.

## <a name="get-started"></a>Introdução

1.  Baixe o arquivo **Xamarin-component.exe** [aqui](https://components.xamarin.com/submit/xpkg) e extraia o arquivo.

2. Leia os [termos de licença](https://components.xamarin.com/license/microsoft.intune.mam) do Componente Xamarin para MAM no Microsoft Intune.

3.  Baixar a pasta do Componente Xamarin do SDK de Aplicativo do Intune do [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) ou do [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) e extraia. Os arquivos baixados na etapa 1 e na etapa 2 deve estar no mesmo nível de diretório.

4.  Na linha de comando como administrador, execute `Xamain.Component.exe install <.xam> file`.

5.  No Visual Studio, clique com o botão direito do mouse em **componentes** no seu projeto Xamarin criado anteriormente.

6.  Selecione **Editar Componentes** e adicione o componente do SDK de Aplicativo do Intune que você baixou localmente em seu computador.



## <a name="enabling-intune-mam-in-your-ios-mobile-app"></a>Habilitar o MAM do Intune em seu aplicativo móvel iOS
1.  Para inicializar o SDK de Aplicativo do Intune, você precisará fazer uma chamada de API na classe `AppDelegate.cs`. Por exemplo:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Agora que o componente foi adicionado e inicializado, você pode seguir as etapas gerais necessárias para a criação do SDK de Aplicativo em um aplicativo móvel iOS. Você pode encontrar a documentação completa para habilitar aplicativos iOS nativos no [Guia do SDK de Aplicativos do Intune para desenvolvedores de iOS](intune-app-sdk-ios).
3. **Importante**: há várias modificações específicas para aplicativos iOS baseados em Xamarin. Por exemplo, ao habilitar grupos de conjunto de chaves, você precisará adicionar o seguinte para incluir o aplicativo de exemplo do Xamarin que incluímos no componente. Veja abaixo um exemplo dos grupos que você precisaria ter em seus grupos de Acesso de Conjunto de Chaves:

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

Você concluiu as etapas necessárias para incorporar o componente em seu aplicativo iOS baseado em Xamarin. Se estiver utilizando o Xcode para criar seu projeto, você poderá usar o `Intune App SDK Settings.bundle`. Isso permitirá ativar e desativar as configurações de política do Intune conforme você criar seu projeto para testar e depurar. Para tirar proveito desse pacote, siga as etapas em [Guia do SDK de Aplicativos do Intune para desenvolvedores de iOS](intune-app-sdk-ios) e leia a seção sobre [depuração no Xcode](intune-app-sdk-ios#debug-information).

## <a name="enabling-mam-in-your-android-mobile-app"></a>Habilitando MAM em seu aplicativo móvel Android
Para aplicativos Android baseados em Xamarin que não usam uma estrutura de interface do usuário, você precisará ler e seguir o [Guia de desenvolvedores do SDK de Aplicativos do Intune para Android]. Para seu aplicativo Android baseado em Xamarin, você precisará substituir classe, métodos e atividades pelos equivalentes do MAM com base na [tabela](intune-app-sdk-android#replace-classes-methods-and-activities-with-their-mam-equivalent-required) incluída no guia. Se o seu aplicativo não definir uma classe `android.app.Application`, você precisará criar uma e certificar-se de herdar de `MAMApplication`.

Para Formulários do Xamarin e outras estruturas de interface do usuário, fornecemos uma ferramenta chamada `MAM.Remapper`. A ferramenta realizará a substituição da classe para você. No entanto, você precisará realizar as seguintes etapas:

1.  Adicione uma referência ao` Microsoft.Intune.MAM.Remapper.Tasks` pacote NuGet 0.1.0.0 ou superior.

2.  Adicione a seguinte linha ao seu csproj Android:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Defina a ação de build do arquivo `remapping-config.json` adicionado como **RemappingConfigFile**. O `remapping-config.json` incluído só funciona com Xamarin.Forms. Para outras estruturas de interface do usuário, consulte o arquivo Leiame incluído no pacote NuGet Remapper.

## <a name="test-your-app"></a>Teste seu aplicativo

Você concluiu as etapas básicas da incorporação do componente ao seu aplicativo. Agora, você pode seguir as etapas incluídas no aplicativo de exemplo de Xamarin para Android. Nós fornecemos dois exemplos, um para Xamarin.Forms e outro para o Android.



<!--HONumber=Nov16_HO4-->

