---
title: Habilitar o Lookout MTP no Intune
description: Habilite a proteção contra ameaças móveis Lookout no console de administrador do Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/19/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 99c9952b8df3e9b4b1992cbc45366a5ceed458aa
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="enable-lookout-mtd-connection-in-the-intune-classic-portal"></a>Habilite a conexão da Consulta MTD no Portal Clássico do Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Para habilitar a conexão do MTD (defesa contra ameaças móveis) do Lookout no Intune, você já deve ter configurado o Conector do Intune no console do Lookout.  Se você ainda não fez isso, é necessário [Configurar sua assinatura na Defesa contra Ameaças Móveis do Lookout](setup-your-lookout-mtd-subscription.md).

Para habilitar a conexão com o Consulta MTP no Intune, na página **Administração** no [Console do Administrador do Microsoft Intune](https://manage.microsoft.com), escolha **Integração de Serviço de Terceiros**. Escolha **Status do Lookout** e habilite **Sincronização com MTP** usando o botão de alternância.

![captura de tela da página de sincronização do Lookout com o botão de alternância habilitar realçado](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Você **precisa** configurar o aplicativo do Lookout for Work antes de criar regras de política de conformidade e configurar o acesso condicional. Isso garante que o aplicativo esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.

Isso conclui a configuração da integração do Lookout com o Intune no console do administrador do Intune.  As próximas etapas para implementar esta solução envolvem a implantação da política dos [aplicativos do Lookout for Work](/intune-classic/deploy-use/device-threat-protection-policy).


## <a name="next-steps"></a>Próximas etapas
[Configurar o aplicativo Lookout for Work ](/intune-classic/deploy-use/device-threat-protection-apps)
