---
title: "Apagamento de dispositivos móveis gerenciados pelo Exchange"
description: "O Microsoft Intune permite apagar ou redefinir dispositivos móveis que são gerenciados usando o EAS (Exchange ActiveSync) com o Intune Exchange Connector"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 665f57a4cdb25c1e9f2bef7f1c25f284589df16f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="6f83a-103">Wipe for Exchange-managed mobile devices</span><span class="sxs-lookup"><span data-stu-id="6f83a-103">Wipe for Exchange-managed mobile devices</span></span>
<a id="wipe-for-exchange-managed-mobile-devices" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="6f83a-104">O Microsoft Intune permite apagar ou redefinir dispositivos móveis que são gerenciados usando o EAS (Exchange ActiveSync) com o Intune Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="6f83a-104">Microsoft Intune allows you to wipe or reset mobile devices that are managed using Exchange ActiveSync (EAS) with the Intune Exchange Connector.</span></span> <span data-ttu-id="6f83a-105">A tabela a seguir descreve os recursos de apagamento disponíveis por meio do Exchange ActiveSync:</span><span class="sxs-lookup"><span data-stu-id="6f83a-105">The following table describes the wipe capabilities available through Exchange ActiveSync:</span></span>

|<span data-ttu-id="6f83a-106">Tipo de apagamento</span><span class="sxs-lookup"><span data-stu-id="6f83a-106">Type of wipe</span></span>|<span data-ttu-id="6f83a-107">Windows 8.1 e Windows RT 8.1</span><span class="sxs-lookup"><span data-stu-id="6f83a-107">Windows 8.1 and Windows RT 8.1</span></span>|<span data-ttu-id="6f83a-108">iOS</span><span class="sxs-lookup"><span data-stu-id="6f83a-108">iOS</span></span>|<span data-ttu-id="6f83a-109">Android</span><span class="sxs-lookup"><span data-stu-id="6f83a-109">Android</span></span>|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|<span data-ttu-id="6f83a-110">Apagamento completo</span><span class="sxs-lookup"><span data-stu-id="6f83a-110">Full wipe</span></span>|<span data-ttu-id="6f83a-111">Remove a conta de email e os emails armazenados em cache.</span><span class="sxs-lookup"><span data-stu-id="6f83a-111">Removes mail account and cached mail.</span></span>|<span data-ttu-id="6f83a-112">Redefinição XFactory.</span><span class="sxs-lookup"><span data-stu-id="6f83a-112">XFactory reset.</span></span>|<span data-ttu-id="6f83a-113">Redefinição de fábrica.</span><span class="sxs-lookup"><span data-stu-id="6f83a-113">Factory reset.</span></span>|
|<span data-ttu-id="6f83a-114">Apagamento seletivo/email</span><span class="sxs-lookup"><span data-stu-id="6f83a-114">Selective wipe/email</span></span>|<span data-ttu-id="6f83a-115">Remove conta de email.</span><span class="sxs-lookup"><span data-stu-id="6f83a-115">Removes email account.</span></span>|<span data-ttu-id="6f83a-116">Não há suporte.</span><span class="sxs-lookup"><span data-stu-id="6f83a-116">Not supported.</span></span>|<span data-ttu-id="6f83a-117">Não há suporte.</span><span class="sxs-lookup"><span data-stu-id="6f83a-117">Not supported.</span></span>|
|<span data-ttu-id="6f83a-118">Apagamento seletivo/políticas</span><span class="sxs-lookup"><span data-stu-id="6f83a-118">Selective wipe/policies</span></span>|<span data-ttu-id="6f83a-119">Aplicação de políticas é removida, mas as configurações não são alteradas</span><span class="sxs-lookup"><span data-stu-id="6f83a-119">Policy enforcement removed, but settings are not changed</span></span>|<span data-ttu-id="6f83a-120">Aplicação XFactory é removida, mas as configurações não são alteradas.</span><span class="sxs-lookup"><span data-stu-id="6f83a-120">XPolicy enforcement removed, but settings are not changed.</span></span>|<span data-ttu-id="6f83a-121">A aplicação da política é removida, mas as configurações não são alteradas.</span><span class="sxs-lookup"><span data-stu-id="6f83a-121">Policy enforcement removed, but settings are not changed.</span></span>|
