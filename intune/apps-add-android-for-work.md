---
title: Atribuir aplicativos a dispositivos Android for Work
titlesuffix: Microsoft Intune
description: Saiba como sincronizar e atribuir aplicativos a dispositivos Android for Work no Google Play for Work.
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
ms.openlocfilehash: 1742c33642667a9e7b8ca2f780094345959cd86c
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="assign-apps-to-android-for-work-devices-with-intune"></a>Atribuir aplicativos a dispositivos Android for Work com o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Android for Work é um programa para dispositivos Android. Todos os aplicativos instalados em dispositivos Android for Work são obtidos na loja Google Play for Work. A maneira pela qual aplicativos são atribuídos a dispositivos Android for Work e dispositivos Android padrão é diferente. Faça logon na Store, procure os aplicativos desejados e aprove-os. O aplicativo aparece no nó **Aplicativos licenciados** do Portal do Azure e você pode gerenciar a atribuição do aplicativo como faria com qualquer outro aplicativo.

Além disso, se você criou seus próprios aplicativos LOB (linha de negócios), poderá atribuí-los da seguinte maneira:
- Inscreva-se em uma conta de Desenvolvedor do Google que permite publicar aplicativos em uma área particular da Google Play Store.
- Sincronize os aplicativos com o Intune.

## <a name="before-you-start"></a>Antes de começar

Verifique se você configurou o Intune e o Android for Work para trabalharem juntos na carga de trabalho **Registro de dispositivo** do Portal do Azure.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Sincronize um aplicativo da loja do Google Play for Work

1. Vá para a [loja do Google Play for Work](https://play.google.com/work). Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work.
2. Pesquise na Store e selecione o aplicativo que deseja atribuir usando o Intune.
3. Na página que exibe o aplicativo, selecione **Aprovar**.  
    No exemplo a seguir, o aplicativo do Microsoft Excel foi escolhido.

    ![O botão Aprovar no Google Play for Work](media/approve.png)
    
   Uma janela do aplicativo se abrirá solicitando que você conceda permissões para o aplicativo executar várias operações. 

4. Selecione **Aprovar** para aceitar as permissões do aplicativo e continuar.

    ![O botão Aprovar para permissões de aplicativo](media/approve-app-permissions.png)

5. Selecione uma opção de gerenciamento das novas solicitações de permissão de aplicativo e, em seguida, selecione **Salvar**.

    ![Opções para gerencia novas solicitações de permissão de aplicativo](media/approve-app-settings.png)

    O aplicativo é aprovado e exibido no console do administrador de TI. Em seguida, você pode [sincronizar o aplicativo Android for Work com o Intune](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## <a name="sync-an-android-for-work-app-with-intune"></a>Sincronizar um aplicativo Android for Work com o Intune

Se você aprovou um aplicativo da loja e ainda não o encontrou no nó **Aplicativos licenciados** da carga de trabalho **Aplicativos móveis**, force uma sincronização imediata da seguinte maneira:

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Aplicativos móveis**.
4. No painel de carga de trabalho **Aplicativos móveis**, em **Instalação**, selecione **Android for Work**.
5. No painel **Android for Work**, escolha **Sincronizar**.  
    A página atualiza a hora e o status da última sincronização.
6. No painel de carga de trabalho **Aplicativos móveis**, selecione **Aplicativos**.  
    O recém-lançado aplicativo do Android for Work é exibido.

Quando o aplicativo for exibido no nó **Aplicativos licenciados** do painel de carga de trabalho **Aplicativos móveis**, você poderá [atribuí-lo, assim como atribuiria qualquer outro aplicativo](/intune-azure/manage-apps/deploy-apps). O aplicativo pode ser atribuído somente em grupos de usuários.

Depois de atribuir o aplicativo, ele é instalado nos dispositivos de destino. A aprovação da instalação do dispositivo não é solicitada ao usuário.

## <a name="manage-android-for-work-app-permissions"></a>Gerenciar permissões de aplicativo do Android for Work
O Android for Work exige que você aprove aplicativos no console da Web gerenciado do Google Play antes de sincronizá-los com o Intune e atribuí-los aos usuários. Como Android for Work permite que você envie de maneira silenciosa e automática os aplicativos aos dispositivos dos usuários, você deve aceitar as permissões do aplicativo em nome de todos os seus usuários. Os usuários não veem as permissões do aplicativo ao instalarem os aplicativos; portanto, é importante que você leia e entenda essas permissões.

Quando um desenvolvedor de aplicativo publica uma nova versão do aplicativo com permissões atualizadas, as permissões não são automaticamente aceitas, mesmo se você tiver aprovado as permissões anteriores. Os dispositivos que executam a versão antiga do aplicativo ainda podem usá-lo. No entanto, só é feito o upgrade do aplicativo quando as novas permissões são aprovadas. Os dispositivos sem o aplicativo instalado só instalam o aplicativo quando você aprova as novas permissões do aplicativo.

### <a name="update-app-permissions"></a>Atualizar as permissões do aplicativo

Periodicamente, acesse o console gerenciado do Google Play para verificar se há novas permissões. Você pode configurar o Google Play para enviar um email a você ou a outras pessoas quando novas permissões forem necessárias para um aplicativo aprovado. Se você atribuir um aplicativo e observar que ele não está instalado nos dispositivos, verifique se há novas permissões da seguinte maneira:

1. Vá ao [Google Play](http://play.google.com/work).
2. Entre com a conta do Google usada para publicar e aprovar os aplicativos.
3. Selecione a guia **Atualizações** e verifique se todos os aplicativos precisam de atualização.  
    Os aplicativos listados exigem novas permissões e só são atribuídos quando elas são aplicadas.

Como alternativa, você pode configurar o Google Play para aprovar permissões de aplicativo novamente de forma automática por aplicativo. 

## <a name="working-with-a-line-of-business-app-from-the-google-play-for-work-store"></a>Trabalhando com um aplicativo de linha de negócios da loja Google Play for Work

1. Entre no [Console do desenvolvedor do Google Play](https://play.google.com/apps/publish) com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work.  
    Se você estiver entrando pela primeira vez, será necessário se registrar e pagar uma taxa para se tornar membro do programa de Desenvolvedor do Google.
2. No console, selecione **Adicionar novo aplicativo**.
3. Carregue e forneça informações sobre o aplicativo da mesma maneira que você publica aplicativos na loja do Google Play. No entanto, você deve selecionar **Disponibilizar este aplicativo somente para minha organização (<*nome da organização*>)**.

    ![Disponibilizar o aplicativo apenas para a sua organização](media/restrict.png)

    Essa operação garante que o aplicativo estará disponível apenas para a sua organização e não no Google Play público.

    Para saber mais sobre como carregar e publicar aplicativos Android, veja [Ajuda do Console do Desenvolvedor do Google](https://support.google.com/googleplay/android-developer/answer/113469).
4. Depois de publicar o aplicativo, entre no [Google Play for Work](https://play.google.com/work) com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work.
5. No nó **Aplicativos** da Store, verifique se o aplicativo que você publicou aparece.  
    A sincronização do aplicativo com o Intune é aprovada automaticamente.

## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos](apps-deploy.md) 

