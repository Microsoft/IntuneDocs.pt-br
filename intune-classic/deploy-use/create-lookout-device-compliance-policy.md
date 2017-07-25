---
title: "Habilitar a regra de proteção de dispositivo"
description: "Habilite a regra de proteção contra ameaças móveis na política de conformidade do dispositivo."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 28ae825a9e33547a1987989d38667417214b97b2
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="e7565-103">Criar política de conformidade de dispositivo do Lookout no Intune</span><span class="sxs-lookup"><span data-stu-id="e7565-103">Create Lookout device compliance policy in Intune</span></span>
<a id="create-lookout-device-compliance-policy-in-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e7565-104">O Intune com a Defesa contra Ameaças Móveis do Lookout permite detectar ameaças em dispositivos móveis e avaliar o risco nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e7565-104">Intune with Lookout Mobile Threat Defense lets you detect threats on mobile devices and assess risk on those devices.</span></span> <span data-ttu-id="e7565-105">Você pode criar uma regra de política de conformidade que avalia o risco para determinar se o dispositivo está em conformidade.</span><span class="sxs-lookup"><span data-stu-id="e7565-105">You can create a compliance policy rule that assesses risk to determine if the device is compliant.</span></span> <span data-ttu-id="e7565-106">Em seguida, é possível usar a política de acesso condicional para bloquear o acesso a serviços de acordo com a conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e7565-106">You can then use conditional access policy to block access to services based on device compliance.</span></span>

<span data-ttu-id="e7565-107">Pré-requisitos para a política de conformidade com a Defesa contra Ameaças Móveis do Lookout:</span><span class="sxs-lookup"><span data-stu-id="e7565-107">Prerequisites for compliance policy with Lookout Mobile Threat Defense:</span></span>

- [<span data-ttu-id="e7565-108">Configurar a assinatura da Defesa contra Ameaças Móveis do Lookout</span><span class="sxs-lookup"><span data-stu-id="e7565-108">Set up Lookout Mobile Threat Defense subscription</span></span>](setup-your-lookout-mtd-subscription.md)
- [<span data-ttu-id="e7565-109">Habilitar a conexão do Lookout MTP no console do administrador do Intune</span><span class="sxs-lookup"><span data-stu-id="e7565-109">Enable the Lookout connection in Intune</span></span>](enable-lookout-mtd-connection.md)
- [<span data-ttu-id="e7565-110">Configurar e implantar o aplicativo Lookout for work</span><span class="sxs-lookup"><span data-stu-id="e7565-110">Configure and deploy the Lookout for work app</span></span>](configure-deploy-lookout-for-work-app.md)

<span data-ttu-id="e7565-111">Como parte da configuração da Defesa contra Ameaças Móveis do Lookout, no [console do Lookout](https://aad.lookout.com), você criou uma política que classifica diversas ameaças nos níveis alto, médio e baixo.</span><span class="sxs-lookup"><span data-stu-id="e7565-111">As part of the Lookout Mobile Threat Defense setup, in the [Lookout console](https://aad.lookout.com), you created a policy that classifies various threats as high, medium and low.</span></span> <span data-ttu-id="e7565-112">Na política de conformidade do Intune, defina o nível máximo de ameaças permitido.</span><span class="sxs-lookup"><span data-stu-id="e7565-112">In the Intune compliance policy, you set the maximum allowed threat level.</span></span>

1. <span data-ttu-id="e7565-113">No [console do administrador do Intune](https://manage.microsoft.com), acesse a página **Políticas de Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="e7565-113">In the [Intune administrator console](https://manage.microsoft.com), go to the **Compliance Policies** page.</span></span> <span data-ttu-id="e7565-114">É possível usar uma política de conformidade existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="e7565-114">You can either use an existing compliance policy or create a new one.</span></span> <span data-ttu-id="e7565-115">Acesse **Integridade do Dispositivo** e habilite **Proteção contra Ameaças ao Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="e7565-115">Go to **Device Health** and enable **Device Threat Protection**.</span></span>
  <span data-ttu-id="e7565-116">![captura de tela que mostra a definição da regra de proteção contra ameaças ao dispositivo no ](../media/mtp/mtp-compliance-policy-rule.png)</span><span class="sxs-lookup"><span data-stu-id="e7565-116">![screenshot showing the device threat protection rule setting in ](../media/mtp/mtp-compliance-policy-rule.png)</span></span>

2. <span data-ttu-id="e7565-117">Selecione o **Nível máximo de ameaça permitido**:</span><span class="sxs-lookup"><span data-stu-id="e7565-117">Select the **Maximum allowed threat level**:</span></span>
  * <span data-ttu-id="e7565-118">**Nenhum (Seguro)**: este é o mais seguro.</span><span class="sxs-lookup"><span data-stu-id="e7565-118">**None (Secured)**: This is the most secure.</span></span>  <span data-ttu-id="e7565-119">O dispositivo não pode ter nenhuma ameaça presente e ainda acessar os recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="e7565-119">The device cannot have any threats present and still access company resources.</span></span>  <span data-ttu-id="e7565-120">Se nenhuma ameaça for encontrada, o dispositivo será avaliado como fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="e7565-120">If any threats are found, the device is evaluated as non-compliant.</span></span>  
  * <span data-ttu-id="e7565-121">**Baixo**: o dispositivo estará em conformidade se apenas ameaças de nível baixo estiverem presentes.</span><span class="sxs-lookup"><span data-stu-id="e7565-121">**Low**: The device is compliant if only low level threats are present.</span></span> <span data-ttu-id="e7565-122">Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.</span><span class="sxs-lookup"><span data-stu-id="e7565-122">Anything higher puts the device in a non-compliant status.</span></span>
  * <span data-ttu-id="e7565-123">**Médio**: o dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio.</span><span class="sxs-lookup"><span data-stu-id="e7565-123">**Medium**: The device is compliant if the threats found on the device are low or medium level.</span></span> <span data-ttu-id="e7565-124">Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="e7565-124">If high level threats are detected, the device is determined as non-compliant.</span></span>
  * <span data-ttu-id="e7565-125">**Alto**: esta é a opção menos segura.</span><span class="sxs-lookup"><span data-stu-id="e7565-125">**High**: This is the least secure.</span></span> <span data-ttu-id="e7565-126">Isso permite todos os níveis de ameaça e usa o Lookout Mobile Threat Protection apenas para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="e7565-126">This allows all threat levels, and uses Lookout mobile threat protection for reporting purposes only.</span></span>

![captura de tela mostrando a opção de nível de ameaça para a configuração de regra de proteção contra ameaças do dispositivo](../media/mtp/mtp-compliance-policy-setting.png)

<span data-ttu-id="e7565-128">Se você criar políticas de acesso condicional para o Office 365 ou outros serviços, essa avaliação de conformidade será avaliada e os dispositivos que não estiverem em conformidade serão impedidos de acessar esses serviços até que a ameaça seja resolvida.</span><span class="sxs-lookup"><span data-stu-id="e7565-128">If you create conditional access policies for Office 365 or other services, this compliance evaluation is assessed and non-compliant devices are blocked from accessing those services until the threat is resolved.</span></span>

## <span data-ttu-id="e7565-129">Monitorar ameaças ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="e7565-129">Monitor device threats</span></span>
<a id="monitor-device-threats" class="xliff"></a>
<span data-ttu-id="e7565-130">Para ver o estado de conformidade de um dispositivo, acesse o [console do administrador do Intune](https://manage.microsoft.com) e exiba **Todos os Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="e7565-130">To see the compliance state of a device, go to the [Intune administrator console](https://manage.microsoft.com) and view **All Devices**.</span></span>

![captura de tela da página de dispositivos no console do administrador do Intune mostrando o status de conformidade de um dispositivo](../media/mtp/mtp-device-status-intune-console.png)

## <span data-ttu-id="e7565-132">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e7565-132">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
* <span data-ttu-id="e7565-133">Criar política de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="e7565-133">Create conditional access policy</span></span>
  * [<span data-ttu-id="e7565-134">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e7565-134">Exchange Online</span></span>](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [<span data-ttu-id="e7565-135">Exchange Local</span><span class="sxs-lookup"><span data-stu-id="e7565-135">Exchange On-premises</span></span>](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [<span data-ttu-id="e7565-136">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e7565-136">SharePoint Online</span></span>](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [<span data-ttu-id="e7565-137">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e7565-137">Skype for Business Online</span></span>](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [<span data-ttu-id="e7565-138">Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="e7565-138">Dynamics CRM</span></span>](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
