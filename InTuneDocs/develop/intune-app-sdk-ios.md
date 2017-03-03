---
title: Guia do desenvolvedor do SDK de Aplicativo do Microsoft Intune para iOS | Microsoft Docs
description: "O SDK de Aplicativo do Microsoft Intune para iOS permite incorporar políticas de proteção de aplicativo do Intune – na forma de MAM (gerenciamento de aplicativo móvel) – em seu aplicativo iOS."
keywords: 
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 96861614075d4eed41ca440af8a8cc42e5f2ff38
ms.openlocfilehash: 8633de5aea6cc3f98c5e331fc3de43daf85903ae
ms.lasthandoff: 02/23/2017


---

# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>SDK de Aplicativo do Microsoft Intune para o Guia do Desenvolvedor do iOS

> [!NOTE]
> Primeiro, leia o artigo [Guia de Introdução ao SDK de Aplicativo do Intune](intune-app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.

O SDK do Aplicativo do Microsoft Intune para iOS permite incorporar políticas de proteção do aplicativo do Intune – também conhecidas como políticas MAM – em seu aplicativo iOS. Um aplicativo habilitado para MAM é aquele que está integrado ao SDK do Aplicativo do Intune. Ele permite que os administradores de TI implantem políticas de proteção do aplicativo em seu aplicativo móvel quando o Intune gerencia o aplicativo de forma ativa.

## <a name="prerequisites"></a>Pré-requisitos

* Você precisará de um computador Mac OS que executa o OS X 10.8.5 ou posterior e tenha a versão 5 ou posterior do conjunto de ferramentas XCode instalada.

* Examinar os [Termos de Licença do SDK de Aplicativo do Intune para iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Imprimir e guardar uma cópia dos termos de licença para seus registros. Ao baixar e usar o SDK de Aplicativo do Intune para iOS, você concorda com esses termos de licença.  Se você não aceitá-los, não use o software.

* Baixe os arquivos para o SDK do Aplicativo do Intune para iOS no [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).

## <a name="whats-in-the-sdk"></a>Novidades no SDK

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


## <a name="how-the-intune-app-sdk-works"></a>Como o SDK de Aplicativos do Intune funciona

O objetivo do SDK do Intune APP para iOS é adicionar recursos de gerenciamento de aplicativos a aplicativos iOS com alterações mínimas de código. Quanto menos alterações houver no código, menor será o tempo de chegada no mercado sem afetar a consistência e a estabilidade do aplicativo móvel.


## <a name="build-the-sdk-into-your-mobile-app"></a>Compilar o SDK em seu aplicativo móvel

Para habilitar o SDK de Aplicativo do Intune, siga estas etapas:

1. **Opção 1**: Link para a biblioteca `libIntuneMAM.a`. Arraste e solte a biblioteca `libIntuneMAM.a` na lista **Estruturas e Bibliotecas Vinculadas** do projeto de destino.
    ![SDK de Aplicativos do Intune para iOS: estruturas e bibliotecas vinculadas](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    > [!NOTE]
    > Se você planeja lançar o aplicativo na App Store, use a versão de `libIntuneMAM.a` criada para a versão de lançamento e não para a versão de depuração. A versão de lançamento estará na pasta **lançamento**. A versão de depuração tem saída detalhada, o que ajuda a solucionar problemas com o SDK do Aplicativo do Intune.

    **Opção 2**: vincular `IntuneMAM.framework` ao seu projeto. Arraste `IntuneMAM.framework` para a lista **Estruturas e Bibliotecas Vinculadas** do projeto de destino.

    > [!NOTE]
    > Se você usar a estrutura, precisará remover manualmente as arquiteturas de simulador da estrutura universal antes de enviar seu aplicativo à App Store. Veja a seção "Enviando seu aplicativo à App Store".

2. Adicione as seguintes estruturas de iOS ao projeto:
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.dylib
    * libc++.dylib
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework

    > [!NOTE]
    > Se o aplicativo se destinar ao iOS 7, defina o atributo `Status` de `LocalAuthentication.framework` como Opcional. Se `Status` não for definido, o lançamento do aplicativo no iOS 7 falhará.
    >
    > Além disso, o Xcode 7 mudou as extensões `.dylib` para `.tbd`.

3. Adicione o pacote de recursos `IntuneMAMResources.bundle` ao projeto arrastando-o para **Copiar Recursos do Pacote** em **Fases de Build**.
![SDK de Aplicativo do Intune para iOS: copiar recursos do pacote](../media/intune-app-sdk-ios-copy-bundle-resources.png)

4. Adicione `-force_load {PATH_TO_LIB}/libIntuneMAM.a` a um dos seguintes, substituindo `{PATH_TO_LIB}` pelo local do SDK do Intune App:
    * A definição de configuração de build `OTHER_LDFLAGS` do projeto
    * Os **Outros Sinalizadores do Vinculador** da interface do usuário<br>

    > [!NOTE]
    > Para encontrar `PATH_TO_LIB`, selecione o arquivo `libIntuneMAM.a` e escolha **Obter Informações** no menu **Arquivo**. Copie e cole as informações **Onde** (o caminho) da seção **Geral** da janela **Informações**.

5. Se seu aplicativo móvel definir um Nib ou Storyboard principal em seu Info.plist, remova os campos do arquivo **Storyboard Principal** ou **Nib Principal**. Adicione os valores de storyboard ou nib removidos anteriormente a um novo dicionário chamado IntuneMAMSettings com os seguintes nomes de chave, conforme aplicável:
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

7. Depois que você habilitar o compartilhamento de conjunto de chaves, siga estas etapas para criar um grupo de acesso separado no qual os dados do SDK de Aplicativo do Intune serão armazenados. Você pode criar um grupo de acesso do conjunto de chaves usando a interface do usuário ou o arquivo de direitos.

    Se você estiver usando a interface do usuário para criar um grupo de acesso do conjunto de chaves:

    a. Se seu aplicativo móvel não tiver grupos de acesso do conjunto de chaves definidos, adicione a ID do pacote do aplicativo como o primeiro grupo.

    b. Adicione o grupo de conjunto de chaves compartilhado `com.microsoft.intune.mam`. Este grupo de acesso é usado pelo SDK de Aplicativo do Intune para armazenar dados.

    c. Adicione `com.microsoft.adalcache` a seus grupos de acesso existentes.

    ![SDK de Aplicativo do Intune para iOS: compartilhamento de conjunto de chaves](../media/intune-app-sdk-ios-keychain-sharing.png)

    Se você estiver usando o arquivo de direitos para criar o grupo de acesso do conjunto de chaves, você precisará acrescentar `$(AppIdentifierPrefix)` no início do arquivo de direito do grupo de acesso de conjunto de chaves. Por exemplo:  

    * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
    * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    > [!NOTE]
    > Um arquivo de direitos é um arquivo XML que é exclusivo para seu aplicativo móvel. Ele é usado para especificar funcionalidades e permissões especiais em seu aplicativo iOS.

8. Se o aplicativo definir esquemas de URL em seu arquivo info.plist, adicione outro esquema com um sufixo `-intunemam` a cada esquema de URL.

9. Para aplicativos móveis desenvolvidos no iOS 9 e posterior, inclua todos os protocolos que o aplicativo passar para `UIApplication canOpenURL` na matriz `LSApplicationQueriesSchemes` do arquivo Info.plist do aplicativo. Além disso, para cada protocolo listado, adicione um novo protocolo e acrescente `-intunemam` a ele. Você também deve incluir `http-intunemam`, `https-intunemam`e `ms-outlook-intunemam` na matriz.

10. Se o aplicativo tiver grupos de aplicativo definidos em seus direitos, adicione esses grupos ao dicionário IntuneMAMSettings sob a chave `AppGroupIdentifiers` como uma matriz de cadeias de caracteres.

11. Vincule seu aplicativo móvel à ADAL (Biblioteca de Autenticação do Diretório do Azure). A biblioteca ADAL para Objective-C está [disponível no GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    > [!NOTE]
    > O SDK de Aplicativo do Intune foi testado com o código da agência do agente ADAL de 19 de junho de 2015. Verifique se você está vinculando com a versão mais recente/de trabalho da biblioteca ADAL.

12. Inclua o pacote de recursos `ADALiOSBundle.bundle` no projeto arrastando-o para **Copiar Recursos do Pacote** em **Fases de Build**.

13. Use a opção do vinculador `-force_load PATH_TO_ADAL_LIBRARY` ao vincular para a biblioteca.

    Adicione `-force_load {PATH_TO_LIB}/libADALiOS.a` à definição de configuração de build `OTHER_LDFLAGS` do projeto ou **Outros Sinalizadores do Vinculador** na interface do usuário. `PATH_TO_LIB` deve ser substituído pelo local dos binários da ADAL.



## <a name="set-up-azure-directory-authentication-library"></a>Definir Biblioteca de Autenticação do Active Directory

O SDK de Aplicativo do Intune usa ADAL para seus cenários de inicialização condicional e autenticação. Ele também se baseia na ADAL para registrar a identidade do usuário no serviço de MAM para gerenciamento sem cenários de registro de dispositivo.

Normalmente, a ADAL requer que os aplicativos se registrem no Azure Active Directory (Azure AD) e obtenham uma ID exclusiva (conhecida como a ID do cliente), entre outros identificadores, para assegurar a segurança dos tokens concedidos ao aplicativo. O SDK de Aplicativo do Intune usa valores de registro padrão ao contatar o Azure AD.  

Se o aplicativo usa ADAL para seu cenário de autenticação, o aplicativo deve usar seus valores de registro existentes e substituir os valores padrão do SDK de Aplicativo do Intune. Isso garante que a autenticação não seja solicitada duas vezes dos usuários (uma vez pelo SDK de Aplicativo do Intune e uma vez pelo aplicativo).

### <a name="adal-faqs"></a>Perguntas frequentes sobre a ADAL

**Que binários da ADAL devo usar?**

Atualmente, o SDK de Aplicativo do Intune usa a ramificação do agente da [ADAL no GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-objc) para dar suporte a aplicativos que precisam de acesso condicional. (Esses aplicativos, portanto, dependem do aplicativo Microsoft Authenticator.) No entanto, o SDK é ainda compatível com a ramificação mestre da ADAL. Use a ramificação apropriada para seu aplicativo.

**Como vincular a binários da ADAL?**

Adicione `-force_load {PATH_TO_LIB}/libADALiOS.a` à definição de configuração de build `OTHER_LDFLAGS` do projeto ou **Outros Sinalizadores do Vinculador** na interface do usuário. `PATH_TO_LIB` deve ser substituído pelo local dos binários da ADAL. Além disso, certifique-se de copiar o pacote da ADAL para seu aplicativo.  

Para obter mais detalhes, veja as instruções de [ADAL no GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

**Como compartilhar o cache da ADAL com outros aplicativos assinados com o mesmo perfil de provisionamento?**

Se o seu aplicativo não tiver grupos de acesso do conjunto de chaves definidos, adicione a ID do pacote do aplicativo como o primeiro grupo.

Habilite o SSO (logon único) da ADAL adicionando os grupos de acesso `com.microsoft.adalcache` e `com.microsoft.workplacejoin` nos direitos do conjunto de chaves.

Caso você esteja definindo explicitamente o grupo de conjunto de chaves do cache compartilhado da ADAL, certifique-se de que ele seja definido como `<app_id_prefix>.com.microsoft.adalcache`. A ADAL definirá isso para você a menos que você faça uma substituição. Se você quiser especificar um grupo de conjunto de chaves personalizado para substituir `com.microsoft.adalcache`, especifique isso no arquivo Info.plist em "IntuneMAMSettings", usando a chave `ADALCacheKeychainGroupOverride`.

**Como posso forçar o SDK de Aplicativo do Intune a usar as configurações da ADAL que meu aplicativo já usa?**

Caso o aplicativo já use a ADAL, consulte [Definir as configurações do SDK do Aplicativo do Intune](#configure-settings-for-the-intune-app-sdk) para obter informações sobre como popular as seguintes configurações:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride


**Como posso substituir a URL de autoridade do Azure AD por uma URL específica do locatário fornecida no tempo de execução?**

Defina a propriedade `aadAuthorityUriOverride` na instância de IntuneMAMPolicyManager.

> [!NOTE]
> Você precisaria disso no cenário de MAM sem registro do dispositivo para permitir que o SDK reutilizasse o token de atualização do ADAL buscado pelo aplicativo.

O SDK continuará usando essa URL da autoridade para atualização da política e todas as solicitações de registro posteriores, a menos que o valor seja apagado ou alterado.  Portanto, é importante apagar o valor quando um usuário corporativo sai do aplicativo e redefini-lo quando um novo usuário corporativo entrar.

**O que devo fazer se o meu aplicativo usar a ADAL para autenticação?**

As etapas a seguir serão obrigatórias se o aplicativo já usar a ADAL para autenticação:

1. No arquivo Info.plist do projeto, no dicionário IntuneMAMSettings com o nome de chave `ADALClientId`, especifique a ID do cliente a ser usada para chamadas da ADAL.

2. Também no dicionário IntuneMAMSettings com o nome de chave `ADALAuthority`, especifique a autoridade do Azure AD.

3. Também no dicionário IntuneMAMSettings com o nome de chave `ADALRedirectUri`, especifique o URI de redirecionamento a ser usado para chamadas da ADAL. Você também precisa especificar o `ADALRedirectScheme` dependendo do formato de URI de redirecionamento do aplicativo.

**E se meu aplicativo ainda não usar ADAL para autenticação?**

Se seu aplicativo não usar a ADAL, o SDK de Aplicativo do Intune fornecerá valores padrão para parâmetros ADAL e lidará com a autenticação no Azure AD.

## <a name="register-your-app-with-the-intune-mam-service"></a>Registrar seu aplicativo no serviço MAM do Intune

### <a name="use-the-apis"></a>Usar as APIs
Agora, o SDK do Aplicativo do Intune oferece a capacidade de os aplicativos iOS receberem a política de proteção do aplicativo do Intune sem a necessidade de estarem registrados no Intune por meio do MDM (gerenciamento de dispositivo móvel). Para dar suporte a essa nova funcionalidade, o SDK fornece novas APIs que permitem que o aplicativo receba políticas de proteção do aplicativo. Para usar as novas APIs, siga estas etapas:

1. Use a versão mais recente do SDK de Aplicativo do Intune, que dá suporte ao gerenciamento de aplicativos com ou sem registro de dispositivo. .

2. Adicione IntuneMAMEnrollment.h a todos os arquivos que chamarão as APIs.

### <a name="register-accounts"></a>Registrar contas

Um aplicativo poderá receber a política de proteção do aplicativo do serviço do Intune se o aplicativo estiver registrado em nome de uma conta de usuário especificada. É responsabilidade do aplicativo registrar qualquer usuário conectado recentemente com o SDK de Aplicativo do Intune. Após a nova conta de usuário ser autenticada, o aplicativo deve chamar o método `registerAndEnrollAccount` encontrado em Headers/IntuneMAMEnrollment.h:

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

### <a name="deregister-accounts"></a>Cancelar o registro de contas

Antes que um usuário seja desconectado de um aplicativo, o aplicativo deve cancelar o registro do usuário do SDK. Isso garantirá que:

1. novas tentativas de registro na conta do usuário deixem de ser feitas.

2. Se o usuário tiver registrado o aplicativo com êxito, o registro do usuário e do aplicativo será cancelado do serviço de MAM do Intune e a política de proteção do aplicativo será removida.

3. Se o aplicativo iniciar um apagamento seletivo (opcional), todos os dados relacionados a trabalho ou a escola serão excluídos.

Antes que o usuário seja desconectado, o aplicativo deverá chamar a seguinte API em Headers/IntuneMAMEnrollment.h:

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

Esse método deve ser chamado antes que os tokens do Azure AD da conta do usuário sejam excluídos. O SDK precisa do token do aplicativo do usuário para fazer solicitações específicas ao serviço de MAM do Intune em nome do usuário.

Se o aplicativo for, por conta própria, excluir dados do usuário relacionados a trabalho ou escola, o sinalizador `doWipe` pode ser definido como falso. Caso contrário, o aplicativo pode fazer o SDK iniciar um apagamento seletivo. Isso resultará em uma chamada ao delegado de apagamento seletivo do aplicativo.

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

### <a name="enroll-without-prior-sign-in"></a>Registrar sem entrada anterior

Um aplicativo que não conecta o usuário ao Azure Active Directory ainda poderá receber a política de proteção do aplicativo do serviço do Intune pela chamada à API, para que o SDK manipule a autenticação. Os aplicativos deverão usar essa técnica quando não autenticaram um usuário ao Azure AD, mas ainda precisarem recuperar a política de proteção do aplicativo para ajudar a proteger os dados. Um exemplo é se outro serviço de autenticação estiver sendo usado para entrar no aplicativo ou se o aplicativo não oferecer nenhum suporte para entrar. Para fazer isso, o aplicativo deve chamar o método `loginAndEnrollAccount` em Headers/IntuneMAMEnrollment.h:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```

Ao chamar esse método, se nenhum token existente puder ser encontrado, o SDK solicitará credenciais ao usuário. O SDK tentará então registrar o aplicativo em nome dessa conta. O método pode ser chamado com "nulo" como a identidade. Nesse caso, o SDK fará o registro com o usuário de MAM existente no dispositivo ou solicitará que o usuário forneça um nome de usuário, se nenhum usuário existente for encontrado.

Se o registro falhar, o aplicativo deverá considerar chamar essa API novamente no futuro, dependendo dos detalhes da falha. O aplicativo pode receber notificações, por meio de um delegado, sobre os resultados das solicitações de registro.

Após essa API ser invocada, o aplicativo pode continuar funcionando normalmente. Se o registro for bem-sucedido, o SDK notificará o usuário se que uma reinicialização do aplicativo é necessária.

## <a name="status-result-and-debug-notifications"></a>Notificações de status, resultados e depuração

O aplicativo pode receber notificações de status, resultados e depuração sobre as seguintes solicitações ao serviço de MAM do Intune:

 - Solicitações de registro
 - Solicitações de atualização de políticas
 - Solicitações de cancelamento de registro

As notificações são apresentadas por meio de métodos delegados em Headers/IntuneMAMEnrollmentDelegate.h:

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

Esse objeto é definido em IntuneMAMEnrollmentStatus.h, em conjunto com os códigos de status específicos que podem ser retornados.




### <a name="sample-code"></a>Código de exemplo

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

## <a name="app-restart"></a>Reinicialização do aplicativo

Quando um aplicativo recebe políticas de proteção do aplicativo pela primeira vez, ele deve ser reiniciado para que os ganchos obrigatórios sejam aplicados. Para notificar o aplicativo de que uma reinicialização precisa ocorrer, o SDK fornece um método delegado em Headers/IntuneMAMPolicyDelegate.h.

```objc
 - (BOOL) restartApplication
```
O valor retornado desse método informa o SDK se o aplicativo realizará a reinicialização necessária:   

 - Se true for retornado, o aplicativo realizará a reinicialização.   

 - Se false for retornado, o SDK reiniciará o aplicativo depois que o método retornar. O SDK mostrará imediatamente uma caixa de diálogo informando ao usuário para reiniciar o aplicativo.

## <a name="customize-your-apps-behavior"></a>Personalizar o comportamento do aplicativo

O SDK do Aplicativo do Intune contém várias APIs que podem ser chamadas para obter informações sobre a política de proteção do aplicativo do Intune implantada no aplicativo. É possível usar esses dados para personalizar o comportamento do aplicativo. A maioria das configurações de política de proteção do aplicativo é imposta automaticamente pelo SDK e não pelo aplicativo. A única configuração que o aplicativo deve implementar é o controle Salvar como.

### <a name="get-the-app-protection-policy-settings"></a>Obter as configurações de política de proteção do aplicativo

#### <a name="intunemampolicymanagerh"></a>IntuneMAMPolicyManager.h
A classe IntuneMAMPolicyManager expõe a política de proteção do aplicativo do Intune implantada no aplicativo. Particularmente, ela expõe APIs que são úteis para [habilitar várias identidades](#-enable-multi-identity-optional).

#### <a name="intunemampolicyh"></a>IntuneMAMPolicy.h
A classe IntuneMAMPolicy expõe a política de proteção do aplicativo do Intune implantada no aplicativo. A maioria das configurações de política expostas nessa classe é aplicada pelo SDK, mas sempre é possível personalizar o comportamento do aplicativo de acordo com a forma de imposição das configurações de política.

Essa classe expõe algumas APIs necessárias para implementar controles salvar como, detalhadas na próxima seção.

### <a name="implement-save-as-controls"></a>Implementar controles salvar como

O Intune permite que os administradores de TI selecionem em quais locais de armazenamento um aplicativo gerenciado pode salvar dados. Os aplicativos podem consultar o SDK do Aplicativo do Intune quanto aos locais de armazenamento permitidos usando a API **isSaveToAllowedForLocation**, definida em **IntuneMAMPolicy.h**.

Antes que os aplicativos possam salvar dados gerenciados em um armazenamento em nuvem ou localmente, eles devem consultar a API **isSaveToAllowedForLocation** para saber se o administrador de TI permitiu que os dados fossem salvos no local em questão.

Quando os aplicativos usarem a API **isSaveToAllowedForLocation**, deverão passar o UPN para o local de armazenamento, se estiver disponível.

#### <a name="supported-save-locations"></a>Locais de salvamento com suporte

A API **isSaveToAllowedForLocation** fornece constantes para verificar se o administrador de TI permite que os dados sejam salvos nos seguintes locais definidos em IntuneMAMPolicy.h:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationBox
* IntuneMAMSaveLocationDropbox
* IntuneMAMSaveLocationGoogleDrive
* IntuneMAMSaveLocationLocalDrive

Os aplicativos devem usar as constantes na API **isSaveToAllowedForLocation** para verificar se os dados podem ser salvos em locais considerados "gerenciados" como o OneDrive for Business ou "pessoal". Além disso, a API deve ser usada quando o aplicativo não pode verificar se um local é "gerenciado" ou "pessoal".

Os locais conhecidos como “pessoais” são representados pela constante `IntuneMAMSaveLocationOther`.

A constante `IntuneMAMSaveLocationLocalDrive` deve ser usada quando o aplicativo salva dados em qualquer local no dispositivo local.

## <a name="configure-settings-for-the-intune-app-sdk"></a>Definir as configurações do SDK do Aplicativo do Intune

O dicionário **IntuneMAMSettings** é usado no arquivo Info.plist do aplicativo para configurar o SDK do Aplicativo do Intune. A tabela a seguir lista todas as configurações com suporte.

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
MAMPolicyRequired| Booliano| Especifica se a inicialização do aplicativo será impedida se ele não tiver uma política de proteção do aplicativo do Intune. O padrão é NÃO. <br><br> Observação: os aplicativos não podem ser enviados para a Loja de Aplicativos com MAMPolicyRequired definido como SIM. | Opcional. |
MAMPolicyWarnAbsent | Booliano| Especifica se o aplicativo alertará o usuário durante a inicialização se ele não tiver uma política de proteção do aplicativo do Intune. Observe que aplicativos não podem ser enviados para a loja com essa configuração definida como SIM. | Opcional. |
MultiIdentity | Booliano| Especifica se o aplicativo reconhece ou não várias identidades. | Opcional. |
SplashIconFile <br>SplashIconFile ~ ipad | Cadeia de caracteres  | Especifica o arquivo de ícone de abertura (inicialização) do Intune. | Opcional. |
SplashDuration | Número | Quantidade mínima de tempo em segundos pelo qual a tela inicial do Intune será exibida ao iniciar o aplicativo. O padrão é 1,5. | Opcional. |
BackgroundColor| Cadeia de caracteres| Especifica a cor da tela de fundo para as telas de inicialização e de PIN. Aceita uma cadeia de caracteres hexadecimal RGB no formato "#XXXXXX", em que os X pode variar de 0 a 9 ou de A a F. O sinal de libra pode ser omitido.   | Opcional. Opcional; o padrão é cinza claro. |
ForegroundColor| Cadeia de caracteres| Especifica a cor de primeiro plano para as telas de inicialização e de PIN como a cor do texto. Aceita uma cadeia de caracteres hexadecimal RGB no formato "#XXXXXX", em que os X pode variar de 0 a 9 ou de A a F. O sinal de libra pode ser omitido.  | Opcional. O padrão é preto. |
AccentColor | Cadeia de caracteres| Especifica a cor de destaque de tela de PIN como a cor da caixa de texto e a cor de destaque da caixa. Aceita uma cadeia de caracteres hexadecimal RGB no formato "#XXXXXX", em que os X pode variar de 0 a 9 ou de A a F. O sinal de libra pode ser omitido.| Opcional. Opcional; o padrão é azul. |
MAMTelemetryDisabled| Booliano| Especifica se o SDK não enviará dados de telemetria para seu back-end.| Opcional. |

> [!NOTE]
> Se o aplicativo for liberado para a Loja de Aplicativos, `MAMPolicyRequired` deverá ser definido como “NÃO”, conforme os padrões da Loja de Aplicativos.

## <a name="telemetry"></a>Telemetria

Por padrão, o SDK do Aplicativo do Intune para iOS registra dados de telemetria nos eventos de uso a seguir. Esses dados são enviados para o Microsoft Intune.

* **Inicialização do aplicativo**: para ajudar o Microsoft Intune a obter informações sobre o uso de aplicativos habilitados para MAM por tipo de gerenciamento (MAM com MDM, MAM sem registro de MDM etc.).

* **Chamadas de registro**: para ajudar o Microsoft Intune a obter informações sobre a taxa de sucesso e outras métricas de desempenho de chamadas de registro iniciadas do lado do cliente.

> [!NOTE]
> Se optar por não enviar dados de telemetria do SDK de Aplicativo do Intune para o Microsoft Intune do seu aplicativo móvel, você deverá desabilitar a captura de telemetria pelo SDK de Aplicativo do Intune. Defina a propriedade `MAMTelemetryDisabled` como SIM no dicionário IntuneMAMSettings.

## <a name="enable-multi-identity-optional"></a>Habilitar várias identidades (opcional)

Por padrão, o SDK aplica a política ao aplicativo como um todo. Várias identidades é um recurso do MAM que você pode habilitar para aplicar uma política em um nível por identidade. Ele requer mais participação do aplicativo do que outros recursos de MAM.

O aplicativo precisa informar ao SDK de aplicativo quando pretende alterar a identidade ativa. O SDK também notificará o aplicativo quando uma alteração de identidade for necessária. Atualmente, há suporte para apenas uma identidade gerenciada. Depois que o usuário registrar o dispositivo ou o aplicativo, o SDK usará essa identidade e a considerará a identidade gerenciada primária. Outros usuários no aplicativo serão tratados como não gerenciados, com configurações de política irrestritas.

Observe que uma identidade é definida simplesmente como uma cadeia de caracteres. As identidades não diferenciam maiúsculas de minúsculas. As solicitações de identidade ao SDK podem não retornar o mesmo esquema de maiúsculas e minúsculas usado originalmente ao definir a identidade.

### <a name="identity-overview"></a>Visão geral de identidade

Uma identidade é simplesmente o nome de usuário de uma conta (por exemplo, user@contoso.com). Os desenvolvedores podem definir a identidade do aplicativo nos níveis a seguir:

* **Identidade de processo**: define a identidade de todo o processo e é usada principalmente para aplicativos de identidade única. Essa identidade afeta todas as tarefas, arquivos e a interface do usuário.

* **Identidade de interface do usuário**: determina quais políticas são aplicadas às tarefas de interface do usuário no thread principal, como recortar/copiar/colar, PIN, autenticação e compartilhamento de dados. A identidade de interface do usuário não afeta as tarefas de arquivo como criptografia, backup etc.

* **Identidade de thread**: a identidade de thread afeta quais políticas são aplicadas no thread atual. Essa identidade afeta todas as tarefas, arquivos e a interface do usuário.

É responsabilidade do aplicativo definir as identidades adequadamente, quer o usuário seja gerenciado ou não.

A qualquer momento, todo thread tem uma identidade efetiva para tarefas de interface do usuário e tarefas de arquivo. Essa é a identidade usada para verificar quais políticas, se houver, devem ser aplicadas. Se a identidade for "nenhuma identidade" ou o usuário não for gerenciado, nenhuma política será aplicada. Os diagramas abaixo mostram como as identidades efetivas são determinadas.

  ![SDK do Aplicativo do Intune para iOS: estruturas e bibliotecas vinculadas](../media/intune-app-sdk/ios-thread-identities.png)

### <a name="thread-queues"></a>Filas de thread

Frequentemente, os aplicativos expedem tarefas síncronas e assíncronas para filas de thread. O SDK intercepta chamadas de GCD (Grand Central Dispatch) e associa a identidade do thread atual às tarefas expedidas. Quando as tarefas são concluídas, o SDK altera temporariamente a identidade do thread para a identidade associada às tarefas, conclui as tarefas e restaura a identidade do thread original.


Como `NSOperationQueue` é criado sobre o GCD, `NSOperations` será executado na identidade do thread no momento em que as tarefas forem adicionadas ao `NSOperationQueue`. O `NSOperations` ou funções expedidas diretamente usando o GCD também têm a capacidade de alterar a identidade do thread atual conforme são executadas. Essa identidade substituirá a identidade herdada do thread de expedição.

### <a name="file-owner"></a>Proprietário do arquivo

O SDK acompanha as identidades dos proprietários do arquivo local e aplica políticas de acordo com elas. Um proprietário do arquivo é estabelecido quando o arquivo é criado ou quando é aberto no modo de truncamento. O proprietário é definido como a identidade de operação do arquivo efetivo do thread que executa a operação.

Como alternativa, os aplicativos podem definir a identidade do proprietário do arquivo explicitamente usando `IntuneMAMFilePolicyManager`. Os aplicativos podem usar o `IntuneMAMFilePolicyManager` para recuperar o proprietário do arquivo e definir a identidade da interface do usuário antes de mostrar o conteúdo do arquivo.

### <a name="shared-data"></a>Dados compartilhados

Se o aplicativo criar arquivos que contêm dados de usuários gerenciados e não gerenciados, será responsabilidade do aplicativo criptografar os dados do usuário gerenciado. Você pode criptografar dados usando as APIs `protect` e `unprotect` em `IntuneMAMDataProtectionManager`.

O método `protect` aceita uma identidade que pode ser um usuário gerenciado ou não gerenciado. Se o usuário for gerenciado, os dados serão criptografados. Se o usuário não for gerenciado, um cabeçalho será adicionado aos dados codificando a identidade, mas os dados não serão criptografados. O método `protectionInfo` pode ser usado para recuperar o proprietário dos dados.

### <a name="share-extensions"></a>Extensões de compartilhamento

Se o aplicativo contiver uma Extensão de compartilhamento, o proprietário do item sendo compartilhado poderá ser recuperado usando o método `protectionInfoForItemProvider` em `IntuneMAMDataProtectionManager`. Se o item compartilhado for um arquivo, o SDK processará a definição do proprietário do arquivo. Se o item compartilhado forem dados, o aplicativo será responsável por definir o proprietário do arquivo se esses dados forem persistidos em um arquivo; será responsável também por chamar a API `setUIPolicyIdentity` antes de mostrar esses dados na interface do usuário.

### <a name="turning-on-multi-identity"></a>Ligar várias identidades

Por padrão, considera-se que todos os aplicativos são aplicativos de identidade única. O SDK define a identidade do processo para o usuário registrado. Para habilitar o suporte a várias identidades, uma configuração booliana com o nome `MultiIdentity` e o valor YES deve ser adicionada ao dicionário IntuneMAMSettings no arquivo Info.plist do aplicativo.

> [!NOTE]
> Quando o recurso várias identidades estiver habilitado, a identidade do processo, identidade da interface do usuário e identidades de thread serão definidas como nulas. O aplicativo é responsável por defini-las adequadamente.

### <a name="switching-identities"></a>Alternando identidades

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

## <a name="debug-the-intune-app-sdk-in-xcode"></a>Depurar o SDK do Aplicativo do Intune no Xcode

Antes de testar manualmente seu aplicativo habilitado para MAM com o Microsoft Intune, você pode usar um arquivo de pacote Settings.bundle enquanto estiver no Xcode. Isso permitirá que você defina políticas de teste sem a necessidade de uma conexão com o Intune. Para habilitar:

1. Adicione um arquivo Settings.bundle clicando com o botão direito do mouse na pasta de nível superior no seu projeto. Selecione **Adicionar** > **Novo Arquivo** no menu. Em **Recursos**, selecione o modelo de **Pacote de Configurações** a adicionar.

2. Em compilações somente de depuração, copie MAMDebugSettings.plist para Settings.bundle.

3. No Root.plist (que é Settings.bundle), adicione uma preferência com `Type` = `Child Pane` e `FileName` = `MAMDebugSettings`.

4. Em **Configurações** > **Nome do Seu Aplicativo**, habilite **Habilitar Políticas de Teste**.

5. Inicie o aplicativo (dentro ou fora do Xcode).

6. Em **Configurações** > **Nome do Seu Aplicativo** > **Habilitar Políticas de Teste**, habilite uma política, por exemplo, **PIN**.

7. Inicie o aplicativo (dentro ou fora do Xcode). Verifique se o PIN funciona conforme o esperado.

> [!NOTE]
> Agora você pode usar **Configurações** > **Nome do Seu Aplicativo** > **Habilitar Políticas de Teste** para habilitar e mudar configurações.

## <a name="ios-best-practices"></a>Melhores práticas de iOS

A seguir estão algumas melhores práticas para o desenvolvimento para iOS:

* O sistema de arquivos iOS diferencia maiúsculas de minúsculas. Certifique-se de que o caso está correto para nomes de arquivo como `libIntuneMAM.a` e `IntuneMAMResources.bundle`.

* Se o Xcode tiver problemas para encontrar `libIntuneMAM.a`, você pode corrigir o problema adicionando o caminho para essa biblioteca aos caminhos de pesquisa do vinculador.

## <a name="faq"></a>Perguntas Frequentes


**Todas as APIs são endereçáveis pelo Swift nativo ou pela interoperabilidade Objective-C e Swift?**

As APIs do SDK do aplicativo Intune estão apenas em objective-C e não dão suporte ao Swift nativo.  


**Todos os usuários do meu aplicativo precisam estar registrados no serviço de MAM?**

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



## <a name="submit-your-app-to-the-app-store"></a>Enviar seu aplicativo à App Store

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

