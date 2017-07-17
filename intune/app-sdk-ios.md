---
title: SDK de Aplicativo do Microsoft Intune para o Guia do Desenvolvedor do iOS
description: "O SDK de Aplicativo do Microsoft Intune para iOS permite incorporar políticas de proteção de aplicativo do Intune – na forma de MAM (gerenciamento de aplicativo móvel) – em seu aplicativo iOS."
keywords: 
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0fb1d52a97a03609ddefb94caf707bd8cbee8f12
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# SDK de Aplicativo do Microsoft Intune para o Guia do Desenvolvedor do iOS
<a id="microsoft-intune-app-sdk-for-ios-developer-guide" class="xliff"></a>

> [!NOTE]
> Primeiro, leia o artigo [Guia de Introdução ao SDK de Aplicativo do Intune](app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.

O SDK do Aplicativo do Microsoft Intune para iOS permite incorporar políticas de proteção do aplicativo do Intune (também conhecidas como políticas **APP** ou **MAM**) em seu aplicativo iOS nativo. Um aplicativo habilitado para MAM é aquele que está integrado ao SDK do Aplicativo do Intune. Os administradores de TI podem implantar políticas de proteção do aplicativo em seu aplicativo móvel quando o Intune gerencia o aplicativo de forma ativa.

## Pré-requisitos
<a id="prerequisites" class="xliff"></a>

* Você precisará de um computador Mac OS que executa o OS X 10.8.5 ou posterior e tenha o Xcode 8 ou posterior instalado.

* Seu aplicativo deve ser direcionado para iOS 9 ou superior.

* Examinar os [Termos de Licença do SDK de Aplicativo do Intune para iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Imprimir e guardar uma cópia dos termos de licença para seus registros. Ao baixar e usar o SDK de Aplicativo do Intune para iOS, você concorda com esses termos de licença.  Se você não aceitá-los, não use o software.

* Baixe os arquivos para o SDK do Aplicativo do Intune para iOS no [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).

## Novidades no SDK
<a id="whats-in-the-sdk" class="xliff"></a>

O SDK de Aplicativo do Intune para iOS inclui uma biblioteca estática, arquivos de recursos, cabeçalhos de API, um arquivo .plist de configurações de depuração e uma ferramenta do configurador. Aplicativos móveis podem simplesmente incluir os arquivos de recursos e um link estático para as bibliotecas para a maioria das imposições de política. Recursos de MAM avançados do Intune são aplicados por meio de APIs.

Este guia aborda o uso dos seguintes componentes do SDK do Aplicativo do Intune para iOS:

* **libIntuneMAM.a**: a biblioteca estática do SDK do Aplicativo do Intune. Se o aplicativo não usar extensões, vincule essa biblioteca ao seu projeto para habilitar a aplicativo para o gerenciamento de aplicativo móvel do Intune.

* **IntuneMAM.framework**: a estrutura do SDK do Aplicativo do Intune. Vincule essa estrutura ao seu projeto para habilitar a aplicativo para o gerenciamento de aplicativo móvel do Intune. Use a estrutura em vez da biblioteca estática se seu aplicativo usar extensões, para que o projeto não crie várias cópias da biblioteca estática.

* **IntuneMAMResources.bundle**: um pacote de recursos que contém recursos dos quais o SDK depende.

* **Cabeçalhos**: expõe as APIs do SDK do Intune App. Se você usar uma API, precisará incluir o arquivo de cabeçalho que contém a API. Os seguintes arquivos de cabeçalho incluem as chamadas de função de API necessárias para habilitar a funcionalidade do SDK do Aplicativo do Intune:

    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h


## Como o SDK de Aplicativos do Intune funciona
<a id="how-the-intune-app-sdk-works" class="xliff"></a>

O objetivo do SDK do Intune APP para iOS é adicionar recursos de gerenciamento de aplicativos a aplicativos iOS com alterações mínimas de código. Quanto menos alterações houver no código, menor será o tempo de chegada no mercado sem afetar a consistência e a estabilidade do aplicativo móvel.


## Compilar o SDK em seu aplicativo móvel
<a id="build-the-sdk-into-your-mobile-app" class="xliff"></a>

Para habilitar o SDK de Aplicativo do Intune, siga estas etapas:

1. **Opção 1 (recomendado)**: vincule `IntuneMAM.framework` ao seu projeto. Arraste `IntuneMAM.framework` para a lista **Binários inseridos** do destino do projeto.

    > [!NOTE]
    > Se você usar a estrutura, precisará remover manualmente as arquiteturas de simulador da estrutura universal antes de enviar seu aplicativo à App Store. Confira [Enviar seu aplicativo à App Store](#Submit-your-app-to-the-App-Store) para obter mais detalhes.

2. **Opção 2**: Link para a biblioteca `libIntuneMAM.a`. Arraste e solte a biblioteca `libIntuneMAM.a` na lista **Estruturas e Bibliotecas Vinculadas** do projeto de destino.

    ![SDK do Aplicativo do Intune para iOS: estruturas e bibliotecas vinculadas](./media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    > [!NOTE]
    > Se você planeja lançar o aplicativo na App Store, use a versão de `libIntuneMAM.a` criada para a versão de lançamento e não para a versão de depuração. A versão de lançamento estará na pasta **lançamento**. A versão de depuração tem saída detalhada, o que ajuda a solucionar problemas com o SDK do Aplicativo do Intune.

    Adicione `-force_load {PATH_TO_LIB}/libIntuneMAM.a` a um dos seguintes, substituindo `{PATH_TO_LIB}` pelo local do SDK do Intune App:
      * A definição de configuração de build `OTHER_LDFLAGS` do projeto
      * Os **Outros Sinalizadores do Vinculador** da interface do usuário

        > [!NOTE]
        > Para encontrar `PATH_TO_LIB`, selecione o arquivo `libIntuneMAM.a` e escolha **Obter Informações** no menu **Arquivo**. Copie e cole as informações **Onde** (o caminho) da seção **Geral** da janela **Informações**.

3. Adicione as seguintes estruturas de iOS ao projeto:
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.tbd
    * libc++.tbd
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework


4. Adicione o pacote de recursos `IntuneMAMResources.bundle` ao projeto arrastando-o para **Copiar Recursos do Pacote** em **Fases de Build**.

    ![SDK de Aplicativo do Intune para iOS: copiar recursos do pacote](./media/intune-app-sdk-ios-copy-bundle-resources.png)

5. Se seu aplicativo móvel definir um Nib ou Storyboard principal em seu Info.plist, recorte os campos do arquivo **Storyboard Principal** ou **Nib Principal**. Em Info.plist, cole esses campos e seus valores correspondentes em um novo dicionário chamado **IntuneMAMSettings** com os seguintes nomes de chave, conforme aplicável:
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad
    > [!NOTE]
  > Se seu aplicativo móvel não definir um arquivo nib ou storyboard em seu arquivo Info.plist, essas configurações não serão obrigatórias.

    Você pode exibir o Info.plist em formato bruto (para ver os nomes de chave) clicando com o botão direito do mouse em qualquer lugar do corpo do documento e alterando o tipo de exibição para **Mostrar Chaves/Valores Brutos**.

6. Habilite o compartilhamento de conjunto de chaves (se já não estiver habilitado) escolhendo em **Funcionalidades** em cada destino do projeto e habilitando a opção **Compartilhamento de Conjunto de Chaves**. O compartilhamento de conjunto de chaves é necessário para que você prossiga para a próxima etapa.

  > [!NOTE]
    > O perfil de provisionamento precisa dar suporte aos novos valores de compartilhamento de conjunto de chaves. Os grupos de acesso do conjunto de chaves devem dar suporte a um caractere curinga. Você pode verificar isso abrindo o arquivo .mobileprovision em um editor de texto, pesquisando por **keychain-access-groups** e incluindo um curinga. Por exemplo:
    ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```

7. Depois que você habilitar o compartilhamento de conjunto de chaves, siga estas etapas para criar um grupo de acesso separado no qual os dados do SDK de Aplicativo do Intune serão armazenados. Você pode criar um grupo de acesso do conjunto de chaves usando a interface do usuário ou o arquivo de direitos. Se você estiver usando a interface do usuário para criar o grupo de acesso do conjunto de chaves, execute as etapas abaixo:

    1. Se seu aplicativo móvel não tiver grupos de acesso do conjunto de chaves definidos, adicione a ID do pacote do aplicativo como o primeiro grupo.

    2. Adicione o grupo de conjunto de chaves compartilhado `com.microsoft.intune.mam` aos grupos de acesso existentes. Este grupo de acesso é usado pelo SDK de Aplicativo do Intune para armazenar dados.

    3. Adicione `com.microsoft.adalcache` a seus grupos de acesso existentes.

        4. Adicione `com.microsoft.workplacejoin` a seus grupos de acesso existentes.
            ![SDK de Aplicativo do Intune para iOS: compartilhamento de conjunto de chaves](./media/intune-app-sdk-ios-keychain-sharing.png)

    5. Se você estiver usando o arquivo de direitos para criar o grupo de acesso do conjunto de chaves, você precisará acrescentar `$(AppIdentifierPrefix)` no início do arquivo de direito do grupo de acesso de conjunto de chaves. Por exemplo:

            * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
            * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    > [!NOTE]
    > Um arquivo de direitos é um arquivo XML que é exclusivo para seu aplicativo móvel. Ele é usado para especificar funcionalidades e permissões especiais em seu aplicativo iOS.

7. Se o aplicativo definir esquemas de URL em seu arquivo info.plist, adicione outro esquema com um sufixo `-intunemam` a cada esquema de URL.

8. Para aplicativos móveis desenvolvidos no iOS 9 e posterior, inclua todos os protocolos que o aplicativo passar para `UIApplication canOpenURL` na matriz `LSApplicationQueriesSchemes` do arquivo Info.plist do aplicativo. Além disso, para cada protocolo listado, adicione um novo protocolo e acrescente `-intunemam` a ele. Você também deve incluir `http-intunemam`, `https-intunemam`e `ms-outlook-intunemam` na matriz.

9. Se o aplicativo tiver grupos de aplicativo definidos em seus direitos, adicione esses grupos ao dicionário **IntuneMAMSettings** sob a chave `AppGroupIdentifiers` como uma matriz de cadeias de caracteres.



## Configurar a ADAL (Biblioteca de Autenticação do Azure Active Directory)
<a id="configure-azure-active-directory-authentication-library-adal" class="xliff"></a>

O SDK de Aplicativo do Intune usa a [Biblioteca de Autenticação do Azure Active Directory](https://github.com/AzureAD/azure-activedirectory-library-for-objc) para seus cenários de inicialização condicional e autenticação. Ele também se baseia na ADAL para registrar a identidade do usuário no serviço de MAM para gerenciamento sem cenários de registro de dispositivo.

Normalmente, a ADAL requer que os aplicativos se registrem no Azure Active Directory (AAD) e obtenham uma ID exclusiva (ID do cliente), entre outros identificadores, para assegurar a segurança dos tokens concedidos ao aplicativo. A menos que seja especificado de outra forma, o SDK de Aplicativo do Intune usa valores de registro padrão ao contatar o Azure AD.  

Se o aplicativo já usar a ADAL para autenticar usuários, o aplicativo deverá usar seus valores de registro existentes e substituir os valores padrão do SDK de Aplicativo do Intune. Isso garante que a autenticação não seja solicitada duas vezes dos usuários (uma vez pelo SDK de Aplicativo do Intune e uma vez pelo aplicativo).

### Recomendações
<a id="recommendations" class="xliff"></a>

Recomendamos que seu aplicativo tenha links para a [versão mais recente da ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) em sua ramificação mestre. Atualmente, o SDK de Aplicativo do Intune usa a ramificação do agente da ADAL para dar suporte a aplicativos que precisam de acesso condicional. (Esses aplicativos, portanto, dependem do aplicativo Microsoft Authenticator.) No entanto, o SDK é ainda compatível com a ramificação mestre da ADAL. Use a ramificação apropriada para seu aplicativo.

### Vincular a binários da ADAL
<a id="link-to-adal-binaries" class="xliff"></a>

Execute estas etapas para vincular seu aplicativo aos binários do ADAL:

1. Baixe a [Biblioteca de Autenticação do Azure Active Directory (ADAL) para Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) do GitHub e siga as [instruções](https://github.com/AzureAD/azure-activedirectory-library-for-objc/blob/master/README.md) sobre como baixar a ADAL usando submódulos do Git ou CocoaPods.

2. Inclua o pacote de recursos `ADALiOSBundle.bundle` no projeto arrastando-o para **Copiar Recursos do Pacote** em **Fases de Build**.

3. Adicione `-force_load {PATH_TO_LIB}/libADALiOS.a` à definição de configuração de build `OTHER_LDFLAGS` do projeto ou **Outros Sinalizadores do Vinculador** na interface do usuário. `PATH_TO_LIB` deve ser substituído pelo local dos binários da ADAL.



### Compartilhar o cache do token da ADAL com outros aplicativos assinados com o mesmo perfil de provisionamento?**
<a id="share-the-adal-token-cache-with-other-apps-signed-with-the-same-provisioning-profile" class="xliff"></a>

Se você quiser compartilhar tokens ADAL entre aplicativos assinados com o mesmo perfil de provisionamento, siga as instruções abaixo:

1. Se o seu aplicativo não tiver grupos de acesso do conjunto de chaves definidos, adicione a ID do pacote do aplicativo como o primeiro grupo.

2. Habilite o SSO (logon único) da ADAL adicionando os grupos de acesso `com.microsoft.adalcache` e `com.microsoft.workplacejoin` nos direitos do conjunto de chaves.

3. Caso você esteja definindo explicitamente o grupo de conjunto de chaves do cache compartilhado da ADAL, certifique-se de que ele seja definido como `<app_id_prefix>.com.microsoft.adalcache`. A ADAL definirá isso para você a menos que você faça uma substituição. Se você quiser especificar um grupo de conjunto de chaves personalizado para substituir `com.microsoft.adalcache`, especifique isso no arquivo Info.plist em "IntuneMAMSettings", usando a chave `ADALCacheKeychainGroupOverride`.

### Definir as configurações de ADAL para o SDK do Aplicativo do Intune
<a id="configure-adal-settings-for-the-intune-app-sdk" class="xliff"></a>

Se o seu aplicativo já usar a ADAL para autenticação e tiver suas próprias configurações de ADAL, force o SDK de Aplicativo do Intune a usar as mesmas configurações durante a autenticação no Azure Active Directory. Isso garantirá que o aplicativo não solicitará a autenticação duas vezes ao usuário. Veja [Definir as configurações do SDK do Aplicativo do Intune](#configure-settings-for-the-intune-app-sdk) para obter informações sobre como popular as seguintes configurações:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Se o seu aplicativo já usar a ADAL, as configurações a seguir serão necessárias:

1. No arquivo Info.plist do projeto, no dicionário **IntuneMAMSettings** com o nome de chave `ADALClientId`, especifique a ID do cliente a ser usada para chamadas da ADAL.

2. Também no dicionário **IntuneMAMSettings** com o nome de chave `ADALAuthority`, especifique a autoridade do Azure AD.

3. Também no dicionário **IntuneMAMSettings** com o nome de chave `ADALRedirectUri`, especifique o URI de redirecionamento a ser usado para chamadas da ADAL. Você também precisa especificar o `ADALRedirectScheme` dependendo do formato de URI de redirecionamento do aplicativo.


Além disso, você pode substituir a URL de Autoridade do Azure AD por uma URL específica do locatário fornecida no tempo de execução. Para fazer isso, basta definir a propriedade `aadAuthorityUriOverride` na instância `IntuneMAMPolicyManager`.

> [!NOTE]
> A configuração da URL de Autoridade do AAD é obrigatória para [APP sem registro do dispositivo](#App-protection-policy-without-device-enrollment) para permitir que o SDK reutilize o token de atualização do ADAL buscado pelo aplicativo.

O SDK continuará usando essa URL da autoridade para atualização da política e todas as solicitações de registro posteriores, a menos que o valor seja apagado ou alterado.  Portanto, é importante apagar o valor quando um usuário gerenciado sai do aplicativo e para redefini-lo quando um novo usuário gerenciado entrar.

### Se o seu aplicativo não usar a ADAL
<a id="if-your-app-does-not-use-adal" class="xliff"></a>

Se seu aplicativo não usar a ADAL, o SDK de Aplicativo do Intune fornecerá valores padrão para parâmetros ADAL e lidará com a autenticação no Azure AD. Você não precisa especificar qualquer valor para as configurações de ADAL listadas acima.

## Política de proteção do aplicativo sem registro de dispositivo
<a id="app-protection-policy-without-device-enrollment" class="xliff"></a>

### Visão geral
<a id="overview" class="xliff"></a>
Política de proteção de aplicativo do Intune sem registro do dispositivo, também conhecido como **APP-WE** ou MAM-WE, permite que os aplicativos sejam gerenciados pelo Intune sem a necessidade de o dispositivo ser registrado no Gerenciamento de Dispositivo Móvel (MDM) do Intune. Para oferecer suporte a essa nova funcionalidade, o aplicativo deverá participar para registrar as contas de usuário para o gerenciamento. Para usar as novas APIs, siga estas etapas:

1. Use a versão mais recente do SDK de Aplicativo do Intune, que dá suporte ao gerenciamento de aplicativos com ou sem registro de dispositivo.

2. Adicione IntuneMAMEnrollment.h a todos os arquivos que chamarão as APIs.

### Registrar as contas de usuário
<a id="register-user-accounts" class="xliff"></a>

Um aplicativo poderá receber a política de proteção do aplicativo do serviço do Intune se o aplicativo estiver registrado com um serviço APP-WE em nome de uma conta de usuário especificada. É responsabilidade do aplicativo registrar qualquer usuário conectado recentemente com o SDK. Após a nova conta de usuário ser autenticada, o aplicativo deve chamar o método `registerAndEnrollAccount` encontrado em Headers/IntuneMAMEnrollment.h:

```objc
/**


 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```
Chamando o método `registerAndEnrollAccount`, o SDK registrará a conta de usuário e tentará registrar o aplicativo em nome dessa conta. Se o registro falhar por algum motivo, o SDK automaticamente tentará realizar o registro novamente após 24 horas. Para fins de depuração, o aplicativo pode receber notificações, por meio de um delegado, sobre os resultados das solicitações de registro.

Depois de invocar essa API, o aplicativo poderá continuar funcionando normalmente. Se o registro for bem-sucedido, o SDK notificará o usuário se que uma reinicialização do aplicativo é necessária. Nesse momento, o usuário poderá reiniciar o aplicativo imediatamente.

### Cancelar o registro de contas de usuário
<a id="deregister-user-accounts" class="xliff"></a>

Antes que um usuário seja desconectado de um aplicativo, o aplicativo deve cancelar o registro do usuário do SDK. Isso garantirá que:

1. novas tentativas de registro na conta do usuário deixem de ser feitas.

2. A política de proteção do aplicativo será removida.

3. Se o aplicativo iniciar um apagamento seletivo (opcional), todos os dados corporativos serão excluídos.

Antes que o usuário seja desconectado, o aplicativo deverá chamar a seguinte API em `Headers/IntuneMAMEnrollment.h`:

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune MAM AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */

(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

Esse método deve ser chamado antes que os tokens do Azure AD da conta do usuário sejam excluídos. O SDK precisa do token do AAD da conta do usuário para fazer solicitações específicas ao serviço de APP-WE em nome do usuário.

Se o aplicativo for, por conta própria, excluir dados corporativos do usuário, o sinalizador `doWipe` poderá ser definido como falso. Caso contrário, o aplicativo pode fazer o SDK iniciar um apagamento seletivo. Isso resultará em uma chamada ao delegado de apagamento seletivo do aplicativo.

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

### Aplicativos que não usam a ADAL
<a id="apps-that-do-not-use-adal" class="xliff"></a>

Os aplicativos que não conectam o usuário usando ADAL ainda poderão receber a política de proteção do aplicativo do serviço do Intune pela chamada à API, para que o SDK manipule a autenticação. Os aplicativos deverão usar essa técnica quando não autenticaram um usuário ao Azure AD, mas ainda precisarem recuperar a política de proteção do aplicativo para ajudar a proteger os dados. Um exemplo é se outro serviço de autenticação estiver sendo usado para entrar no aplicativo ou se o aplicativo não oferecer nenhum suporte para entrar. Para fazer isso, o aplicativo deve chamar o método `loginAndEnrollAccount` em Headers/IntuneMAMEnrollment.h:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```

Ao chamar esse método, se nenhum token existente puder ser encontrado, o SDK solicitará credenciais ao usuário. O SDK, em seguida, tentará registrar o aplicativo com o serviço APP-WE em nome da conta de usuário fornecida. O método pode ser chamado com "nulo" como a identidade. Nesse caso, o SDK fará o registro com o usuário gerenciado existente no dispositivo ou solicitará que o usuário forneça um nome de usuário, se nenhum usuário existente for encontrado.

Se o registro falhar, o aplicativo deverá considerar chamar essa API novamente no futuro, dependendo dos detalhes da falha. O aplicativo pode receber [notificações](#Status-result-and-debug-notifications), por meio de um delegado, sobre os resultados das solicitações de registro.

Após essa API ser invocada, o aplicativo pode continuar funcionando normalmente. Se o registro for bem-sucedido, o SDK notificará o usuário se que uma reinicialização do aplicativo é necessária.

## Notificações de status, resultados e depuração
<a id="status-result-and-debug-notifications" class="xliff"></a>

O aplicativo pode receber notificações de status, resultados e depuração sobre as seguintes solicitações ao serviço de MAM do Intune:

 - Solicitações de registro
 - Solicitações de atualização de políticas
 - Solicitações de cancelamento de registro

As notificações são apresentadas por meio de métodos de delegação no `Headers/IntuneMAMEnrollmentDelegate.h`:

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

Esses métodos de delegação retornam um objeto `IntuneMAMEnrollmentStatus` que contém as seguintes informações:

- a identidade da conta associada à solicitação
- Um código de status indicando o resultado da solicitação
- uma cadeia de caracteres de erro com uma descrição do código de status
- Um objeto `NSError`

Esse objeto é definido em `IntuneMAMEnrollmentStatus.h`, em conjunto com os códigos de status específicos que podem ser retornados.


### Código de exemplo
<a id="sample-code" class="xliff"></a>

A seguir, temos exemplos de implementações dos métodos de delegação:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}


- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

```

## Reinicialização do aplicativo
<a id="app-restart" class="xliff"></a>

Quando um aplicativo recebe políticas de proteção do aplicativo pela primeira vez, ele deve ser reiniciado para que os ganchos obrigatórios sejam aplicados. Para notificar o aplicativo de que uma reinicialização precisa ocorrer, o SDK fornece um método delegado em Headers/IntuneMAMPolicyDelegate.h.

```objc
 - (BOOL) restartApplication
```
O valor retornado desse método informa o SDK se o aplicativo deverá realizar a reinicialização necessária:   

 - Se true for retornado, o aplicativo deverá realizar a reinicialização.   

 - Se false for retornado, o SDK reiniciará o aplicativo depois que o método retornar. O SDK mostrará imediatamente uma caixa de diálogo informando ao usuário para reiniciar o aplicativo.

## Personalizar o comportamento do aplicativo
<a id="customize-your-apps-behavior" class="xliff"></a>

O SDK do Aplicativo do Intune contém várias APIs que podem ser chamadas para obter informações sobre a política de proteção do aplicativo do Intune implantada no aplicativo. É possível usar esses dados para personalizar o comportamento do aplicativo. A maioria das configurações de política de proteção do aplicativo é imposta automaticamente pelo SDK e não pelo aplicativo. A única configuração que o aplicativo deve implementar é o controle Salvar como.

### Obtenha a política de proteção do aplicativo
<a id="get-app-protection-policy" class="xliff"></a>

#### IntuneMAMPolicyManager.h
<a id="intunemampolicymanagerh" class="xliff"></a>
A classe IntuneMAMPolicyManager expõe a política de proteção do aplicativo do Intune implantada no aplicativo. Particularmente, ela expõe APIs que são úteis para [habilitar várias identidades](#-enable-multi-identity-optional).

#### IntuneMAMPolicy.h
<a id="intunemampolicyh" class="xliff"></a>
A classe IntuneMAMPolicy expõe a política de proteção do aplicativo do Intune implantada no aplicativo. A maioria das configurações de política expostas nessa classe é aplicada pelo SDK, mas sempre é possível personalizar o comportamento do aplicativo de acordo com a forma de imposição das configurações de política.

Essa classe expõe algumas APIs necessárias para implementar controles salvar como, detalhadas na próxima seção.

### Implementar controles salvar como
<a id="implement-save-as-controls" class="xliff"></a>

O Intune permite que os administradores de TI selecionem em quais locais de armazenamento um aplicativo gerenciado pode salvar dados. Os aplicativos podem consultar o SDK do Aplicativo do Intune quanto aos locais de armazenamento permitidos usando a API **isSaveToAllowedForLocation**, definida em **IntuneMAMPolicy.h**.

Antes que os aplicativos possam salvar dados gerenciados em um armazenamento em nuvem ou localmente, eles devem consultar a API **isSaveToAllowedForLocation** para saber se o administrador de TI permitiu que os dados fossem salvos no local em questão.

Quando os aplicativos usarem a API **isSaveToAllowedForLocation**, deverão passar o UPN para o local de armazenamento, se estiver disponível.

#### Locais de salvamento com suporte
<a id="supported-save-locations" class="xliff"></a>

A API **isSaveToAllowedForLocation** fornece constantes para verificar se o administrador de TI permite que os dados sejam salvos nos seguintes locais definidos em IntuneMAMPolicy.h:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Os aplicativos devem usar as constantes na API **isSaveToAllowedForLocation** para verificar se os dados podem ser salvos em locais considerados "gerenciados" como o OneDrive for Business ou "pessoal". Além disso, a API deve ser usada quando o aplicativo não pode verificar se um local é "gerenciado" ou "pessoal".

Os locais conhecidos como “pessoais” são representados pela constante `IntuneMAMSaveLocationOther`.

A constante `IntuneMAMSaveLocationLocalDrive` deve ser usada quando o aplicativo salva dados em qualquer local no dispositivo local.

## Definir as configurações do SDK do Aplicativo do Intune
<a id="configure-settings-for-the-intune-app-sdk" class="xliff"></a>

Você pode usar o dicionário **IntuneMAMSettings** no arquivo Info.plist do aplicativo para configurar o SDK do Aplicativo do Intune. Se o dicionário IntuneMAMSettings não for visto no arquivo Info.plist, você deverá criar um dicionário no Info.plist em seu aplicativo com o nome do campo "IntuneMAMSettings".

No dicionário IntuneMAMSettings, você poderá adicionar as linhas de configuração de chave/valor para configurar o SDK. A tabela abaixo lista todas as configurações com suporte.

Algumas dessas configurações podem ter sido abordadas nas seções anteriores e outras não se aplicam a todos os aplicativos.

Setting  | Tipo  | Definição | Necessário?
--       |  --   |   --       |  --
ADALClientId  | Cadeia de caracteres  | O identificador do cliente do Azure AD do aplicativo. | Obrigatório se o aplicativo usar a ADAL. |
ADALAuthority | Cadeia de caracteres | A autoridade do Azure AD do aplicativo em uso. É necessário usar seu próprio ambiente no qual as contas do AAD foram configuradas. | Obrigatório se o aplicativo usar a ADAL. Se esse valor estiver ausente, um padrão do Intune será usado.|
ADALRedirectUri  | Cadeia de caracteres  | O URI de redirecionamento do Azure AD do aplicativo. | ADALRedirectUri ou ADALRedirectScheme é obrigatório se o aplicativo usar a ADAL.  |
ADALRedirectScheme  | Cadeia de caracteres  | O URI do esquema de redirecionamento do Azure AD do aplicativo. Pode ser usado no lugar de ADALRedirectUri se o URI de redirecionamento do aplicativo estiver no formato `scheme://bundle_id`. | ADALRedirectUri ou ADALRedirectScheme é obrigatório se o aplicativo usar a ADAL. |
ADALLogOverrideDisabled | Booliano  | Especifica se o SDK roteará todos os logs de ADAL (incluindo chamadas de ADAL do aplicativo, se houver) para seu próprio arquivo de log. O padrão é NÃO. Defina como SIM caso o aplicativo vá definir seu próprio retorno de chamada de log ADAL. | Opcional. |
ADALCacheKeychainGroupOverride | Cadeia de caracteres  | Especifica o grupo de conjunto de chaves a ser usado para o cache da ADAL em vez de "com.microsoft.adalcache". Observe que ele não tem o prefixo app-id. O prefixo será acrescentado à cadeia de caracteres fornecida em tempo de execução. | Opcional. |
AppGroupIdentifiers | Matriz de cadeia de caracteres  | Matriz de grupos de aplicativo na seção de grupos de com.apple.security.application de direitos do aplicativo. | Necessário se o aplicativo usar grupos de aplicativos. |
ContainingAppBundleId | Cadeia de caracteres | Especifica a ID do pacote do aplicativo que contém a extensão. | Necessário para extensões do iOS. |
DebugSettingsEnabled| Booliano | Se definido como SIM, as políticas de teste do pacote de Configurações podem ser aplicadas. Os aplicativos *não* devem ser fornecidos com essa configuração habilitada. | Opcional. |
MainNibFile<br>MainNibFile~ipad  | Cadeia de caracteres  | Essa configuração deve conter o nome do arquivo nib principal do aplicativo.  | Obrigatório se o aplicativo definir MainNibFile em Info.plist. |
MainStoryboardFile<br>MainStoryboardFile~ipad  | Cadeia de caracteres  | Essa configuração deve conter o nome do arquivo storyboard principal do aplicativo. | Necessário se o aplicativo definir UIMainStoryboardFile em Info.plist. |
AutoEnrollOnLaunch| Booliano| Especifica se o aplicativo deverá tentar se registrar automaticamente na inicialização se uma identidade gerenciada existente for detectada e ainda não tiver feito o registro. O padrão é NÃO. <br><br> Observações: se nenhuma identidade gerenciada for encontrada ou nenhum token válido para a identidade estiver disponível no cache do ADAL, a tentativa de registro silenciosamente falhará sem solicitar credenciais, a menos que o aplicativo também tenha definido MAMPolicyRequired como SIM. | Opcional. |
MAMPolicyRequired| Booliano| Especifica se a inicialização do aplicativo será impedida se ele não tiver uma política de proteção do aplicativo do Intune. O padrão é NÃO. <br><br> Observações: os aplicativos não podem ser enviados para a Loja de Aplicativos com MAMPolicyRequired definido como SIM. Ao configurar o MAMPolicyRequired como SIM, o AutoEnrollOnLaunch também deverá ser definido como SIM. | Opcional. |
MAMPolicyWarnAbsent | Booliano| Especifica se o aplicativo alertará o usuário durante a inicialização se ele não tiver uma política de proteção do aplicativo do Intune. <br><br> Observação: os usuários ainda poderão usar o aplicativo sem política após ignorarem o aviso. | Opcional. |
MultiIdentity | Booliano| Especifica se o aplicativo reconhece ou não várias identidades. | Opcional. |
SplashIconFile <br>SplashIconFile ~ ipad | Cadeia de caracteres  | Especifica o arquivo de ícone de abertura (inicialização) do Intune. | Opcional. |
SplashDuration | Número | Quantidade mínima de tempo em segundos pelo qual a tela inicial do Intune será exibida ao iniciar o aplicativo. O padrão é 1,5. | Opcional. |
BackgroundColor| Cadeia de caracteres| Especifica a cor da tela de fundo para as telas de inicialização e de PIN. Aceita uma cadeia de caracteres hexadecimal RGB no formato "#XXXXXX", em que os X pode variar de 0 a 9 ou de A a F. O sinal de libra pode ser omitido.   | Opcional. Opcional; o padrão é cinza claro. |
ForegroundColor| Cadeia de caracteres| Especifica a cor de primeiro plano para as telas de inicialização e de PIN como a cor do texto. Aceita uma cadeia de caracteres hexadecimal RGB no formato "#XXXXXX", em que os X pode variar de 0 a 9 ou de A a F. O sinal de libra pode ser omitido.  | Opcional. O padrão é preto. |
AccentColor | Cadeia de caracteres| Especifica a cor de destaque de tela de PIN como a cor da caixa de texto e a cor de destaque da caixa. Aceita uma cadeia de caracteres hexadecimal RGB no formato "#XXXXXX", em que os X pode variar de 0 a 9 ou de A a F. O sinal de libra pode ser omitido.| Opcional. Opcional; o padrão é azul. |
MAMTelemetryDisabled| Booliano| Especifica se o SDK não enviará dados de telemetria para seu back-end.| Opcional. |

> [!NOTE]
> Se o aplicativo for liberado para a Loja de Aplicativos, `MAMPolicyRequired` deverá ser definido como “NÃO”, conforme os padrões da Loja de Aplicativos.

## Habilitar a configuração voltada para MAM para seus aplicativos iOS
<a id="enabling-mam-targeted-configuration-for-your-ios-applications" class="xliff"></a>
A configuração voltada para MAM permite que um aplicativo receba dados de configuração por meio do SDK do aplicativo do Intune. O formato e as variantes desses dados devem ser definidos e comunicados aos clientes do Intune pelo proprietário/desenvolvedor do aplicativo. Os administradores do Intune podem direcionar e implantar dados de configuração por meio do console do Intune Azure. A partir do SDK do Intune App para iOS (v 7.0.1), aplicativos que participam da configuração voltada para MAM podem receber dados de configuração de MAM direcionada por meio do serviço de MAM. Os dados de configuração de aplicativo são enviados por push por meio de nosso Serviço MAM diretamente para o aplicativo em vez de pelo canal MDM. O SDK do aplicativo do Intune fornece uma classe para acessar os dados recuperados desses consoles. Considere os seguintes pré-requisitos: <br>
* O aplicativo precisa ser registrado em MAM-WE para poder acessar a interface do usuário de configuração voltada para MAM. Para obter mais informações sobre MAM-WE, consulte [Política de proteção de aplicativo sem registro de dispositivo no guia do SDK do aplicativo do Intune](https://docs.microsoft.com/en-us/intune/app-sdk-ios#app-protection-policy-without-device-enrollment).
* Inclua ```IntuneMAMAppConfigManager.h``` no arquivo de origem do aplicativo.
* Chame ```[[IntuneMAMAppConfig instance] appConfigForIdentity:]``` para obter o objeto de configuração do aplicativo.
* Chame o seletor apropriado no objeto ```IntuneMAMAppConfig```. Por exemplo, se a chave do seu aplicativo é uma cadeia de caracteres, use ```stringValueForKey``` ou ```allStringsForKey```. O arquivo ```IntuneMAMAppConfig.h header``` aborda as condições de erro/valores retornados.

Para obter mais informações sobre as funcionalidades da API do Graph em relação aos valores de configuração voltada para MAM, consulte [Referência da API do Graph para a configuração voltada para MAM](https://graph.microsoft.io/en-us/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create). <br>

Para obter mais informações sobre como criar uma política de configuração de aplicativo voltada para MAM no iOS, consulte a seção sobre configuração de aplicativo voltada para MAM em [Como usar políticas de configuração de aplicativo do Microsoft Intune para iOS](https://docs.microsoft.com/en-us/intune/app-configuration-policies-use-ios).

## Telemetria
<a id="telemetry" class="xliff"></a>

Por padrão, o SDK do Aplicativo do Intune para iOS registra dados de telemetria nos eventos de uso a seguir. Esses dados são enviados para o Microsoft Intune.

* **Inicialização do aplicativo**: para ajudar o Microsoft Intune a obter informações sobre o uso de aplicativos habilitados para MAM por tipo de gerenciamento (MAM com MDM, MAM sem registro de MDM etc.).

* **Chamadas de registro**: para ajudar o Microsoft Intune a obter informações sobre a taxa de sucesso e outras métricas de desempenho de chamadas de registro iniciadas do lado do cliente.

> [!NOTE]
> Se optar por não enviar dados de telemetria do SDK de Aplicativo do Intune para o Microsoft Intune do seu aplicativo móvel, você deverá desabilitar a captura de telemetria pelo SDK de Aplicativo do Intune. Defina a propriedade `MAMTelemetryDisabled` como SIM no dicionário IntuneMAMSettings.

## Habilitar várias identidades (opcional)
<a id="enable-multi-identity-optional" class="xliff"></a>

Por padrão, o SDK aplica a política ao aplicativo como um todo. Várias identidades é um recurso do MAM que você pode habilitar para aplicar uma política em um nível por identidade. Ele requer mais participação do aplicativo do que outros recursos de MAM.

O aplicativo precisa informar ao SDK de aplicativo quando pretende alterar a identidade ativa. O SDK também notificará o aplicativo quando uma alteração de identidade for necessária. Atualmente, há suporte para apenas uma identidade gerenciada. Depois que o usuário registrar o dispositivo ou o aplicativo, o SDK usará essa identidade e a considerará a identidade gerenciada primária. Outros usuários no aplicativo serão tratados como não gerenciados, com configurações de política irrestritas.

Observe que uma identidade é definida simplesmente como uma cadeia de caracteres. As identidades não diferenciam maiúsculas de minúsculas. As solicitações de identidade ao SDK podem não retornar o mesmo esquema de maiúsculas e minúsculas usado originalmente ao definir a identidade.

### Visão geral de identidade
<a id="identity-overview" class="xliff"></a>

Uma identidade é simplesmente o nome de usuário de uma conta (por exemplo, user@contoso.com). Os desenvolvedores podem definir a identidade do aplicativo nos níveis a seguir:

* **Identidade de processo**: define a identidade de todo o processo e é usada principalmente para aplicativos de identidade única. Essa identidade afeta todas as tarefas, arquivos e a interface do usuário.

* **Identidade de interface do usuário**: determina quais políticas são aplicadas às tarefas de interface do usuário no thread principal, como recortar/copiar/colar, PIN, autenticação e compartilhamento de dados. A identidade de interface do usuário não afeta as tarefas de arquivo como criptografia, backup etc.

* **Identidade de thread**: a identidade de thread afeta quais políticas são aplicadas no thread atual. Essa identidade afeta todas as tarefas, arquivos e a interface do usuário.

É responsabilidade do aplicativo definir as identidades adequadamente, quer o usuário seja gerenciado ou não.

A qualquer momento, todo thread tem uma identidade efetiva para tarefas de interface do usuário e tarefas de arquivo. Essa é a identidade usada para verificar quais políticas, se houver, devem ser aplicadas. Se a identidade for "nenhuma identidade" ou o usuário não for gerenciado, nenhuma política será aplicada. Os diagramas abaixo mostram como as identidades efetivas são determinadas.

  ![SDK do Aplicativo do Intune para iOS: estruturas e bibliotecas vinculadas](./media/ios-thread-identities.png)

### Filas de thread
<a id="thread-queues" class="xliff"></a>

Frequentemente, os aplicativos expedem tarefas síncronas e assíncronas para filas de thread. O SDK intercepta chamadas de GCD (Grand Central Dispatch) e associa a identidade do thread atual às tarefas expedidas. Quando as tarefas são concluídas, o SDK altera temporariamente a identidade do thread para a identidade associada às tarefas, conclui as tarefas e restaura a identidade do thread original.


Como `NSOperationQueue` é criado sobre o GCD, `NSOperations` será executado na identidade do thread no momento em que as tarefas forem adicionadas ao `NSOperationQueue`. O `NSOperations` ou funções expedidas diretamente usando o GCD também têm a capacidade de alterar a identidade do thread atual conforme são executadas. Essa identidade substituirá a identidade herdada do thread de expedição.

### Proprietário do arquivo
<a id="file-owner" class="xliff"></a>

O SDK acompanha as identidades dos proprietários do arquivo local e aplica políticas de acordo com elas. Um proprietário do arquivo é estabelecido quando o arquivo é criado ou quando é aberto no modo de truncamento. O proprietário é definido como a identidade de operação do arquivo efetivo do thread que executa a operação.

Como alternativa, os aplicativos podem definir a identidade do proprietário do arquivo explicitamente usando `IntuneMAMFilePolicyManager`. Os aplicativos podem usar o `IntuneMAMFilePolicyManager` para recuperar o proprietário do arquivo e definir a identidade da interface do usuário antes de mostrar o conteúdo do arquivo.

### Dados compartilhados
<a id="shared-data" class="xliff"></a>

Se o aplicativo criar arquivos que contêm dados de usuários gerenciados e não gerenciados, será responsabilidade do aplicativo criptografar os dados do usuário gerenciado. Você pode criptografar dados usando as APIs `protect` e `unprotect` em `IntuneMAMDataProtectionManager`.

O método `protect` aceita uma identidade que pode ser um usuário gerenciado ou não gerenciado. Se o usuário for gerenciado, os dados serão criptografados. Se o usuário não for gerenciado, um cabeçalho será adicionado aos dados codificando a identidade, mas os dados não serão criptografados. O método `protectionInfo` pode ser usado para recuperar o proprietário dos dados.

### Extensões de compartilhamento
<a id="share-extensions" class="xliff"></a>

Se o aplicativo contiver uma Extensão de compartilhamento, o proprietário do item sendo compartilhado poderá ser recuperado usando o método `protectionInfoForItemProvider` em `IntuneMAMDataProtectionManager`. Se o item compartilhado for um arquivo, o SDK processará a definição do proprietário do arquivo. Se o item compartilhado forem dados, o aplicativo será responsável por definir o proprietário do arquivo se esses dados forem persistidos em um arquivo; será responsável também por chamar a API `setUIPolicyIdentity` antes de mostrar esses dados na interface do usuário.

### Ligar várias identidades
<a id="turning-on-multi-identity" class="xliff"></a>

Por padrão, considera-se que todos os aplicativos são aplicativos de identidade única. O SDK define a identidade do processo para o usuário registrado. Para habilitar o suporte a várias identidades, uma configuração booliana com o nome `MultiIdentity` e o valor YES deve ser adicionada ao dicionário IntuneMAMSettings no arquivo Info.plist do aplicativo.

> [!NOTE]
> Quando o recurso várias identidades estiver habilitado, a identidade do processo, identidade da interface do usuário e identidades de thread serão definidas como nulas. O aplicativo é responsável por defini-las adequadamente.

### Alternando identidades
<a id="switching-identities" class="xliff"></a>

* **Alternância de identidade iniciada pelo aplicativo**:

    Na inicialização, é considerado que aplicativos com várias identidades estejam sendo executados sob uma conta desconhecida, não gerenciada. A interface do usuário de inicialização condicional não será executada e nenhuma política será imposta ao aplicativo. É responsabilidade do aplicativo notificar o SDK sempre que a identidade precisar ser alterada. Normalmente, isso ocorrerá sempre que o aplicativo estiver prestes a mostrar dados de uma conta de usuário específica.

    Um exemplo é quando o usuário tenta abrir um documento, caixa de correio ou uma guia em um bloco de anotações. O aplicativo precisa notificar o SDK antes que arquivo, caixa de correio ou guia seja, de fato, aberto. Isso é feito através da API `setUIPolicyIdentity` em `IntuneMAMPolicyManager`. Essa API deve ser chamada quer o usuário seja gerenciado ou não. Se o usuário for gerenciado, o SDK executará as verificações de inicialização condicional (como detecção de jailbreak, PIN, autenticação etc.).

    O resultado da alternância de identidade é retornado ao aplicativo de forma assíncrona por meio de um manipulador de conclusão. O aplicativo deve adiar a abertura do documento, da caixa de correio ou da guia até que um código de resultado de êxito seja retornado. Se a mudança de identidade falhar, o aplicativo deverá cancelar a tarefa.

* **Alternância de identidade iniciada pelo SDK**:

    Há casos em que o SDK precisa solicitar que o aplicativo mude para uma identidade específica. Aplicativos com várias identidades devem implementar o método `identitySwitchRequired` em `IntuneMAMPolicyDelegate` para processar essa solicitação.

    Quando esse método é chamado, se o aplicativo for capaz de processar a solicitação de mudar para a identidade especificada, ele deverá passar `IntuneMAMAddIdentityResultSuccess` no manipulador de conclusão. Se não for capaz de processar a mudança de identidade, o aplicativo deverá passar `IntuneMAMAddIdentityResultFailed` para o manipulador de conclusão.

    O aplicativo não precisa chamar `setUIPolicyIdentity` em resposta a essa chamada. Se o SDK precisar que o aplicativo alterne para uma conta de usuário não gerenciada, a cadeia de caracteres vazia será passada para a chamada `identitySwitchRequired`.

* **Apagamento seletivo**:

    Quando o aplicativo for apagado seletivamente, o SDK chamará o método `wipeDataForAccount` em `IntuneMAMPolicyDelegate`. É responsabilidade do aplicativo remover a conta de usuário especificada e todos os dados associados a ela. O SDK é capaz de remover todos os arquivos pertencentes ao usuário e fará isso se o aplicativo retornas FALSE da chamada `wipeDataForAccount`.

    Observe que este método é chamado de um thread em segundo plano. O aplicativo não deve retornar um valor até que todos os dados para o usuário tenham sido removidos (com exceção dos arquivos, se o aplicativo retornar FALSE).

## Testar as configurações de política de proteção de aplicativo no Xcode
<a id="test-app-protection-policy-settings-in-xcode" class="xliff"></a>

Antes de testar manualmente seu aplicativo habilitado para Intune em produção, você pode usar um arquivo Settings.bundle no Xcode. Isso permitirá que você defina políticas de proteção de aplicativo para teste sem a necessidade de uma conexão com o Intune.

### Habilitar o teste da política
<a id="enable-policy-testing" class="xliff"></a>

Execute as etapas abaixo para habilitar o teste de política no Xcode:

1. Você precisa estar em uma compilação de depuração. Adicione um arquivo Settings.bundle clicando com o botão direito do mouse na pasta de nível superior no seu projeto. Selecione **Adicionar** > **Novo Arquivo** no menu. Em **Recursos**, selecione o modelo **Pacote de Configurações**.

2.  Copie o seguinte bloco no arquivo Settings.bundle/**Root.plist** para a compilação de depuração:
    ```xml
    <key>PreferenceSpecifiers</key>
    <array>
        <dict>
            <key>Type</key>
            <string>PSChildPaneSpecifier</string>
            <key>Title</key>
            <string>MDM Debug Settings</string>
            <key>Key</key>
            <string>MAMDebugSettings</string>
            <key>File</key>
            <string>MAMDebugSettings</string>
        </dict>
    </array>
    ```

3. No dicionário**IntuneMAMSettings** no Info.plist do aplicativo, adicione um valor booliano chamado "DebugSettingsEnabled". Defina o valor de DebugSettingsEnabled como "SIM".



### Configurações da política de proteção de aplicativo
<a id="app-protection-policy-settings" class="xliff"></a>

A tabela a seguir descreve as configurações da política de proteção de aplicativo que você pode testar usando MAMDebugSettings.plist. Para ativar uma configuração, adicione-a em MAMDebugSettings.plist.

| Nome da configuração de política | Descrição | Valores possíveis |
| -- | -- | -- |
| AccessRecheckOfflineTimeout | O período em minutos durante os quais o aplicativo pode ficar offline antes de o Intune bloquear sua inicialização ou retomada se a autenticação estiver habilitada. | Qualquer inteiro maior do que 0 |
|   AccessRecheckOnlineTimeout | O período em minutos durante o qual o aplicativo pode executar antes de o usuário receber uma solicitação de PIN ou autenticação ao iniciar ou retomar (se a autenticação ou PIN para acesso estiver habilitado). | Qualquer inteiro maior do que 0 |
| AppSharingFromLevel | Especifica de quais aplicativos este aplicativo pode aceitar dados. | 0 = |
## Melhores práticas de iOS
<a id="ios-best-practices" class="xliff"></a>

A seguir estão algumas melhores práticas para o desenvolvimento para iOS:

* O sistema de arquivos iOS diferencia maiúsculas de minúsculas. Certifique-se de que o caso está correto para nomes de arquivo como `libIntuneMAM.a` e `IntuneMAMResources.bundle`.

* Se o Xcode tiver problemas para encontrar `libIntuneMAM.a`, você pode corrigir o problema adicionando o caminho para essa biblioteca aos caminhos de pesquisa do vinculador.

## Perguntas Frequentes
<a id="faqs" class="xliff"></a>


**Todas as APIs são endereçáveis pelo Swift nativo ou pela interoperabilidade Objective-C e Swift?**

As APIs do SDK do aplicativo Intune estão apenas em Objective-C e não dão suporte ao Swift **nativo**. A interoperabilidade Swift com Objective-C é obrigatória.


**Todos os usuários do meu aplicativo precisam estar registrados no serviço de APP-WE?**

Não. Na verdade, somente contas corporativas ou de estudante devem ser registradas com o SDK do Intune App. Os aplicativos são responsáveis por determinar se uma conta é usada em um contexto de trabalho ou escolar.   

**E quanto aos usuários que já entraram no aplicativo? Eles precisam ser registrados?**

O aplicativo é responsável pelo registro de usuários depois que eles tiverem sido autenticados com êxito. O aplicativo também é responsável pelo registro de todas as contas existentes que podem ter estado presentes antes do aplicativo ter funcionalidade de MAM sem MDM.   

Para fazer isso, o aplicativo deve fazer uso do método `registeredAccounts:`. Esse método retorna um dicionário NSDictionary que contém todas as contas registradas no serviço de MAM do Intune. Se qualquer conta existente no aplicativo não estiver na lista, o aplicativo deverá registrar essas contas via `registerAndEnrollAccount:`.

**Com que frequência o SDK repete tentativas de registro?**

O SDK tentará, automaticamente, realizar todas as inscrições com falha em um intervalo de 24 horas. O SDK faz isso para garantir que, se a organização de um usuário tiver habilitado o MAM após o usuário ter se conectado ao aplicativo, o usuário seja registrado e receba políticas com êxito.

O SDK deixará de repetir as tentativas quando detectar que um usuário registrou o aplicativo com êxito. Isso acontece porque apenas um usuário pode registrar um aplicativo em um dado momento. Se o registro do usuário for cancelado, as tentativas começarão novamente no mesmo intervalo de 24 horas.

**Por que o registro do usuário precisa ser cancelado?**

O SDK executará periodicamente as seguintes ações na tela de fundo:

 - Se o aplicativo ainda não estiver registrado, ele tentará registrar todas as contas registradas a cada 24 horas.
 - Se o aplicativo estiver registrado, o SDK verificará se há atualizações da política de proteção do aplicativo a cada 8 horas.

Ao cancelar o registro de um usuário, ele notifica o SDK que o usuário não usará mais o aplicativo e que o SDK pode interromper qualquer um dos eventos periódicos para essa conta de usuário. Ele também dispara o cancelamento do registro do aplicativo e um apagamento seletivo, se necessário.

**Eu devo definir o sinalizador doWipe como true no método de cancelamento de registro?**

Esse método deve ser chamado antes que usuário seja desconectado do aplicativo.  Se, como parte da desconexão, os dados do usuário forem excluídos do aplicativo, `doWipe` poderá ser definido como false. No entanto, se o aplicativo não remover os dados do usuário, `doWipe` deverá ser definido como true para que o SDK possa excluir os dados.

**Há outras formas de cancelar o registro de um aplicativo?**

Sim, o administrador de TI pode enviar um comando de apagamento seletivo para o aplicativo. Isso cancelará o registro do usuário e apagará seus dados. O SDK processa automaticamente esse cenário e envia uma notificação por meio do método de delegação de cancelamento de registro.



## Enviar seu aplicativo à App Store
<a id="submit-your-app-to-the-app-store" class="xliff"></a>

Ambos o build da biblioteca estática e o do framework do SDK de Aplicativo do Intune são binários universais. Isso significa que eles têm código para todas as arquiteturas de dispositivo e de simulador. A Apple rejeitará aplicativos enviados à App Store se eles contiverem código de simulador. Ao compilar com a biblioteca estática para builds somente de dispositivo, o vinculador removerá automaticamente o código de simulador. Siga as etapas abaixo para garantir que todos os códigos de simulador sejam removidos antes de carregar o aplicativo na App Store.

1. Confirme se `IntuneMAM.framework` está em sua área de trabalho.

2. Execute estes comandos:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    O primeiro comando remove as arquiteturas de simulador do arquivo DYLIB da estrutura. O segundo comando copia o arquivo DYLIB somente para dispositivos de volta para o diretório da estrutura.
