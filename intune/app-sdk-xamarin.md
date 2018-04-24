---
title: Associações Xamarin do SDK de Aplicativo do Microsoft Intune
description: As Associações do Xamarin do SDK de Aplicativo do Intune habilitam a política de Proteção de Aplicativo do Intune em aplicativos Android e iOS criados com o Xamarin.
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
ms.openlocfilehash: 9f9cc117925f59c9fb7c55d0ff10aedf09d26f93
ms.sourcegitcommit: b727b6bd6f138c5def7ac7bf1658068db30a0ec3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Associações Xamarin do SDK de Aplicativo do Microsoft Intune

> [!NOTE]
> Primeiro, leia o artigo [Introdução ao SDK de Aplicativo do Intune](app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.

## <a name="overview"></a>Visão geral
As [Associações do Xamarin do SDK de Aplicativo do Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) habilitam a [Política de Proteção de Aplicativo do Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) em aplicativos Android e iOS criados com o Xamarin. As associações permitem aos desenvolvedores inserir facilmente recursos de Proteção de Aplicativo do Intune em seus aplicativos baseados em Xamarin.

As Associações do Xamarin do SDK de Aplicativo do Microsoft Intune permitem que você incorpore políticas de Proteção de Aplicativo do Intune (também conhecidas como políticas APP ou MAM) a seus aplicativos desenvolvidos com o Xamarin. Um aplicativo habilitado para MAM é um que esteja integrado ao SDK de Aplicativos do Intune. Os administradores de TI podem implantar políticas de proteção do aplicativo ao seu aplicativo móvel quando o Intune gerencia o aplicativo ativamente.

## <a name="whats-supported"></a>Para que há suporte?

### <a name="developer-machines"></a>Computadores de desenvolvedores
* Windows
* macOS


### <a name="mobile-app-platforms"></a>Plataformas de aplicativo móvel
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Cenários de gerenciamento de aplicativo móvel do Intune

* APP-WE do Intune (sem registro de dispositivo)
* Dispositivos registrados no MDM do Intune
* Dispositivos registrados em EMM de terceiros

Os aplicativos Xamarin criados com as Associações do Xamarin do SDK de Aplicativo do Intune agora podem receber políticas de Proteção de Aplicativo do Intune em dispositivos registrados no MDM (gerenciamento de dispositivo móvel) do Intune e em dispositivos não registrados.

## <a name="prerequisites"></a>Pré-requisitos

Examine os [termos de licença](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf). Imprimir e guardar uma cópia dos termos de licença para seus registros. Ao baixar e usar as Associações do Xamarin do SDK de Aplicativo do Intune, você concorda com esses termos de licença. Se você não os aceitar, não use o software.

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Habilite as políticas de proteção de aplicativo do Intune políticas em seu aplicativo móvel iOS
1. Adicione o [pacote do NuGet Microsoft.Intune.MAM.Xamarin.iOS](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) ao seu projeto Xamarin.iOS.
2.  Execute as etapas gerais necessárias para integrar o SDK do Aplicativo do Intune em um aplicativo móvel do iOS. Comece com a etapa 3 das instruções de integração do [Guia do desenvolvedor do SDK do Aplicativo do Intune para iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). É possível ignorar a etapa final na seção de execução do IntuneMAMConfigurator, porque essa ferramenta está incluída no pacote Microsoft.Intune.MAM.Xamarin.iOS e será executada automaticamente em tempo de build.
    **Importante**: a permissão do compartilhamento do conjunto de chaves para um aplicativo é um pouco diferente no Visual Studio e no Xcode. Abra a plist de Direitos do aplicativo e verifique se a opção "Habilitar Conjunto de Chaves" está habilitada, e se os grupos de compartilhamento de conjunto de chaves apropriados foram adicionados nessa seção. Em seguida, verifique se a plist de Direitos está especificada no campo "Direitos Personalizados" das opções de "Assinatura de Pacote do iOS" do projeto para todas as combinações apropriadas de Configuração/Plataforma.
3.  Após a adição das associações e da configuração correta do aplicativo, seu aplicativo pode começar a usar as APIs do SDK do Intune. Para fazer isso, inclua o namespace a seguir:

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
Adicione o [pacote do NuGet Microsoft.Intune.MAM.Xamarin.Android](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) ao seu projeto Xamarin.Android.

Para aplicativos Xamarin.Android, você precisa ler e seguir o [Guia do desenvolvedor do SDK do Aplicativo do Intune para Android](app-sdk-android.md) integralmente, incluindo substituição de classe, métodos e atividades pelos seus equivalentes MAM com base na [tabela](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) incluída no guia. 

> [!NOTE]
> Se o seu aplicativo não definir uma classe `android.app.Application`, você precisará criar uma e verificar se herdou do `MAMApplication`.

> [!NOTE]
> Ao tentar localizar APIs equivalente do [Guia do desenvolvedor do SDK do Aplicativo do Intune para Android](app-sdk-android.md) em Associações do `Microsoft.Intune.MAM.Xamarin.Android` ou converter trechos de código do guia, lembre-se de que o gerador de associações do Xamarin modifica as APIs do Android das seguintes maneiras importantes:
> * Todos os identificadores são convertidos em caso de Pascale (com.microsoft.foo -> Com.Microsoft.Foo)
> * Todas as operações get/set são convertidas em operações de propriedade (por exemplo, Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap")
> * Todas as interfaces têm o caractere 'I' anexado no nome (FooInterface -> IFooInterface)

Para aplicativos que utilizam Xamarin.Forms ou outras estruturas da interface do usuário, nós fornecemos uma ferramenta chamada `Microsoft.Intune.MAM.Remapper`. A ferramenta realiza a substituição de classe para você. Para usá-la, faça o seguinte:

1.  Adicione o pacote do NuGet [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) ao seu projeto.

2.  Defina a ação de build do arquivo `remapping-config.json` que está incluído no pacote do NuGet para **RemappingConfigFile**. O `remapping-config.json` incluído só funciona com Xamarin.Forms. Para outras estruturas de interface do usuário, consulte o arquivo Leiame incluído no pacote NuGet do Remapeador.

3.  Adicione uma chamada para Xamarin.Forms.Forms.Init(Context, Bundle) na função OnMAMCreate do seu MAMApplication porque, com o gerenciamento do Intune, seu aplicativo pode ser iniciado em segundo plano.

4.  Execute o restante das etapas no [Guia do desenvolvedor do SDK do Aplicativo do Intune para Android](app-sdk-android.md) aplicáveis ao seu aplicativo.

> [!NOTE]
> A ação de build de remapping-config.json às vezes pode ser redefinida ao carregar o pacote Microsoft.Intune.MAM.Remapper.Tasks, o que provocaria falha dos seus builds.

## <a name="next-steps"></a>Próximas etapas

Você concluiu as etapas básicas de configuração de seu aplicativo para o gerenciamento do Intune. Agora você pode seguir as etapas incluídas nos guias de integração para cada uma das plataformas listadas acima.

Se a sua organização for um cliente do Intune existente, trabalhe com seu representante do Suporte da Microsoft para abrir um tíquete de suporte e criar um problema [na página de problemas do GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), e nós ajudaremos assim que possível. 