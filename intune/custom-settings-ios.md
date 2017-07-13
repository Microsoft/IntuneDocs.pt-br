---
title: "Configurações personalizadas do Intune para dispositivos iOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações que você pode usar em um perfil personalizado do iOS."
keywords: 
author: robstackmsft
ms.author: robstack
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
ms.openlocfilehash: b169fe74063b618f947f5d3d6809e0e49a5136e3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="856b8-103">Configurações personalizadas do Microsoft Intune para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="856b8-103">Microsoft Intune custom settings for iOS devices</span></span>
<a id="microsoft-intune-custom-settings-for-ios-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="856b8-104">Use o perfil personalizado do iOS do Microsoft Intune para atribuir configurações que você criou usando a [ferramenta Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) em dispositivos iOS.</span><span class="sxs-lookup"><span data-stu-id="856b8-104">Use the Microsoft Intune iOS custom profile to assign settings that you created by using the [Apple Configurator tool](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) to iOS devices.</span></span> <span data-ttu-id="856b8-105">Essa ferramenta permite que você crie várias configurações que controlam a operação desses dispositivos e as exporte para um perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="856b8-105">This tool lets you create many settings that control the operation of these devices and export them to a configuration profile.</span></span> <span data-ttu-id="856b8-106">Você poderá, então, importar este perfil de configuração para um perfil personalizado do iOS do Intune e atribuir as configurações aos usuários e dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="856b8-106">You can then import this configuration profile into an Intune iOS custom profile and assign the settings to users and devices in your organization.</span></span>

<span data-ttu-id="856b8-107">Essa funcionalidade permite atribuir configurações do iOS que não são configuráveis com outros tipos de perfil do Intune.</span><span class="sxs-lookup"><span data-stu-id="856b8-107">This capability allows you to assign iOS settings that are not configurable with other Intune profile types.</span></span>


1. <span data-ttu-id="856b8-108">Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.</span><span class="sxs-lookup"><span data-stu-id="856b8-108">Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="856b8-109">Na folha **Criar Perfil**, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="856b8-109">On the **Create Profile** blade, specify the following:</span></span>

- <span data-ttu-id="856b8-110">**Nome do perfil de configuração personalizado** – Forneça um nome para a política que será exibida no dispositivo e no status do Intune.</span><span class="sxs-lookup"><span data-stu-id="856b8-110">**Custom configuration profile name** - Provide a name for the policy as it will be displayed on the device, and in Intune status.</span></span>
- <span data-ttu-id="856b8-111">**Arquivo de perfil de configuração** – Navegue até o perfil de configuração criado usando o Apple Configurator.</span><span class="sxs-lookup"><span data-stu-id="856b8-111">**Configuration profile file** - Browse to the configuration profile that you created by using the Apple Configurator.</span></span>
<span data-ttu-id="856b8-112">Certifique-se de que as configurações que você exportar da ferramenta Apple Configurator seja compatível com a versão do iOS nos dispositivos nos quais você atribuir a política personalizada do iOS.</span><span class="sxs-lookup"><span data-stu-id="856b8-112">Ensure that the settings you export from the Apple Configurator tool are compatible with the version of iOS on the devices to which you assign the iOS custom policy.</span></span> <span data-ttu-id="856b8-113">Para obter informações sobre como as incompatibilidades de configuração são resolvidas, pesquise a **Referência de Perfil de Configuração** e a **Referência de Protocolo de Gerenciamento de Dispositivo Móvel** no site do [Desenvolvedor Apple](https://developer.apple.com/).</span><span class="sxs-lookup"><span data-stu-id="856b8-113">For information about how incompatible settings are resolved, search for **Configuration Profile Reference** and **Mobile Device Management Protocol Reference** on the [Apple Developer](https://developer.apple.com/) website.</span></span>

<span data-ttu-id="856b8-114">O arquivo importado será exibido na área da folha **Conteúdo do arquivo**.</span><span class="sxs-lookup"><span data-stu-id="856b8-114">The file you imported will be displayed in the **File contents** area of the blade.</span></span>
