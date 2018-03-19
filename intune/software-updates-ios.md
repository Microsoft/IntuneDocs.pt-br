---
title: "Configurar políticas de atualização do iOS no Microsoft Intune"
titlesuffix: 
description: "Configure políticas de atualização do iOS para forçar dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 6ba354fb3b39544f09363651abfd9e1a5c0f6154
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Configurar políticas de atualização do iOS no Microsoft Intune
Políticas de atualização do iOS permitem forçar os dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível. Existe a opção de configurar os dias e horários em que não deseja que os dispositivos instalem a atualização.

## <a name="configure-the-ios-update-policy"></a>Configurar a política de atualização do iOS
1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
2. No painel **Intune**, escolha **Atualizações de software** > **Políticas de Atualização do iOS**.
4. No painel de políticas, escolha **Criar** e, em seguida, insira um nome e uma descrição para a política.
5. Selecione **Configurações** > **Configurar** e insira os detalhes de quando os dispositivos iOS não serão forçados a instalar a atualização mais recente.
6. Escolha **OK** para salvar esta configuração. Agora você retornou à página **Criar política de atualização**. Escolha **Criar** para criar a política e salvar suas configurações.

O perfil é criado e aparece no painel de lista de políticas de atualização do iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Atribuir uma política de atualização do iOS a usuários
Para atribuir uma política de atualização do iOS a usuários, escolha uma política que você configurou. As políticas existentes são encontradas no painel **Atualizações de software** > **Políticas de atualização do iOS**.
1. Escolha a política que você deseja atribuir aos usuários e escolha **Atribuições**. É aberto o painel no qual você pode selecionar grupos de segurança do Azure Active Directory e atribuí-los à política.
2. Escolha **Grupos selecionados** para abrir o painel que exibe os grupos de segurança do Azure AD.
3. Escolha **Salvar** para implantar a política para os usuários.

Você aplicou a política para os usuários. Os dispositivos usados pelos usuários que são afetados pela política são avaliados quanto à conformidade de atualizações.

## <a name="change-the-restricted-days-for-the-policy"></a>Alterar os dias restritos da política
1. No painel **Atualizações de software**, escolha **Políticas de Atualização do iOS**.
2. Selecione a política de atualização do iOS que deseja atualizar.
3. Selecione **Propriedades** > **Configurações** para atualizar as informações de dias restritos.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Monitorar dispositivos iOS com versões anteriores do iOS
<!-- 1352223 -->
O relatório **Dispositivos iOS desatualizados** está disponível no painel **Atualizações de software** > **Políticas de Atualização do iOS**. No relatório, você pode exibir uma lista de dispositivos iOS supervisionados que foram afetados por uma política de atualização do iOS e não puderam ser atualizados. Para cada dispositivo, você pode exibir um status de por que o dispositivo não foi atualizado automaticamente.
