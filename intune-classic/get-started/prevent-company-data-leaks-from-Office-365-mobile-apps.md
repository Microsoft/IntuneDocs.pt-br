---
title: "Impedir vazamentos de dados da empresa de aplicativos móveis do Office 365"
description: "Use o Intune para proteger os dados de sua organização usando políticas de MAM (gerenciamento de aplicativo móvel) que ajudam a evitar vazamentos de dados da empresa de aplicativos móveis do Office 365 ou outros aplicativos de LOB (linha de negócios)."
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 19be3de7-539c-49f5-8c46-5363b987fef9
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3f35dcb7168e9c76a8286a1425a26306914cfdb3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="d9579-103">Guia de início rápido: Impedir vazamentos de dados da empresa de aplicativos móveis do Office 365</span><span class="sxs-lookup"><span data-stu-id="d9579-103">Quick Start Guide: Prevent company data leaks from Office 365 mobile apps</span></span>
<a id="quick-start-guide-prevent-company-data-leaks-from-office-365-mobile-apps" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="d9579-104">O Microsoft Intune pode ajudá-lo a proteger os dados da sua organização usando políticas de MAM (gerenciamento de aplicativos móveis) que ajudam a evitar vazamentos de dados da empresa de aplicativos móveis do Office 365 ou outros aplicativos de LOB (linha de negócios).</span><span class="sxs-lookup"><span data-stu-id="d9579-104">Microsoft Intune can help you secure your organization’s data using mobile application management (MAM) policies that help prevent company data leaks from Office 365 mobile apps or other line of business (LOB) apps.</span></span> <span data-ttu-id="d9579-105">As políticas de MAM do Intune podem ser usadas sem a necessidade dos usuários finais registrarem seus dispositivos no MDM (gerenciamento de dispositivo móvel) do Intune.</span><span class="sxs-lookup"><span data-stu-id="d9579-105">Intune MAM policies can be used without requiring end users to enroll their devices in Intune mobile device management (MDM).</span></span> <span data-ttu-id="d9579-106">Portanto, se você tiver usuários que não desejam registrar seus dispositivos BYOD iOS ou Android em uma solução de MDM da Microsoft (Intune, Configuration Manager ou EAS), quiser proteger dados corporativos sem gerenciar dispositivos de usuários finais ou já estiver usando uma solução que não faz parte do MDM da Microsoft, o Intune poderá ajudar você a aumentar a segurança de dados da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="d9579-106">So, if you have users who do not want to enroll their BYOD iOS or Android mobile devices into a Microsoft MDM solution (Intune, Configuration Manager, or EAS), you want to protect corporate data without managing end users devices, or you are already using a non-Microsoft MDM solution, Intune can help you increase your company’s data security.</span></span>   

## <span data-ttu-id="d9579-107">Este é o guia de início rápido certo para mim?</span><span class="sxs-lookup"><span data-stu-id="d9579-107">Is this quick start guide right for me?</span></span>
<a id="is-this-quick-start-guide-right-for-me" class="xliff"></a>
<span data-ttu-id="d9579-108">Você gostaria de permitir que os usuários finais acessassem seus dados do Office 365 e de aplicativos de LOB em seus dispositivos Android e iOS sem a necessidade de registrar o dispositivo em uma solução de MDM (gerenciamento de dispositivo móvel), mas ainda controlar o que eles podem ou não fazer com esses dados, como copiar e colá-los em aplicativos pessoais?</span><span class="sxs-lookup"><span data-stu-id="d9579-108">Would you like to allow your end users to access your Office 365 and LOB app data on their iOS and Android devices without requiring device enrollment in a Mobile Device Management (MDM) solution, but still control what they can or cannot do with that data such as copying and pasting it onto personal apps?</span></span>

<span data-ttu-id="d9579-109">Se sim, o Microsoft Intune permite que você defina políticas de MAM para aplicativos móveis do Office 365 no iOS e Android, inclusive restrições para recortar/copiar/colar, impedir “salvar como”, definir requisitos de PIN e a capacidade de apagar remotamente dados protegidos por MAM.</span><span class="sxs-lookup"><span data-stu-id="d9579-109">If yes, Microsoft Intune allows you to set MAM policies for Office 365 mobile apps on iOS and Android, including cut/copy/paste restrictions, preventing ‘save-as’, setting PIN requirements, and the ability to remotely wipe MAM protected data.</span></span>  <span data-ttu-id="d9579-110">Isso protege os dados da empresa sem exigir que os usuários registrem seus dispositivos em uma solução de MDM, enquanto mantém uma excelente experiência do usuário final com aplicativos móveis do Office.</span><span class="sxs-lookup"><span data-stu-id="d9579-110">This protects company data without requiring users to enroll their devices into an MDM solution while maintaining a great end-user experience with Office mobile apps.</span></span>

## <span data-ttu-id="d9579-111">Como fazer isso?</span><span class="sxs-lookup"><span data-stu-id="d9579-111">How do I do it?</span></span>
<a id="how-do-i-do-it" class="xliff"></a>
1.  <span data-ttu-id="d9579-112">Tenha um entendimento básico de [como o MAM (gerenciamento de aplicativos móveis) do Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) funciona.</span><span class="sxs-lookup"><span data-stu-id="d9579-112">Get a basic understanding of [how Intune mobile application management (MAM)](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) works.</span></span>
2.  <span data-ttu-id="d9579-113">Descubra [o que você precisa fazer para começar a criar políticas de MAM](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="d9579-113">Find out [what you need to do before you can create MAM policies](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) in the Azure portal.</span></span>
3.  <span data-ttu-id="d9579-114">[Criar e implantar políticas de MAM](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) com o Intune.</span><span class="sxs-lookup"><span data-stu-id="d9579-114">[Create and deploy MAM policies](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) with Intune.</span></span>

### <span data-ttu-id="d9579-115">Informação adicional:</span><span class="sxs-lookup"><span data-stu-id="d9579-115">Additional information:</span></span>
<a id="additional-information" class="xliff"></a>
- <span data-ttu-id="d9579-116">[Experiência do usuário final](/intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune) usando aplicativos habilitados para MAM.</span><span class="sxs-lookup"><span data-stu-id="d9579-116">[End user experience](/intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune) using MAM enabled apps.</span></span>
- [<span data-ttu-id="d9579-117">Preparar aplicativos de LOB para MAM com o Intune</span><span class="sxs-lookup"><span data-stu-id="d9579-117">Prepare LOB apps for MAM with Intune</span></span>](/intune/apps-prepare-mobile-application-management)
- <span data-ttu-id="d9579-118"><a href="https://www.microsoft.com/cloud-platform/microsoft-intune-partners" target="_blank"> Lista de parceiros de aplicativos do Microsoft Intune &rarr;</a> que fornecem aplicativos habilitados para MAM.</span><span class="sxs-lookup"><span data-stu-id="d9579-118"><a href="https://www.microsoft.com/cloud-platform/microsoft-intune-partners" target="_blank"> List of Microsoft Intune application partners &rarr;</a> providing MAM-enabled apps.</span></span>

## <span data-ttu-id="d9579-119">O que devo fazer em seguida?</span><span class="sxs-lookup"><span data-stu-id="d9579-119">What should I do next?</span></span>
<a id="what-should-i-do-next" class="xliff"></a>
[<span data-ttu-id="d9579-120">Migrar de uma solução que não faz parte do MDM da Microsoft para o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d9579-120">Migrate from a non-Microsoft MDM solution to Microsoft Intune</span></span>](/intune-classic/deploy-use/migrate-to-intune)

[<span data-ttu-id="d9579-121">Registrar dispositivos no MDM do Intune</span><span class="sxs-lookup"><span data-stu-id="d9579-121">Enroll devices into Intune MDM</span></span>](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
