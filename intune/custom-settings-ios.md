---
title: "Configurações personalizadas do Microsoft Intune para dispositivos que executam o iOS"
titleSuffix: Azure portal
description: "Conheça as configurações que podem ser usadas em um perfil personalizado do iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 40e34a2e22c9349cad63d813b892863e0e8a2933
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-ios"></a>Configurações personalizadas de dispositivos do Microsoft Intune para dispositivos que executam o iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use o perfil personalizado do iOS do Microsoft Intune para atribuir configurações que você criou usando a [ferramenta Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) em dispositivos iOS. Essa ferramenta permite que você crie várias configurações que controlam a operação desses dispositivos e as exporte para um perfil de configuração. Você poderá, então, importar este perfil de configuração para um perfil personalizado do iOS do Intune e atribuir as configurações aos usuários e dispositivos em sua organização.

Essa funcionalidade permite atribuir configurações do iOS que não são configuráveis com outros tipos de perfil do Intune.


1. Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.
2. No painel **Perfil de Configuração Personalizada**, defina todas as configurações a seguir:

- **Nome do perfil de configuração personalizada** – Forneça um nome para a política que será exibida no dispositivo e no status do Intune.
- **Arquivo de perfil de configuração** – Navegue até o perfil de configuração criado usando o Apple Configurator.
Certifique-se de que as configurações que você exportar da ferramenta Apple Configurator seja compatível com a versão do iOS nos dispositivos nos quais você atribuir a política personalizada do iOS. Para obter informações sobre como as incompatibilidades de configuração são resolvidas, pesquise a **Referência de Perfil de Configuração** e a **Referência de Protocolo de Gerenciamento de Dispositivo Móvel** no site do [Desenvolvedor Apple](https://developer.apple.com/).

O arquivo importado será exibido na área **Conteúdo do arquivo** do painel.
