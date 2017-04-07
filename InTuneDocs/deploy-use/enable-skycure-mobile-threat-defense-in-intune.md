---
title: "Habilitar a Defesa contra Ameaças Móveis do Skycure no Intune | Microsoft Docs"
description: "Habilite a Defesa contra Ameaças Móveis do Skycure no console clássico do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: a110f2ae4d8a101a7fb977aa651e5ce2c8828e7e
ms.lasthandoff: 03/22/2017


---

# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Habilitar a Defesa contra Ameaças Móveis do Skycure no Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Para habilitar a conexão do MTD (defesa contra ameaças móveis) do Skycure no Intune, você já deve ter configurado o [Conector do Intune no console do Skycure](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune).

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>Para habilitar a conexão do Skycure MTD no Intune

1.  Acesse o [console clássico Intune](https://manage.microsoft.com/) e insira suas credenciais.

2.  Escolha **Administrador** &gt; **Integração de Serviços de Terceiros**, escolha **Status do Skycure** e habilite **Sincronização com MTD** usando o botão de alternância.

    ![Habilitar alternância do Skycure no console clássico do Intune](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> Você precisa configurar os aplicativos do Skycure antes de criar regras de política de conformidade e configurar o acesso condicional. Isso garante que o aplicativo esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.

Isso conclui a configuração da integração do Skycure com o Intune no console de administrador do Intune. As próximas etapas para implementar esta solução envolvem a implantação de aplicativos do Skycure for Work e a configuração da política de conformidade.

## <a name="next-steps"></a>Próximas etapas

[Criar a política de conformidade da Defesa contra Ameaças Móveis do Skycure](https://docs.microsoft.com/intune/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)

