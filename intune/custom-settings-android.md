---
title: "Configurações personalizadas do Intune para dispositivos Android"
titleSuffix: Intune on Azure
description: "Conheça as configurações que você pode usar em um perfil personalizado do Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 014e59c017eac0d54a632e545692e1a1a8053164
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="11e4c-103">Configurações personalizadas para dispositivos Android no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="11e4c-103">Custom settings for Android devices in Microsoft Intune</span></span>
<a id="custom-settings-for-android-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="11e4c-104">Use o perfil **Personalizado** do Android do Microsoft Intune para atribuir configurações OMA-URI, que podem ser usadas para controlar recursos em dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="11e4c-104">Use the Microsoft Intune Android **Custom** profile to assign OMA-URI settings that can be used to control features on Android devices.</span></span> <span data-ttu-id="11e4c-105">Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="11e4c-105">These are standard settings that many mobile device manufacturers use to control device features.</span></span>

<span data-ttu-id="11e4c-106">Essa funcionalidade destina-se a permitir que você atribua configurações do Android que não são configuráveis com as políticas do Intune.</span><span class="sxs-lookup"><span data-stu-id="11e4c-106">This capability is intended to allow you to assign Android settings that are not configurable with Intune policies.</span></span>

## <span data-ttu-id="11e4c-107">Configurações de perfil personalizadas para dispositivos Android</span><span class="sxs-lookup"><span data-stu-id="11e4c-107">Custom profile settings for Android devices</span></span>
<a id="custom-profile-settings-for-android-devices" class="xliff"></a>

1. <span data-ttu-id="11e4c-108">Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.</span><span class="sxs-lookup"><span data-stu-id="11e4c-108">Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="11e4c-109">Na folha **Criar Perfil**, escolha **Configurações** para adicionar uma ou mais configurações OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="11e4c-109">On the **Create Profile** blade, choose **Settings** to add one or more OMA-URI settings.</span></span>
3. <span data-ttu-id="11e4c-110">Na folha **Editar Linha**, defina os seguintes valores para cada configuração:</span><span class="sxs-lookup"><span data-stu-id="11e4c-110">On the **Edit Row** blade, configure the following values for each setting:</span></span>
    - <span data-ttu-id="11e4c-111">**Nome** – Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.</span><span class="sxs-lookup"><span data-stu-id="11e4c-111">**Name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.</span></span>
    - <span data-ttu-id="11e4c-112">**Descrição** – Forneça uma descrição que proporciona uma visão geral da configuração e outras informações relevantes que ajudarão a localizá-la.</span><span class="sxs-lookup"><span data-stu-id="11e4c-112">**Description** - Provide a description that gives an overview of the setting and other relevant information to help you locate it.</span></span>
    - <span data-ttu-id="11e4c-113">**Tipo de dados** – Selecione o tipo de dados em que você especificará essa configuração de OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="11e4c-113">**Data type** - Select the data type in which you will specify this OMA-URI setting.</span></span> <span data-ttu-id="11e4c-114">Escolha dentre **Cadeia de caracteres**, **Cadeia de caracteres (XML)**, **Data e hora**, **Inteiro**, **Ponto flutuante** ou **Booliano**.</span><span class="sxs-lookup"><span data-stu-id="11e4c-114">Choose from **String**, **String (XML)**, **Date and time**, **Integer**, **Floating point**, or **Boolean**.</span></span>
    - <span data-ttu-id="11e4c-115">**OMA-URI** – Especifique o OMA-URI para o qual você deseja fornecer uma configuração.</span><span class="sxs-lookup"><span data-stu-id="11e4c-115">**OMA-URI** - Specify the OMA-URI you want to supply a setting for.</span></span>
    - <span data-ttu-id="11e4c-116">**Valor** – Especifique o valor que você deseja associar ao OMA-URI inserido.</span><span class="sxs-lookup"><span data-stu-id="11e4c-116">**Value** - Enter the value you want to associate with the OMA-URI you entered.</span></span>
4. <span data-ttu-id="11e4c-117">Clique em **OK** quando terminar e continue a adicionar mais configurações conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="11e4c-117">Click **OK** once you are done, then continue to add more settings as required.</span></span>
