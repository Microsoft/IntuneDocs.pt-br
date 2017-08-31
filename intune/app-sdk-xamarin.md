---
title: Componente Xamarin do SDK de Aplicativo do Microsoft Intune
description: 
keywords: sdk, Xamarin, intune
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a684f7ab5841513e8e72a5e6c0af99f52e5fd207
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2017
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Componente Xamarin do SDK de Aplicativo do Microsoft Intune

> [!NOTE]
> Primeiro, leia o artigo [Introdução ao SDK de Aplicativo do Intune](app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.



## <a name="overview"></a>Visão geral
O [componente do Microsoft Intune App SDK Xamarin](https://components.xamarin.com/view/microsoft.intune.mam) habilita a [política de proteção de aplicativo do Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) em aplicativos Android e iOS criados com o Xamarin. O componente permite que os desenvolvedores incorporem facilmente recursos de proteção de aplicativo do Intune em seus aplicativos baseados em Xamarin.

O componente Xamarin do SDK de Aplicativo do Microsoft Intune permite que você incorpore políticas de proteção de aplicativo do Intune (também conhecidas como políticas de aplicativo ou de MAM) em seus aplicativos desenvolvidos com o Xamarin. Um aplicativo habilitado para MAM é um que esteja integrado ao SDK de Aplicativos do Intune. Os administradores de TI podem implantar políticas de proteção do aplicativo ao seu aplicativo móvel quando o Intune gerencia o aplicativo ativamente.

## <a name="whats-supported"></a>Para que há suporte?

### <a name="developer-machines"></a>Computadores de desenvolvedores
* macOS


### <a name="mobile-app-platforms"></a>Plataformas de aplicativo móvel
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Cenários de gerenciamento de aplicativo móvel do Intune

* Dispositivos registrados no MDM do Intune
* Dispositivos registrados em EMM de terceiros
* Dispositivos não gerenciados (não registrados com em nenhum MDM)

Os aplicativos Xamarin criados com o Componente Xamarin do SDK de Aplicativo do Intune agora podem receber políticas de proteção de aplicativo do Intune em dispositivos registrados no MDM (gerenciamento de dispositivo móvel) do Intune e em dispositivos não registrados.

## <a name="prerequisites"></a>Pré-requisitos

* **[Somente Android]** O aplicativo Portal da Empresa do Microsoft Intune mais recente deve estar instalado no dispositivo.

## <a name="get-started"></a>Introdução

1.  Baixe o arquivo **Xamarin-component.exe** [aqui](https://components.xamarin.com/submit/xpkg) e extraia o arquivo.

2. Leia os [termos de licença](https://components.xamarin.com/license/microsoft.intune.mam) do Componente Xamarin para MAM no Microsoft Intune.

3.  Baixar a pasta do Componente Xamarin do SDK de Aplicativo do Intune do [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) ou do [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) e extraia. Os arquivos baixados na etapa 1 e na etapa 3 deve estar no mesmo nível de diretório.

4.  Na linha de comando como administrador, execute `Xamarin.Component.exe install <.xam> file`.

5.  No Visual Studio, clique com o botão direito do mouse em **componentes** em seu projeto Xamarin criado anteriormente.

6.  Selecione **Editar Componentes** e adicione o componente do SDK de Aplicativo do Intune que você baixou localmente em seu computador.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Habilite as políticas de proteção de aplicativo do Intune políticas em seu aplicativo móvel iOS
1.  Para inicializar o SDK de Aplicativo do Intune, você precisa fazer uma chamada a qualquer API na classe `AppDelegate.cs`. Por exemplo:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Agora que o componente foi adicionado e inicializado, você pode seguir as etapas gerais necessárias para a criação do SDK de Aplicativo em um aplicativo móvel iOS. Você pode encontrar a documentação completa para habilitar aplicativos iOS nativos no [Guia do SDK de Aplicativos do Intune para desenvolvedores de iOS](app-sdk-ios.md).
3. **Importante**: há várias modificações específicas para aplicativos iOS baseados em Xamarin. Por exemplo, ao habilitar grupos de conjuntos de chaves, você precisa adicionar o seguinte para incluir o aplicativo de exemplo do Xamarin que nós incluímos no componente. Veja abaixo um exemplo dos grupos que você precisaria ter em seus grupos de Acesso de Conjunto de Chaves:

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

Você concluiu as etapas necessárias para incorporar o componente em seu aplicativo iOS baseado em Xamarin. Se estiver utilizando o Xcode para criar seu projeto, você poderá usar o `Intune App SDK Settings.bundle`. Isso permite ativar e desativar as configurações de política do Intune conforme você cria seu projeto para testar e depurar. Para tirar proveito desse pacote, siga as etapas em [Guia do SDK de Aplicativos do Intune para desenvolvedores de iOS](app-sdk-ios.md) e leia a seção sobre [depuração no Xcode](app-sdk-ios.md#status-result-and-debug-notifications).

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Habilitar as políticas de proteção de aplicativo em seu aplicativo móvel Android
Para aplicativos Android baseados em Xamarin que não usam uma estrutura de interface do usuário, você precisa ler e seguir o [Guia do SDK de Aplicativo do Microsoft Intune para desenvolvedores do Android](app-sdk-android.md). Para seu aplicativo Android baseado em Xamarin, você precisa substituir classe, métodos e atividades pelos equivalentes do MAM com base na [tabela](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) incluída no guia. Se o seu aplicativo não definir uma classe `android.app.Application`, você precisará criar uma e verificar se herdou do `MAMApplication`.

Para Formulários do Xamarin e outras estruturas de interface do usuário, fornecemos uma ferramenta chamada `MAM.Remapper`. A ferramenta realiza a substituição de classe para você. No entanto, você precisa realizar as seguintes etapas:

1.  Adicione uma referência à versão 0.1.0.0 ou superior do pacote NuGet do `Microsoft.Intune.MAM.Remapper.Tasks`.

2.  Adicione a seguinte linha ao seu csproj Android:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Defina a ação de build do arquivo `remapping-config.json` adicionado como **RemappingConfigFile**. O `remapping-config.json` incluído só funciona com Xamarin.Forms. Para outras estruturas de interface do usuário, consulte o arquivo Leiame incluído no pacote NuGet do Remapeador.

## <a name="next-steps"></a>Próximas etapas

Você concluiu as etapas básicas da incorporação do componente ao seu aplicativo. Agora, você pode seguir as etapas incluídas no aplicativo de exemplo de Xamarin para Android. Nós fornecemos dois exemplos, um para Xamarin.Forms e outro para o Android.