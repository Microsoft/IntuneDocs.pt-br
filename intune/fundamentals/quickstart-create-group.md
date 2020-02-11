---
title: Início Rápido – Criar um grupo para gerenciar usuários
titleSuffix: Microsoft Intune
description: Neste início rápido você usará o Microsoft Intune para criar um grupo com base em usuários existentes.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/17/2020
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d9b06043dd10f92b6176d4b2e9f90f1b7c87aac9
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76540938"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Início Rápido: Criar um grupo para gerenciar usuários

Neste início rápido, você usará o Intune para criar um grupo com base em usuários existentes. Os grupos são usados para gerenciar os usuários e controlar o acesso dos funcionários aos recursos da empresa. Esses recursos podem fazer parte da intranet da empresa ou recursos externos, como sites do SharePoint, aplicativos SaaS ou aplicativos Web.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

>[!NOTE]
>O Intune fornece os grupos **Todos os Usuários** e **Todos os Dispositivos** pré-criados no console, com otimizações internas para sua conveniência.

## <a name="prerequisites"></a>Pré-requisitos

- Assinatura do Microsoft Intune – [inscreva-se para uma conta de avaliação gratuita](../fundamentals/free-trial-sign-up.md).
- Para concluir esse início rápido, é preciso [criar um usuário](quickstart-create-user.md).

## <a name="sign-in-to-intune-in-the-microsoft-endpoint-manager"></a>Entre no Intune no Gerenciador de Ponto de Extremidade da Microsoft

Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) como [Administrador global ou Administrador de serviços do Intune](users-add.md#types-of-administrators). Se você tiver criado uma assinatura de avaliação do Intune, a conta com a qual você criou a assinatura será a de administrador Global.

## <a name="create-a-group"></a>Criar um grupo

Você criará um grupo que será usado posteriormente nesta série de início rápido. Para criar um grupo:

1. Após abrir o **Gerenciador de Ponto de Extremidade da Microsoft**, selecione **Grupos** > **Novo grupo**.
2. Na caixa suspensa **Tipo de grupo**, selecione **Segurança**.
3. No campo **Nome do grupo**, insira o nome do novo grupo (por exemplo, **Testes da Contoso**).
4. Adicione uma **Descrição do grupo** para o grupo.
5. Defina o **Tipo de associação** como **Atribuído**. 
6. Em **Membros**, selecione o link e adicione um ou mais membros para o grupo na lista.

    ![Captura de tela da criação de um grupo no Microsoft Intune](./media/quickstart-create-group/quickstart-use-groups-01.png)

7. Clique em **Selecionar** > **Criar**.

Depois de ter criado o grupo com êxito, ele aparecerá na lista de **Todos os grupos**. 

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você usará o Intune para criar um grupo com base em usuários existentes. Para obter mais informações sobre como adicionar grupos ao Intune, confira [Adicionar grupos para organizar usuários e dispositivos](../groups-add.md).

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início rápido: Configurar o registro automático para dispositivos Windows 10](../enrollment/quickstart-setup-auto-enrollment.md)
