---
title: "Restringir o acesso usando a proteção contra ameaças ao dispositivo | Microsoft Docs"
description: Restringir o acesso a recursos da empresa com base em riscos de dispositivo, rede e aplicativo.
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6b83d06ecbe6e202bf022444c288e0866b3507c6
ms.openlocfilehash: 1dd2c4a46857aef1ba273904d58d5eacae99c7bc


---

# <a name="restrict-access-to-company-resource-based-on-device-network-and-application-risk"></a>Restringir o acesso a recursos da empresa com base em riscos de dispositivo, rede e aplicativo
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
Detecta ameaças à sua rede, como ataques do tipo man-in-the-middle, e restringe o acesso a redes Wi-Fi com base no risco do dispositivo.

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
1.  [Configurar sua assinatura com a proteção contra ameaças móveis do Lookout](set-up-your-subscription-with-lookout-mtp.md)
2.  [Habilitar a conexão do Lookout MTP no Intune](enable-lookout-mtp-connection-in-intune.md)
3.  [Configurar e implantar o aplicativo Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)
4.  [Configurar a política de conformidade](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [Solucionar problemas de integração do Lookout](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)



<!--HONumber=Dec16_HO4-->


