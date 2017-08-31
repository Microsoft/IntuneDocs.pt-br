---
title: Acesso condicional com o Intune
titleSuffix: Intune on Azure
description: "Saiba como definir as condições que os usuários e dispositivos devem atender para acessar os recursos da empresa no Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7f6f7443224b9ec114f0323d1715f343b0adfec4
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2017
---
# <a name="whats-conditional-access"></a>O que é o acesso condicional?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este tópico descreve o Acesso condicional, conforme ele se aplica ao EMS (Enterprise Mobility + Security) e apresenta, em seguida, cenários comuns do Acesso condicional ao usar o Intune.

O Acesso Condicional do EMS (Enterprise Mobility + Security) não é um produto autônomo, mas uma solução que integra todos os serviços e produtos que fazem parte do EMS. Ele fornece controle de acesso granular para proteger os dados da empresa, ao mesmo tempo que oferece aos usuários uma experiência que lhes permite fazer o melhor trabalho em qualquer dispositivo e em qualquer localização.

Você pode definir condições que fornecem acesso aos dados corporativos com base na localização, no dispositivo, no estado do usuário e na sensibilidade do aplicativo.

> [!NOTE] 
> O Acesso Condicional também estende suas funcionalidades aos [serviços do Office 365](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).

![Diagrama de arquitetura do acesso condicional](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Acesso condicional com o Intune

O Intune adiciona políticas de conformidade de dispositivo móvel e de gerenciamento de aplicativos para dar suporte à solução de Acesso Condicional do EMS.

![Intune e acesso condicional durante o uso do EMS](./media/intune-with-ca-1.png)

Maneiras de usar o acesso condicional com o Intune:

-   **Acesso condicional baseado no dispositivo**

    -   Acesso condicional para o Exchange Local

    -   Acesso condicional baseado em controle de acesso à rede

    -   Acesso condicional baseado nos riscos do dispositivo

    -   Acesso condicional para computadores Windows

        -   De propriedade corporativa

        -   BYOD (Traga seu próprio dispositivo)

-   **Acesso condicional baseado no aplicativo**

## <a name="next-steps"></a>Próximas etapas

[Maneiras comuns de usar o acesso condicional com o Intune](conditional-access-intune-common-ways-use.md)