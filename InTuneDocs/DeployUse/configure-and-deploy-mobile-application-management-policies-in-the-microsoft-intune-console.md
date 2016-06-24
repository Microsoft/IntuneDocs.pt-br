---
# required metadata

title: Configurar e implantar políticas de gerenciamento de aplicativo móvel no console do Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: joglocke
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configure and deploy mobile application management policies in the Microsoft Intune console
As políticas de gerenciamento de aplicativos móveis no Microsoft Intune permitem que você modifique a funcionalidade dos aplicativos implantados para ajudar a alinhá-los às políticas de segurança e conformidade de sua empresa. Por exemplo, você pode restringir as operações de recortar, copiar e colar em um aplicativo gerenciado, ou configurar um aplicativo para abrir todos os links da web dentro do navegador gerenciado.

As políticas de gerenciamento de aplicativos móveis dão suporte a:

-   Dispositivos que executam o Android 4 e posterior.

-   Dispositivos que executam o iOS 7 e posterior.

> [!TIP] Políticas de gerenciamento de aplicativos móveis dão suporte a dispositivos registrados com o Intune.
>
> Se você estiver procurando informações sobre como criar políticas de gerenciamento de aplicativos para dispositivos que não são gerenciados pelo Intune, consulte [Protect app data using mobile app management policies with Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) (Proteger os dados do aplicativo usando políticas de gerenciamento de aplicativos móveis com o Microsoft Intune).

Diferente de outras políticas do Intune, você não implanta uma política de gerenciamento de aplicativo móvel diretamente. Em vez disso, você associa a política ao aplicativo que deseja restringir. Quando o aplicativo é implantado e instalado em dispositivos, as configurações especificadas entrarão em vigor.

Para aplicar restrições a um aplicativo, o aplicativo deve incorporar o SDK de Aplicativos do Microsoft Intune. Há três métodos de obter esse tipo de aplicativo:

-   **Usar um aplicativo gerenciado por política** – tem o SDK interno do aplicativo. Para adicionar este tipo de aplicativo, especifique um link para o aplicativo de uma loja de aplicativos, como a iTunes Store ou o Google Play. Nenhum processamento adicional é necessário para este tipo de aplicativo. Veja uma lista de [aplicativos que você pode usar com políticas de gerenciamento de aplicativos móveis do Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

-   **Usar um aplicativo "encapsulado"** – aplicativos que são empacotados novamente para incluir o SDK do aplicativo usando a **Ferramenta de Encapsulamento de Aplicativos do Microsoft Intune**. Normalmente, essa ferramenta é usada para processar aplicativos da empresa criados internamente. Ele não pode ser usado para processar aplicativos que foram baixados da loja de aplicativos. Consulte [Prepare iOS apps for mobile application management with the Microsoft Intune App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) (Preparar aplicativos iOS para o gerenciamento de aplicativos móveis com a Ferramenta de Disposição de Aplicativo do Microsoft Intune) e [Prepare Android apps for mobile application management with the Microsoft Intune App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) (Preparar aplicativos Android para o gerenciamento de aplicativos móveis com a Ferramenta de Disposição do Aplicativo do Microsoft Intune).

- **Escrever seu próprio aplicativo que incorpora o SDK de Aplicativos do Intune** - O SDK de Aplicativos do Intune permite que você incorpore recursos de gerenciamento de aplicativo em um aplicativo enquanto ele estiver sendo gravado. Para obter mais informações, consulte [Intune App SDK Overview](/develop/intune-app-sdk) (Visão geral do SDK de Aplicativos do Intune)

Para obter ajuda para decidir entre a ferramenta de disposição de aplicativo e o SDK de Aplicativos do Intune, consulte [Decide how to prepare apps for mobile application management with Microsoft Intune](/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) (Decidir como preparar aplicativos para gerenciamento de aplicativo móvel com o Microsoft Intune)

Alguns aplicativos gerenciados, como o aplicativo do Outlook para iOS e Android, dão suporte a **multi-identidade**. Isso significa que Intune aplica as configurações de gerenciamento somente a dados ou contas corporativas no aplicativo.

Por exemplo, usando o aplicativo do Outlook:

-   Se o usuário configurar uma conta de email pessoal e uma corporativa, o Intune aplicará as configurações de gerenciamento apenas à conta corporativa e não gerencia a conta pessoal.

-   Se o dispositivo for desativado ou seu registrado cancelado, somente os dados corporativos do Outlook serão removidos do dispositivo.

-   A conta corporativa usada deve ser a mesma conta que foi usada para registrar o dispositivo no Intune.

> [!TIP] Se estiver usando o Intune com o Configuration Manager, consulte [How to Control Apps Using Mobile Application Management Policies in Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx) (Como controlar aplicativos usando políticas de gerenciamento de aplicativos móveis no Configuration Manager).

## Criar e implantar um aplicativo com uma política de gerenciamento de aplicativos móveis

-   **Etapa 1:** obtenha o link para um aplicativo gerenciado por política, crie um aplicativo disposto ou use o SDK de Aplicativos do Intune para gravar um aplicativo habilitado para MAM.

-   **Etapa 2:** publicar o aplicativo em seu espaço de armazenamento de nuvem.

-   **Etapa 3:** criar uma política de gerenciamento de aplicativos móveis.

-   **Etapa 4:** implantar o aplicativo, selecionando a opção para associar o aplicativo a uma política de gerenciamento de aplicativos móveis.

-   **Etapa 5:** monitorar a implantação do aplicativo.

## **Etapa 1:** obtenha o link para um aplicativo gerenciado por política, crie um aplicativo disposto ou use o SDK de Aplicativos do Intune para gravar um aplicativo habilitado para MAM.

-   **Para obter um link para um aplicativo gerenciado por política em uma loja de aplicativos** - Na loja de aplicativos, encontre e anote a URL do aplicativo gerenciado por política que você deseja implantar.

    Por exemplo, a URL do aplicativo do Microsoft Word para iPad é **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**


## **Etapa 2:** publicar o aplicativo em seu espaço de armazenamento de nuvem
Quando você publica um aplicativo gerenciado, os procedimentos diferem se você estiver publicando um aplicativo gerenciado por política ou um aplicativo que foi processado usando a ferramenta de disposição de aplicativos do Microsoft Intune para iOS.

#### Para publicar um aplicativo gerenciado por política

1.  Quando você estiver pronto para carregar o aplicativo em seu espaço de armazenamento em nuvem, siga as instruções em [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) (Adicionar aplicativos para dispositivos móveis no Microsoft Intune).

2.  Para aplicativos do iOS, selecione **Aplicativo iOS gerenciado da App Store**em **Selecionar como este software é disponibilizado para dispositivos**.

    Para aplicativos Android, selecione **Link externo**.

3.  Em **Especificar a URL**, digite a URL para o aplicativo gerenciado por política que você anotou anteriormente.

Após o carregamento ser concluído, você verá **Sim** para **Políticas de Gerenciamento de Aplicativo** na página **Propriedades de Software** do aplicativo carregado.

Depois de verificar se o aplicativo foi carregado com êxito, prossiga para a Etapa 3.

#### Para publicar um aplicativo que foi processado usando a Ferramenta de disposição de aplicativos do Microsoft Intune

1.  Quando você estiver pronto para carregar o aplicativo em seu espaço de armazenamento em nuvem, siga as instruções em [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) (Adicionar aplicativos para dispositivos móveis no Microsoft Intune).

2.  Selecione **Instalador de Software**em **selecionar como este software é disponibilizado para dispositivos**.

3.  Selecione **Pacote do aplicativo para iOS (arquivo &#42;.ipa)** em **Tipo de arquivo do instalador de software**.

Após o carregamento ser concluído, você verá **Sim** para **Políticas de Gerenciamento de Aplicativo** na página **Propriedades de Software** do aplicativo carregado.

Depois de verificar se o aplicativo foi carregado com êxito, prossiga para a Etapa 3.

## **Etapa 3:** criar uma política de gerenciamento de aplicativos móveis

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Política** &gt; **Visão geral** &gt; **Adicionar Política**.

2.  Configure e implante uma das seguintes políticas de **Software** , dependendo do tipo de dispositivo para o qual deseja configurar aplicativos:

    -   **Política de gerenciamento de aplicativos móveis (Android 4 e posterior)**

    -   **Política de gerenciamento de aplicativos móveis (iOS 7 e posterior)**

    É possível usar as configurações recomendadas ou personalizá-las. Para obter mais detalhes, consulte [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune).

3.  Defina as seguintes configurações conforme necessário. As opções podem variar dependendo do tipo de dispositivo para o qual você está configurando a política.

|Nome da configuração|Detalhes|
    |---------|--------------------|
    |**Nome**|Especifique um nome para esta política.|
    |**Descrição**|Ou especifique uma descrição para a política.|
    |**Restringir o conteúdo da web a ser exibido em um navegador gerenciado corporativo**|Quando essa configuração for habilitada, todos os links no aplicativo serão abertos no navegador gerenciado. Você precisa ter implantado o aplicativo em dispositivos para que essa opção funcione.|
    |**Impedir backups do Android** ou **Impedir backups do iTunes e iCloud**|Desabilita o backup de todas as informações do aplicativo.|
    |**Permitir que o aplicativo transfira dados para outros aplicativos**|Especifica os aplicativos para os quais esse aplicativo pode enviar dados. Você pode optar por não permitir a transferência de dados para qualquer aplicativo, permitir somente a transferência para outros aplicativos gerenciados ou permitir a transferência para qualquer aplicativo. Essa configuração não controla o uso do recurso **Open In** em dispositivos móveis.<br /><br />Por exemplo, quando você não permite a transferência de dados, você restringe a transferência de dados em serviços como mensagens SMS, atribuição de imagens a contatos e publicações no Facebook ou Twitter.<br /><br />Para dispositivos iOS, para evitar a transferência de documentos entre os aplicativos gerenciados e não gerenciados, você deve também deve configurar e implantar uma política de segurança de dispositivo móvel que desabilite a configuração **Permitir documentos gerenciados em outros aplicativos não gerenciados**. Se você optar por permitir somente a transferência para outros aplicativos gerenciados, os visualizadores de imagem e PDF do Intune (se implantados) serão usados para abrir o conteúdo dos respectivos tipos.<br /><br />Além disso, se você definir essa opção como **Aplicativos Gerenciados por Política** ou **Nenhum**, o recurso do iOS 9 que permite a Pesquisa de Destaque pesquise dados em aplicativos será bloqueado.|
    |**Permitir que o aplicativo receba dados de outros aplicativos**|Especifica os aplicativos dos quais este aplicativo pode receber dados. Você pode optar por não permitir a transferência de dados de qualquer aplicativo, permitir somente a transferência de outros aplicativos gerenciados ou permitir a transferência de qualquer aplicativo<br /><br />Para aplicativos iOS que dão suporte a várias identidades (em que o Intune só aplica configurações de gerenciamento a contas corporativas ou dados no aplicativo), para um dispositivo registrado com uma política de gerenciamento de aplicativos móveis aplicada, quando um usuário acessa dados em um aplicativo que não é gerenciado por uma política de gerenciamento de aplicativos móveis, os dados serão tratados como dados corporativos e protegidos pela política.|
    |**Impedir "Salvar como"**|Desabilita o uso da opção **Salvar como** para salvar dados em locais de armazenamento de nuvem particular (como OneDrive pessoal ou Dropbox) em qualquer aplicativo que use essa política.|
    |**Restringir recortar, copiar e colar com outros aplicativos**|Especifica como as operações recortar, copiar e colar podem ser usadas com o aplicativo. Escolha:<br /><br />**Bloqueado** – não permite as operações de recortar, copiar e colar entre este aplicativo e outros aplicativos.<br /><br />**Aplicativos Gerenciados por Política** – permite apenas operações de recortar, copiar e colar entre este aplicativo e outros aplicativos gerenciados.<br /><br />**Aplicativos Gerenciados por Política com Colar em** – permite a transferência de dados copiados ou recortados deste aplicativo somente para outros aplicativos gerenciados. Permitir a transferência de dados recortados ou copiados de qualquer aplicativo para este aplicativo.<br /><br />**Qualquer Aplicativo** – sem restrições para operações de recortar, copiar e colar deste ou para este aplicativo.<br /><br />Para copiar e colar dados entre aplicativos gerenciados, ambos os aplicativos devem ter as configurações **Aplicativos Gerenciados por Política** ou **Aplicativos Gerenciados por Política com Colar em** definidas.|
    |**Solicitar PIN simples para acesso**|Requer que o usuário insira um número PIN que ele especificar para usar o aplicativo. O usuário será solicitado a configurar isso na primeira vez em que executar o aplicativo.|
    |**Número de tentativas antes da redefinição do PIN**|Especifique o número de tentativas de entrada do PIN que podem ser feitas antes que o usuário precise redefinir o PIN.|
    |**Exigir credenciais corporativas para acesso**|Requer que o usuário insira suas informações de logon corporativo antes de acessar o aplicativo.|
    |**Exigir conformidade do dispositivo com a política corporativa para acesso**|Permite que o aplicativo seja usado somente quando o dispositivo não está desbloqueado ou modificado.|
    |**Verificar novamente os requisitos de acesso após (minutos)**|No campo **Tempo Limite** , especifique o período de tempo antes que os requisitos de acesso para o aplicativo sejam verificados novamente após o aplicativo ser iniciado.|
    |**Período de cortesia offline**|Se o dispositivo estiver offline, especifique o período de tempo antes que os requisitos de acesso ao aplicativo sejam verificados novamente.|
    |**Criptografar dados do aplicativo**|Especifica que todos os dados associados ao aplicativo sejam criptografados, inclusive dados armazenados externamente, como em cartões SD.<br /><br />**Criptografia para iOS**<br /><br />Para aplicativos associados a uma política de gerenciamento de aplicativo móvel do Intune, os dados são criptografados em repouso usando a criptografia no nível do dispositivo fornecida pelo sistema operacional. Isso é habilitado pela política de PIN do dispositivo que deve ser definida com o administrador de TI. Quando um PIN for solicitado, os dados serão criptografados segundo as configurações na política de gerenciamento de aplicativos móveis. Conforme indicado na documentação da Apple, [os módulos usados pelo iOS 7 têm a certificação FIPS 140-2](http://support.apple.com/en-us/HT202739).<br /><br />**Criptografia para Android**<br /><br />Para aplicativos associados a uma política de gerenciamento de aplicativos móveis do Intune, a criptografia é fornecida pela Microsoft. Os dados são criptografados de forma síncrona durante operações de E/S de arquivo.  O conteúdo no armazenamento do dispositivo sempre será criptografado. O método de criptografia não tem certificação FIPS 140-2.|
    |**Bloquear captura de tela** (somente para dispositivos Android)|Especifica que as funcionalidades de captura de tela do dispositivo sejam bloqueadas durante o uso do aplicativo.|

4.  Quando tiver terminado, selecione **Salvar Política**.

A nova política é exibida no nó **Políticas de configuração** do espaço de trabalho **Política** .

## **Etapa 4:** associar o aplicativo a uma política de gerenciamento de aplicativos móveis e implantá-lo.
Implantar o aplicativo, garantindo que você selecione a política de gerenciamento de aplicativo móvel na página **Gerenciamento de Aplicativo Móvel** para associar a política ao aplicativo.

Para mais detalhes, consulte [Deploy apps in Microsoft Intune](deploy-apps.md) (Implantar aplicativos no Microsoft Intune).

> [!IMPORTANT] Para dispositivos que executam sistemas operacionais anteriores ao iOS 7.1, as políticas associadas não serão removidas quando o aplicativo for desinstalado.
>
> Se o dispositivo tiver o registro no Intune desfeito, as políticas não serão removidas dos aplicativos. Quaisquer aplicativos que tiverem políticas aplicadas manterão as configurações de política, mesmo depois de ser desinstalado e reinstalado.

### O que fazer quando um aplicativo já está implantado em dispositivos
Pode haver situações em que você implantar um aplicativo e um dos usuários ou dispositivos de destino já tem uma versão não gerenciada do aplicativo instalada, por exemplo, o usuário instalou o Microsoft Word da loja de aplicativos.

Nesse caso, você deve pedir ao usuário para desinstalar manualmente a versão não gerenciada para que possa ser instalada a versão gerenciada que você configurou.

No entanto, para dispositivos que executam o iOS 9 e versões posteriores, o Intune automaticamente solicitará ao usuário permissão para assumir o gerenciamento do aplicativo existente. Se eles concordarem, o aplicativo será gerenciado pelo Intune e qualquer política de gerenciamento de aplicativo móvel associada ao aplicativo também será aplicada.

> [!TIP] Se o dispositivo estiver em modo supervisionado, o Intune assumirá o gerenciamento do aplicativo existente sem solicitar permissão de usuários.

## **Etapa 5:** monitorar a implantação do aplicativo.
Após ter criado e implantado um aplicativo associado a uma política de gerenciamento de aplicativo móvel, use os procedimentos a seguir para monitorar o aplicativo e resolver conflitos de política.

#### Para exibir o status da implantação

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Grupos** &gt; **Visão Geral**.

2.  Execute uma das seguintes etapas:

    -   Selecione **Todos os Usuários** e clique duas vezes no usuário cujos dispositivos você deseja examinar. Na página **Propriedades do Usuário**, selecione **Dispositivos** e clique duas vezes no dispositivo que você deseja examinar.

    -   Selecione **Todos os Dispositivos** &gt; **Todos os Dispositivos Móveis**. Na página **Propriedades do Grupo de Dispositivos**, selecione **Dispositivos** e clique duas vezes no dispositivo que você deseja examinar.

3.  Na página **Propriedades do Dispositivo Móvel**, selecione **Política** para ver uma lista das políticas de gerenciamento de aplicativo móvel que foram implantados no dispositivo.

4.  Selecione a política de gerenciamento de aplicativo móvel cujo status você deseja exibir. Você pode ver detalhes da política no painel inferior e expandir o nó para exibir as configurações.

5.  Na coluna **Status** de cada uma das políticas de gerenciamento de aplicativo móvel, **Compatível**, **Compatível (Pendente)**ou **Erro** será exibido. Se a política selecionada tiver uma ou mais configurações conflitantes, **Erro** será exibido nesse campo.

6.  Após ter identificado um conflito, você pode revisar as configurações de política conflitantes para usar a mesma configuração ou implantar apenas uma política para o aplicativo e o usuário.

### Como os conflitos de política são resolvidos
Quando houver um conflito de política de gerenciamento de aplicativo móvel na primeira implantação para o usuário ou dispositivo, o valor da configuração específica em conflito será removido da política implantada para o aplicativo e ele usará um valor de conflito interno.

Quando houver um conflito de política de gerenciamento de aplicativo móvel em implantações posteriores ao aplicativo ou usuário, o valor da configuração específica em conflito não será atualizado na política de gerenciamento de aplicativos móveis implantada para o aplicativo e ele usará o valor existente para essa configuração.

Em casos em que o dispositivo ou usuário receber duas políticas conflitantes, o comportamento a seguir se aplicará:

-   Se já tiver sido implantada uma política para o dispositivo, as configurações de política existentes não serão substituídas.

-   Se nenhuma política tiver sido implantada no dispositivo e duas configurações conflitantes forem implantadas, a configuração padrão integrada no dispositivo será usada.


<!--HONumber=Jun16_HO2-->


