---
title: "Prepare-se para configurar as políticas de proteção do aplicativo para Windows 10 | Microsoft Docs"
description: "Provedor de instalação do gerenciamento de aplicativos móveis (MAM) no Azure AD"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c48f9181e8fd740ab080a8620f3873909d0fd0f1
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Prepare-se para configurar as políticas de proteção do aplicativo para Windows 10

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Antes de criar uma política de proteção de aplicativo do Windows 10, você precisará habilitar o gerenciamento de aplicativos móveis (MAM) para o Windows 10 configurando o provedor de MAM no Azure AD. Essa configuração permite definir o estado do registro ao criar uma nova política do WIP (Proteção de Informações do Windows) com o Intune.

> [!NOTE]
> O estado do registro pode ser MAM ou MDM (gerenciamento de dispositivo móvel).

## <a name="to-configure-the-mam-provider"></a>Para configurar o provedor de MAM

1.  Vá para o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais do Intune.

2.  No menu à esquerda, escolha **Azure Active Directory**.

    ![Configuração do provedor do MAM](../media/AppManagement/mam-provider-sc-1.png)

3.  A folha **Azure AD** é aberta, escolha **Mobilidade (MDM e MAM)**, em seguida, clique em **Microsoft Intune**.

    ![Mobilidade MDM e MAM](../media/AppManagement/mam-provider-sc-2.png)

4.  A folha de configuração é aberta, escolha **Restaurar as URLs padrão do MAM** primeiro, em seguida, configure o seguinte:

    a.  Escopo do usuário de MAM: você pode usar o MAM para proteger dados corporativos em um grupo específico de usuários que usam dispositivos com Windows 10 ou todos os usuários.

    b.  URL de termos de uso do MAM: a URL do ponto de extremidade dos termos de uso do serviço MAM. Isso é usado para exibir os termos do serviço MAM para os usuários finais.

    c.  URL de descoberta de MAM: essa é a URL que os dispositivos buscam quando precisam aplicar políticas de proteção de aplicativo.

    d.  URL de conformidade do MAM:

5.  Quando você tiver definido essas configurações, selecione **Salvar**.

## <a name="next-steps"></a>Próximas etapas

[Criar uma política de proteção de aplicativo WIP](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune)

