---
title: Acesso condicional com o Microsoft Intune
titlesuffix: ''
description: Saiba como definir as condições que os usuários, dispositivos e aplicativos devem atender para acessar os recursos da empresa no Microsoft Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 03/06/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a62166792570c5bb81391d05d1cbc3f8486543a4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31022332"
---
# <a name="whats-conditional-access"></a>O que é o acesso condicional?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Acesso condicional significa às formas de controlar os dispositivos e aplicativos que têm permissão para se conectar ao email e aos recursos da empresa. Neste tópico, saiba mais sobre acesso condicional baseado em dispositivo e em aplicativo, e veja cenários comuns para usar o acesso condicional com o Intune.

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
