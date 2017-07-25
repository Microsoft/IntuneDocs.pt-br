---
title: "Publicar aplicativos móveis para seus usuários"
description: 
keywords: 
author: jeffgilb
ms.author: jeffgilb
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
ms.openlocfilehash: 71d57965164f0822e1a6d95715c4f9c92f7bf4bd
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="4b5fa-102">Guia de início rápido: Publicar aplicativos móveis para seus usuários</span><span class="sxs-lookup"><span data-stu-id="4b5fa-102">Quick Start Guide: Publish mobile apps to your users</span></span>
<a id="quick-start-guide-publish-mobile-apps-to-your-users" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4b5fa-103">O Microsoft Intune pode ajudar a aumentar a produtividade de seus usuários de modo rápido e fácil dando a eles acesso aos aplicativos móveis e da área de trabalho de que precisam dos dispositivos de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-103">Microsoft Intune can help increase your end users’ productivity by quickly and easily giving them access to the mobile and desktop apps they need from the devices of their choice.</span></span> <span data-ttu-id="4b5fa-104">Tornar aplicativos facilmente disponíveis para os usuários finais reduz o tempo e os esforços que os usuários dispendem procurando e instalando os aplicativos corretos, o que reduz as chamadas de assistência técnica quando os usuários não conseguem localizar os aplicativos de que precisam.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-104">Making apps easily available to end users reduces the time and effort users spend searching for and installing the correct apps, which reduces helpdesk calls when users cannot find the apps they need.</span></span>   

## <span data-ttu-id="4b5fa-105">Este é o guia de início rápido certo para mim?</span><span class="sxs-lookup"><span data-stu-id="4b5fa-105">Is this quick start guide right for me?</span></span>
<a id="is-this-quick-start-guide-right-for-me" class="xliff"></a>
<span data-ttu-id="4b5fa-106">Você gostaria que os usuários tivessem acesso rápido a todos os aplicativos de que precisam para serem produtivos no trabalho, apresentados em um portal comum, independentemente do tipo de dispositivo que usam?</span><span class="sxs-lookup"><span data-stu-id="4b5fa-106">Would you like your users to quickly have access to all the apps they need to be productive at work, presented in a common portal regardless of the type of device they use?</span></span>

<span data-ttu-id="4b5fa-107">Se sim, o Microsoft Intune permitirá que você publique aplicativos (Office Mobile, aplicativos de linha de negócios internos ou outros aplicativos móveis e de área de trabalho) em um único portal comum: o [site ou aplicativo de Portal da Empresa do Intune](/intune-user-help/company-portal-frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="4b5fa-107">If yes, Microsoft Intune allows you to publish apps (Office mobile, internal line of business or other mobile and desktop apps) in a single common portal: the [Intune Company Portal app or website](/intune-user-help/company-portal-frequently-asked-questions).</span></span>

## <span data-ttu-id="4b5fa-108">Como fazer isso?</span><span class="sxs-lookup"><span data-stu-id="4b5fa-108">How do I do it?</span></span>
<a id="how-do-i-do-it" class="xliff"></a>
1.  <span data-ttu-id="4b5fa-109">[Registre dispositivos](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune) no gerenciamento de dispositivo móvel do Intune.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-109">[Enroll devices](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune) into Intune mobile device management.</span></span>
2.  <span data-ttu-id="4b5fa-110">[Adicione ao Intune aplicativos](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) que você deseja implantar em dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-110">[Add apps to Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) that you want to deploy to enrolled devices.</span></span>
3.  <span data-ttu-id="4b5fa-111">[Implante aplicativos usando o Intune](/intune-classic/deploy-use/deploy-apps) em dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="4b5fa-111">[Deploy apps using Intune](/intune-classic/deploy-use/deploy-apps) to enrolled devices.</span></span>

### <span data-ttu-id="4b5fa-112">Informação adicional:</span><span class="sxs-lookup"><span data-stu-id="4b5fa-112">Additional information:</span></span>
<a id="additional-information" class="xliff"></a>
<span data-ttu-id="4b5fa-113">Se a publicação de aplicativos do Office Mobile for feita com a intenção de usar recursos de MAM do Intune para gerenciar a proteção contra perda de dados para esses aplicativos, cada usuário final que for alvo de políticas de MAM precisará [receber uma licença de usuário para o Office 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="4b5fa-113">If publishing Office mobile apps is done with the intention of using Intune’s MAM capabilities to manage data loss protection for those apps, then each end user assigned MAM policies will need to be [assigned a user license for Office 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <span data-ttu-id="4b5fa-114">O que devo fazer em seguida?</span><span class="sxs-lookup"><span data-stu-id="4b5fa-114">What should I do next?</span></span>
<a id="what-should-i-do-next" class="xliff"></a>
- [<span data-ttu-id="4b5fa-115">Monitorar implantações de aplicativo no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4b5fa-115">Monitor app deployments in Microsoft Intune</span></span>](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)
- [<span data-ttu-id="4b5fa-116">Proteger dados da empresa contra perda de dados em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="4b5fa-116">Protect company data against data loss in mobile devices</span></span>](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
