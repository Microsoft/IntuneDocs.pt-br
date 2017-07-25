---
title: "Como os usuários iOS podem obter aplicativos"
description: "Métodos para disponibilizar aplicativos do iOS para usuários finais"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0061d4ecd8d71f8b7363193e36b838741aa56a92
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="b9f03-103">Como os usuários iOS podem obter aplicativos</span><span class="sxs-lookup"><span data-stu-id="b9f03-103">How your iOS users get their apps</span></span>
<a id="how-your-ios-users-get-their-apps" class="xliff"></a>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="b9f03-104">Use estas informações para entender como e onde os usuários finais obtêm os aplicativos que você distribui por meio do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="b9f03-104">Use this information to understand how and where your end users get the apps that you distribute through Microsoft Intune.</span></span>

<span data-ttu-id="b9f03-105">**Aplicativos necessários** – Aplicativos que são exigidos pelo administrador e instalados no dispositivo com envolvimento mínimo do usuário, dependendo da plataforma.</span><span class="sxs-lookup"><span data-stu-id="b9f03-105">**Required apps**--Apps that are required by the admin and that are installed on the device with minimal user involvement, depending on the platform.</span></span>

<span data-ttu-id="b9f03-106">**Aplicativos disponíveis** – Aplicativos fornecidos na lista de aplicativos do Portal da Empresa e que o usuário pode optar por instalar.</span><span class="sxs-lookup"><span data-stu-id="b9f03-106">**Available apps**--Apps that are provided in the Company Portal app list and that a user may optionally choose to install.</span></span>

<span data-ttu-id="b9f03-107">**Aplicativos gerenciados** – Aplicativos que podem ser gerenciados por meio de políticas e que foram “encapsulados” pelo Intune ou compilados com o SDK (Software Development Kit) do MAM (Mobile Application Management) do Intune.</span><span class="sxs-lookup"><span data-stu-id="b9f03-107">**Managed apps**--Apps that can be managed through policies and that have been "wrapped" by Intune or have been built with the Intune Mobile Application Management (MAM) Software Development Kit (SDK).</span></span> <span data-ttu-id="b9f03-108">Esses aplicativos podem ser gerenciados pelo Intune e é possível aplicar políticas de aplicativo a eles.</span><span class="sxs-lookup"><span data-stu-id="b9f03-108">These apps can be managed by Intune, and application policies can be applied to them.</span></span>

<span data-ttu-id="b9f03-109">**Aplicativos não gerenciados** – Aplicativos que podem ser gerenciados por meio de políticas e que não foram encapsulados pelo Intune ou que não incorporam o SDK do MAM do Intune.</span><span class="sxs-lookup"><span data-stu-id="b9f03-109">**Unmanaged apps**--Apps that can be managed through policies and that have not been wrapped by Intune or that do not incorporate the Intune MAM SDK.</span></span> <span data-ttu-id="b9f03-110">Políticas de aplicativo que não podem ser aplicadas a esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b9f03-110">Application policies cannot be applied to these apps.</span></span>

<span data-ttu-id="b9f03-111">As restrições da Apple proíbem que aplicativos gerenciados e de linha de negócios da loja de aplicativos sejam listados no aplicativo do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="b9f03-111">Apple restrictions prohibit line-of-business and managed App Store apps from being listed in the Company Portal app.</span></span> <span data-ttu-id="b9f03-112">Para solucionar esse problema, os blocos no aplicativo do Portal da Empresa para iOS encaminham os usuários a diferentes modos de exibição em um único local (o site do Portal da Empresa) para todos os seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b9f03-112">To get around this issue, the tiles in the Company Portal app for iOS point users to different views in a single location (the Company Portal website) for all of their apps.</span></span>

<span data-ttu-id="b9f03-113">Os usuários registrados obtêm seus aplicativos tocando nos blocos a seguir na tela Aplicativos do aplicativo de Portal da Empresa:</span><span class="sxs-lookup"><span data-stu-id="b9f03-113">Enrolled users get their apps by tapping on the following tiles on the Apps screen of the Company Portal app:</span></span>

- <span data-ttu-id="b9f03-114">**Todos os Aplicativos** aponta para uma lista de todos os aplicativos na guia TODOS do [site do Portal da Empresa](https://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b9f03-114">**All Apps** points to a list of all apps in the ALL tab of the [Company Portal website](https://portal.manage.microsoft.com).</span></span>

- <span data-ttu-id="b9f03-115">**Aplicativos em destaque** leva os usuários à guia EM DESTAQUE do site do Portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="b9f03-115">**Featured Apps** take users to the FEATURED tab of the Company Portal website.</span></span>

- <span data-ttu-id="b9f03-116">**Categorias** aponta para a guia CATEGORIAS do site do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="b9f03-116">**Categories** points to the CATEGORIES tab of the Company Portal website.</span></span>


![Tela de aplicativos do Portal da Empresa para iOS](./media/ios-cp-app-main-apps-screen.png)

<span data-ttu-id="b9f03-118">Para obter informações sobre como adicionar aplicativos e colocá-los nesses blocos, consulte [Adicionar aplicativos para dispositivos registrados ao Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="b9f03-118">For information on how to add apps and put them in these tiles, see [Add apps for enrolled devices to Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).</span></span>

### <span data-ttu-id="b9f03-119">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b9f03-119">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="b9f03-120">Como os usuários do Android podem obter aplicativos</span><span class="sxs-lookup"><span data-stu-id="b9f03-120">How your Android users get their apps</span></span>](end-user-apps-android.md)

[<span data-ttu-id="b9f03-121">Como os usuários do Windows podem obter aplicativos</span><span class="sxs-lookup"><span data-stu-id="b9f03-121">How your Windows users get their apps</span></span>](end-user-apps-windows.md)
