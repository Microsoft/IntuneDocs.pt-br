---
title: Atribuir aplicativos a dispositivos Android for Work
titlesuffix: Microsoft Intune
description: Saiba como sincronizar e atribuir aplicativos a dispositivos Android for Work na loja Google Play for Work.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4168f78bff8937ca403cdb75b1028954cbbebd6f
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Como atribuir aplicativos em dispositivos Android for Work com o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Android for Work é um programa para dispositivos Android. Todos os aplicativos instalados em dispositivos Android for Work são obtidos na loja Google Play for Work. A maneira pela qual aplicativos são atribuídos em dispositivos Android for Work e dispositivos Android padrão é diferente. Faça logon na loja, procure os aplicativos desejados e aprove-os. Então, o aplicativo aparecerá no nó **Aplicativos licenciados** do Portal do Azure. A partir desse momento, é possível gerenciar a atribuição do aplicativo do mesmo modo que você atribui qualquer outro aplicativo.

Além disso, se você criou seus próprios aplicativos LOB (linha de negócios), poderá atribuí-los da seguinte maneira:
- Inscreva-se em uma conta de Desenvolvedor do Google que permite publicar aplicativos em uma área particular da Google Play Store.
- Sincronize os aplicativos com o Intune.

## <a name="before-you-start"></a>Antes de começar

Verifique se você configurou o Intune e o Android for Work para trabalharem juntos na carga de trabalho **Registro de dispositivo** do Portal do Azure.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Sincronize um aplicativo da loja do Google Play for Work

1. Vá para a [loja do Google Play for Work](https://play.google.com/work). Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work.
2. Pesquise na loja e selecione o aplicativo que deseja atribuir usando o Intune.
3. Selecione **Aprovar** na página que mostra o aplicativo. Os exemplos a seguir mostram que o aplicativo Microsoft Excel foi escolhido.</br>

    ![Exemplo – aprovar o aplicativo na loja Google Play for Work](media/approve.png)</br>
    
   Uma janela do aplicativo se abrirá solicitando que você conceda permissões para o aplicativo executar várias operações. 

4. Selecione **Aprovar** para aceitar as permissões do aplicativo e continuar.</br>

    ![Exemplo – aprovar as permissões do aplicativo](media/approve-app-permissions.png)

5. Escolha como lidar com novas solicitações de permissão do aplicativo. Em seguida, selecione **Salvar** para salvar como as novas solicitações de permissão do aplicativo serão tratadas.</br>

    ![Exemplo – salvar novas solicitações de permissão do aplicativo](media/approve-app-settings.png)</br>

    O aplicativo foi aprovado e é exibido no console do administrador de TI. Agora, você pode [sincronizar o aplicativo Android for Work com o Intune](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## <a name="sync-an-android-for-work-app-with-intune"></a>Sincronizar um aplicativo Android for Work com o Intune

Se você aprovou um aplicativo da loja e ainda não o encontrou no nó **Aplicativos licenciados** da carga de trabalho **Aplicativos móveis**, force uma sincronização imediata da seguinte maneira:

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Android for Work** na seção **Instalação**.
5. No painel Android for Work, escolha **Sincronizar**. A página atualizará a hora e o status da última sincronização.
6. Na carga de trabalho **Aplicativos móveis**, selecione **Aplicativos** para exibir o aplicativo Android for Work que acabou de ser disponibilizado.

Quando o aplicativo for exibido no nó **Aplicativos licenciados** da carga de trabalho **Aplicativos móveis**, você poderá [atribuí-lo, assim como atribuiria qualquer outro aplicativo](/intune-azure/manage-apps/deploy-apps). O aplicativo pode ser atribuído somente em grupos de usuários.

Depois de atribuir o aplicativo, ele será instalado nos dispositivos de destino. A aprovação da instalação do dispositivo não é solicitada ao usuário.

## <a name="manage-android-for-work-app-permissions"></a>Gerenciar permissões de aplicativo do Android for Work
O Android for Work exige que você aprove aplicativos no console da Web do Play gerenciado do Google antes de sincronizá-los para o Intune e atribuí-los para os usuários.  Como Android for Work permite que você envie de maneira silenciosa e automática esses aplicativos para os dispositivos dos usuários, você deve aceitar as permissões do aplicativo em nome de todos os seus usuários.  Os usuários finais não veem as permissões do aplicativo durante a instalação; portanto, é importante que você leia e entenda essas permissões.

Quando um desenvolvedor de aplicativo publica uma nova versão do aplicativo com permissões atualizadas, essas permissões não são automaticamente aceitas, mesmo se você tiver aprovado as permissões anteriores. Os dispositivos que executam a versão antiga do aplicativo ainda podem usá-lo. No entanto, só é feito o upgrade do aplicativo quando as novas permissões são aprovadas. Os dispositivos sem o aplicativo instalado só instalam o aplicativo quando você aprova as novas permissões do aplicativo.

### <a name="how-to-update-app-permissions"></a>Como atualizar as permissões do aplicativo

Periodicamente, acesse o console gerenciado do Google Play para verificar se há novas permissões. Você pode configurar o Google Play para enviar um email a você ou a outras pessoas quando novas permissões forem necessárias para um aplicativo aprovado. Se você atribuir um aplicativo e observar que ele não está instalado nos dispositivos, verifique se há novas permissões com as seguintes etapas:

1. Acesse http://play.google.com/work
2. Entre com a conta do Google usada para publicar e aprovar os aplicativos.
3. Visite a guia **Atualizações** para ver se algum aplicativo precisa de atualização.  Os aplicativos listados exigem novas permissões e só são atribuídos quando elas são aplicadas.  

Como alternativa, você pode configurar o Google Play para aprovar permissões de aplicativo novamente de forma automática por aplicativo. 

## <a name="working-with-a-line-of-business-app-from-the-google-play-for-work-store"></a>Trabalhando com um aplicativo de linha de negócios da loja Google Play for Work

1. Acesse o Console do Desenvolvedor do Google Play, em [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work. Se você estiver entrando pela primeira vez, será necessário se registrar e pagar uma taxa para se tornar membro do programa de Desenvolvedor do Google.
3. No console, escolha **Adicionar novo aplicativo**.
4. Carregue e forneça informações sobre o aplicativo da mesma maneira que você publica aplicativos na loja do Google Play. No entanto, você deve selecionar a configuração **Disponibilizar este aplicativo somente para minha organização (<*nome da organização*>)**:</br>

    ![Opção para disponibilizar aplicativos apenas para a sua organização](media/restrict.png)</br>

Essa operação garante que o aplicativo estará disponível apenas para sua organização e não na Google Play Store pública.
Para obter mais informações sobre como carregar e publicar aplicativos Android, consulte [Ajuda do Console do Desenvolvedor do Google](https://support.google.com/googleplay/android-developer/answer/113469).
5. Depois publicar o aplicativo, vá para a [loja do Google Play for Work](https://play.google.com/work). Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work.
6. No nó **Aplicativos** da loja, verifique se o aplicativo que você publicou pode ser visto. A sincronização do aplicativo com o Intune é aprovada automaticamente.

## <a name="next-steps"></a>Próximas etapas

- [Como atribuir aplicativos aos grupos](apps-deploy.md)

