---
title: Habilitar o Lookout MTP no Intune
description: "Habilite a proteção contra ameaças móveis Lookout no console de administrador do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: aad5b158e1217155c3e3ec671654ee6e81054675
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="enable-lookout-mtd-connection-in-the-intune-classic-console"></a>Habilite a conexão da Consulta MTD no console clássico do Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Para habilitar a conexão do MTD (defesa contra ameaças móveis) do Lookout no Intune, você já deve ter configurado o Conector do Intune no console do Lookout.  Se você ainda não fez isso, é necessário [Configurar sua assinatura na Defesa contra Ameaças Móveis do Lookout](setup-your-lookout-mtd-subscription.md).

Para habilitar a conexão com o Consulta MTP no Intune, na página **Administração** no [Console do Administrador do Microsoft Intune](https://manage.microsoft.com), escolha **Integração de Serviço de Terceiros**. Escolha **Status do Lookout** e habilite **Sincronização com MTP** usando o botão de alternância.

![captura de tela da página de sincronização do Lookout com o botão de alternância habilitar realçado](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Você **precisa** configurar o aplicativo do Lookout for Work antes de criar regras de política de conformidade e configurar o acesso condicional. Isso garante que o aplicativo esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.

Isso conclui a configuração da integração do Lookout com o Intune no console do administrador do Intune.  As próximas etapas para implementar esta solução envolvem a implantação da política dos [aplicativos do Lookout for Work](/intune-classic/deploy-use/device-threat-protection-policy).


## <a name="next-steps"></a>Próximas etapas
[Configurar o aplicativo Lookout for Work ](/intune-classic/deploy-use/device-threat-protection-apps)
