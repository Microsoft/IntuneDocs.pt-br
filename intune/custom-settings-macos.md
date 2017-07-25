---
title: "Configurações personalizadas do Intune para dispositivos macOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações que você pode usar em um perfil personalizado do macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 57c4ec3621ffaef5c1aaffd55c87baac91e50154
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="9ea5b-103">Configurações personalizadas para dispositivos macOS no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9ea5b-103">Custom settings for macOS devices in Microsoft Intune</span></span>
<a id="custom-settings-for-macos-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="9ea5b-104">Use o perfil personalizado do macOS do Microsoft Intune para atribuir configurações que você criou usando a [ferramenta Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) em dispositivos macOS.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-104">Use the Microsoft Intune macOS custom profile to assign settings that you created by using the [Apple Configurator tool](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) to macOS devices.</span></span> <span data-ttu-id="9ea5b-105">Essa ferramenta permite que você crie várias configurações que controlam a operação desses dispositivos e as exporte para um perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-105">This tool lets you create many settings that control the operation of these devices and export them to a configuration profile.</span></span> <span data-ttu-id="9ea5b-106">Você poderá, então, importar este perfil de configuração para um perfil personalizado do macOS do Intune e atribuir as configurações aos usuários e dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-106">You can then import this configuration profile into an Intune macOS custom profile and assign the settings to users and devices in your organization.</span></span>

<span data-ttu-id="9ea5b-107">Essa funcionalidade permite atribuir configurações do macOS que não são configuráveis com outros tipos de perfil do Intune.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-107">This capability allows you to assign macOS settings that are not configurable with other Intune profile types.</span></span>


1. <span data-ttu-id="9ea5b-108">Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-108">Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="9ea5b-109">Na folha **Criar Perfil**, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9ea5b-109">On the **Create Profile** blade, specify the following:</span></span>

- <span data-ttu-id="9ea5b-110">**Nome do perfil de configuração personalizado** – Forneça um nome para a política que será exibida no dispositivo e no status do Intune.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-110">**Custom configuration profile name** - Provide a name for the policy as it will be displayed on the device, and in Intune status.</span></span>
- <span data-ttu-id="9ea5b-111">**Arquivo de perfil de configuração** – Navegue até o perfil de configuração criado usando o Apple Configurator.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-111">**Configuration profile file** - Browse to the configuration profile that you created by using the Apple Configurator.</span></span>
<span data-ttu-id="9ea5b-112">Verifique se as configurações exportadas da ferramenta Apple Configurator são compatíveis com a versão do macOS nos dispositivos para os quais você atribuirá a política personalizada do macOS.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-112">Ensure that the settings you export from the Apple Configurator tool are compatible with the version of macOS on the devices to which you assign the macOS custom policy.</span></span> <span data-ttu-id="9ea5b-113">Para obter informações sobre como as incompatibilidades de configuração são resolvidas, pesquise a **Referência de Perfil de Configuração** e a **Referência de Protocolo de Gerenciamento de Dispositivo Móvel** no site do [Desenvolvedor Apple](https://developer.apple.com/).</span><span class="sxs-lookup"><span data-stu-id="9ea5b-113">For information about how incompatible settings are resolved, search for **Configuration Profile Reference** and **Mobile Device Management Protocol Reference** on the [Apple Developer](https://developer.apple.com/) website.</span></span>

<span data-ttu-id="9ea5b-114">O arquivo importado será exibido na área da folha **Conteúdo do arquivo**.</span><span class="sxs-lookup"><span data-stu-id="9ea5b-114">The file you imported will be displayed in the **File contents** area of the blade.</span></span>
