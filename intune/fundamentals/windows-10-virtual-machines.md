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
ms.openlocfilehash: 486ca7eae1b1e8b016f44c735ec04a23145421a8
ms.sourcegitcommit: e1ff157f692983b49bdd6e20cc9d0f93c3b3733c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124972"
---
# <a name="using-windows-10-virtual-machines-with-intune"></a>Usar máquinas virtuais do Windows 10 com o Intune

O Intune dá suporte ao gerenciamento de máquinas virtuais que executam o Windows 10 Enterprise com determinadas limitações. O gerenciamento do Intune não depende nem interfere no gerenciamento da Área de Trabalho Virtual do Windows em uma mesma máquina virtual.

Ao gerenciar VMs do Windows 10 com o Intune, lembre-se sempre do seguinte:

## <a name="enrollment"></a>Registro
- Não é recomendável o gerenciamento de máquinas virtuais de host de sessão sob demanda com o Intune. Cada VM deve ser registrada quando é criada. Além disso, a exclusão regular de VMs deixará os registros de dispositivos órfãos no Intune até que sejam [limpos](../remote-actions/devices-wipe.md#automatically-delete-devices-with-cleanup-rules). 
- Os tipos de implantação de assistência individual e autoimplantação do Windows Autopilot não são compatíveis porque exigem um TPM (Trusted Platform Module). 
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


