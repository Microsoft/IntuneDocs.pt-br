---
title: Início Rápido – Criar e atribuir uma política de proteção de aplicativo
titlesuffix: Microsoft Intune
description: Neste início rápido, você usará o Microsoft Intune para criar e atribuir uma política de proteção de aplicativo.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/09/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2586fce0-5dca-4686-b9c4-791778838401
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e3057009eb758e37a4b42cddc4673bd721d1bce
ms.sourcegitcommit: d8edd1c3d24123762dd6d14776836df4ff2a31dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "51576625"
---
# <a name="quickstart-create-and-assign-an-app-protection-policy"></a>Início Rápido: criar e atribuir uma política de proteção de aplicativo

Nesse início rápido, você usará o Intune para criar e atribuir uma política de proteção de aplicativo para um aplicativo cliente no dispositivo do usuário final. O Intune usa políticas de proteção de aplicativo para confirmar que seus aplicativos atendem aos requisitos de proteção de dados da sua organização.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos

- Para concluir esse início rápido, é preciso [criar um usuário](quickstart-create-user.md), [criar um grupo](quickstart-create-group.md), [registrar um dispositivo](quickstart-setup-auto-enrollment.md) e [adicionar e atribuir um aplicativo](quickstart-add-assign-app.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um [administrador global ou um administrador de serviços do Intune](users-add.md#types-of-administrators). Se você tiver criado uma assinatura de avaliação do Intune, a conta com a qual você criou a assinatura será a de administrador Global.

## <a name="create-an-app-protection-policy"></a>Criar uma política de proteção de aplicativo

Use as seguintes etapas para criar uma política de proteção do aplicativo:

1. No [Intune](https://aka.ms/intuneportal), selecione **Aplicativos clientes** > **Políticas de proteção de aplicativo** > **Criar Política**. 
2. Insira os seguintes detalhes: 

    - **Nome**: *proteção de conteúdo do Windows 10*
    - **Descrição**: *os usuários associados a essa política não poderão recortar, copiar ou colar qualquer conteúdo entre o aplicativo atribuído e outros aplicativos não gerenciados no dispositivo.*
    - **Plataforma**: *Windows 10*
    - **Estado do registro**: *com o registro*

3. Selecione **Aplicativos protegidos** para escolher os aplicativos que devem aderir a esta política.
4. Clique em **Adicionar aplicativos**.
5. Em **Aplicativos recomendados**, selecione **Word Mobile**.
5. Clique em **OK** > **OK**. 
6. Selecione as **Configurações necessárias** para configurar o aplicativo.
7. Clique em **Permitir Substituições** para definir o modo de Proteção de Informações do Windows. Caso essa opção seja selecionada, os dados da empresa não poderão deixar o aplicativo protegido.
8. Clique em **OK** > **Criar**.

Agora, você verá a política de proteção de aplicativo no Intune.

### <a name="assign-the-app-protection-policy"></a>Atribuir a política de proteção do aplicativo

Depois de criar uma política de proteção de aplicativo no Intune, você poderá atribuir a grupos. 

Use as seguintes etapas para atribuir a política de proteção do aplicativo:

1.  No [Intune](https://aka.ms/intuneportal), selecione **Intune** > **Aplicativos cliente** > **Políticas de proteção de aplicativo**. 
2.  Selecione a política de proteção de aplicativo criada anteriormente. Neste início rápido, a política é a **proteção de conteúdo do Windows 10**.
3.  Selecione **Atribuições**.
4.  Clique em **Selecionar grupos para incluir** na guia **Incluir**.
5.  Selecione **Testadores Contoso** como grupo para incluir.
6.  Clique em **Selecionar**. 

Você agora atribuiu a política de proteção de aplicativo.

> [!NOTE]
> As políticas de proteção de aplicativo só podem ser aplicadas aos grupos que contêm usuários, não grupos que contêm dispositivos.

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você criou um usuário e atribuiu uma política de proteção de aplicativo. Os usuários deste aplicativo que têm essa política atribuída não poderão recortar, copiar ou colar qualquer conteúdo entre o aplicativo atribuído e outros aplicativos não gerenciados no dispositivo. Esse tipo de proteção ajudará a proteger dados da sua organização. Para saber mais sobre políticas de proteção de aplicativo no Intune, confira [O que são políticas de proteção de aplicativo?](app-protection-policy.md)

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início Rápido: criar e atribuir uma função personalizada](quickstart-create-custom-role.md)
