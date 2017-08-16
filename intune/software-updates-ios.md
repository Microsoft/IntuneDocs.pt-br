---
title: "Configurar políticas de atualização do iOS"
titleSuffix: Intune on Azure
description: "Configure políticas de atualização do iOS para forçar dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível."
keywords: 
author: dougeby
manager: dougeby
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6334421-85e1-4457-9c44-e5db8d4ee00e
ms.openlocfilehash: d4af2d58ec21c54362cf451eac1a33b2088885d5
ms.sourcegitcommit: 7674efb7de5ad54390801165364f5d9c58ccaf84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2017
---
# <a name="configure-ios-update-policies"></a>Configurar políticas de atualização do iOS
Políticas de atualização do iOS permitem forçar os dispositivos iOS supervisionados a instalarem automaticamente a atualização de software mais recente disponível. Existe a opção de configurar os dias e horários em que não deseja que os dispositivos instalem a atualização.

## <a name="configure-the-ios-update-policy"></a>Configurar a política de atualização do iOS
1. Vá para a folha do Intune no portal do Azure.
2. Na folha **Intune**, escolha **Atualizações do Software** > **Políticas de Atualização do iOS**.
4. Na folha de políticas, escolha **criar**e, em seguida, insira um nome e uma descrição para a política.
5. Selecione **Configurações** > **Configurar** e insira os detalhes de quando os dispositivos iOS não serão forçados a instalar a atualização mais recente.
6. Escolha **OK** para salvar esta configuração. Agora, você retornou à folha **Criar uma política de atualização**. Escolha **Criar** para criar a política e salvar suas configurações.

O perfil é criado e exibido na folha da lista de políticas de atualização do iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Atribuir uma política de atualização do iOS a usuários
Para atribuir uma política de atualização do iOS a usuários, escolha uma política que você configurou. As políticas existentes são encontradas na folha **Atualizações de Software** > **Políticas de Atualização do iOS**.
1. Escolha a política que você deseja atribuir aos usuários e escolha **Atribuições**. Isso abrirá a folha na qual é possível selecionar Grupos de segurança do Azure Active Directory e atribuí-los à política.
2. Escolha **Selecionar grupos** para abrir a folha que exibe os grupos de segurança do Azure AD. Escolha **Selecionar** para implantar a política para usuários.

Você aplicou a política para os usuários. A conformidade de atualizações dos dispositivos usados pelos usuários de destino da política será avaliada.

## <a name="change-the-restricted-days-for-the-policy"></a>Alterar os dias restritos da política
1. Na folha **Atualizações do Software**, escolha **Políticas de Atualização do iOS**.
2. Selecione a política de atualização do iOS que deseja atualizar.
3. Selecione **Propriedades** e atualize as informações de dias restritos.
