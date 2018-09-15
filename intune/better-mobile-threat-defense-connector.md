---
title: Conector de Defesa contra Ameaças do Better Mobile com o Intune
titleSuffix: Intune on Azure
description: Configure o Conector de Defesa contra Ameaças do Better Mobile com o Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 7/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.openlocfilehash: 25a6c892284b6014fc3090b3e673c6385ccbad13
ms.sourcegitcommit: 973a06f4a35b74314fece2bae17dd6885b4211c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42823214"
---
# <a name="better-mobile-threat-defense-connector-with-intune"></a>Conector de Defesa contra Ameaças do Better Mobile com o Intune

Você pode controlar o acesso de dispositivos móveis aos recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Better Mobile, uma solução de MTD (Defesa contra Ameaças Móveis) integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos que executam o aplicativo Better Mobile.

Você pode configurar políticas de acesso condicional com base na avaliação de risco do Better Mobile, habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos incompatíveis a recursos corporativos, com base nas ameaças detectadas.

## <a name="how-do-intune-and-better-mobile-help-protect-your-company-resources"></a>Como o Intune e o Better Mobile ajudam a proteger os recursos da empresa?

O aplicativo Better Mobile é instalado e executado em dispositivos móveis. Esse aplicativo captura o sistema de arquivos, a pilha de rede, o dispositivo e a telemetria de aplicativos, quando disponível, e envia os dados para o serviço de nuvem do Better Mobile para avaliar o risco de ameaças móveis ao dispositivo.

A política de conformidade do dispositivo do Intune inclui uma regra para a Defesa contra Ameaças Móveis, que se baseia na avaliação de risco do Better Mobile. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada. Se o dispositivo for considerado não compatível, o acesso dos usuários aos recursos corporativos como o Exchange Online e o SharePoint Online será bloqueado. Os usuários também recebem diretrizes do aplicativo Better Mobile instalado nos dispositivos para resolver o problema e recuperar o acesso aos recursos corporativos.

## <a name="sample-scenarios"></a>Cenários de exemplo

Confira alguns cenários comuns.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Controlar o acesso com base em ameaças de aplicativos mal-intencionados

Quando aplicativos mal-intencionados, como malware, são detectados nos dispositivos, é possível impedir as seguintes ações dos dispositivos até que a ameaça seja resolvida:

-   Conectar-se ao email corporativo

-   Sincronizar arquivos corporativos com o aplicativo OneDrive for Work

-   Acessar aplicativos da empresa

**Bloquear quando aplicativos mal-intencionados forem detectados:**

![Aplicativos mal-intencionados detectados](./media/better_mobile_maliciousapps_blocked.png)

**Concessão do acesso após a correção:**

![Acesso concedido a aplicativos mal-intencionados detectado](./media/better_mobile_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede

Detecta ameaças à rede, como ataques **Man-in-the-middle** e protege o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloquear o acesso à rede por meio de Wi-Fi:**

![Bloquear o acesso à rede por meio de Wi-Fi](./media/better_mobile_network_wifi_blocked.png)

**Concessão do acesso após a correção:**

![Acesso concedido após a correção](./media/better_mobile_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede

Detecta ameaças à rede, como ataques **Man-in-the-middle** e impede a sincronização de arquivos corporativos com base no risco do dispositivo.

**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**

![Bloquear o SharePoint Online quando ameaças à rede forem detectadas](./media/better_mobile_network_spo_blocked.png)

**Concessão do acesso após a correção:**

![Acesso concedido após correção para exemplo do Sharepoint](./media/better_mobile_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Plataformas com Suporte

-   **Android 4.1 e posterior**

-   **iOS 8.0 e posterior**

## <a name="prerequisites"></a>Pré-requisitos

-   Azure Active Directory Premium

-   Assinatura do Microsoft Intune

-   Assinatura da Defesa contra Ameaças do Better Mobile

    -   Para mais informações, consulte o [site do Better Mobile](https://www.better.mobi/).

## <a name="next-steps"></a>Próximas etapas

- [Integrar o Better Mobile com o Intune](better-mobile-mtd-connector-integration.md)

- [Configurar aplicativos Better Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Criar uma política de conformidade do dispositivo Better Mobile](mtd-device-compliance-policy-create.md)

- [Ativar conector MTD Better Mobile](mtd-connector-enable.md)