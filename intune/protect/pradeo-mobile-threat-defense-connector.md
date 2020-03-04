---
title: Conector de Defesa Contra Ameaças Móveis do Pradeo com o Intune
titleSuffix: Intune on Azure
description: Saiba como integrar o Intune ao conector da Defesa contra Ameaças Móveis do Pradeo para controlar o acesso de dispositivos móveis aos recursos corporativos.
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
ms.assetid: cde4d389-1770-4226-85a3-a2f3b3fb92a3
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 262d36817e86c8087c6ef4b642d1bd53b1511104
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782105"
---
# <a name="pradeo-mobile-threat-defense-connector-with-intune"></a>Conector de Defesa Contra Ameaças Móveis do Pradeo com o Intune

Você pode controlar o acesso de dispositivos móveis aos recursos corporativos usando o Acesso Condicional com base na avaliação de risco realizada pelo Pradeo, uma solução de MTD (Defesa contra Ameaças Móveis) integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos que executam o aplicativo Pradeo.

Você pode configurar políticas de Acesso Condicional com base na avaliação de risco do Pradeo, habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos fora de conformidade a recursos corporativos, com base nas ameaças detectadas.

> [!NOTE]
> O fornecedor da Defesa Contra Ameaças Móveis não é compatível com dispositivos não registrados.

## <a name="how-do-intune-and-pradeo-help-protect-your-company-resources"></a>Como o Intune e o Pradeo ajudam a proteger os recursos de sua empresa?

O aplicativo Pradeo para Android e iOS/iPadOS captura o sistema de arquivos, a pilha de rede e, quando disponível, a telemetria dos dispositivos e dos aplicativos, e envia os dados telemétricos ao serviço de nuvem do Pradeo para avaliar o risco do dispositivo de ameaças móveis.

A política de conformidade do dispositivo do Intune inclui uma regra para a Defesa contra Ameaças Móveis do Pradeo, que se baseia na avaliação de risco do Pradeo. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada. Se o dispositivo for considerado não compatível, o acesso dos usuários aos recursos corporativos como o Exchange Online e o SharePoint Online será bloqueado. Os usuários também recebem diretrizes do aplicativo Pradeo instalado nos dispositivos para resolver o problema e recuperar o acesso aos recursos corporativos.

## <a name="sample-scenarios"></a>Exemplo de cenários

Confira alguns cenários comuns.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Controlar o acesso com base em ameaças de aplicativos mal-intencionados

Quando aplicativos mal-intencionados, como malware, são detectados nos dispositivos, é possível impedir as seguintes ações dos dispositivos até que a ameaça seja resolvida:

- Conectar-se ao email corporativo

- Sincronizar arquivos corporativos com o aplicativo OneDrive for Work

- Acessar aplicativos da empresa

**Bloquear quando aplicativos mal-intencionados forem detectados:**

![Imagem conceitual de aplicativos mal-intencionados detectados](./media/pradeo-mobile-threat-defense-connector/pradeo_maliciousapps_blocked.png)

**Concessão do acesso após a correção:**

![Acesso concedido a aplicativos mal-intencionados detectado](./media/pradeo-mobile-threat-defense-connector/pradeo_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede

Detecta ameaças à rede, como ataques **Man-in-the-middle** e protege o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloquear o acesso à rede por meio de Wi-Fi:**

![Bloquear o acesso à rede por meio de Wi-Fi](./media/pradeo-mobile-threat-defense-connector/pradeo_network_wifi_blocked.png)

**Concessão do acesso após a correção:**

![Imagem conceitual de Acesso concedido após a correção](./media/pradeo-mobile-threat-defense-connector/pradeo_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede

Detecta ameaças à rede, como ataques **Man-in-the-middle** e impede a sincronização de arquivos corporativos com base no risco do dispositivo.

**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**

![Bloquear o SharePoint Online quando ameaças à rede forem detectadas](./media/pradeo-mobile-threat-defense-connector/pradeo_network_spo_blocked.png)

**Concessão do acesso após a correção:**

![Imagem conceitual de Acesso concedido após a correção para exemplo do Sharepoint](./media/pradeo-mobile-threat-defense-connector/pradeo_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Plataformas com Suporte

- **Android 4.0.3 e posterior**

- **iOS 7 e posterior**

## <a name="prerequisites"></a>Pré-requisitos

- Azure Active Directory Premium

- Assinatura do Microsoft Intune

- Assinatura da Segurança do Pradeo para Defesa contra Ameaças Móveis

  - Para obter mais informações, confira o [site do Pradeo](https://www.pradeo.com/en-US/mobile-threat-protection).

## <a name="next-steps"></a>Próximas etapas

- [Integrar o Pradeo ao Intune](pradeo-mtd-connector-integration.md)

- [Configurar aplicativos do Pradeo](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Criar uma política de conformidade do dispositivo do Pradeo](mtd-device-compliance-policy-create.md)

- [Habilitar o conector MTD do Pradeo](mtd-connector-enable.md)
