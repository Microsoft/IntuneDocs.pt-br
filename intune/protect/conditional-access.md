---
title: Acesso Condicional com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Saiba como definir as condições que os usuários, dispositivos e aplicativos devem atender para acessar os recursos da empresa no Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: cef8bcf74509d83b076b30a1ee7f2406e622b129
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722638"
---
# <a name="learn-about-conditional-access-and-intune"></a>Saiba mais sobre o Acesso Condicional e o Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Acesso Condicional significa às formas de controlar os dispositivos e aplicativos que têm permissão para se conectar ao email e aos recursos da empresa. Neste tópico, saiba mais sobre Acesso Condicional baseado em dispositivo e em aplicativo, e veja cenários comuns para usar o Acesso Condicional com o Intune.

O Acesso Condicional do EMS (Enterprise Mobility + Security) não é um produto autônomo, mas uma solução que integra todos os serviços e produtos que fazem parte do EMS. Ele fornece controle de acesso granular para proteger os dados da empresa, ao mesmo tempo que oferece aos usuários uma experiência que lhes permite fazer o melhor trabalho em qualquer dispositivo e em qualquer localização.

Você pode definir condições que fornecem acesso aos dados corporativos com base na localização, no dispositivo, no estado do usuário e na sensibilidade do aplicativo.

> [!NOTE] 
> O Acesso Condicional também estende suas funcionalidades aos [serviços do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access).

![Diagrama de arquitetura do Acesso Condicional](./media/conditional-access/ca-diagram-1.png)

## <a name="use-conditional-access-with-intune"></a>Usar o Acesso Condicional com o Intune

O Acesso Condicional é um recurso do Azure Active Directory incluído com uma licença do Azure Active Directory Premium. O Intune aprimora esse recurso, adicionando a conformidade de dispositivo móvel e o gerenciamento de aplicativo móvel à solução. 

![Intune e Acesso Condicional ao usar o EMS](./media/conditional-access/intune-with-ca-1.png)

Formas de usar o Acesso Condicional com o Intune:

- **Acesso Condicional baseado no dispositivo**

  - Acesso Condicional para o Exchange local

  - Acesso Condicional baseado em controle de acesso à rede

  - Acesso Condicional baseado nos riscos do dispositivo

  - Acesso Condicional para computadores Windows

    - De propriedade corporativa

    - BYOD (Traga seu próprio dispositivo)

- **Acesso Condicional baseado no aplicativo**

## <a name="next-steps"></a>Próximas etapas

[Maneiras comuns de usar o Acesso Condicional com o Intune](conditional-access-intune-common-ways-use.md)
