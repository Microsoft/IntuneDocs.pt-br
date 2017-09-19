---
title: "Configurações personalizadas do Intune para dispositivos iOS"
titleSuffix: Azure portal
description: "Conheça as configurações que você pode usar em um perfil personalizado do iOS."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6da8caa8-65c2-4f47-842f-9570dcb1ac22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6ef1d45946b22a2e41e1b6ea758a7cb1a472fefd
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
---
# <a name="microsoft-intune-custom-settings-for-ios-devices"></a>Configurações personalizadas do Microsoft Intune para dispositivos iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use o perfil personalizado do iOS do Microsoft Intune para atribuir configurações que você criou usando a [ferramenta Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) em dispositivos iOS. Essa ferramenta permite que você crie várias configurações que controlam a operação desses dispositivos e as exporte para um perfil de configuração. Você poderá, então, importar este perfil de configuração para um perfil personalizado do iOS do Intune e atribuir as configurações aos usuários e dispositivos em sua organização.

Essa funcionalidade permite atribuir configurações do iOS que não são configuráveis com outros tipos de perfil do Intune.


1. Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.
2. Na folha **Criar Perfil**, especifique o seguinte:

- **Nome do perfil de configuração personalizado** – Forneça um nome para a política que será exibida no dispositivo e no status do Intune.
- **Arquivo de perfil de configuração** – Navegue até o perfil de configuração criado usando o Apple Configurator.
Certifique-se de que as configurações que você exportar da ferramenta Apple Configurator seja compatível com a versão do iOS nos dispositivos nos quais você atribuir a política personalizada do iOS. Para obter informações sobre como as incompatibilidades de configuração são resolvidas, pesquise a **Referência de Perfil de Configuração** e a **Referência de Protocolo de Gerenciamento de Dispositivo Móvel** no site do [Desenvolvedor Apple](https://developer.apple.com/).

O arquivo importado será exibido na área da folha **Conteúdo do arquivo**.
