---
title: Usar o Sophos Mobile com o Intune
titleSuffix: Intune on Azure
description: Como usar a solução Sophos Mobile com o Microsoft Intune para controlar o acesso a dispositivo móvel para seus recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: e8823aa8467ef380223a486874c68d52926db733
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72503748"
---
# <a name="sophos-mobile-threat-defense-connector-with-intune"></a>Conector de Defesa contra Ameaças do Sophos Mobile com o Intune
Você pode controlar o acesso de dispositivos móveis aos recursos corporativos usando o Acesso Condicional com base na avaliação de risco realizada pelo Sophos Mobile, uma solução de MTD (Defesa contra Ameaças Móveis) integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos que executam o aplicativo Sophos Mobile.
Você pode configurar políticas de Acesso Condicional com base na avaliação de risco do Sophos Mobile, habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos incompatíveis a recursos corporativos, com base nas ameaças detectadas.

## <a name="how-do-intune-and-sophos-mobile-help-protect-your-company-resources"></a>Como o Intune e o Sophos Mobile ajudam a proteger os recursos da empresa?
O aplicativo Sophos Mobile para Android e iOS captura o sistema de arquivos, a pilha de rede e, quando disponível, a telemetria dos dispositivos e dos aplicativos para enviar os dados telemétricos ao serviço de nuvem do Sophos Mobile e avaliar o risco de ameaças móveis ao dispositivo.
A política de conformidade do dispositivo do Intune inclui uma regra para a Defesa contra Ameaças Móveis do Sophos, que se baseia na avaliação de risco do Sophos Mobile. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada. Se o dispositivo for considerado não compatível, o acesso dos usuários aos recursos corporativos como o Exchange Online e o SharePoint Online será bloqueado. Os usuários também recebem diretrizes do aplicativo Sophos Mobile instalado nos dispositivos para resolver o problema e recuperar o acesso aos recursos corporativos.  

## <a name="sample-scenarios"></a>Cenários de exemplo
Confira alguns cenários comuns.  
### <a name="control-access-based-on-threats-from-malicious-apps"></a>Controlar o acesso com base em ameaças de aplicativos mal-intencionados
Quando aplicativos mal-intencionados, como malware, são detectados nos dispositivos, é possível impedir as seguintes ações dos dispositivos até que a ameaça seja resolvida:
- Conectar-se ao email corporativo
- Sincronizar arquivos corporativos com o aplicativo OneDrive for Work
- Acessar aplicativos da empresa

**Bloquear quando aplicativos mal-intencionados forem detectados**:
 
![Imagem conceitual de aplicativos mal-intencionados detectados](./media/sophos-mtd-connector/sophos_malicious_apps_blocked.png)  

**Acesso concedido após a correção**:  
![Imagem conceitual do acesso concedido após a correção](./media/sophos-mtd-connector/sophos_malicious_apps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede  
Detecta ameaças à rede (assim como ataques Man-in-the-middle) e protege o acesso a redes Wi-Fi com base no risco do dispositivo.  

**Bloqueie o acesso à rede por meio de Wi-Fi**:  
![Bloquear o acesso à rede por meio de Wi-Fi](./media/sophos-mtd-connector/sophos_network_wifi_blocked.png)

**Acesso concedido após a correção**:   
![Acesso concedido após a correção](./media/sophos-mtd-connector/sophos_network_wifi_unblocked.png)  

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede  
Detecta ameaças à rede (assim como ataques Man-in-the-middle) e impede a sincronização de arquivos corporativos com base no risco do dispositivo.  

**Bloqueie o SharePoint Online quando ameaças à rede forem detectadas**:   
![Bloquear o SharePoint Online quando ameaças à rede forem detectadas](./media/sophos-mtd-connector/sophos_network_spo_blocked.png)  

**Acesso concedido após a correção**:  
![Acesso concedido após correção para exemplo do Sharepoint](./media/sophos-mtd-connector/sophos_network_spo_unblocked.png)  

## <a name="supported-platforms"></a>Plataformas com Suporte  
- Android 5.0 e posterior
- iOS 11.0 e posterior

## <a name="prerequisites"></a>Pré-requisitos  
- Azure Active Directory Premium
- Assinatura do Microsoft Intune 
- Assinatura da Defesa contra Ameaças do Sophos Mobile

Para obter mais informações, confira o [site do Sophos](https://www.sophos.com/products/mobile-control).  

## <a name="next-steps"></a>Próximas etapas  
- [Integrar o Sophos com o Intune](sophos-mtd-connector-integration.md)
- [Configurar aplicativos do Sophos](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Criar uma política de conformidade do dispositivo do Sophos](mtd-device-compliance-policy-create.md)
- [Habilitar o conector MTD do Sophos](mtd-connector-enable.md)
