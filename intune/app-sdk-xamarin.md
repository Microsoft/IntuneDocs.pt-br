---
title: Associações Xamarin do SDK de Aplicativo do Microsoft Intune
description: As Associações do Xamarin do SDK de Aplicativo do Intune habilitam a política de Proteção de Aplicativo do Intune em aplicativos Android e iOS criados com o Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/16/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: bd162f6af256c104c04374290a695141cdcc26f6
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566192"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Associações Xamarin do SDK de Aplicativo do Microsoft Intune

> [!NOTE]
> Primeiro, leia o artigo [Introdução ao SDK de Aplicativo do Intune](app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.

## <a name="overview"></a>Visão geral
As [Associações do Xamarin do SDK de Aplicativo do Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) habilitam a [Política de Proteção de Aplicativo do Intune](app-protection-policy.md) em aplicativos Android e iOS criados com o Xamarin. As associações permitem aos desenvolvedores inserir facilmente recursos de Proteção de Aplicativo do Intune em seus aplicativos baseados em Xamarin.

As Associações do Xamarin do SDK de Aplicativo do Microsoft Intune permitem que você incorpore políticas de Proteção de Aplicativo do Intune (também conhecidas como políticas APP ou MAM) a seus aplicativos desenvolvidos com o Xamarin. Um aplicativo habilitado para MAM é um que esteja integrado ao SDK de Aplicativos do Intune. Os administradores de TI podem implantar políticas de proteção do aplicativo ao seu aplicativo móvel quando o Intune gerencia o aplicativo ativamente.

## <a name="whats-supported"></a>Para que há suporte?

### <a name="developer-machines"></a>Computadores de desenvolvedores
* Windows (Visual Studio versão 15.7 e posterior)
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

O SDK depende da [Biblioteca de Autenticação do Active Directory (ADAL)](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) para a [autenticação](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) e cenários de inicialização condicional, o que exige que os aplicativos sejam configurados com o [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). 

Caso seu aplicativo já esteja configurado para usar a ADAL ou a MSAL e tenha sua própria ID do cliente personalizada usada para se autenticar com o Azure Active Directory, verifique se as etapas para conceder permissões do aplicativo Xamarin ao serviço de MAM (gerenciamento de aplicativo móvel) do Intune são seguidas. Use as instruções descritas na seção "[Fornecer ao aplicativo o acesso ao serviço de Proteção de Aplicativo do Intune](app-sdk-get-started.md#give-your-app-access-to-the-intune-app-protection-service-optional)" do [guia de introdução ao SDK do Intune](app-sdk-get-started.md).

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Habilite as políticas de proteção de aplicativo do Intune políticas em seu aplicativo móvel iOS
1. Adicione o [pacote do NuGet Microsoft.Intune.MAM.Xamarin.iOS](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) ao seu projeto Xamarin.iOS.
2.  Execute as etapas gerais necessárias para integrar o SDK do Aplicativo do Intune em um aplicativo móvel do iOS. Comece com a etapa 3 das instruções de integração do [Guia do desenvolvedor do SDK do Aplicativo do Intune para iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). É possível ignorar a etapa final na seção de execução do IntuneMAMConfigurator, porque essa ferramenta está incluída no pacote Microsoft.Intune.MAM.Xamarin.iOS e será executada automaticamente em tempo de build.
    **Importante**: a permissão do compartilhamento do conjunto de chaves para um aplicativo é um pouco diferente no Visual Studio e no Xcode. Abra a plist de Direitos do aplicativo e verifique se a opção "Habilitar Conjunto de Chaves" está habilitada, e se os grupos de compartilhamento de conjunto de chaves apropriados foram adicionados nessa seção. Em seguida, verifique se a plist de Direitos está especificada no campo "Direitos Personalizados" das opções de "Assinatura de Pacote do iOS" do projeto para todas as combinações apropriadas de Configuração/Plataforma.
3.  Após a adição das associações e da configuração correta do aplicativo, seu aplicativo pode começar a usar as APIs do SDK do Intune. Para fazer isso, inclua o namespace a seguir:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Para começar a receber as políticas de proteção do aplicativo, seu aplicativo deve ser registrado no serviço MAM do Intune. Se o aplicativo não usar a ADAL ([Biblioteca de Autenticação do Azure Active Directory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory)) ou a MSAL ([Biblioteca de Autenticação da Microsoft](https://www.nuget.org/packages/Microsoft.Identity.Client)) para autenticar usuários e você gostaria de ter o SDK do Intune para lidar com a autenticação, seu aplicativo deverá fornecer o UPN do usuário para o método LoginAndEnrollAccount do IntuneMAMEnrollmentManager:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```
      Os aplicativos poderão passar nulo se o UPN do usuário for desconhecido no momento da chamada. Nesse caso, os usuários deverão inserir seu endereço de email e a senha.
      
      Se o aplicativo já usar a ADAL ou a MSAL para autenticar os usuários, você poderá configurar uma experiência de SSO (logon único) entre seu aplicativo e o SDK do Intune. Primeiro, você precisará configurar a ADAL/MSAL para armazenar os tokens no mesmo grupo de acesso de conjunto de chaves usado pelas Associações do Xamarin do Intune para iOS (com.microsoft.adalcache). Para a ADAL, você pode fazer isso [configurando a propriedade KeychainSecurityGroup de AuthenticationContext](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/wiki/Token-cache-serialization#enable-token-cache-sharing-across-ios-applications). Para a MSAL, você precisará [configurar a propriedade KeychainSecurityGroup do PublicClientApplication](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/msal-net-2-released#you-can-now-enable-sso-between-adal-and-msal-apps-on-xamarinios). Em seguida, você precisará substituir as configurações de AAD padrão usadas pelo SDK do Intune com aqueles do seu aplicativo. Faça isso por meio do dicionário IntuneMAMSettings no Info.plist do aplicativo, conforme mencionado no [Guia do desenvolvedor do SDK do Aplicativo do Intune para iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), ou você pode usar as propriedades de substituição do AAD da instância IntuneMAMPolicyManager. A abordagem de Info.plist é recomendada para aplicativos cujas configurações de ADAL são estáticas, enquanto as propriedades de substituição são recomendadas para aplicativos que determinam esses valores em tempo de execução. Depois que todas as configurações do SSO forem configuradas, seu aplicativo deverá fornecer o UPN do usuário para o método RegisterAndEnrollAccount do IntuneMAMEnrollmentManager após a autenticação bem-sucedida:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      Os aplicativos podem determinar o resultado de uma tentativa de registro implementando o método EnrollmentRequestWithStatus em uma subclasse de IntuneMAMEnrollmentDelegate e configurando a propriedade Delegado do IntuneMAMEnrollmentManager para uma instância da classe. Consulte nosso [aplicativo de amostra do Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) para ver um exemplo.

      Após um registro bem-sucedido, os aplicativos podem determinar o UPN da conta registrado (se desconhecido anteriormente) consultando a propriedade a seguir: 
      ```csharp
       string enrolledAccount = IntuneMAMEnrollmentManager.Instance.EnrolledAccount;
      ```      
> [!NOTE] 
> Não há nenhum remapeador para o iOS. A integração em um aplicativo Xamarin.Forms deve ser feita da mesma maneira que para um projeto normal do Xamarin.iOS. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Habilitar as políticas de proteção de aplicativo do Intune em seu aplicativo móvel Android

1. Adicione o [pacote do NuGet Microsoft.Intune.MAM.Xamarin.Android](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) ao seu projeto Xamarin.Android.
    1. Para um aplicativo xamarin. Forms, adicione a [pacote do Microsoft.Intune.MAM.Remapper.Tasks NuGet](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) ao seu projeto xamarin. Android também. 
2. Siga as etapas gerais necessárias para [a integração do SDK do Intune App](app-sdk-android.md) em um aplicativo móvel Android, fazendo referência a este documento para obter mais detalhes.

### <a name="xamarinandroid-integration"></a>Integração do Xamarin.Android

Uma visão geral completa para a integração do SDK do Intune App pode ser encontrada na [Microsoft Intune App SDK para o guia do desenvolvedor Android](app-sdk-android.md). Como ler o guia e integrar o SDK do Intune App ao seu aplicativo Xamarin as seções a seguir destinam-se para destacar as diferenças entre a implementação para um aplicativo nativo do Android desenvolvido em Java e um aplicativo Xamarin desenvolvido em C#. Estas seções devem ser tratadas como complementares e não podem atuar como um substituto para ler o guia em sua totalidade.

#### <a name="renamed-methodsapp-sdk-androidmdrenamed-methods"></a>[Métodos renomeados](app-sdk-android.md#renamed-methods)
Em muitos casos, um método disponível na classe Android foi marcado como final na classe de MAM de substituição. Nesse caso, a classe de MAM de substituição fornece um método nomeado da mesma forma (com o sufixo `MAM`), que deve ser substituído em vez disso. Por exemplo, ao derivar de `MAMActivity`, em vez de substituir `OnCreate()` e chamar `base.OnCreate()`, `Activity` deve substituir `OnMAMCreate()` e chamar `base.OnMAMCreate()`.

#### <a name="mam-applicationapp-sdk-androidmdmamapplication"></a>[Aplicativo de MAM](app-sdk-android.md#mamapplication)
Seu aplicativo deve definir um `Android.App.Application` classe que herda de `MAMApplication`. Verifique se a subclasse está corretamente decorada com o atributo `[Application]` e substitui o construtor `(IntPtr, JniHandleOwnership)`.
```csharp
    [Application]
    class TaskrApp : MAMApplication
    {
    public TaskrApp(IntPtr handle, JniHandleOwnership transfer)
        : base(handle, transfer) { }
```

#### <a name="enable-features-that-require-app-participationapp-sdk-androidmdenable-features-that-require-app-participation"></a>[Habilitar recursos que exigem a participação do aplicativo](app-sdk-android.md#enable-features-that-require-app-participation)
Exemplo: determinar se o PIN é necessário para o aplicativo
```csharp
MAMPolicyManager.GetPolicy(currentActivity).IsPinRequired;
```
Exemplo: determinar o usuário principal do Intune
```csharp
IMAMUserInfo info = MAMComponents.Get<IMAMUserInfo>();
return info?.PrimaryUser;
```
Exemplo: determinar se é permitido salvar em dispositivo ou armazenamento em nuvem
```csharp
MAMPolicyManager.GetPolicy(currentActivity).GetIsSaveToLocationAllowed(SaveLocation service, String username);
```

#### <a name="register-for-notifications-from-the-sdkapp-sdk-androidmdregister-for-notifications-from-the-sdk"></a>[Registrar-se para notificações do SDK](app-sdk-android.md#register-for-notifications-from-the-sdk)
O aplicativo deve ser registrado para receber notificações do SDK, criando uma `MAMNotificationReceiver` e registrando-a com `MAMNotificationReceiverRegistry`. Isso é feito fornecendo o receptor e o tipo de notificação desejada em `App.OnMAMCreate`, como mostra o exemplo a seguir:
```csharp
public override void OnMAMCreate()
{
    // Register the notification receivers
    IMAMNotificationReceiverRegistry registry = MAMComponents.Get<IMAMNotificationReceiverRegistry>();
    foreach (MAMNotificationType notification in MAMNotificationType.Values())
    {
    registry.RegisterReceiver(new ToastNotificationReceiver(this), notification);
    }
    ...
```

#### <a name="mam-enrollment-managerapp-sdk-androidmdmamenrollmentmanager"></a>[Gerenciador de registro de MAM](app-sdk-android.md#mamenrollmentmanager)
```csharp
IMAMEnrollmentManager mgr = MAMComponents.Get<IMAMEnrollmentManager>();
```

### <a name="xamarinforms-integration"></a>Integração do Xamarin.Forms

Para `Xamarin.Forms` aplicativos que fornecemos a `Microsoft.Intune.MAM.Remapper` pacote para executar a substituição de classe MAM automaticamente injetando `MAM` classes na hierarquia da classe de comumente usados `Xamarin.Forms` classes. 

> [!NOTE]
> A integração com o xamarin. Forms deve ser feito, além disso, para a integração com o xamarin. Android detalhada acima.

Depois que o remapeador é adicionado ao seu projeto, que você precisará executar as substituições equivalentes do MAM. Por exemplo, `FormsAppCompatActivity` e `FormsApplicationActivity` pode continuar a ser usado em suas substituições de aplicativo fornecido para `OnCreate` e `OnResume` são substituídas por equivalentes do MAM `OnMAMCreate` e `OnMAMResume` , respectivamente.

```csharp
    public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
    {
        protected override void OnMAMCreate(Bundle savedInstanceState)
        {
            base.OnMAMCreate(savedInstanceState);
            global::Xamarin.Forms.Forms.Init(this, savedInstanceState);
            LoadApplication(new App());
        }
```
Se as substituições não forem feitas, em seguida, você pode encontrar os seguintes erros de compilação até que você faça as substituições:
* [Erro do compilador CS0239](https://docs.microsoft.com/dotnet/csharp/misc/cs0239). Esse erro é geralmente visto desta forma: ``'MainActivity.OnCreate(Bundle)': cannot override inherited member 'MAMAppCompatActivityBase.OnCreate(Bundle)' because it is sealed``.
Isso é esperado porque quando o remapeador modifica a herança de classes do Xamarin, algumas funções são tornadas `sealed` e, em vez disso, uma nova variante do MAM é adicionada para substituição.
* [Erro do compilador CS0507](https://docs.microsoft.com/dotnet/csharp/language-reference/compiler-messages/cs0507): esse erro é geralmente visto neste formulário ``'MyActivity.OnRequestPermissionsResult()' cannot change access modifiers when overriding 'public' inherited member ...``. Quando o Remapeador faz alterações na herança de algumas das classes Xamarin, algumas das funções de membro são alteradas para `public`. Se você substituir qualquer uma dessas funções, você precisará alterá-los os modificadores de acesso para as substituições para ser `public` também.

> [!NOTE]
> O remapeador regrava uma dependência que o Visual Studio usa para AutoPreenchimento IntelliSense. Portanto, você talvez precise recarregar e recompile o projeto quando o remapeador é adicionado para o IntelliSense reconhecer corretamente as alterações.

## <a name="support"></a>Suporte
Se a sua organização for um cliente do Intune existente, trabalhe com seu representante do Suporte da Microsoft para abrir um tíquete de suporte e criar um problema [na página de problemas do GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues), e nós ajudaremos assim que possível. 
