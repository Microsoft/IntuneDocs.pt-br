---
title: "Proteger dados de aplicativos usando políticas de MAM"
description: "Este tópico explica como as políticas de gerenciamento de aplicativo móvel podem ajudar a proteger os dados da empresa, evitar perda de dados e manter as informações pessoais e de trabalho separadas."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 40a6badf072c254f635a2656189d626e4f13a320
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="d5069-103">Proteger dados de aplicativo usando políticas de proteção de aplicativo com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d5069-103">Protect app data using app protection policies with Microsoft Intune</span></span>
<a id="protect-app-data-using-app-protection-policies-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <span data-ttu-id="d5069-104">Como proteger os dados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d5069-104">How you can protect app data</span></span>
<a id="how-you-can-protect-app-data" class="xliff"></a>
<span data-ttu-id="d5069-105">Os funcionários usam dispositivos móveis para tarefas de pessoais e corporativas.</span><span class="sxs-lookup"><span data-stu-id="d5069-105">Your employees use mobile devices for both personal and work tasks.</span></span> <span data-ttu-id="d5069-106">Embora seja necessário verificar se seus funcionários estão produtivos, você também deseja evitar a perda de dados, intencional ou acidental.</span><span class="sxs-lookup"><span data-stu-id="d5069-106">While you're making sure your employees can be productive, you also want to prevent data loss—intentional and unintentional.</span></span>  <span data-ttu-id="d5069-107">Além disso, você deseja ter a capacidade de proteger os dados corporativos que os funcionários acessam usando dispositivos não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="d5069-107">In addition, you want to have the ability to protect company data that employees access by using devices that you don't manage.</span></span>

<span data-ttu-id="d5069-108">Você pode usar as políticas de proteção de aplicativo do Intune para ajudar a proteger os dados da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="d5069-108">You can use Intune app protection policies to help protect your company’s data.</span></span> <span data-ttu-id="d5069-109">Como as políticas de proteção de aplicativo do Intune podem ser usadas **independentemente de qualquer solução de MDM (gerenciamento de dispositivo móvel)**, você pode usá-las para proteger os dados da sua empresa registrando ou não os dispositivos em uma solução de gerenciamento de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5069-109">Because Intune App protection policies can be used **independent of any mobile device management (MDM) solution**, you can use MAM to protect your company’s data with or without enrolling devices in a device management solution.</span></span> <span data-ttu-id="d5069-110">Implementando as **políticas de nível de aplicativo**, você pode restringir o acesso aos recursos da empresa e manter os dados dentro do alcance do seu departamento de TI.</span><span class="sxs-lookup"><span data-stu-id="d5069-110">By implementing **app-level policies**, you can restrict access to company resources and keep data within the purview of your IT department.</span></span>

<span data-ttu-id="d5069-111">É possível configurar as políticas de proteção de aplicativo para aplicativos em execução em dispositivos que são:</span><span class="sxs-lookup"><span data-stu-id="d5069-111">You can configure app protection policies for apps running on devices that are:</span></span>

-   <span data-ttu-id="d5069-112">**Registrados com o Microsoft Intune:** os dispositivos dessa categoria normalmente são dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="d5069-112">**Enrolled in Microsoft Intune:** The devices in this category are typically corporate-owned devices.</span></span>

-   <span data-ttu-id="d5069-113">**Registrados em uma solução de terceiros de MDM:** os dispositivos dessa categoria normalmente são dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="d5069-113">**Enrolled in a third-party MDM solution:** The devices in this category are typically corporate-owned devices.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d5069-114">Não recomendamos usar políticas de proteção de aplicativo com soluções de contêiner seguro ou gerenciamento de aplicativos móveis de terceiros.</span><span class="sxs-lookup"><span data-stu-id="d5069-114">We don't recommend using app protection policies with third-party mobile application management or secure container solutions.</span></span>

-   <span data-ttu-id="d5069-115">**Não registrados em nenhuma solução de MDM:** os dispositivos dessa categoria normalmente são dispositivos de funcionários que não são gerenciados ou registrados no Intune ou outras soluções de MDM.</span><span class="sxs-lookup"><span data-stu-id="d5069-115">**Not enrolled in any MDM solution:** The devices in this category are typically employee-owned devices that are not managed or enrolled in Intune or other MDM solutions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5069-116">Você pode criar políticas de proteção de aplicativo para aplicativos móveis do Office que se conectam aos serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5069-116">You can create app protection policies for Office mobile apps that connect to Office 365 services.</span></span> <span data-ttu-id="d5069-117">As políticas de proteção de aplicativo não têm suporte em aplicativos que se conectam aos serviços do Exchange, Skype for Business ou SharePoint local.</span><span class="sxs-lookup"><span data-stu-id="d5069-117">App protection policies are not supported for apps that connect to on-premises Exchange, Skype for Business, or SharePoint services.</span></span>

## <span data-ttu-id="d5069-118">Benefícios do uso de políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="d5069-118">Benefits of using app protection policies</span></span>
<a id="benefits-of-using-app-protection-policies" class="xliff"></a>

-   <span data-ttu-id="d5069-119">**Elas ajudam a proteger os dados da empresa no nível do aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="d5069-119">**They help protect your company data at the app level.**</span></span> <span data-ttu-id="d5069-120">Como o gerenciamento de aplicativos móveis não requer gerenciamento de dispositivos, é possível proteger os dados da empresa em dispositivos gerenciados e não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="d5069-120">Because mobile application management doesn't require device management, you can protect company data on both managed and unmanaged devices.</span></span> <span data-ttu-id="d5069-121">O gerenciamento concentra-se na identidade do usuário, o que elimina a necessidade de gerenciar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d5069-121">The management is centered on the user identity, which removes the requirement for device management.</span></span>

-   <span data-ttu-id="d5069-122">**A produtividade do usuário não é afetada e as políticas não são aplicadas quando ao usar o aplicativo em um contexto pessoal.**</span><span class="sxs-lookup"><span data-stu-id="d5069-122">**User productivity is not impacted, and the policies aren't applied when you're using the app in a personal context.**</span></span> <span data-ttu-id="d5069-123">As políticas são aplicadas somente em um contexto corporativo, que proporciona a capacidade de proteger dados da empresa sem tocar em dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="d5069-123">The policies are applied only in a work context, which gives you the ability to protect company data without touching personal data.</span></span>

<span data-ttu-id="d5069-124">Há benefícios adicionais em usar MDM com políticas de proteção de aplicativo e as empresas podem usar MAM com e sem MDM ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="d5069-124">There are additional benefits to using MDM with app protection policies, and companies can use MAM with and without MDM at the same time.</span></span> <span data-ttu-id="d5069-125">Por exemplo, um funcionário pode usar um telefone da empresa e um tablet particular.</span><span class="sxs-lookup"><span data-stu-id="d5069-125">For example, an employee might use a company-issued phone, as well as a personal tablet.</span></span> <span data-ttu-id="d5069-126">Nesse caso, o telefone da empresa é registrado no MDM e protegido pelas políticas de proteção de aplicativo e o dispositivo pessoal é protegido somente pelas políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d5069-126">In this case, the company phone is enrolled in MDM and protected by app protection policies, and the personal device is protected by app protection policies only.</span></span>

- <span data-ttu-id="d5069-127">**O MDM garante que o dispositivo estará protegido.**</span><span class="sxs-lookup"><span data-stu-id="d5069-127">**MDM makes sure that the device is protected.**</span></span> <span data-ttu-id="d5069-128">Por exemplo, você pode exigir um PIN acessar o dispositivo ou pode implantar aplicativos gerenciados para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5069-128">For example, you can require a PIN to access the device, or you can deploy managed apps to the device.</span></span> <span data-ttu-id="d5069-129">Também é possível implantar aplicativos em dispositivos por meio da solução MDM, para ter mais controle sobre o gerenciamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d5069-129">You can also deploy apps to devices through your MDM solution to give you more control over app management.</span></span>

- <span data-ttu-id="d5069-130">**Políticas de proteção de aplicativo garantem que as proteções de camada de aplicativo estejam em vigor.**</span><span class="sxs-lookup"><span data-stu-id="d5069-130">**App protection policies make sure that the app-layer protections are in place.**</span></span> <span data-ttu-id="d5069-131">Por exemplo, é possível ter uma política que exige um PIN para abrir um aplicativo em um contexto corporativo, impedir dados de serem compartilhados entre aplicativos e impedir que os dados de aplicativo da empresa sejam salvos em um local de armazenamento pessoal.</span><span class="sxs-lookup"><span data-stu-id="d5069-131">For example, you can have a policy that requires a PIN to open an app in a work context, prevents data from being shared between apps, and prevents company app data from being saved to a personal storage location.</span></span>

## <span data-ttu-id="d5069-132">Dispositivos em que há suporte para MAM</span><span class="sxs-lookup"><span data-stu-id="d5069-132">Devices that support MAM</span></span>
<a id="devices-that-support-mam" class="xliff"></a>
<span data-ttu-id="d5069-133">Atualmente, há suporte para políticas de proteção de aplicativo em:</span><span class="sxs-lookup"><span data-stu-id="d5069-133">App protection policies are currently supported on:</span></span>
-   <span data-ttu-id="d5069-134">iOS 8.1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="d5069-134">iOS 8.1 or later</span></span>
-   <span data-ttu-id="d5069-135">Android 4 ou posterior</span><span class="sxs-lookup"><span data-stu-id="d5069-135">Android 4 or later</span></span>

>[!NOTE]
><span data-ttu-id="d5069-136">Os dispositivos Windows não são compatíveis com o MAM sem um cenário de registro.</span><span class="sxs-lookup"><span data-stu-id="d5069-136">Windows devices are not supported in the MAM without enrollment scenario.</span></span> <span data-ttu-id="d5069-137">No entanto, quando registra dispositivos Windows 10 no Intune, você pode usar a Proteção de Informações do Windows, que oferece funcionalidades semelhantes.</span><span class="sxs-lookup"><span data-stu-id="d5069-137">However, when you enroll Windows 10 devices with Intune, you can use Windows Information Protection, which offers similar functionality.</span></span> <span data-ttu-id="d5069-138">Para obter detalhes, consulte [Proteger seus dados empresariais usando a WIP (Proteção de Informações do Windows)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="d5069-138">For details, see [Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span></span>


##  <span data-ttu-id="d5069-139">Como as políticas de proteção de aplicativo protegem dados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d5069-139">How app protection policies protect app data</span></span>
<a id="how-app-protection-policies-protect-app-data" class="xliff"></a>

###  <span data-ttu-id="d5069-140">Aplicativos sem políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="d5069-140">Apps without app protection policies</span></span>
<a id="apps-without-app-protection-policies" class="xliff"></a>

![Imagem que mostra como os dados pode ser movidos livremente entre aplicativos quando não há nenhuma política de proteção de aplicativo em vigor](../media/Apps_without_MAM_policies.png)

<span data-ttu-id="d5069-142">Ao usar aplicativos sem restrições, os dados corporativos e pessoais podem se misturar.</span><span class="sxs-lookup"><span data-stu-id="d5069-142">When you use apps without restrictions, company and personal data can get intermingled.</span></span> <span data-ttu-id="d5069-143">Os dados corporativos podem acabar em locais como um armazenamento pessoal ou serem transferidos para aplicativos fora do seu alcance, resultando na perda de dados.</span><span class="sxs-lookup"><span data-stu-id="d5069-143">Company data might end up in locations like personal storage or might be transferred to apps outside of your purview, which could result in data loss.</span></span> <span data-ttu-id="d5069-144">As setas no diagrama mostram a movimentação de dados irrestrita entre aplicativos (corporativos e pessoais) e locais de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="d5069-144">The arrows in the diagram show unrestricted data movement between apps (corporate and personal) and to storage locations.</span></span>

### <span data-ttu-id="d5069-145">Proteção de dados com as políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="d5069-145">Data protection with app protection policies</span></span>
<a id="data-protection-with-app-protection-policies" class="xliff"></a>

![A imagem que mostra como os dados da empresa são protegidos quando as políticas de proteção de aplicativo são aplicadas](../media/Apps_with_mobile_app_policies.png)

<span data-ttu-id="d5069-147">Você pode usar as políticas de proteção de aplicativo para impedir que os dados da empresa sejam salvos no armazenamento local do dispositivo, bem como restringir a movimentação de dados para outros aplicativos que não estão protegidos pelas políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d5069-147">You can use app protection policies to prevent company data from saving to the local storage of the device, and to restrict data movement to other apps that aren't protected by app protection policies.</span></span> <span data-ttu-id="d5069-148">As configurações de política de proteção de aplicativo incluem:</span><span class="sxs-lookup"><span data-stu-id="d5069-148">App protection policy settings include:</span></span>
- <span data-ttu-id="d5069-149">Políticas de realocação de dados como **Evitar Salvar Como** e **Restringir recortar, copiar e colar**.</span><span class="sxs-lookup"><span data-stu-id="d5069-149">Data relocation policies like **Prevent Save As** and **Restrict cut, copy, and paste**.</span></span>
- <span data-ttu-id="d5069-150">As configurações de política de acesso como **Exigir PIN simples para acesso** e **Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou raiz**.</span><span class="sxs-lookup"><span data-stu-id="d5069-150">Access policy settings like **Require simple PIN for access** and **Block managed apps from running on jailbroken or rooted devices**.</span></span>

### <span data-ttu-id="d5069-151">Proteção de dados com proteção de aplicativo em dispositivos gerenciados por uma solução de MDM</span><span class="sxs-lookup"><span data-stu-id="d5069-151">Data protection with app protection on devices that are managed by a MDM solution</span></span>
<a id="data-protection-with-app-protection-on-devices-that-are-managed-by-a-mdm-solution" class="xliff"></a>

![Imagem que mostra como as políticas de proteção de aplicativo funcionam em dispositivos BYOD (Bring Your Own Devices, tragam seus próprios dispositivos)](../media/MAM_BYOD_November.png)

<span data-ttu-id="d5069-153">**Para dispositivos registrados em uma solução MDM**: o diagrama anterior mostra as camadas de proteção que as políticas MDM e de proteção de aplicativo oferecem juntas.</span><span class="sxs-lookup"><span data-stu-id="d5069-153">**For devices enrolled in an MDM solution**: The preceding diagram shows the layers of protection that MDM and app protection policies offer together.</span></span>

<span data-ttu-id="d5069-154">A solução MDM:</span><span class="sxs-lookup"><span data-stu-id="d5069-154">The MDM solution:</span></span>

-   <span data-ttu-id="d5069-155">Registra o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5069-155">Enrolls the device.</span></span>

-   <span data-ttu-id="d5069-156">Implanta aplicativos no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5069-156">Deploys apps to the device.</span></span>

-   <span data-ttu-id="d5069-157">Fornece gerenciamento e a conformidade contínuos no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5069-157">Provides ongoing device compliance and management.</span></span>

<span data-ttu-id="d5069-158">**Políticas de proteção de aplicativo agregam valor porque:**</span><span class="sxs-lookup"><span data-stu-id="d5069-158">**App protection policies add value because they:**</span></span>

-   <span data-ttu-id="d5069-159">Ajudam a proteger os dados da empresa contra vazamento de serviços e aplicativos de consumidor.</span><span class="sxs-lookup"><span data-stu-id="d5069-159">Help protect company data from leaking to consumer apps and services.</span></span>

-   <span data-ttu-id="d5069-160">Aplicam restrições (salvar como, área de transferência, PIN etc.) aos aplicativos móveis.</span><span class="sxs-lookup"><span data-stu-id="d5069-160">Apply restrictions (save-as, clipboard, PIN, etc.) to mobile apps.</span></span>

-   <span data-ttu-id="d5069-161">Apagam os dados da empresa dos aplicativos sem removê-los do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5069-161">Wipe company data from apps without removing those apps from the device.</span></span>


### <span data-ttu-id="d5069-162">Proteção de dados com políticas de proteção de aplicativo para dispositivos sem registro</span><span class="sxs-lookup"><span data-stu-id="d5069-162">Data protection with app protection policies for devices without enrollment</span></span>
<a id="data-protection-with-app-protection-policies-for-devices-without-enrollment" class="xliff"></a>

![A imagem que mostra como as políticas de proteção de aplicativo funcionam em dispositivos gerenciados](../media/MAM_ManagedDevices_November.png)

<span data-ttu-id="d5069-164">O diagrama anterior ilustra como as políticas de proteção de dados funcionam no nível do aplicativo sem MDM.</span><span class="sxs-lookup"><span data-stu-id="d5069-164">The preceding diagram illustrates how data protection policies work at the app level without MDM.</span></span>

<span data-ttu-id="d5069-165">Para dispositivos BYOD não registrados em nenhuma solução MDM, as políticas de proteção de aplicativo podem ajudar a proteger os dados da empresa no nível do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d5069-165">For BYOD devices that aren't enrolled in any MDM solution, app protection policies can help protect company data at the app level.</span></span>

<span data-ttu-id="d5069-166">Contudo, existem algumas limitações a serem consideradas:</span><span class="sxs-lookup"><span data-stu-id="d5069-166">However, there are some limitations to be aware of:</span></span>

-   <span data-ttu-id="d5069-167">Não é possível implantar aplicativos no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5069-167">You can't deploy apps to the device.</span></span> <span data-ttu-id="d5069-168">O usuário precisa obter os aplicativos na loja.</span><span class="sxs-lookup"><span data-stu-id="d5069-168">The user has to get the apps from the store.</span></span>

-   <span data-ttu-id="d5069-169">Não é possível provisionar perfis de certificado nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d5069-169">You can't provision certificate profiles on these devices.</span></span>

-   <span data-ttu-id="d5069-170">Não é possível configurar as configurações de Wi-Fi e VPN da empresa nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d5069-170">You can't set up company Wi-Fi and VPN settings on these devices.</span></span>


## <span data-ttu-id="d5069-171">Várias identidades</span><span class="sxs-lookup"><span data-stu-id="d5069-171">Multi-identity</span></span>
<a id="multi-identity" class="xliff"></a>

<span data-ttu-id="d5069-172">Aplicativos que dão suporte a várias identidades permitem usar contas diferentes (pessoal e corporativa) para acessar os mesmos aplicativos quando políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d5069-172">Apps that support multi-identity let you use different accounts (work and personal) to access the same apps, while app protection policies are applied only when the apps are used in the work context.</span></span>  

<span data-ttu-id="d5069-173">Por exemplo, quando o usuário inicia o aplicativo OneDrive usando sua conta de trabalho, ele não pode mover os arquivos para um local de armazenamento pessoal.</span><span class="sxs-lookup"><span data-stu-id="d5069-173">For example, when a user starts the OneDrive app by using their work account, they can't move the files to a personal storage location.</span></span> <span data-ttu-id="d5069-174">No entanto, quando ele usa o OneDrive com sua conta pessoal, ele pode copiar e mover dados do seu OneDrive pessoal sem restrições.</span><span class="sxs-lookup"><span data-stu-id="d5069-174">However, when they use OneDrive with their personal account, they can copy and move data from their personal OneDrive without restrictions.</span></span>  

- <span data-ttu-id="d5069-175">Saiba mais sobre os aplicativos que oferecem suporte a [MAM e várias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) com o Intune.</span><span class="sxs-lookup"><span data-stu-id="d5069-175">Learn more about the apps that support [MAM and multi-identity](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) with Intune.</span></span>

##  <span data-ttu-id="d5069-176">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d5069-176">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
- [<span data-ttu-id="d5069-177">Prepare-se para configurar as políticas de proteção do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d5069-177">Get ready to configure app protection policies</span></span>](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [<span data-ttu-id="d5069-178">Criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d5069-178">Create and deploy app protection policies with Microsoft Intune</span></span>](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
