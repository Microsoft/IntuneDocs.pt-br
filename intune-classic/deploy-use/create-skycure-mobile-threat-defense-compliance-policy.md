---
title: "Criar a política de conformidade da Defesa contra Ameaças Móveis do Skycure"
description: "Crie a política de conformidade da Defesa contra Ameaças Móveis do Skycure no console clássico do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56ff1728-1119-4e8a-aae6-ed5c7fafa052
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 29caf162500e25c2a0151be92aabe4cc432e241b
ms.contentlocale: pt-br
ms.lasthandoff: 06/08/2017


---

# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a>Criar a política de conformidade da Defesa contra Ameaças Móveis do Skycure

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Intune com a Defesa contra Ameaças Móveis do Skycure permite detectar ameaças em dispositivos móveis e avaliar o risco nesses dispositivos. Você pode criar uma regra de política de conformidade do Intune que avalia o risco para determinar se o dispositivo está em conformidade. Em seguida, é possível usar a política de acesso condicional para bloquear o acesso a serviços de acordo com a conformidade do dispositivo.

## <a name="before-you-begin"></a>Antes de começar

Pré-requisitos para a política de conformidade com a proteção contra ameaças ao dispositivo do Skycure:

-   [Configurar a integração do Skycure com o Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

-   [Habilitar a conexão do Skycure no Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

Como parte da configuração da Defesa contra Ameaças Móveis do Skycure, no console do Skycure, você criou uma política que classifica diversas ameaças nos níveis alto, médio e baixo. Defina o nível máximo de ameaças permitido na política de conformidade do Intune.

## <a name="to-create-skycure-compliance-policy"></a>Para criar a política de conformidade do Skycure

1.  Acesse o [console clássico Intune](https://manage.microsoft.com/) e insira suas credenciais.

2.  Escolha **Política** &gt; **Políticas de Conformidade**. É possível usar uma política de conformidade existente ou criar uma nova.

3.  Escolha **Adicionar** &gt; **Integridade do Dispositivo** e habilite **Proteção contra Ameaças ao Dispositivo**.

4.  Selecione o **Nível máximo de ameaça permitido**:

    a.  **Nenhum (Seguro)**: este é o mais seguro. O dispositivo não pode ter nenhuma ameaça presente e ainda acessar os recursos da empresa. Se nenhuma ameaça for encontrada, o dispositivo será avaliado como fora de conformidade.

    b.  **Baixo**: o dispositivo estará em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.

    c.  **Médio**: o dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio. Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.

    d.  **Alto**: esta é a opção menos segura. Isso permite todos os níveis de ameaça e usa a Defesa contra Ameaças Móveis do Skycure apenas para fins de relatório.

> [!IMPORTANT]
> Se você criar políticas de acesso condicional para o Office 365 ou outros serviços, essa avaliação de conformidade será avaliada e os dispositivos que não estiverem em conformidade serão impedidos de acessar esses serviços até que a ameaça seja resolvida.

## <a name="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps"></a><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Próximas etapas

-   Criar política de acesso condicional para:

    -   [Exchange Online](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [Exchange Local](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [Skype for Business Online](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [Dynamics CRM](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

