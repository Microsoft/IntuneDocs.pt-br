---
title: "Adicionar grupos para organizar usuários e dispositivos"
titlesuffix: Microsoft Intune
description: "Adicione grupos para organizar usuários e dispositivos por particularidades de localização geográfica, departamento ou hardware."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b7d2b551832d8d0e467d079df673954318623e4c
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="add-groups-to-organize-users-and-devices"></a>Adicionar grupos para organizar usuários e dispositivos
O Intune usa grupos do AD (Azure Active Directory) para gerenciar dispositivos e usuários. Como administrador do Intune, você pode configurar grupos para atender às necessidades da sua organização. Crie grupos para organizar usuários ou dispositivos por localização geográfica, departamento ou características de hardware. Use grupos para gerenciar tarefas em grande escala. Por exemplo, você pode definir políticas para vários usuários ou implantar aplicativos em um conjunto de dispositivos.

Este tópico explica como adicionar grupos para serem usados no Intune.

Você pode adicionar os seguintes tipos de grupos:
- **Grupos atribuídos** – Adicione usuários ou dispositivos manualmente em um grupo estático
- **Grupos dinâmicos** – (Usando o Azure Active Directory Premium) Permitem que você crie dinamicamente grupos de usuários ou de dispositivos definidos com regras simples ou avançadas

## <a name="add-a-new-group"></a>Adicionar um novo grupo

Use as etapas a seguir para criar um novo grupo.
1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel do **Intune**, escolha **Grupos** e, em seguida, escolha **Novo grupo** no painel **Todos os grupos**.
  ![Captura de tela do Portal do Azure com o novo grupo selecionado](./media/groups-add-new.png)
2. Especifique um **Tipo de grupo**, o **Nome** e a **Descrição** do novo grupo. Essas propriedades só aparecem no portal de gerenciamento e não são exibidas para os usuários.

3. Escolha o **Tipo de associação**:
  - **Atribuído** para criar um grupo com membros atribuídos manualmente. Saiba mais sobre [Grupos atribuídos do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Usuário Dinâmico** para criar um grupo de usuários definidos com uma **Consulta dinâmica**.
  - **Dispositivo Dinâmico** para criar um grupo de dispositivos definidos com uma **Consulta dinâmica**.

  ![Captura de tela das propriedades do grupo do Intune](./media/groups-add-properties.png)

  O Azure AD permite criar grupos dinâmicos com base nas regras que definem a associação. Aprenda a [criar grupos dinâmicos com base em atributo](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

4. Você pode selecionar **Habilitar recursos do Office** para conceder acesso aos membros do grupo de usuários para aplicativos do Office 365 compartilhados. Saiba mais sobre os [Grupos do Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
5. Escolha **Criar** para adicionar o novo grupo.

## <a name="see-also"></a>Veja também
- [Gerenciar o acesso a recursos com grupos do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Grupos clássicos do Intune no Portal do Azure](groups-get-started.md)
