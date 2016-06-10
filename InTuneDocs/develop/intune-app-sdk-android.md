---
# required metadata

title: Guia do SDK de Aplicativo do Microsoft Intune para Desenvolvedores do Android | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Guia do SDK de Aplicativos do Microsoft Intune para Desenvolvedores do Android

> [!NOTE] Leia primeiro a [Intune App SDK overview](intune-app-sdk.md) (Visão geral do SDK de Aplicativo do Intune), que explica os recursos atuais do SDK e descreve a preparação para a integração em cada plataforma com suporte. 

# Novidades no SDK 

O SDK de Aplicativos do Microsoft Intune é uma biblioteca Android padrão sem dependências externas. 
O SDK é composto de:  

* **`Microsoft.Intune MAM.SDK.jar`**: as interfaces necessárias para habilitar o MAM em um aplicativo, além de habilitar a interoperabilidade com o aplicativo Portal da Empresa do Microsoft Intune. Os aplicativos devem especificá-lo como uma referência de biblioteca Android.

*  **`Microsoft.Intune.MAM.SDK.Support.v4.jar`**: as interfaces necessárias para habilitar o MAM em aplicativos que utilizam a biblioteca de suporte do Android v4.  Os aplicativos que precisam desse suporte devem referenciar diretamente o arquivo jar. 

* **`Microsoft.Intune.MAM.SDK.Support.v7.jar`**: as interfaces necessárias para habilitar o MAM em aplicativos que utilizam a biblioteca de suporte do Android v7.   Os aplicativos que precisam desse suporte devem referenciar diretamente o arquivo jar

* **O diretório de recursos**: os recursos (como cadeias de caracteres) dos quais o SDK depende. 

* **`Microsoft.Intune.MAM.SDK.aar`**: os componentes do SDK, exceto os jars Support.V4 e Support.V7. Esse arquivo pode ser usado no lugar de componentes individuais se sua compilação do sistema der suporte a arquivos AAR.

* **`AndroidManifest.xml`**: os pontos de entrada adicionais e os requisitos da biblioteca. 

* **`THIRDPARTYNOTICES.TXT`**: um aviso de atribuição que reconhece códigos de terceiros e/ou códigos de sistemas operacionais que serão compilados em seu aplicativo. 

# Requisitos 

O SDK de Aplicativos do Intune é um projeto Android compilado. Como resultado, ele é amplamente independente da versão do Android que o aplicativo usa para suas versões de API mínima ou de destino. O SDK dá suporte à API do Android 14 (Android 4.0 +) ao Android 24. 

# Como o SDK de Aplicativos do Intune funciona 

O SDK de Aplicativos do Intune requer alterações no código-fonte do aplicativo para habilitar as políticas de gerenciamento do aplicativo. Isso é feito por meio da substituição das classes base do Android por classes gerenciadas equivalentes, mencionadas no documento com o prefixo `MAM`. As classes do SDK estão entre a classe base do Android e a versão do próprio aplicativo derivada dessa classe.  Usando uma atividade como exemplo, você acabará com uma hierarquia de herança que se parece com: `Activity ->MAMActivity->AppSpecificActivity`.

Quando `AppSpecificActivity` quiser interagir com seu pai, por exemplo, `super.onCreate())`, `MAMActivity` será a superclasse apesar de estar na hierarquia de herança e substituir alguns métodos. Aplicativos Android têm um modo único e têm acesso a todo o sistema por meio de seu objeto de Contexto.  Aplicativos que incorporam o SDK de Aplicativos do Intune, por outro lado, têm dois modos, conforme os aplicativos continuam acessando o sistema por meio do objeto de Contexto, mas, dependendo da Atividade de base usada, o objeto de Contexto também será fornecido pelo Android ou vai multiplexar de forma inteligente entre uma exibição restrita do sistema e o Contexto fornecido pelo Android.

O SDK de Aplicativos do Intune para Android depende da presença do aplicativo de Portal da Empresa no dispositivo para habilitar as políticas de MAM. Quando o aplicativo de Portal da Empresa não estiver presente, o comportamento do aplicativo habilitado para MAM não será alterado e ele atuará como qualquer outro aplicativo móvel. Quando o Portal da Empresa estiver instalado e tiver a política para o usuário, os pontos de entrada do SDK serão inicializados assincronamente. A inicialização só é necessária quando o processo é criado inicialmente pelo Android. Durante a inicialização, uma conexão é estabelecida com o aplicativo de Portal da Empresa e a política de restrição de aplicativo é baixada.  

# Como integrar o SDK de Aplicativos do Intune
 
Conforme descrito anteriormente, o SDK requer alterações no código-fonte do aplicativo para habilitar as políticas de gerenciamento do aplicativo. Aqui estão as etapas necessárias para habilitar o MAM em seu aplicativo: 

## Substitua classes, métodos e atividades por seus equivalentes com MAM (obrigatório) 

* Classes com base em Android devem ser substituídas por seus equivalentes com MAM. Para fazer isso, localize todas as instâncias das classes listadas na tabela a seguir e as substitua pelo SDK de Aplicativos do Intune equivalente.  

    | Classe do Android | Substituição do SDK de Aplicativos do Intune |
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
    | android.app.PendingIntent | MAMPendingIntent |
    | android.app.Service | MAMService |
    | android.app.TabActivity | MAMTabActivity |
    | android.app.TaskStackBuilder | MAMTaskStackBuilder |
    | android.app.backup.BackupAgent | MAMBackupAgent |
    | android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
    | android.app.backup.FileBackupHelper | MAMFileBackupHelper |
    | android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
    | android.content.BroadcastReceiver | MAMBroadcastReceiver |
    | android.content.ContentProvider | MAMContentProvider |
    | android.os.Binder | MAMBinder * |
    | android.provider.DocumentsProvider | MAMDocumentsProvider |
    | android.preference.PreferenceActivity | MAMPreferenceActivity |

    *Somente é necessário substituir Binder por MAMBinder se o fichário não for gerado de uma interface AIDL.

    **Microsoft.Intune.MAM.SDK.Suppout.v4.jar**:

    | MAM do Intune da classe Android | Substituição do SDK |
    |--|--|
    | android.support.v4.app.DialogFragment | MAMDialogFragment
    | Android.support.v4.App.FragmentActivity | MAMFragmentActivity
    | android.support.v4.app.Fragment | MAMFragment
    | android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
    | android.support.v4.content.FileProvider | MAMFileProvider
    
    **Microsoft.Intune.MAM.SDK.Suppout.v7.jar**:

    |Classe do Android | Substituição do SDK de MAM do Intune |
    |--|--|
    |Android.support.v7.App.ActionBarActivity | MAMActionBarActivity |


* Ao usar um ponto de entrada Android que foi substituído por seu equivalente MAM, uma versão alternativa do ciclo de vida do ponto de entrada deve ser usada (com exceção da classe `MAMApplication`).

    Por exemplo, ao derivar de `MAMActivity`, em vez de substituir `onCreate` e chamar `super.onCreate`, a Atividade deve substituir `onMAMCreate` e chamar s`uper.onMAMCreate`. Isso permite que a inicialização da Atividade (entre outros) seja restrito em determinados casos. 

# Habilitar recursos que exigem a participação do aplicativo 

Há algumas políticas que o SDK não pode implementar por conta própria. Para habilitar o aplicativo a controlar seu comportamento para esses recursos, expomos várias APIs que você pode encontrar na interface `AppPolicy` abaixo.  

    /**
     * External facing app policies.
     */
    public interface AppPolicy {
        /**
         * Restrict where an app can save personal data.
         * 
         * @return True if the app is allowed to save to personal data stores;
         *         false otherwise.
         */
        boolean getIsSaveToPersonalAllowed();
    
        /**
         * Check if policy prohibits saving to a content provider location.
         * 
         * @param location
         *            a content URI to check
         * @return True if location is not a content URI or if policy does not 
         *         prohibit saving to the content location.
         */
        boolean getIsSaveToLocationAllowed(android.net.Uri location); 
    
        /**
         * Whether the SDK PIN prompt is enlightened for the app.
         * 
         * @return True if the PIN is enabled. False otherwise.
         */
        boolean getIsPinRequired();
        /**
         * Whether the Intune Managed Browser is required to open web links.
         *
         * @return True if the Managed Browser is required, false otherwise
         */
        boolean getIsManagedBrowserRequired();
    }

## Habilitar o controle de administração de TI sobre o comportamento de salvamento do aplicativo

Muitos aplicativos implementam recursos que permitem que o usuário final salve arquivos localmente ou em outro serviço. O SDK de Aplicativos do Azure permite que os administradores de TI protejam contra vazamento de dados aplicando as restrições de política da forma como acharem melhor para sua organização.  Uma das políticas que o administrador pode controlar é se o usuário final pode salvar em um repositório de dados pessoais. Isso inclui salvar localmente, em cartões SD ou serviços de backup. A participação do aplicativo é necessária para habilitar o recurso. Se seu aplicativo permitir o salvamento em locais na nuvem ou pessoais diretamente do aplicativo, você deve implementar esse recurso para garantir que o administrador de TI possa controlar se é permitido salvar em um local ou não. A API abaixo permite que o aplicativo saiba se salvar em um armazenamento pessoal é permitido segundo a atual política do administrador. O aplicativo pode, então, aplicar a política, pois ele está ciente de que o armazenamento pessoal de dados está disponível para o usuário final por meio do aplicativo.  

Para determinar se a política é aplicada, o aplicativo pode fazer a chamada a seguir: 

    MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();

**Observação**: MAMComponents.get(AppPolicy.class) sempre retornará uma Política de aplicativo não nula, mesmo que o dispositivo ou aplicativo não esteja sob gerenciamento. 

## Permitir que o aplicativo detecte se a Política de PIN é necessária
 
 Há políticas adicionais em que o aplicativo pode querer desabilitar algumas das suas funcionalidades para não duplicar a funcionalidade no SDK de Aplicativos do Intune. Por exemplo, se o aplicativo tiver sua própria experiência do usuário de PIN, ele poderá desabilitá-la se o SDK estiver configurado para exigir que o usuário final insira um PIN. 

Para determinar se a política de PIN será configurada para exigir a entrada do PIN periodicamente, o aplicativo pode fazer a chamada a seguir: 

    MAMComponents.get(AppPolicy.class).getIsPinRequired();

## Registrando-se para notificações do SDK  

O SDK de Aplicativos do Intune permite que seu aplicativo tenha controle sobre o comportamento quando algumas políticas, como uma política de apagamento remoto, são usadas pelo administrador de TI. Para fazer isso, você precisará se registrar para notificações do SDK, criando uma classe `MAMNotificationReceiver` e registrando-a no `MAMNotificationReceiverRegistry`. Isso é feito fornecendo o receptor e o tipo de notificação que o receptor deseja receber em  `App.onCreate`, como mostra o exemplo a seguir:
 
    @Override
      public void onCreate() {
            super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class).registerReceiver(
    new ToastNotificationReceiver(), MAMNotificationType.WIPE_USER_DATA);
    }

`MAMNotificationReceiver` apenas recebe notificações. Algumas notificações são manipuladas pelo SDK diretamente, outros exigem a participação do aplicativo. Um aplicativo deve retornar true ou false de uma notificação. Ele deve sempre retornar true, a menos que alguma ação que ele tentou executar como resultado da notificação falhe. Essa falha pode ser relatada ao serviço do Intune, como se o aplicativo indicar que falhou ao apagar os dados do usuário. É seguro bloquear `MAMNotificationReceiver.onReceive`; seu retorno de chamada não está em execução no thread da interface do usuário. 

A interface `MAMNotificationReceiver está incluída abaixo conforme definido no SDK: 

    /**
     * The SDK is signaling that a MAM event has occurred. 
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

As seguintes notificações são enviadas para o aplicativo e algumas delas podem exigir a participação do aplicativo: 

* **`WIPE_USER_DATA` notificação**: essa notificação é enviada em uma classe `MAMUserNotification`. Quando essa notificação é recebida, o aplicativo deve excluir todos os dados associados à identidade passada com a `MAMUserNotification`. Atualmente, essa notificação é enviada durante o cancelamento do registro do Serviço do Intune. O nome principal do usuário geralmente é especificado durante o processo de registro. Se você se registrar para essa notificação, seu aplicativo deve garantir que todos os dados do usuário foram excluídos. Se você não se registrar para ela, o comportamento de apagamento seletivo padrão será executado. 

* **`WIPE_USER_AUXILIARY_DATA` notificação**: os aplicativos podem se registrar para essa notificação se quiserem que o SDK de Aplicativos do Intune execute o apagamento padrão, mas ainda desejarem remover alguns dados auxiliares quando o apagamento ocorrer.  

* **`REFRESH_POLICY` notificação**: essa notificação é enviada em um MAMNotification sem qualquer informação adicional. Quando essa notificação é recebida, qualquer política armazenada em cache deve ser considerada não invalidada e, portanto, deve verificar qual é a política. Normalmente, isso é tratado pelo SDK, porém deve ser tratado pelo aplicativo se a política for usada de qualquer maneira persistente. 

## Métodos e tentativas pendentes 

Depois de derivar de um dos pontos de entrada de MAM, você pode usar o Contexto como faria normalmente, para iniciar Atividades, usando seu `PackageManager`etc.  `PendingIntents` são uma exceção a essa regra. Ao chamar essas classes, você precisa alterar o nome de classe. Por exemplo, em vez de usar `PendingIntent.get*`, `MAMPendingIntents.get*` deve ser usado. 

Em alguns casos, um método disponível na classe Android foi marcado como final na classe de MAM de substituição. Nesse caso, a classe de MAM de substituição fornece um método nomeado da mesma forma (em geral com o sufixo "MAM") que deve ser substituído em vez disso. Por exemplo, em vez de substituir `ContentProvider.query`, você substituiria `MAMContentProvider.queryMAM`. O compilador Java deve impor as restrições finais para evitar a substituição acidental do método original em vez do MAM equivalente. 

# Proteção de dados de backup 

A partir do Android Marshmallow (API 23), o Android tem duas formas para um aplicativo fazer backup de seus dados. Essas opções estão disponíveis para uso em seu aplicativo e exigem etapas diferentes para garantir que a proteção de dados de MAM seja aplicada corretamente. Você pode examinar a tabela abaixo para ter visão geral rápida sobre as ações correspondentes necessárias para o comportamento correto de proteção de dados.  Você também pode encontrar mais informações sobre backup do Android no [Guia de backup de dados para o desenvolvedor Android](http://developer.android.com/guide/topics/data/backup.html.). 

## Backup completo automático

No Android M, o Android começou a oferecer backups completos automáticos para aplicativos, independentemente da API de destino durante a execução em um dispositivo do Android M. Desde que o atributo `android:allowBackup` não seja false, um aplicativo receberá backups completos e não filtrados de seu aplicativo. Isso representa um risco de vazamento de dados, portanto, o SDK requer as alterações descritas na tabela a seguir para garantir que a proteção de dados seja aplicada.  É importante seguir as diretrizes descritas abaixo para proteger os dados do cliente corretamente.  Se você definir `android:allowBackup=false` , seu aplicativo nunca será ser enfileirado para backups pelo sistema operacional e você não terá outra ação para o MAM, já que não haverá nenhum backup
 
 ## Backups de “chave/valor”

Essa opção está disponível para todas as APIs e usa `BackupAgent` e `BackupAgentHelper`. 

### Usando BackupAgentHelper

`BackupAgentHelper` é muito mais simples de implementar do que o `BackupAgent` em termos de funcionalidade nativa do Android e integração de MAM. `BackupAgentHelper` permite que o desenvolvedor registre arquivos inteiros e preferências compartilhadas com um `FileBackupHelper` ou `SharedPreferencesBackupHelper`, respectivamente, que são adicionados ao `BackupAgentHelper` no momento da criação. 

### Usando BackupAgent

`BackupAgent` permite que você seja muito mais explícito sobre de quais dados é feito backup. No entanto, esta opção significa que você não poderá aproveitar a estrutura de backup do Android.  Como você é bastante responsável pela implementação, há mais etapas necessárias para garantir a proteção de dados apropriada do MAM. Uma vez que a maioria do trabalho é passado para você, o desenvolvedor, integração do MAM é um pouco mais envolvida. 

#### O aplicativo não tem um agente de backup
  
Essas são as opções do desenvolvedor quando `Android:allowbBackup =true`:

##### Backup completo de acordo com um arquivo de configuração: 

Forneça um recurso sob a marca de metadados `com.microsoft.intune.mam.FullBackupContent` em seu manifesto. Por exemplo:
    `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Adicione o seguinte atributo na marca `<application>` : `android:fullBackupContent="@xml/my_scheme"`, em que `my_scheme` é um recurso XML em seu aplicativo. 

##### Backup completo sem exclusões 

Forneça uma marcação no manifesto, como `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Adicione o seguinte atributo na marcação `<application>`: `android:fullBackupContent="true"`.

#### O aplicativo tem um agente de backup

Siga as recomendações nas seções `BackupAgent` e `BackupAgentHelper` descritas acima 

Considere a possibilidade de usar nosso `MAMDefaultFullBackupAgent`, que fornece backup fácil no Android M. 

### Antes do backup

Antes de iniciar o backup, você deve verificar se os arquivos ou buffers de dados de que você pretende fazer backup têm permissão para backup. Nós fornecemos uma função `isBackupAllowed` em `MAMFileProtectionManager` e `MAMDataProtectionManager` para determinar isso. Se o buffer de dados ou arquivo não tiver permissão para backup, você não deve tentar continuar utilizando-o em seu backup.

Em algum momento durante o backup, se desejar que as identidades dos arquivos verificados na etapa 1 façam backup, você deverá chamar `backupMAMFileIdentity(BackupDataOutput data, File … files)` com os arquivos dos quais planejada extrair dados. Isso criará automaticamente novas entidades de backup e as gravará em `BackupDataOutput` para você. Essas entidades serão consumidas automaticamente após a restauração. 

## Configurar a ADAL (Biblioteca de Autenticação do Active Directory)  

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

### Configurações comuns do ADAL 

A seguir estão as configurações comua para os valores explicados acima. 

#### O aplicativo não se integra ao ADAL

* A autoridade deve ser configurada para o ambiente desejado em que as contas do AAD foram configuradas.

* O SkipBroker deve ser definido como true.

#### O aplicativo integra o ADAL

* A autoridade deve ser configurada para o ambiente desejado em que as contas do AAD foram configuradas.

* A ID do cliente deve ser definida como ID cliente do aplicativo.

* `NonBrokerRedirectURI` deve ser definido como um URI de redirecionamento válido para o aplicativo.
    * Or `urn:ietf:wg:oauth:2.0:oob` deve ser configurado como um URI de redirecionamento do AAD válido.

* O SkipBroker deve ser definido como false (ou absent)

* O AAD deve ser configurado para aceitar o URI de redirecionamento do agente.

#### O aplicativo integra-se ao ADAL, mas não dá suporte ao aplicativo do Autenticador do AAD.

* A autoridade deve ser configurada para o ambiente desejado em que as contas do AAD foram configuradas.

* A ID do cliente deve ser definida como ID cliente do aplicativo.

* `NonBrokerRedirectURI` deve ser definido como um URI de redirecionamento válido para o aplicativo.

    * Or `urn:ietf:wg:oauth:2.0:oob` deve ser configurado como um URI de redirecionamento do AAD válido.

## Como habilitar o registro no SDK 

O registro em log é feito por meio da estrutura `java.util.logging` . Para receber os logs, configure o registro conforme descrito no [Guia técnico de Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Dependendo do aplicativo, `App.onCreate` geralmente é o melhor local para iniciar o registro. Observe que as mensagens de Log são criptografadas pelo nome de classe, que pode ser ofuscado.

# Limitações conhecidas da plataforma 

## Limitações de tamanho do arquivo 

No Android, as limitações do formato de arquivo executável Dalvik podem se tornar um problema para grandes bases de código que são executadas sem o ProGuard. Especificamente, as limitações a seguir podem ocorrer: 

* O limite de 65 mil para campos.

* O limite de 65 mil para métodos.

Ao incluir vários projetos, cada android:package obterá uma cópia do R que aumentará consideravelmente o número de campos conforme bibliotecas forem adicionadas. As recomendações a seguir podem ajudar a reduzir essa limitação:
 
* Todos os projetos de biblioteca devem compartilhar o mesmo android:package sempre que possível. Isso não falhará esporadicamente no campo, pois é essencialmente um problema de tempo de compilação.   Além disso, as versões mais recentes do SDK do Android vão pré-processar arquivos DEX para remover parte da redundância. Isso reduz a distância entre os campos ainda mais.

* Use das ferramentas de compilação do SDK do Android mais recentes disponíveis.

* Remova todas as bibliotecas desnecessárias e não utilizadas (por exemplo, `android.support.v4`)

## Limitações de imposição de política

**Captura de tela**: o SDK não impõe um novo valor de configuração de captura de tela Atividades que já passaram por Activity.onCreate. Isso pode resultar em um período de tempo em que o aplicativo foi configurado para desabilitar as capturas de tela, mas capturas de tela ainda podem ser feitas.

**Usando Resolvedores de Conteúdo*: a política de transferência ou de recebimento pode bloquear ou bloquear parcialmente o uso de um resolvedor de conteúdo para acessar o provedor de conteúdo em outro aplicativo. Isso fará com que os métodos de ContentResolver retornem null ou gerem um valor de falha (por exemplo, `openOutputStream` lançará `FileNotFoundException` se bloqueado). O aplicativo pode determinar se uma falha de gravação de dados por meio de um resolvedor de conteúdo foi causada pela política (ou seria causada pela política), fazendo a chamada:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Serviços exportados**: o arquivo `AndroidManifest.xml` incluído no SDK de Aplicativos do Intune contém `MAMNotificationReceiverService`, que deve ser um serviço exportado para permitir que o Portal da Empresa envie notificações para um aplicativo esclarecido. O serviço verifica o chamador para garantir que apenas o Portal da Empresa tenha permissão para enviar notificações. 

# Práticas Recomendadas de Android 

O SDK do Intune mantém o contrato fornecido pela API do Android, embora condições de falha possam ser disparadas com mais frequência como resultado da aplicação de políticas. Essas práticas recomendadas do Android reduzirão a probabilidade de falha: 

* Funções do SDK do Android que podem retornar valores nulos agora têm maior alta probabilidade de ser nulas.  Para minimizar problemas, certifique-se de que verificações nulas estejam nos lugares certos.

* Recursos que podem ser verificados devem ser verificados por meio de suas APIs do SDK.

* Quaisquer funções derivadas devem chamar por meio de suas versões de superclasse.

* Evite o uso de qualquer API de forma ambígua. Por exemplo, `Activity.startActivityForResult/onActivityResult` sem verificar o requestCode causará um comportamento estranho.


<!--HONumber=May16_HO2-->


