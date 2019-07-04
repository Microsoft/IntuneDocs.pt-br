---
title: Configurar a MTD do Check Point SandBlast
titleSuffix: Microsoft Intune
description: Saiba como integrar o Intune com a Defesa contra Ameaças Móveis do Check Point SandBlast para controlar o acesso de dispositivos móveis aos recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba12b8c8561d02a9bcf7bc7286bcbaa096d2b2ee
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67045315"
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a>Conector da Defesa contra Ameaças Móveis do Check Point SandBlast com o Intune

É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o Acesso Condicional com base na avaliação de risco realizada pelo Check Point SandBlast Mobile, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos executando o aplicativo Check Point SandBlast Mobile.

Você pode configurar políticas de Acesso Condicional com base na avaliação de risco do Check Point SandBlast Mobile, habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos não compatíveis aos recursos corporativos com base em ameaças detectadas.

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a>Como o Intune e o Check Point SandBlast Mobile ajudam a proteger os recursos da empresa?

O aplicativo móvel do Check Point SandBlast Mobile para Android e iOS captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível e envia os dados de telemetria ao serviço de nuvem do Check Point SandBlast para avaliar o risco causado por ameaças móveis ao dispositivo.

A política de conformidade do dispositivo do Intune inclui uma regra para Defesa contra Ameaças Móveis do Check Point SandBlast, que tem base na avaliação de risco do Check Point SandBlast. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada. Se o dispositivo for considerado não compatível, o acesso dos usuários aos recursos corporativos como o Exchange Online e o SharePoint Online será bloqueado. Os usuários também recebem diretrizes do aplicativo móvel do Check Point SandBlast para resolver o problema e recuperar o acesso aos recursos corporativos.

<!-- ## Sample scenarios 
closing syntax for comment above is missing. Please insert closing syntax at intended location. -->

Confira alguns cenários comuns:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Controlar o acesso com base em ameaças de aplicativos mal-intencionados

Quando aplicativos mal-intencionados, como malwares, são detectados nos dispositivos, é possível bloquear os dispositivos até que a ameaça seja resolvida:

-   Conectar-se ao email corporativo

-   Sincronizar arquivos corporativos com o aplicativo OneDrive for Work

-   Acessar aplicativos da empresa

**Bloquear quando aplicativos mal-intencionados forem detectados:**

![Bloqueio de MTD do Check Point quando aplicativos mal-intencionados são detectados](./media/checkpoint-MTD-2.PNG)

**Concessão do acesso após a correção:**

![Acesso concedido pelo MTD do Check Point](./media/checkpoint-MTD-3.PNG)

### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede

Detecte ameaças como  **Man-in-the-middle**  na rede e proteja o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloquear o acesso à rede por meio de Wi-Fi:**

![Bloqueio de MTD do Check Point do acesso a rede por meio de Wi-Fi](./media/checkpoint-MTD-4.PNG)

**Concessão do acesso após a correção:**

![Acesso Wi-Fi concedido pelo MTD do Check Point](./media/checkpoint-MTD-5.PNG)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede

Detecte ameaças como  **Man-in-the-middle**  na rede e impeça a sincronização de arquivos corporativos com base no risco do dispositivo.

**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**

![Bloqueio de MTD do Check Point do acesso ao SharePoint Online](./media/checkpoint-MTD-6.PNG)

**Concessão do acesso após a correção:**

![Acesso ao SharePoint Online concedido pelo MTD do Check Point](./media/checkpoint-MTD-7.PNG)

## <a name="supported-platforms"></a>Plataformas com Suporte

-   **Android 4.1 e posterior**

-   **iOS 8 e posterior**

## <a name="pre-requisites"></a>Pré-requisitos

-   Azure Active Directory Premium

-   Assinatura do Microsoft Intune

-   Assinatura do Check Point SandBlast Mobile para Defesa contra Ameaças Móveis
    -   Consulte o [site do CheckPoint SandBlast](https://www.checkpoint.com/) para obter mais informações.

## <a name="next-steps"></a>Próximas etapas

- [Integrar o CheckPoint SandBlast com o Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

- [Configurar o aplicativo CheckPoint SandBlast Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Criar política de conformidade de dispositivo móvel do CheckPoint SandBlast](mtd-device-compliance-policy-create.md)

- [Habilitar conector de MTD do CheckPoint SandBlast Mobile](mtd-connector-enable.md)
