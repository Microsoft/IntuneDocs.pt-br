---
title: "Criar a política de conformidade da Defesa contra Ameaças Móveis do Skycure"
description: "Crie a política de conformidade da Defesa contra Ameaças Móveis do Skycure no console clássico do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56ff1728-1119-4e8a-aae6-ed5c7fafa052
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 29caf162500e25c2a0151be92aabe4cc432e241b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="bbfe6-103">Criar a política de conformidade da Defesa contra Ameaças Móveis do Skycure</span><span class="sxs-lookup"><span data-stu-id="bbfe6-103">Create Skycure Mobile Threat Defense compliance policy</span></span>
<a id="create-skycure-mobile-threat-defense-compliance-policy" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="bbfe6-104">O Intune com a Defesa contra Ameaças Móveis do Skycure permite detectar ameaças em dispositivos móveis e avaliar o risco nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-104">Intune with Skycure Mobile Threat Defense lets you detect threats on mobile devices and assess risk on those devices.</span></span> <span data-ttu-id="bbfe6-105">Você pode criar uma regra de política de conformidade do Intune que avalia o risco para determinar se o dispositivo está em conformidade.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-105">You can create an Intune compliance policy rule that assesses risk to determine if the device is compliant.</span></span> <span data-ttu-id="bbfe6-106">Em seguida, é possível usar a política de acesso condicional para bloquear o acesso a serviços de acordo com a conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-106">You can then use conditional access policy to block access to services based on device compliance.</span></span>

## <span data-ttu-id="bbfe6-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="bbfe6-107">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

<span data-ttu-id="bbfe6-108">Pré-requisitos para a política de conformidade com a proteção contra ameaças ao dispositivo do Skycure:</span><span class="sxs-lookup"><span data-stu-id="bbfe6-108">Prerequisites for compliance policy with Skycure device threat protection:</span></span>

-   [<span data-ttu-id="bbfe6-109">Configurar a integração do Skycure com o Intune</span><span class="sxs-lookup"><span data-stu-id="bbfe6-109">Set up Skycure integration with Intune</span></span>](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

-   [<span data-ttu-id="bbfe6-110">Habilitar a conexão do Skycure no Intune</span><span class="sxs-lookup"><span data-stu-id="bbfe6-110">Enable the Skycure connection in Intune</span></span>](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

<span data-ttu-id="bbfe6-111">Como parte da configuração da Defesa contra Ameaças Móveis do Skycure, no console do Skycure, você criou uma política que classifica diversas ameaças nos níveis alto, médio e baixo.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-111">As part of the Skycure Mobile Threat Defense setup, in the Skycure console, you created a policy that classifies various threats as high, medium and low.</span></span> <span data-ttu-id="bbfe6-112">Defina o nível máximo de ameaças permitido na política de conformidade do Intune.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-112">You now need to set the maximum allowed threat level in the Intune compliance policy.</span></span>

## <span data-ttu-id="bbfe6-113">Para criar a política de conformidade do Skycure</span><span class="sxs-lookup"><span data-stu-id="bbfe6-113">To create Skycure compliance policy</span></span>
<a id="to-create-skycure-compliance-policy" class="xliff"></a>

1.  <span data-ttu-id="bbfe6-114">Acesse o [console clássico Intune](https://manage.microsoft.com/) e insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-114">Go to the [Intune classic console](https://manage.microsoft.com/) then enter your credentials.</span></span>

2.  <span data-ttu-id="bbfe6-115">Escolha **Política** &gt; **Políticas de Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-115">Choose **Policy** &gt; **Compliance Policies**.</span></span> <span data-ttu-id="bbfe6-116">É possível usar uma política de conformidade existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-116">You can either use an existing compliance policy or create a new one.</span></span>

3.  <span data-ttu-id="bbfe6-117">Escolha **Adicionar** &gt; **Integridade do Dispositivo** e habilite **Proteção contra Ameaças ao Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-117">Choose **Add** &gt; **Device Health**, then enable **Device Threat Protection**.</span></span>

4.  <span data-ttu-id="bbfe6-118">Selecione o **Nível máximo de ameaça permitido**:</span><span class="sxs-lookup"><span data-stu-id="bbfe6-118">Select the **Maximum allowed threat level**:</span></span>

    <span data-ttu-id="bbfe6-119">a.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-119">a.</span></span>  <span data-ttu-id="bbfe6-120">**Nenhum (Seguro)**: este é o mais seguro.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-120">**None (Secured)**: This is the most secure.</span></span> <span data-ttu-id="bbfe6-121">O dispositivo não pode ter nenhuma ameaça presente e ainda acessar os recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-121">The device cannot have any threats present and still access company resources.</span></span> <span data-ttu-id="bbfe6-122">Se nenhuma ameaça for encontrada, o dispositivo será avaliado como fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-122">If any threats are found, the device is evaluated as non-compliant.</span></span>

    <span data-ttu-id="bbfe6-123">b.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-123">b.</span></span>  <span data-ttu-id="bbfe6-124">**Baixo**: o dispositivo estará em conformidade se apenas ameaças de nível baixo estiverem presentes.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-124">**Low**: The device is compliant if only low level threats are present.</span></span> <span data-ttu-id="bbfe6-125">Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-125">Anything higher puts the device in a non-compliant status.</span></span>

    <span data-ttu-id="bbfe6-126">c.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-126">c.</span></span>  <span data-ttu-id="bbfe6-127">**Médio**: o dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-127">**Medium**: The device is compliant if the threats found on the device are low or medium level.</span></span> <span data-ttu-id="bbfe6-128">Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-128">If high level threats are detected, the device is determined as non-compliant.</span></span>

    <span data-ttu-id="bbfe6-129">d.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-129">d.</span></span>  <span data-ttu-id="bbfe6-130">**Alto**: esta é a opção menos segura.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-130">**High**: This is the least secure.</span></span> <span data-ttu-id="bbfe6-131">Isso permite todos os níveis de ameaça e usa a Defesa contra Ameaças Móveis do Skycure apenas para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-131">This allows all threat levels, and uses Skycure mobile threat defense for reporting purposes only.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbfe6-132">Se você criar políticas de acesso condicional para o Office 365 ou outros serviços, essa avaliação de conformidade será avaliada e os dispositivos que não estiverem em conformidade serão impedidos de acessar esses serviços até que a ameaça seja resolvida.</span><span class="sxs-lookup"><span data-stu-id="bbfe6-132">If you create conditional access policies for Office 365 or other services, this compliance evaluation is assessed and non-compliant devices are blocked from accessing those services until the threat is resolved.</span></span>

## <span data-ttu-id="bbfe6-133"><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="bbfe6-133"><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Next steps</span></span>
<a id="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps" class="xliff"></a>

-   <span data-ttu-id="bbfe6-134">Criar política de acesso condicional para:</span><span class="sxs-lookup"><span data-stu-id="bbfe6-134">Create a conditional access policy for:</span></span>

    -   [<span data-ttu-id="bbfe6-135">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bbfe6-135">Exchange Online</span></span>](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [<span data-ttu-id="bbfe6-136">Exchange Local</span><span class="sxs-lookup"><span data-stu-id="bbfe6-136">Exchange On-premises</span></span>](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [<span data-ttu-id="bbfe6-137">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bbfe6-137">SharePoint Online</span></span>](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [<span data-ttu-id="bbfe6-138">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bbfe6-138">Skype for Business Online</span></span>](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [<span data-ttu-id="bbfe6-139">Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="bbfe6-139">Dynamics CRM</span></span>](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)
