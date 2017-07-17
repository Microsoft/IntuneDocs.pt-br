---
title: "Introdução ao Intune"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef58e46118a0a44609abba5de4986b5a1526a151
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# O que é o Microsoft Intune?
<a id="what-is-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

![Microsoft Intune no Portal do Azure](./media/generic-intune-azure.png)

O Microsoft Intune é um dos serviços mais novos do Azure. Ele oferece ferramentas para gerenciar dispositivos móveis, computadores e aplicativos da sua organização que são [atualizadas regularmente](whats-new.md). Além do console moderno do Azure, o Intune também permite que você use o console Clássico. O console Clássico é a primeira versão do Intune que ainda é acessado para [gerenciar computadores Windows com o cliente de software do Intune](/intune-classic/deploy-use/pc-management-comparison.md). O portal Clássico, que é criado no Silverlight, é usado para um pequeno número de tarefas. Todo o resto, incluindo o gerenciamento de dispositivos móveis e aplicativos, é realizado no Portal do Azure. O guia de introdução aborda as tarefas básicas que você precisa realizar para usar o Intune no Portal do Azure com êxito.

![A folha de ajuda e suporte, disponível na parte inferior da lista de ações na barra lateral esquerda do Intune.](./media/intune-azure-help-support-closeup.png)

## O que o Intune no Portal do Azure oferece?
<a id="what-does-intune-in-the-azure-portal-provide" class="xliff"></a>

O Intune no Portal do Azure fornece:

* Um console integrado para todos os seus [componentes de EMS (Enterprise Mobility + Security)](https://docs.microsoft.com/enterprise-mobility-security)
* Um console baseado em HTML criado em padrões da Web que dá suporte aos [navegadores da Web modernos](supported-devices-browsers.md)
* [Grupos do Azure Active Directory](groups-get-started.md) para fornecer compatibilidade entre todos os aplicativos do Azure
* Automação por meio da [API do Microsoft Graph](intune-graph-apis.md)

## Pré-requisitos
<a id="prerequisites" class="xliff"></a>

Antes de começar, você deve ter uma conta de administrador e de locatário do Intune ativadas. Você pode se inscrever para essas contas [aqui](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20). Os assinantes atuais também podem executar essas atividades em seu locatário dinâmico. Verifique se que você está trabalhando somente em dispositivos de teste!

Também é necessário verificar se você é o administrador global da sua organização para concluir todas as tarefas no guia.
