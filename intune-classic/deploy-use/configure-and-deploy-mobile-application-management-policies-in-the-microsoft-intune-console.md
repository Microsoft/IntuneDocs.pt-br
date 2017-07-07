---
title: "Configurar políticas de MAM no console do Intune"
description: "As políticas de gerenciamento de aplicativos móveis no Microsoft Intune permitem que você modifique a funcionalidade dos aplicativos implantados para ajudar a alinhá-los às políticas de segurança e conformidade de sua empresa."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ce97f18a799725a86ef3ab7f4f7c0cc8cdf8f062
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console"></a>Configure and deploy mobile application management policies in the Microsoft Intune console

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As políticas de MAM (gerenciamento de aplicativos móveis) no Microsoft Intune permitem que você modifique a funcionalidade dos aplicativos implantados para ajudar a alinhá-los às políticas de segurança e conformidade de sua empresa. Por exemplo, você pode restringir as operações de recortar, copiar e colar em um aplicativo gerenciado ou configurar um aplicativo para abrir todos os links da Web dentro do navegador gerenciado.

As políticas de gerenciamento de aplicativos móveis dão suporte a:

-   Dispositivos que executam o Android 4 e posterior.

-   Dispositivos que executam o iOS 8.0 e posterior.

> [!TIP]
> Políticas de gerenciamento de aplicativos móveis dão suporte a dispositivos registrados com o Intune.
>
> Se estiver procurando informações sobre como criar políticas de gerenciamento de aplicativos para dispositivos não gerenciados pelo Intune, consulte [Proteger dados de aplicativo usando políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

Diferente de outras políticas do Intune, você não implanta uma política de gerenciamento de aplicativo móvel diretamente. Em vez disso, você associa a política ao aplicativo que deseja restringir. Quando o aplicativo é implantado e instalado em dispositivos, as configurações especificadas entrarão em vigor.

Para aplicar restrições a um aplicativo, o aplicativo deve incorporar o SDK de Aplicativos do Microsoft Intune. Há três métodos de obter esse tipo de aplicativo:

-   **Usar um aplicativo gerenciado por política**. Um aplicativo gerenciado por política tem o SDK interno do aplicativo. Para adicionar este tipo de aplicativo, especifique um link para o aplicativo de uma loja de aplicativos, como a iTunes Store ou o Google Play. Nenhum processamento adicional é necessário para este tipo de aplicativo. Para obter mais informações, veja a lista de [aplicativos que você pode usar com políticas de gerenciamento de aplicativos móveis do Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

-   **Usar um aplicativo encapsulado**. Um aplicativo encapsulado é um aplicativo que é empacotado novamente para incluir o SDK do aplicativo usando a Ferramenta de Disposição do Aplicativo do Microsoft Intune. Normalmente, essa ferramenta é usada para processar aplicativos da empresa criados internamente. Você não pode utilizá-la para processar aplicativos que foram baixados da loja de aplicativos. Para obter mais informações, consulte [Preparar aplicativos iOS para gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune](/intune/app-wrapper-prepare-ios) e [Preparar aplicativos Android para o gerenciamento de aplicativos móveis com a Ferramenta de Disposição do Aplicativo do Microsoft Intune](/intune/app-wrapper-prepare-android).

- **Escreva seu próprio aplicativo que incorpora o SDK do Aplicativo do Intune**. O SDK do Aplicativo do Intune permite que você incorpore recursos de gerenciamento de aplicativo a um aplicativo enquanto o estiver escrevendo. Para obter mais informações, consulte [Visão Geral do SDK de Aplicativo do Intune](/intune/app-sdk).
/intune/apps-prepare-mobile-application-management Para obter ajuda para decidir entre a Ferramenta de Disposição do Aplicativo e o SDK do Aplicativo do Intune, consulte [Decidir como preparar aplicativos para o gerenciamento de aplicativo móvel com o Microsoft Intune](/intune/apps-prepare-mobile-application-management).

Alguns aplicativos gerenciados, como o aplicativo do Outlook para iOS e Android, dão suporte a *multi-identidade*. Isso significa que Intune aplica as configurações de gerenciamento somente a dados ou contas corporativas no aplicativo.

Por exemplo, usando o aplicativo do Outlook:

-   Se o usuário configurar uma conta de email pessoal e uma corporativa, o Intune aplicará as configurações de gerenciamento apenas à conta corporativa e não gerenciará a conta pessoal.

-   Se o dispositivo for desativado ou seu registrado cancelado, somente os dados corporativos do Outlook serão removidos dele.

-   A conta corporativa deve ser a mesma conta que foi usada para registrar o dispositivo no Intune.

> [!TIP]
> Se estiver usando o Intune com o Configuration Manager, consulte [How to Control Apps Using Mobile Application Management Policies in Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx) (Como controlar aplicativos usando políticas de gerenciamento de aplicativos móveis no Configuration Manager).

## <a name="create-and-deploy-an-app-with-a-mobile-application-management-policy"></a>Criar e implantar um aplicativo com uma política de gerenciamento de aplicativos móveis

-   **Etapa 1:** obtenha o link para um aplicativo gerenciado por política, crie um aplicativo disposto ou use o SDK de Aplicativos do Intune para gravar um aplicativo habilitado para MAM.

-   **Etapa 2:** publicar o aplicativo em seu espaço de armazenamento de nuvem.

-   **Etapa 3:** criar uma política de gerenciamento de aplicativos móveis.

-   **Etapa 4:** Associar o aplicativo a uma política de gerenciamento de aplicativos móveis e implantá-lo.

-   **Etapa 5:** monitorar a implantação do aplicativo.

## <a name="step-1-get-the-link-to-a-policy-managed-app-create-a-wrapped-app-or-use-the-intune-app-sdk-to-write-a-mam-enabled-app"></a>Etapa 1: Obtenha o link para um aplicativo gerenciado por política, crie um aplicativo disposto ou use o SDK do Aplicativo do Intune para gravar um aplicativo habilitado para MAM

Na loja de aplicativos, encontre e anote a URL do aplicativo gerenciado por política que você deseja implantar. Por exemplo, a URL do aplicativo do Microsoft Word para iPad é **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.


## <a name="step-2-publish-the-app-to-your-cloud-storage-space"></a>Etapa 2: Publicar o aplicativo em seu espaço de armazenamento de nuvem
Quando você publica um aplicativo gerenciado, os procedimentos diferem se você estiver publicando um aplicativo gerenciado por política ou um aplicativo que foi processado usando a ferramenta de disposição de aplicativos do Microsoft Intune para iOS.

#### <a name="to-publish-a-policy-managed-app"></a>Para publicar um aplicativo gerenciado por política

1.  Quando você estiver pronto para carregar o aplicativo em seu espaço de armazenamento em nuvem, siga as instruções em [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) (Adicionar aplicativos para dispositivos móveis no Microsoft Intune).

2.  Para aplicativos do iOS, selecione **Aplicativo iOS gerenciado da App Store** em **Selecionar como este software é disponibilizado para dispositivos**.

    Para aplicativos Android, selecione **Link externo**.

3.  Em **Especificar a URL**, digite a URL para o aplicativo gerenciado por política que você anotou anteriormente.

Após o upload ser concluído, você verá **Sim** para **Políticas de Gerenciamento de Aplicativo** na página **Propriedades de Software** do aplicativo carregado.

Depois de verificar se o aplicativo foi carregado com êxito, prossiga para a Etapa 3.

#### <a name="to-publish-an-app-that-was-processed-through-the-microsoft-intune-app-wrapping-tool"></a>Para publicar um aplicativo que foi processado por meio da Ferramenta de Disposição do Aplicativo do Microsoft Intune

1.  Quando você estiver pronto para carregar o aplicativo em seu espaço de armazenamento em nuvem, siga as instruções em [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) (Adicionar aplicativos para dispositivos móveis no Microsoft Intune).

2.  Selecione **Instalador de Software** em **selecionar como este software é disponibilizado para dispositivos**.

3.  Selecione **Pacote do aplicativo para iOS (arquivo &#42;.ipa)** em **Tipo de arquivo do instalador de software**.

Após o upload ser concluído, você verá **Sim** para **Políticas de Gerenciamento de Aplicativo** na página **Propriedades de Software** do aplicativo carregado.

Depois de verificar se o aplicativo foi carregado com êxito, prossiga para a Etapa 3.

## <a name="step-3-create-a-mobile-application-management-policy"></a>Etapa 3: criar uma política de gerenciamento de aplicativos móveis

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Política** &gt; **Visão geral** &gt; **Adicionar Política**.

2.  Configure e implante uma das seguintes políticas de **Software**, dependendo do tipo de dispositivo para o qual deseja configurar aplicativos:

    -   **Política de gerenciamento de aplicativos móveis (Android 4 e posterior)**

    -   **Política de Gerenciamento de Aplicativo Móvel (iOS 8.0 e posterior)**

    É possível usar as configurações recomendadas ou personalizá-las. Para obter mais detalhes, consulte [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune).

3.  Defina as seguintes configurações conforme necessário. As opções podem variar dependendo do tipo de dispositivo para o qual você está configurando a política.

|Nome da configuração|Detalhes|
    |---------|--------------------|
    |**Nome**|Especifique um nome para esta política.|
    |**Descrição**|Ou especifique uma descrição para a política.|
    |**Restringir o conteúdo da web a ser exibido em um navegador gerenciado corporativo**|Quando essa configuração for habilitada, todos os links no aplicativo serão abertos no navegador gerenciado. Para que essa opção funcione, você precisa ter implantado o aplicativo em dispositivos.|
    |**Impedir backups do Android** ou **Impedir backups do iTunes e iCloud**|Essa configuração desabilita o backup de todas as informações do aplicativo.|
    |**Permitir que o aplicativo transfira dados para outros aplicativos**|Essa configuração especifica os aplicativos para os quais esse aplicativo pode enviar dados. Você pode optar por não permitir a transferência de dados para qualquer aplicativo, permitir somente a transferência para outros aplicativos gerenciados ou permitir a transferência para qualquer aplicativo. <br /><br />Por exemplo, quando você não permite a transferência de dados, você restringe a transferência de dados em serviços como mensagens SMS, atribuição de imagens a contatos e publicações no Facebook ou Twitter.<br /><br />Para dispositivos iOS, para evitar a transferência de documentos entre os aplicativos gerenciados e não gerenciados, você precisa também configurar e implantar uma política de segurança de dispositivo móvel que desabilite a configuração **Permitir documentos gerenciados em outros aplicativos não gerenciados**. Se você optar por permitir a transferência apenas para outros aplicativos gerenciados, os visualizadores de imagens e PDF do Intune (se implantados) serão usados para abrir o conteúdo dos respectivos tipos.<br /><br />Além disso, se você definir essa opção como **Aplicativos Gerenciados por Política** ou **Nenhum**, o recurso do iOS 9 que permite a Pesquisa de Destaque pesquise dados em aplicativos será bloqueado.<br><br>Essa configuração não controla o uso do recurso “Abrir em” em dispositivos móveis. Para gerenciar o “Abrir em”, consulte [Gerenciar transferência de dados entre aplicativos iOS com Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).|
    |**Permitir que o aplicativo receba dados de outros aplicativos**|Essa configuração especifica os aplicativos dos quais este aplicativo pode receber dados. Você pode optar por não permitir a transferência de dados de qualquer aplicativo, permitir somente a transferência de outros aplicativos gerenciados ou permitir a transferência de qualquer aplicativo.<br /><br />Quando um usuário acessa dados de um aplicativo que não é gerenciado por uma política de gerenciamento de aplicativos móveis, os dados serão tratados como dados corporativos e protegidos pela política. Isso se aplica a aplicativos iOS que dão suporte a multi-identidade (em que o Intune aplica as configurações de gerenciamento apenas para contas ou dados corporativos no aplicativo). Isso se aplica também a dispositivos registrados com uma política de gerenciamento de aplicativos móveis aplicada.|
    |**Impedir "Salvar como"**|Essa configuração desabilita o uso da opção **Salvar como** para salvar dados em locais de armazenamento de nuvem particular (como OneDrive ou Dropbox) em qualquer aplicativo que use essa política.|
    |**Restringir recortar, copiar e colar com outros aplicativos**|Essa configuração especifica como as operações recortar, copiar e colar podem ser usadas com o aplicativo. Escolha:<br /><br />**Bloqueado**. Não permite as operações de recortar, copiar e colar entre este aplicativo e outros aplicativos.<br /><br />**Aplicativos gerenciados por política**. Permite as operações de recortar, copiar e colar somente entre este aplicativo e outros aplicativos.<br /><br />**Aplicativos gerenciados por política com Colar em**. Permite que dados recortados ou copiados desse aplicativo sejam colados somente em outros aplicativos gerenciados. Permitir a transferência de dados recortados ou copiados de qualquer aplicativo para este aplicativo.<br /><br />**Qualquer aplicativo**. Não coloca nenhuma restrição para as operações recortar, copiar e colar para ou desse aplicativo.<br /><br />Para copiar e colar dados entre aplicativos gerenciados, ambos os aplicativos devem ter as configurações **Aplicativos Gerenciados por Política** ou **Aplicativos Gerenciados por Política com Colar em** definidas.|
    |**Solicitar PIN simples para acesso**|Essa configuração requer que o usuário insira um PIN que ele especifica para usar o aplicativo. O usuário será solicitado a configurar isso na primeira vez em que executar o aplicativo.|
    |**Número de tentativas antes da redefinição do PIN**|Especifique o número de tentativas de entrada do PIN que podem ser feitas antes que o usuário tenha de redefinir o PIN.|
    |**Exigir credenciais corporativas para acesso**|Essa configuração requer que o usuário insira suas informações de logon corporativo antes de acessar o aplicativo.|
    |**Exigir conformidade do dispositivo com a política corporativa para acesso**|Essa configuração permite que o aplicativo seja usado somente quando o dispositivo não estiver desbloqueado ou modificado.|
    |**Verificar novamente os requisitos de acesso após (minutos)**|No campo **Tempo Limite**, especifique o período de tempo antes que os requisitos de acesso para o aplicativo sejam verificados novamente após o aplicativo ser aberto.|
    |**Período de cortesia offline**|Se o dispositivo estiver offline, especifique o período de tempo antes que os requisitos de acesso ao aplicativo sejam verificados novamente.|
    |**Criptografar dados do aplicativo**|Essa configuração especifica que todos os dados associados ao aplicativo sejam criptografados. Isso inclui dados armazenados externamente, como cartões SD.<br /><br />**Criptografia para iOS**<br /><br />Para aplicativos associados a uma política de gerenciamento de aplicativo móvel do Intune, os dados são criptografados em repouso por meio da criptografia no nível do dispositivo fornecida pelo iOS. Isso é habilitado por uma política de PIN do dispositivo que é ser definida pelo administrador de TI. Quando um PIN for solicitado, os dados serão criptografados de acordo com as configurações na política de gerenciamento de aplicativos móveis. Conforme indicado na documentação da Apple, [os módulos usados pelo iOS têm a certificação FIPS 140-2](http://support.apple.com/HT202739).<br /><br />**Criptografia para Android**<br /><br />Para aplicativos associados a uma política de gerenciamento de aplicativos móveis do Intune, a Microsoft fornece a criptografia. Os dados são criptografados de forma síncrona durante operações de E/S de arquivo.  O conteúdo no armazenamento do dispositivo sempre será criptografado. O método de criptografia é compatível com o FIPS 140-2 somente para dispositivos Samsung KNOX.|
    |**Bloquear captura de tela** (somente para dispositivos Android)|Essa configuração especifica que as funcionalidades de captura de tela do dispositivo sejam bloqueadas quando alguém estiver usando o aplicativo.|

4. Quando tiver terminado, selecione **Salvar Política**.

A nova política aparece no nó **Políticas de configuração** do espaço de trabalho **Política**.

## <a name="step-4-associate-the-app-with-a-mobile-application-management-policy-and-then-deploy-the-app"></a>Etapa 4: Associar o aplicativo a uma política de gerenciamento de aplicativos móveis e implantá-lo
Certifique-se de selecionar a política de gerenciamento de aplicativos móveis na página **Gerenciamento de Aplicativo Móvel** da caixa de diálogo **Gerenciar Implantação** para associar a política ao aplicativo.

Para mais detalhes, consulte [Deploy apps in Microsoft Intune](deploy-apps.md) (Implantar aplicativos no Microsoft Intune).

> [!IMPORTANT]
> Se o dispositivo tiver seu registro no Intune cancelado, as políticas não serão removidas dos aplicativos. Quaisquer aplicativos que tivessem políticas aplicadas manterão as configurações de política após o aplicativo ser desinstalado e reinstalado.

### <a name="what-to-do-when-an-app-is-already-deployed-on-devices"></a>O que fazer quando um aplicativo já está implantado em dispositivos
Pode haver situações em que você implantar um aplicativo e um dos usuários ou dispositivos de destino já tem uma versão não gerenciada do aplicativo instalada. Por exemplo, o usuário pode ter instalado o Microsoft Word da loja de aplicativos.

Nesse caso, você deve pedir ao usuário para desinstalar manualmente a versão não gerenciada para que possa ser instalada a versão gerenciada que você configurou.

No entanto, para dispositivos que executam o iOS 9 e versões posteriores, o Intune automaticamente solicitará ao usuário permissão para assumir o gerenciamento do aplicativo existente. Se ele concordar, o aplicativo será gerenciado pelo Intune e qualquer política de gerenciamento de aplicativo móvel associada ao aplicativo também será aplicada.

> [!TIP]
> Se o dispositivo estiver em modo de supervisionado, o Intune assumirá o gerenciamento do aplicativo existente sem solicitar permissão de usuários.

## <a name="step-5-monitor-the-app-deployment"></a>Etapa 5: Monitorar a implantação do aplicativo
Após ter criado e implantado um aplicativo associado a uma política de gerenciamento de aplicativo móvel, use os procedimentos a seguir para monitorar o aplicativo e resolver conflitos de política.

#### <a name="to-view-the-status-of-the-deployment"></a>Para exibir o status da implantação

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Grupos** &gt; **Visão Geral**.

2.  Execute uma das seguintes etapas:

    -   Selecione **Todos os Usuários** e clique duas vezes no usuário cujos dispositivos você deseja examinar. Na página **Propriedades do Usuário**, selecione **Dispositivos** e clique duas vezes no dispositivo que você deseja examinar.

    -   Selecione **Todos os Dispositivos** &gt; **Todos os Dispositivos Móveis**. Na página **Propriedades do Grupo de Dispositivos**, selecione **Dispositivos** e clique duas vezes no dispositivo que você deseja examinar.

3.  Na página **Propriedades do Dispositivo Móvel**, selecione **Política** para ver uma lista das políticas de gerenciamento de aplicativo móvel que foram implantados no dispositivo.

4.  Selecione a política de gerenciamento de aplicativo móvel cujo status você deseja exibir. Você pode ver detalhes da política no painel inferior e expandir o nó para exibir as configurações.

5.  Na coluna **Status** de cada uma das políticas de gerenciamento de aplicativo móvel, **Compatível**, **Compatível (Pendente)**ou **Erro** aparecerá. Se a política selecionada tiver uma ou mais configurações conflitantes, **Erro** aparecerá nesse campo.

6.  Após ter identificado um conflito, você pode revisar as configurações de política conflitantes para usar a mesma configuração ou pode implantar apenas uma política para o aplicativo e o usuário.

### <a name="how-policy-conflicts-are-resolved"></a>Como os conflitos de política são resolvidos
Quando houver um conflito de política de gerenciamento de aplicativo móvel na primeira implantação para o usuário ou dispositivo, o valor da configuração específica em conflito será removido da política implantada para o aplicativo. O aplicativo usará um valor de conflito interno.

Quando houver um conflito de política de gerenciamento de aplicativo móvel em implantações posteriores ao aplicativo ou usuário, o valor da configuração específica em conflito não será atualizado na política de gerenciamento de aplicativos móveis implantada para o aplicativo. O aplicativo usará o valor existente para essa configuração.

Em casos em que o dispositivo ou usuário receber duas políticas conflitantes, o comportamento a seguir se aplicará:

-   Se já tiver sido implantada uma política para o dispositivo, as configurações de política existentes não serão substituídas.

-   Se nenhuma política tiver sido implantada no dispositivo e duas configurações conflitantes forem implantadas, a configuração padrão integrada no dispositivo será usada.
