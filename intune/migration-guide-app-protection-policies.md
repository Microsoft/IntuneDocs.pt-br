---
title: "Configurar políticas de proteção de aplicativo durante uma migração do Intune"
description: "A finalidade deste artigo é mostrar as etapas necessárias para configurar políticas de proteção de aplicativo durante uma migração do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cbe2c794a68ab37722c56448560a3c64f6087969
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="3e345-103">Configurar políticas de proteção de aplicativo (opcional)</span><span class="sxs-lookup"><span data-stu-id="3e345-103">Configure app protection policies (optional)</span></span>
<a id="configure-app-protection-policies-optional" class="xliff"></a>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="3e345-104">As políticas de proteção de aplicativo permitem que você criptografe aplicativos, defina um PIN quando o aplicativo for acessado, bloqueie a execução dos aplicativos em dispositivos desbloqueados ou modificados, além de muitas outras proteções.</span><span class="sxs-lookup"><span data-stu-id="3e345-104">App protection policies allow you to encrypt apps, define a PIN when the app is accessed, block apps from running on jail-broken or rooted devices, and many other protections.</span></span> <span data-ttu-id="3e345-105">Se o telefone do usuário for perdido ou roubado, você poderá apagar remota e seletivamente os dados corporativos, deixando os dados pessoais intactos por meio da aplicação de políticas de proteção do aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="3e345-105">If the user's phone is lost or stolen, you can selectively remote wipe the corporate data while leaving the personal data intact by applying mobile app protection policies.</span></span>

<span data-ttu-id="3e345-106">As políticas de proteção de aplicativo aplicam a segurança no nível do aplicativo e não exigem o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e345-106">App protection policies apply security at the app level and do not require device enrollment.</span></span> <span data-ttu-id="3e345-107">Elas podem ser usadas com dispositivos registrados no Intune ou não.</span><span class="sxs-lookup"><span data-stu-id="3e345-107">It can be used with devices enrolled into Intune or not.</span></span> <span data-ttu-id="3e345-108">Além disso, pode ser usada com dispositivos registrados em um provedor de MDM de terceiros.</span><span class="sxs-lookup"><span data-stu-id="3e345-108">Additionally, it can be used with devices enrolled into a third-party MDM provider.</span></span>

## <span data-ttu-id="3e345-109">Políticas de proteção de aplicativo com aplicativos LOB</span><span class="sxs-lookup"><span data-stu-id="3e345-109">App protection policies with LOB apps</span></span>
<a id="app-protection-policies-with-lob-apps" class="xliff"></a>

<span data-ttu-id="3e345-110">Também é possível estender as políticas de proteção de aplicativo móvel aos seus aplicativos LOB (linha de negócios) aproveitando o [SDK de Aplicativo do Microsoft Intune](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) ou a Microsoft Intune App Wrapping Tool para as plataformas [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) e [Android](https://www.microsoft.com/download/details.aspx?id=47267).</span><span class="sxs-lookup"><span data-stu-id="3e345-110">You can also extend the mobile app protection policies to your line-of-business (LOB) apps by leveraging the [Microsoft Intune App SDK](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) or the Microsoft Intune App Wrapping Tool for both [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) and [Android](https://www.microsoft.com/download/details.aspx?id=47267) platforms.</span></span>

## <span data-ttu-id="3e345-111">Como as políticas de proteção de aplicativo ajudam durante a migração?</span><span class="sxs-lookup"><span data-stu-id="3e345-111">How do app protection policies help during migration?</span></span>
<a id="how-do-app-protection-policies-help-during-migration" class="xliff"></a>

<span data-ttu-id="3e345-112">A migração exige a remoção de dispositivos do provedor antigo de MDM e o registro deles no Intune.</span><span class="sxs-lookup"><span data-stu-id="3e345-112">Migration requires removing devices from the old MDM provider and enrolling them into Intune.</span></span> <span data-ttu-id="3e345-113">Planeje bem essa ação e estimule os usuários finais a deixarem o provedor antigo de MDM e a registrarem-se imediatamente no Intune.</span><span class="sxs-lookup"><span data-stu-id="3e345-113">You should plan for this and encourage your end-users to leave the old MDM provider and immediately enroll into Intune.</span></span> <span data-ttu-id="3e345-114">No entanto, durante a migração alguns usuários, cujos dispositivos não são gerenciados pelo provedor de MDM, podem atrasar a conclusão do processo de registro.</span><span class="sxs-lookup"><span data-stu-id="3e345-114">However, during the migration there may be users who delay completing the enrollment process and whose devices are not managed by either MDM provider.</span></span>

<span data-ttu-id="3e345-115">Esse período pode deixar sua organização mais vulnerável a roubos de dispositivo e perda de dados corporativos se o acesso aos recursos corporativos ainda for permitido, e/ou perda de produtividade do usuário se o acesso aos recursos corporativos for bloqueado.</span><span class="sxs-lookup"><span data-stu-id="3e345-115">This period can leave your organization more vulnerable to device theft and corporate data loss if corporate resource access is still allowed, and/or loss of user productivity if corporate resource access is blocked.</span></span>

<span data-ttu-id="3e345-116">O Intune pode oferecer proteção de dados corporativos durante a migração para que você ainda tenha cobertura de segurança para seus dados corporativos quando não houver gerenciamento no nível do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3e345-116">Intune can offer corporate data protections during the migration so you can still have security coverage for your corporate data when there’s no device-level management.</span></span>

<span data-ttu-id="3e345-117">Quando você desabilita o acesso condicional no provedor antigo de MDM, os usuários ainda podem ser produtivos enquanto você os integra ao Intune.</span><span class="sxs-lookup"><span data-stu-id="3e345-117">As you disable conditional access in the old MDM provider, users can still be productive while you on-board them into Intune.</span></span>

## <span data-ttu-id="3e345-118">Lista de tarefas para políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="3e345-118">Task list for app protection policies</span></span>
<a id="task-list-for-app-protection-policies" class="xliff"></a>

1. [<span data-ttu-id="3e345-119">Criar uma política de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="3e345-119">Create an app protection policy</span></span>](/intune/app-protection-policies#create-an-app-protection-policy)
2. [<span data-ttu-id="3e345-120">Implantar uma política</span><span class="sxs-lookup"><span data-stu-id="3e345-120">Deploy a policy</span></span>](/intune/app-protection-policies#deploy-a-policy-to-users)


## <span data-ttu-id="3e345-121">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3e345-121">Next steps</span></span>
<a id="next-steps" class="xliff"></a> 

[<span data-ttu-id="3e345-122">Considerações especiais de migração</span><span class="sxs-lookup"><span data-stu-id="3e345-122">Special migration considerations</span></span>](migration-guide-considerations.md)
