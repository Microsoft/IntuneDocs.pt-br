---
title: Crie grupos para organizar usuários e dispositivos
description: Criar usuários e grupos para sua assinatura do Intune
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 02/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8e023035dabea653b289b767ff08801b13068a9e
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="create-groups-to-organize-users-and-devices"></a>Crie grupos para organizar usuários e dispositivos

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico informa os administradores como eles podem criar grupos de usuários do Intune.

Os grupos no Intune oferecem grande flexibilidade para o gerenciamento de dispositivos e usuários. Você pode configurar grupos para atender às suas necessidades organizacionais (por exemplo, por localização geográfica, departamento ou características de hardware) e usá-los para executar uma variedade de tarefas administrativas, da implantação de políticas para um conjunto de usuários à implantação de aplicativos para um conjunto de dispositivos.

## <a name="group-management-moving-to-azure-ad"></a>Gerenciamento de grupo migrando para o Azure AD

**A partir de novembro de 2016**, novas contas gerenciarão grupos de usuários e dispositivos no portal do Azure AD (Active Directory). Em dezembro de 2016, a equipe de produtos do Intune iniciará a migração de clientes existentes para a nova experiência de gerenciamento de grupos baseada no Azure AD. Todos os grupos de dispositivos e usuários serão migrados para grupos de segurança do Azure AD. Não começaremos as migrações até que possamos minimizar o efeito sobre seu trabalho diário e quando esperarmos que não haja nenhum efeito sobre seus usuários. Também notificaremos você antes de migrar sua conta.


>[!IMPORTANT]
>
>Se você abrir o espaço de trabalho Grupos no portal do Intune e vir **Grupos de usuários do Intune agora são gerenciados como grupos no Azure Active Directory** com um link para o portal do Azure Active Directory, então você já está usando a *nova* abordagem de grupos de segurança do Azure AD para o gerenciamento de grupos no Intune. Para saber como criar grupos, consulte [Gerenciar grupos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
>
>Caso não esteja vendo o link para o portal do Azure AD, você ainda está usando o portal do Intune para gerenciamento de grupos.

## <a name="group-management-in-the-intune-portal"></a>Gerenciamento de grupos no portal do Intune

Os grupos de usuários e de dispositivos são criados no espaço de trabalho GRUPOS do console de administração do Intune.

![Espaço de trabalho de grupos do console de administração](./media/groups.png)


> [!TIP]
> Para saber mais sobre como usar grupos, consulte [Use groups to manage users and devices with Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune) (Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune).


## <a name="create-a-device-group"></a>Criar um grupo de dispositivos
Use grupos de dispositivos para implantar aplicativos e atualizações e para configurar outros recursos. Por exemplo, configure um grupo "Meus Dispositivos" usando as seguintes etapas:

1.  No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** > **Visão Geral** > **Criar Grupo**.

2.  Em **Nome do Grupo**, digite “Meus Dispositivos” e, na lista de grupos pai, selecione **Todos os Dispositivos** e selecione **Avançar**.

3.  Na página **Definir critérios de associação** , selecione **Todos os dispositivos** , para indicar que o grupo inclui tanto dispositivos móveis quanto computadores.

4.  Na página **Definir Associação Direta**, selecione **Avançar**. Caso você tenha criado anteriormente um grupo que não incluiu todos os dispositivos e deseje adicionar dispositivos específicos ao seu novo grupo, você pode fazer isso aqui.

5.  Na página **Resumo**, examine as ações que serão tomadas e, em seguida, escolha **Concluir**.

O grupo recém-criado pode ser encontrado na lista **Grupos**, no espaço de trabalho **Grupos**, em **Todos os Dispositivos**. Nesse local, também é possível editar ou excluir o grupo.

## <a name="create-a-user-group"></a>Criar um grupo de usuários
Use grupos de usuários para implantar políticas de dispositivo e software. Por exemplo, configure um grupo "Usuários do Intune" usando as seguintes etapas:

1.  No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** > **Visão Geral** > **Criar Grupo**.

2.  Em **Nome do Grupo**, digite “Usuários do Intune” e, na lista de grupos pai, selecione **Todos os Usuários** e selecione **Avançar**.

3.  Na página **Definir Critérios de Associação** , defina **Iniciar associação de grupo com** como **Todos os usuários no grupo Pai**.

4.  Ao lado de **Excluir membros destes grupos de segurança**, escolha **Procurar** e, em seguida, selecione **Administrador da Empresa**. Essa exclusão permite gerenciar o grupo Usuários do Intune sem afetar a conta Administrador da empresa (também conhecida como administrador de locatários).

5.  Na página **Definir Associação Direta**, selecione **Avançar**. Você não precisa fazer nada aqui porque deseja que o grupo Usuários do Intune inclua todos os usuários, exceto o Administrador da Empresa.

6.  Na página **Resumo**, examine as ações que serão tomadas e, em seguida, escolha **Concluir**.

O grupo recém-criado pode ser encontrado na lista **Grupos**, no espaço de trabalho **Grupos**, em **Todos os usuários**. Nesse local, também é possível editar ou excluir o grupo.

>[!div class="step-by-step"]
/intune/licenses-assign [&larr; **Gerenciar licenças do Intune**](/intune/licenses-assign)       [**Criar políticas e aplicativos** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)  
