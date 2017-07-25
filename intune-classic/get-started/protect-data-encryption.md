---
title: Protegendo dados da empresa com criptografia de dados
description: "Este guia pode ajudar você a proteger sua empresa contra perda de dados forçando uma senha e criptografia de dados usando uma política em aplicativos móveis."
keywords: criptografia, PIN, dados
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b1e84ef8-a260-4e3d-aaf1-8b3facfecafa
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 42ae7cdedbcbd9bf6420ca9fd2cfa39a75174736
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="25c86-104">Guia de início rápido: proteger dados da empresa com criptografia de dados</span><span class="sxs-lookup"><span data-stu-id="25c86-104">Quick Start Guide: Protect company data with data encryption</span></span>
<a id="quick-start-guide-protect-company-data-with-data-encryption" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="25c86-105">O Microsoft Intune pode ajudar você a evitar a perda de dados de aplicativos móveis do Office de diversas maneiras, inclusive:</span><span class="sxs-lookup"><span data-stu-id="25c86-105">Microsoft Intune can help you prevent data loss from Office mobile apps in a variety of ways, including:</span></span>
- <span data-ttu-id="25c86-106">Criptografando dados corporativos com o nível mais alto de criptografia de dispositivo fornecido pelo iOS e pelo Android.</span><span class="sxs-lookup"><span data-stu-id="25c86-106">By encrypting corporate data with the highest level of device encryption provided by iOS and Android.</span></span>
- <span data-ttu-id="25c86-107">Em dispositivos iOS e Android que, devido a requisitos de privacidade ou legais, não podem ser registrados em uma solução de gerenciamento de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="25c86-107">On iOS and Android devices that, because of privacy or legal requirements, cannot be enrolled in a mobile device management solution.</span></span>

<span data-ttu-id="25c86-108">O Microsoft Intune também pode ajudar você a evitar a perda de dados de aplicativos móveis do Office e proteger dados do Office 365 (O365) sem precisar registrar dispositivos móveis iOS ou Android no gerenciamento de dispositivo móvel completo.</span><span class="sxs-lookup"><span data-stu-id="25c86-108">Microsoft Intune can also help you prevent data loss from Office mobile apps and secure Office 365 (O365) data without having to enroll iOS or Android mobile devices in full mobile device management.</span></span> <span data-ttu-id="25c86-109">Isso vale mesmo se você usar uma solução de gerenciamento de dispositivo móvel de terceiros para dispositivos móveis gerenciados.</span><span class="sxs-lookup"><span data-stu-id="25c86-109">This is true even if you use a third-party mobile device management solution to managed mobile devices.</span></span>

## <span data-ttu-id="25c86-110">Este é o guia de início rápido certo para mim?</span><span class="sxs-lookup"><span data-stu-id="25c86-110">Is this quick start guide right for me?</span></span>
<a id="is-this-quick-start-guide-right-for-me" class="xliff"></a>
<span data-ttu-id="25c86-111">Este guia de início rápido é um bom recurso se você atender aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="25c86-111">This quick start guide is a good resource if you meet the following prerequisites:</span></span>
- <span data-ttu-id="25c86-112">Você já usa ou tem licenças do O365 que deseja usar e gerencia seus aplicativos móveis do Office.</span><span class="sxs-lookup"><span data-stu-id="25c86-112">You already use or have O365 licenses that you want to use and you manage Office mobile apps.</span></span>
- <span data-ttu-id="25c86-113">Você planeja usar aplicativos móveis do Office no iOS ou no Android.</span><span class="sxs-lookup"><span data-stu-id="25c86-113">You are planning to use Office mobile apps on iOS or Android.</span></span>
- <span data-ttu-id="25c86-114">Você usa qualquer solução de gerenciamento de dispositivo móvel, sela ela da Microsoft ou não.</span><span class="sxs-lookup"><span data-stu-id="25c86-114">You use any mobile device management solution - Microsoft or non-Microsoft.</span></span> <span data-ttu-id="25c86-115">Se você não puder usar uma solução de gerenciamento de dispositivo móvel devido a regras estatutárias, este guia será algo que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="25c86-115">If you cannot use a mobile device management solution because of statutory rules, this guide is something that you can use.</span></span>

> [!NOTE]
> <span data-ttu-id="25c86-116">O Windows ainda não é uma plataforma com suporte para aplicativos móveis do Office.</span><span class="sxs-lookup"><span data-stu-id="25c86-116">Windows is not yet a supported platform for Office mobile apps.</span></span> <span data-ttu-id="25c86-117">O gerenciamento de aplicativo móvel sem registro ainda não é compatível com o Exchange ou com o SharePoint local.</span><span class="sxs-lookup"><span data-stu-id="25c86-117">Mobile application management without enrollment is not yet compatible with Exchange or SharePoint on-premise.</span></span> <span data-ttu-id="25c86-118">Você só pode proteger dados hospedados em versões online.</span><span class="sxs-lookup"><span data-stu-id="25c86-118">You can only protect data hosted in online versions.</span></span>

<span data-ttu-id="25c86-119">Este guia pode ajudar você a proteger sua empresa contra perda de dados forçando senhas e criptografia de dados usando políticas nos aplicativos móveis que seus funcionários usam para acessar dados confidenciais, sem exigir o registro completo em qualquer solução de gerenciamento de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25c86-119">This guide can help you protect your company from data loss by forcing passcodes and data encryption using policies on the mobile apps that your employees use to access sensitive data, without requiring full enrollment in any device management solution.</span></span> <span data-ttu-id="25c86-120">O Microsoft Intune permite que você defina políticas de MAM (gerenciamento de aplicativo móvel) em aplicativos móveis do Office para [iOS](https://products.office.com/mobile/office-mobile-apps-for-ios) e [Android](https://products.office.com/mobile/office-mobile-apps-for-android).</span><span class="sxs-lookup"><span data-stu-id="25c86-120">Microsoft Intune allows you to set mobile application management (MAM) policies on Office mobile apps for [iOS](https://products.office.com/mobile/office-mobile-apps-for-ios) and [Android](https://products.office.com/mobile/office-mobile-apps-for-android).</span></span> <span data-ttu-id="25c86-121">Esta abordagem protege dados do O365 sem exigir que os usuários registrem seus dispositivos em uma solução de gerenciamento de dispositivo móvel, enquanto mantêm uma excelente experiência do usuário final com aplicativos móveis do Office.</span><span class="sxs-lookup"><span data-stu-id="25c86-121">This approach protects O365 data without requiring users to enroll their devices into a mobile device management solution while also maintaining a great end-user experience with Office mobile apps.</span></span>

## <span data-ttu-id="25c86-122">Como fazer isso?</span><span class="sxs-lookup"><span data-stu-id="25c86-122">How do I do it?</span></span>
<a id="how-do-i-do-it" class="xliff"></a>
1.  [<span data-ttu-id="25c86-123">Examine como você pode proteger dados de aplicativos</span><span class="sxs-lookup"><span data-stu-id="25c86-123">Review how you can protect app data</span></span>](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
2.  [<span data-ttu-id="25c86-124">Prepare-se para configurar políticas de gerenciamento de aplicativos móveis</span><span class="sxs-lookup"><span data-stu-id="25c86-124">Get ready to configure mobile app management policies</span></span>](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)
3.  [<span data-ttu-id="25c86-125">Crie e implante políticas de gerenciamento de aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="25c86-125">Create and deploy mobile app management policies</span></span>](/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

## <span data-ttu-id="25c86-126">Informação adicional:</span><span class="sxs-lookup"><span data-stu-id="25c86-126">Additional information:</span></span>
<a id="additional-information" class="xliff"></a>
- [<span data-ttu-id="25c86-127">Saiba mais sobre a experiência do usuário final de aplicativos habilitados para MAM com o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="25c86-127">Find out about the end user experience for MAM enabled apps with Microsoft Intune.</span></span>](/intune-classic/eploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune)
- [<span data-ttu-id="25c86-128">Decidir como preparar aplicativos para o gerenciamento de aplicativo móvel com o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="25c86-128">Decide how to prepare apps for mobile application management with Microsoft Intune.</span></span>](/intune/apps-prepare-mobile-application-management)
- [<span data-ttu-id="25c86-129">Exiba a lista de parceiros de aplicativos do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="25c86-129">View the list of Microsoft Intune application partners</span></span>](https://www.microsoft.com/cloud-platform/microsoft-intune-partners)
