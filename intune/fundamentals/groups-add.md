---
title: Adicionar grupos para organizar usuários e dispositivos
titleSuffix: Microsoft Intune
description: Adicione grupos para organizar usuários e dispositivos por particularidades de localização geográfica, departamento ou hardware.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/13/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7477d8c6325d801d575f2fee66dc9cbee363ce61
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726486"
---
# <a name="add-groups-to-organize-users-and-devices"></a>Adicionar grupos para organizar usuários e dispositivos
O Intune usa grupos do AD (Azure Active Directory) para gerenciar dispositivos e usuários. Como administrador do Intune, você pode configurar grupos para atender às necessidades da sua organização. Crie grupos para organizar usuários ou dispositivos por localização geográfica, departamento ou características de hardware. Use grupos para gerenciar tarefas em grande escala. Por exemplo, você pode definir políticas para vários usuários ou implantar aplicativos em um conjunto de dispositivos.

Você pode adicionar os seguintes tipos de grupos:
- **Grupos atribuídos** – Adicione usuários ou dispositivos manualmente em um grupo estático
- **Grupos dinâmicos** – (Usando o Azure Active Directory Premium) Permitem que você crie dinamicamente grupos de usuários ou de dispositivos definidos com regras simples ou avançadas

## <a name="add-a-new-group"></a>Adicionar um novo grupo

Use as etapas a seguir para criar um novo grupo.
1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel do **Intune**, escolha **Grupos** e, em seguida, escolha **Novo grupo** no painel **Todos os grupos**.
   ![Captura de tela do Portal do Azure com o novo grupo selecionado](./media/groups-add/groups-add-new.png)
4. Para **Tipo de grupo**, escolha uma das seguintes opções:
    - **Segurança**: Grupos de segurança são um bom recurso para usar ao popular grupos de usuários. Como os grupos de segurança definem quem tem acesso a quais recursos, eles podem ser bem traduzidos em grupos de usuários do Intune. Os grupos de segurança sincronizados do Active Directory com o Azure Active Directory ou criados diretamente no Azure Active Directory por meio do centro de administração do Microsoft 365 ou do portal do Azure estão disponíveis para serem usados quando você cria grupos de usuários no Intune.
    - **Office 365**

5. Digite um **Nome** e uma **Descrição** para o novo grupo. Essas propriedades só aparecem no portal de gerenciamento e não são exibidas para os usuários.

6. Escolha o **Tipo de associação**:
   - **Atribuído** para criar um grupo com membros atribuídos manualmente. Saiba mais sobre [Grupos atribuídos do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
   - **Usuário Dinâmico** para criar um grupo de usuários definidos com uma **Consulta dinâmica**.
   - **Dispositivo Dinâmico** para criar um grupo de dispositivos definidos com uma **Consulta dinâmica**.

   ![Captura de tela das propriedades do grupo do Intune](./media/groups-add/groups-add-properties.png)

   O Azure AD permite criar grupos dinâmicos com base nas regras que definem a associação. Aprenda a [criar grupos dinâmicos com base em atributo](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

7. Você pode selecionar **Habilitar recursos do Office** para conceder acesso aos membros do grupo de usuários para aplicativos do Office 365 compartilhados. Saiba mais sobre os [Grupos do Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
8. Escolha **Criar** para adicionar o novo grupo.

## <a name="groups-and-policies"></a>Grupos e políticas

Quando criar grupos, pense em como você aplicará [políticas](../protect/device-compliance-get-started.md). Por exemplo, você pode ter políticas específicas ao sistema operacional de um dispositivo e políticas específicas a diferentes funções em sua organização ou a unidades organizacionais que você já definiu no Active Directory. Pode ser útil ter grupos de dispositivos separados para iOS, Android e Windows, bem como um grupo de usuários para cada função organizacional.

É possível que você também queira criar uma política padrão que se aplica a todos os grupos e dispositivos, para estabelecer os requisitos de conformidade básicos da sua organização. Em seguida, você pode criar políticas mais específicas para as categorias mais amplas de usuários e dispositivos. Por exemplo, você pode criar políticas de email para cada um dos sistemas operacionais do dispositivo.



## <a name="see-also"></a>Consulte também
- [Gerenciar o acesso a recursos com grupos do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Grupos clássicos do Intune no Portal do Azure](groups-get-started.md)
