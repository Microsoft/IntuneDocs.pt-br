---
title: Ativar o modo supervisionado do iOS com o Microsoft Intune
titleSuffix: ''
description: Saiba como ativar o modo supervisionado do iOS com o Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8190814-07f0-42d8-9b3a-87c67dd2b7ed
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 99f27992009332a2a5fae0768225d8c69d3ac5ad
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509401"
---
# <a name="turn-on-ios-supervised-mode"></a>Ativar o modo supervisionado do iOS


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O modo supervisionado do Apple iOS fornece aos administradores mais opções ao gerenciar dispositivos Apple, tornando-o útil para dispositivos corporativos implantados em escala. Por exemplo, você pode restringir o AirDrop ou impedir que usuários alterem o nome do dispositivo. Para obter uma lista de configurações que exijam o modo supervisionado, consulte [Configurações de restrição de dispositivo iOS no Intune](../configuration/device-restrictions-ios.md).

O Intune dá suporte ao modo supervisionado como parte do [DEP (Programa de Registro de Dispositivos)](../enrollment/device-enrollment-program-enroll-ios.md) da Apple.

Para obter uma lista de controles da Apple que exigem a supervisão, consulte a [Payload settings reference](http://help.apple.com/configurator/mac/2.4/#/cad5370d089) (Referência de configurações de carga) da Apple.

## <a name="turn-on-supervised-mode-during-enrollment"></a>Ativar o modo supervisionado durante o registro

No Intune, você pode ativar o modo supervisionado para dispositivos ao [criar um perfil de registro da Apple no DEP](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile). Em **Configurações de Gerenciamento de Dispositivo**, marque a caixa **Supervisionado**.

## <a name="turn-on-supervised-mode-after-enrollment"></a>Ativar o modo supervisionado após o registro

Após o registro, a única maneira de habilitar o modo supervisionado é conectando um dispositivo iOS a um Mac e [usando o Apple Configurator](../enrollment/apple-configurator-enroll-ios.md) (que reiniciará o dispositivo). Você não pode configurar um dispositivo para o Modo supervisionado no Intune após o registro.

## <a name="identify-a-supervised-device"></a>Identificar um dispositivo supervisionado

Para determinar se um dispositivo é supervisionado, verifique a tela de bloqueio ou a página **Sobre**:
- Na tela de bloqueio do dispositivo, estará indicado **Este iPhone é gerenciado pela “Nome da Empresa”.**
- Na página **Sobre** do dispositivo, estará indicado **Este iPhone é supervisionado. A “Nome da empresa” pode monitorar o tráfego de Internet e localizar este dispositivo.**

## <a name="next-steps"></a>Próximas etapas

Para obter detalhes, consulte [O que é o gerenciamento de dispositivo do Microsoft Intune?](device-management.md)
