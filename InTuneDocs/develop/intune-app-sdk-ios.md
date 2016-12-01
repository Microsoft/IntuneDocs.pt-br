---
title: Guia de Desenvolvedor do SDK de Aplicativo do Microsoft Intune para iOS | Microsoft Intune
description: 
keywords: 
author: Msmbaldwin
manager: angrobe
ms.author: oydang
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 018faada59819938d443605a454465a38600c9a4
ms.openlocfilehash: f44d2a43c6717c9b3adde9ba49a54e014f4e3528


---

# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>SDK do Microsoft Intune App para o Guia do Desenvolvedor do iOS

> [!NOTE]
> Primeiro, leia o artigo [Introdução ao SDK de Aplicativo do Intune](intune-app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.

## <a name="overview"></a>Visão geral

O SDK de Aplicativo do Microsoft Intune para iOS permite incorporaras políticas de proteção do aplicativo do Intune ao seu aplicativo iOS. Um aplicativo habilitado para MAM é integrado ao SDK de Aplicativo do Intune e permite que administradores de TI implantem políticas em seu aplicativo móvel quando o aplicativo for gerenciado ativamente pelo MAM (gerenciamento de aplicativo móvel) do Intune.


## <a name="prerequisites"></a>Pré-requisitos

* Você precisará de um computador Mac OS que executa o OS X 10.8.5 ou posterior e tenha a versão 5 ou posterior do conjunto de ferramentas XCode instalada.

* Examinar os [Termos de Licença do SDK de Aplicativo do Intune para iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Imprimir e guardar uma cópia dos termos de licença para seus registros. Ao baixar e usar o SDK de Aplicativo do Intune para iOS, você concorda com esses termos de licença.  Se você não aceitá-los, não use o software.


## <a name="whats-in-the-sdk"></a>Novidades no SDK

O SDK do Intune App para iOS inclui uma biblioteca estática, arquivos de recursos, cabeçalhos de API, um plist de configurações de Depuração e uma ferramenta do configurador. Aplicativos móveis podem simplesmente incluir os arquivos de recursos e um link estático para as bibliotecas para a maioria das imposições de política. Recursos de MAM avançados do Intune são aplicados por meio de APIs.

Este guia aborda o uso dos seguintes componentes do SDK do Aplicativo do Intune para iOS:

* **libIntuneMAM.a**: a biblioteca estática do SDK do Aplicativo do Intune. Se o aplicativo não usar extensões, vincule essa biblioteca ao seu projeto para habilitar a aplicativo para o gerenciamento de aplicativo móvel do Intune. As instruções são encontradas na seção "Criando seu aplicativo com o SDK do Intune App".

* **IntuneMAM.framework**: a estrutura do SDK do Aplicativo do Intune. Vincule essa estrutura ao seu projeto para habilitar a aplicativo para o gerenciamento de aplicativo móvel do Intune. Use a estrutura em vez da biblioteca estática se seu aplicativo usar extensões, para que o projeto não crie várias cópias da biblioteca estática.

* **IntuneMAMResources.bundle**: um pacote de recursos que contém recursos usados pelo SDK.

* **Cabeçalhos**: expõe as APIs do SDK do Intune App. Se você usar uma API, precisará incluir o arquivo de cabeçalho que contém a API. Os seguintes arquivos de cabeçalho incluem as chamadas de função de API necessárias para habilitar a funcionalidade do SDK do Aplicativo do Intune.

    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h


## <a name="how-the-intune-app-sdk-works"></a>Como o SDK de Aplicativos do Intune funciona

O objetivo do SDK do Intune APP para iOS é adicionar recursos de gerenciamento de aplicativos a aplicativos iOS com alterações mínimas de código. Quanto menos alterações houver no código, menor será o tempo de chegada no mercado, mas a consistência e a estabilidade do aplicativo móvel ainda são garantidas.

O aplicativo precisa estar vinculado à biblioteca estática e deve incluir o pacote de recursos. O arquivo MAMDebugSettings.plist é opcional e pode ser incluído no pacote para simular políticas de MAM sendo aplicadas ao aplicativo sem a necessidade de implantá-lo por meio do Microsoft Intune. Além disso, em builds de depuração, as políticas no arquivo MAMDebugSettings.plist podem ser aplicadas ao transferir o arquivo para diretório de Documentos do aplicativo por meio do compartilhamento de arquivos do iTunes.

## <a name="building-the-sdk-into-your-mobile-app"></a>Incorporando o SDK ao seu aplicativo móvel

Conclua as etapas a seguir para habilitar o SDK do Intune App:

1. **Opção 1**: vincular à biblioteca `libIntuneMAM.a` fazendo o seguinte:

    Arraste e solte a biblioteca `libIntuneMAM.a` na lista "Estruturas e Bibliotecas Vinculadas" do projeto de destino.

    ![SDK de Aplicativos do Intune para iOS - estruturas e bibliotecas vinculadas](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    **Observação**: se você planeja lançar o aplicativo na App Store, use a versão de `libIntuneMAM.a` criada para a versão de lançamento e não para a versão de depuração. A versão de lançamento estará na pasta "lançamento". A versão de depuração tem saída detalhada, o que ajuda a solucionar problemas com o SDK do Aplicativo do Intune.

    **Opção 2**: vincular `IntuneMAM.framework` ao seu projeto. Arraste e solte `IntuneMAM.framework` na lista "Estruturas e Bibliotecas Vinculadas" do projeto de destino.

    **Observação**: se usar a estrutura, você precisará remover manualmente as arquiteturas de simulador da estrutura universal antes de enviar seu aplicativo à App Store. Consulte a seção chamada "Enviando seu aplicativo à App Store".

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

    **Observação**: se o aplicativo se destinar ao iOS 7, defina o atributo “Status” de `LocalAuthentication.framework` como "Opcional". Se “Status” não for definido, o lançamento do aplicativo no iOS 7 falhará.

    **Observação**: o Xcode 7 mudou as extensões `.dylib` para `.tbd`.

3. Adicione o pacote de recursos `IntuneMAMResources.bundle` ao projeto arrastando-o para "Copiar Recursos do Pacote” em “Fases de Build”.
![SDK de Aplicativo do Intune para iOS – copiar recursos do pacote](../media/intune-app-sdk-ios-copy-bundle-resources.png)

4. Adicione `-force_load {PATH_TO_LIB}/libIntuneMAM.a` a um dos seguintes, substituindo `{PATH_TO_LIB}` pelo local do SDK do Intune App:
    * a definição de configuração de build `OTHER_LDFLAGS` do projeto
    * as “Outros Sinalizadores do Vinculador” da interface do usuário<br>

    **Observação**: para encontrar `PATH_TO_LIB`, selecione o arquivo `libIntuneMAM.a` e escolha “Obter Informações” no menu “Arquivo”. Copie e cole as informações “Onde” (o caminho) da seção “Geral” da janela “Informações”.

5. Se seu aplicativo móvel definir um Nib ou Storyboard principal em seu Info.plist, remova os campos do arquivo Storyboard Principal ou Nib Principal. Adicione os valores de Storyboard ou Nib removidos anteriormente a um novo dicionário chamado IntuneMAMSettings com os seguintes nomes de chave, conforme aplicável:
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad

   **Observação**: se seu aplicativo móvel não definir um Nib ou Storyboard em seu Info.plist, essas configurações **não serão obrigatórias**.

    **Observação**: você pode exibir o Info.plist em formato bruto (para ver os nomes de chave) clicando com o botão direito do mouse em qualquer lugar do corpo do documento e alterando o tipo de exibição para "Mostrar Chaves/Valores Brutos".

6. Habilite o compartilhamento de conjunto de chaves (se já não estiver habilitado) clicando em “Funcionalidades” em cada destino do projeto e habilitando a opção "Compartilhamento de Conjunto de Chaves". O compartilhamento de conjunto de chaves é necessário para prosseguir para a próxima etapa.

    **Observação**: o perfil de provisionamento precisa dar suporte aos novos valores de compartilhamento de conjunto de chaves. Os grupos de acesso do conjunto de chaves devem dar suporte a um caractere curinga. Você pode verificar isso abrindo o arquivo .mobileprovision em um editor de texto, pesquisando por “keychain-access-groups” e incluindo um curinga, como:
    ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```
7. Depois de habilitar o compartilhamento de conjunto de chaves, siga estas etapas para criar um grupo de acesso separado no qual os dados do SDK do Intune App serão armazenados. Você pode criar um grupo de acesso do conjunto de chaves usando a interface do usuário ou o arquivo de direitos:

    Usando a interface do usuário para criar um grupo de acesso do conjunto de chaves:

    * Se seu aplicativo móvel não tiver grupos de acesso do conjunto de chaves definidos, adicione a ID do pacote do aplicativo como o primeiro grupo.
    * Adicione o grupo de conjunto de chaves compartilhado `com.microsoft.intune.mam`. Este grupo de acesso é usado pelo SDK do Intune App para armazenar dados.  
    * Adicione `com.microsoft.adalcache` a seus grupos de acesso existentes.

    ![SDK do Intune App para iOS - compartilhamento de conjunto de chaves](../media/intune-app-sdk-ios-keychain-sharing.png)

    Se você estiver usando o arquivo de direitos para criar o grupo de acesso do conjunto de chaves, em vez de interface do usuário regular, você precisará acrescentar `$(AppIdentifierPrefix)` no início do arquivo de direito do grupo de acesso de conjunto de chaves. Por exemplo:  
    * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
    * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    **Observação**: um arquivo de direitos é um arquivo XML exclusivo ao seu aplicativo móvel que é usado para especificar permissões especiais e recursos em seu aplicativo iOS.

8. Se o aplicativo definir esquemas de URL em seu arquivo info.plist, adicione outro esquema com um sufixo `-intunemam` a cada esquema de URL.

9. Para aplicativos móveis desenvolvidos para iOS 9+, é necessário incluir cada protocolo que seu aplicativo móvel passar a `UIApplication canOpenURL` na matriz `LSApplicationQueriesSchemes` do arquivo Info.plist do seu aplicativo móvel. Além disso, para cada protocolo listado, um novo protocolo precisa ser adicionado e precedido com `-intunemam`. Você também deve incluir `http-intunemam`, `https-intunemam`e `ms-outlook-intunemam` na matriz.

10. Se o aplicativo tiver grupos de aplicativo definidos em seus direitos, adicione esses grupos ao dicionário IntuneMAMSettings sob a chave `AppGroupIdentitifiers` como uma matriz de cadeias de caracteres.

11. Vincule seu aplicativo móvel à ADAL (Biblioteca de Autenticação do Diretório do Azure). A biblioteca ADAL para Objetivo C está [disponível no GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **Observação**: o SDK do Intune App foi testado com o código da agência do agente ADAL de 19/06/2015. Verifique se você está vinculando com a versão mais recente/de trabalho da biblioteca ADAL.

12. Inclua o pacote de recursos `ADALiOSBundle.bundle` no projeto arrastando-o para "Copiar Recursos do Pacote” em “Fases de Build”.

13. Use a opção do vinculador `-force_load PATH_TO_ADAL_LIBRARY` ao vincular para a biblioteca.

    Adicione `-force_load {PATH_TO_LIB}/libADALiOS.a` à definição de configuração de build `OTHER_LDFLAGS` do projeto ou “Outros Sinalizadores do Vinculador” na interface do usuário. `PATH_TO_LIB` deve ser substituído pelo o local dos binários da ADAL.

## <a name="configure-azure-directory-authentication-library-adal"></a>Configurar a ADAL (Biblioteca de Autenticação do Active Directory)

O SDK de Aplicativo do Intune usa a ADAL para cenários de inicialização e autenticação condicional. Ele também se baseia na ADAL para registrar a identidade do usuário no serviço de MAM para gerenciamento sem cenários de registro de dispositivo.

Normalmente, a ADAL requer que os aplicativos se registrem no [Azure Active Directory] e obtenham uma ID exclusiva, conhecida como ClientID, entre outros identificadores, para assegurar a segurança dos tokens concedidos ao aplicativo. O SDK do Intune App usa valores de registro padrão ao contatar o Active Directory do Azure.  

Se o próprio aplicativo usar a ADAL para seu cenário de autenticação, ele deverá usar seus valores de registro existentes e substituir os valores padrão do SDK do Intune App para que não seja solicitada a autenticação dos usuários finais duas vezes (uma vez pelo SDK do Intune App e outra pelo aplicativo).

### <a name="adal-faqs"></a>Perguntas frequentes sobre a ADAL

**Que binários da ADAL devo usar?**

Atualmente, o SDK do Intune App usa a ramificação do agente da [ADAL no GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-objc) para dar suporte a aplicativos que precisam de Acesso condicional (aplicativos que, portanto, dependem do aplicativo Microsoft Authenticator). No entanto, o SDK é ainda compatível com a ramificação mestre da ADAL. Use a ramificação apropriada para seu aplicativo.

**Como vincular a binários da ADAL?**

Adicione `-force_load {PATH_TO_LIB}/libADALiOS.a` à definição de configuração de build `OTHER_LDFLAGS` do projeto ou “Outros Sinalizadores do Vinculador” na interface do usuário. `PATH_TO_LIB` deve ser substituído pelo o local dos binários da ADAL. Além disso, certifique-se de copiar o pacote da ADAL para seu aplicativo.  

Para obter mais detalhes, consulte as instruções sobre a [ADAL no Github](https://github.com/AzureAD/azure-activedirectory-library-for-objc).


**Como compartilhar o cache da ADAL com outros aplicativos assinados com o mesmo perfil de provisionamento?**

Se o seu aplicativo não tiver grupos de acesso do conjunto de chaves definidos, adicione a ID do pacote do aplicativo como o primeiro grupo.
Habilite o SSO da ADAL adicionando os grupos de acesso `com.microsoft.adalcache` e `com.microsoft.workplacejoin` nos direitos do conjunto de chaves.

Caso você esteja definindo explicitamente o grupo de conjunto de chaves do cache compartilhado da ADAL, certifique-se de que ele seja definido como `<app_id_prefix>.com.microsoft.adalcache`. A ADAL definirá isso para você a menos que você faça uma substituição. Se você quiser especificar um grupo de conjunto de chaves personalizado para substituir `com.microsoft.adalcache`, especifique isso no arquivo Info.plist em "IntuneMAMSettings", usando a chave `ADALCacheKeychainGroupOverride`.

**Como posso forçar o SDK de Aplicativo do Intune a usar as configurações da ADAL que meu aplicativo já usa?**

Se seu aplicativo já usa a ADAL, consulte a seção sobre IntuneMAMSettings abaixo para obter informações sobre como preencher as configurações a seguir:  

* ADALClientId
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

**Como mudar entre ambientes de teste internos e de produção do AAD?**

A configuração `AadAuthorityURI` em `MAMPolicies.plist` pode ser usada para especificar o ambiente do AAD usado para chamadas da ADAL. Atualmente, ela está definida para usar o PPE (Ambiente de pré-produção) do AAD por padrão, a menos que seja substituída.

Para fazer o teste no PPE, você pode usar uma opção de tempo de compilação ou tempo de execução.

Para uma opção de ambiente de tempo de compilação do AAD e de URLs do serviço de MAM, defina o sinalizador booliano `UsePPE` como verdadeiro em MAMEnvironment.plist (**Observação**: não há suporte para fazer isso pelo Info.plist).

Para uma opção de ambiente de tempo de execução, defina `com.microsoft.intune.mam.useppe` nos padrões do usuário padrão como "1" para usar o PPE. Isso substituirá a configuração `com.microsoft.intune.mam.AADAuthorityEnvironment` existente.

**Como posso substituir a URL de autoridade do AAD por uma URL específica do locatário fornecida no tempo de execução?**

Defina a propriedade `aadAuthorityUriOverride` na instância de IntuneMAMPolicyManager.

**Observação**: você precisaria disso no MAM sem o cenário de registro do dispositivo para permitir que o SDK reutilize o token de atualização do ADAL buscado pelo aplicativo.

**Observação:** o SDK continuará usando essa URL da autoridade para atualização da política e todas as solicitações de registro posteriores, a menos que o valor seja apagado ou alterado.  Portanto, é importante apagar o valor quando um usuário corporativo sai do aplicativo e redefini-lo quando um novo usuário corporativo voltar a entrar.


**O que devo fazer se o meu aplicativo usar a ADAL para autenticação?**

As etapas a seguir são obrigatórias se o aplicativo já usar a ADAL para autenticação. Se o seu aplicativo não se basear na ADAL, leia a seção sobre como se registrar no serviço Intune se o aplicativo não usar a ADAL.

* No Info.plist do projeto, no dicionário IntuneMAMSettings com o nome de chave `ADALClientId`, especifique a ClientID a ser usada para chamadas da ADAL.

* No Info.plist do projeto, no dicionário IntuneMAMSettings com o nome de chave `ADALRedirectUri`, especifique o URI de redirecionamento a ser usado para chamadas da ADAL. Você também precisa especificar o `ADALRedirectScheme` dependendo do formato de URI de redirecionamento do aplicativo.



## <a name="register-your-app-with-intune-mam-service"></a>Registrar seu aplicativo no serviço de MAM do Intune

### <a name="use-the-apis"></a>Usar as APIs
Agora, o SDK do Aplicativo do Intune oferece a capacidade de aplicativos iOS receberem políticas de MAM do Intune sem a necessidade de estarem registrados no MDM com o Intune. Para dar suporte a essa nova funcionalidade, o SDK fornece novas APIs que permitem que o aplicativo receba políticas de MAM. Para usar as novas APIs, conclua as seguintes etapas:

1. Use a versão mais recente do SDK do Intune App que dá suporte ao gerenciamento de aplicativos com ou sem registro de dispositivo. Se o seu aplicativo tiver usado uma versão mais antiga do SDK sem esse recurso, você precisará atualizar a biblioteca de MAM do Intune, bem como atualizar a pasta de Cabeçalhos com os cabeçalhos do SDK mais recente.

2. Adicione IntuneMAMEnrollment.h a todos os arquivos que chamarão as APIs

3. Para fazer o teste no PPE, você pode incluir uma opção de tempo de compilação ou tempo de execução.

    Para uma opção de ambiente de tempo de compilação do AAD e de URLs do serviço de MAM, defina o sinalizador booliano `UsePPE` como verdadeiro em MAMEnvironment.plist (**observação**: não há suporte para fazer isso pelo Info.plist).

    Para uma opção de ambiente de tempo de execução, defina `com.microsoft.intune.mam.useppe` nos padrões do usuário padrão como "1" para usar o PPE. Isso substituirá a configuração `com.microsoft.intune.mam.AADAuthorityEnvironment` existente.


### <a name="register-accounts"></a>Registrar contas

Um aplicativo pode receber políticas de MAM do serviço do Intune se o aplicativo estiver registrado em nome de uma conta de usuário especificada.  É responsabilidade do aplicativo registrar qualquer usuário conectado recentemente com o SDK do Intune App.  Após a nova conta de usuário ser autenticada, o aplicativo deve chamar o método `registerAndEnrollAccount` encontrado em **Headers/IntuneMAMEnrollment.h**:

```objc
/**


 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```
Chamando o método acima, o SDK registrará a conta de usuário e tentará registrar o aplicativo em nome dessa conta.  Se o registro falhar por algum motivo, o SDK automaticamente tentará realizar o registro novamente após 24 horas.  Para fins de depuração, o aplicativo pode receber notificações, por meio de um delegado, sobre os resultados das solicitações de registro (consulte os detalhes abaixo).

Após essa API ser invocada, o aplicativo pode continuar funcionando normalmente.  Se o registro for bem-sucedido, o SDK notificará o usuário se que uma reinicialização do aplicativo é necessária.  Nesse momento, o usuário poderá reiniciar o aplicativo imediatamente.


### <a name="de-register-accounts"></a>Cancelar o registro de contas


Antes que um usuário seja desconectado de um aplicativo, o aplicativo deve cancelar o registro do usuário do SDK.  Isso garantirá que:

1. novas tentativas de registro na conta do usuário deixem de ser feitas.
2. Se o usuário tiver registrado o aplicativo com êxito, o cancelamento do registro do usuário e do aplicativo será cancelado do Serviço de MAM do Intune e as políticas de MAM serão removidas.
3. Opcionalmente, um apagamento seletivo pode ser iniciado para garantir que todos os dados relacionados a trabalho ou a escola sejam excluídos.

Antes que o usuário seja desconectado, o aplicativo deverá chamar a seguinte API encontrada em **Headers/IntuneMAMEnrollment.h**:

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

Esse método deve ser chamado antes que os tokens do AAD da conta do usuário sejam excluídos.  O SDK precisa do token do aplicativo do usuário para fazer solicitações específicas ao Serviço de MAM do Intune em nome do usuário.

Se o aplicativo for, por conta própria, excluir dados do usuário relacionados a trabalho ou escola, o sinalizador `doWipe` pode ser definido como falso.  Caso contrário, o aplicativo pode fazer com que o SDK inicie um apagamento seletivo, o que resultará em uma chamada para o delegado de apagamento seletivo do aplicativo.

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```


## <a name="enrolling-without-prior-sign-in"></a>Registrar sem conexão anterior

Um aplicativo que não conectar o usuário ao Azure Active Directory ainda pode receber políticas de MAM do Serviço do Intune chamando a API abaixo para que o SDK processe a autenticação. Os aplicativos devem usar essa opção quando não tiverem autenticado um usuário no AAD, mas ainda precisarem recuperar políticas de MAM para proteger os dados em seu aplicativo. Por exemplo, se outro serviço de autenticação estiver sendo usado para logon do aplicativo ou se o aplicativo não der nenhum suporte para logon. Para fazer isso, o aplicativo deve chamar o método `loginAndEnrollAccount` encontrado em **Headers/IntuneMAMEnrollment.h**:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```
Ao chamar esse método, o SDK solicitará credenciais do usuário se nenhum token existente puder ser encontrado e, em seguida, tentará registrar o aplicativo em nome dessa conta. O método pode ser chamado com "nulo" como a identidade. Nesse caso, o SDK fará o registro com o usuário de MAM existente no dispositivo ou solicitará que o usuário forneça um nome de usuário, se nenhum usuário existente for encontrado.

Se o registro falhar, o aplicativo deverá considerar chamar essa API novamente no futuro, dependendo dos detalhes da falha. O aplicativo pode receber notificações, por meio de um delegado, sobre os resultados das solicitações de registro (consulte os detalhes).

Após essa API ser invocada, o aplicativo pode continuar funcionando normalmente.  Se o registro for bem-sucedido, o SDK notificará o usuário de que uma reinicialização do aplicativo é necessária, conforme mostrado na seção acima sobre o registro de contas.

## <a name="debug-information"></a>Informações de depuração

O aplicativo pode receber notificações de depuração sobre as seguintes solicitações ao Serviço de MAM do Intune:

 - Solicitações de registro
 - Solicitações de atualização de políticas
 - Cancelar o registro de solicitações

As notificações são apresentadas por meio de métodos delegados que podem ser encontrados em **Headers/IntuneMAMEnrollmentDelegate.h**:

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
- código de status indicando o resultado da solicitação
- uma cadeia de caracteres de erro com uma descrição do código de status
- um objeto NSError

Esse objeto é definido em **Headers/IntuneMAMEnrollmentStatus.h** em conjunto com os códigos de status específicos que podem ser retornados.

É importante observar que essas informações são destinadas a fins de depuração e nenhuma lógica de negócios do aplicativo deve se basear nessas notificações.  A ideia é que o aplicativo possa enviar essas informações para um serviço de telemetria para fins de depuração ou monitoramento.


## <a name="sample-code"></a>Código de exemplo

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

Quando um aplicativo receber políticas de MAM pela primeira vez, ele precisará ser reiniciado para aplicar os ganchos necessários.  Para notificar o aplicativo de que uma reinicialização precisa ocorrer, o SDK fornece um método delegado em **Headers/IntuneMAMPolicyDelegate.h**.
```objc
 - (BOOL) restartApplication
```
O valor de retorno desse método informa o SDK se o aplicativo realizará a reinicialização necessária.   

 - Se true for retornado, o aplicativo será responsável por realizar a reinicialização.   
 - Se false for retornado, o SDK reiniciará o aplicativo depois que o método retornar.  O SDK abrirá imediatamente uma caixa de diálogo informando o usuário de que o aplicativo precisa ser reiniciado.

## <a name="implementing-save-as-controls"></a>Implementar controles Salvar como

O Intune permite que os administradores de TI selecionem em quais locais de armazenamento um aplicativo gerenciado pode salvar dados. Os aplicativos podem consultar o SDK do Aplicativo do Intune quanto aos locais de armazenamento permitidos usando a API **isSaveToAllowedForLocation**.

Antes de salvar dados gerenciados em um armazenamento em nuvem ou localmente, os aplicativos devem consultar a API **isSaveToAllowedForLocation** para saber se o administrador de TI permitiu que os dados fossem salvos no local em questão.

Ao usar a API **isSaveToAllowedForLocation**, aplicativos devem passar o UPN usado para o local de armazenamento, se estiver disponível.

### <a name="supported-save-locations"></a>Locais de salvamento com suporte

A API **isSaveToAllowedForLocation** fornece constantes para verificar se o administrador de TI permite que os dados sejam salvos nos seguintes locais:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationBox
* IntuneMAMSaveLocationDropbox
* IntuneMAMSaveLocationGoogleDrive
* IntuneMAMSaveLocationLocalDrive

Os aplicativos devem usar as constantes na API **isSaveToAllowedForLocation** para verificar se os dados podem ser salvos em locais considerados "gerenciados" como o OneDrive for Business ou "pessoal". Além disso, a API deve ser usada quando o aplicativo não pode determinar se um local é "gerenciado" ou "pessoal".

Quando se sabe que um local é "pessoal", os aplicativos devem usar o valor **IntuneMAMSaveLocationOther**.

A constante **IntuneMAMSaveLocationLocalDrive** deve ser usada quando o aplicativo está salvando dados em qualquer local no dispositivo local.



## <a name="configure-intune-app-sdk-settings"></a>Definir configurações do SDK de Aplicativo do Intune

O dicionário IntuneMAMSettings contido no Info.plist do aplicativo é usado para configurar o SDK do Intune App. Confira a seguir uma lista de configurações com suporte.

Algumas dessas configurações podem ter sido abordadas nas seções anteriores e outras não se aplicam a todos os aplicativos.

Setting  | Tipo  | Definição | Necessário?
--       |  --   |   --       |  --
ADALClientId  | Cadeia de caracteres  | O identificador do cliente do AAD do aplicativo. | Obrigatório se o aplicativo usar a ADAL.
ADALRedirectUri  | Cadeia de caracteres  | O URI de redirecionamento do AAD do aplicativo. | ADALRedirectUri ou ADALRedirectScheme é obrigatório se o aplicativo usar a ADAL.
ADALRedirectScheme  | Cadeia de caracteres  | O esquema de redirecionamento do AAD do aplicativo. Pode ser usado no lugar de ADALRedirectUri se o URI de redirecionamento do aplicativo estiver no formato `scheme://bundle_id`. | ADALRedirectUri ou ADALRedirectScheme é obrigatório se o aplicativo usar a ADAL.
ADALLogOverrideDisabled | Booliano  | Especifica se o SDK roteará todos os logs de ADAL (incluindo chamadas de ADAL do aplicativo, se houver) para seu próprio arquivo de log. O padrão é NÃO. Defina como SIM se desejar que o aplicativo defina seu próprio retorno de chamada de log ADAL. | Opcional.
ADALCacheKeychainGroupOverride | Cadeia de caracteres  | Especifica o grupo de conjunto de chaves a ser usado para o cache da ADAL em vez de "com.microsoft.adalcache". Observe que ele não contém o prefixo app-id. O prefixo será acrescentado à cadeia de caracteres fornecida em tempo de execução. | Opcional.
AppGroupIdentifiers | Matriz de cadeia de caracteres  | Matriz de grupos de aplicativo na seção de grupos de com.apple.security.application de direitos do aplicativo. | Necessário se o aplicativo usar grupos de aplicativos.
ContainingAppBundleId | Cadeia de caracteres | Especifica a ID do pacote da extensão que contém aplicativos. | Necessário para extensões do iOS.
DebugSettingsEnabled| Booliano | Se definido como SIM, as políticas de teste do pacote de Configurações podem ser aplicadas. Os aplicativos **não** devem ser fornecidos com essa configuração habilitada. | Opcional.
MainNibFile<br>MainNibFile~ipad  | Cadeia de caracteres  | Essa configuração deve conter o nome do arquivo nib principal do aplicativo.  | Obrigatório se o aplicativo definir MainNibFile em seu Info.plist.
MainStoryboardFile<br>MainStoryboardFile~ipad  | Cadeia de caracteres  | Essa configuração deve conter o nome do arquivo de storyboard principal do aplicativo. | Necessário se o aplicativo definir UIMainStoryboardFile em seu Info.plist
MAMPolicyRequired| Booliano| Especifica se a inicialização do aplicativo será impedida se ele não tiver a política de MAM do Intune. O padrão é "não".
MAMPolicyWarnAbsent | Booliano| Especifica se o aplicativo alertará o usuário durante a inicialização se ele não tiver a política de MAM do Intune. Observação: aplicativos não podem ser enviados para a loja com essa configuração definida como SIM | Opcional.
MultiIdentity | Booliano| Especifica se o aplicativo reconhece várias identidade ou não | Opcional.
SplashIconFile <br>SplashIconFile ~ ipad | Cadeia de caracteres  | Especifica o arquivo de ícone de abertura do Intune. Consulte a seção "Arquivos de imagem na inicialização" aqui para obter mais detalhes. | Opcional.
SplashDuration | Número | Quantidade mínima de tempo em segundos que a tela inicial do Intune será exibida ao iniciar o aplicativo. O padrão é 1,5. | Opcional.
BackgroundColor| Cadeia de caracteres| Especifica a cor da tela de fundo da tela inicial e da tela de PIN. Aceita uma cadeia de caracteres hexadecimal RGB no formato "#XXXXXX", em que os Xs podem variar de 0 a 9 ou de A a F. O sinal de libra pode ser omitido.   | Opcional; o padrão é cinza claro.
ForegroundColor| Cadeia de caracteres| Especifica a cor de primeiro plano da tela inicial e da tela de PIN, como a cor do texto. Aceita uma cadeia de caracteres hexadecimal RGB no formato "#XXXXXX", em que os Xs podem variar de 0 a 9 ou de A a F. O sinal de libra pode ser omitido.  | Opcional; o padrão é preto.
AccentColor | Cadeia de caracteres| Especifica a cor de destaque de tela de PIN, como a cor da caixa de texto e a cor de destaque da caixa.  Aceita uma cadeia de caracteres hexadecimal RGB no formato "#XXXXXX", em que os Xs podem variar de 0 a 9 ou de A a F. O sinal de libra pode ser omitido.| Opcional; o padrão é azul.
MAMTelemetryDisabled| Booliano| Especifica se o SDK não enviará dados de telemetria de volta para seu back-end| Opcional.
MAMTelemetryUsePPE | Booliano | Especifica se o SDK enviará dados para o back-end do PPE (Ambiente de pré-produção). Use ao testar seus aplicativos com a política do Intune para que os dados de telemetria de teste não se misture com dados de clientes. | Opcional.

## <a name="telemetry"></a>Telemetria

Por padrão, o SDK do Aplicativo do Intune para iOS registra dados de telemetria em eventos de uso, que são enviados para o Microsoft Intune. Os dados são registrados nos eventos de uso a seguir:

1. **Inicialização do aplicativo**: para ajudar o Microsoft Intune a obter informações sobre o uso de aplicativos habilitados para MAM por tipo de gerenciamento (MAM com MDM, MAM sem registro de MDM etc.).

2. **Chamada à API EnrollApplication**: para ajudar o Microsoft Intune a obter informações sobre a taxa de sucesso e várias outras métricas de desempenho de chamada `enrollApplication` do lado do cliente.

**Observação**: se optar por não enviar dados de telemetria do SDK do Intune App para o Microsoft Intune do seu aplicativo móvel, você precisará desabilitar a captura de telemetria pelo SDK do Intune App definindo a propriedade `MAMTelemetryDisabled` como '”YES” no dicionário IntuneMAMSettings.





## <a name="enable-multi-identity-optional"></a>Habilitar várias identidades (opcional)

Por padrão, o SDK aplicará a política ao aplicativo como um todo. O recurso de várias identidades do MAM pode ser habilitado para permitir que a política seja aplicada por identidade.  Ele requer mais participação do aplicativo do que outros recursos de MAM.

O aplicativo precisa informar o SDK do aplicativo quando pretende alterar a identidade ativa. O SDK também notificará o aplicativo quando uma alteração de identidade for necessária. Atualmente, há suporte para apenas uma identidade gerenciada. Depois que o usuário registrar o dispositivo ou o aplicativo, o SDK usará essa identidade e a considerará a identidade gerenciada primária. Outros usuários no aplicativo serão tratados como não gerenciados, com configurações de política irrestritas.

Observe que uma identidade é definida simplesmente como uma cadeia de caracteres. As identidades não diferenciam maiúsculas de minúsculas e as solicitações de identidade ao SDK podem não retornar o mesmo esquema de maiúsculas e minúsculas usado originalmente ao definir a identidade.


### <a name="overview"></a>Visão geral

Uma identidade é simplesmente o nome de usuário de uma conta (por exemplo, user@contoso.com). Os desenvolvedores podem definir a identidade do aplicativo nos diferentes níveis a seguir:

* **Identidade de processo**: a identidade de processo define a identidade de todo o processo e é usada principalmente para aplicativos de identidade única. Essa identidade afeta todas as operações, arquivos e a interface do usuário.
* **Identidade de interface do usuário**: determina quais políticas são aplicadas às operações de interface do usuário no thread principal, como recortar/copiar/colar, PIN, autenticação, dados de compartilhamento etc. A identidade de interface do usuário não afeta as operações de arquivo (criptografia, backup etc.).
* **Identidade de thread**: a identidade de thread afeta quais políticas são aplicadas no thread atual. Isso afeta todas as operações, arquivos e a interface do usuário.

É responsabilidade do aplicativo definir as identidades adequadamente, quer o usuários seja gerenciado ou não.

A qualquer momento, todo thread tem uma identidade efetiva para operações de interface do usuário e operações de arquivo. Essa é a identidade usada para determinar quais políticas, se houver, devem ser aplicadas. Se a identidade for "nenhuma identidade" ou o usuário não for gerenciado, nenhuma políticas será aplicada.



### <a name="thread-queues"></a>Filas de thread

Frequentemente, os aplicativos expedem tarefas síncronas e assíncronas para filas de thread. O SDK intercepta chamadas de GCD (Grand Central Dispatch) e associa a identidade do thread atual às tarefas expedidas. Quando as tarefas são executadas, o SDK altera temporariamente a identidade do thread para a identidade associada à tarefa, executa as tarefas e restaura a identidade do thread original. Como `NSOperationQueue` é criado sobre o GCD, `NSOperations` será executado na identidade do thread no momento em que forem adicionados ao `NSOperationQueue`. O `NSOperations` ou funções expedidas usando o GCD diretamente também têm a capacidade de alterar a identidade do thread atual conforme são executadas. Essa identidade substituirá a identidade herdada do thread de expedição.

### <a name="file-owner"></a>Proprietário do arquivo

O SDK mantém o controle da identidade do proprietário do arquivo local e aplica políticas de acordo com ela. O proprietário do arquivo é estabelecido quando o arquivo é criado ou quando é aberto no modo de truncamento. O proprietário é definido como a identidade de operação do arquivo efetivo do thread que executa a operação. Como alternativa, os aplicativos podem definir a identidade do proprietário do arquivo explicitamente usando o `IntuneMAMFilePolicyManager`. Os aplicativos podem usar o `IntuneMAMFilePolicyManager` para recuperar o proprietário do arquivo e definir a identidade da interface do usuário antes de exibir o conteúdo do arquivo.


### <a name="shared-data"></a>Dados compartilhados

Se o aplicativo criar arquivos que contêm dados de usuários gerenciados e não gerenciados, será responsabilidade do aplicativo criptografar os dados do usuário gerenciado. Os dados podem ser criptografados usando as APIs `protect` e `unprotect` do `IntuneMAMDataProtectionManager`. O método `protect` aceita uma identidade que pode ser um usuário gerenciado ou não gerenciado. Se o usuário for gerenciado, os dados serão criptografados. Se o usuário não for gerenciado, um cabeçalho será adicionado aos dados codificando a identidade, mas os dados não serão criptografados.  O método `protectionInfo` pode ser usado para recuperar o proprietário dos dados.

### <a name="share-extensions"></a>Extensões de compartilhamento

Se o aplicativo contiver uma Extensão de compartilhamento, o proprietário do item que está sendo compartilhado poderá ser recuperado usando o método `protectionInfoForItemProvider` em `IntuneMAMDataProtectionManager`. Se o item compartilhado for um arquivo, o SDK processará a definição do proprietário do arquivo. Se o item compartilhado for dados, será responsabilidade do aplicativo definir o proprietário do arquivo se esses dados forem persistidos em um arquivo, bem como chamar a API `setUIPolicyIdentity` (descrita abaixo) antes de exibir esses dados na interface do usuário.

### <a name="turn-on-multi-identity"></a>Ativar várias identidades

Por padrão, os aplicativos são considerados de única identidade e o SDK define a identidade do processo como o usuário registrado. Para habilitar o suporte a várias identidades, uma configuração booliana com o nome `MultiIdentity` e o valor 'YES' deve ser adicionada ao dicionário **IntuneMAMSettings** no arquivo Info.plist do aplicativo.

> [!NOTE]
> Quando várias identidades estiverem habilitadas, a identidade do processo, identidade da interface do usuário e identidades de thread serão definidas como nulas. É responsabilidade do aplicativo defini-las adequadamente.


### <a name="switching-identities"></a>Alternando identidades

* **Alternância de identidade iniciada pelo aplicativo**:

    Na inicialização, é considerado que aplicativos com várias identidades estejam sendo executados sob uma conta desconhecida, não gerenciada. A interface do usuário de inicialização condicional não será executada e nenhuma política será imposta ao aplicativo. É responsabilidade do aplicativo notificar o SDK sempre que a identidade precisar ser alterada. Normalmente, isso ocorrerá sempre que o aplicativo estiver prestes a exibir dados de uma conta de usuário específica.

    Um exemplo é quando o usuário tenta abrir um documento, caixa de correio ou uma guia em um bloco de anotações. O aplicativo precisa notificar o SDK antes que arquivo, caixa de correio ou guia seja, de fato, aberto. Isso é feito através da API `setUIPolicyIdentity` em `IntuneMAMPolicyManager`. Essa API deve ser chamada quer o usuário seja gerenciado ou não. Se o usuário for gerenciado, o SDK executará as verificações de inicialização condicional (detecção de jailbreak, PIN, autenticação etc.). O resultado da alternância de identidade é retornado ao aplicativo de forma assíncrona por meio de um manipulador de conclusão. O aplicativo deve adiar a abertura do documento, caixa de correio, guia etc. até que um código de resultado de êxito seja retornado. Se a alternância de identidade falhar, o aplicativo deverá cancelar a operação.

* **Alternância de identidade iniciada pelo SDK**:

    Há casos em que o SDK precisa solicitar que o aplicativo mude para uma identidade específica. Aplicativos com várias identidades devem implementar o método `identitySwitchRequired` em `IntuneMAMPolicyDelegate` para processar essa solicitação. Quando chamado, se o aplicativo for capaz de processar a solicitação de mudar para a identidade especificada, ele deverá passar `IntuneMAMAddIdentityResultSuccess` no manipulador de conclusão. Se não for possível processar a alternância de identidade, o aplicativo deverá passar `IntuneMAMAddIdentityResultFailed` para o manipulador de conclusão. O aplicativo não precisa chamar `setUIPolicyIdentity` em resposta a essa chamada. Se o SDK precisar que o aplicativo alterne para uma conta de usuário não gerenciada, a cadeia de caracteres vazia será passada para a chamada `identitySwitchRequired`.

* **Apagamento seletivo**:

    Quando o aplicativo for apagado seletivamente, o SDK chamará o método `wipeDataForAccount` em `IntuneMAMPolicyDelegate`. É responsabilidade do aplicativo remover a conta de usuário especificada e todos os dados associados a ela. O SDK é capaz de remover todos os arquivos pertencentes ao usuário e fará isso se o aplicativo retornar "FALSE" da chamada `wipeDataForAccount`. Observe que esse método é chamado de um thread em segundo plano e o aplicativo não deve retornar até que todos os dados do usuário tenham sido removidos (com exceção dos arquivos se o aplicativo for retornar "FALSE").

## <a name="debug-the-intune-app-sdk-in-xcode"></a>Depurar o SDK do Aplicativo do Intune no Xcode

Antes de testar manualmente seu aplicativo habilitado para MAM com o Microsoft Intune, você pode usar um arquivo de pacote **Settings.bundle** enquanto estiver no Xcode. Isso permitirá que você defina políticas de teste sem a necessidade de uma conexão com o Intune. Para habilitar:

* Adicionar um arquivo Settings.bundle clicando com o botão direito do mouse na pasta de nível superior no seu projeto. Selecione "Adicionar -> Novo Arquivo" no menu. Selecione o modelo de "Pacote de Configurações" encontrado em "Recursos" para adicionar.

* Em compilações somente de depuração, copie o MAMDebugSettings.plist para o Settings.bundle.

* Em Root.plist (no Settings.bundle), adicione uma preferência com "Tipo" = Painel Filho e "FileName" = MAMDebugSettings.

* Em **Configurações -> Nome do Seu Aplicativo**, habilite "Habilitar Políticas de Teste".

* Inicie o aplicativo (dentro ou fora do Xcode).

* Em **Configurações -> Nome do Seu Aplicativo -> Habilitar Políticas de Teste**, habilite uma política, como "PIN".

* Inicie o aplicativo (dentro ou fora do Xcode). Verifique se o PIN funciona conforme o esperado.

> [!NOTE]
> Agora você pode usar **Configurações -> Nome do Seu Aplicativo -> Habilitar Políticas de Teste** para habilitar e alternar configurações.

## <a name="recommended-ios-best-practices"></a>Práticas recomendadas para iOS

A seguir estão algumas práticas recomendadas para o desenvolvimento para iOS:

O sistema de arquivos iOS diferencia maiúsculas de minúsculas. Verifique se a caixa está correta para nomes de arquivo como `libIntuneMAM.a` e `IntuneMAMResources.bundle`.

Se o Xcode tiver problemas para encontrar `libIntuneMAM.a`, você pode corrigir o problema adicionando o caminho para essa biblioteca aos caminhos de pesquisa do vinculador.



## <a name="faq"></a>Perguntas Frequentes

 **Todos os usuários do meu aplicativo precisam estar registrados no serviço de MAM?**

Não.  Na verdade, somente contas corporativas ou de estudante devem ser registradas com o SDK do Intune App.  Os aplicativos são responsáveis por determinar se uma conta é usada em um contexto de trabalho ou escolar.   

**E quanto aos usuários que já entraram no aplicativo?  Eles precisam ser registrados?**

Enquanto é responsável pelo registro de usuários após eles terem sido autenticados com êxito, o aplicativo também é responsável por registrar todas as contas existentes que podem ter estado presentes antes que ele tivesse a funcionalidade de MAM sem MDM.   


Para fazer isso, o aplicativo deve fazer uso do método `registeredAccounts:`.  Esse método retorna um dicionário NSDictionary que contém todas as contas registradas no serviço de MAM do Intune.  Se qualquer conta existente no aplicativo não estiver presente na lista, o aplicativo deverá registrar essas contas via `registerAndEnrollAccount:`.




**Com que frequência o SDK repete tentativas de registro?**

O SDK tentará, automaticamente, realizar todas as inscrições com falha em um intervalo de 24 horas.  O SDK faz isso para garantir que, se a organização de um usuário tiver habilitado o MAM após o usuário ter se conectado ao aplicativo, o usuário seja registrado e receba políticas com êxito.

O SDK deixará de repetir as tentativas quando detectar que um usuário registrou o aplicativo com êxito.  Isso acontece porque apenas um usuário pode registrar um aplicativo em um dado momento. Se o registro do usuário for cancelado, as tentativas começarão novamente no mesmo intervalo de 24 horas.


**Por que o registro do usuário precisa ser cancelado?**

O SDK executará periodicamente as seguintes ações na tela de fundo:

 - Se o aplicativo ainda não estiver registrado, ele tentará registrar todas as contas registradas a cada 24 horas.
 - Se o aplicativo estiver registrado, o SDK verificará se há atualizações de política de MAM a cada 8 horas.

Ao cancelar o registro de um usuário, ele notifica o SDK que o usuário não usará mais o aplicativo e pode interromper qualquer um dos eventos periódicos acima para essa conta de usuário.  Ele também disparará o cancelamento do registro do aplicativo e um apagamento seletivo, se necessário.

**Eu devo definir o sinalizador doWipe como true no método de cancelamento de registro?**
Esse método deve ser chamado antes que usuário seja desconectado do aplicativo.  Se, como parte da desconexão, os dados do usuário forem excluídos do aplicativo, `doWipe` poderá ser definido como false.  No entanto, se o aplicativo não remover os dados do usuário, ele deverá ser definido como true para que o SDK possa excluir manualmente os dados.

**Há outras formas de cancelar o registro de um aplicativo?**
Sim, o administrador de TI pode enviar um comando de apagamento seletivo para o aplicativo, que fará com que o registro do usuário seja cancelado e seus dados sejam apagados.  O SDK processa automaticamente esse cenário e envia uma notificação por meio do método de delegação de cancelamento de registro.

## <a name="submitting-your-app-to-the-app-store"></a>Enviando seu aplicativo à App Store
Os builds de estrutura e biblioteca estática do SDK do Aplicativo do Intune são binários universais, o que significa que eles contêm código para todas as arquiteturas de dispositivo e simulador. A Apple rejeitará aplicativos enviados à App Store se eles contiverem código de simulador. Ao compilar com a biblioteca estática para builds somente de dispositivo, o vinculador removerá automaticamente o código de simulador.

Se o seu aplicativo usar o **build de estrutura** do SDK do Intune App, você precisará remover manualmente as arquiteturas de simulador da estrutura universal antes de enviar seu aplicativo à App Store. As instruções a seguir o ajudarão a fazer isso:

1. Confirme se `IntuneMAM.framework` está em sua Área de trabalho.
2. Execute os seguintes comandos:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```
    O primeiro comando remove as arquiteturas de simulador do dylib da estrutura.
    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    O segundo comando copia o dylib somente para dispositivos de volta para o diretório da estrutura.



<!--HONumber=Nov16_HO3-->


