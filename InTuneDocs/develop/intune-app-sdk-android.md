---
title: Guia do SDK de Aplicativo do Microsoft Intune para Desenvolvedores do Android | Microsoft Intune
description: 
keywords: SDK
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: edbc701effb3817c2f9a160f05e7b5bc8ad0070e
ms.openlocfilehash: ee3a668a5415d14eb82e64e6bb16d9621bb13b57


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Guia do SDK de Aplicativos do Microsoft Intune para Desenvolvedores do Android

> [!NOTE]
> Leia primeiro a [Intune App SDK overview](intune-app-sdk.md) (Visão geral do SDK de Aplicativo do Intune), que explica os recursos atuais do SDK e descreve a preparação para a integração em cada plataforma com suporte. 

O SDK de Aplicativo do Microsoft Intune para Android permite incorporar o MAM (gerenciamento de aplicativo móvel) do Intune em seu aplicativo Android. Um aplicativo habilitado para MAM é integrado com o SDK do Aplicativo do Intune e permite que administradores de TI implantem políticas em seu aplicativo móvel quando o aplicativo for gerenciado ativamente pelo Intune.

# <a name="whats-in-the-sdk"></a>O que está contido no SDK 

O SDK de Aplicativos do Microsoft Intune é uma biblioteca Android padrão sem dependências externas. O SDK é composto por:  

* **Microsoft.Intune.MAM.SDK.jar**: as interfaces necessárias para habilitar o MAM e a interoperabilidade com o aplicativo de Portal da Empresa do Intune. Os aplicativos devem especificá-lo como uma referência de biblioteca Android.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: as interfaces necessárias para habilitar o MAM em aplicativos que utilizam a biblioteca de suporte do Android v4.  Os aplicativos que precisam desse suporte devem fazer referência diretamente ao arquivo jar. 

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: as interfaces necessárias para habilitar o MAM em aplicativos que utilizam a biblioteca de suporte do Android v7. Os aplicativos que precisam desse suporte devem fazer referência diretamente ao arquivo jar.

* **O diretório de recursos**: os recursos (como cadeias de caracteres) dos quais o SDK depende. 

* **Microsoft.Intune.MAM.SDK.aar**: os componentes do SDK, com exceção dos jars Support.V4 e Support.V7. Esse arquivo pode ser usado no lugar de componentes individuais se sua compilação do sistema der suporte a arquivos AAR.

* **AndroidManifest.xml**: os pontos de entrada adicionais e os requisitos da biblioteca. 

* **THIRDPARTYNOTICES.TXT**: um aviso de atribuição que reconhece códigos de terceiros e/ou de OSS que serão compilados em seu aplicativo. 

# <a name="requirements"></a>Requisitos 

O SDK de Aplicativos do Intune é um projeto Android compilado. Como resultado, ele é amplamente independente da versão do Android que o aplicativo usa para suas versões de API mínima ou de destino. O SDK dá suporte da API 14 do Android (Android 4.0 +) à API 24 do Android. 

O SDK de Aplicativo do Intune para Android depende da presença do aplicativo de [Portal da Empresa](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) no dispositivo para habilitar as políticas de MAM. Para MAM sem registro de dispositivo, o usuário **não** precisa registrar o dispositivo usando o Portal da Empresa.


# <a name="how-the-intune-app-sdk-works"></a>Como o SDK de Aplicativos do Intune funciona 

##<a name="entry-points"></a>Pontos de entrada

O SDK de Aplicativo do Intune requer alterações no código-fonte do aplicativo para habilitar as políticas de gerenciamento de aplicativo do Intune. Isso é feito por meio da substituição das classes base do Android por classes base do Intune equivalentes, cujos nomes têm o prefixo **MAM**. As classes do SDK estão entre a classe base do Android e a versão do próprio aplicativo derivada dessa classe.  Usando uma atividade como exemplo, você acabará com uma hierarquia de herança que se parece com: Activity > MAMActivity > AppSpecificActivity.

Por exemplo, quando **AppSpecificActivity** interage com seu pai (por exemplo, chamando `super.onCreate()`), **MAMActivity** é a superclasse. 

Aplicativos Android típicos têm um modo único e têm acesso ao sistema por meio de seu objeto de [Contexto](https://developer.android.com/reference/android/content/Context.html).  Aplicativos que incorporam o SDK de Aplicativo do Intune, por outro lado, têm modo dual. Esses aplicativos continuam acessando o sistema por meio do objeto de Contexto, mas, dependendo da Atividade de base usada, o objeto de Contexto será fornecido pelo Android ou multiplexará de forma inteligente entre uma exibição restrita do sistema e o Contexto fornecido pelo Android.

Ao usar um [ponto de entrada](https://developer.android.com/guide/components/fundamentals.html) do Android que foi substituído por seu equivalente de MAM, uma versão de MAM do ciclo de vida do ponto de entrada deve ser usada (com exceção da classe **MAMApplication**).

Por exemplo, ao derivar de **MAMActivity**, em vez de substituir `onCreate` e chamar `super.onCreate`, a Atividade deve substituir `onMAMCreate` e chamar `super.onMAMCreate`. Isso permite que a inicialização da Atividade (entre outros) seja restrita em determinados casos. 


##<a name="sdk-permissions"></a>Permissões do SDK

O SDK de Aplicativo do Intune exige três [permissões de sistema do Android](https://developer.android.com/guide/topics/security/permissions.html) em aplicativos que o integram:

* `android.permission.GET_ACCOUNTS`  [solicitada em tempo de execução se necessário]
* `android.permission.MANAGE_ACCOUNTS`
* `android.permission.USE_CREDENTIALS`

Essas permissões são exigidas pela [ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/) (Biblioteca de Autenticação do Azure Active Directory) para realizar a autenticação agenciada. Se essas permissões não forem concedidas ao aplicativo ou revogadas pelo usuário, os fluxos de autenticação que exigem o agente (o aplicativo de Portal da Empresa) serão desabilitados.


##<a name="company-portal"></a>Portal da Empresa

Por que o aplicativo de Portal da Empresa é exigido? Quando o Portal da Empresa é instalado no dispositivo e recupera a política de restrição de aplicativo para o usuário do serviço Intune, os pontos de entrada do SDK são inicializados de forma assíncrona. A inicialização só é necessária quando o processo é criado inicialmente pelo Android. Durante a inicialização, uma conexão é estabelecida com o aplicativo de Portal da Empresa e a política é recuperada do aplicativo.  

> [!NOTE]
> Quando o aplicativo de Portal da Empresa não estiver presente no dispositivo, o comportamento do aplicativo habilitado para o Intune não será alterado e ele se comportará como um aplicativo normal.


# <a name="how-to-integrate-with-the-intune-app-sdk"></a>Como integrar o SDK de Aplicativos do Intune
 
Como dissemos anteriormente, o SDK requer alterações no código-fonte do aplicativo para habilitar as políticas de gerenciamento do aplicativo. Aqui estão as etapas necessárias para habilitar o MAM em seu aplicativo: 

## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Substitua classes, métodos e atividades por seus equivalentes com MAM (obrigatório) 

As classes base do Android devem ser substituídas por seus equivalentes com MAM. Para fazer isso, localize todas as instâncias das classes listadas na tabela a seguir e as substitua pelo SDK de Aplicativos do Intune equivalente. 

| Classe base do Android | Substituição do SDK de Aplicativo do Intune |
|--|--|
| android.app.Activity | MAMActivity |
| android.app.ActivityGroup | MAMActivityGroup |
| android.app.AliasActivity | MAMAliasActivity |
| android.app.Application | MAMApplication |
| android.app.DialogFragment | MAMDialogFragment |
| android.app.ExpandableListActivity | MAMExpandableListActivity |
| android.app.Fragment | MAMFragment |
| android.app.IntentService | MAMIntentService |
| android.app.LauncherActivity | MAMLauncherActivity |
| android.app.ListActivity | MAMListActivity |
| android.app.NativeActivity | MAMNativeActivity |
| android.app.PendingIntent | **MAMPendingIntent** * |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | **MAMBinder** (necessário apenas se o Associador não for gerado de uma interface da AIDL (linguagem IDL do Android)) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Suppout.v4.jar**:

| MAM do Intune da classe Android | Substituição do SDK de Aplicativo do Intune |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| Android.support.v4.App.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider
    
**Microsoft.Intune.MAM.SDK.Suppout.v7.jar**:

|Classe do Android | Substituição do SDK de Aplicativo do Intune |
|--|--|
|Android.support.v7.App.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>Lembre-se: ao usar um [ponto de entrada](https://developer.android.com/guide/components/fundamentals.html) do Android que foi substituído por seu equivalente com MAM, a versão de MAM do ciclo de vida do ponto de entrada deve ser usada (com exceção da classe **MAMApplication**).
>
>Por exemplo, ao derivar de **MAMActivity**, em vez de substituir `onCreate` e chamar `super.onCreate`, a Atividade deve substituir `onMAMCreate` e chamar `super.onMAMCreate`. Isso permite que a inicialização da Atividade (entre outros) seja restrita em determinados casos. 

### <a name="pendingintents-and-renamed-methods"></a>PendingIntents e métodos renomeados 

Após derivar de um dos pontos de entrada de MAM, é seguro usar o Contexto como você faria normalmente – para iniciar Atividades, usar seu **PackageManager** etc.  

**PendingIntents** são uma exceção a essa regra. Ao chamar essas classes, você precisa alterar o nome de classe. Por exemplo, em vez de `PendingIntent.get*`, o método `MAMPendingIntents.get*` deve ser usado. Depois disso, o **PendingIntents** resultante pode ser usado normalmente.

Em alguns casos, um método disponível na classe Android foi marcado como final na classe de MAM de substituição. Nesse caso, a classe de MAM de substituição fornece um método nomeado da mesma forma (em geral com o sufixo "MAM") que deve ser substituído em vez disso. Por exemplo, em vez de substituir `ContentProvider.query`, você substituiria `MAMContentProvider.queryMAM`. O compilador Java deve impor as restrições finais para evitar a substituição acidental do método original em vez do MAM equivalente. 

##<a name="enable-features-that-require-app-participation"></a>Habilitar recursos que exigem a participação do aplicativo 

Há algumas políticas que o SDK não pode implementar por conta própria. O aplicativo pode controlar seu comportamento para conquistar esses recursos usando várias APIs que você pode encontrar na interface **AppPolicy** incluída abaixo.  

```
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * <strong>This function is now deprecated. Please use {@link #getIsSaveToLocationAllowed(SaveLocation, String)} instead</strong>
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 * 
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 * 
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 * 
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();


}

```

## <a name="enable-it-control-over-app-saving-behavior"></a>Habilitar o controle do setor de TI sobre o comportamento de salvamento do aplicativo

Muitos aplicativos implementam recursos que permitem que o usuário final salve arquivos localmente ou em um serviço de armazenamento em nuvem. O SDK de Aplicativo do Azure permite que os administradores de TI protejam contra vazamento de dados aplicando as restrições de política da forma que considerarem adequada para sua organização.  Uma das políticas que o setor de TI pode controlar é se o usuário final pode salvar em um armazenamento de dados "pessoal" não gerenciado. Isso inclui salvar localmente, em cartões SD ou em serviços de backup de terceiros. 

**A participação do aplicativo é necessária para habilitar o recurso.** Se o seu aplicativo permitir o salvamento em locais na nuvem ou pessoais diretamente do aplicativo, você deve implementar esse recurso para garantir que o administrador de TI possa controlar se é permitido salvar em um local. A API abaixo permite que o aplicativo saiba se é permitido salvar em um armazenamento pessoal de acordo com a atual política do administrador. O aplicativo pode, então, aplicar a política, pois ele está ciente de que o armazenamento pessoal de dados está disponível para o usuário final por meio do aplicativo.  

Para determinar se a política é aplicada, o aplicativo pode fazer a chamada a seguir: 

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

**Observação**: `MAMComponents.get(AppPolicy.class)` sempre retornará uma Política de aplicativo não nula, mesmo que o dispositivo ou aplicativo não esteja sob uma política de gerenciamento do Intune. 

## <a name="allow-app-to-detect-if-pin-policy-is-required"></a>Permitir que o aplicativo detecte se a Política de PIN é necessária
 
Para algumas restrições de aplicativo do Intune, talvez você queira que o aplicativo desabilite algumas das suas funcionalidades para não duplicar a funcionalidade no SDK de Aplicativo do Intune. Por exemplo, se o aplicativo tiver sua própria experiência do usuário de PIN, ele poderá desabilitá-la se o SDK estiver configurado para exigir que o usuário final insira um PIN. 

Para determinar se uma política de PIN do Intune será configurada para exigir um PIN do aplicativo na inicialização, o aplicativo poderá fazer a chamada a seguir: 

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

## <a name="registering-for-notifications-from-the-sdk"></a>Registrando-se para notificações do SDK  

O SDK de Aplicativo do Intune permite que seu aplicativo controle o comportamento de algumas políticas, como um apagamento remoto, quando elas são implantadas pelo administrador de TI. Quando um administrador de TI implanta tal política, o serviço do Intune envia uma notificação para o SDK.

Seu aplicativo precisa se registrar para notificações do SDK criando uma classe **MAMNotificationReceiver** e registrando-a no **MAMNotificationReceiverRegistry**. Isso é feito fornecendo o receptor e o tipo de notificação desejada em `App.onCreate`, como mostra o exemplo a seguir:

``` 
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
.registerReceiver(
                new ToastNotificationReceiver(),
MAMNotificationType.WIPE_USER_DATA);
    }
```

**MAMNotificationReceiver** apenas recebe notificações do serviço do Intune. Algumas notificações são manipuladas pelo SDK diretamente, enquanto outras exigem a participação do aplicativo. 

Um aplicativo **deve** retornar true ou false de uma notificação. 

Ele deve sempre retornar true, a menos que alguma ação que ele tentou executar como resultado da notificação falhe. 

* Essa falha pode ser relatada ao serviço do Intune. Um exemplo de cenário a ser relatado é se o aplicativo falhar ao apagar dados do usuário após o administrador de TI iniciar um apagamento. 

É seguro bloquear em `MAMNotificationReceiver.onReceive` porque seu retorno de chamada não está em execução no thread da interface do usuário. 

A interface **MAMNotificationReceiver** está incluída abaixo conforme definido no SDK: 

```
/**
 * The SDK is signaling that a WG event has occurred. 
 * 
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     * 
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in 
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}

```

##<a name="types-of-notifications"></a>Tipos de notificações
As seguintes notificações são enviadas para o aplicativo e algumas delas podem exigir a participação do aplicativo: 

* **`WIPE_USER_DATA`**: esta notificação é enviada em uma classe **MAMUserNotification**. Quando a notificação é recebida, o aplicativo deve excluir todos os dados associados à identidade "corporativa" passada com **MAMUserNotification**. Atualmente, essa notificação é enviada durante o cancelamento do registro do Serviço do Intune. O nome principal do usuário geralmente é especificado durante o processo de registro. Se você se registrar para essa notificação, seu aplicativo deve garantir que todos os dados do usuário tenham sido excluídos. Se você não se registrar para ela, o comportamento de apagamento seletivo padrão será executado.

* **`WIPE_USER_AUXILIARY_DATA`**: os aplicativos podem se registrar para essa notificação se quiserem que o SDK de Aplicativo do Intune execute o comportamento de apagamento seletivo padrão, mas ainda desejarem remover alguns dados auxiliares quando o apagamento ocorrer.  

* **`REFRESH_POLICY`**: esta notificação é enviada em uma **MAMUserNotification**. Quando a notificação é recebida, qualquer política do Intune armazenada em cache deve ser invalidada e atualizada. Normalmente, isso é tratado pelo SDK, porém deve ser tratado pelo aplicativo se a política for usada de qualquer maneira persistente. 



## <a name="protecting-backup-data"></a>Proteção de dados de backup 

A partir do Android Marshmallow (API 23), o Android tem duas formas para um aplicativo fazer backup de seus dados. Cada opção está disponível para seu aplicativo e requer etapas diferentes para garantir que a proteção de dados do Intune seja implementada corretamente. Examine a tabela abaixo para ver as ações correspondentes necessárias para o comportamento correto de proteção de dados.  Leia mais sobre os métodos de backup no [Guia da API do Android](http://developer.android.com/guide/topics/data/backup.html). 

### <a name="auto-backup-for-apps"></a>Backup automático de aplicativos

O Android começou a oferecer [backups completos automáticos](https://developer.android.com/guide/topics/data/autobackup.html) para aplicativos em dispositivos Android Marshmallow, independentemente da API de destino do aplicativo. Em seu AndroidManifest.xml, se você definir explicitamente `android:allowBackup` como **false**, seu aplicativo nunca será enfileirado para backups pelo Android e os dados "corporativos" permanecerão no aplicativo. Nesse caso, nenhuma ação adicional é necessária.

No entanto, por padrão, o atributo `android:allowBackup` é definido como true, mesmo que `android:allowBackup` não esteja especificado no arquivo de manifesto. Isso significa que todos os dados do aplicativo são copiados automaticamente para a conta do Google Drive do usuário, um comportamento padrão que representa um **risco de vazamento de dados**. Portanto, o SDK requer as alterações descritas na tabela a seguir para garantir que a proteção de dados seja aplicada.  É importante seguir as diretrizes abaixo para proteger os dados do cliente corretamente se você quiser que seu aplicativo seja executado em dispositivos Android Marshmallow.  

*  Se não tiver escrito um agente de backup para fazer backup do seu aplicativo usando um **MAMBackupAgent** ou **MAMBackupAgentHelper**, você deve considerar e controlar como os dados de seu aplicativo serão carregados pelo Backup Automático. O Intune permite que você utilize todos os [recursos de Backup Automático](https://developer.android.com/guide/topics/data/autobackup.html) disponíveis no Android, incluindo a capacidade de definir regras personalizadas no XML, mas você precisa seguir as etapas abaixo para proteger seus dados:

    1. Use o MAMBackupAgent padrão para permitir backups completos automáticos que sejam compatíveis com a política do Intune. Coloque `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` no manifesto do seu aplicativo. 
    2. Quando decidir qual tipo de backup completo seu aplicativo deve receber (filtrado, não filtrado ou nenhum), você precisará definir o atributo `android:fullBackupContent` como true, false ou um recurso XML em seu aplicativo. Copie tudo o que você colocar em `android:fullBackupContent` em uma marca de metadados chamada `com.microsoft.intune.mam.FullBackupContent`

    **Exemplos**: se você quiser que seu aplicativo tenha backups completos de acordo com suas regras personalizadas em um arquivo XML, forneça um recurso sob a marca de metadados `com.microsoft.intune.mam.FullBackupContent` em seu manifesto, como: 
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



### <a name="keyvalue-backup"></a>Backups de chave/valor

Essa opção está disponível para todas as APIs e usa `BackupAgent` e `BackupAgentHelper`. 

#### <a name="using-backupagenthelper"></a>Usando BackupAgentHelper

`BackupAgentHelper` é muito mais simples de implementar do que o `BackupAgent` em termos de funcionalidade nativa do Android e integração de MAM. `BackupAgentHelper` permite que o desenvolvedor registre arquivos inteiros e preferências compartilhadas com um `FileBackupHelper` ou `SharedPreferencesBackupHelper`, respectivamente, que são adicionados ao `BackupAgentHelper` no momento da criação. 

#### <a name="using-backupagent"></a>Usando BackupAgent

`BackupAgent` permite que você seja muito mais explícito sobre de quais dados é feito backup. No entanto, esta opção significa que você não poderá aproveitar a estrutura de backup do Android.  Como você é bastante responsável pela implementação, há mais etapas necessárias para garantir a proteção de dados apropriada do MAM. Uma vez que a maioria do trabalho é passado para você, o desenvolvedor, integração do MAM é um pouco mais envolvida. 

##### <a name="app-does-not-have-a-backup-agent"></a>O aplicativo não tem um agente de backup
  
Essas são as opções do desenvolvedor quando `android:allowBackup =true`:

###### <a name="full-back-up-according-to-a-configuration-file"></a>Backup completo de acordo com um arquivo de configuração: 

Forneça um recurso sob a marca de metadados `com.microsoft.intune.mam.FullBackupContent` em seu manifesto. por exemplo,     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Adicione o seguinte atributo na marca `<application>` : `android:fullBackupContent="@xml/my_scheme"`, em que `my_scheme` é um recurso XML em seu aplicativo. 

###### <a name="full-back-dup-without-exclusions"></a>Backup completo sem exclusões 

Forneça uma marca no manifesto, como `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Adicione o seguinte atributo na marcação `<application>`: `android:fullBackupContent="true"`.

##### <a name="app-has-a-backup-agent"></a>O aplicativo tem um agente de backup

Siga as recomendações nas seções `BackupAgent` e `BackupAgentHelper` descritas acima 

Considere a possibilidade de usar nosso `MAMDefaultFullBackupAgent`, que fornece backup fácil no Android M. 

#### <a name="before-your-backup"></a>Antes do backup

Antes de iniciar o backup, você deve verificar se os arquivos ou buffers de dados de que você pretende fazer backup têm permissão para backup. Nós fornecemos uma função `isBackupAllowed` em `MAMFileProtectionManager` e `MAMDataProtectionManager` para determinar isso. Se o buffer de dados ou arquivo não tiver permissão para backup, você não deve tentar continuar utilizando-o em seu backup.

Em algum momento durante o backup, se desejar que as identidades dos arquivos verificados na etapa 1 façam backup, você deverá chamar `backupMAMFileIdentity(BackupDataOutput data, File … files)` com os arquivos dos quais planejada extrair dados. Isso criará automaticamente novas entidades de backup e as gravará em `BackupDataOutput` para você. Essas entidades serão consumidas automaticamente após a restauração. 

### <a name="configure-azure-directory-authentication-library-adal"></a>Configurar a ADAL (Biblioteca de Autenticação do Active Directory)  

O SDK depende a ADAL para autenticação e cenários de inicialização condicional, o que exige que os aplicativos tenham alguma configuração do Active Directory do Azure. Os valores de configuração são comunicados para o SDK por meio dos metadados `AndroidManifest` . Para configurar seu aplicativo e habilitar a autenticação adequada, adicione o seguinte ao nó de aplicativo no `AndroidManifest`. Algumas dessas configurações somente são necessárias se seu aplicativo usar o ADAL para autenticação em geral. Nesse caso, você precisará dos valores específicos que seu aplicativo usa para se registrar com o AAD. Isso é feito para garantir que não seja solicitada a autenticação do usuário final duas vezes devido ao AAD reconhecer dois valores de registro separados: um do aplicativo e um do SDK. 

        <meta-data
            android:name="com.microsoft.intune.mam.aad.Authority"
            android:value="https://AAD authority/" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.ClientID"
            android:value="your-client-ID-GUID" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
            android:value="your-redirect-URI" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.SkipBroker"
            android:value="[true | false]" />

Os GUIDs não devem ter o colchete à direita ou à esquerda.

#### <a name="common-adal-configurations"></a>Configurações comuns do ADAL 

A seguir estão as configurações comua para os valores explicados acima. 

##### <a name="app-does-not-integrate-adal"></a>O aplicativo não se integra ao ADAL

* A autoridade deve ser configurada para o ambiente desejado em que as contas do AAD foram configuradas.

* O SkipBroker deve ser definido como true.

##### <a name="app-integrates-adal"></a>O aplicativo integra o ADAL

* A autoridade deve ser configurada para o ambiente desejado em que as contas do AAD foram configuradas.

* A ID do cliente deve ser definida como ID cliente do aplicativo.

* `NonBrokerRedirectURI` deve ser definido como um URI de redirecionamento válido para o aplicativo.
    * Or `urn:ietf:wg:oauth:2.0:oob` deve ser configurado como um URI de redirecionamento do AAD válido.

* O SkipBroker deve ser definido como false (ou absent)

* O AAD deve ser configurado para aceitar o URI de redirecionamento do agente.

##### <a name="app-integrates-adal-but-does-not-support-the-aad-authenticator-app"></a>O aplicativo integra-se ao ADAL, mas não dá suporte ao aplicativo do Autenticador do AAD.

* A autoridade deve ser configurada para o ambiente desejado em que as contas do AAD foram configuradas.

* A ID do cliente deve ser definida como ID cliente do aplicativo.

* `NonBrokerRedirectURI` deve ser definido como um URI de redirecionamento válido para o aplicativo.

    * Or `urn:ietf:wg:oauth:2.0:oob` deve ser configurado como um URI de redirecionamento do AAD válido.

### <a name="how-to-enable-logging-in-the-sdk"></a>Como habilitar o registro no SDK 

O registro em log é feito por meio da estrutura `java.util.logging` . Para receber os logs, configure o registro conforme descrito no [Guia técnico de Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Dependendo do aplicativo, `App.onCreate` geralmente é o melhor local para iniciar o registro. Observe que as mensagens de Log são criptografadas pelo nome de classe, que pode ser ofuscado.

##<a name="multiidentity"></a>Várias identidades
###<a name="overview"></a>Visão geral
Por padrão, o SDK de Aplicativo do Intune aplicará a política ao aplicativo como um todo. O recurso de várias identidades do MAM pode ser habilitado para permitir que a política seja aplicada por identidade.  Ele requer uma participação significativamente maior do aplicativo do que outros recursos de MAM. O aplicativo precisa informar o SDK do aplicativo quando pretender alterar a identidade ativa. O SDK também notificará o aplicativo quando uma alteração de identidade for necessária. Atualmente, há suporte para apenas uma identidade gerenciada. Depois que o usuário registrar o dispositivo ou o aplicativo, o SDK usará essa identidade e a considerará a identidade gerenciada primária. Outros usuários no aplicativo serão tratados como não gerenciados, com configurações de política irrestritas. 

Observe que uma identidade é definida simplesmente como uma cadeia de caracteres. As identidades não diferenciam maiúsculas de minúsculas e as solicitações de identidade ao SDK podem não retornar o mesmo esquema de maiúsculas e minúsculas usado originalmente ao definir a identidade.

###<a name="enabling-multiidentity"></a>Habilitando várias identidades
Por padrão, considera-se que todos os aplicativos são aplicativos de identidade única. Um aplicativo declara que reconhece várias identidades colocando os seguintes metadados no manifesto do Android.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
###<a name="setting-the-identity"></a>Definindo a identidade

Os desenvolvedores podem definir a identidade do aplicativo nos níveis a seguir: 
1. Nível de processo 
2. Nível de contexto (geralmente, a Atividade) 
3. Nível de thread 

Uma identidade definida no nível do thread substitui uma identidade definida no nível do Contexto, que substitui uma identidade definida no nível do processo. Uma identidade definida em um Contexto é usada apenas quando apropriado. Operações de E/S de arquivo, por exemplo, não têm um Contexto associado. Os seguintes métodos no MAMPolicyManager podem ser usados para definir a identidade e recuperar os valores de identidade definidos anteriormente.

```
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

public static String getUIPolicyIdentity(final Context context);

public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

public static String getProcessIdentity();

public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

public static String getCurrentThreadIdentity();

/**
 * Get the currently applicable app policy. Same as MAMComponents.get(AppPolicy.class). This method does
    not take the context identity into account.
 */
public static AppPolicy getPolicy();

/**
 * Get the currently applicable app policy, taking the context
 * identity into account.
 */
public static AppPolicy getPolicy(final Context context);


public static AppPolicy getPolicyForIdentity(final String identity);

public static boolean getIsIdentityManaged(final String identity);

```
Você também pode limpar a identidade do aplicativo definido-a como nula. A cadeia de caracteres vazia pode ser usada como uma identidade que nunca terá restrições. Todos os métodos para definir a identidade relatam os valores de resultado via ``` MAMIdentitySwitchResult```. Há quatro valores que podem ser retornados:

1.**SUCCEEDED**: a alteração de identidade foi bem-sucedida 2.**NOT_ALLOWED**: não é permitido alterar a identidade. Isso ocorrerá se for feita uma tentativa de mudar para outro usuário corporativo que pertence à mesma empresa que o usuário registrado. Ocorrerá também se for feita uma tentativa de definir a identidade da interface do usuário (Contexto) quando uma identidade diferente estiver definida no thread atual.
3.**CANCELLED**: o usuário cancelou a alteração de identidade, normalmente pressionando o botão Voltar em um prompt de PIN/Autenticação.
4.**FAILED**: ocorreu uma falha na alteração da identidade por um motivo não especificado.

No caso da definição de uma identidade de Contexto, o resultado é relatado de forma assíncrona. Se o Contexto for uma Atividade, não será possível saber se a alteração de identidade foi bem-sucedida até que a inicialização condicional seja realizada, o que pode exigir que o usuário insira um PIN ou suas credenciais corporativas completas. Espera-se que o aplicativo implemente um ```MAMSetUIIdentityCallback``` para receber esse resultado, embora seja permitido passar null para esse parâmetro.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult); 
}
```

Você também pode definir a identidade de uma atividade diretamente por meio de um método em MAMActivity, em vez de chamar ``` MAMPolicyManager.setUIPolicyIdentity```. Você pode fazer isso usando os método a seguir:

 ```public final void switchMAMIdentity(final String newIdentity);```

Os aplicativos também podem substituir um método em MAMActivity para serem notificados do resultado das tentativas de alterar a identidade da atividade 

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

**Observação:** alterar a identidade pode exigir a recriação da atividade. Nesse caso, o retorno de chamada ```onSwitchMAMIdentityComplete``` será entregue para a nova instância da atividade.

###<a name="implicit-identity-changes"></a>Alterações de identidade implícitas

Além da capacidade do aplicativo de definir a identidade, um thread ou a identidade de um contexto pode mudar com base na entrada de dados de outro aplicativo habilitado para MAM. Por exemplo, se uma atividade for iniciada de uma Tentativa enviada por outro aplicativo com MAM, a identidade da atividade será definida com base na identidade em vigor no outro aplicativo no momento em que a Tentativa foi enviada.
Para serviços, a identidade do thread será definida da mesma forma pela duração de uma chamada onStart ou onBind. Chamadas para o Associador retornadas de onBind também definirão temporariamente a identidade do thread.
De forma semelhante, chamadas para um ```ContentProvider``` definirão a identidade do thread no período de sua duração.
Além disso, a interação do usuário com uma atividade pode causar uma mudança de identidade implícita.
Por exemplo, se um usuário cancelar após um prompt de autorização durante o ```Resume```, ocorrerá uma mudança implícita para uma identidade vazia.
O aplicativo tem uma oportunidade de ser informado dessas alterações e, em alguns casos, proibi-las se necessário. ```MAMService``` e ```MAMContentProvider``` expõem o seguinte método que as subclasses podem substituir:

```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
```
No caso de ```MAMActivity```, um parâmetro adicional está presente no método: 
```
public void onMAMIdentitySwitchRequired(final String identity, 
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
```
O ```AppIdentitySwitchReason``` captura a fonte da mudança implícita e pode aceitar os valores ```CREATE```, ```RESUME_CANCELLED``` e ```NEW_INTENT```.  O motivo ```RESUME_CANCELLED``` é usado quando a atividade é retomada e faz com que o PIN, a autenticação ou outra interface do usuário de conformidade seja exibida; o usuário tenta cancelar para sair dessa interface do usuário, normalmente usando o uso do botão Voltar.
```AppIdentitySwitchResultCallback``` é o seguinte:
```
public interface AppIdentitySwitchResultCallback {
    /**
     * @param result
     *            whether the identity switch can proceed.
     */
    void reportIdentitySwitchResult(AppIdentitySwitchResult result);
}
```
Em que ```AppIdentitySwitchResult``` é ```SUCCESS``` ou ```FAILURE```. 

O método ```onMAMIdentitySwitchRequired``` é chamado para todas as mudanças de identidade implícitas, exceto por aquelas feitas por meio de um Associador retornado de ```MAMService.onMAMBind```. As implementações padrão de ```onMAMIdentitySwitchRequired``` chamam ```reportIdentitySwitchResult(FAILURE)``` imediatamente quando o motivo é ```RESUME_CANCELLED```, e ```reportIdentitySwitchResult(SUCCESS)``` em todos os outros casos. 

Não é esperado que a maioria dos aplicativos precisem bloquear ou adiar uma mudança de identidade de maneira diferente, mas se um aplicativo precisar fazer isso, os seguintes pontos devem ser considerados: *se uma mudança de identidade for bloqueada, o resultado será o mesmo que apareceria se as configurações de compartilhamento de ```Receive``` tivessem proibido a entrada de dados. *Se um Serviço estiver em execução no thread principal, ```reportIdentitySwitchResult``` **deve** ser chamado de forma síncrona ou o thread da interface do usuário para de responder. 
*Para criação de ```Activity```, ```onMAMIdentitySwitchRequired``` será chamado antes de ```onMAMCreate```. Se o aplicativo precisar mostrar a interface do usuário para determinar se deve permitir a mudança de identidade, a interface do usuário deverá ser exibida usando uma atividade diferente. *Em uma Atividade, quando for solicitada uma mudança para a identidade vazia com o motivo igual a ```RESUME_CANCELLED```, o aplicativo deverá modificar a atividade retomada para exibir dados consistentes com essa mudança de identidade.  Se isso não for possível, o aplicativo deverá recusar a mudança e o usuário será solicitado novamente a obedecer a política para retomar a identidade (por exemplo, recebendo a tela de entrada de PIN). 

**Observação:** um aplicativo com várias identidades sempre receberá dados de entrada de aplicativos gerenciados e não gerenciados. É responsabilidade do aplicativo tratar dados de identidades gerenciadas de maneira gerenciada. Se uma identidade solicitada for gerenciada ```(MAMPolicyManager.getIsIdentityManaged)```, mas o aplicativo não puder usar a conta (por exemplo, porque contas, como contas de email, devem ser configuradas no aplicativo primeiro), a chave de identidade deverá ser recusada.

##<a name="file-protection"></a>Proteção de arquivo
Cada arquivo terá uma identidade associada no momento da criação, com base na identidade do thread e do processo. Essa identidade será usada para a criptografia de arquivos e o apagamento seletivo. Somente arquivos cuja identidade tem uma política que exige criptografia serão criptografados. O apagamento seletivo padrão do SDK apagará apenas arquivos associados à identidade para a qual um apagamento foi solicitado. O aplicativo pode consultar ou alterar a identidade de um arquivo usando ```MAMFileProtectionManager```
```
public final class MAMFileProtectionManager {

    /**
     * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
     * future protection changes.
     * 
     * @param identity
     *            Identity to set.
     * @param file
     *            File to protect.
     * @throws IOException
     *             If the file cannot be changed.
     */
    public static void protect(final File file, final String identity) throws IOException;

    /**
     * Get the protection info on a file.
     * 
     * @param file
     *            File or directory to get information on.
     * @return File protection info, or null if there is no protection info.
     * @throws IOException
     *             If the file cannot be read or opened.
     */
    public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;
}

public interface MAMFileProtectionInfo {
String getIdentity();
}
```

**Observação:** a marcação de identidade do arquivo é sensível ao modo offline. Os aspectos a seguir devem ser levados em conta.
* Se o Portal da Empresa não estiver instalado, os arquivos não poderão ser marcados segundo a identidade. 
* Se o Portal da Empresa estiver instalado, mas o aplicativo não tiver a política, os arquivos não poderão ser marcados segundo a identidade de forma confiável.
* Quando a marcação de identidade do arquivo se torna disponível, todos os arquivos criados anteriormente são tratados como pessoais (pertencentes à identidade de cadeia de caracteres vazia), a menos que o aplicativo tenha sido instalado anteriormente como um aplicativo gerenciado de identidade única. Nesse caso, eles serão tratados como pertencentes ao usuário registrado.

###<a name="data-protection"></a>Proteção de dados
Não é possível marcar um arquivo como pertencente a várias identidades. Aplicativos que precisam armazenar dados pertencentes a diferentes usuários no mesmo arquivo podem fazer isso manualmente usando os recursos fornecidos pelo ```MAMDataProtectionManager```. Isso permite que o aplicativo criptografe dados e os vincule a um usuário específico. Os dados criptografados são adequados para armazenamento em disco em um arquivo. Você pode consultar os dados associados à identidade e os dados podem ser descriptografados mais tarde. 

```
public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected 
 * input.
     * 
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function 
 *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The 
 *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original 
 *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method. 
 *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     * 
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the 
 * unprotected input.
     * 
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     * 
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     * 
     * @param input
     *            Input stream to get information on. Either this input 
 *            stream must have been returned by a previous call to 
     *            protect OR input.markSupported() must return true. 
 *            Otherwise it will be impossible to get protection info 
 *            without advancing the stream position. The stream must be 
 *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection 
 *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     * 
     * @param input
     *            Input bytes to get information on. These must be bytes 
 *            returned by a previous call to protect() or a copy of 
 *            such bytes.
     * @return Data protection info, or null if there is no protection 
 *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}
```
##<a name="content-providers"></a>Provedores de conteúdo
Se o aplicativo estiver fornecendo dados potencialmente corporativos diferentes de um ```ParcelFileDescriptor``` por meio de um ```ContentProvider```, o aplicativo deve chamar o método ```isProvideContentAllowed(String)``` do ```MAMContentProvider``` passando o proprietário ```UPN``` para o conteúdo. Se essa função retornar false, o conteúdo não pode ser retornado ao chamador. Descritores de arquivo retornados por meio de um provedor de conteúdo são manipulados automaticamente com base na identidade do arquivo.

##<a name="selective-wipe"></a>Apagamento seletivo
Se um aplicativo se registrar para notificação do ```WIPE_USER_DATA```, ele não receberá o benefício do comportamento de apagamento seletivo do SDK padrão. Para aplicativos com reconhecimento de várias identidades, isso pode ser mais significativo, uma vez que o apagamento seletivo padrão do MAM apagará apenas os arquivos que correspondem à identidade a ser apagada. Se estiver criando um aplicativo com reconhecimento de várias identidades, você pode se registrar para o ```WIPE_USER_AUXILIARY_DATA```, o que permitirá que você aproveite o comportamento de apagamento padrão do SDK. Essa notificação será enviada imediatamente antes de executar o apagamento seletivo padrão do SDK. Observe que um aplicativo nunca deve se registrar para ```WIPE_USER_DATA``` e ```WIPE_USER_AUXILIARY_DATA``` simultaneamente.

## <a name="known-platform-limitations"></a>Limitações conhecidas da plataforma 

### <a name="file-size-limitations"></a>Limitações de tamanho do arquivo 

No Android, as limitações do formato de arquivo executável Dalvik podem se tornar um problema para grandes bases de código que são executadas sem o ProGuard. Especificamente, as limitações a seguir podem ocorrer: 

* O limite de 65 mil para campos.

* O limite de 65 mil para métodos.

Ao incluir vários projetos, cada android:package obterá uma cópia do R que aumentará consideravelmente o número de campos conforme bibliotecas forem adicionadas. As recomendações a seguir podem ajudar a reduzir essa limitação:
 
* Todos os projetos de biblioteca devem compartilhar o mesmo android:package sempre que possível. Isso não falhará esporadicamente no campo, pois é essencialmente um problema de tempo de compilação.   Além disso, as versões mais recentes do SDK do Android vão pré-processar arquivos DEX para remover parte da redundância. Isso reduz a distância entre os campos ainda mais.

* Use das ferramentas de compilação do SDK do Android mais recentes disponíveis.

* Remova todas as bibliotecas desnecessárias e não utilizadas (por exemplo, `android.support.v4`)

### <a name="policy-enforcement-limitations"></a>Limitações de imposição de política

**Captura de tela**: o SDK não impõe um novo valor de configuração de captura de tela Atividades que já passaram por Activity.onCreate. Isso pode resultar em um período de tempo em que o aplicativo foi configurado para desabilitar as capturas de tela, mas capturas de tela ainda podem ser feitas.

**Usando resolvedores de conteúdo*: a política de transferência ou de recebimento pode bloquear ou bloquear parcialmente o uso de um resolvedor de conteúdo para acessar o provedor de conteúdo em outro aplicativo. Isso fará com que os métodos de ContentResolver retornem null ou gerem um valor de falha (por exemplo, `openOutputStream` lançará `FileNotFoundException` se bloqueado). O aplicativo pode determinar se uma falha de gravação de dados por meio de um resolvedor de conteúdo foi causada pela política (ou seria causada pela política), fazendo a chamada:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Serviços exportados**: o arquivo `AndroidManifest.xml` incluído no SDK de Aplicativos do Intune contém `MAMNotificationReceiverService`, que deve ser um serviço exportado para permitir que o Portal da Empresa envie notificações para um aplicativo esclarecido. O serviço verifica o chamador para garantir que apenas o Portal da Empresa tenha permissão para enviar notificações. 

## <a name="recommended-android-best-practices"></a>Práticas Recomendadas de Android 

O SDK do Intune mantém o contrato fornecido pela API do Android, embora condições de falha possam ser disparadas com mais frequência como resultado da aplicação de políticas. Essas práticas recomendadas do Android reduzirão a probabilidade de falha: 

* Funções do SDK do Android que podem retornar valores nulos agora têm maior alta probabilidade de ser nulas.  Para minimizar problemas, certifique-se de que verificações nulas estejam nos lugares certos.

* Recursos que podem ser verificados devem ser verificados por meio de suas APIs do SDK.

* Quaisquer funções derivadas devem chamar por meio de suas versões de superclasse.

* Evite o uso de qualquer API de forma ambígua. Por exemplo, `Activity.startActivityForResult/onActivityResult` sem verificar o requestCode causará um comportamento estranho.






<!--HONumber=Oct16_HO5-->


