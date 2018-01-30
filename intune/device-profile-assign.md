---
title: Como atribuir perfis de dispositivo com o Intune
titlesuffix: Azure portal
description: "Depois de criar um perfil de dispositivo do Intune, use este tópico para saber como atribuí-lo a dispositivos."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef03eeab32050559d34d3d7d580c06c21f5ffb05
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-assign-microsoft-intune-device-profiles"></a>Como atribuir perfis de dispositivo do Microsoft Intune

## <a name="assign-a-device-profile"></a>Atribuir um perfil de dispositivo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
1. Na folha **Configurações do dispositivo**, escolha **Gerenciar** > **Perfis**.
2. Na folha da lista de perfis, escolha o perfil que você deseja gerenciar e, na folha <*nome do perfil*> **Relatórios**, escolha **Gerenciar** > **Atribuições**.
3. Na folha a seguir, escolha **Incluir** (para incluir grupos) ou **Excluir** (para excluir grupos) e clique em **Selecionar grupos**.
![Incluir e excluir grupos de uma atribuição de perfil.](./media/group-include-exclude.png)
4. Na folha **Selecionar grupos**, escolha os grupos do Azure AD que você deseja incluir ou excluir da atribuição. Você pode manter a tecla **CTRL** pressionada para selecionar vários grupos.
4. Após terminar, na folha **Selecionar grupos**, escolha **Selecionar**.



## <a name="how-to-exclude-groups-from-a-device-profile-assignment"></a>Como excluir grupos de uma atribuição de perfil de dispositivo

Os perfis de configuração de dispositivo do Intune permitem que você exclua grupos da atribuição de política. Por exemplo, você pode atribuir um perfil de dispositivo para o grupo **Todos os usuários corporativos**, mas excluir os membros do grupo **Equipe de Gerenciamento Sênior**.

Ao excluir grupos de uma atribuição, exclua apenas o usuário ou grupos de dispositivos, não uma combinação de grupos. O Intune não leva em conta as associações entre usuário e dispositivo ao excluir grupos. É improvável que você consiga os resultados necessários ao incluir grupos de usuários e excluir grupos de dispositivos. Se utilizar grupos mistos ou em caso de outros conflitos, a inclusão têm prioridade sobre a exclusão.

Por exemplo, digamos que você deseja atribuir um perfil de dispositivo para todos os dispositivos na sua organização, exceto os dispositivos de quiosque. você inclui o grupo **Todos os Usuários**, mas exclui o grupo **Todos os Dispositivos**.

Nesse caso, todos os usuários e seus dispositivos obterão a política, mesmo se o dispositivo do usuário fizer parte do grupo **Todos os Dispositivos**. 

A exclusão somente avalia os membros diretos dos grupos e não inclui os dispositivos que estão associados um usuário. No entanto, dispositivos que não têm um usuário não obterão a política, pois eles não têm uma associação para o grupo **Todos os Usuários**. 

Se você incluir **Todos os Dispositivos**, mas excluir **Todos os Usuários**, todos os dispositivos receberão a política. A intenção nesse caso é excluir dispositivos que têm um usuário associado dessa política. No entanto, ela não funciona, pois o recurso de exclusão compara apenas os membros diretos do grupo. 

>[!Tip]
>Exclusões não estão disponíveis no momento para políticas de conformidade ou atribuição de aplicativo. Para excluir membros de uma atribuição, você pode usar as intenções de atribuição Disponível e Não aplicável. Por exemplo, você pode atribuir um aplicativo **Todos os usuários corporativos** com a intenção **Disponível** e **Equipe de Gerenciamento Sênior** com a intenção **Não aplicável**. o aplicativo é atribuído a todos os usuários, *exceto* aos usuários do grupo **Equipe de Gerenciamento Sênior**. Se você atribuir o aplicativo a **Todos os usuários corporativos** com a intenção **Necessário**, os usuários do grupo **Equipe de Gerenciamento Sênior** não serão excluídos.
 
    
## <a name="next-steps"></a>Próximas etapas
Consulte [Como monitorar perfis de dispositivo](device-profile-monitor.md) para obter informações para ajudar a monitorar as atribuições de perfil de dispositivo.
