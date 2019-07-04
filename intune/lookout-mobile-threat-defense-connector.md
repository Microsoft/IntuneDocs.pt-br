---
title: Conector do MTD do Lookout com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Saiba como integrar o Intune à MTD (Defesa contra Ameaças Móveis) do Lookout para controlar o acesso de dispositivos móveis aos recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3566d144abad563ead64c124e128c221e725a25c
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67045692"
---
# <a name="lookout-mobile-endpoint-security-connector-with-intune"></a>Conector de segurança de ponto de extremidade móvel do Lookout com o Intune

É possível controlar o acesso de dispositivos móveis a recursos corporativos com base na avaliação de risco realizada pelo Lookout, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos pelo serviço Lookout, incluindo:
- Vulnerabilidades do sistema operacional
- Aplicativos mal-intencionados instalados
- Perfis de rede mal-intencionados

É possível configurar políticas de acesso condicional com base na avaliação de risco do Lookout habilitada por meio das políticas de conformidade do Intune. As configurações possibilitam permitir ou bloquear dispositivos fora de conformidade de acordo com as ameaças detectadas.

## <a name="how-do-intune-and-lookout-mobile-endpoint-security-help-protect-company-resources"></a>Como a segurança de ponto de extremidade móvel do Lookout e do Intune ajudam a proteger recursos da empresa?
O aplicativo móvel do Lookout, **Lookout for Work**, é instalado e executado em dispositivos móveis. Esse aplicativo captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível, e envia-os ao serviço de nuvem do Lookout para avaliar o risco do dispositivo a ameaças móveis. É possível alterar as classificações de nível de risco das ameaças no console do Lookout para atender às suas necessidades.  

A política de conformidade no Intune inclui uma regra para a Defesa contra Ameaças Móveis do Lookout de acordo com a avaliação de risco do Lookout. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada.

Se o dispositivo for considerado fora de conformidade, o acesso a recursos como o Exchange Online e o SharePoint Online poderá ser bloqueado. Os usuários nos dispositivos bloqueados recebem etapas para resolver o problema e obter o acesso novamente. As diretrizes são iniciadas por meio do aplicativo Lookout for Work.

## <a name="supported-platforms"></a>Plataformas com Suporte  
Há suporte para as seguintes plataformas no Lookout quando registradas no Intune:
* **Android 4.1 e posterior**  
* **iOS 8 e posterior**  

Para saber mais sobre o suporte a plataformas e idiomas, visite o [site do Lookout](https://personal.support.lookout.com/hc/articles/114094140253).  

## <a name="prerequisites"></a>Pré-requisitos
* Assinatura corporativa do Lookout Mobile Endpoint Security  
* Assinatura do Microsoft Intune
* Azure Active Directory Premium
* Enterprise Mobility and Security (EMS) E3 ou E5, com licenças atribuídas aos usuários.  

Para obter mais informações, consulte [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="sample-scenarios"></a>Cenários de exemplo

Estes são os cenários comuns ao usar a segurança de pontos de extremidade móvel com o Intune.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Controlar o acesso com base em ameaças de aplicativos mal-intencionados
Quando aplicativos mal-intencionados, como malware, são detectados nos dispositivos, é possível impedir que os dispositivos façam o seguinte até que a ameaça seja resolvida:
* Conectar-se ao email corporativo
* Sincronizar arquivos corporativos com o aplicativo OneDrive for Work
* Acessar aplicativos da empresa

**Bloquear quando aplicativos mal-intencionados forem detectados:**

![Imagem conceitual da política bloqueando o acesso devido a aplicativos mal-intencionados](./media/malicious-apps-blocked.png)

**Concessão do acesso após a correção:**

![Imagem conceitual mostrando o acesso sendo concedido aos dispositivos após a correção](./media/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede
Detecta ameaças à sua rede, como ataques “man-in-the-middle” e protege o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloquear o acesso à rede por meio de Wi-Fi:**

![Imagem mostrando o bloqueio do acesso Wi-Fi com base nas ameaças à rede](./media/network-wifi-blocked.png)

**Concessão do acesso após a correção:**

![Imagem conceitual do acesso condicional permitindo o acesso após a correção](./media/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede

Detecta ameaças à sua rede, como ataques do tipo man-in-the-middle, e impede a sincronização de arquivos corporativos com base no risco do dispositivo.

**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**

![Imagem conceitual do bloqueio do acesso ao SharePoint Online](./media/network-spo-blocked.png)


**Concessão do acesso após a correção:**

![Imagem conceitual de permissão do acesso após a correção da ameaça à rede](./media/network-spo-unblocked.png)

## <a name="next-steps"></a>Próximas etapas
Veja as principais etapas que você precisa realizar para implementar esta solução:
1.  [Configurar a integração com o Lookout](lookout-mtd-connector-integration.md)
2.  [Habilitar a segurança de ponto de extremidade móvel no Intune](mtd-connector-enable.md)
3.  [Adicionar e atribuir o aplicativo Lookout for Work](mtd-apps-ios-app-configuration-policy-add-assign.md)
4.  [Configurar política de conformidade de dispositivo do Lookout](mtd-device-compliance-policy-create.md)
