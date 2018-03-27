---
title: Habilitar a Defesa contra Ameaças Móveis do Skycure no Intune
description: Habilite a Defesa contra Ameaças Móveis do Skycure no Portal Clássico do Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 971600d59a6afe019f5f3bd51459964c168afa82
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Habilitar a Defesa contra Ameaças Móveis do Skycure no Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Para habilitar a defesa contra ameaças móveis do Skycure, você deve já ter configurado o [Conector do Intune no console do Skycure] (/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune).

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>Para habilitar a conexão do Skycure MTD no Intune

1.  Acesse o [Portal Clássico do Intune](https://manage.microsoft.com/) e insira suas credenciais.

2.  Escolha **Administrador** &gt; **Integração de Serviços de Terceiros**, escolha **Status do Skycure** e habilite **Sincronização com MTD** usando o botão de alternância.

    ![Habilitar a alternância do Skycure no Portal Clássico do Intune](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> Você precisa configurar os aplicativos do Skycure antes de criar regras de política de conformidade e configurar o acesso condicional. Isso garante que o aplicativo esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.

Isso conclui a configuração da integração do Skycure com o Intune no console de administrador do Intune. As próximas etapas para implementar esta solução envolvem a implantação de aplicativos do Skycure for Work e a configuração da política de conformidade.

## <a name="next-steps"></a>Próximas etapas

[Criar a política de conformidade da Defesa contra Ameaças Móveis do Skycure](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
