---
title: Habilitar a Consulta MTP no Intune | Microsoft Intune
description: "Habilite a proteção contra ameaças móveis Lookout no console de administrador do Intune."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1334500471d2aea5e8c58a3219c755bfd9953424
ms.openlocfilehash: 4ae7d6c571f69c0cc51dc15355e50325afb88694


---

# Habilite a conexão da Consulta MTP no console de administrador do Intune
Este tópico mostra como habilitar a conexão com a Consulta MTP no Intune. Você precisa ter configurado o Conector do Intune no console da Consulta MTP antes de realizar esta etapa.  Se ainda não tiver feito isso, siga as etapas descritas em  [Set up your subscription with Lookout mobile threat protection](set-up-your-subscription-with-lookout-mtp.md) (Configurar sua assinatura com a proteção contra ameaças móveis Lookout).

Para habilitar a conexão com o Consulta MTP no Intune, na página **Administração** no [Console do Administrador do Microsoft Intune](https://manage.microsoft.com), escolha **Integração de Serviço de Terceiros**. Escolha **Status do Lookout** e habilite **Sincronização com MTP** usando o botão de alternância.

![captura de tela da página de sincronização do Lookout com o botão de alternância habilitar realçado](../media/mtp/lookout-intune-synchronization.png)

Isso conclui a configuração da integração do Lookout com o Intune no console do administrador do Intune.  As próximas etapas para implementar esta solução envolvem a implantação de [aplicativos do Lookout for Work](configure-and-deploy-lookout-for-work-apps.md) e a configuração da política de [conformidade](enable-device-threat-protection-rule-in-compliance-policy.md).

>[!IMPORTANT]
> Você **precisa** configurar o aplicativo do Lookout for Work antes de criar regras de política de conformidade e configurar o acesso condicional. Isso garante que o aplicativo esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.
## Próximas etapas
[Configurar o aplicativo Lookout for Work ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Sep16_HO2-->


