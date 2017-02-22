---
title: "Configurações personalizadas do Intune para dispositivos macOS | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba as configurações que você pode usar em um perfil personalizado do macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: 113572430f0ef82c9a6fa533e3d6fc17b86119cb


---

# <a name="custom-settings-for-macos-devices-in-intune-azure-preview"></a>Configurações personalizadas para dispositivos macOS na versão prévia do Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use o perfil personalizado do macOS do Microsoft Intune para implantar configurações que você criou usando a [ferramenta Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) em dispositivos macOS. Essa ferramenta permite que você crie várias configurações que controlam a operação desses dispositivos e as exporte para um perfil de configuração. Você poderá, então, importar este perfil de configuração para um perfil personalizado do macOS do Intune e atribuir as configurações aos usuários e dispositivos em sua organização.

Essa funcionalidade permite implantar configurações do macOS que não são configuráveis com outros tipos de perfil do Intune.


1. Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](how-to-configure-custom-settings.md) para começar.
2. Na folha **Criar Perfil**, especifique o seguinte:

- **Nome do perfil de configuração personalizado** – Forneça um nome para a política que será exibida no dispositivo e no status do Intune.
- **Arquivo de perfil de configuração** – Navegue até o perfil de configuração criado usando o Apple Configurator.
Verifique se as configurações exportadas da ferramenta Apple Configurator são compatíveis com a versão do macOS nos dispositivos para os quais você implantará a política personalizada do macOS. Para obter informações sobre como as incompatibilidades de configuração são resolvidas, pesquise a **Referência de Perfil de Configuração** e a **Referência de Protocolo de Gerenciamento de Dispositivo Móvel** no site do [Desenvolvedor Apple](https://developer.apple.com/).

O arquivo importado será exibido na área da folha **Conteúdo do arquivo**.



<!--HONumber=Feb17_HO1-->


