---
title: Usar máquinas virtuais do Windows 10 com o Microsoft Intune
titleSuffix: ''
description: Diretrizes para usar máquinas virtuais do Windows 10 com o Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9afaf2c8a63bfaed1fdb593baf42c8fa258d7893
ms.sourcegitcommit: 1a22b8b31424847d3c86590f00f56c5bc3de2eb5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74263111"
---
# <a name="using-windows-10-virtual-machines-with-intune"></a>Usar máquinas virtuais do Windows 10 com o Intune

O Intune dá suporte ao gerenciamento de máquinas virtuais que executam o Windows 10 Enterprise com determinadas limitações. O gerenciamento do Intune não depende nem interfere no gerenciamento da Área de Trabalho Virtual do Windows em uma mesma máquina virtual.

Ao gerenciar VMs do Windows 10 com o Intune, lembre-se sempre do seguinte:

## <a name="enrollment"></a>Registro
- Não é recomendável o gerenciamento de máquinas virtuais de host de sessão sob demanda com o Intune. Cada VM deve ser registrada quando é criada. Além disso, a exclusão regular de VMs deixará os registros de dispositivos órfãos no Intune até que sejam [limpos](../remote-actions/devices-wipe.md#automatically-delete-devices-with-cleanup-rules). 
- O modo de autoimplantação do Windows Autopilot não recebe suporte porque requer um TPM (Trusted Platform Module). 
- Não há suporte para o registro de OOBE (Experiência imediata) em VMs que só podem ser acessadas usando o RDP (como as VMs hospedadas no Azure). Essa restrição significa que:
    - Não há suporte para o Azure Autopilot e o OOBE comercial.
    - Não há suporte para as opções de Página de status de registro para políticas de contexto de dispositivo.

## <a name="configuration"></a>Configuração
O Intune não oferece suporte a nenhuma configuração que use um gerenciamento de hardware ou de Trusted Platform Module, entre elas:
- [Configurações do BitLocker](../configuration/device-profiles.md#endpoint-protection)
- [Configurações de Interface de Configuração de Firmware do Dispositivo](../configuration/device-profiles.md#device-firmware-configuration-interface)

## <a name="reporting"></a>Relatórios
O Intune detecta automaticamente as máquinas virtuais e as relata como "Máquina virtual" no campo **Dispositivos** > **Todos os Dispositivos** > escolha um dispositivo > **Visão geral** > **Modelo**. 

As máquinas virtuais desalocadas podem contribuir para relatórios de dispositivos não compatíveis porque não conseguem [fazer check-in com o serviço do Intune](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

## <a name="retirement"></a>Desativação
Se você só tiver acesso RDP, não use a [ação Apagar](../remote-actions/devices-wipe.md#wipe). A ação Apagar exclui as configurações de RDP da máquina virtual e impede que você se conecte novamente.


