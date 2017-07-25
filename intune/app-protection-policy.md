---
title: "O que são políticas de proteção do aplicativo"
titleSuffix: Intune on Azure
description: "Use este tópico para saber como proteger os dados da empresa com as políticas de Proteção de Aplicativo do Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 13b3199108c34a61d117e4d89d118bdd05d7d20f
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <span data-ttu-id="ac241-103">O que são políticas de proteção de aplicativo?</span><span class="sxs-lookup"><span data-stu-id="ac241-103">What are app protection policies?</span></span>
<a id="what-are-app-protection-policies" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="ac241-104">As políticas de proteção de aplicativo do Microsoft Intune ajudam a proteger os dados da empresa e evitar a perda de dados.</span><span class="sxs-lookup"><span data-stu-id="ac241-104">Microsoft Intune app protection policies help protect your company data and prevent data loss.</span></span>

## <span data-ttu-id="ac241-105">Como proteger os dados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="ac241-105">How you can protect app data</span></span>
<a id="how-you-can-protect-app-data" class="xliff"></a>
<span data-ttu-id="ac241-106">Os funcionários usam dispositivos móveis para tarefas de pessoais e corporativas.</span><span class="sxs-lookup"><span data-stu-id="ac241-106">Your employees use mobile devices for both personal and work tasks.</span></span>  <span data-ttu-id="ac241-107">Embora seja necessário certificar-se que seus funcionários sejam produtivos, você também deseja evitar a perda de dados, intencional ou acidental.</span><span class="sxs-lookup"><span data-stu-id="ac241-107">While making sure your employees can be productive, you also want to prevent data loss, intentional and unintentional.</span></span>  <span data-ttu-id="ac241-108">Além disso, é útil ter a capacidade de proteger os dados corporativos acessados usando dispositivos mesmo caso eles não sejam gerenciados por você.</span><span class="sxs-lookup"><span data-stu-id="ac241-108">In addition, you want to have the ability to protect company data accessed using devices even in the case where they are not managed by you.</span></span>

<span data-ttu-id="ac241-109">Você pode usar as políticas de proteção de aplicativo do Intune para ajudar a proteger os dados da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ac241-109">You can use Intune  app protection policies to help protect your company’s data.</span></span> <span data-ttu-id="ac241-110">Como as políticas de proteção de aplicativo do Intune podem ser usadas **independentemente de qualquer solução de MDM (gerenciamento de dispositivo móvel)**, você pode usá-las para proteger os dados da sua empresa registrando ou não os dispositivos em uma solução de gerenciamento de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac241-110">Because Intune app protection policies can be used **independent of any mobile-device management (MDM) solution**, you can use it to protect your company’s data with or without enrolling devices in a device management solution.</span></span> <span data-ttu-id="ac241-111">Implementando as **políticas de nível de aplicativo**, você pode restringir o acesso aos recursos da empresa e manter os dados dentro do alcance do seu departamento de TI.</span><span class="sxs-lookup"><span data-stu-id="ac241-111">By implementing **app-level policies**, you can restrict access to company resources and keep data within the purview of your IT department.</span></span>

<span data-ttu-id="ac241-112">As políticas de proteção de aplicativo podem ser configuradas para aplicativos em execução em dispositivos que são:</span><span class="sxs-lookup"><span data-stu-id="ac241-112">App protection policies can be configured for app running on devices that are:</span></span>

- <span data-ttu-id="ac241-113">**Registrados com o Microsoft Intune:** os dispositivos nessa categoria normalmente são dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="ac241-113">**Enrolled in Microsoft Intune:** The devices in this category are typically corporate owned devices.</span></span>

-   <span data-ttu-id="ac241-114">**Registrados em uma solução de MDM (gerenciamento de dispositivo móvel) de terceiros:** os dispositivos nessa categoria normalmente são dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="ac241-114">**Enrolled in a third-party Mobile device management (MDM)  solution:**   The devices in this category are typically corporate owned devices.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ac241-115">Políticas de gerenciamento de aplicativo móvel não devem ser usadas com o gerenciamento de aplicativos móveis de terceiros ou com soluções seguras de contêiner.</span><span class="sxs-lookup"><span data-stu-id="ac241-115">Mobile app management policies should not be used with third party mobile app management  or secure container solutions.</span></span>

-   <span data-ttu-id="ac241-116">**Não registrados em nenhuma solução de gerenciamento de dispositivo móvel:** os dispositivos nessa categoria normalmente são dispositivos de funcionários que não são gerenciados ou registrados no Intune ou outras soluções de MDM.</span><span class="sxs-lookup"><span data-stu-id="ac241-116">**Not enrolled in any mobile device management solution:**  The devices in this category are typically employee owned devices that are not managed or enrolled in Intune or other MDM solutions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac241-117">Você pode criar políticas de gerenciamento para aplicativos móveis do Office que se conectam aos serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac241-117">You can create mobile app management policies for Office mobile apps that connect to Office 365 services.</span></span> <span data-ttu-id="ac241-118">As políticas de proteção de aplicativo não têm suporte em aplicativos que se conectam aos serviços do Exchange, Skype for Business ou SharePoint local.</span><span class="sxs-lookup"><span data-stu-id="ac241-118">App protection policies are not supported for apps that connect to on-premises Exchange, Skype for Business, or SharePoint services.</span></span>

<span data-ttu-id="ac241-119">**Os principais benefícios do uso de políticas de proteção de aplicativo são**</span><span class="sxs-lookup"><span data-stu-id="ac241-119">**The important benefits of using App protection policies are**</span></span>

-   <span data-ttu-id="ac241-120">Proteger os dados da empresa no nível do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ac241-120">Protecting your company data at the app level.</span></span>  <span data-ttu-id="ac241-121">Como o gerenciamento de aplicativos móveis não requer gerenciamento de dispositivos, você pode proteger os dados da empresa em dispositivos gerenciados e não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="ac241-121">Since mobile app management does not require device management, you can protect company data on both managed and unmanaged devices.</span></span> <span data-ttu-id="ac241-122">O gerenciamento concentra-se na identidade do usuário, o que elimina a necessidade de gerenciar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ac241-122">The management is centered on the user identity, which removes the requirement for device management.</span></span>

-   <span data-ttu-id="ac241-123">A produtividade do usuário final não é afetada e as políticas não são aplicadas ao usar o aplicativo em um contexto pessoal.</span><span class="sxs-lookup"><span data-stu-id="ac241-123">End user productivity is not impacted, and the policies are not applied when using the app in a personal context.</span></span>  <span data-ttu-id="ac241-124">As políticas são aplicadas somente em um contexto corporativo, proporcionando assim a capacidade de proteger dados da empresa sem tocar em dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="ac241-124">The policies are applied only in a work context, thus giving you the ability to protect company data without touching personal data.</span></span>

<span data-ttu-id="ac241-125">Há benefícios adicionais em usar MDM com políticas de proteção de aplicativo, e as empresas podem usar ambos (políticas de proteção de aplicativo com e sem MDM) ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ac241-125">There are additional benefits to using MDM with App protection  policies, and companies can use both App protection policies with and without MDM at the same time.</span></span> <span data-ttu-id="ac241-126">Por exemplo, um funcionário pode usar um telefone da empresa e um tablet particular.</span><span class="sxs-lookup"><span data-stu-id="ac241-126">For example, an employee may use a phone issued by the company as well as a personal tablet.</span></span>  <span data-ttu-id="ac241-127">Nesse caso, o telefone da empresa é registrado no MDM e protegido pelas políticas de proteção de aplicativo e o dispositivo pessoal é protegido somente pelas políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ac241-127">In this case, the company phone is enrolled in MDM and protected by App protection policies, and the personal device is protected by App protection policies only.</span></span>

- <span data-ttu-id="ac241-128">**O MDM garante que o dispositivo estará protegido**.</span><span class="sxs-lookup"><span data-stu-id="ac241-128">**MDM makes sure that the device is protected**.</span></span>  <span data-ttu-id="ac241-129">Por exemplo, você pode exigir um PIN acessar o dispositivo ou pode implantar aplicativos gerenciados para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac241-129">For example, you can require a PIN to access the device, or you can deploy managed apps to the device.</span></span> <span data-ttu-id="ac241-130">Você também pode implantar aplicativos em dispositivos por meio da solução MDM, para conferir mais controle sobre o gerenciamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ac241-130">You can also deploy apps to devices through your MDM solution, to give you more control over app management.</span></span>

- <span data-ttu-id="ac241-131">**Políticas de proteção de aplicativo garantem que as proteções de camada de aplicativo estejam em vigor**.</span><span class="sxs-lookup"><span data-stu-id="ac241-131">**App protection policies makes sure that the app-layer protections are in place**.</span></span> <span data-ttu-id="ac241-132">Por exemplo, você pode exigir um PIN abrir um aplicativo em um contexto corporativo, se os dados puderem ser compartilhados entre aplicativos ou impedindo que os dados de aplicativo da empresa sejam salvos em um local de armazenamento pessoal.</span><span class="sxs-lookup"><span data-stu-id="ac241-132">For example, you can require a PIN to open an app in a work context, or if data can be shared between apps, or preventing company app data from being saved to a personal storage location.</span></span>


### <span data-ttu-id="ac241-133">Plataformas com suporte para as políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="ac241-133">Supported platforms for app protection polices</span></span>
<a id="supported-platforms-for-app-protection-polices" class="xliff"></a>
-   <span data-ttu-id="ac241-134">iOS 8.1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="ac241-134">iOS 8.1 or later</span></span>

-   <span data-ttu-id="ac241-135">Android 4 ou posterior</span><span class="sxs-lookup"><span data-stu-id="ac241-135">Android 4 or later</span></span>

<span data-ttu-id="ac241-136">Não há suporte para dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="ac241-136">Windows devices are currently not supported.</span></span> <span data-ttu-id="ac241-137">No entanto, quando registra dispositivos Windows 10 no Intune, você pode usar a Proteção de Informações do Windows, que oferece funcionalidades semelhantes.</span><span class="sxs-lookup"><span data-stu-id="ac241-137">However, when you enroll Windows 10 devices with Intune, you can use Windows Information Protection, which offers similar functionality.</span></span> <span data-ttu-id="ac241-138">Para obter detalhes, consulte [Proteger seus dados empresariais usando a WIP (Proteção de Informações do Windows)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="ac241-138">For details, see [Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span></span>
##  <span data-ttu-id="ac241-139">Como as políticas de proteção de aplicativo protegem dados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="ac241-139">How app protection policies protect app data</span></span>
<a id="how-app-protection-policies-protect-app-data" class="xliff"></a>

####  <span data-ttu-id="ac241-140">Aplicativos sem políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="ac241-140">Apps without app protection policies</span></span>
<a id="apps-without-app-protection-policies" class="xliff"></a>

![Imagem que mostra que os dados pode ser movidos livremente entre aplicativos quando não há nenhuma política de proteção de aplicativo em vigor](./media/apps-without-protection-policies.png)

<span data-ttu-id="ac241-142">Quando os aplicativos são usados sem restrições, os dados corporativos e pessoais podem se misturar.</span><span class="sxs-lookup"><span data-stu-id="ac241-142">When apps are used without restrictions, company and personal data can get intermingled.</span></span>  <span data-ttu-id="ac241-143">Os dados corporativos poderiam acabar em locais como um armazenamento pessoal ou transferidos para aplicativos fora do seu alcance, resultando na perda de dados.</span><span class="sxs-lookup"><span data-stu-id="ac241-143">Company data could end up in locations like personal storage or transferred to apps outside of your  purview,  resulting in data loss.</span></span> <span data-ttu-id="ac241-144">As setas no diagrama mostram a movimentação de dados irrestrita entre aplicativos (corporativos e pessoais) e locais de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="ac241-144">The arrows in the diagram show unrestricted data movement between apps (corporate and personal) and to storage locations.</span></span>

### <span data-ttu-id="ac241-145">Proteção de dados com as políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="ac241-145">Data protection with app protection policies</span></span>
<a id="data-protection-with-app-protection-policies" class="xliff"></a>

![<span data-ttu-id="ac241-146">A imagem que mostra como os dados da empresa são protegidos quando as políticas de proteção de aplicativo são aplicadas</span><span class="sxs-lookup"><span data-stu-id="ac241-146">Image that shows how company data is protect when App protection policies are applied</span></span> ](./media/apps-with-protection-policies.png)


<span data-ttu-id="ac241-147">Você pode usar as políticas de proteção de aplicativo para impedir que os dados da empresa sejam salvos no armazenamento local do dispositivo, bem como restringir a movimentação de dados para outros aplicativos que não estão protegidos pelas políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ac241-147">You can use App protection policies to prevent company data from saving to the local storage of the device, and restrict data movement to other apps that are not protected by App protection policies.</span></span> <span data-ttu-id="ac241-148">As configurações de política de proteção de aplicativo incluem:</span><span class="sxs-lookup"><span data-stu-id="ac241-148">App protection policy settings include:</span></span>
- <span data-ttu-id="ac241-149">Políticas de realocação de dados como **Evitar Salvar como**, **Restringir recortar, copiar e colar**.</span><span class="sxs-lookup"><span data-stu-id="ac241-149">Data relocation policies like **Prevent Save As**, **Restrict cut, copy, and paste**.</span></span>
- <span data-ttu-id="ac241-150">Configurações de política de acesso como **Exigir PIN simples para acesso**, **Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou raiz**.</span><span class="sxs-lookup"><span data-stu-id="ac241-150">Access policy settings like **Require simple PIN for access**, **Block managed apps from running on jailbroken or rooted devices**.</span></span>

### <span data-ttu-id="ac241-151">Proteção de dados com políticas de proteção de aplicativo nos dispositivos gerenciados por uma solução de MDM</span><span class="sxs-lookup"><span data-stu-id="ac241-151">Data protection with app protection policies on devices managed by a MDM solution</span></span>
<a id="data-protection-with-app-protection-policies-on-devices-managed-by-a-mdm-solution" class="xliff"></a>

![A imagem que mostra como as políticas de proteção de aplicativo funcionam em dispositivos BYOD](./media/app-protection-policies-with-mdm.png)

<span data-ttu-id="ac241-153">**Para dispositivos registrados em uma solução de MDM**-</span><span class="sxs-lookup"><span data-stu-id="ac241-153">**For devices enrolled in an MDM solution**-</span></span>

<span data-ttu-id="ac241-154">A ilustração acima mostra as camadas de proteção que as políticas de MDM e proteção de aplicativo oferecem juntas.</span><span class="sxs-lookup"><span data-stu-id="ac241-154">The illustration above shows the layers of protection that MDM and App protection policies offer together.</span></span>

<span data-ttu-id="ac241-155">A solução MDM:</span><span class="sxs-lookup"><span data-stu-id="ac241-155">The MDM solution:</span></span>

-   <span data-ttu-id="ac241-156">Registra o dispositivo</span><span class="sxs-lookup"><span data-stu-id="ac241-156">Enrolls the device</span></span>

-   <span data-ttu-id="ac241-157">Implanta os aplicativos no dispositivo</span><span class="sxs-lookup"><span data-stu-id="ac241-157">Deploys the apps to the device</span></span>

-   <span data-ttu-id="ac241-158">Fornece gerenciamento e a conformidade contínuos no dispositivo</span><span class="sxs-lookup"><span data-stu-id="ac241-158">Provides ongoing device compliance and management</span></span>

<span data-ttu-id="ac241-159">**Políticas de proteção de aplicativo agregam valor da seguinte forma:**</span><span class="sxs-lookup"><span data-stu-id="ac241-159">**App protection policies add value by:**</span></span>

-   <span data-ttu-id="ac241-160">Ajudar a proteger os dados da empresa contra vazamento de serviços e aplicativos de consumidor</span><span class="sxs-lookup"><span data-stu-id="ac241-160">Helping protect  company data from leaking to consumer apps and services</span></span>

-   <span data-ttu-id="ac241-161">Aplicar restrições (salvar como, área de transferência, PIN, etc.) aos aplicativos móveis</span><span class="sxs-lookup"><span data-stu-id="ac241-161">Applying restrictions (save-as, clipboard, PIN, etc.) to mobile apps</span></span>

-   <span data-ttu-id="ac241-162">Apagar os dados da empresa dos aplicativos sem remover esses aplicativos do dispositivo</span><span class="sxs-lookup"><span data-stu-id="ac241-162">Wipe company data from apps without removing those apps from the device</span></span>


### <span data-ttu-id="ac241-163">Proteção de dados com políticas de proteção de aplicativo para dispositivos sem registro</span><span class="sxs-lookup"><span data-stu-id="ac241-163">Data protection with app protection policies for devices without enrollment</span></span>
<a id="data-protection-with-app-protection-policies-for-devices-without-enrollment" class="xliff"></a>

![A imagem que mostra como as políticas de proteção de aplicativo funcionam em dispositivos gerenciados](./media/app-protection-policies-without-mdm.png)

<span data-ttu-id="ac241-165">O diagrama acima ilustra como as políticas de proteção de dados funcionam no nível do aplicativo sem MDM.</span><span class="sxs-lookup"><span data-stu-id="ac241-165">The diagram above illustrates how the data protection policies work at the app level without MDM.</span></span>

<span data-ttu-id="ac241-166">Para dispositivos BYOD não registrados em nenhuma solução MDM, as políticas de proteção de aplicativo podem ajudar a proteger os dados da empresa no nível do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ac241-166">For BYOD devices not enrolled in any MDM solution, App protection policies can help protect company data at the app level.</span></span>
<span data-ttu-id="ac241-167">Contudo, existem algumas limitações a serem consideradas, como:</span><span class="sxs-lookup"><span data-stu-id="ac241-167">However, there are some limitations to be aware of, like:</span></span>

-   <span data-ttu-id="ac241-168">Você não pode implantar aplicativos no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ac241-168">You cannot deploy apps to the device.</span></span>  <span data-ttu-id="ac241-169">O usuário final precisa obter os aplicativos na loja.</span><span class="sxs-lookup"><span data-stu-id="ac241-169">The end user has to get the apps from the store.</span></span>

-   <span data-ttu-id="ac241-170">Não é possível provisionar perfis de certificado nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ac241-170">You cannot provision certificate profiles on these devices.</span></span>

-   <span data-ttu-id="ac241-171">Não é possível provisionar as configurações de Wi-Fi e VPN da empresa nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ac241-171">You cannot provision company Wi-Fi and VPN settings on these devices.</span></span>


## <span data-ttu-id="ac241-172">Várias identidades</span><span class="sxs-lookup"><span data-stu-id="ac241-172">Multi-identity</span></span>
<a id="multi-identity" class="xliff"></a>

<span data-ttu-id="ac241-173">Aplicativos que dão suporte a várias identidades permitem usar contas diferentes (pessoal e corporativa) para acessar os mesmos aplicativos quando políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ac241-173">Apps that support multi-identity let you use different accounts (work and personal) to access the same apps, while app protection policies are applied only when the apps are used in the work context.</span></span>

<span data-ttu-id="ac241-174">Por exemplo, quando o usuário inicia o aplicativo OneDrive usando sua conta de trabalho, ele não pode mover os arquivos para um local de armazenamento pessoal.</span><span class="sxs-lookup"><span data-stu-id="ac241-174">For example, when a user starts the OneDrive app by using their work account, they can't move the files to a personal storage location.</span></span> <span data-ttu-id="ac241-175">No entanto, quando ele usa o OneDrive com sua conta pessoal, ele pode copiar e mover dados do seu OneDrive pessoal sem restrições.</span><span class="sxs-lookup"><span data-stu-id="ac241-175">However, when they use OneDrive with their personal account, they can copy and move data from their personal OneDrive without restrictions.</span></span>

- <span data-ttu-id="ac241-176">Saiba mais sobre os aplicativos que oferecem suporte a [MAM e várias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) com o Intune.</span><span class="sxs-lookup"><span data-stu-id="ac241-176">Learn more about the apps that support [MAM and multi-identity](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) with Intune.</span></span>

##  <span data-ttu-id="ac241-177">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ac241-177">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="ac241-178">Como criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ac241-178">How to create and deploy app protection policies with Microsoft Intune</span></span>](app-protection-policies.md)
