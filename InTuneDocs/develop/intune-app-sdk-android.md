---
title: Guia do SDK de Aplicativo do Microsoft Intune para desenvolvedores do Android | Microsoft Docs
description: "O SDK de Aplicativo do Microsoft Intune para Android permite incorporar o MAM (gerenciamento de aplicativo móvel) do Intune em seu aplicativo Android."
keywords: SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 17fa23f1d04e22a2cb10452fe3a9425f7482a6de
ms.lasthandoff: 04/14/2017


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Guia do SDK de Aplicativo do Microsoft Intune para desenvolvedores do Android

> [!NOTE]
> Leia primeiro a [Visão geral do SDK de Aplicativo do Intune](intune-app-sdk.md), que explica os recursos atuais do SDK e descreve como preparar a integração em cada plataforma com suporte.

O SDK de Aplicativo do Microsoft Intune para Android permite incorporar o MAM (gerenciamento de aplicativo móvel) do Intune em seu aplicativo Android. Um aplicativo habilitado para MAM é um que esteja integrado com o SDK de Aplicativo do Intune. Ele permite que os administradores de TI implantem políticas para seu aplicativo móvel quando o Intune gerencia ativamente o aplicativo.

## <a name="whats-in-the-sdk"></a>O que está contido no SDK

O SDK de Aplicativos do Microsoft Intune é uma biblioteca Android padrão sem dependências externas. O SDK é composto por:  

* **Microsoft.Intune.MAM.SDK.jar**: as interfaces necessárias para habilitar o MAM e a interoperabilidade com o aplicativo de Portal da Empresa do Intune. Os aplicativos devem especificá-lo como uma referência de biblioteca Android.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: as interfaces necessárias para habilitar o MAM em aplicativos que utilizam a biblioteca de suporte do Android v4. Os aplicativos que precisam desse suporte devem referenciar diretamente o arquivo JAR.

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: as interfaces necessárias para habilitar o MAM em aplicativos que utilizam a biblioteca de suporte do Android v7. Os aplicativos que precisam desse suporte devem referenciar diretamente o arquivo JAR.

* **O diretório de recursos**: os recursos (como cadeias de caracteres) dos quais o SDK depende.

* **Microsoft.Intune.MAM.SDK.aar**: os componentes do SDK, com exceção dos arquivos JAR Support.V4 e Support.V7. Esse arquivo pode ser usado no lugar de componentes individuais se sua compilação do sistema der suporte a arquivos AAR.

* **AndroidManifest.xml**: os pontos de entrada adicionais e os requisitos da biblioteca.

* **THIRDPARTYNOTICES.TXT**: um aviso de atribuição que reconhece códigos de terceiros e/ou de OSS que serão compilados em seu aplicativo.

## <a name="requirements"></a>Requisitos

O SDK de Aplicativos do Intune é um projeto Android compilado. Como resultado, ele não é afetado pela versão do Android que o aplicativo usa para suas versões de API mínima ou de destino. O SDK dá suporte da API 14 do Android (Android 4.0 +) à API 24 do Android.

O SDK de Aplicativo do Intune para Android depende da presença do aplicativo de [Portal da Empresa](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) no dispositivo para habilitar as políticas de MAM. Para MAM sem registro de dispositivo, o usuário *não* precisa registrar o dispositivo usando o aplicativo do Portal da Empresa.


## <a name="how-the-intune-app-sdk-works"></a>Como o SDK de Aplicativos do Intune funciona

###<a name="entry-points"></a>Pontos de entrada

O SDK de Aplicativo do Intune requer alterações no código-fonte do aplicativo para habilitar as políticas de gerenciamento de aplicativo do Intune. Isso é feito por meio da substituição das classes base do Android por classes base equivalentes do Intune, cujos nomes têm o prefixo `MAM`. As classes do SDK estão entre a classe base do Android e a versão do próprio aplicativo derivada dessa classe. Usando uma atividade como exemplo, você acabará com uma hierarquia de herança que se parece com: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Por exemplo, quando `AppSpecificActivity` interage com seu pai (por exemplo, chamando `super.onCreate()`), `MAMActivity` é a superclasse.

Aplicativos Android típicos têm um modo único e têm acesso ao sistema por meio de seu objeto de [Contexto](https://developer.android.com/reference/android/content/Context.html). Aplicativos que incorporam o SDK de Aplicativo do Intune, por outro lado, têm modo dual. Esses aplicativos continuam a acessar o sistema por meio do objeto `Context`. Dependendo da base de `Activity` utilizada, o objeto `Context` será fornecido pelo Android ou será inteligentemente multiplexado entre uma exibição restrita do sistema e a fornecida pelo Android `Context`.

Quando um [ponto de entrada](https://developer.android.com/guide/components/fundamentals.html) do Android for substituído por seu equivalente de MAM, uma versão de MAM do ciclo de vida do ponto de entrada deve ser usada (com exceção da classe `MAMApplication`).

Por exemplo, ao derivar de `MAMActivity`, em vez de substituir `onCreate` e chamar `super.onCreate`, `Activity` deve substituir `onMAMCreate` e chamar `super.onMAMCreate`. Isso permite que o Intune restrinja a inicialização de `Activity` (entre outros) em determinados casos.


###<a name="sdk-permissions"></a>Permissões do SDK

O SDK de Aplicativo do Intune exige três [permissões de sistema do Android](https://developer.android.com/guide/topics/security/permissions.html) em aplicativos que o integram:

* `android.permission.GET_ACCOUNTS`  (solicitada em tempo de execução se necessário)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

A Biblioteca de Autenticação do Azure Active Directory ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) exige essas permissões para realizar a autenticação agenciada. Se essas permissões não forem concedidas ao aplicativo ou revogadas pelo usuário, os fluxos de autenticação que exigem o agente (o aplicativo de Portal da Empresa) serão desabilitados.


###<a name="company-portal-app"></a>Aplicativo do Portal da Empresa

Por que o aplicativo de Portal da Empresa é exigido? Quando o aplicativo do Portal da Empresa é instalado no dispositivo e recupera a política de restrição de aplicativo para o usuário do serviço Intune, os pontos de entrada do SDK são inicializados de forma assíncrona. A inicialização é necessária somente quando o Android cria o processo no início. Durante a inicialização, uma conexão é estabelecida com o aplicativo do Portal da Empresa e a política é recuperada do aplicativo.  

> [!NOTE]
> Quando o aplicativo do Portal da Empresa não estiver presente no dispositivo, o comportamento do aplicativo habilitado para o Intune não será alterado e ele se comportará como um aplicativo normal.


## <a name="how-to-integrate-with-the-intune-app-sdk"></a>Como integrar o SDK de Aplicativos do Intune

Como dissemos anteriormente, o SDK requer alterações no código-fonte do aplicativo para habilitar as políticas de gerenciamento do aplicativo. Aqui estão as etapas necessárias para habilitar o MAM em seu aplicativo.

### <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Substitua classes, métodos e atividades por seus equivalentes com MAM (obrigatório)

As classes base do Android devem ser substituídas por seus equivalentes com MAM. Para fazer isso, localize todas as instâncias das classes listadas na tabela a seguir e as substitua pelo SDK de Aplicativo do Intune equivalente.

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
| android.app.PendingIntent | MAMPendingIntent* |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder (necessário apenas se o Associador não for gerado de uma interface da linguagem IDL do Android (AIDL)) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Suppout.v4.jar**:

| MAM do Intune da classe do Android | Substituição do SDK de Aplicativo do Intune |
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
>Lembre-se: quando um [ponto de entrada](https://developer.android.com/guide/components/fundamentals.html) do Android for substituído por seu equivalente com MAM, a versão com MAM do ciclo de vida do ponto de entrada deve ser usada (com exceção da classe `MAMApplication`).
>
>Por exemplo, ao derivar de `MAMActivity`, em vez de substituir `onCreate` e chamar `super.onCreate`, `Activity` deve substituir `onMAMCreate` e chamar `super.onMAMCreate`. Isso permite que o Intune restrinja a inicialização de `Activity` (entre outros) em determinados casos.

#### <a name="pendingintent-classes-and-renamed-methods"></a>Classes PendingIntent e métodos renomeados

Após derivar de um dos pontos de entrada com MAM, é seguro usar `Context` normalmente – por exemplo, iniciando as classes `Activity` e usando `PackageManager`.  

As classes `PendingIntent` são uma exceção a essa regra. Ao chamar essas classes, é necessário alterar o nome de classe. Por exemplo, em vez de `PendingIntent.get*`, você deve usar o método `MAMPendingIntent.get*`. Depois disso, você pode usar o `PendingIntent` resultante, como de costume.

Em alguns casos, um método disponível na classe Android foi marcado como final na classe de MAM de substituição. Nesse caso, a classe de MAM de substituição fornece um método nomeado da mesma forma (em geral, com o sufixo `MAM`), que deve ser substituído em vez disso. Por exemplo, em vez de substituir `ContentProvider.query`, você substituiria `MAMContentProvider.queryMAM`. O compilador Java deve impor as restrições finais para evitar a substituição acidental do método original em vez do MAM equivalente.

###<a name="enable-features-that-require-app-participation"></a>Habilitar recursos que exigem a participação do aplicativo

Há algumas políticas que o SDK não pode implementar por conta própria. O aplicativo pode controlar seu comportamento para conquistar esses recursos usando várias APIs que podem ser encontradas na interface `AppPolicy` a seguir.

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

### <a name="enable-it-control-over-app-saving-behavior"></a>Habilitar o controle do setor de TI sobre o comportamento de salvamento do aplicativo

Muitos aplicativos implementam recursos que permitem que o usuário salve arquivos localmente ou em um serviço de armazenamento em nuvem. O SDK de Aplicativo do Azure ajuda administradores de TI a se protegerem contra vazamento de dados aplicando as restrições de política da forma que acharem melhor para a organização.  Uma das políticas que o setor de TI pode controlar é se o usuário pode salvar em um armazenamento de dados "pessoal" não gerenciado. Isso inclui salvar localmente, em cartões SD ou em serviços de backup de terceiros.

A participação do aplicativo é necessária para habilitar o recurso. Se o aplicativo permitir salvamento em locais na nuvem ou pessoais diretamente do aplicativo, você deverá implementar esse recurso para garantir que o administrador de TI possa controlar se é permitido salvar em um local.   

Para determinar se a política é aplicada, o aplicativo pode fazer a chamada a seguir. Essa chamada permite que o aplicativo saiba se a política atual do administrador do Intune permite salvar em um repositório pessoal. O aplicativo pode, então, aplicar a política, pois ele está ciente de que o armazenamento de dados pessoal está disponível para o usuário por meio do aplicativo.

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

> [!NOTE]
> `MAMComponents.get(AppPolicy.class)` sempre retornará uma política de aplicativo não nula, mesmo que o dispositivo ou aplicativo não esteja sob uma política de gerenciamento do Intune.

### <a name="let-the-app-detect-if-a-pin-policy-is-required"></a>Permitir que o aplicativo detecte se a política de PIN é necessária

Para algumas restrições de aplicativo do Intune, talvez você queira que o aplicativo desabilite algumas das suas funcionalidades para não duplicar a funcionalidade no SDK de Aplicativo do Intune. Por exemplo, se o aplicativo tiver sua própria experiência do usuário de PIN, você poderá desabilitá-la se o SDK estiver configurado para exigir que o usuário insira um PIN.

Para determinar se uma política de PIN do Intune será configurada para exigir um PIN do aplicativo na inicialização, o aplicativo poderá fazer a chamada a seguir:

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="register-for-notifications-from-the-sdk"></a>Registrar-se para notificações do SDK  

O SDK de Aplicativo do Intune permite que seu aplicativo controle o comportamento de algumas políticas, como um apagamento remoto, quando elas são implantadas pelo administrador de TI. Quando um administrador de TI implanta tal política, o serviço do Intune envia uma notificação para o SDK.

O aplicativo deve ser registrado para receber notificações do SDK, criando uma classe `MAMNotificationReceiver` e registrando-a com `MAMNotificationReceiverRegistry`. Isso é feito fornecendo o receptor e o tipo de notificação desejada em `App.onCreate`, como mostra o exemplo a seguir:

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

`MAMNotificationReceiver` apenas recebe notificações do serviço do Intune. O SDK lida com algumas notificações diretamente. Outras notificações exigem a participação do aplicativo.

Um aplicativo *deve* retornar true ou false de uma notificação. Ele deve sempre retornar true, a menos que alguma ação que ele tentou executar como resultado da notificação falhe. Essa falha pode ser relatada ao serviço do Intune. Um exemplo de cenário a ser relatado é se o aplicativo falhar ao apagar dados do usuário após o administrador de TI iniciar um apagamento.

É seguro bloquear em `MAMNotificationReceiver.onReceive` porque seu retorno de chamada não está em execução no thread da interface do usuário.

A interface `MAMNotificationReceiver` a seguir é definida no SDK:

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

###<a name="types-of-notifications"></a>Tipos de notificações

As notificações a seguir são enviadas ao aplicativo. Algumas delas podem exigir a participação do aplicativo.

* **`WIPE_USER_DATA`**: essa notificação é enviada em uma classe `MAMUserNotification`. Quando a notificação é recebida, o aplicativo deve excluir todos os dados associados à identidade "corporativa" passada com `MAMUserNotification`. Atualmente, essa notificação é enviada durante o cancelamento do registro do serviço do Intune. O nome principal do usuário geralmente é especificado durante o processo de registro. Se você se registrar para essa notificação, seu aplicativo deve garantir que todos os dados do usuário tenham sido excluídos. Se você não se registrar nela, o aplicativo realizará o comportamento de apagamento seletivo padrão será executado.

* **`WIPE_USER_AUXILIARY_DATA`**: os aplicativos podem se registrar para essa notificação se quiserem que o SDK de Aplicativo do Intune execute o comportamento de apagamento seletivo padrão, mas ainda desejarem remover alguns dados auxiliares quando o apagamento ocorrer.  

* **`REFRESH_POLICY`**: essa notificação é enviada em `MAMUserNotification`. Quando a notificação é recebida, qualquer política do Intune armazenada em cache deve ser invalidada e atualizada. Geralmente, o SDK lida com essa tarefa. Porém, o aplicativo deve lidar com essa tarefa se a política for usada de modo persistente.



### <a name="protection-of-backup-data"></a>Proteção de dados de backup

A partir do Android Marshmallow (API 23), o Android tem duas formas para um aplicativo fazer backup de seus dados. Cada opção está disponível para seu aplicativo e requer etapas diferentes para garantir que a proteção de dados do Intune seja implementada corretamente. Leia mais sobre os métodos de backup no [Guia da API do Android](http://developer.android.com/guide/topics/data/backup.html).

#### <a name="automatic-backup-for-apps"></a>Backup automático de aplicativos

O Android começou a oferecer [backups completos automáticos](https://developer.android.com/guide/topics/data/autobackup.html) para aplicativos em dispositivos Android Marshmallow, independentemente da API de destino do aplicativo. Se você definir explicitamente `android:allowBackup` como false no arquivo AndroidManifest.xml, o aplicativo nunca será enfileirado para backups pelo Android e os dados "corporativos" permanecerão no aplicativo. Nesse caso, nenhuma ação adicional é necessária.

Por padrão, o atributo `android:allowBackup` é definido como true, mesmo que `android:allowBackup` não esteja especificado no arquivo de manifesto. Isso significa que todos os dados do aplicativo são copiados automaticamente para a conta do Google Drive do usuário, um comportamento padrão que representa um *risco de vazamento de dados*. O SDK requer as alterações a seguir para garantir que a proteção de dados seja aplicada. É importante seguir estas diretrizes para proteger os dados do cliente corretamente se você quiser que o aplicativo seja executado em dispositivos Android Marshmallow.  

Se você não tiver gravado um agente de backup para fazer backup do aplicativo usando `MAMBackupAgent` ou `MAMBackupAgentHelper`, será necessário considerar e controlar como o backup automático carregará os dados do aplicativo. O Intune permite que você use todos os [recursos de backup automático](https://developer.android.com/guide/topics/data/autobackup.html) disponíveis no Android, incluindo a capacidade de definir regras personalizadas em XML. Porém, é necessário seguir estas regras para ajudar a proteger seus dados:

1. Use o padrão `MAMBackupAgent` para permitir backups completos automáticos que sejam compatíveis com a política do Intune. Coloque `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` no manifesto do seu aplicativo.

2. Ao decidir o tipo de backup completo que seu aplicativo deve receber (filtrado, não filtrado ou nenhum), defina o atributo `android:fullBackupContent` como true, false ou um recurso XML em seu aplicativo. Copie tudo o que você colocar em `android:fullBackupContent` em uma marca de metadados nomeada como `com.microsoft.intune.mam.FullBackupContent`.

    Por exemplo, se você quiser que seu aplicativo tenha backups completos de acordo com regras personalizadas em um arquivo XML, forneça um recurso sob a marca de metadados `com.microsoft.intune.mam.FullBackupContent` em seu manifesto, como:
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



#### <a name="keyvalue-backup"></a>Backups de chave/valor

A opção backups de chave/valor está disponível para todas as APIs e usa `BackupAgentHelper` e `BackupAgent`.

##### <a name="backupagenthelper"></a>BackupAgentHelper

`BackupAgentHelper` é muito mais simples de implementar do que `BackupAgent` em termos de funcionalidade nativa do Android e integração de MAM. `BackupAgentHelper` permite que você registre arquivos inteiros e preferências compartilhadas, como `FileBackupHelper` ou `SharedPreferencesBackupHelper`, respectivamente. Em seguida, elas são adicionadas à `BackupAgentHelper` no momento da criação.

##### <a name="backupagent"></a>BackupAgent

`BackupAgent` permite que você seja muito mais explícito sobre de quais dados é feito o backup. Essa opção significa que você não poderá aproveitar a estrutura de backup do Android. Como você é responsável pela implementação, mais etapas são necessárias para garantir a proteção de dados apropriada do MAM. Uma vez que a maioria do trabalho é passado para você, o desenvolvedor, integração do MAM é um pouco mais envolvida.

###### <a name="app-does-not-have-a-backup-agent"></a>O aplicativo não tem um agente de backup

Essas são as opções do desenvolvedor quando `android:allowBackup =true`.

####### <a name="full-backup-according-to-a-configuration-file"></a>Backup completo de acordo com um arquivo de configuração

Forneça um recurso sob a marca de metadados `com.microsoft.intune.mam.FullBackupContent` em seu manifesto. Por exemplo:     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Adicione o seguinte atributo na marca `<application>` : `android:fullBackupContent="@xml/my_scheme"`, em que `my_scheme` é um recurso XML em seu aplicativo.

####### <a name="full-backup-without-exclusions"></a>Backup completo sem exclusões

Forneça uma marca no manifesto, como `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />`.

Adicione o seguinte atributo na marcação `<application>`: `android:fullBackupContent="true"`.

###### <a name="app-has-a-backup-agent"></a>O aplicativo tem um agente de backup

Siga as recomendações neste guia para `BackupAgent` e `BackupAgentHelper`.

Considere a possibilidade de usar `MAMDefaultFullBackupAgent`, que fornece backup fácil no Android Marshmallow.

##### <a name="before-your-backup"></a>Antes do backup

Antes de iniciar o backup, é necessário verificar se os arquivos ou buffers de dados de que você pretende fazer backup têm permissão para backup. Uma função `isBackupAllowed` lhe foi dada em `MAMFileProtectionManager` e `MAMDataProtectionManager` para verificar isso. Se o buffer de dados ou arquivo não tiver permissão para backup, não tente continuar o utilizando em seu backup.

Em algum momento durante o backup, se desejar que as identidades dos arquivos verificados na etapa 1 façam backup, você deverá chamar `backupMAMFileIdentity(BackupDataOutput data, File … files)` com os arquivos dos quais planeja extrair dados. Isso criará automaticamente novas entidades de backup e as gravará em `BackupDataOutput` para você. Essas entidades serão consumidas automaticamente após a restauração.

#### <a name="azure-directory-authentication-library-setup"></a>Configuração da Biblioteca de Autenticação do Active Directory  

O SDK de Aplicativo do Intune usa a ADAL para seus cenários de inicialização condicional e autenticação. Esses cenários exigem que os aplicativos tenham algum valor de configuração do Azure Active Directory (Azure AD). Os valores de configuração são comunicados para o SDK por meio dos metadados `AndroidManifest` .

Para configurar seu aplicativo e habilitar a autenticação adequada, adicione o seguinte ao nó de aplicativo em `AndroidManifest`. Algumas dessas configurações são necessárias apenas se o aplicativo usa ADAL para autenticação em geral. Nesse caso, você precisará dos valores específicos usados pelo aplicativo para se registrar com o Azure AD. Isso garante que a autenticação do usuário não seja solicitada duas vezes, pois o Azure AD reconhece dois valores de registro separados: um do aplicativo e um do SDK.

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

##### <a name="common-adal-configurations"></a>Configurações comuns do ADAL

A seguir estão as configurações comuns para os valores explicados acima.

###### <a name="app-does-not-integrate-adal"></a>O aplicativo não se integra ao ADAL

* A autoridade deve ser configurada para o ambiente desejado em que as contas do Azure AD foram configuradas.

* O SkipBroker deve ser definido como true.

###### <a name="app-integrates-adal"></a>O aplicativo integra o ADAL

* A autoridade deve ser configurada para o ambiente desejado em que as contas do Azure AD foram configuradas.

* A ID do cliente deve ser definida como ID cliente do aplicativo.

* `NonBrokerRedirectURI` deve ser definido como um URI de redirecionamento válido para o aplicativo. Ou `urn:ietf:wg:oauth:2.0:oob` deve ser definido como um URI de redirecionamento válido do Azure AD.

* O SkipBroker deve ser definido como false (ou absent).

* O Azure AD deve ser configurado para aceitar o URI de redirecionamento do agente.

###### <a name="app-integrates-adal-but-does-not-support-the-azure-ad-authenticator-app"></a>O aplicativo se integra ao ADAL, mas não dá suporte ao aplicativo do Autenticador do Azure AD

* A autoridade deve ser configurada para o ambiente desejado em que as contas do Azure AD foram configuradas.

* A ID do cliente deve ser definida como ID cliente do aplicativo.

* `NonBrokerRedirectURI` deve ser definido como um URI de redirecionamento válido para o aplicativo. Ou `urn:ietf:wg:oauth:2.0:oob` deve ser definido como um URI de redirecionamento válido do Azure AD.

#### <a name="logging-in-the-sdk"></a>Registro no SDK

O registro em log é feito por meio da estrutura `java.util.logging` . Para receber os logs, configure o registro conforme descrito no [Guia técnico de Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Dependendo do aplicativo, `App.onCreate` geralmente é o melhor local para iniciar o registro. Observe que as mensagens de log são criptografadas pelo nome de classe, que pode estar oculto.

###<a name="multi-identity"></a>Várias identidades

Por padrão, o SDK de Aplicativo do Intune aplica uma política ao aplicativo como um todo. Várias identidades é um recurso do MAM que você pode habilitar para aplicar uma política em um nível por identidade. Ele requer uma participação significativamente maior do aplicativo do que outros recursos de MAM. O aplicativo precisa informar o SDK do aplicativo quando pretende alterar a identidade ativa. O SDK também deve notificar o aplicativo quando uma alteração de identidade for necessária.

Atualmente, há suporte para apenas uma identidade gerenciada. Depois que o usuário registrar o dispositivo ou o aplicativo, o SDK usará essa identidade e a considerará a identidade gerenciada primária. Outros usuários no aplicativo são tratados como não gerenciados, com configurações de política irrestritas.

Observe que uma identidade é definida simplesmente como uma cadeia de caracteres. As identidades não diferenciam maiúsculas de minúsculas. As solicitações de identidade ao SDK podem não retornar o mesmo esquema de maiúsculas e minúsculas usado originalmente ao definir a identidade.

####<a name="enabling-multi-identity"></a>Habilitando várias identidades

Por padrão, considera-se que todos os aplicativos são aplicativos de identidade única. Um aplicativo declara que reconhece várias identidades colocando os seguintes metadados no manifesto do Android.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
####<a name="setting-the-identity"></a>Definindo a identidade

É possível definir a identidade do aplicativo nos níveis a seguir:

1. Nível de processo

2. Nível de contexto (geralmente, `Activity`)

3. Nível de thread

Uma identidade definida no nível do thread substitui uma identidade definida no nível de `Context`, que substitui uma identidade definida no nível de processo. Uma identidade definida em `Context` é usada apenas quando apropriado. Operações de E/S de arquivo, por exemplo, não têm um `Context` associado. Os seguintes métodos no `MAMPolicyManager` podem ser usados para definir a identidade e recuperar os valores de identidade definidos anteriormente.

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
Você também pode limpar a identidade do aplicativo definido-a como nula. A cadeia de caracteres vazia pode ser usada como uma identidade que nunca terá restrições. Todos os métodos para definir a identidade relatam os valores de resultado via ``` MAMIdentitySwitchResult```. Quatro valores podem ser retornados:

* **SUCCEEDED**: a alteração de identidade foi bem-sucedida.

* **NOT_ALLOWED**: não é permitido alterar a identidade. Isso ocorrerá se for feita uma tentativa de mudar para outro usuário corporativo que pertence à mesma empresa que o usuário registrado. Ocorrerá também se for feita uma tentativa de definir a identidade da interface do usuário (`Context`) quando uma identidade diferente estiver definida no thread atual.

* **CANCELLED**: o usuário cancelou a alteração de identidade, normalmente pressionando o botão Voltar em uma solicitação de PIN/autenticação.

* **FAILED**: ocorreu uma falha na alteração da identidade por um motivo não especificado.

No caso da definição de uma identidade de `Context`, o resultado é relatado de forma assíncrona. Se `Context` for uma classe `Activity`, ele não será conhecido se a identidade foi alterada com êxito até após a inicialização condicional. A inicialização condicional pode exigir que usuário insira um PIN ou a credencial corporativa completa. Espera-se que o aplicativo implemente um ```MAMSetUIIdentityCallback``` para receber esse resultado, embora seja permitido passar null para esse parâmetro.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
}
```

Também é possível definir a identidade de uma atividade diretamente por meio de um método em `MAMActivity`, em vez de chamar ```MAMPolicyManager.setUIPolicyIdentity```. Você pode fazer isso usando os método a seguir:

 ```public final void switchMAMIdentity(final String newIdentity);```

Os aplicativos também podem substituir um método em `MAMActivity` para serem notificados do resultado das tentativas de alterar a identidade da atividade.

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

> [!NOTE]
> Alterar a identidade pode exigir a recriação da atividade. Nesse caso, o retorno de chamada ```onSwitchMAMIdentityComplete``` será entregue para a nova instância da atividade.


####<a name="implicit-identity-changes"></a>Alterações de identidade implícitas

Além da capacidade do aplicativo de definir a identidade, um thread ou a identidade de um contexto pode mudar com base na entrada de dados de outro aplicativo habilitado para MAM. Por exemplo, se uma atividade for iniciada de uma classe `Intent` enviada por outro aplicativo com MAM, a identidade da atividade será definida com base na identidade em vigor no outro aplicativo no momento em que a classe `Intent` foi enviada.

Para serviços, a identidade do thread será definida da mesma forma pela duração de uma chamada `onStart` ou `onBind`. Chamadas para `Binder` retornadas de `onBind` também definirão temporariamente a identidade do thread. De forma semelhante, chamadas para um ```ContentProvider``` definirão a identidade do thread no período de sua duração.

Além disso, a interação do usuário com uma atividade pode causar uma mudança de identidade implícita. Por exemplo, se um usuário cancelar após um prompt de autorização durante o ```Resume```, ocorrerá uma mudança implícita para uma identidade vazia.
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
A parte ```AppIdentitySwitchReason``` captura a origem da mudança implícita. Ela pode aceitar os valores ```CREATE```, ```RESUME_CANCELLED``` e ```NEW_INTENT```.  O motivo ```RESUME_CANCELLED``` é usado quando a atividade é retomada e faz com que o PIN, a autenticação ou outra interface do usuário de conformidade seja exibida; o usuário tenta cancelar para sair dessa interface do usuário, normalmente usando o botão Voltar.
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
```AppIdentitySwitchResult``` é ```SUCCESS``` ou ```FAILURE```.

O método ```onMAMIdentitySwitchRequired``` é chamado para todas as mudanças de identidade implícitas, exceto por aquelas feitas por meio de um `Binder` retornado de ```MAMService.onMAMBind```. As implementações padrão de ```onMAMIdentitySwitchRequired``` chamam ```reportIdentitySwitchResult(FAILURE)``` imediatamente quando o motivo é ```RESUME_CANCELLED``` e ```reportIdentitySwitchResult(SUCCESS)``` em todos os outros casos.

Na maioria dos aplicativos, provavelmente não será necessário bloquear ou atrasar uma mudança de identidade de maneira diferente. Porém, se um aplicativo precisar fazê-lo, considere os seguintes pontos:

* Se uma mudança de identidade estiver bloqueada, o resultado será o mesmo, como se as configurações de compartilhamento de ```Receive``` tivessem proibido a entrada de dados.

* Se um serviço estiver em execução no thread principal, ```reportIdentitySwitchResult``` *deve* ser chamado de forma síncrona ou o thread da interface do usuário falhará.

* Para criação de ```Activity```, ```onMAMIdentitySwitchRequired``` será chamado antes de ```onMAMCreate```. Se o aplicativo precisar mostrar a interface do usuário para determinar se deve permitir a mudança de identidade, a interface do usuário deverá ser exibida usando uma atividade diferente.

* Em ```Activity```, quando for solicitada uma mudança para a identidade vazia com o motivo igual a ```RESUME_CANCELLED```, o aplicativo deverá modificar a atividade retomada para exibir dados consistentes com essa mudança de identidade. Se isso não for possível, o aplicativo deverá recusar a mudança. O usuário será solicitado novamente a obedecer a política para retomar a identidade (por exemplo, recebendo a tela de entrada de PIN).

> [!NOTE]
> Um aplicativo com várias identidades sempre receberá dados de entrada de aplicativos gerenciados e não gerenciados. É responsabilidade do aplicativo tratar dados de identidades gerenciadas de maneira gerenciada. Se uma identidade solicitada for gerenciada ```(MAMPolicyManager.getIsIdentityManaged)```, mas o aplicativo não puder usar a conta (por exemplo, porque contas, como contas de email, devem ser configuradas no aplicativo primeiro), a mudança de identidade deverá ser recusada.

###<a name="file-protection"></a>Proteção de arquivo

Cada arquivo tem uma identidade associada no momento da criação, com base na identidade do thread e do processo. Essa identidade é usada para a criptografia de arquivos e o apagamento seletivo. Somente arquivos cuja identidade tem uma política que exige criptografia serão criptografados. O apagamento seletivo padrão do SDK apagará apenas arquivos associados à identidade para a qual um apagamento foi solicitado. O aplicativo pode consultar ou alterar a identidade de um arquivo usando ```MAMFileProtectionManager```.
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

> [!NOTE]
> A marcação de identidade do arquivo é sensível ao modo offline. Considere os seguintes pontos:
> * Se o aplicativo do Portal da Empresa não estiver instalado, os arquivos não poderão ser marcados segundo a identidade.
>
> * Se o aplicativo do Portal da Empresa estiver instalado, mas o aplicativo não tiver uma política, os arquivos não poderão ser marcados segundo a identidade de forma confiável.
>
> * Quando a marcação de identidade do arquivo se torna disponível, todos os arquivos criados anteriormente são tratados como pessoais (pertencentes à identidade de cadeia de caracteres vazia), a menos que o aplicativo tenha sido instalado anteriormente como um aplicativo gerenciado de identidade única. Nesse caso, eles serão tratados como pertencentes ao usuário registrado.

####<a name="data-protection"></a>Proteção de dados

Não é possível marcar um arquivo como pertencente a várias identidades. Aplicativos que precisam armazenar dados pertencentes a diferentes usuários no mesmo arquivo podem fazer isso manualmente usando os recursos fornecidos pelo ```MAMDataProtectionManager```. Isso permite que o aplicativo criptografe dados e os vincule a um usuário específico. Os dados criptografados são adequados para armazenamento em disco em um arquivo. É possível consultar os dados associados à identidade e os dados podem ser descriptografados posteriormente.

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
###<a name="content-providers"></a>Provedores de conteúdo

Se o aplicativo estiver fornecendo dados potencialmente corporativos diferentes de um ```ParcelFileDescriptor``` por meio de um ```ContentProvider```, o aplicativo deverá chamar o método ```isProvideContentAllowed(String)``` do ```MAMContentProvider``` passando o proprietário ```UPN``` para o conteúdo. Se essa função retornar false, o conteúdo não poderá ser retornado ao chamador. Descritores de arquivo retornados por meio de um provedor de conteúdo são manipulados automaticamente com base na identidade do arquivo.

###<a name="selective-wipe"></a>Apagamento seletivo

Se um aplicativo se registrar para notificação do ```WIPE_USER_DATA```, ele não receberá o benefício do comportamento de apagamento seletivo do SDK padrão. Para aplicativos com reconhecimento de várias identidades, isso pode ser mais significativo, uma vez que o apagamento seletivo padrão do MAM apagará apenas os arquivos que correspondem à identidade a ser apagada.

Se você estiver compilando um aplicativo com reconhecimento de várias identidades, será possível se registrar para ```WIPE_USER_AUXILIARY_DATA```. Essa notificação permite aproveitar o comportamento de apagamento padrão do SDK. Essa notificação será enviada imediatamente antes de executar o apagamento seletivo padrão do SDK. Observe que um aplicativo nunca deve se registrar para ```WIPE_USER_DATA``` e ```WIPE_USER_AUXILIARY_DATA``` simultaneamente.

### <a name="known-platform-limitations"></a>Limitações conhecidas da plataforma

#### <a name="file-size-limitations"></a>Limitações de tamanho do arquivo

No Android, as limitações do formato de arquivo executável Dalvik podem se tornar um problema para grandes bases de código executadas sem o ProGuard. Especificamente, as limitações a seguir podem ocorrer:

* O limite de 65 mil para campos

* O limite de 65 mil para métodos

Ao incluir vários projetos, cada `android:package` obterá uma cópia do R que aumentará consideravelmente o número de campos conforme as bibliotecas forem adicionadas. As recomendações a seguir podem ajudar a reduzir essa limitação:

* Todos os projetos de biblioteca devem compartilhar o mesmo `android:package` sempre que possível. Isso não falhará esporadicamente no campo, pois é essencialmente um problema de tempo de build. Além disso, as versões mais recentes do SDK do Android vão pré-processar arquivos DEX para remover parte da redundância. Isso reduz a distância entre os campos ainda mais.

* Use das ferramentas de compilação do SDK do Android mais recentes disponíveis.

* Remova todas as bibliotecas desnecessárias e não utilizadas (por exemplo, `android.support.v4`).

#### <a name="policy-enforcement-limitations"></a>Limitações de imposição de política

**Captura de tela**: o SDK não impõe um novo valor de configuração de captura de tela em classes `Activity` que já passaram por `Activity.onCreate`. Isso pode resultar em um período de tempo em que o aplicativo foi definido para desabilitar as capturas de tela, mas elas ainda podem ser feitas.

**Usando resolvedores de conteúdo**: a política de transferência ou de recebimento pode bloquear ou bloquear parcialmente o uso de um resolvedor de conteúdo para acessar o provedor de conteúdo em outro aplicativo. Isso fará com que os métodos `ContentResolver` retornem null ou gerem um valor de falha. (Por exemplo, `openOutputStream` lançará `FileNotFoundException` se bloqueado.) O aplicativo pode fazer essa chamada para verificar se uma política causou (ou provocou) uma falha de gravação de dados por meio de um resolvedor de conteúdo:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Serviços exportados**: o arquivo `AndroidManifest.xml` incluído no SDK de Aplicativo do Intune tem `MAMNotificationReceiverService`. Isso deve ser um serviço exportado para permitir que o aplicativo do Portal da Empresa envie notificações a um aplicativo habilitado. O serviço verifica o chamador para garantir que apenas o aplicativo Portal da Empresa tenha permissão para enviar notificações.

### <a name="android-best-practices"></a>Práticas recomendadas para o Android

O SDK do Intune mantém o contrato fornecido pela API do Android, embora condições de falha possam ser disparadas com mais frequência como resultado da aplicação de políticas. Essas práticas recomendadas do Android reduzirão a probabilidade de falha:

* As funções do SDK do Android que podem retornar valores nulos agora têm maior probabilidade de serem nulas. Para minimizar problemas, certifique-se de que verificações nulas estejam nos locais certos.

* Para recursos que você pode verificar, use as APIs do SDK para verificá-los.

* Quaisquer funções derivadas devem chamar por meio de suas versões de superclasse.

* Evite o uso de qualquer API de forma ambígua. Por exemplo, usar `Activity.startActivityForResult/onActivityResult` sem verificar o `requestCode` causará um comportamento estranho.

