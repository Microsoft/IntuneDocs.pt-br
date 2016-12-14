---
title: "Restringir o acesso usando a proteção contra ameaças a dispositivos | Microsoft Intune"
description: Restringir o acesso a recursos da empresa com base em riscos de dispositivo, rede e aplicativo.
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: d529bd1c2a281c06f70593e73b71d09962a3c714


---

# <a name="restrict-access-to-company-resource-based-on-device-network-and-application-risk"></a>Restringir o acesso a recursos da empresa com base em riscos de dispositivo, rede e aplicativo
Você pode controlar o acesso de dispositivos móveis a recursos corporativos, com base na avaliação de risco conduzida pelo Lookout, uma solução de proteção contra ameaças de dispositivos integrada ao Microsoft Intune. O risco se baseia na telemetria que o serviço do Lookout coleta de dispositivos com relação a vulnerabilidades do sistema operacional, aplicativos mal-intencionados instalados e perfis de rede mal-intencionados. Com base na avaliação de risco do Lookout habilitada por meio das políticas de conformidade do Intune, você pode configurar políticas de acesso condicional no Intune e permitir ou bloquear dispositivos que foram considerados incompatíveis devido a ameaças detectadas neles.  

## <a name="what-problem-does-this-solve"></a>Que problema isso resolve?
Empresas e organizações precisam proteger dados confidenciais contra ameaças emergentes que incluem ameaças físicas, baseadas em aplicativos e baseadas em rede, bem como vulnerabilidades do SO.

Historicamente, as empresas e organizações assumem uma posição ativa na proteção de computadores contra ataques mal-intencionados. A área móvel é uma área emergente que geralmente permanece desprotegida. Embora as plataformas móveis tenham proteção interna do SO, usando técnicas como isolamento de aplicativo e lojas de aplicativos de consumidor verificadas, essas plataformas continuam vulneráveis a ataques sofisticados. Uma vez que são cada vez mais usados por funcionários para trabalhar e precisam ter acesso a informações que podem ser valiosas e confidenciais, os dispositivos móveis precisam ser protegidos contra uma variedade de ataques sofisticados.

O Intune oferece a capacidade de controlar o acesso a recursos e dados da empresa com base na avaliação de risco que as soluções de proteção contra ameaças ao dispositivo, como Lookout, fornecem.

## <a name="how-do-intune-and-lookout-device-threat-protection-help-protect-company-resources"></a>Como a proteção contra ameaças ao dispositivo do Lookout e do Intune ajudam a proteger recursos da empresa?
O aplicativo móvel do Lookout (Lookout for Work), quando executado em dispositivos móveis, coleta telemetria do sistema de arquivos, da pilha de rede, de dispositivos e aplicativos (quando disponível) e a envia para o serviço de nuvem de proteção contra ameaças ao dispositivo para calcular um risco agregado do dispositivo quanto a ameaças móveis. Você também pode alterar a classificação do nível de risco das ameaças no console do Lookout para atender às suas necessidades.  

Agora, a política de conformidade no Intune inclui uma nova regra para a proteção contra ameaças móveis do Lookout com base na avaliação de riscos de ameaças ao dispositivo do Lookout. Quando essa regra for habilitada, o Microsoft Intune avaliará a conformidade do dispositivo com a política que você habilitou.

Se for determinado que o dispositivo não é compatível com a política de conformidade, o acesso a recursos como o Exchange Online e o SharePoint Online pode ser bloqueado usando políticas de acesso condicional. Quando o acesso é bloqueado, os usuários finais recebem um passo a passo para ajudar a resolver o problema e obter acesso aos recursos da empresa. Esse passo a passo é iniciado por meio do aplicativo Lookout for Work.
## <a name="supported-platforms"></a>Plataformas com suporte:
* **Android 4.1 e versões posteriores** e registradas no Microsoft Intune.
* **iOS 8 e versões posteriores** e registradas no Microsoft Intune.
Para obter informações sobre as plataformas e os idiomas que dão suporte ao Lookout, consulte este [artigo](https://personal.support.lookout.com/hc/en-us/articles/114094140253).

## <a name="prerequisites"></a>Pré-requisitos:
* Uma assinatura do Microsoft Intune e o Azure Active Directory.
* Uma assinatura corporativa do Lookout Mobile EndPoint Security.  Para obter mais informações, consulte [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="example-scenarios"></a>Cenários de exemplo
A seguir, temos alguns cenários comuns:
### <a name="control-access-based-on-threat-from-malicious-apps"></a>Controlar o acesso com base em ameaças de aplicativos mal-intencionados:
Quando aplicativos mal-intencionados, como malwares, são detectados no dispositivo, você pode impedir que esses dispositivos:
* Conectem-se ao email corporativo antes de resolver a ameaça.
* Sincronizem arquivos corporativos usando o aplicativo OneDrive for Work.
* Acessem aplicativos críticos para os negócios.

**Acesso bloqueado quando aplicativos mal-intencionados são detectados:**
![diagrama mostrando a política de acesso condicional bloqueando o acesso quando é determinado que o dispositivo é incompatível devido à presença de aplicativos mal-intencionados](../media/mtp/malicious-apps-blocked.png)

**O dispositivo é desbloqueado e pode acessar os recursos da empresa quando a ameaça é corrigida:**

![diagrama mostrando a política de acesso condicional concedendo acesso quando é determinado que o dispositivo é compatível após a correção](../media/mtp/malicious-apps-unblocked.png)
### <a name="control-access-based-on-threat-to-network"></a>Controlar o acesso com base em ameaças à rede:
Detecta ameaças à sua rede, como ataques do tipo man-in-the-middle, e restringe o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloqueio de acesso à rede por WiFi:**
![diagrama mostrando o acesso condicional bloqueando o acesso à rede WiFi com base em ameaças à rede](../media/mtp/network-wifi-blocked.png)

**Acesso concedido após a correção:**

![diagrama mostrando o acesso condicional permitindo o acesso após a correção da ameaça](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Controlar o acesso ao SharePoint Online com base em ameaças à rede:

Detecta ameaças à sua rede, como ataques do tipo man-in-the-middle, e impede a sincronização de arquivos corporativos com base no risco do dispositivo.

**Bloqueio do acesso ao SharePoint Online com base em ameaça à rede detectada no dispositivo:**

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



<!--HONumber=Dec16_HO2-->


