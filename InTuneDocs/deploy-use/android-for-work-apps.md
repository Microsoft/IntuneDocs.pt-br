---
title: Implantar aplicativos em dispositivos Android para Trabalho | Microsoft Docs
description: "Use este tópico para sincronizar e implantar aplicativos em dispositivos Android for Work da Google Play for Work Store."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0936051b5c33a2e98f275ef7a3a32be2e8f5a8b0
ms.openlocfilehash: 3b608d42f04b9fce457b6b61587d05ab5d59bb0a
ms.lasthandoff: 03/10/2017


---

# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Como implantar aplicativos em dispositivos Android for Work com o Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

A maneira pela qual aplicativos são implantados em dispositivos Android for Work e dispositivos Android padrão é diferente. Todos os aplicativos instalados no Android for Work são obtidos na loja do Google Play for Work. Faça logon na loja, procure os aplicativos que você deseja e aprove-os.
Então, o aplicativo aparecerá no nó **Aplicativos Adquiridos por Volume** do console do Intune. A partir desse momento, é possível gerenciar a implantação do aplicativo do mesmo modo que você implanta qualquer outro aplicativo.

Além disso, se você criou seus próprios aplicativos de linha de negócios (LOB), você pode implantá-los. Para fazer isso, é necessário criar um conta de desenvolvedor do Google, que permite que você publique aplicativos em uma área privada da loja do Google Play e sincronize-os com o Intune.

## <a name="before-you-start"></a>Antes de começar

1. Verifique se você configurou o Intune e o Android for Work para trabalharem juntos na guia **Admin** do console do Intune.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Sincronize um aplicativo da loja do Google Play for Work


1. Vá para a [loja do Google Play for Work](https://play.google.com/work). Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work.
2. Pesquise o aplicativo que deseja implantar usando o Intune.
3. Na página do aplicativo que você escolheu, escolha **Aprovar**. Neste exemplo, você escolheu o aplicativo Microsoft Excel.<br>
  ![Aprovar o exemplo de aplicativo](media/approve.png)
4. Uma janela do aplicativo se abrirá solicitando que você conceda permissões para o aplicativo executar várias operações. Você deve escolher **Aprovar** para continuar.<br>
  ![Aprovar o exemplo de permissões de aplicativo](media/approve-app-permissions.png)
5. Após alguns instantes, você verá uma mensagem de confirmação informando que o aplicativo foi aprovado e está disponível no console do administrador de TI.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Publique e, em seguida, sincronize um aplicativo de linha de negócios da loja do Google Play for Work

1. Acesse o Console do Desenvolvedor do Google Play, em [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work. Se você estiver entrando pela primeira vez, será necessário se registrar e pagar uma taxa para se tornar membro do programa de Desenvolvedor do Google.
3. No console, escolha **Adicionar novo aplicativo**.
4. Carregue e forneça informações sobre o aplicativo da mesma maneira que você publica aplicativos na loja do Google Play. No entanto, você deve selecionar a configuração **Disponibilizar este aplicativo somente para a minha organização (<* nome da organização* >)** , conforme mostrado abaixo.<br>
  ![Opção para disponibilizar o aplicativo apenas para sua organização](media/restrict.png)<br>
Isso garante que o aplicativo estará disponível apenas para a sua organização e não estará disponível na loja pública do Google Play.
Para obter mais informações sobre como carregar e publicar aplicativos Android, consulte [Ajuda do Console do Desenvolvedor do Google](https://support.google.com/googleplay/android-developer/answer/113469).
5. Depois publicar o aplicativo, vá para a [loja do Google Play for Work](https://play.google.com/work). Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work.
6. No nó **Aplicativos** da loja, verifique se o aplicativo que você publicou pode ser visto. Observe que a sincronização do aplicativo com o Intune foi aprovada automaticamente.

## <a name="deploy-an-android-for-work-app"></a>Implantar um aplicativo Android for Work

Se você aprovou um aplicativo da loja e ainda não o encontrou no nó **Aplicativos Adquiridos por Volume** do espaço de trabalho **Aplicativos**, será possível forçar uma sincronização imediata da seguinte maneira:

1. No [Console do administrador do Intune](https://manage.microsoft.com), escolha **Admin** > **Gerenciamento de Dispositivo Móvel** > **Android for Work**.
2. Na página **Configuração do Gerenciamento de Dispositivo Móvel do Android for Work**, escolha **Sincronizar Agora**.
3. A página também exibe o tempo e o status da última sincronização.

Quando o aplicativo for exibido no nó **Aplicativos Adquiridos por Volume** do espaço de trabalho **Aplicativos**, você pode [implantá-lo, assim como faria com qualquer outro aplicativo](deploy-apps-in-microsoft-intune.md). O aplicativo pode ser implantado somente em grupos de usuários. No momento, você pode selecionar apenas as ações **Necessário** e **Desinstalar**.

A capacidade de implantar um aplicativo como **Disponível** utiliza a nova experiência de agrupamento e direcionamento. As contas de serviço do Intune recém-provisionadas poderão usar esse recurso após o lançamento. Os clientes atuais do Intune podem usar esse recurso quando seu locatário for migrado no portal do Intune Azure. Clientes atuais são incentivados a criar uma conta de avaliação do Intune para planejar e testar o recurso até que seu locatário seja migrado.

Depois de implantar o aplicativo, ele será instalado nos dispositivos de destino. A aprovação do usuário do dispositivo não será solicitada.

## <a name="manage-app-permissions"></a>Gerenciar permissões de aplicativo
O Android for Work exige que você aprove aplicativos no console da web do Play gerenciado do Google antes de sincronizá-los para o Intune e implantá-los para os usuários.  Como Android for Work permite que você envie de maneira silenciosa e automática esses aplicativos para os dispositivos dos usuários, você deve aceitar as permissões do aplicativo em nome de todos os seus usuários.  Os usuários finais não verão as permissões do aplicativo ao instalar; portanto, é importante que você leia e entenda essas permissões.

Quando um desenvolvedor de aplicativo publica uma nova versão do aplicativo com permissões atualizadas, essas permissões não são automaticamente aceitas, mesmo se você tiver aprovado as permissões anteriores. Os dispositivos que executarem a versão antiga do aplicativo ainda poderão usá-lo, mas o aplicativo não será atualizado até que as novas permissões sejam aprovadas. Os dispositivos sem o aplicativo instalado não podem instalar o aplicativo até que você aprove novas permissões do aplicativo.

### <a name="how-to-update-app-permissions"></a>Como atualizar as permissões do aplicativo

Periodicamente, você deverá visitar o console gerenciado do Google Play para verificar se há novas permissões. Se você implantar um aplicativo e observar que ele não está instalado nos dispositivos, verifique se há novas permissões com as seguintes etapas:

1. Visite http://play.google.com/work
2. Entre com a conta do Google usada para publicar e aprovar os aplicativos.
3. Visite a guia **Atualizações** para ver se algum aplicativo precisa de atualização.  Todos os aplicativos listados exigem novas permissões e não serão implantados até que isso aconteça.  

