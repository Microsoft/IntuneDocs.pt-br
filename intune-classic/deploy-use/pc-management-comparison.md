---
title: "Comparar as opções de gerenciamento de computadores Windows"
description: Registro de dispositivos iOS corporativos usando o DEP (Programa de Registro de Dispositivo) da Apple ou o Apple Configurator
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 560ce922fa58e759157358c6b7348fe0388ce408
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Comparar o gerenciamento de computadores Windows como computadores ou dispositivos móveis
<a id="compare-managing-windows-pcs-as-computers-or-mobile-devices" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As organizações podem usar o Microsoft Intune para gerenciar computadores Windows como dispositivos móveis com o MDM (gerenciamento de dispositivo móvel) ou como computadores com o cliente de software do Intune.  A Microsoft recomenda que os clientes usem a solução de gerenciamento MDM sempre que possível. No entanto, para ajudá-lo a compreender melhor as diferenças entre essas opções, o gráfico a seguir compara as duas opções de gerenciamento.

|**Funcionalidade/Cenário** |**Windows como Computador**<br>Cliente de software do Intune | **Windows como dispositivos móveis**<br>MDM |
|--------------|-------------------------------|-------------------------------|
|**Sistemas operacionais** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Suporte do Portal do Intune** |[Console do Silverlight](https://manage.microsoft.com)|[Portal do Azure](https://portal.azure.com) |
|**Acesso condicional**|Não disponível|Disponível <br>[O que é o acesso condicional?](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access)|
|**Registro em massa**|Não disponível|Disponível <br>[Registro em massa para dispositivos Windows](https://docs.microsoft.com/intune-azure/enroll-devices/bulk-enroll-windows)|
|**Perfis de dispositivo**|Não disponível|Disponível <br>[O que são perfis de dispositivo do Microsoft Intune?](https://docs.microsoft.com/intune-azure/configure-devices/what-are-device-profiles)|
|**Registro sem agente**|Não disponível |Disponível<br>[Registrar dispositivos Windows](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-windows-devices)|
|**Gerenciamento de atualizações de software**| Windows Updates e atualizações de aplicativos da Microsoft<br>[Manter Computadores Windows atualizados com as atualizações de software](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)|Microsoft Store para Empresas para atualizações do Windows 10 e de aplicativos da Microsoft<br> [Definir as configurações do Windows Update for Business](https://docs.microsoft.com/intune-azure/configure-devices/how-to-configure-windows-update-for-business) |
|**Gerenciamento de licenças de software**|Disponível <br>[Gerenciar contratos de licença para software de computadores Windows](https://docs.microsoft.com/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)|Microsoft Store para Empresas (somente aplicativos .appx)<br>[Gerenciar aplicativos comprados na Windows Store para Empresas](https://docs.microsoft.com/intune-azure/manage-apps/wsfb-apps)|
|**Inventário**|Disponível <br>[Exibir o inventário de software e hardware de computadores Windows](https://docs.microsoft.com/intune/deploy-use/view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune)|Disponível <br>[Como monitorar as informações do aplicativo](https://docs.microsoft.com/intune/apps-monitor)<br>[O que é o gerenciamento de dispositivo](https://docs.microsoft.com/intune/device-management)|
|**Política de Firewall do Windows**|Disponível <br>[Ajude a proteger Computadores Windows usando políticas de Firewall do Windows](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune) |Não disponível|
|**Proteção antimalware**|Endpoint Protection<br>[Ajudar a proteger computadores Windows com o Endpoint Protection](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)|Windows Defender<br>[Configurações do Windows Defender](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-windows-10#windows-defender-settings)|
|**Assistência remota** |TeamViewer<br>[Solicitar e fornecer assistência remota para computadores Windows](https://docs.microsoft.com/intune/deploy-use/request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune)|Não disponível |
|**Implantação de aplicativo** | Não disponível para a Microsoft Store para Empresas,<br>somente .exe, .appx e .msi de vários arquivos<br>[Adicionar aplicativos a computadores Windows que executam o cliente de software do Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)|Disponível para aplicativos da Microsoft Store e aplicativos de linha de negócios<br>[Como adicionar aplicativos da Windows Store](https://docs.microsoft.com/intune-azure/manage-apps/windows-store-app)<br>Implantação de aplicativos da Microsoft e aplicativos Win32 em breve |
|**Proteção de aplicativo**|Não disponível|Disponível <br>[O que são políticas de proteção do aplicativo?](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-protection-policy)|


### Vantagens do gerenciamento MDM de computadores Windows
<a id="advantages-of-mdm-windows-pc-management" class="xliff"></a>
O gerenciamento de computadores Windows com o moderno gerenciamento de dispositivo móvel apresenta as seguintes vantagens:
- **Escalabilidade** – o gerenciamento MDM é dimensionado com gerenciamento de nuvem do Intune. O cliente de software do Intune é limitado a 7.000 computadores.
- **Simplicidade** – usa funcionalidades de gerenciamento modernas incluídas no sistema operacional sem depender do download de um cliente de software
- **Consistência** – os computadores Windows são gerenciados como todos os outros dispositivos móveis em sua organização
<!-- - **Cloud optimization** - -->
