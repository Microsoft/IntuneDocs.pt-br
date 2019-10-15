---
title: Associações Xamarin do SDK de Aplicativo do Microsoft Intune
description: As Associações do Xamarin do SDK de Aplicativo do Intune habilitam a política de Proteção de Aplicativo do Intune em aplicativos Android e iOS criados com o Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/21/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: de367f28f3f1c7731e5ab67d904aec799925cc03
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71733719"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Associações Xamarin do SDK de Aplicativo do Microsoft Intune

> [!NOTE]
> Primeiro, leia o artigo [Introdução ao SDK de Aplicativo do Intune](app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.

## <a name="overview"></a>Visão geral
As [Associações do Xamarin do SDK de Aplicativo do Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) habilitam a [Política de Proteção de Aplicativo do Intune](../apps/app-protection-policy.md) em aplicativos Android e iOS criados com o Xamarin. As associações permitem aos desenvolvedores inserir facilmente recursos de Proteção de Aplicativo do Intune em seus aplicativos baseados em Xamarin.

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

O SDK do Intune depende da [Biblioteca de Autenticação do Active Directory (ADAL)](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) para a [autenticação](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) e cenários de inicialização condicional, o que exige que os aplicativos sejam configurados com o [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). 

Caso seu aplicativo já esteja configurado para usar a ADAL ou a MSAL e tenha sua própria ID do cliente personalizada usada para se autenticar com o Azure Active Directory, verifique se as etapas para conceder permissões do aplicativo Xamarin ao serviço de MAM (gerenciamento de aplicativo móvel) do Intune são seguidas. Use as instruções descritas na seção "[Fornecer ao aplicativo o acesso ao serviço de Proteção de Aplicativo do Intune](app-sdk-get-started.md#give-your-app-access-to-the-intune-app-protection-service-optional)" do [guia de introdução ao SDK do Intune](app-sdk-get-started.md).



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Habilite as políticas de proteção de aplicativo do Intune políticas em seu aplicativo móvel iOS
1. Adicione o [pacote do NuGet Microsoft.Intune.MAM.Xamarin.iOS](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) ao seu projeto Xamarin.iOS.
2. Execute as etapas gerais necessárias para integrar o SDK do Aplicativo do Intune em um aplicativo móvel do iOS. Comece com a etapa 3 das instruções de integração do [Guia do desenvolvedor do SDK do Aplicativo do Intune para iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). É possível ignorar a etapa final na seção de execução do IntuneMAMConfigurator, porque essa ferramenta está incluída no pacote Microsoft.Intune.MAM.Xamarin.iOS e será executada automaticamente em tempo de build.
    **Importante**: a permissão do compartilhamento do conjunto de chaves para um aplicativo é um pouco diferente no Visual Studio e no Xcode. Abra a plist de Direitos do aplicativo e verifique se a opção "Habilitar Conjunto de Chaves" está habilitada, e se os grupos de compartilhamento de conjunto de chaves apropriados foram adicionados nessa seção. Em seguida, verifique se a plist de Direitos está especificada no campo "Direitos Personalizados" das opções de "Assinatura de Pacote do iOS" do projeto para todas as combinações apropriadas de Configuração/Plataforma.
3. Após a adição das associações e da configuração correta do aplicativo, seu aplicativo pode começar a usar as APIs do SDK do Intune. Para fazer isso, inclua o namespace a seguir:

      ```csharp
      using Microsoft.Intune.MAM;
      ```

4. Para começar a receber as políticas de proteção do aplicativo, seu aplicativo deve ser registrado no serviço MAM do Intune. Se o aplicativo não usar a ADAL ([Biblioteca de Autenticação do Azure Active Directory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory)) ou a MSAL ([Biblioteca de Autenticação da Microsoft](https://www.nuget.org/packages/Microsoft.Identity.Client)) para autenticar usuários e você gostaria de ter o SDK do Intune para lidar com a autenticação, seu aplicativo deverá fornecer o UPN do usuário para o método LoginAndEnrollAccount do IntuneMAMEnrollmentManager:

      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

      Os aplicativos poderão passar nulo se o UPN do usuário for desconhecido no momento da chamada. Nesse caso, os usuários deverão inserir seu endereço de email e a senha.
      
      Se o aplicativo já usar a ADAL ou a MSAL para autenticar os usuários, você poderá configurar uma experiência de SSO (logon único) entre seu aplicativo e o SDK do Intune. Primeiro, você precisará configurar a ADAL/MSAL para armazenar os tokens no mesmo grupo de acesso de conjunto de chaves usado pelas Associações do Xamarin do Intune para iOS (com.microsoft.adalcache). Para a ADAL, você pode fazer isso [configurando a propriedade iOSKeychainSecurityGroup de AuthenticationContext](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/wiki/iOS-Keychain-Access). Para a MSAL, você precisará [configurar a propriedade iOSKeychainSecurityGroup do PublicClientApplication](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/Xamarin-iOS-specifics#enable-keychain-access). Em seguida, você precisará substituir as configurações de AAD padrão usadas pelo SDK do Intune com aqueles do seu aplicativo. Faça isso por meio do dicionário IntuneMAMSettings no Info.plist do aplicativo, conforme mencionado no [Guia do desenvolvedor do SDK do Aplicativo do Intune para iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), ou você pode usar as propriedades de substituição do AAD da instância IntuneMAMPolicyManager. A abordagem de Info.plist é recomendada para aplicativos cujas configurações de ADAL são estáticas, enquanto as propriedades de substituição são recomendadas para aplicativos que determinam esses valores em tempo de execução. Depois que todas as configurações do SSO forem configuradas, seu aplicativo deverá fornecer o UPN do usuário para o método RegisterAndEnrollAccount do IntuneMAMEnrollmentManager após a autenticação bem-sucedida:

      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```

      Os aplicativos podem determinar o resultado de uma tentativa de registro implementando o método EnrollmentRequestWithStatus em uma subclasse de IntuneMAMEnrollmentDelegate e configurando a propriedade Delegado do IntuneMAMEnrollmentManager para uma instância da classe. 

      Após um registro bem-sucedido, os aplicativos podem determinar o UPN da conta registrado (se desconhecido anteriormente) consultando a propriedade a seguir: 

      ```csharp
       string enrolledAccount = IntuneMAMEnrollmentManager.Instance.EnrolledAccount;
      ```      
### <a name="sample-applications"></a>Aplicativos de Exemplo
Aplicativos de exemplo destacando a funcionalidade de MAM em aplicativos Xamarin. iOS estão disponíveis no [GitHub](https://github.com/msintuneappsdk/sample-intune-xamarin-ios).

> [!NOTE] 
> Não há nenhum remapeador para o iOS. A integração em um aplicativo Xamarin.Forms deve ser feita da mesma maneira que para um projeto normal do Xamarin.iOS. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Habilitar as políticas de proteção de aplicativo do Intune em seu aplicativo móvel Android
1. Adicione o [pacote do NuGet Microsoft.Intune.MAM.Xamarin.Android](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) ao seu projeto Xamarin.Android.
    1. Para um aplicativo Xamarin.Forms, adicione o [pacote do NuGet Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) ao seu projeto Xamarin.Android também. 
2. Siga as etapas gerais necessárias para [integrar o SDK do Aplicativo do Intune](app-sdk-android.md) a um aplicativo móvel Android enquanto consulta este documento para obter mais detalhes.

### <a name="xamarinandroid-integration"></a>Integração do Xamarin.Android

Uma visão geral completa para a integração do SDK do aplicativo do Intune pode ser encontrada no [guia do desenvolvedor do SDK do Aplicativo Microsoft Intune para Android](app-sdk-android.md). Conforme você lê o guia e integra o SDK do Aplicativo Intune ao seu aplicativo Xamarin, as seções a seguir destinam-se para realçar as diferenças entre a implementação para um aplicativo nativo do Android desenvolvido em Java e um aplicativo Xamarin desenvolvido em C#. Estas seções devem ser tratadas como complementares e não podem atuar como um substituto à leitura do guia em sua totalidade.

#### <a name="remapper"></a>Remapeador
A partir da versão 1.4428.1, o pacote `Microsoft.Intune.MAM.Remapper` pode ser adicionado a um aplicativo Xamarin. Android como [ferramentas de compilação](app-sdk-android.md#build-tooling) para executar a classe MAM, o método e as substituições dos serviços de sistemas. Se o remapeador for incluído, as seções de substituição equivalentes de MAM dos métodos renomeados e de aplicativo MAM serão executadas automaticamente quando o aplicativo for compilado.

Para excluir uma classe de MAM-unificação pelo remapeador, a seguinte propriedade pode ser adicionada em seu arquivo de projetos `.csproj`.

```xml
  <PropertyGroup>
    <ExcludeClasses>Semicolon separated list of relative class paths to exclude from MAM-ification</ExcludeClasses>
  </PropertyGroup>
```

> [!NOTE]
> Neste momento, um problema com o remapeador impede a depuração em aplicativos Xamarin. Android. A integração manual é recomendada para depurar seu aplicativo até que esse problema seja resolvido.

#### <a name="renamed-methodsapp-sdk-androidmdrenamed-methods"></a>[Métodos renomeados](app-sdk-android.md#renamed-methods)
Em muitos casos, um método disponível na classe Android foi marcado como final na classe de MAM de substituição. Nesse caso, a classe de MAM de substituição fornece um método nomeado da mesma forma (com o sufixo `MAM`), que deve ser substituído em vez disso. Por exemplo, ao derivar de `MAMActivity`, em vez de substituir `OnCreate()` e chamar `base.OnCreate()`, `Activity` deve substituir `OnMAMCreate()` e chamar `base.OnMAMCreate()`.

#### <a name="mam-applicationapp-sdk-androidmdmamapplication"></a>[Aplicativo MAM](app-sdk-android.md#mamapplication)
Seu aplicativo deve definir uma classe `Android.App.Application`. Se você estiver integrando o MAM manualmente, ele deverá herdar de `MAMApplication`. Verifique se a subclasse está corretamente decorada com o atributo `[Application]` e substitui o construtor `(IntPtr, JniHandleOwnership)`.

```csharp
    [Application]
    class TaskrApp : MAMApplication
    {
    public TaskrApp(IntPtr handle, JniHandleOwnership transfer)
        : base(handle, transfer) { }
```

> [!NOTE]
> Um problema com as associações do Xamarin MAM pode fazer com que o aplicativo falhe quando implantado no modo de depuração. Como alternativa, o atributo `Debuggable=false` deve ser adicionado à classe `Application` e o sinalizador `android:debuggable="true"` deve ser removido do manifesto se foi definido manualmente.

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

#### <a name="mam-enrollment-managerapp-sdk-androidmdmamenrollmentmanager"></a>[Gerenciador de Registros do MAM](app-sdk-android.md#mamenrollmentmanager)

```csharp
IMAMEnrollmentManager mgr = MAMComponents.Get<IMAMEnrollmentManager>();
```

### <a name="xamarinforms-integration"></a>Integração do Xamarin.Forms

Para aplicativos `Xamarin.Forms`, o pacote `Microsoft.Intune.MAM.Remapper` executa a substituição de classe MAM injetando automaticamente as classes `MAM` na hierarquia de classes referente a classes `Xamarin.Forms` comumente usadas. 

> [!NOTE]
> A integração com o Xamarin.Forms deve ser feita além da integração com o Xamarin.Android detalhada acima. O remapeador se comporta de forma diferente para aplicativos Xamarin. Forms, de modo que as substituições de MAM manuais ainda precisarão ser feitas.

Depois que o remapeador é adicionado ao seu projeto, que você precisa executar as substituições equivalentes do MAM. Por exemplo, `FormsAppCompatActivity` e `FormsApplicationActivity` podem continuar sendo usados em seu aplicativo, desde que as substituições para `OnCreate` e `OnResume` sejam substituídas pelos equivalentes do MAM `OnMAMCreate` e `OnMAMResume`, respectivamente.

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

Se as substituições não forem feitas, você poderá encontrar os seguintes erros de compilação até que faça as substituições:
* [Erro do compilador CS0239](https://docs.microsoft.com/dotnet/csharp/misc/cs0239). Esse erro é geralmente visto desta forma: ``'MainActivity.OnCreate(Bundle)': cannot override inherited member 'MAMAppCompatActivityBase.OnCreate(Bundle)' because it is sealed``.
Isso é esperado porque quando o remapeador modifica a herança de classes do Xamarin, algumas funções são tornadas `sealed` e, em vez disso, uma nova variante do MAM é adicionada para substituição.
* [Erro do Compilador CS0507](https://docs.microsoft.com/dotnet/csharp/language-reference/compiler-messages/cs0507): esse erro geralmente é visto neste formulário ``'MyActivity.OnRequestPermissionsResult()' cannot change access modifiers when overriding 'public' inherited member ...``. Quando o Remapeador faz alterações na herança de algumas das classes Xamarin, algumas das funções de membro são alteradas para `public`. Se você substituir qualquer uma dessas funções, precisará alterar esses modificadores de acesso para essas substituições serem `public` também.

> [!NOTE]
> O Remapeador regrava uma dependência que o Visual Studio usa para preenchimento automático do IntelliSense. Portanto, você talvez precise recarregar e recompilar o projeto quando o remapeador for adicionado para o IntelliSense reconhecer corretamente as alterações.

#### <a name="troubleshooting"></a>Solução de problemas
* Se você estiver encontrando uma tela branca em branco em seu aplicativo na inicialização, talvez seja necessário forçar as chamadas de navegação a serem executadas no thread principal.
* As associações do Xamarin SDK do Intune não oferecem suporte a aplicativos que usam uma estrutura de plataforma cruzada, como MvvmCross, devido a conflitos entre MvvmCross e classes MAM do Intune. Embora alguns clientes possam ter tido sucesso com a integração depois de mover seus aplicativos para o Xamarin. Forms, não fornecemos orientações ou plugins explícitos para desenvolvedores de aplicativos usando o MvvmCross.

### <a name="company-portal-app"></a>Aplicativo do Portal da Empresa
As associações do Xamarin SDK do Intune dependem da presença do aplicativo [portal da empresa](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) Android no dispositivo para habilitar as políticas de proteção do aplicativo. O Portal da Empresa recupera as políticas de proteção de aplicativo do serviço Intune. Quando o aplicativo é inicializado, ele carrega a política e o código para impor essa política do Portal da Empresa. O usuário não precisa estar conectado.

> [!NOTE]
> Quando o aplicativo do Portal da Empresa não está no dispositivo **Android**, um aplicativo gerenciado pelo Intune comporta-se como um aplicativo normal que não é compatível com as políticas de proteção de aplicativo do Intune.

Para a proteção do aplicativo sem registro de dispositivo, o usuário _**não**_ precisa registrar o dispositivo usando o aplicativo do Portal da Empresa.

### <a name="sample-applications"></a>Aplicativos de Exemplo
Aplicativos de exemplo destacando a funcionalidade de MAM nos aplicativos Xamarin. Android e Xamarin. Forms estão disponíveis no [GitHub](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps).

## <a name="support"></a>Suporte
Se a sua organização for um cliente do Intune existente, trabalhe com seu representante do Suporte da Microsoft para abrir um tíquete de suporte e criar um problema [na página de problemas do GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues). Ajudaremos assim que for possível. 