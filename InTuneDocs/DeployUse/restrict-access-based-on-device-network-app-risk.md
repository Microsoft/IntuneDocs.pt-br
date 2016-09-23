---
title: "Restringir o acesso usando a proteção contra ameaças móveis | Microsoft Intune"
description: Restringir o acesso a recursos da empresa com base em riscos de dispositivo, rede e aplicativo.
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 61480eb11cc8f4b6b336e48a50c2fe1b5fcd3fac
ms.openlocfilehash: c05dfc8154cd13b74f42b4f63262613be8956d87


---

# Restringir o acesso a recursos da empresa com base em riscos de dispositivo, rede e aplicativo
Você pode controlar o acesso de dispositivos móveis a recursos corporativos, com base na avaliação de risco conduzida pelo Lookout, uma solução de MTO (proteção contra ameaças móveis) que é integrada ao Microsoft Intune. O risco se baseia na telemetria que o serviço da Consulta MTP coleta de dispositivos com relação a vulnerabilidades do SO (sistema operacional), aplicativos mal-intencionados instalados e perfis de rede. Com base na avaliação de risco, você pode configurar políticas de acesso condicional no Intune e permitir ou bloquear dispositivos que foram considerados incompatíveis devido a ameaças detectadas neles.  Atualmente, só já suporte para isso em dispositivos **Android** que executam a versão **4.1 e posteriores** e estão registrados no Microsoft Intune.  
## Que problema isso resolve?
Empresas e organizações precisam proteger dados confidenciais contra ameaças emergentes que incluem ameaças físicas, baseadas em aplicativos e baseadas em rede, bem como vulnerabilidades do SO.

Historicamente, as empresas e organizações assumem uma posição ativa na proteção de computadores contra ataques mal-intencionados. A área móvel é uma área emergente que geralmente permanece desprotegida. Embora as plataformas móveis tenham proteção interna do SO, usando técnicas como isolamento de aplicativo e lojas de aplicativos de consumidor verificadas, essas plataformas continuam vulneráveis a ataques sofisticados. Uma vez que são cada vez mais usados por funcionários para trabalhar e precisam ter acesso a informações que podem ser valiosas e confidenciais, os dispositivos móveis precisam ser protegidos contra uma variedade de ataques sofisticados.

O Intune oferece a capacidade de controlar o acesso a recursos e dados da empresa com base na avaliação de risco que soluções de MTP como o Lookout fornecem.

## Como a proteção contra ameaças móveis do Lookout e o Intune ajudam a proteger recursos da empresa?
O aplicativo móvel do Lookout (Lookout for Work), quando executado em dispositivos móveis, coleta telemetria do sistema de arquivos, da pilha de rede e de dispositivos e aplicativos (quando disponível) e a envia para o serviço de nuvem de MTP (proteção contra ameaças móveis) para calcular um risco agregado do dispositivo quanto a ameaças móveis. Você também pode alterar a classificação do nível de risco das ameaças no console do MTP para atender às suas necessidades.  
Agora, a política de conformidade no Intune inclui uma nova regra para a proteção contra ameaças móveis do Lookout com base na avaliação de riscos da Consulta MTP. Quando essa regra for habilitada, o Microsoft Intune avaliará a conformidade do dispositivo com a política que você habilitou.

Se for determinado que o dispositivo não é compatível com a política de conformidade, o acesso a recursos como o Exchange Online e o SharePoint Online pode ser bloqueado usando políticas de acesso condicional. Quando o acesso é bloqueado, os usuários finais recebem um passo a passo para ajudar a resolver o problema e obter acesso aos recursos da empresa. Esse passo a passo é iniciado por meio do aplicativo Lookout for Work.

## Cenários de exemplo
A seguir, temos alguns cenários comuns:
### Ameaças de aplicativos mal-intencionados:
Quando aplicativos mal-intencionados, como malwares, são detectados no dispositivo, você pode impedir que esses dispositivos:
* conectem-se ao email corporativo antes de resolver a ameaça.
* sincronizem arquivos corporativos usando o aplicativo OneDrive for Work.
* acessem aplicativos críticos para os negócios.

**Acesso bloqueado quando aplicativos mal-intencionados são detectados:**
![ diagrama mostrando a política de acesso condicional bloqueando o acesso quando é determinado que o dispositivo é incompatível devido à presença de aplicativos mal-intencionados](../media/mtp/malicious-apps-blocked.png)

**O dispositivo é desbloqueado e pode acessar os recursos da empresa quando a ameaça é corrigida:**

![diagrama mostrando a política de acesso condicional concedendo acesso quando é determinado que o dispositivo é compatível após a correção](../media/mtp/malicious-apps-unblocked.png)
### Ameaça à rede:
Detecta ameaças à sua rede, como ataques do tipo man-in-the-middle, e restringe o acesso a redes Wi-Fi com base no risco do dispositivo.

**Bloqueio de acesso à rede por Wi-Fi:**
![ diagrama mostrando o acesso condicional bloqueando o acesso à rede Wi-Fi com base em ameaças à rede](../media/mtp/network-wifi-blocked.png)

**Acesso concedido após a correção:**

![diagrama mostrando o acesso condicional permitindo o acesso após a correção da ameaça](../media/mtp/network-wifi-unblocked.png)
### Ameaça à rede (impedindo o acesso ao SharePoint Online):

Detecta ameaças à sua rede, como ataques do tipo man-in-the-middle, e impede a sincronização de arquivos corporativos com base no risco do dispositivo.

**Bloqueio do acesso ao SharePoint Online com base em ameaça à rede detectada no dispositivo:**

![diagrama mostrando o acesso condicional bloqueando o acesso do dispositivo ao SharePoint Online com base na detecção de ameaças](../media/mtp/network-spo-blocked.png)


**Acesso concedido após a correção:**

![diagrama mostrando o acesso condicional permitindo o acesso após a correção da ameaça à rede](../media/mtp/network-spo-unblocked.png)

## Próximas etapas
Veja as principais etapas que você precisa realizar para implementar esta solução:
1.  [Configurar sua assinatura com a proteção contra ameaças móveis do Lookout](set-up-your-subscription-with-lookout-mtp.md)
2.  [Habilitar a conexão do Lookout MTP no Intune](enable-lookout-mtp-connection-in-intune.md)
3.  [Configurar e implantar o aplicativo Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)
4.  [Configurar a política de conformidade](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [Solucionar problemas de integração do Lookout](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration.md)



<!--HONumber=Sep16_HO2-->


