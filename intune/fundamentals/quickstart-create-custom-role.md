---
title: Início Rápido – Criar e atribuir uma função personalizada no Intune
description: Início Rápido – Criar e atribuir uma função personalizada para um gerenciador de dispositivos remoto.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 03/26/2019
ms.author: erikje
ms.assetid: 0b3ac749-4a61-4717-bf08-e0e6a15c3b0a
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5b38df90e47e709e02f12a6ccdab68714d04ca93
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77575869"
---
# <a name="quickstart-create-and-assign-a-custom-role"></a>Início Rápido: Criar e atribuir uma função personalizada

No início rápido do Intune, você criará uma função personalizada com permissões específicas a um departamento de operações de segurança. Em seguida, você atribuirá a função a um grupo desses operadores. Há várias funções padrão que você pode usar imediatamente. Contudo, ao criar funções personalizadas como essa, você tem controle de acesso preciso sobre todas as partes do seu sistema de gerenciamento de dispositivo móvel.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos

- Para concluir este início rápido, é preciso [criar um grupo](quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune. Se você tiver criado uma assinatura de avaliação do Intune, a conta com a qual você criou a assinatura será a de administrador Global.

## <a name="create-a-custom-role"></a>Criar uma função personalizada

Ao criar uma função personalizada, você pode definir as permissões para uma ampla variedade de ações. Para a função de operações de segurança, definiremos algumas permissões de Leitura para que o operador possa examinar as configurações e políticas de um dispositivo.

1. No Intune, escolha **Funções** > **Todas as funções** > **Adicionar**.
![Navegador](./media/quickstart-create-custom-role/add-custom-role.png)
2. Em **Adicionar função personalizada**, na caixa **Nome**, digite *Operações de segurança*.
3. Na caixa **Descrição**, digite *Essa função permite que um operador monitore informações de configuração e de conformidade do dispositivo.*
4. Escolha **Configurar** > **Identificadores de dispositivo corporativo** > **Sim** ao lado de **Leitura** > **OK**.
![Navegador](./media/quickstart-create-custom-role/corp-device-id-read.png)
5. Escolha **Políticas de conformidade do dispositivo** > **Sim** ao lado de **Leitura** > **OK**.
6. Escolha **Configurações do dispositivo** > **Sim** ao lado de **Leitura** > **OK**.
7. Escolha **Organização** > **Sim** ao lado de **Leitura** > **OK**.
8. Escolha **OK** > **Criar**.

## <a name="assign-the-role-to-a-group"></a>Atribuir uma função a um grupo

Para que seu operador de segurança possa usar as novas permissões, é preciso atribuir a função a um grupo que contém o usuário de segurança.

1. No Intune, escolha **Funções** > **Todas as funções** > **Operações de segurança**.
2. Em **Funções do Intune**, escolha **Atribuições** > **Atribuir**.
3. Na caixa **Nome da atribuição**, digite *Operações seg*.
4. Escolha **Membro (Grupos)**  > **Adicionar**.
5. Escolha o grupo **Testadores Contoso**.
6. Escolher **Selecionar** > **OK**.
7. Escolher **Escopo (Grupos)**  > **Selecionar grupos a serem incluídos** > **Testadores Contoso**.
8. Escolha **Selecionar** > **OK** > **OK**.

Agora, todos no grupo são membros da função *Operações de segurança* e pode examinar as seguintes informações sobre um dispositivo: identificadores de dispositivo corporativo, políticas de conformidade do dispositivo, configurações do dispositivo e informações da organização.

## <a name="clean-up-resources"></a>Limpar os recursos

Se você não quiser mais usar a nova função personalizada, poderá excluí-la. Escolha **Funções** > **Todas as funções** > escolha as reticências ao lado da função > **Excluir**.

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você criou uma função de operações de segurança personalizada e a atribuiu a um grupo. Para obter mais informações sobre funções no Intune, confira [RBAC (controle de administração baseado em funções) com o Microsoft Intune](role-based-access-control.md)

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início rápido: Criar um perfil de dispositivo de email para o iOS/iPadOS](../configuration/quickstart-email-profile.md)
