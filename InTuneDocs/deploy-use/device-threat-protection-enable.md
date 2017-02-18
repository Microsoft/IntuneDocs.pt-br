---
title: Habilitar o Lookout MTP no Intune | Microsoft Docs
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
translationtype: Human Translation
ms.sourcegitcommit: 53862e49c922b75b414fd5aceec3bba2b10299a6
ms.openlocfilehash: 1297522d0f7b52ebe14eb7b938f3458e7308ae27


---

# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>Habilite a conexão da Consulta MTP no console de administrador do Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Para habilitar a conexão de MTP (proteção contra ameaças mal-intencionadas) do Lookout no Intune, você já deve ter configurado o Conector do Intune no console do Lookout.  Se você ainda não fez isso, é necessário [Configurar sua assinatura no Lookout Mobile Threat Protection](set-up-your-subscription-with-lookout-mtp.md).

Para habilitar a conexão com o Consulta MTP no Intune, na página **Administração** no [Console do Administrador do Microsoft Intune](https://manage.microsoft.com), escolha **Integração de Serviço de Terceiros**. Escolha **Status do Lookout** e habilite **Sincronização com MTP** usando o botão de alternância.

![captura de tela da página de sincronização do Lookout com o botão de alternância habilitar realçado](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Você **precisa** configurar o aplicativo do Lookout for Work antes de criar regras de política de conformidade e configurar o acesso condicional. Isso garante que o aplicativo esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.

Isso conclui a configuração da integração do Lookout com o Intune no console do administrador do Intune.  As próximas etapas para implementar esta solução envolvem a implantação de [aplicativos do Lookout for Work](configure-and-deploy-lookout-for-work-apps.md) e a configuração da política de [conformidade](enable-device-threat-protection-rule-in-compliance-policy.md).


## <a name="next-steps"></a>Próximas etapas
[Configurar o aplicativo Lookout for Work ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Jan17_HO2-->


