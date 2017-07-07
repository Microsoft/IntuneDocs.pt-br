---
title: Implantar aplicativos em dispositivos Android for Work
description: "Use este tópico para sincronizar e implantar aplicativos em dispositivos Android for Work da Google Play for Work Store."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: adc4a343e610a1a75f8a5bc51a1894f6fcf998bb
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Como implantar aplicativos em dispositivos Android for Work com o Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A maneira pela qual aplicativos são implantados em dispositivos Android for Work e dispositivos Android padrão é diferente. Todos os aplicativos instalados no Android for Work são obtidos na loja do Google Play for Work. Faça logon na loja, procure os aplicativos desejados e aprove-os.
Então, o aplicativo aparecerá no nó **Aplicativos Adquiridos por Volume** do console do Intune. A partir desse momento, é possível gerenciar a implantação do aplicativo do mesmo modo que você implanta qualquer outro aplicativo.

Além disso, se você criou seus próprios aplicativos LOB (linha de negócios), poderá implantá-los da seguinte maneira:
- Inscreva-se em uma conta de Desenvolvedor do Google que permite publicar aplicativos em uma área particular da Google Play Store.
- Sincronize os aplicativos com o Intune.

## <a name="before-you-start"></a>Antes de começar

Verifique se você configurou o Intune e o Android for Work para trabalharem juntos na guia **Admin** do console do Intune.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Sincronize um aplicativo da loja do Google Play for Work


1. Vá para a [loja do Google Play for Work](https://play.google.com/work). Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work.
2. Pesquise o aplicativo que deseja implantar usando o Intune.
3. Na página do aplicativo que você escolheu, escolha **Aprovar**. Neste exemplo, você escolheu o aplicativo Microsoft Excel.<br>
  ![Aprovar o exemplo de aplicativo](media/approve.png)
4. Uma janela do aplicativo se abrirá solicitando que você conceda permissões para o aplicativo executar várias operações. Escolha **Aprovar** para continuar.<br>
  ![Aprovar o exemplo de permissões de aplicativo](media/approve-app-permissions.png)
5. O aplicativo foi aprovado e é exibido no console do administrador de TI.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Publicar e, em seguida, sincronizar um aplicativo de linha de negócios da Google Play for Work Store

1. Acesse o Console do Desenvolvedor do Google Play, em [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work. Se você estiver entrando pela primeira vez, será necessário se registrar e pagar uma taxa para se tornar membro do programa de Desenvolvedor do Google.
3. No console, escolha **Adicionar novo aplicativo**.
4. Carregue e forneça informações sobre o aplicativo da mesma maneira que você publica aplicativos na loja do Google Play. No entanto, você deve selecionar a configuração **Disponibilizar este aplicativo somente para minha organização (<*nome da organização*>)**:<br>
  ![Opção para disponibilizar o aplicativo apenas para sua organização](media/restrict.png)<br>
Essa operação garante que o aplicativo estará disponível apenas para sua organização e não na Google Play Store pública.
Para obter mais informações sobre como carregar e publicar aplicativos Android, consulte [Ajuda do Console do Desenvolvedor do Google](https://support.google.com/googleplay/android-developer/answer/113469).
5. Depois publicar o aplicativo, vá para a [loja do Google Play for Work](https://play.google.com/work). Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work.
6. No nó **Aplicativos** da loja, verifique se o aplicativo que você publicou pode ser visto. Sua sincronização com o Intune é aprovada automaticamente.

## <a name="deploy-an-android-for-work-app"></a>Implantar um aplicativo Android for Work

Se você aprovou um aplicativo da loja e ainda não o encontrou no nó **Aplicativos Comprados por Volume** do espaço de trabalho **Aplicativos**, force uma sincronização imediata da seguinte maneira:

1. No [Console do administrador do Intune](https://manage.microsoft.com), escolha **Admin** > **Gerenciamento de Dispositivo Móvel** > **Android for Work**.
2. Na página **Configuração do Gerenciamento de Dispositivo Móvel do Android for Work**, escolha **Sincronizar Agora**.
3. A página também exibe o tempo e o status da última sincronização.

Quando o aplicativo for exibido no nó **Aplicativos Comprados por Volume** do espaço de trabalho **Aplicativos**, você poderá [implantá-lo, assim como faria com qualquer outro aplicativo](deploy-apps-in-microsoft-intune.md). O aplicativo pode ser implantado somente em grupos de usuários. No momento, você pode selecionar apenas as ações **Necessário** e **Desinstalar**.

A capacidade de implantar um aplicativo como **Disponível** aplica a nova experiência de agrupamento e direcionamento. As contas de serviço do Intune recém-provisionadas podem usar esse recurso após o lançamento. Os clientes atuais do Intune podem usar esse recurso quando seu locatário for migrado no portal do Intune Azure. Os clientes existentes podem criar uma conta de avaliação do Intune para planejar e testar esse recurso até que seus locatários sejam migrados.

Depois de implantar o aplicativo, ele será instalado nos dispositivos de destino. A aprovação do usuário do dispositivo não é solicitada.

## <a name="manage-app-permissions"></a>Gerenciar permissões de aplicativo
O Android for Work exige que você aprove aplicativos no console da web do Play gerenciado do Google antes de sincronizá-los para o Intune e implantá-los para os usuários.  Como Android for Work permite que você envie de maneira silenciosa e automática esses aplicativos para os dispositivos dos usuários, você deve aceitar as permissões do aplicativo em nome de todos os seus usuários.  Os usuários finais não veem as permissões do aplicativo durante a instalação; portanto, é importante que você leia e entenda essas permissões.

Quando um desenvolvedor de aplicativo publica uma nova versão do aplicativo com permissões atualizadas, essas permissões não são automaticamente aceitas, mesmo se você tiver aprovado as permissões anteriores. Os dispositivos que executam a versão antiga do aplicativo ainda poderão usá-lo, mas só será feito o upgrade do aplicativo quando as novas permissões forem aprovadas. Os dispositivos sem o aplicativo instalado não podem instalar o aplicativo até que você aprove novas permissões do aplicativo.

### <a name="how-to-update-app-permissions"></a>Como atualizar as permissões do aplicativo

Periodicamente, acesse o console gerenciado do Google Play para verificar se há novas permissões. Você pode configurar o Google Play para enviar um email a você ou a outras pessoas quando novas permissões forem necessárias para um aplicativo aprovado. Se você atribuir um aplicativo e observar que ele não está instalado nos dispositivos, verifique se há novas permissões com as seguintes etapas:

1. Visite http://play.google.com/work
2. Entre com a conta do Google usada para publicar e aprovar os aplicativos.
3. Visite a guia **Atualizações** para ver se algum aplicativo precisa de atualização.  Os aplicativos listados exigem novas permissões e só são atribuídos quando elas são aplicadas.  

Como alternativa, você pode configurar o Google Play para aprovar permissões de aplicativo novamente de forma automática por aplicativo. 
