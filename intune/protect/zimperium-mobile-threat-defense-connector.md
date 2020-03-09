---
title: Conector do Zimperium MTD ao Intune
titleSuffix: Intune on Azure
description: Saiba como integrar o Intune com a Defesa contra Ameaças Móveis do Zimperium para controlar o acesso de dispositivos móveis aos recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 975d8d84-792a-41ad-925a-4a7f1ae4dcaf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 32ace832e44f1cb6d334f69a0c1f03cb41515b2f
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782039"
---
# <a name="zimperium-mobile-threat-defense-connector-with-intune"></a>Conector do Zimperium Mobile Threat Defense ao Intune

Você pode controlar o Acesso de dispositivos móveis aos recursos corporativos usando o Acesso Condicional com base na avaliação de risco realizada pelo Zimperium, uma solução de MTD (Defesa contra Ameaças Móveis) integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos que executam o aplicativo Zimperium.

Você pode configurar políticas de Acesso Condicional com base na avaliação de risco do Zimperium, habilitadas por meio de políticas de conformidade do dispositivo do Intune para dispositivos registrados, que podem ser usadas para permitir ou bloquear o acesso de dispositivos não compatíveis a recursos corporativos, com base nas ameaças detectadas. Para dispositivos não registrados, você pode usar políticas de proteção de aplicativo para impor um bloqueio ou apagamento seletivo com base em ameaças detectadas.

## <a name="how-do-intune-and-zimperium-help-protect-your-company-resources"></a>Como o Intune e o Zimperium ajudam a proteger os recursos da empresa?

O aplicativo Zimperium para Android e iOS/iPadOS captura o sistema de arquivos, a pilha de rede e, quando disponível, a telemetria dos dispositivos e dos aplicativos, e envia os dados telemétricos ao serviço de nuvem do Zimperium para avaliar o risco ao dispositivo causado por ameaças móveis.

A política de conformidade do dispositivo do Intune inclui uma regra para o Zimperium Mobile Threat Defense, que se baseia na avaliação de risco do Zimperium. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada. Se o dispositivo for considerado não compatível, o acesso dos usuários aos recursos corporativos como o Exchange Online e o SharePoint Online será bloqueado. Os usuários também recebem diretrizes do aplicativo Zimperium instalado nos dispositivos para resolver o problema e recuperar o acesso aos recursos corporativos.

## <a name="sample-scenarios"></a>Exemplo de cenários

Veja abaixo alguns cenários de integração do Zimperium ao Intune:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Controlar o acesso com base em ameaças de aplicativos mal-intencionados

Quando aplicativos mal-intencionados, como malwares, são detectados nos dispositivos, é possível bloquear os dispositivos até que a ameaça seja resolvida:

- Conectar-se ao email corporativo

- Sincronizar arquivos corporativos com o aplicativo OneDrive for Work

- Acessar aplicativos da empresa

**Bloquear quando aplicativos mal-intencionados forem detectados:**

![Imagem conceitual de aplicativos mal-intencionados detectados](./media/zimperium-mobile-threat-defense-connector/Maliciousapps_blocked_Zimperium.png)

**Concessão do acesso após a correção:**

![Imagem conceitual do acesso concedido após a correção](./media/zimperium-mobile-threat-defense-connector/maliciousapps_unblocked_Zimperium.png)

### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede

Detecta ameaças como **Man-in-the-middle** na rede e protege o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloquear o acesso à rede por meio de Wi-Fi:**

![Bloquear o acesso à rede por meio de Wi-Fi](./media/zimperium-mobile-threat-defense-connector/network_wifi_blocked_Zimperium.png)

**Concessão do acesso após a correção:**

![Acesso concedido após a correção](./media/zimperium-mobile-threat-defense-connector/network_wifi_unblocked_Zimperium.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede

Detectar ameaças como **Man-in-the-middle** na rede e impede a sincronização de arquivos corporativos com base no risco ao dispositivo.

**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**

![Bloquear o SharePoint Online quando ameaças à rede forem detectadas](./media/zimperium-mobile-threat-defense-connector/network_spo_blocked_Zimperium.png)

**Concessão do acesso após a correção:**

![Acesso concedido após correção para exemplo do Sharepoint](./media/zimperium-mobile-threat-defense-connector/network_spo_unblocked_Zimperium.png)

## <a name="supported-platforms"></a>Plataformas com Suporte

- **Android 4.1 e posterior**

- **iOS 8 e posterior**

## <a name="prerequisites"></a>Pré-requisitos

- Azure Active Directory Premium

- Assinatura do Microsoft Intune

- Assinatura do Zimperium Mobile Threat Defense

  - Para obter mais informações, confira o [site do Zimperium](https://www.zimperium.com/zips-mobile-ips).

## <a name="next-steps"></a>Próximas etapas

- [Integrar o Zimperium ao Intune](zimperium-mtd-connector-integration.md)

- [Configurar os aplicativos do Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Criar política de conformidade do dispositivo Zimperium](mtd-device-compliance-policy-create.md)

- [Habilitar o conector do Zimperium MTD](mtd-connector-enable.md)

- [Criar uma política de proteção de aplicativo MTD](../protect/mtd-app-protection-policy.md)
