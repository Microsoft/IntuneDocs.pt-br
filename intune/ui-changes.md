---
title: Para onde foi o meu recurso Intune no Azure?
titleSuffix: Intune on Azure
description: Ajuda a encontrar recursos do Intune no console do Azure.
keywords: 
author: dagerrit
ms.author: dagerrit
manager: angrobe
ms.date: 03/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b9d1ac3930e29bc024ece7e6b9b11c91a4e14c1
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="dd436-103">Para onde foi o meu recurso Intune no Azure?</span><span class="sxs-lookup"><span data-stu-id="dd436-103">Where did my Intune feature go in Azure?</span></span>
<a id="where-did-my-intune-feature-go-in-azure" class="xliff"></a>
<span data-ttu-id="dd436-104">Aproveitamos a oportunidade para organizar algumas tarefas mais logicamente à medida que mudamos o Intune para o portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="dd436-104">We took the opportunity to organize some tasks more logically as we moved Intune into the Azure portal.</span></span> <span data-ttu-id="dd436-105">Mas cada aperfeiçoamento vem com o custo de aprender a nova organização.</span><span class="sxs-lookup"><span data-stu-id="dd436-105">But every improvement comes with the cost of learning the new organization.</span></span> <span data-ttu-id="dd436-106">Assim, criamos este guia de referência para aqueles que estão totalmente familiarizados com o Intune no console clássico e querem saber como fazer algo no Intune no Azure.</span><span class="sxs-lookup"><span data-stu-id="dd436-106">So, we created this reference guide for those of you who are thoroughly familiar with Intune in the classic console and are wondering how to get something done in Intune on Azure.</span></span> <span data-ttu-id="dd436-107">Se este artigo não abordar um recurso que você está tentando localizar, deixe um comentário no final do artigo para que possamos atualizá-lo.</span><span class="sxs-lookup"><span data-stu-id="dd436-107">If this article doesn’t cover a feature you’re trying to find, please leave a comment at the end of the article so we can update it.</span></span>
## <span data-ttu-id="dd436-108">Guia de referência rápida</span><span class="sxs-lookup"><span data-stu-id="dd436-108">Quick reference guide</span></span>
<a id="quick-reference-guide" class="xliff"></a>
<span data-ttu-id="dd436-109">|Recurso |Caminho no console clássico |Caminho no Intune no Azure| |------------||---------------|---------------| |DEP (Programa de registro de dispositivos) |Administrador > Gerenciamento de Dispositivo Móvel > iOS e Mac OS X > Programa de registro de dispositivos |[Registro de dispositivo > Registro da Apple > Token do Programa de Registro](#where-did-apple-dep-go) | |DEP (Programa de registro de dispositivos)| Administrador > Gerenciamento de Dispositivo Móvel > iOS e Mac OS X > Programa de registro de dispositivos |[Registro de dispositivo > Registro da Apple > Números de Série do Programa de Registro](#where-did-apple-dep-go) | |Regras de Registro | Administrador > Gerenciamento de Dispositivo Móvel > Regras de Registro |[Registro de dispositivo > Restrições de Registro](#where-did-enrollment-rules-go) | |Grupos por Número de Série do iOS |Grupos > Todos os Dispositivos > Dispositivos corporativos pré-registrados > Por Número de Série do iOS|[Registro de dispositivo > Registro da Apple > Números de Série do Programa de Registro](#where-did-corporate-pre-enrolled-devices-go) | |Grupos por Número de Série do iOS |Grupos > Todos os Dispositivos > Dispositivos corporativos pré-registrados > Por Número de Série do iOS| [Registro de dispositivo > Registro da Apple > Números de Série da CA](#where-did-corporate-pre-enrolled-devices-go)| |Grupos por IMEI (todas as plataformas) | Grupos > Todos os Dispositivos > Dispositivos corporativos pré-registrados > Por IMEI (Todas as plataformas) | [Registro de dispositivo > Identificadores de Dispositivo Corporativo](#by-imei-all-platforms)| |Perfil de Registro de Dispositivo Corporativo | Política > Registro de Dispositivo Corporativo | [Registro de dispositivo > Registro da Apple > Perfis do Programa de Registro](#where-did-corporate-pre-enrolled-devices-go) | | Perfil de Registro do Dispositivo Corporativo | Política > Registro de Dispositivo Corporativo | [Registro de dispositivo > Registro da Apple > Perfis de CA](#where-did-corporate-pre-enrolled-devices-go) | | Android for Work | Administrador > Gerenciamento de Dispositivo Móvel > Android for Work | Registro de dispositivo > Registro do Android for Work | | Termos e Condições | Política > Termos e Condições | Registro de dispositivo > Termos e Condições |</span><span class="sxs-lookup"><span data-stu-id="dd436-109">|Feature |Path in classic console|Path in Intune on Azure| |------------||---------------|---------------| |Device Enrollment Program (DEP) |Admin > Mobile Device Management > iOS and Mac OS X > Device Enrollment Program|[Device enrollment > Apple Enrollment > Enrollment Program Token](#where-did-apple-dep-go) | |Device Enrollment Program (DEP)| Admin > Mobile Device Management > iOS and Mac OS X > Device Enrollment Program |[Device enrollment > Apple Enrollment > Enrollment Program Serial Numbers](#where-did-apple-dep-go) | |Enrollment Rules |Admin > Mobile Device Management > Enrollment Rules|[Device enrollment > Enrollment Restrictions](#where-did-enrollment-rules-go) | |Groups by iOS Serial Number |Groups > All Devices > Corporate Pre-enrolled devices > By iOS Serial Number|[Device enrollment > Apple Enrollment > Enrollment Program Serial Numbers](#where-did-corporate-pre-enrolled-devices-go) | |Groups by iOS Serial Number |Groups > All Devices > Corporate Pre-enrolled devices > By iOS Serial Number| [Device enrollment > Apple Enrollment > AC Serial numbers](#where-did-corporate-pre-enrolled-devices-go)| |Groups by IMEI (all platforms)| Groups > All Devices > Corporate Pre-enrolled devices > By IMEI (All platforms) | [Device enrollment > Corporate Device Identifiers](#by-imei-all-platforms)| | Corporate Device Enrollment profile| Policy > Corporate Device Enrollment | [Device enrollment > Apple Enrollment > Enrollment Program Profiles](#where-did-corporate-pre-enrolled-devices-go) | | Corporate Device Enrollment profile | Policy > Corporate Device Enrollment | [Device enrollment > Apple Enrollment > AC Profiles](#where-did-corporate-pre-enrolled-devices-go) | | Android for Work | Admin > Mobile Device Management > Android for Work | Device enrollment > Android for Work Enrollment | | Terms and Conditions | Policy > Terms and Conditions | Device enrollment > Terms and Conditions |</span></span>


## <span data-ttu-id="dd436-110">Onde gerencio grupos?</span><span class="sxs-lookup"><span data-stu-id="dd436-110">Where do I manage groups?</span></span>
<a id="where-do-i-manage-groups" class="xliff"></a>
<span data-ttu-id="dd436-111">Intune no Azure usa o [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) para gerenciar grupos.</span><span class="sxs-lookup"><span data-stu-id="dd436-111">Intune on Azure uses [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) to manage groups.</span></span>

## <span data-ttu-id="dd436-112">Para onde foram as regras de registro?</span><span class="sxs-lookup"><span data-stu-id="dd436-112">Where did enrollment rules go?</span></span>
<a id="where-did-enrollment-rules-go" class="xliff"></a>
<span data-ttu-id="dd436-113">No console clássico, você pode definir regras que regem o registro de MDM de dispositivos móveis e modernos com Windows e macOS:</span><span class="sxs-lookup"><span data-stu-id="dd436-113">In the classic console, you could set rules governing the MDM enrollment of mobile and modern Windows and macOS devices:</span></span>

![Imagem de regras de registro de dispositivo móvel clássico](./media/01-classic-rules.png)

<span data-ttu-id="dd436-115">Estas regras eram aplicadas a todos os usuários em sua conta do Intune, sem exceção.</span><span class="sxs-lookup"><span data-stu-id="dd436-115">These rules applied to all users in your Intune account without exception.</span></span> <span data-ttu-id="dd436-116">No portal Azure, estas regras agora são exibidas em dois diferentes tipos de políticas: restrições de tipo de dispositivo e restrições de limite do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="dd436-116">In the Azure portal these rules now appear in two distinct polices types: Device Type Restrictions and Device Limit Restrictions:</span></span>

![Imagem das restrições de registro de dispositivo móvel do Azure](./media/02-azure-enroll-restrictions.png)

<span data-ttu-id="dd436-118">A restrição de limite de dispositivo padrão corresponde ao limite de registro de dispositivo no console clássico:</span><span class="sxs-lookup"><span data-stu-id="dd436-118">The default Device Limit Restriction corresponds to the Device Enrollment Limit in the classic console:</span></span>

![Imagem das restrições de limite de dispositivo do Azure](./media/03-azure-device-limit.png)

<span data-ttu-id="dd436-120">A restrição de tipo de dispositivo padrão corresponde às restrições de plataforma no console clássico:</span><span class="sxs-lookup"><span data-stu-id="dd436-120">The default Device Type Restriction corresponds to the Platform Restrictions in the classic console:</span></span>

![Imagem das restrições de tipo de dispositivo do Azure](./media/04-azure-platform-restrictions.png)

<span data-ttu-id="dd436-122">A capacidade de permitir ou bloquear dispositivos de propriedade pessoal agora é gerenciada nas Configurações de plataforma da restrição do tipo de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="dd436-122">The ability to allow or block personally owned devices is now managed under the Device Type Restriction’s Platform Configurations:</span></span>

![Imagem das configurações de bloqueio de dispositivo pessoal do Azure](./media/05-azure-personal-block.png)

<span data-ttu-id="dd436-124">Novos recursos de restrição serão adicionados ao Portal do Azure apenas.</span><span class="sxs-lookup"><span data-stu-id="dd436-124">New restriction capabilities will be added to the Azure Portal only.</span></span>

## <span data-ttu-id="dd436-125">Para onde foi o Apple DEP?</span><span class="sxs-lookup"><span data-stu-id="dd436-125">Where did Apple DEP go?</span></span>
<a id="where-did-apple-dep-go" class="xliff"></a>
<span data-ttu-id="dd436-126">No console clássico, você podia configurar o Intune para integrar o programa de registro de dispositivo da Apple e solicitar manualmente a sincronização com o serviço da Apple:</span><span class="sxs-lookup"><span data-stu-id="dd436-126">In the classic console, you could set up Intune to integrate with Apple’s Device Enrollment Program and manually request synchronization with Apple’s service:</span></span>

![Imagem de token DEP clássico](./media/06-classic-dep-token.png)

<span data-ttu-id="dd436-128">No portal do Azure, você configura o programa de registro de dispositivo Apple com as mesmas etapas do Intune clássico:</span><span class="sxs-lookup"><span data-stu-id="dd436-128">In the Azure portal, you set up Apple Device Enrollment Program with the same steps as in Intune classic:</span></span>

![Imagem de token de DEP do Azure](./media/07-azure-dep-token.png)

<span data-ttu-id="dd436-130">No entanto, a opção de **sincronização** no console clássico foi movida para o fluxo de trabalho de gerenciamento do número de série, pois os resultados de uma sincronização manual aparecerão lá:</span><span class="sxs-lookup"><span data-stu-id="dd436-130">However the **Sync** option in the classic console has been moved to the serial number management workflow since the results of a manual sync will appear there:</span></span>

![Imagem da sincronização de DEP do Azure](./media/08-azure-dep-sync.png)

## <span data-ttu-id="dd436-132">Para onde foram os dispositivos corporativos pré-registrados?</span><span class="sxs-lookup"><span data-stu-id="dd436-132">Where did corporate pre-enrolled devices go?</span></span>
<a id="where-did-corporate-pre-enrolled-devices-go" class="xliff"></a>
### <span data-ttu-id="dd436-133">Por número de série do iOS</span><span class="sxs-lookup"><span data-stu-id="dd436-133">By iOS serial number</span></span>
<a id="by-ios-serial-number" class="xliff"></a>
<span data-ttu-id="dd436-134">No console clássico, você pode registrar dispositivos iOS por meio do programa de registro de dispositivo (DEP) da Apple e da ferramenta Apple Configurator.</span><span class="sxs-lookup"><span data-stu-id="dd436-134">In the classic console, you can enroll iOS devices through the Apple Device Enrollment Program (DEP) and the Apple Configurator tool.</span></span> <span data-ttu-id="dd436-135">Ambos os métodos oferecem pré-registro do dispositivo por número de série e envolvem a atribuição de perfis especiais de registro de dispositivo corporativo.</span><span class="sxs-lookup"><span data-stu-id="dd436-135">Both methods offer device pre-enrollment by serial number and involve the assignment of special Corporate Device Enrollment profiles.</span></span> <span data-ttu-id="dd436-136">Antes do registro, a atribuição de perfil de registro pode ser gerenciada por meio do **Dispositivo corporativo pré-registrado pelo grupo de dispositivos de número de série do iOS**:</span><span class="sxs-lookup"><span data-stu-id="dd436-136">Prior to enrollment, the enrollment profile assignment can be managed through the **Corporate Pre-enrolled Device by iOS Serial Number** device group:</span></span>

![Imagem de números de série da Apple clássicos](./media/09-classic-apple-serials.png)

<span data-ttu-id="dd436-138">Lista os números de série para o registro DEP e o Configurator da Apple em uma única lista.</span><span class="sxs-lookup"><span data-stu-id="dd436-138">This lists serial numbers for both Apple DEP and Configurator enrollment in a single list.</span></span> <span data-ttu-id="dd436-139">Para reduzir a incompatibilidade de atribuição do perfil (perfil DEP para o número de série de CA e vice-versa), dividimos os números de série em duas listas no portal do Azure:</span><span class="sxs-lookup"><span data-stu-id="dd436-139">To reduce profile assignment mis-match (DEP profile to AC serial number and vice-versa), we have separated the serial numbers into two lists in the Azure portal:</span></span>

<span data-ttu-id="dd436-140">**Números de série DEP**
![Imagem de números de série do Azure DEP](./media/10-azure-dep-serials.png)</span><span class="sxs-lookup"><span data-stu-id="dd436-140">**DEP serial numbers**
![Image of Azure DEP serial numbers](./media/10-azure-dep-serials.png)</span></span>

<span data-ttu-id="dd436-141">**Números de série do Apple Configurator**
![Imagem de números de série do Azure Apple Configurator](./media/11-azure-ac-serials.png)</span><span class="sxs-lookup"><span data-stu-id="dd436-141">**Apple Configurator serial numbers**
![Image of Azure Apple Configurator serial numbers](./media/11-azure-ac-serials.png)</span></span>

### <span data-ttu-id="dd436-142">Por IMEI (todas as plataformas)</span><span class="sxs-lookup"><span data-stu-id="dd436-142">By IMEI (all platforms)</span></span>
<a id="by-imei-all-platforms" class="xliff"></a>

<span data-ttu-id="dd436-143">No console clássico, você pode listar previamente os números IMEI de dispositivos para marcá-los como corporativos quando eles foram registrados no Intune:</span><span class="sxs-lookup"><span data-stu-id="dd436-143">In the classic console, you can pre-list the IMEI numbers of devices to mark them as corporate when they enrolled to Intune:</span></span>

![Imagem da lista clássica de números IMEI](./media/12-classic-corp-imei.png)

<span data-ttu-id="dd436-145">No console do Azure, você deve carregar o mesmo IMEI à lista de identificadores de dispositivo corporativo com um arquivo contendo valores separados por vírgulas (CSV).</span><span class="sxs-lookup"><span data-stu-id="dd436-145">In the Azure console, you must upload the same IMEI to the Corporate Device Identifiers list with a comma-separated-values (CSV) file.</span></span> <span data-ttu-id="dd436-146">O novo portal não oferecerá suporte à entrada manual de números IMEI:</span><span class="sxs-lookup"><span data-stu-id="dd436-146">The new portal will not support manual entry of IMEI numbers:</span></span>

![Imagem da lista de números IMEI do Azure](./media/13-azure-corp-imei.png)

<span data-ttu-id="dd436-148">Intune no portal do Azure está preparado para o futuro para dar suporte a outros tipos de identificadores além de IMEI, mas atualmente só permite números IMEI para pré-listagem.</span><span class="sxs-lookup"><span data-stu-id="dd436-148">Intune in the Azure portal is future-proofed to support other types of identifiers beside IMEI, but currently only allows IMEI numbers for pre-listing.</span></span>

## <span data-ttu-id="dd436-149">Para onde foram os perfis de registro de dispositivo corporativo?</span><span class="sxs-lookup"><span data-stu-id="dd436-149">Where did Corporate Device Enrollment profiles go?</span></span>
<a id="where-did-corporate-device-enrollment-profiles-go" class="xliff"></a>
<span data-ttu-id="dd436-150">Para registrar dispositivos iOS por meio do programa de registro de dispositivo Apple ou com a ferramenta Apple Configurator, você deve fornecer um perfil de registro de dispositivo corporativo para ser atribuído ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dd436-150">To enroll iOS devices through the Apple Device Enrollment Program or with the Apple Configurator tool, you must supply a Corporate Device Enrollment profile to be assigned the device.</span></span> <span data-ttu-id="dd436-151">No console clássico, a criação e o gerenciamento desses perfis estavam localizados em uma única lista:</span><span class="sxs-lookup"><span data-stu-id="dd436-151">In the classic console, the creation and management of these profiles was located in a single list:</span></span>

![Imagem de perfis de registro de dispositivo clássico](./media/14-classic-corp-profiles.png)

<span data-ttu-id="dd436-153">Esta lista mostra perfis habilitados para uso com o programa de registro de dispositivo Apple (**DEP On**) e perfil habilitado somente para uso com a ferramenta Apple Configurator (**DEP Off**).</span><span class="sxs-lookup"><span data-stu-id="dd436-153">This list shows profiles enabled for use with the Apple Device Enrollment Program (**DEP On**) and profile only enabled for use with the Apple Configurator tool (**DEP Off**).</span></span>

<span data-ttu-id="dd436-154">Para reduzir a confusão entre os dois tipos de perfil e potencias atribuições incorretas de correspondência (perfil DEP para dispositivos Configurator e vice-versa), separamos a criação e o gerenciamento de perfis de programa de registro (para dar suporte ao programa de registro de dispositivo Apple e Apple School Manager) e perfis do Apple Configurator:</span><span class="sxs-lookup"><span data-stu-id="dd436-154">To reduce confusion between the two profile types and potential mis-matched assignments (DEP profile to Configurator devices and vice-versa), we have separated creation and management of Enrollment Program profiles (support both Apples Device Enrollment Program and Apple School Manager) and Apple Configurator profiles:</span></span>

<span data-ttu-id="dd436-155">**Perfis DEP**
![Imagem de perfis do Azure DEP](./media/15-azure-dep-profiles.png)</span><span class="sxs-lookup"><span data-stu-id="dd436-155">**DEP profiles**
![Image of Azure DEP profiles](./media/15-azure-dep-profiles.png)</span></span>

<span data-ttu-id="dd436-156">**Perfis do Apple Configurator**
![Imagem de perfis do Azure Apple Configurator](./media/16-azure-ac-profiles.png)</span><span class="sxs-lookup"><span data-stu-id="dd436-156">**Apple Configurator profiles**
![Image of Azure Apple Configurator profiles](./media/16-azure-ac-profiles.png)</span></span>
