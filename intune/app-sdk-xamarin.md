---
title: Componente Xamarin do SDK de Aplicativo do Microsoft Intune
description: O componente do Intune App SDK Xamarin habilita a política de proteção de aplicativo do Intune em aplicativos Android e iOS criados com o Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b69cccca8c8be859de94ca8bdb50d6030439233a
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Componente Xamarin do SDK de Aplicativo do Microsoft Intune

> [!NOTE]
> Primeiro, leia o artigo [Introdução ao SDK de Aplicativo do Intune](app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.

## <a name="overview"></a>Visão geral
O [componente do Microsoft Intune App SDK Xamarin](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) habilita a [política de proteção de aplicativo do Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) em aplicativos Android e iOS criados com o Xamarin. O componente permite que os desenvolvedores incorporem facilmente recursos de proteção de aplicativo do Intune em seus aplicativos baseados em Xamarin.

> [!NOTE]
> Atualmente, o suporte para o SDK do Intune para Xamarin está disponível na versão prévia. 

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

1. Leia os [termos de licença](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf) do Componente Xamarin para MAM no Microsoft Intune.

2.  Baixe os pacotes NuGet do componente Xamarin do SDK de Aplicativo do Intune do [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin). Esses pacotes estarão disponíveis em Nuget.org em breve.  

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Habilite as políticas de proteção de aplicativo do Intune políticas em seu aplicativo móvel iOS
1. Adicione o pacote NuGet `Microsoft.Intune.MAM.Xamarin.iOS` ao seu projeto Xamarin.iOS.
2.  Execute as etapas gerais necessárias para integrar o SDK do Aplicativo do Intune em um aplicativo móvel do iOS. Comece com a etapa 3 das instruções de integração do [Guia do desenvolvedor do SDK do Aplicativo do Intune para iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). É possível ignorar a etapa final na seção de execução do IntuneMAMConfigurator, porque essa ferramenta está incluída no pacote Microsoft.Intune.MAM.Xamarin.iOS e será executada automaticamente em tempo de build.
    **Importante**: a permissão do compartilhamento do conjunto de chaves para um aplicativo é um pouco diferente no Visual Studio e no Xcode. Abra a plist de Direitos do aplicativo e verifique se a opção "Habilitar Conjunto de Chaves" está habilitada, e se os grupos de compartilhamento de conjunto de chaves apropriados foram adicionados nessa seção. Em seguida, verifique se a plist de Direitos está especificada no campo "Direitos Personalizados" das opções de "Assinatura de Pacote do iOS" do projeto para todas as combinações apropriadas de Configuração/Plataforma.
3.  Após a adição do componente e da configuração correta do aplicativo, seu aplicativo pode começar a usar as APIs do SDK do Intune. Para fazer isso, inclua o namespace a seguir:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Para começar a receber as políticas de proteção do aplicativo, seu aplicativo deve ser registrado no serviço MAM do Intune. Se o seu aplicativo já usar a ADAL (Biblioteca de Autenticação do Azure Active Directory) para autenticar usuários, seu aplicativo deverá fornecer o UPN do usuário para o método registerAndEnrollAccount do IntuneMAMEnrollmentManager após sua autenticação bem-sucedida:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Importante**: substitua as configurações padrão de ADAL do SDK do Aplicativo do Intune pelas configurações de seu aplicativo. Faça isso por meio do dicionário IntuneMAMSettings no Info.plist do aplicativo, conforme mencionado no [Guia do desenvolvedor do SDK do Aplicativo do Intune para iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), ou você pode usar as propriedades de substituição do AAD da instância IntuneMAMPolicyManager. A abordagem de Info.plist é recomendada para aplicativos cujas configurações de ADAL são estáticas, enquanto as propriedades de substituição são recomendadas para aplicativos que determinam esses valores em tempo de execução. 
      
      Se o seu aplicativo não usar ADAL, e você quiser que o SDK do Intune lide com a autenticação, seu aplicativo deverá chamar o método loginAndEnrollAccount do IntuneMAMEnrollmentManager:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Habilitar as políticas de proteção de aplicativo em seu aplicativo móvel Android
Adicione o pacote NuGet `Microsoft.Intune.MAM.Xamarin.Android` ao seu projeto Xamarin.Android.

Para aplicativos Android baseados em Xamarin que não usam uma estrutura de interface do usuário, você precisa ler e seguir o [Guia do SDK de Aplicativo do Microsoft Intune para desenvolvedores do Android](app-sdk-android.md). Para seu aplicativo Android baseado em Xamarin, você precisa substituir classe, métodos e atividades pelos equivalentes do MAM com base na [tabela](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) incluída no guia. Se o seu aplicativo não definir uma classe `android.app.Application`, você precisará criar uma e verificar se herdou do `MAMApplication`.

Para Formulários do Xamarin e outras estruturas de interface do usuário, fornecemos uma ferramenta chamada `MAM.Remapper`. A ferramenta realiza a substituição de classe para você. No entanto, você precisa realizar as seguintes etapas:

1.  Adicione o pacote NuGet `Microsoft.Intune.MAM.Remapper.Tasks`.

2.  Adicione a seguinte linha ao seu csproj do Android (substitua "x.x.x.x" pela versão de pacote real):
  ```xml
 <Import Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.x.x.x.x\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Defina a ação de build do arquivo `remapping-config.json` adicionado como **RemappingConfigFile**. O `remapping-config.json` incluído só funciona com Xamarin.Forms. Para outras estruturas de interface do usuário, consulte o arquivo Leiame incluído no pacote NuGet do Remapeador.

## <a name="next-steps"></a>Próximas etapas

Você concluiu as etapas básicas da incorporação do componente ao seu aplicativo. Agora, você pode seguir as etapas incluídas no aplicativo de exemplo de Xamarin para Android. Nós fornecemos dois exemplos, um para Xamarin.Forms e outro para o Android.
