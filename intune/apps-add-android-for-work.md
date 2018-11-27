---
title: Atribuir aplicativos a dispositivos de perfil de trabalho Android
titlesuffix: Microsoft Intune
description: Entenda como sincronizar e atribuir aplicativos a dispositivos de perfil de trabalho Android por meio da Google Play Store gerenciada.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: c7d5d29df0f91a4cff1060cd10a5d2355e196e39
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180129"
---
# <a name="assign-apps-to-android-work-profile-devices-with-intune"></a>Atribuir aplicativos a dispositivos de perfil de trabalho Android com o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Android Enterprise é um programa para dispositivos de perfil de trabalho Android e dispositivos de quiosque. Para dispositivos de perfil de trabalho Android, o Android Enterprise é um conjunto de recursos e serviços que separam os aplicativos e dados pessoais dos aplicativos e dados de trabalho. O Android Enterprise oferece privacidade e opções de gerenciamento adicionais quando as pessoas usam seus dispositivos Android para trabalhar. O Intune ajuda você a implantar aplicativos e configurações em dispositivos de perfil de trabalho Android para garantir que suas informações pessoais e de trabalho fiquem separadas. Todos os aplicativos instalados nos dispositivos de perfil de trabalho Android vêm da Google Play Store gerenciada. A maneira de atribuir aplicativos a dispositivos de perfil de trabalho Android é diferente da maneira de atribuí-los a dispositivos Android padrão. Faça logon na Store, procure os aplicativos desejados e aprove-os. O aplicativo aparece no nó **Aplicativos licenciados** do Portal do Azure e você pode gerenciar a atribuição do aplicativo como faria com qualquer outro aplicativo.

Além disso, se você criou seus próprios aplicativos LOB (linha de negócios), poderá atribuí-los da seguinte maneira:
- Inscreva-se em uma conta de Desenvolvedor do Google que permite publicar aplicativos em uma área particular da Google Play Store.
- Sincronize os aplicativos com o Intune.

## <a name="before-you-start"></a>Antes de começar

Verifique se você configurou o Intune e os perfis de trabalho Android para trabalharem juntos na carga de trabalho de **Registro de dispositivo** do Portal do Azure. Para obter mais informações, confira [Registrar dispositivos Android](android-work-profile-enroll.md).

## <a name="synchronize-an-app-from-the-managed-google-play-store"></a>Sincronizar um aplicativo da Google Play Store gerenciada

1. Acesse a [Google Play Store gerenciada](https://play.google.com/work). Entre com a mesma conta que foi usada para configurar a conexão entre o Intune e o Android Enterprise.
2. Pesquise na Store e selecione o aplicativo que deseja atribuir usando o Intune.
3. Na página que exibe o aplicativo, selecione **Aprovar**.  
    No exemplo a seguir, o aplicativo do Microsoft Excel foi escolhido.

    ![O botão Aprovar na Google Play Store gerenciada](media/approve.png)
    
   Uma janela do aplicativo se abrirá solicitando que você conceda permissões para o aplicativo executar várias operações. 

4. Selecione **Aprovar** para aceitar as permissões do aplicativo e continuar.

    ![O botão Aprovar para permissões de aplicativo](media/approve-app-permissions.png)

5. Selecione uma opção de gerenciamento das novas solicitações de permissão de aplicativo e, em seguida, selecione **Salvar**.

    ![Opções para gerencia novas solicitações de permissão de aplicativo](media/approve-app-settings.png)

    O aplicativo é aprovado e exibido no console do administrador de TI. Em seguida, você poderá [sincronizar o aplicativo de perfil de trabalho Android com o Intune](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## <a name="sync-a-managed-google-play-app-with-intune"></a>Sincronizar um aplicativo do Google Play gerenciado com o Intune

Se você aprovou um aplicativo da loja e ainda não o encontrou no nó **Aplicativos licenciados** da carga de trabalho **Aplicativos clientes**, force uma sincronização imediata da seguinte maneira:

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Aplicativos clientes**.
4. No painel da carga de trabalho **Aplicativos clientes**, em **Instalação**, selecione **Google Play gerenciado**.
5. No painel **Google Play gerenciado**, escolha **Atualizar**.  
    A página atualiza a hora e o status da última sincronização.
6. No painel da carga de trabalho **Aplicativos clientes**, selecione **Aplicativos**.  
    O aplicativo que acabou de ficar disponível no Google Play gerenciado é exibido.

Quando o aplicativo for exibido no nó **Licenças de aplicativo** do painel da carga de trabalho **Aplicativos clientes**, você poderá [atribuí-lo, assim como atribuiria qualquer outro aplicativo](/intune-azure/manage-apps/deploy-apps). O aplicativo pode ser atribuído somente em grupos de usuários.

Depois de atribuir o aplicativo, ele é instalado nos dispositivos de destino. A aprovação da instalação do dispositivo não é solicitada ao usuário.

## <a name="manage-android-enterprise-app-permissions"></a>Gerenciar permissões de aplicativo do Android Enterprise
O Android Enterprise exige que você aprove aplicativos no console Web do Google Play gerenciado antes de sincronizá-los com o Intune e atribuí-los aos usuários. Como Android Enterprise permite que você envie por push de maneira silenciosa e automática os aplicativos aos dispositivos dos usuários, você precisa aceitar as permissões do aplicativo em nome de todos os usuários. Os usuários não veem as permissões dos aplicativos quando os instalam, portanto, é importante que você entenda essas permissões.

Quando um desenvolvedor de aplicativo atualiza as permissões com uma nova versão do aplicativo, as permissões não são aceitas automaticamente, mesmo se você aprovou as permissões anteriores. Os dispositivos que executam a versão antiga do aplicativo ainda podem usá-lo. No entanto, só é feito o upgrade do aplicativo quando as novas permissões são aprovadas. Os dispositivos sem o aplicativo instalado só instalam o aplicativo quando você aprova as novas permissões do aplicativo.

### <a name="update-app-permissions"></a>Atualizar as permissões do aplicativo

Periodicamente, acesse o console gerenciado do Google Play para verificar se há novas permissões. Você pode configurar o Google Play para enviar um email a você ou a outras pessoas quando novas permissões forem necessárias para um aplicativo aprovado. Se você atribuir um aplicativo e observar que ele não está instalado nos dispositivos, verifique as novas permissões seguindo estas etapas:

1. Vá ao [Google Play](http://play.google.com/work).
2. Entre com a conta do Google usada para publicar e aprovar os aplicativos.
3. Selecione a guia **Atualizações** e verifique se todos os aplicativos precisam de atualização.  
    Os aplicativos listados exigem novas permissões e só são atribuídos quando elas são aplicadas.

Como alternativa, você pode configurar o Google Play para aprovar permissões de aplicativo novamente de forma automática por aplicativo. 

## <a name="working-with-a-line-of-business-app-from-the-managed-google-play-store"></a>Trabalhando com um aplicativo de linha de negócios da Google Play Store gerenciada

1. Entre no [Console do desenvolvedor do Google Play](https://play.google.com/apps/publish) com a mesma conta que foi usada para configurar a conexão entre o Intune e o Android Enterprise.  
    Se você estiver entrando pela primeira vez, será necessário se registrar e pagar uma taxa para se tornar membro do programa de Desenvolvedor do Google.
2. No console, selecione **Adicionar novo aplicativo**.
3. Carregue e forneça informações sobre o aplicativo da mesma maneira que você publica aplicativos na loja do Google Play. No entanto, você deve selecionar **Disponibilizar este aplicativo somente para minha organização (<*nome da organização*>)**.

    ![Disponibilizar o aplicativo apenas para a sua organização](media/restrict.png)

    Essa operação faz com que o aplicativo fique disponível somente para sua organização. Ele não ficará disponível na Google Play Store pública.

    Para saber mais sobre como carregar e publicar aplicativos Android, veja [Ajuda do Console do Desenvolvedor do Google](https://support.google.com/googleplay/android-developer/answer/113469).
4. Depois de publicar o aplicativo, entre na [Google Play Store gerenciada](https://play.google.com/work) com a mesma conta que foi usada para configurar a conexão entre o Intune e o Android Enterprise.
5. No nó **Aplicativos** da Store, verifique se o aplicativo que você publicou aparece.  
    A sincronização do aplicativo com o Intune é aprovada automaticamente.

## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos](apps-deploy.md) 

