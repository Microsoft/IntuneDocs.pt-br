---
title: "Definir restrições de registro no Intune"
titleSuffix: Intune on Azure
description: Restrinja o registro pela plataforma e defina um limite de registro de dispositivo no Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce779e8dad2c9813d5faf1f03bca9b33690508fe
ms.sourcegitcommit: b287025b1a0d09d41faf51cf98c34b676fa1d98e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2017
---
# <a name="add-groups-in-intune"></a>Adicionar grupos no Intune
O Intune usa grupos do AD (Azure Active Directory) para gerenciar dispositivos e usuários. Como administrador do Intune, você pode configurar grupos para atender às necessidades da sua organização. Crie grupos para organizar usuários ou dispositivos por localização geográfica, departamento ou características de hardware. Use grupos para gerenciar tarefas em grande escala. Por exemplo, você pode definir políticas para vários usuários ou implantar aplicativos em um conjunto de dispositivos.

Este tópico explica como adicionar grupos para serem usados no Intune.

Você pode adicionar os seguintes tipos de grupos:
- **Grupos atribuídos** – Adicione usuários ou dispositivos manualmente em um grupo estático
- **Grupos dinâmicos** – (Azure Active Directory Premium) Permitem que você crie dinamicamente grupos de usuários ou dispositivos definidos com regras simples ou avançadas

## <a name="add-a-new-group"></a>Adicionar um novo grupo

Use as etapas a seguir para criar um novo grupo.
1. No Portal do Intune, acesse **Grupos** e escolha **Novo grupo** na folha **Todos os grupos**.
  ![Captura de tela do Portal do Intune com o novo grupo selecionado](./media/groups-add-new.png)
2. Especifique o **Nome** e a **Descrição** do novo grupo. Essas propriedades só aparecem no Portal do Intune e não são exibidas para os usuários.

3. Escolha o **Tipo de associação**:
  - **Atribuído** para criar um grupo com membros atribuídos manualmente. Saiba mais sobre [Grupos atribuídos do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Usuário Dinâmico** para criar um grupo de usuários definidos com uma **Consulta dinâmica**.
  - **Dispositivo Dinâmico** para criar um grupo de dispositivos definidos com uma **Consulta dinâmica**.

  ![Captura de tela das propriedades do grupo do Intune com Nome, Descrição, Tipo de associação, Habilitar recursos do Office e Membros](./media/groups-add-properties.png)

  O Azure AD permite criar grupos dinâmicos com base nas regras que definem a associação. Aprenda a [criar grupos dinâmicos com base em atributo](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

4. Você pode selecionar **Habilitar recursos do Office** para conceder acesso aos membros do grupo de usuários para aplicativos do Office 365 compartilhados.
5. Escolha **Criar** para adicionar o novo grupo.

## <a name="see-also"></a>Veja também
- [Gerenciar o acesso a recursos com grupos do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Grupos clássicos do Intune no Portal do Azure](groups-get-started.md)
