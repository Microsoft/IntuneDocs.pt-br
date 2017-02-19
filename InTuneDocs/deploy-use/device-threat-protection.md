---
title: "Proteger o acesso usando a proteção contra ameaças ao dispositivo | Microsoft Docs"
description: Proteja o acesso a recursos da empresa com base em riscos de dispositivo, rede e aplicativo.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 931f222898a224c2f646ad203f12676c39b78946
ms.openlocfilehash: aaa0965c2bd4d4093da0c57eaa2e3bd05eb6779a


---

# <a name="protect-access-to-company-resource-based-on-device-network-and-application-risk"></a>Proteger o acesso a recursos da empresa com base em riscos de dispositivo, rede e aplicativo

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

É possível controlar o acesso de dispositivos móveis a recursos corporativos com base na avaliação de risco realizada pelo Lookout, uma solução de proteção contra ameaças ao dispositivo integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos pelo serviço Lookout, incluindo:
- Vulnerabilidades do sistema operacional
- Aplicativos mal-intencionados instalados
- Perfis de rede mal-intencionados

É possível configurar políticas de acesso condicional com base na avaliação de risco do Lookout habilitada por meio das políticas de conformidade do Intune. As configurações possibilitam permitir ou bloquear dispositivos fora de conformidade de acordo com as ameaças detectadas.  

## <a name="what-problem-does-this-solve"></a>Que problema isso resolve?
As empresas precisam proteger dados confidenciais contra ameaças emergentes, incluindo ameaças físicas, baseadas em aplicativo e em rede, bem como vulnerabilidades do sistema operacional.

Historicamente, as empresas têm sido proativas ao proteger computadores contra ataques, enquanto os dispositivos móveis ficam sem monitoramento e proteção. Plataformas móveis têm proteção interna, como isolamento de aplicativo e lojas de aplicativos de consumidor verificadas, mas permanecerão vulneráveis a ataques sofisticados. Hoje, um número maior de funcionários usa dispositivos para o trabalho e precisam ter acesso a informações confidenciais. Os dispositivos precisam ser protegidos contra ataques cada vez mais sofisticados.

O Intune permite controlar o acesso aos recursos da empresa com base na avaliação de risco fornecida pelas soluções de proteção contra ameaças ao dispositivo, como o Lookout.

## <a name="how-do-intune-and-lookout-device-threat-protection-help-protect-company-resources"></a>Como a proteção contra ameaças ao dispositivo do Lookout e do Intune ajudam a proteger recursos da empresa?
O aplicativo móvel do Lookout, **Lookout for Work**, é instalado e executado em dispositivos móveis. Esse aplicativo captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível, e envia-os ao serviço de nuvem do Lookout para avaliar o risco do dispositivo a ameaças móveis. É possível alterar as classificações de nível de risco das ameaças no console do Lookout para atender às suas necessidades.  

A política de conformidade no Intune inclui uma regra para o Lookout Mobile Threat Protection de acordo com a avaliação de risco do Lookout. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada.

Se o dispositivo for considerado fora de conformidade, o acesso a recursos como o Exchange Online e o SharePoint Online poderá ser bloqueado. Os usuários nos dispositivos bloqueados recebem etapas para resolver o problema e obter o acesso novamente. As diretrizes são iniciadas por meio do aplicativo Lookout for Work.

## <a name="supported-platforms"></a>Plataformas com suporte:
Há suporte para as seguintes plataformas no Lookout quando registradas no Intune:
* **Android 4.1 e posterior**
* **iOS 8 e posterior** Para obter mais informações sobre o suporte a plataformas e idiomas, visite o [site do Lookout](https://personal.support.lookout.com/hc/en-us/articles/114094140253).

## <a name="prerequisites"></a>Pré-requisitos:
* Assinatura do Microsoft Intune
* Active Directory do Azure
* Assinatura corporativa do Lookout Mobile Endpoint Security  

Para obter mais informações, consulte [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="sample-scenarios"></a>Cenários de exemplo
A seguir, temos alguns cenários comuns:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Controlar o acesso com base em ameaças de aplicativos mal-intencionados
Quando aplicativos mal-intencionados, como malware, são detectados nos dispositivos, é possível impedir que os dispositivos façam o seguinte até que a ameaça seja resolvida:
* Conectar-se ao email corporativo
* Sincronizar arquivos corporativos com o aplicativo OneDrive for Work
* Acessar aplicativos da empresa

**Bloquear quando aplicativos mal-intencionados forem detectados:**
![diagrama que mostra a política de acesso condicional bloqueando o acesso quando for determinado que o dispositivo não está em conformidade devido à presença de aplicativos mal-intencionados no dispositivo](../media/mtp/malicious-apps-blocked.png)

**Acesso concedido após a correção:**

![diagrama mostrando a política de acesso condicional concedendo acesso quando é determinado que o dispositivo é compatível após a correção](../media/mtp/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede
Detecta ameaças à sua rede, como ataques do tipo man-in-the-middle e protege o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloquear o acesso à rede por meio de WiFi:**
![diagrama que mostra o acesso condicional bloqueando o acesso WiFi com base nas ameaças à rede](../media/mtp/network-wifi-blocked.png)

**Acesso concedido após a correção:**

![diagrama mostrando o acesso condicional permitindo o acesso após a correção da ameaça](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede

Detecta ameaças à sua rede, como ataques do tipo man-in-the-middle, e impede a sincronização de arquivos corporativos com base no risco do dispositivo.

**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**

![Diagrama mostrando o acesso condicional bloqueando o acesso do dispositivo ao SharePoint Online com base na detecção de ameaças](../media/mtp/network-spo-blocked.png)


**Acesso concedido após a correção:**

![Diagrama mostrando o acesso condicional permitindo o acesso após a correção da ameaça à rede](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>Próximas etapas
Veja as principais etapas que você precisa realizar para implementar esta solução:
1.    [Configurar a assinatura da proteção contra ameaças ao dispositivo](device-threat-protection-subscription-setup.md)
2.    [Habilitar a conexão de proteção contra ameaças ao dispositivo no Intune](device-threat-protection-enable.md)
3.  [Configurar e implantar o aplicativo de proteção contra ameaças ao dispositivo](device-threat-protection-apps.md)
4.    [Configurar a política de conformidade da proteção contra ameaças ao dispositivo](device-threat-protection-policy.md)
5.    [Solucionar problemas de integração da proteção contra ameaças ao dispositivo](http://docs.microsoft.com/intune/troubleshoot/device-threat-protection-troubleshooting)



<!--HONumber=Jan17_HO4-->


