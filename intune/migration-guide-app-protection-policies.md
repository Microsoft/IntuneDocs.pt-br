---
<<<<<<< HEAD
title: "<span data-ttu-id=\"10a51-101\">Configurar políticas de proteção de aplicativo durante uma migração do Intune</span><span class=\"sxs-lookup\"><span data-stu-id=\"10a51-101\">Configure app protection policies during an Intune migration</span></span>"
description: "<span data-ttu-id=\"10a51-102\">Este artigo fornece as etapas necessárias para configurar políticas de proteção de aplicativo durante uma migração do Intune.</span><span class=\"sxs-lookup\"><span data-stu-id=\"10a51-102\">This article provides the necessary steps to set up app protection policies during an Intune migration.</span></span>"
=======
title: "Configurar políticas de proteção de aplicativo durante uma migração do Intune"
description: "Este artigo fornece as etapas necessárias para configurar políticas de proteção de aplicativo durante uma migração do Intune."
>>>>>>> live
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: c58ce51731b476cfca71851430297aff3edc5cd6
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="configure-app-protection-policies-optional"></a><span data-ttu-id="10a51-103">Configurar políticas de proteção de aplicativo (opcional)</span><span class="sxs-lookup"><span data-stu-id="10a51-103">Configure app protection policies (optional)</span></span>


<<<<<<< HEAD
<span data-ttu-id="10a51-104">As políticas de proteção do aplicativo permitem a você:</span><span class="sxs-lookup"><span data-stu-id="10a51-104">App protection policies allow you to:</span></span>
* <span data-ttu-id="10a51-105">Criptografar aplicativos</span><span class="sxs-lookup"><span data-stu-id="10a51-105">Encrypt apps</span></span>
* <span data-ttu-id="10a51-106">Definir um PIN quando o aplicativo é acessado</span><span class="sxs-lookup"><span data-stu-id="10a51-106">Define a PIN when the app is accessed</span></span>
* <span data-ttu-id="10a51-107">Bloquear a execução de aplicativos em dispositivos desbloqueados ou modificados, além de muitas outras proteções.</span><span class="sxs-lookup"><span data-stu-id="10a51-107">Block apps from running on jail-broken or rooted devices, and many other protections.</span></span>

<span data-ttu-id="10a51-108">Se o telefone do usuário for perdido ou roubado, você poderá apagar seletivamente os dados corporativos, deixando os dados pessoais intactos.</span><span class="sxs-lookup"><span data-stu-id="10a51-108">If the user's phone is lost or stolen, you can selectively wipe the corporate data remotely while leaving the personal data intact.</span></span>
=======
As políticas de proteção do aplicativo permitem a você:
* Criptografar aplicativos
* Definir um PIN quando o aplicativo é acessado
* Bloquear a execução de aplicativos em dispositivos desbloqueados ou modificados, além de muitas outras proteções.

Se o telefone do usuário for perdido ou roubado, você poderá apagar seletivamente os dados corporativos, deixando os dados pessoais intactos.

As políticas de proteção de aplicativo aplicam a segurança no nível do aplicativo e não exigem o registro do dispositivo. Você pode usá-las com dispositivos registrados no Intune ou não. Além disso, você pode aplicá-las a dispositivos registrados em um provedor de MDM de terceiros.
>>>>>>> live

<span data-ttu-id="10a51-109">As políticas de proteção de aplicativo aplicam a segurança no nível do aplicativo e não exigem o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="10a51-109">App protection policies apply security at the app level and do not require device enrollment.</span></span> <span data-ttu-id="10a51-110">Você pode usá-las com dispositivos registrados no Intune ou não.</span><span class="sxs-lookup"><span data-stu-id="10a51-110">You can use them with devices enrolled into Intune or not.</span></span> <span data-ttu-id="10a51-111">Além disso, você pode aplicá-las a dispositivos registrados em um provedor de MDM de terceiros.</span><span class="sxs-lookup"><span data-stu-id="10a51-111">Additionally, you can apply them to devices enrolled into a third-party MDM provider.</span></span>

<<<<<<< HEAD
## <a name="app-protection-policies-with-lob-apps"></a><span data-ttu-id="10a51-112">Políticas de proteção de aplicativo com aplicativos LOB</span><span class="sxs-lookup"><span data-stu-id="10a51-112">App protection policies with LOB apps</span></span>
=======
Também é possível estender as políticas de proteção de aplicativo móvel aos seus aplicativos LOB (linha de negócios) usando o [SDK de Aplicativo do Microsoft Intune](app-sdk-get-started.md) ou a Microsoft Intune App Wrapping Tool para as plataformas [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) e [Android](https://www.microsoft.com/download/details.aspx?id=47267).
>>>>>>> live

<span data-ttu-id="10a51-113">Também é possível estender as políticas de proteção de aplicativo móvel aos seus aplicativos LOB (linha de negócios) usando o [SDK de Aplicativo do Microsoft Intune](app-sdk-get-started.md) ou a Microsoft Intune App Wrapping Tool para as plataformas [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) e [Android](https://www.microsoft.com/download/details.aspx?id=47267).</span><span class="sxs-lookup"><span data-stu-id="10a51-113">You can also extend the mobile app protection policies to your line-of-business (LOB) apps by using the [Microsoft Intune App SDK](app-sdk-get-started.md) or the Microsoft Intune App Wrapping Tool for both [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) and [Android](https://www.microsoft.com/download/details.aspx?id=47267) platforms.</span></span>

<<<<<<< HEAD
## <a name="how-do-app-protection-policies-help-during-migration"></a><span data-ttu-id="10a51-114">Como as políticas de proteção de aplicativo ajudam durante a migração?</span><span class="sxs-lookup"><span data-stu-id="10a51-114">How do app protection policies help during migration?</span></span>

<span data-ttu-id="10a51-115">Em uma migração, você deve remover dispositivos do provedor de MDM antigo e registrá-los no Intune.</span><span class="sxs-lookup"><span data-stu-id="10a51-115">In a migration, you must remove devices from the old MDM provider and enroll them into Intune.</span></span> <span data-ttu-id="10a51-116">Planeje bem essa ação e estimule os usuários finais a deixarem o provedor antigo de MDM e a registrarem-se imediatamente no Intune.</span><span class="sxs-lookup"><span data-stu-id="10a51-116">You should plan for this and encourage your end-users to leave the old MDM provider and immediately enroll into Intune.</span></span> <span data-ttu-id="10a51-117">No entanto, durante a migração alguns usuários, cujos dispositivos não são gerenciados pelo provedor de MDM, podem atrasar a conclusão do processo de registro.</span><span class="sxs-lookup"><span data-stu-id="10a51-117">However, during the migration there may be users who delay completing the enrollment process and whose devices are not managed by either MDM provider.</span></span>
=======
Em uma migração, você deve remover dispositivos do provedor de MDM antigo e registrá-los no Intune. Planeje bem essa ação e estimule os usuários finais a deixarem o provedor antigo de MDM e a registrarem-se imediatamente no Intune. No entanto, durante a migração alguns usuários, cujos dispositivos não são gerenciados pelo provedor de MDM, podem atrasar a conclusão do processo de registro.

Esse período pode deixar sua organização mais vulnerável a roubos de dispositivo e perda de dados corporativos se o acesso aos recursos corporativos ainda for permitido. Ele também poderá levar à redução da produtividade do usuário se o acesso aos recursos corporativos for bloqueado.
>>>>>>> live

<span data-ttu-id="10a51-118">Esse período pode deixar sua organização mais vulnerável a roubos de dispositivo e perda de dados corporativos se o acesso aos recursos corporativos ainda for permitido.</span><span class="sxs-lookup"><span data-stu-id="10a51-118">This period can leave your organization more vulnerable to device theft and corporate data loss if corporate resource access is still allowed.</span></span> <span data-ttu-id="10a51-119">Ele também poderá levar à redução da produtividade do usuário se o acesso aos recursos corporativos for bloqueado.</span><span class="sxs-lookup"><span data-stu-id="10a51-119">It may also lead to lower user productivity if corporate resource access is blocked.</span></span>

<span data-ttu-id="10a51-120">O Intune pode oferecer proteção de dados corporativos durante a migração para que você ainda tenha cobertura de segurança para seus dados corporativos quando não houver gerenciamento no nível do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="10a51-120">Intune can offer corporate data protections during the migration so you can still have security coverage for your corporate data when there’s no device-level management.</span></span>

<span data-ttu-id="10a51-121">Quando você desabilita o acesso condicional no provedor antigo de MDM, os usuários ainda podem ser produtivos enquanto você os integra ao Intune.</span><span class="sxs-lookup"><span data-stu-id="10a51-121">As you disable conditional access in the old MDM provider, users can still be productive while you on-board them into Intune.</span></span>

<<<<<<< HEAD
## <a name="task-list-for-app-protection-policies"></a><span data-ttu-id="10a51-122">Lista de tarefas para políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="10a51-122">Task list for app protection policies</span></span>
=======
1. [Criar uma política de proteção de aplicativo](app-protection-policies.md#create-an-app-protection-policy)
2. [Implantar uma política](app-protection-policies.md#deploy-a-policy-to-users)
>>>>>>> live

1. [<span data-ttu-id="10a51-123">Criar uma política de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="10a51-123">Create an app protection policy</span></span>](app-protection-policies.md#create-an-app-protection-policy)
2. [<span data-ttu-id="10a51-124">Implantar uma política</span><span class="sxs-lookup"><span data-stu-id="10a51-124">Deploy a policy</span></span>](app-protection-policies.md#deploy-a-policy-to-users)

<<<<<<< HEAD
=======
## <a name="next-steps"></a>Próximas etapas
>>>>>>> live

## <a name="next-steps"></a><span data-ttu-id="10a51-125">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="10a51-125">Next steps</span></span>

[<span data-ttu-id="10a51-126">Considerações especiais de migração</span><span class="sxs-lookup"><span data-stu-id="10a51-126">Special migration considerations</span></span>](migration-guide-considerations.md)
