---
title: Adicionar grupos para organizar usuários e dispositivos
titleSuffix: Microsoft Intune
description: Adicione grupos para organizar usuários e dispositivos por particularidades de localização geográfica, departamento ou hardware.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e3219e32ef9bea838f0c19258d0b22a99083a12
ms.sourcegitcommit: 1a22b8b31424847d3c86590f00f56c5bc3de2eb5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74261604"
---
# <a name="add-groups-to-organize-users-and-devices"></a>Adicionar grupos para organizar usuários e dispositivos

O Intune usa grupos do Azure Active Directory (Azure AD) para gerenciar dispositivos e usuários. Como administrador do Intune, você pode configurar grupos para atender às necessidades da sua organização. Crie grupos para organizar usuários ou dispositivos por localização geográfica, departamento ou características de hardware. Use grupos para gerenciar tarefas em grande escala. Por exemplo, você pode definir políticas para vários usuários ou implantar aplicativos em um conjunto de dispositivos.

Você pode adicionar os seguintes tipos de grupos:

- **Grupos atribuídos** – adicione usuários ou dispositivos manualmente em um grupo estático. 
- **Grupos dinâmicos** (requer Azure AD Premium) – adicione automaticamente usuários ou dispositivos a grupos de usuários ou de dispositivos com base em uma expressão criada por você.

  Por exemplo, quando um usuário é adicionado com o título de gerente, ele é adicionado automaticamente a um grupo de usuários **Todos os gerentes**. Ou, quando um dispositivo tem o tipo de sistema operacional do dispositivo iOS, ele é adicionado automaticamente a um grupo de dispositivos **Todos os dispositivos iOS**.

## <a name="add-a-new-group"></a>Adicionar um novo grupo

Use as etapas a seguir para criar um novo grupo.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Grupos** > **Novo grupo**:

   ![Captura de tela do portal do Azure com Novo grupo selecionado](./media/groups-add/groups-add-new.png)

3. Em **Tipo de grupo**, escolha uma das seguintes opções:

    - **Segurança**: Os grupos de segurança definem quem pode acessar recursos e são recomendados para seus grupos no Intune. Por exemplo, você pode criar grupos para usuários, como **Todos os funcionários da Alice** ou **Todas as mulheres na Contoso**. Ou crie grupos para dispositivos, como **Todos os dispositivos iOS** ou **Todos os dispositivos Windows 10 de alunos**.

        > [!TIP]
        > Os usuários e grupos criados também podem ser vistos no [Centro de administração do Microsoft 365](https://admin.microsoft.com), no centro de administração do Azure Active Directory e no [Microsoft Intune no portal do Azure](https://go.microsoft.com/fwlink/?linkid=2090973). No locatário de sua organização, você pode criar e gerenciar grupos em todas estas áreas.
        >
        > Se sua função principal for gerenciamento de dispositivos, recomendamos que você use o [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft ](https://go.microsoft.com/fwlink/?linkid=2109431).

    - **Office 365**: esses grupos foram projetados para controlar o acesso e compartilhar recursos do Office 365. Por exemplo, você pode criar um grupo do Office 365 para compartilhar uma caixa de entrada ou calendário do Outlook. Para obter mais informações, confira [Saiba mais sobre Grupos do Office 365](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

4. Insira o **Nome do grupo** e a **Descrição do grupo** para o novo grupo. Seja específico e inclua informações para que outras pessoas saibam qual é o objetivo do grupo.

    Por exemplo, insira **Todos os dispositivos Windows 10 de alunos** como nome do grupo e **Todos os dispositivos Windows 10 usados por alunos do Ensino Médio da Contoso** para a descrição do grupo.

5. Insira o **Tipo de associação**. Suas opções:

    - **Atribuído**: os administradores atribuem usuários ou dispositivos manualmente a esse grupo e também os removem manualmente.
    - **Usuário dinâmico**: os administradores criam regras de associação para adicionar e remover membros automaticamente.
    - **Dispositivo dinâmico**: os administradores criam regras de grupo dinâmicas para adicionar e remover dispositivos automaticamente.

        ![Captura de tela das propriedades do grupo do Intune](./media/groups-add/groups-add-properties.png)

    Para obter mais informações sobre esses tipos de associação e criar expressões dinâmicas, confira:

    - [Criar um grupo básico e adicionar membros usando o Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    - [Regras de associação dinâmicas para grupos no Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)

    > [!NOTE]
    > No centro de administração, quando você cria usuários ou grupos, pode não ver a identidade visual do **Azure Active Directory**. Mas é ela que você está usando.

6. Escolha **Criar** para adicionar o novo grupo. Seu grupo é mostrado na lista.

> [!TIP]
> Considere alguns dos outros grupos de usuários e dispositivos dinâmicos que você pode criar, como:
>
> - Todos os alunos do Ensino Médio da Contoso
> - Todos os Dispositivos Android Enterprise
> - Todos os dispositivos iOS 11 e mais antigos
> - Marketing
> - Recursos humanos
> - Todos os funcionários da Alice
> - Todos os funcionários do WA

## <a name="groups-and-policies"></a>Grupos e políticas

O acesso aos recursos de sua organização é controlado pelos usuários e grupos que você cria.

Ao criar grupos, considere como você aplicará [políticas de conformidade](../protect/device-compliance-get-started.md) e [perfis de configuração](../configuration/device-profiles.md). Por exemplo, você pode ter:

- Políticas específicas para um sistema operacional do dispositivo.
- Políticas específicas para diferentes funções em sua organização.
- Políticas específicas para unidades organizacionais que você definiu no Active Directory.

Para criar os requisitos básicos de conformidade de sua organização, você pode criar uma política padrão que se aplique a todos os grupos e dispositivos. Em seguida, pode criar políticas mais específicas para as categorias mais amplas de usuários e dispositivos. Por exemplo, você pode criar políticas de email para cada um dos sistemas operacionais do dispositivo.

Para obter recomendações e diretrizes do perfil de configuração, confira [Atribuir políticas a grupos de usuários ou grupos de dispositivos](../configuration/device-profile-assign.md#user-groups-vs-device-groups) e [recomendações de perfil](../configuration/device-profile-create.md#recommendations).

## <a name="see-also"></a>Consulte também

- [RBAC (controle de acesso baseado em função) com o Microsoft Intune](role-based-access-control.md)
- [Gerenciar o acesso a recursos com grupos do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
