---
title: Guia do desenvolvedor do SDK de Aplicativos do Microsoft Intune para iOS
description: O SDK de Aplicativos do Microsoft Intune para iOS permite incorporar políticas de proteção de aplicativo do Intune (também conhecidas como políticas MAM ou APP) ao seu aplicativo iOS nativo.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: aanavath
ms.suite: ems
ms.custom: ''
ms.openlocfilehash: c9920e914a80ec3bb02f5066e6d6e34b2236c860
ms.sourcegitcommit: 5d5448f6c365aeb01d6f2488bf122024b9616bec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2018
ms.locfileid: "51212488"
---
# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>Guia do desenvolvedor do SDK de Aplicativos do Microsoft Intune para iOS

> [!NOTE]
> Considere ler o artigo [Guia de Introdução ao SDK de Aplicativos do Intune](app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma compatível.

O SDK de Aplicativos do Microsoft Intune para iOS permite incorporar políticas de proteção de aplicativo do Intune (também conhecidas como **políticas MAM** ou **APP**) ao seu aplicativo iOS nativo. Um aplicativo habilitado para MAM é um que esteja integrado ao SDK de Aplicativos do Intune. Os administradores de TI podem implantar políticas de proteção do aplicativo ao seu aplicativo móvel quando o Intune gerencia o aplicativo ativamente.

## <a name="prerequisites"></a>Pré-requisitos

* Você precisará de um computador Mac OS que execute o OS X 10.8.5 ou posterior e tenha o Xcode 9 ou posterior instalado.

* Seu aplicativo precisa estar direcionado para o iOS 10 ou posterior.

* Examinar os [Termos de Licença do SDK de Aplicativos do Intune para iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS.pdf). Imprimir e guardar uma cópia dos termos de licença para seus registros. Ao baixar e usar o SDK de Aplicativos do Intune para iOS, você concorda com esses termos de licença.  Se você não os aceitar, não use o software.

* Baixar os arquivos para o SDK de Aplicativos do Intune para iOS no [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).

## <a name="whats-in-the-sdk"></a>Novidades no SDK

O SDK de Aplicativos do Intune para iOS inclui uma biblioteca estática, arquivos de recursos, cabeçalhos de API, um arquivo .plist de configurações de depuração e uma ferramenta do configurador. Os aplicativos cliente podem simplesmente incluir os arquivos de recursos e um link estático para as bibliotecas para a maioria das imposições de política. Os recursos avançados de APP do Intune são aplicados por meio de APIs.

Este guia aborda o uso dos seguintes componentes do SDK de Aplicativos do Intune para iOS:

* **libIntuneMAM.a**: a biblioteca estática do SDK de Aplicativos do Intune. Se o aplicativo não usar extensões, vincule essa biblioteca ao seu projeto para habilitar o aplicativo para o gerenciamento de aplicativo de cliente do Intune.

* **IntuneMAM.framework**: a estrutura do SDK de Aplicativos do Intune. Vincule essa estrutura ao projeto para habilitar o aplicativo para o gerenciamento de aplicativo cliente do Intune. Use a estrutura em vez da biblioteca estática se o aplicativo usar extensões, para que o projeto não crie várias cópias da biblioteca estática.

* **IntuneMAMResources.bundle**: um pacote de recursos que contém recursos dos quais o SDK depende.

* **Cabeçalhos**: expõem as APIs do SDK de Aplicativos do Intune. Se você usar uma API, precisará incluir o arquivo de cabeçalho que contém a API. Os Arquivos de Cabeçalho a seguir incluem APIs, tipos de dados e protocolos que o SDK do aplicativo do Intune disponibiliza para desenvolvedores:

    * IntuneMAMAppConfig.h
    * IntuneMAMAppConfigManager.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMDefs.h
    * IntuneMAMEnrollmentDelegate.h
    * IntuneMAMEnrollmentManager.h
    * IntuneMAMEnrollmentStatus.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMLogger.h
    * IntuneMAMPolicy.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMPolicyManager.h
    * IntuneMAMVersionInfo.h

Para que os desenvolvedores possam disponibilizar o conteúdo de todos os cabeçalhos acima, basta apenas importar IntuneMAM.h


## <a name="how-the-intune-app-sdk-works"></a>Como o SDK de Aplicativos do Intune funciona

O objetivo do SDK do Intune APP para iOS é adicionar recursos de gerenciamento de aplicativos a aplicativos iOS com alterações mínimas de código. Quanto menos alterações houver no código, menor será o tempo de chegada no mercado — sem afetar a consistência e a estabilidade do aplicativo móvel.


## <a name="build-the-sdk-into-your-mobile-app"></a>Compilar o SDK em seu aplicativo móvel

Para habilitar o SDK de Aplicativos do Intune, siga estas etapas:

1. **Opção 1 (recomendado)**: vincule `IntuneMAM.framework` ao seu projeto. Arraste `IntuneMAM.framework` para a lista **Binários inseridos** do destino do projeto.

   > [!NOTE]
   > Se você usar a estrutura, precisará remover manualmente as arquiteturas de simulador da estrutura universal antes de enviar seu aplicativo à App Store. Confira [Enviar seu aplicativo à App Store](#Submit-your-app-to-the-App-Store) para obter mais detalhes.

   **Opção 2**: link para a biblioteca `libIntuneMAM.a`. Arraste a biblioteca `libIntuneMAM.a` na lista **Estruturas e Bibliotecas Vinculadas** do destino do projeto.

    ![SDK de Aplicativos do Intune para iOS: estruturas e bibliotecas vinculadas](./media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    Adicione `-force_load {PATH_TO_LIB}/libIntuneMAM.a` a um dos seguintes, substituindo `{PATH_TO_LIB}` pelo local do SDK de Aplicativos do Intune:
   * A definição de configuração de build `OTHER_LDFLAGS` do projeto
   * Os **Outros Sinalizadores do Vinculador** da interface do usuário do Xcode

     > [!NOTE]
     > Para encontrar `PATH_TO_LIB`, selecione o arquivo `libIntuneMAM.a` e escolha **Obter Informações** no menu **Arquivo**. Copie e cole as informações **Onde** (o caminho) na seção **Geral** da janela **Informações**.

     Adicione o pacote de recursos `IntuneMAMResources.bundle` ao projeto arrastando-o para **Copiar Recursos do Pacote** em **Fases de Build**.

     ![SDK de Aplicativos do Intune para iOS: copiar recursos do pacote](./media/intune-app-sdk-ios-copy-bundle-resources.png)

2. Adicione as seguintes estruturas de iOS ao projeto:  
    * MessageUI.framework  
    * Security.framework  
    * MobileCoreServices.framework  
    * SystemConfiguration.framework  
    * libsqlite3.tbd  
    * libc++.tbd  
    * ImageIO.framework  
    * LocalAuthentication.framework  
    * AudioToolbox.framework  
    * QuartzCore.framework  
    * WebKit.framework

3. Habilite o compartilhamento de conjunto de chaves (se já não estiver habilitado) escolhendo em **Funcionalidades** em cada destino do projeto e habilitando a opção **Compartilhamento de Conjunto de Chaves**. O compartilhamento de conjunto de chaves é necessário para que você prossiga para a próxima etapa.

   > [!NOTE]
   > O perfil de provisionamento precisa dar suporte aos novos valores de compartilhamento de conjunto de chaves. Os grupos de acesso do conjunto de chaves devem dar suporte a um caractere curinga. Você pode verificar isso abrindo o arquivo .mobileprovision em um editor de texto, pesquisando por **keychain-access-groups** e garantindo que há um curinga. Por exemplo:
   >  ```xml
   >  <key>keychain-access-groups</key>
   >  <array>
   >  <string>YOURBUNDLESEEDID.*</string>
   >  </array>
   >  ```

4. Depois que você habilitar o compartilhamento de conjunto de chaves, siga estas etapas para criar um grupo de acesso separado no qual o SDK de Aplicativos do Intune armazenará seus dados. Você pode criar um grupo de acesso do conjunto de chaves usando a interface do usuário ou o arquivo de direitos. Se você estiver usando a interface do usuário para criar o grupo de acesso do conjunto de chaves, certifique-se de seguir as etapas abaixo:

   1. Se seu aplicativo móvel não tiver grupos de acesso do conjunto de chaves definidos, adicione a ID do pacote do aplicativo como o primeiro grupo.

   2. Adicione o grupo de conjunto de chaves compartilhado `com.microsoft.intune.mam` aos grupos de acesso existentes. O SDK de Aplicativos do Intune usa esse grupo de acesso para armazenar dados.

   3. Adicione `com.microsoft.adalcache` aos grupos de acesso existentes.

       ![SDK de Aplicativo do Intune para iOS: compartilhamento de conjunto de chaves](./media/intune-app-sdk-ios-keychain-sharing.png)

   4. Se você estiver editando o arquivo de direitos diretamente, em vez de usar a interface do usuário do Xcode exibida acima para criar os grupos de acesso do conjunto de chaves, preceda os grupos de acesso do conjunto de chaves com `$(AppIdentifierPrefix)` (o Xcode gerenciará isso automaticamente). Por exemplo:

           * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
           * `$(AppIdentifierPrefix)com.microsoft.adalcache`

      > [!NOTE]
      > Um arquivo de direitos é um arquivo XML exclusivo ao aplicativo móvel. Ele é usado para especificar funcionalidades e permissões especiais em seu aplicativo iOS. Se o seu aplicativo não tinha um arquivo de direitos anteriormente, habilitar o compartilhamento do conjunto de chaves (etapa 3) deve fazer o Xcode gerar um para seu aplicativo.

5. Inclua todos os protocolos que o aplicativo passar para `UIApplication canOpenURL` na matriz `LSApplicationQueriesSchemes` do arquivo Info.plist do aplicativo. Salve as alterações antes de prosseguir para a próxima etapa.

6. Se o aplicativo ainda não usa a FaceID, verifique se a chave [NSFaceIDUsageDescription Info.plist](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251-SW75) está configurada com uma mensagem padrão. Isso é necessário para que o iOS possa informar o usuário de como o aplicativo pretende usar a FaceID. Uma configuração de política de Proteção de Aplicativo do Intune permite que a FaceID seja usada como um método para o acesso ao aplicativo quando definida pelo administrador de TI.

7. Use a ferramenta IntuneMAMConfigurator que está incluída no [repositório SDK](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios) para concluir a configuração do Info.plist de seu aplicativo. A ferramenta tem três parâmetros:

   |Propriedade|Como usá-lo|
   |---------------|--------------------------------|
   |- i |  `<Path to the input plist>` |
   |- e | `<Path to the entitlements file>` |
   |- o |  (Opcional) `<Path to the output plist>` |

Se o parâmetro '-o' não for especificado, o arquivo de entrada será modificado in-loco. A ferramenta é idempotente e deve ser executada novamente sempre que forem feitas alterações nos direitos ou no Info.plist do aplicativo. Você também deve baixar e executar a versão mais recente da ferramenta ao atualizar o SDK do Intune, caso os requisitos de configuração do Info.plist tiverem sido alterados na versão mais recente.

## <a name="configure-azure-active-directory-authentication-library-adal"></a>Configurar a ADAL (Biblioteca de Autenticação do Azure Active Directory)

O SDK de Aplicativos do Intune usa a [Biblioteca de Autenticação do Azure Active Directory](https://github.com/AzureAD/azure-activedirectory-library-for-objc) para seus cenários de inicialização condicional e autenticação. Ele também se baseia na ADAL para registrar a identidade do usuário no serviço de MAM para gerenciamento sem cenários de registro de dispositivo.

Normalmente, a ADAL requer que os aplicativos se registrem no AAD (Azure Active Directory) e obtenham uma ID exclusiva (ID do cliente), e outros identificadores, para garantir a segurança dos tokens concedidos ao aplicativo. A menos que especificado de outra forma, o SDK de Aplicativos do Intune usa valores de registro padrão ao entrar em contato com o Azure AD.  

Se o aplicativo já usar ADAL para autenticar usuários, o aplicativo deverá usar seus valores de registro existentes e substituir os valores padrão do SDK de Aplicativos do Intune. Isso garante que a autenticação não seja solicitada duas vezes aos usuários (uma vez pelo SDK de Aplicativos do Intune e uma vez pelo aplicativo).

É recomendável que seu aplicativo contenha links para a [versão mais recente da ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) na sua ramificação mestre. Atualmente, o SDK de Aplicativos do Intune usa a ramificação do agente da ADAL para dar suporte a aplicativos que precisam de acesso condicional. (Esses aplicativos, portanto, dependem do aplicativo Microsoft Authenticator.) No entanto, o SDK ainda é compatível com a ramificação mestre da ADAL. Use a ramificação apropriada para seu aplicativo.

### <a name="link-to-adal-binaries"></a>Vincular a binários da ADAL

Siga as etapas abaixo para vincular seu aplicativo aos binários da ADAL:

1. Baixe o [Azure Active Directory Authentication Library (ADAL) for Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) (ADAL (Biblioteca de Autenticação do Azure Active Directory)) do GitHub e siga as [instruções](https://github.com/AzureAD/azure-activedirectory-library-for-objc#download) sobre como baixar a ADAL usando submódulos Git ou CocoaPods.

2. Adicione a estrutura ADAL (opção 1) ou a biblioteca estática (opção 2) ao projeto.

3. Se o aplicativo não tiver grupos de acesso do conjunto de chaves definidos, adicione a ID do pacote do aplicativo como o primeiro grupo.

4. Habilite o SSO (logon único) da ADAL adicionando `com.microsoft.adalcache` e `com.microsoft.workplacejoin` aos grupos de acesso de conjunto de chaves.

5. Caso você esteja definindo explicitamente o grupo de conjunto de chaves do cache compartilhado da ADAL, verifique se ele está definido como `<appidprefix>.com.microsoft.adalcache`. A ADAL definirá isso para você a menos que você faça uma substituição. Se você quiser especificar um grupo de conjunto de chaves personalizado para substituir `com.microsoft.adalcache`, especifique isso no arquivo Info.plist em IntuneMAMSettings, usando a chave `ADALCacheKeychainGroupOverride`.

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a>Configurar a ADAL para o SDK de Aplicativos do Intune

Se seu aplicativo já usa a ADAL para autenticação e tem suas próprias configurações de ADAL, você pode forçar o SDK de Aplicativos do Intune a usar as mesmas configurações durante a autenticação no Azure Active Directory. Isso garante que o aplicativo não solicitará duas vezes a autenticação do usuário. Consulte [Definir as configurações para o SDK de Aplicativos do Intune](#configure-settings-for-the-intune-app-sdk) para obter informações sobre como popular as seguintes configurações:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Se seu aplicativo já usar a ADAL, serão necessárias as seguintes configurações:

1. No arquivo Info.plist do projeto, no dicionário **IntuneMAMSettings** com o nome de chave `ADALClientId`, especifique a ID do cliente a ser usada para chamadas da ADAL.

2. Também no dicionário **IntuneMAMSettings** com o nome da chave `ADALAuthority`, especifique a autoridade do Azure AD.

3. Também no dicionário **IntuneMAMSettings** com o nome de chave `ADALRedirectUri`, especifique o URI de redirecionamento a ser usado para chamadas da ADAL. Como alternativa, você poderia especificar `ADALRedirectScheme` em vez disso, se o URI de redirecionamento do aplicativo estiver no formato `scheme://bundle_id`.


Além disso, os aplicativos podem substituir essas configurações do Azure AD no tempo de execução. Para fazer isso, basta definir as propriedades `aadAuthorityUriOverride`, `aadClientIdOverride` e `aadRedirectUriOverride` na instância `IntuneMAMPolicyManager`.

> [!NOTE]
> A abordagem do Info.plist é recomendada para todas as configurações estáticas e não precisa ser determinada em tempo de execução. Os valores atribuídos para as propriedades `IntuneMAMPolicyManager` têm precedência sobre valores correspondentes especificados no Info.plist, e serão mantidos até mesmo após a reinicialização do aplicativo. O SDK continuará a usá-los para verificações de política até que o registro do usuário seja cancelado ou os valores sejam limpos ou alterados.

### <a name="if-your-app-does-not-use-adal"></a>Se seu aplicativo não usar a ADAL

Conforme mencionado acima, o SDK de Aplicativos do Intune usa a [Biblioteca de Autenticação do Azure Active Directory](https://github.com/AzureAD/azure-activedirectory-library-for-objc) para seus cenários de inicialização condicional e autenticação. Ele também se baseia na ADAL para registrar a identidade do usuário no serviço de MAM para gerenciamento sem cenários de registro de dispositivo. Se **o aplicativo não usar a ADAL para seu próprio mecanismo de autenticação**, o SDK de Aplicativos do Intune fornecerá os valores padrão para os parâmetros da ADAL e lidará com a autenticação no Azure AD. Você não precisa especificar quaisquer valores para as configurações de ADAL listadas acima. Qualquer mecanismo de autenticação, se existir, usado pelo seu aplicativo será mostrado na parte superior dos prompts da ADAL. 

## <a name="configure-settings-for-the-intune-app-sdk"></a>Definir as configurações para o SDK de Aplicativos do Intune

Você pode usar o dicionário **IntuneMAMSettings** contido no arquivo Info.plist do aplicativo para configurar o SDK de Aplicativos do Intune. Se o dicionário IntuneMAMSettings não for visto no arquivo Info.plist, você deverá criá-lo.

No dicionário IntuneMAMSettings, você pode ter as configurações compatíveis a seguir para configurar o SDK do Aplicativo do Intune.

Algumas dessas configurações podem ter sido abordadas nas seções anteriores e outras não se aplicam a todos os aplicativos.

Setting  | Tipo  | Definição | Necessário?
--       |  --   |   --       |  --
ADALClientId  | Cadeia de caracteres  | O identificador do cliente do Azure AD do aplicativo. | Obrigatório se o aplicativo usar a ADAL. |
ADALAuthority | Cadeia de caracteres | A autoridade do Azure AD do aplicativo em uso. Você deve usar seu próprio ambiente em que as contas do AAD foram configuradas. | Obrigatório se o aplicativo usar a ADAL. Se esse valor estiver ausente, um padrão do Intune será usado.|
ADALRedirectUri  | Cadeia de caracteres  | O URI de redirecionamento do Azure AD do aplicativo. | ADALRedirectUri ou ADALRedirectScheme será obrigatório se o aplicativo usar a ADAL.  |
ADALRedirectScheme  | Cadeia de caracteres  | O esquema de redirecionamento do Azure AD do aplicativo. Isso pode ser usado no lugar de ADALRedirectUri se o URI de redirecionamento do aplicativo estiver no formato `scheme://bundle_id`. | ADALRedirectUri ou ADALRedirectScheme será obrigatório se o aplicativo usar a ADAL. |
ADALLogOverrideDisabled | Booliano  | Especifica se o SDK roteará todos os logs da ADAL (incluindo chamadas da ADAL do aplicativo, se houver) para seu próprio arquivo de log. O padrão é NÃO. Defina como SIM caso o aplicativo vá definir seu próprio retorno de chamada de log da ADAL. | Opcional. |
ADALCacheKeychainGroupOverride | Cadeia de caracteres  | Especifica o grupo de conjunto de chaves a ser usado para o cache da ADAL, em vez de “com.microsoft.adalcache". Observe que ele não tem o prefixo app-id. O prefixo será acrescentado à cadeia de caracteres fornecida em tempo de execução. | Opcional. |
AppGroupIdentifiers | Matriz de cadeia de caracteres  | Matriz de grupos de aplicativo na seção de grupos de com.apple.security.application de direitos do aplicativo. | Necessário se o aplicativo usar grupos de aplicativos. |
ContainingAppBundleId | Cadeia de caracteres | Especifica a ID do pacote do aplicativo que contém a extensão. | Necessário para extensões do iOS. |
DebugSettingsEnabled| Booliano | Se definido como SIM, as políticas de teste do pacote de Configurações podem ser aplicadas. Os aplicativos *não* devem ser fornecidos com essa configuração habilitada. | Opcional. Usa Não como padrão.|
MainNibFile <br> MainNibFile~ipad  | Cadeia de caracteres  | Essa configuração deve conter o nome do arquivo nib principal do aplicativo.  | Obrigatório se o aplicativo definir MainNibFile em Info.plist. |
MainStoryboardFile <br> MainStoryboardFile~ipad  | Cadeia de caracteres  | Essa configuração deve conter o nome do arquivo de storyboard principal do aplicativo. | Necessário se o aplicativo definir UIMainStoryboardFile em Info.plist. |
MAMPolicyRequired| Booliano| Especifica se a inicialização do aplicativo será impedida se ele não tiver uma política de APP do Intune. O padrão é NÃO. <br><br> Observação: os aplicativos não podem ser enviados para a Loja de Aplicativos com a opção MAMPolicyRequired definida como SIM. | Opcional. Usa Não como padrão.|
MAMPolicyWarnAbsent | Booliano| Especifica se o aplicativo alertará o usuário durante a inicialização se ele não tiver a política de APP do Intune. <br><br> Observação: os usuários ainda poderão usar o aplicativo sem política após ignorarem o aviso. | Opcional. Usa Não como padrão. |
MultiIdentity | Booliano| Especifica se o aplicativo reconhece várias identidades. | Opcional. Usa Não como padrão. |
SplashIconFile <br> SplashIconFile~ipad | Cadeia de caracteres  | Especifica o arquivo de ícone de abertura (inicialização) do Intune. | Opcional. |
SplashDuration | Número | Quantidade mínima de tempo, em segundos, pela qual a tela inicial do Intune será exibida na inicialização do aplicativo. O padrão é 1,5. | Opcional. |
BackgroundColor| Cadeia de caracteres| Especifica a cor da tela de fundo para as telas de inicialização e de PIN. Aceita uma cadeia de caracteres hexadecimal RGB no formato #XXXXXX, em que X pode variar de 0 a 9 ou de A a F. O sinal de libra pode ser omitido.   | Opcional. O padrão é cinza claro. |
ForegroundColor| Cadeia de caracteres| Especifica a cor de primeiro plano para as telas de inicialização e de PIN, como a cor do texto. Aceita uma cadeia de caracteres hexadecimal RGB no formato #XXXXXX, em que X pode variar de 0 a 9 ou de A a F. O sinal de libra pode ser omitido.  | Opcional. O padrão é preto. |
AccentColor | Cadeia de caracteres| Especifica a cor de destaque da tela de PIN, como a cor do texto do botão e a cor do realce da caixa. Aceita uma cadeia de caracteres hexadecimal RGB no formato #XXXXXX, em que X pode variar de 0 a 9 ou de A a F. O sinal de libra pode ser omitido.| Opcional. O padrão é azul. |
MAMTelemetryDisabled| Booliano| Especifica se o SDK não enviará dados de telemetria para seu back-end.| Opcional. Usa Não como padrão. |
MAMTelemetryUsePPE | Booliano | Especifica se o SDK do MAM enviará dados para o back-end da telemetria de PPE. Use ao testar seus aplicativos com a política do Intune para que os dados de telemetria de teste não se misture com dados de clientes. | Opcional. Usa Não como padrão. |
MaxFileProtectionLevel | Cadeia de caracteres | Opcional. Permite que o aplicativo especifique o `NSFileProtectionType` máximo ao qual ele pode dar suporte. Esse valor substituirá a política enviada pelo serviço se o nível for maior do que o aplicativo pode dar suporte. Valores possíveis: `NSFileProtectionComplete`, `NSFileProtectionCompleteUnlessOpen`, `NSFileProtectionCompleteUntilFirstUserAuthentication`, `NSFileProtectionNone`.|
OpenInActionExtension | Booliano | Defina como SIM para Abrir em Extensões de ação. Confira a seção Compartilhando dados por meio de UIActivityViewController para obter mais informações. |
WebViewHandledURLSchemes | Matriz de cadeia de caracteres | Especifica os esquemas de URL que o WebView do aplicativo manipula. | Será necessário se o aplicativo usar um WebView que manipula URLs por meio de links e/ou javascript. |

## <a name="receive-app-protection-policy"></a>Receber a política de proteção do aplicativo

### <a name="overview"></a>Visão geral

Para receber a política de proteção de aplicativo do Intune, os aplicativos devem iniciar uma solicitação de registro com o serviço MAM do Intune. Aplicativos podem ser configurados no console do Intune para receber a política de proteção de aplicativo com ou sem o registro de dispositivo. A política de proteção de aplicativo sem registro, também conhecida como **APP-WE** ou MAM-WE, permite que os aplicativos sejam gerenciados pelo Intune sem a necessidade de o dispositivo ser registrado no MDM (gerenciamento de dispositivo móvel) do Intune. Em ambos os casos, o registro com o serviço MAM do Intune é necessário para receber a política.

### <a name="apps-that-use-adal"></a>Aplicativos que usam a ADAL

Os aplicativos que já usam a ADAL devem chamar o método `registerAndEnrollAccount` na instância `IntuneMAMEnrollmentManager` depois que o usuário tiver sido autenticado:

```objc
/*
 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;
```

Ao chamar o método `registerAndEnrollAccount`, o SDK registrará a conta de usuário e tentará registrar o aplicativo em nome dessa conta. Se o registro falhar por algum motivo, o SDK automaticamente tentará realizar o registro novamente após 24 horas. Para fins de depuração, o aplicativo pode receber [notificações](#Status-result-and-debug-notifications), por meio de um delegado, sobre os resultados das solicitações de registro.

Após essa API ser invocada, o aplicativo pode continuar funcionando normalmente. Se o registro for bem-sucedido, o SDK notificará o usuário de que uma reinicialização do aplicativo é necessária. Nesse momento, o usuário poderá reiniciar o aplicativo imediatamente.

```objc
[[IntuneMAMEnrollmentManager instance] registerAndEnrollAccount:@”user@foo.com”];
```

### <a name="apps-that-do-not-use-adal"></a>Aplicativos que não usam a ADAL

Os aplicativos que não realizam a entrada do usuário usando a ADAL ainda podem receber a política de proteção de aplicativo do serviço MAM do Intune chamando a API para fazer com que o SDK processe a autenticação. Os aplicativos devem usar essa técnica quando não autenticarem um usuário com o Azure AD, mas ainda precisarem recuperar a política de proteção de aplicativo para ajudar a proteger dados. Um exemplo é se outro serviço de autenticação estiver sendo usado para entrar no aplicativo ou se o aplicativo não der nenhum suporte para entrar. Para fazer isso, o aplicativo pode chamar o método `loginAndEnrollAccount` na instância `IntuneMAMEnrollmentManager`:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;
```

Ao chamar esse método, se nenhum token existente puder ser encontrado, o SDK solicitará credenciais ao usuário. O SDK, em seguida, tentará registrar o aplicativo com o serviço MAM do Intune em nome da conta de usuário fornecida. O método pode ser chamado com "nil" como a identidade. Nesse caso, o SDK fará o registro com o usuário gerenciado existente no dispositivo (no caso do MDM) ou solicitará que o usuário forneça um nome de usuário, se nenhum usuário existente for encontrado.

Se o registro falhar, o aplicativo deverá considerar chamar essa API novamente no futuro, dependendo dos detalhes da falha. O aplicativo pode receber [notificações](#Status-result-and-debug-notifications), por meio de um delegado, sobre os resultados das solicitações de registro.

Após essa API ser invocada, o aplicativo pode continuar funcionando normalmente. Se o registro for bem-sucedido, o SDK notificará o usuário de que uma reinicialização do aplicativo é necessária.

Exemplo:
```objc
[[IntuneMAMEnrollmentManager instance] loginAndEnrollAccount:@”user@foo.com”];
```

### <a name="let-intune-handle-authentication-and-enrollment-at-launch"></a>Permitir que o Intune manipule a autenticação e o registro na inicialização

Caso deseje que o SDK do Intune manipule toda a autenticação usando a ADAL e o registro antes de o aplicativo concluir a inicialização e se o aplicativo sempre exigir a política de APP, você não precisará usar a API `loginAndEnrollAccount`. Você pode simplesmente definir as duas configurações abaixo como SIM no dicionário IntuneMAMSettings no Info.plist do aplicativo.

Setting  | Tipo  | Definição |
--       |  --   |   --       |  
AutoEnrollOnLaunch| Booliano| Especifica se o aplicativo deverá tentar se registrar automaticamente na inicialização se uma identidade gerenciada existente for detectada e ainda não tiver feito o registro. O padrão é NÃO. <br><br> Observação: se nenhuma identidade gerenciada for encontrada ou nenhum token válido para a identidade estiver disponível no cache da ADAL, a tentativa de registro falhará silenciosamente sem solicitar credenciais, a menos que o aplicativo também tenha definido MAMPolicyRequired como SIM. |
MAMPolicyRequired| Booliano| Especifica se a inicialização do aplicativo será impedida se ele não tiver uma política de proteção de aplicativo do Intune. O padrão é NÃO. <br><br> Observação: os aplicativos não podem ser enviados para a Loja de Aplicativos com a opção MAMPolicyRequired definida como SIM. Ao configurar o MAMPolicyRequired como SIM, o AutoEnrollOnLaunch também deverá ser definido como SIM. |

Se você escolher essa opção para seu aplicativo, não precisará manipular a reinicialização do aplicativo após o registro.

### <a name="deregister-user-accounts"></a>Cancelar o registro de contas de usuário

Antes que um usuário seja desconectado de um aplicativo, o aplicativo deve cancelar o registro do usuário do SDK. Isso garantirá que:

1. Novas tentativas de registro para a conta do usuário não ocorrerão mais.

2. A política de proteção do aplicativo será removida.

3. Se o aplicativo iniciar um apagamento seletivo (opcional), todos os dados corporativos serão excluídos.

Antes que o usuário seja desconectado, o aplicativo deverá chamar o seguinte método na instância `IntuneMAMEnrollmentManager`:

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune APP AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */
(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

Esse método deverá ser chamado antes que os tokens do Azure AD da conta do usuário sejam excluídos. O SDK precisa dos tokens do AAD da conta do usuário para realizar solicitações específicas para o serviço MAM do Intune em nome do usuário.

Se o aplicativo for excluir dados corporativos do usuário por conta própria, o sinalizador `doWipe` poderá ser definido como falso. Caso contrário, o aplicativo poderá fazer o SDK iniciar um apagamento seletivo. Isso resultará em uma chamada ao delegado de apagamento seletivo do aplicativo.

Exemplo:
```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

## <a name="status-result-and-debug-notifications"></a>Notificações de status, resultados e depuração

O aplicativo pode receber notificações de status, resultados e depuração sobre as seguintes solicitações ao serviço de MAM do Intune:

* Solicitações de registro
* Solicitações de atualização de política
* Solicitações de cancelamento de registro

As notificações são apresentadas por meio de métodos delegados em `IntuneMAMEnrollmentDelegate.h`:

```objc
/**
 *  Called when an enrollment request operation is completed.
 * @param status status object containing debug information
 */

(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information
 */
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a un-enroll request operation is completed.
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK
 *  @param status status object containing debug information
 */

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;
```

Esses métodos delegados retornam um objeto `IntuneMAMEnrollmentStatus` que contém as seguintes informações:

* A identidade da conta associada à solicitação
* Um código de status que indica o resultado da solicitação
* Uma cadeia de caracteres de erro com uma descrição do código de status
* Um objeto `NSError`. Esse objeto é definido em `IntuneMAMEnrollmentStatus.h`, juntamente com os códigos de status específicos que podem ser retornados.

> [!NOTE]
> Essas informações são apenas para fins de depuração. Nenhuma lógica de negócios no aplicativo deve se basear nessas notificações. Essas informações podem ser enviadas para um serviço de telemetria para fins de depuração ou de monitoramento.

### <a name="sample-code"></a>Código de exemplo

Estes são exemplos de implementações dos métodos delegados:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}
```

## <a name="application-restart"></a>Reinicialização do aplicativo

Quando um aplicativo receber políticas de MAM pela primeira vez, ele precisará ser reiniciado para aplicar os ganchos necessários. Para notificar o aplicativo de que uma reinicialização precisa ocorrer, o SDK fornece um método delegado em `IntuneMAMPolicyDelegate.h`.

```objc
 - (BOOL) restartApplication
```

O valor retornado desse método informa o SDK se o aplicativo deve realizar a reinicialização necessária:

* Se true for retornado, o aplicativo deverá realizar a reinicialização.

* Se false for retornado, o SDK reiniciará o aplicativo depois que o método retornar. O SDK mostrará imediatamente uma caixa de diálogo informando ao usuário para reiniciar o aplicativo.

## <a name="customize-your-apps-behavior-with-apis"></a>Personalizar o comportamento do aplicativo com APIs

O SDK do Aplicativo do Intune tem várias APIs que você pode chamar para obter informações sobre a política de APP do Intune implantada no aplicativo. Você pode usar esses dados para personalizar o comportamento do seu aplicativo. A tabela abaixo fornece informações sobre algumas classes essenciais do Intune que serão usadas.

Classe | Descrição
----- | -----------
IntuneMAMPolicyManager.h | A classe IntuneMAMPolicyManager expõe a política de APP do Intune implantada no aplicativo. Em especial, ela expõe APIs que são úteis para [Habilitar várias identidades](#-enable-multi-identity-optional). |
IntuneMAMPolicy.h | A classe IntuneMAMPolicy expõe algumas configurações de política de MAM que se aplicam ao aplicativo. Essas configurações de política são expostas para que o aplicativo possa personalizar sua interface do usuário. A maioria das configurações de política é imposta pelo SDK e não pelo aplicativo. A única configuração que o aplicativo deve implementar é o controle Salvar como. Essa classe expõe algumas APIs necessárias para implementar Salvar como. |
IntuneMAMFileProtectionManager.h | A classe IntuneMAMFileProtectionManager expõe as APIs que o aplicativo pode usar para proteger os arquivos e os diretórios explicitamente com base em uma identidade fornecida. A identidade pode ser gerenciada pelo Intune ou não gerenciada, e o SDK aplicará a política de MAM apropriada. O uso dessa classe é opcional. |
IntuneMAMDataProtectionManager.h | A classe IntuneMAMDataProtectionManager expõe as APIs que o aplicativo pode usar para proteger os buffers de dados considerando uma identidade fornecida. A identidade pode ser gerenciada pelo Intune ou não gerenciada, e o SDK aplicará a criptografia adequadamente. |

## <a name="implement-save-as-controls"></a>Implementar controles salvar como

O Intune permite que os administradores de TI selecionem em quais locais de armazenamento um aplicativo gerenciado pode salvar dados. Os aplicativos podem consultar o SDK do Aplicativo do Intune quanto aos locais de armazenamento permitidos usando a API `isSaveToAllowedForLocation`, definida em `IntuneMAMPolicy.h`.

Antes que os aplicativos possam salvar os dados gerenciados em um armazenamento em nuvem ou localmente, eles precisam consultar a API `isSaveToAllowedForLocation` para saber se o administrador de TI permitiu que os dados fossem salvos nesse local.

Quando os aplicativos usarem a API `isSaveToAllowedForLocation`, precisarão passar o UPN para o local de armazenamento se ele estiver disponível.

### <a name="supported-save-locations"></a>Locais de salvamento com suporte

A API `isSaveToAllowedForLocation` fornece constantes para verificar se o administrador de TI permite que os dados sejam salvos nos seguintes locais definidos em `IntuneMAMPolicy.h`:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Os aplicativos devem usar as constantes em `isSaveToAllowedForLocation` para verificar se os dados podem ser salvos em locais considerados "gerenciados", como o OneDrive for Business, ou "pessoais". Além disso, a API deve ser usada quando o aplicativo não pode verificar se um local é "gerenciado" ou "pessoal".

Locais conhecidos como "pessoais" são representadas pela constante `IntuneMAMSaveLocationOther`.

A constante `IntuneMAMSaveLocationLocalDrive` deve ser usada quando o aplicativo está salvando dados em qualquer local no dispositivo local.

## <a name="share-data-via-uiactivityviewcontroller"></a>Compartilhar dados por meio de UIActivityViewController

Começando na versão 8.0.2, o SDK do Aplicativo do Intune pode filtrar as ações `UIActivityViewController` para que apenas os locais de compartilhamento gerenciados pelo Intune estejam disponíveis para seleção. Esse comportamento será controlado pela política de transferência de dados do aplicativo.

### <a name="copy-to-actions"></a>Ações de "Copiar para"

Ao compartilhar documentos por meio de `UIActivityViewController` e `UIDocumentInteractionController`, o iOS exibe ações ‘Copiar para’ para cada aplicativo que dá suporte à abertura do documento que está sendo compartilhado. Os aplicativos declaram os tipos de documento aos quais eles dão suporte por meio da configuração de `CFBundleDocumentTypes` no Info.plist deles. Esse tipo de compartilhamento não estará mais disponível se a política proibir o compartilhamento com aplicativos não gerenciados. Como substituição, o usuário precisará adicionar uma extensão de ação que não seja da interface do usuário ao aplicativo deles e vinculá-la ao SDK do Aplicativo do Intune. A extensão de Ação é meramente um stub. O SDK implementará o comportamento de compartilhamento de arquivos. Siga as etapas abaixo:

1. O aplicativo precisa ter, pelo menos, uma schemeURL definida no `CFBundleURLTypes` do Info.plist.

2. O aplicativo e a extensão de ação precisam compartilhar, pelo menos, um Grupo de Aplicativos e o Grupo de Aplicativos precisa estar listado na matriz `AppGroupIdentifiers` nos dicionários IntuneMAMSettings do aplicativo e da extensão.

3. Nomeie a extensão de ação de "Abrir em" seguida pelo nome do aplicativo. Localize o Info.plist conforme necessário.

4. Forneça um ícone de modelo para a extensão, conforme descrito pela [documentação do desenvolvedor da Apple](https://developer.apple.com/ios/human-interface-guidelines/extensions/sharing-and-actions/). Como alternativa, a ferramenta IntuneMAMConfigurator pode ser usada para gerar essas imagens a partir do diretório .app do aplicativo. Para fazer isso, execute:

    ```bash
    IntuneMAMConfigurator -generateOpenInIcons /path/to/app.app -o /path/to/output/directory
    ```

5. Em IntuneMAMSettings no Info.plist da extensão, adicione uma configuração booliana chamada `OpenInActionExtension` com o valor SIM.

6. Configure a `NSExtensionActivationRule` para dar suporte a um único arquivo e a todos os tipos de `CFBundleDocumentTypes` do aplicativo prefixados com `com.microsoft.intune.mam`. Por exemplo, se o aplicativo der suporte a public.text e public.image, a regra de ativação seria:

    ```
    SUBQUERY (
        extensionItems,
        $extensionItem,
        SUBQUERY (
            $extensionItem.attachments,
            $attachment,
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.text” ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.image”).@count == 1
    ).@count == 1
    ```

### <a name="update-existing-share-and-action-extensions"></a>Atualizar extensões de Compartilhamento e Ação existentes

Caso o aplicativo já contenha extensões de Ação ou de Compartilhamento, a `NSExtensionActivationRule` precisará ser modificada para permitir os tipos do Intune. Para cada tipo compatível com a extensão, adicione outro tipo prefixado com `com.microsoft.intune.mam`. Por exemplo, se a regra de ativação existente for:  

    ```
    SUBQUERY (
        extensionItems,
        $extensionItem,
        SUBQUERY (
            $extensionItem.attachments,
            $attachment,
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.url" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.plain-text" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.image" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.data"
        ).@count > 0
    ).@count > 0
    ```

Ela deve ser alterada para:

    ```
    SUBQUERY (
        extensionItems,
        $extensionItem,
        SUBQUERY (
            $extensionItem.attachments,
            $attachment,
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.url" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.plain-text" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.image" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.data" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.url" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.plain-text" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.image" ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.data
        ).@count > 0
    ).@count > 0
    ```

> [!NOTE]
> A ferramenta IntuneMAMConfigurator pode ser usada para adicionar os tipos de Intune à regra de ativação. Se a regra de ativação existente usar as constantes de cadeia de caracteres predefinidas (por exemplo, NSExtensionActivationSupportsFileWithMaxCount, NSExtensionActivationSupportsText etc.), a sintaxe de predicado poderá ficar muito complexa. A ferramenta IntuneMAMConfigurator também pode ser usada para converter a regra de ativação das constantes de cadeia de caracteres em uma cadeia de caracteres de predicado enquanto se adicionam os tipos do Intune.

### <a name="what-the-ui-should-look-like"></a>Qual deve ser a aparência da interface do usuário

Interface do usuário antiga:

![Interface do usuário de compartilhamento antiga](./media/sharing-UI-old.png)

Nova interface do usuário:

![Nova interface do usuário de compartilhamento](./media/sharing-UI-new.png)

## <a name="enable-targeted-configuration-appmam-app-config-for-your-ios-applications"></a>Habilitar a configuração direcionada (configuração de aplicativo de APP/MAM) para aplicativos iOS

A configuração direcionada para MAM (também conhecida como configuração de aplicativo MAM) permite que um aplicativo receba dados de configuração por meio do SDK do Intune. O formato e as variantes desses dados precisam ser definidos e comunicados aos clientes do Intune pelo proprietário/desenvolvedor do aplicativo.

Os administradores do Intune podem direcionar e implantar dados de configuração por meio do portal do Azure no Intune e da API do Graph no Intune. A partir da versão 7.0.1 do SDK do Intune App para iOS, os aplicativos que participam da configuração voltada para MAM podem receber dados de configuração de MAM direcionada por meio do serviço de MAM. Os dados de configuração de aplicativo são enviados por push por meio de nosso Serviço MAM diretamente para o aplicativo em vez de pelo canal MDM. O SDK do aplicativo do Intune fornece uma classe para acessar os dados recuperados desses consoles. Os seguintes itens são pré-requisitos:

* O aplicativo precisa ser registrado no serviço MAM do Intune para poder acessar a interface do usuário de configuração voltada para MAM. Para obter mais informações, confira [Receber a política de proteção de aplicativo](#receive-app-protection-policy).

* Inclua `IntuneMAMAppConfigManager.h` no arquivo de origem do aplicativo.

* Chame `[[IntuneMAMAppConfigManager instance] appConfigForIdentity:]` para obter o objeto de configuração do aplicativo.

* Chame o seletor apropriado no objeto `IntuneMAMAppConfig`. Por exemplo, se a chave do seu aplicativo é uma cadeia de caracteres, use `stringValueForKey` ou `allStringsForKey`. Confira `IntuneMAMAppConfig.h` para obter uma descrição detalhada sobre valores retornados e condições de erro.

Para obter mais informações sobre os recursos da API do Graph, consulte a [Referência de API do Graph](https://developer.microsoft.com/graph/docs/concepts/overview).

Para obter mais informações sobre como criar uma política de configuração de aplicativo voltada para MAM no iOS, consulte a seção sobre configuração de aplicativo voltada para MAM em [Como usar políticas de configuração de aplicativo do Microsoft Intune para iOS](https://docs.microsoft.com/intune/app-configuration-policies-use-ios).

## <a name="telemetry"></a>Telemetria

Por padrão, o SDK do Aplicativo do Intune para iOS coleta telemetria dos seguintes tipos de eventos:

* **Inicialização do aplicativo**: para ajudar o Microsoft Intune a obter informações sobre o uso de aplicativos habilitados para MAM por tipo de gerenciamento (MAM com MDM, MAM sem registro de MDM etc.).

* **Chamadas de registro**: para ajudar o Microsoft Intune a obter informações sobre a taxa de sucesso e outras métricas de desempenho de chamadas de registro iniciadas do lado do cliente.

* **Ações do Intune**: para ajudar a diagnosticar problemas e garantir a funcionalidade do Intune, coletamos informações sobre as ações do SDK do Intune.

> [!NOTE]
> Se optar por não enviar dados de telemetria do SDK de Aplicativos do Intune para o Microsoft Intune do seu aplicativo móvel, você deverá desabilitar a captura de telemetria pelo SDK de Aplicativos do Intune. Defina a propriedade `MAMTelemetryDisabled` como SIM no dicionário IntuneMAMSettings.

## <a name="enable-multi-identity-optional"></a>Habilitar várias identidades (opcional)

Por padrão, o SDK aplica uma política ao aplicativo como um todo. Várias identidades é um recurso do MAM que você pode habilitar para aplicar uma política em um nível por identidade. Ele requer mais participação do aplicativo do que outros recursos de MAM.

O aplicativo precisa informar ao SDK de aplicativo quando pretende alterar a identidade ativa. O SDK também notifica o aplicativo quando uma alteração de identidade é necessária. Atualmente, há suporte para apenas uma identidade gerenciada. Depois que o usuário registra o dispositivo ou o aplicativo, o SDK usa essa identidade e a considera a identidade gerenciada primária. Outros usuários no aplicativo serão tratados como não gerenciados com configurações de política irrestritas.

Observe que uma identidade é definida simplesmente como uma cadeia de caracteres. As identidades não diferenciam maiúsculas de minúsculas. As solicitações de identidade ao SDK podem não retornar o mesmo esquema de maiúsculas e minúsculas usado originalmente ao definir a identidade.

### <a name="identity-overview"></a>Visão geral de identidade

Uma identidade é simplesmente o nome de usuário de uma conta (por exemplo, user@contoso.com). Os desenvolvedores podem definir a identidade do aplicativo nos níveis a seguir:

* **Identidade de processo**: define a identidade de todo o processo e é usada principalmente para aplicativos de identidade única. Essa identidade afeta todas as tarefas, arquivos e a interface do usuário.

* **Identidade de interface do usuário**: determina quais políticas são aplicadas às tarefas de interface do usuário no thread principal, como recortar/copiar/colar, PIN, autenticação e compartilhamento de dados. A identidade de interface do usuário não afeta as tarefas de arquivo como criptografia e backup.

* **Identidade de thread**: afeta quais políticas são aplicadas no thread atual. Essa identidade afeta todas as tarefas, arquivos e a interface do usuário.

É responsabilidade do aplicativo configurar as identidades adequadamente, quer o usuário seja gerenciado ou não.

A qualquer momento, todo thread tem uma identidade efetiva para tarefas de interface do usuário e tarefas de arquivo. Essa é a identidade usada para verificar quais políticas, se houver, devem ser aplicadas. Se a identidade for "nenhuma identidade" ou o usuário não for gerenciado, nenhuma política será aplicada. Os diagramas a seguir mostram como as identidades efetivas são determinadas.

  ![SDK de Aplicativos do Intune para iOS: estruturas e bibliotecas vinculadas](./media/ios-thread-identities.png)

### <a name="thread-queues"></a>Filas de thread

Frequentemente, os aplicativos expedem tarefas síncronas e assíncronas para filas de thread. O SDK intercepta chamadas de GCD (Grand Central Dispatch) e associa a identidade do thread atual às tarefas expedidas. Quando as tarefas são concluídas, o SDK altera temporariamente a identidade do thread para a identidade associada às tarefas, conclui as tarefas e restaura a identidade do thread original.


Como `NSOperationQueue` é criado sobre o GCD, `NSOperations` será executado na identidade do thread no momento em que as tarefas forem adicionadas ao `NSOperationQueue`. O `NSOperations` ou funções expedidas diretamente usando o GCD também têm a capacidade de alterar a identidade do thread atual conforme são executadas. Essa identidade substituirá a identidade herdada do thread de expedição.

### <a name="file-owner"></a>Proprietário do arquivo

O SDK acompanha as identidades dos proprietários do arquivo local e aplica políticas de acordo com elas. Um proprietário do arquivo é estabelecido quando o arquivo é criado ou quando é aberto no modo de truncamento. O proprietário é definido como a identidade de tarefa do arquivo efetivo do thread que executa a operação.

Como alternativa, os aplicativos podem definir a identidade do proprietário do arquivo explicitamente usando `IntuneMAMFilePolicyManager`. Os aplicativos podem usar o `IntuneMAMFilePolicyManager` para recuperar o proprietário do arquivo e definir a identidade da interface do usuário antes de mostrar o conteúdo do arquivo.

### <a name="shared-data"></a>Dados compartilhados

Se o aplicativo criar arquivos que contêm dados de usuários gerenciados e não gerenciados, será responsabilidade do aplicativo criptografar os dados do usuário gerenciado. Você pode criptografar dados usando as APIs `protect` e `unprotect` em `IntuneMAMDataProtectionManager`.

O método `protect` aceita uma identidade que pode ser um usuário gerenciado ou não gerenciado. Se o usuário for gerenciado, os dados serão criptografados. Se o usuário não for gerenciado, um cabeçalho será adicionado aos dados codificando a identidade, mas os dados não serão criptografados. O método `protectionInfo` pode ser usado para recuperar o proprietário dos dados.

### <a name="share-extensions"></a>Extensões de compartilhamento

Se o aplicativo contiver uma extensão de compartilhamento, o proprietário do item sendo compartilhado poderá ser recuperado usando o método `protectionInfoForItemProvider` em `IntuneMAMDataProtectionManager`. Se o item compartilhado for um arquivo, o SDK processará a configuração do proprietário do arquivo. Se o item compartilhado forem dados, o aplicativo será responsável por configurar o proprietário do arquivo se esses dados forem persistidos em um arquivo, será responsável também por chamar a API `setUIPolicyIdentity` antes de mostrar esses dados na interface do usuário.

### <a name="turn-on-multi-identity"></a>Ativar várias identidades

Por padrão, considera-se que todos os aplicativos são aplicativos de identidade única. O SDK define a identidade do processo para o usuário registrado. Para habilitar o suporte a várias identidades, uma configuração booliana com o nome `MultiIdentity` e o valor SIM deve ser adicionada ao dicionário IntuneMAMSettings no arquivo Info.plist do aplicativo.

> [!NOTE]
> Quando o recurso de várias identidades estiver habilitado, a identidade do processo, a identidade da interface do usuário e as identidades de thread serão definidas como nil. O aplicativo é responsável por configurá-las adequadamente.

### <a name="switch-identities"></a>Alternar identidades

* **Alternância de identidade iniciada pelo aplicativo**:

    Na inicialização, é considerado que aplicativos com várias identidades estejam sendo executados sob uma conta desconhecida e não gerenciada. A interface do usuário de inicialização condicional não será executada e nenhuma política será imposta ao aplicativo. É responsabilidade do aplicativo notificar o SDK sempre que a identidade precisar ser alterada. Normalmente, isso ocorrerá sempre que o aplicativo estiver prestes a mostrar dados de uma conta de usuário específica.

    Um exemplo é quando o usuário tenta abrir um documento, uma caixa de correio ou uma guia em um bloco de anotações. O aplicativo precisa notificar o SDK antes que arquivo, caixa de correio ou guia seja, de fato, aberta. Isso é feito através da API `setUIPolicyIdentity` em `IntuneMAMPolicyManager`. Essa API deve ser chamada quer o usuário seja gerenciado ou não. Se o usuário for gerenciado, o SDK executará as verificações de inicialização condicional, como detecção de jailbreak, PIN, autenticação etc.

    O resultado da alternância de identidade é retornado ao aplicativo de forma assíncrona por meio de um manipulador de conclusão. O aplicativo deve adiar a abertura do documento, da caixa de correio ou da guia até que um código de resultado de êxito seja retornado. Se a alternância de identidade falhar, o aplicativo deverá cancelar a tarefa.

* **Alternância de identidade iniciada pelo SDK**:

    Há casos em que o SDK precisa solicitar que o aplicativo alterne para uma identidade específica. Os aplicativos com várias identidades devem implementar o método `identitySwitchRequired` em `IntuneMAMPolicyDelegate` para processar essa solicitação.

    Quando esse método for chamado, se o aplicativo for capaz de processar a solicitação de mudar para a identidade especificada, ele deverá passar `IntuneMAMAddIdentityResultSuccess` no manipulador de conclusão. Se não for capaz de processar a mudança de identidade, o aplicativo deverá passar `IntuneMAMAddIdentityResultFailed` para o manipulador de conclusão.

    O aplicativo não precisa chamar `setUIPolicyIdentity` em resposta a essa chamada. Se o SDK precisar que o aplicativo mude para uma conta de usuário não gerenciada, a cadeia de caracteres vazia será passada para a chamada `identitySwitchRequired`.

* **Apagamento seletivo**:

    Quando o aplicativo for apagado seletivamente, o SDK chamará o método `wipeDataForAccount` em `IntuneMAMPolicyDelegate`. É responsabilidade do aplicativo remover a conta de usuário especificada e todos os dados associados a ela. O SDK é capaz de remover todos os arquivos pertencentes ao usuário e fará isso se o aplicativo retornar FALSE da chamada `wipeDataForAccount`.

    Observe que este método é chamado de um thread em segundo plano. O aplicativo não deve retornar um valor até que todos os dados do usuário tenham sido removidos (com exceção dos arquivos, se o aplicativo retornar FALSE).

## <a name="ios-best-practices"></a>Práticas recomendadas do iOS

A seguir estão algumas práticas recomendadas para o desenvolvimento para iOS:

* O sistema de arquivos iOS diferencia maiúsculas de minúsculas. Certifique-se de que as maiúsculas e minúsculas estejam corretas para nomes de arquivo como `libIntuneMAM.a` e `IntuneMAMResources.bundle`.

* Se o Xcode tiver problemas para encontrar `libIntuneMAM.a`, você poderá corrigir o problema adicionando o caminho para essa biblioteca aos caminhos de pesquisa do vinculador.

## <a name="faqs"></a>Perguntas frequentes

### <a name="are-all-of-the-apis-addressable-through-native-swift-or-the-objective-c-and-swift-interoperability"></a>Todas as APIs são endereçáveis pelo Swift nativo ou pela interoperabilidade Objective-C e Swift?

As APIs do SDK de Aplicativos do Intune estão apenas em Objective-C e não dão suporte ao Swift **nativo**. A interoperabilidade de Swift com Objective-C é necessária.

### <a name="do-all-users-of-my-application-need-to-be-registered-with-the-app-we-service"></a>Todos os usuários do meu aplicativo precisam estar registrados no serviço APP-WE?

Não. Na verdade, somente contas corporativas ou de estudante devem ser registradas com o SDK de Aplicativos do Intune. Os aplicativos são responsáveis por determinar se uma conta é usada em um contexto de trabalho ou escolar.

### <a name="what-about-users-that-have-already-signed-in-to-the-application-do-they-need-to-be-enrolled"></a>E quanto aos usuários que já entraram no aplicativo? Eles precisam ser registrados?

O aplicativo é responsável pelo registro de usuários depois que eles tiverem sido autenticados com êxito. O aplicativo também é responsável pelo registro de todas as contas existentes que podem ter estado presentes antes de o aplicativo ter a funcionalidade de MAM sem MDM.

Para fazer isso, o aplicativo deve fazer uso do método `registeredAccounts:`. Esse método retorna um dicionário NSDictionary que contém todas as contas registradas no serviço de MAM do Intune. Se qualquer conta existente no aplicativo não estiver na lista, o aplicativo deverá registrar essas contas via `registerAndEnrollAccount:`.

### <a name="how-often-does-the-sdk-retry-enrollments"></a>Com que frequência o SDK repete tentativas de registro?

O SDK tentará, automaticamente, realizar todos os registros com falha em um intervalo de 24 horas. O SDK faz isso para garantir que, se a organização de um usuário tiver habilitado o MAM após o usuário ter se conectado ao aplicativo, o usuário seja registrado e receba políticas com êxito.

O SDK deixará de repetir as tentativas quando detectar que um usuário registrou o aplicativo com êxito. Isso acontece porque apenas um usuário pode registrar um aplicativo em um dado momento. Se o registro do usuário for cancelado, as tentativas começarão novamente no mesmo intervalo de 24 horas.

### <a name="why-does-the-user-need-to-be-deregistered"></a>Por que o registro do usuário precisa ser cancelado?

O SDK executará essas ações em segundo plano periodicamente:

* Se o aplicativo ainda não estiver registrado, ele tentará registrar todas as contas registradas a cada 24 horas.
* Se o aplicativo estiver registrado, o SDK verificará se há atualizações de política de MAM a cada 8 horas.

Ao cancelar o registro de um usuário, ele notifica o SDK que o usuário não usará mais o aplicativo e que o SDK pode interromper qualquer um dos eventos periódicos para essa conta de usuário. Ele também dispara o cancelamento do registro do aplicativo e um apagamento seletivo, se necessário.

### <a name="should-i-set-the-dowipe-flag-to-true-in-the-deregister-method"></a>EU devo definir o sinalizador doWipe como true no método de cancelamento de registro?

Esse método deve ser chamado antes que usuário seja desconectado do aplicativo.  Se, como parte da desconexão, os dados do usuário forem excluídos do aplicativo, `doWipe` poderá ser definido como false. No entanto, se o aplicativo não remover os dados do usuário, `doWipe` deverá ser definido como true para que o SDK possa excluir os dados.

### <a name="are-there-any-other-ways-that-an-application-can-be-un-enrolled"></a>Há outras formas de cancelar o registro de um aplicativo?

Sim, o administrador de TI pode enviar um comando de apagamento seletivo para o aplicativo. Isso cancelará o registro do usuário e apagará seus dados. O SDK processa automaticamente esse cenário e envia uma notificação por meio do método de delegação de cancelamento de registro.

### <a name="is-there-a-sample-app-that-demonstrates-how-to-integrate-the-sdk"></a>Há um aplicativo de exemplo que demonstra como integrar o SDK?

Sim. Recentemente, reformulamos nosso aplicativo de exemplo de software livre [Wagr para iOS](https://github.com/Microsoft/Wagr-Sample-Intune-iOS-App). O Wagr agora está habilitado para a política de proteção do aplicativo usando o SDK do Aplicativo do Intune.

## <a name="submit-your-app-to-the-app-store"></a>Enviar seu aplicativo à App Store

Os builds da biblioteca estática e da estrutura do SDK de Aplicativos do Intune são binários universais. Isso significa que eles têm código para todas as arquiteturas de dispositivo e de simulador. A Apple rejeitará aplicativos enviados à App Store se eles contiverem código de simulador. Ao compilar com a biblioteca estática para builds somente de dispositivo, o vinculador removerá automaticamente o código de simulador. Siga as etapas abaixo para garantir que todos os códigos de simulador sejam removidos antes de carregar o aplicativo na App Store.

1. Confirme se `IntuneMAM.framework` está em sua área de trabalho.

2. Execute estes comandos:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    O primeiro comando remove as arquiteturas de simulador do arquivo DYLIB da estrutura. O segundo comando copia o arquivo DYLIB somente para dispositivos de volta para o diretório da estrutura.
