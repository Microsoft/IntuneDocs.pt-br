---
title: Conector do MTD do Lookout com o Microsoft Intune
titlesuffix: 
description: "Saiba como integrar o Intune à MTD (Defesa contra Ameaças Móveis) do Lookout para controlar o acesso de dispositivos móveis aos recursos corporativos."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 31369b0bc3c9798f2322233e9d9a7907444c2274
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="lookout-mobile-threat-defense-connector-with-intune"></a>Conector de Defesa Contra Ameaças Móveis do Lookout com o Intune

É possível controlar o acesso de dispositivos móveis a recursos corporativos com base na avaliação de risco realizada pelo Lookout, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos pelo serviço Lookout, incluindo:
- Vulnerabilidades do sistema operacional
- Aplicativos mal-intencionados instalados
- Perfis de rede mal-intencionados

É possível configurar políticas de acesso condicional com base na avaliação de risco do Lookout habilitada por meio das políticas de conformidade do Intune. As configurações possibilitam permitir ou bloquear dispositivos fora de conformidade de acordo com as ameaças detectadas.

## <a name="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources"></a>Como a Defesa contra Ameaças Móveis do Lookout e do Intune ajudam a proteger recursos da empresa?
O aplicativo móvel do Lookout, **Lookout for Work**, é instalado e executado em dispositivos móveis. Esse aplicativo captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível, e envia-os ao serviço de nuvem do Lookout para avaliar o risco do dispositivo a ameaças móveis. É possível alterar as classificações de nível de risco das ameaças no console do Lookout para atender às suas necessidades.  

A política de conformidade no Intune inclui uma regra para a Defesa contra Ameaças Móveis do Lookout de acordo com a avaliação de risco do Lookout. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada.

Se o dispositivo for considerado fora de conformidade, o acesso a recursos como o Exchange Online e o SharePoint Online poderá ser bloqueado. Os usuários nos dispositivos bloqueados recebem etapas para resolver o problema e obter o acesso novamente. As diretrizes são iniciadas por meio do aplicativo Lookout for Work.

## <a name="supported-platforms"></a>Plataformas com Suporte
Há suporte para as seguintes plataformas no Lookout quando registradas no Intune:
* **Android 4.1 e posterior**
* **iOS 8 e posterior** Para obter mais informações sobre o suporte a plataformas e idiomas, visite o [site do Lookout](https://personal.support.lookout.com/hc/articles/114094140253).

## <a name="prerequisites"></a>Pré-requisitos
* Assinatura do Microsoft Intune
* Active Directory do Azure
* Assinatura corporativa do Lookout Mobile Endpoint Security  

Para obter mais informações, consulte [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="sample-scenarios"></a>Cenários de exemplo

Estes são os cenários comuns ao usar a Defesa contra Ameaças Móveis do Lookout com o Intune.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Controlar o acesso com base em ameaças de aplicativos mal-intencionados
Quando aplicativos mal-intencionados, como malware, são detectados nos dispositivos, é possível impedir que os dispositivos façam o seguinte até que a ameaça seja resolvida:
* Conectar-se ao email corporativo
* Sincronizar arquivos corporativos com o aplicativo OneDrive for Work
* Acessar aplicativos da empresa

**Bloquear quando aplicativos mal-intencionados forem detectados:**

![diagrama que mostra a política de acesso condicional bloqueando o acesso quando for determinado que o dispositivo não está compatível, devido a aplicativos mal-intencionados no dispositivo](./media/malicious-apps-blocked.png)

**Concessão do acesso após a correção:**

![diagrama mostrando a política de acesso condicional concedendo acesso quando é determinado que o dispositivo é compatível após a correção](./media/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede
Detecta ameaças à sua rede, como ataques “man-in-the-middle” e protege o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloquear o acesso à rede por meio de Wi-Fi:**

![Diagrama que mostra o acesso condicional bloqueando o acesso a WiFi com base em ameaças à rede](./media/network-wifi-blocked.png)

**Concessão do acesso após a correção:**

![diagrama mostrando o acesso condicional permitindo o acesso após a correção da ameaça](./media/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede

Detecta ameaças à sua rede, como ataques do tipo man-in-the-middle, e impede a sincronização de arquivos corporativos com base no risco do dispositivo.

**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**

![Diagrama mostrando o acesso condicional bloqueando o acesso do dispositivo ao SharePoint Online com base na detecção de ameaças](./media/network-spo-blocked.png)


**Concessão do acesso após a correção:**

![Diagrama que mostra o acesso condicional permitindo o acesso após a correção da ameaça à rede](./media/network-spo-unblocked.png)

## <a name="next-steps"></a>Próximas etapas
Veja as principais etapas que você precisa realizar para implementar esta solução:
1.  [Configurar a integração com o Lookout](lookout-mtd-connector-integration.md)
2.  [Habilitar a Defesa contra Ameaças Móveis do Lookout no Intune](mtd-connector-enable.md)
3.  [Adicionar e atribuir o aplicativo Lookout for Work](mtd-apps-ios-app-configuration-policy-add-assign.md)
4.  [Configurar política de conformidade de dispositivo do Lookout](mtd-device-compliance-policy-create.md)
