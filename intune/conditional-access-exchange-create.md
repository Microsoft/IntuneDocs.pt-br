---
title: "Criar e atribuir uma política de acesso condicional para o Exchange local"
titleSuffix: Intune on Azure
description: "Como você pode configurar o acesso condicional do Exchange Local e do Exchange Online Dedicado herdado no Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b72dbe27b52be187a907392aea5a1803fb36e4d3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <span data-ttu-id="b96b2-103">Como criar e atribuir uma política de acesso condicional para o Exchange Local e o Exchange Online Dedicado herdado no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b96b2-103">How to create and assign a conditional access policy for Exchange on-premises and legacy Exchange Online Dedicated in Microsoft Intune</span></span>
<a id="how-to-create-and-assign-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b96b2-104">Este tópico explica o processo de configuração de acesso condicional para Exchange local com base na conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b96b2-104">This topic walks you through the process of configuring conditional access for Exchange on-premises based on device compliance.</span></span>

<span data-ttu-id="b96b2-105">Se você tiver um ambiente do Exchange Online Dedicado e precisar descobrir se ele está na configuração nova ou herdada, entre em contato com seu gerente de conta.</span><span class="sxs-lookup"><span data-stu-id="b96b2-105">If you have an Exchange Online Dedicated environment and need to find out whether it is in the new or the legacy configuration, please contact your account manager.</span></span> <span data-ttu-id="b96b2-106">Para controlar o acesso ao email para Exchange local ou para seu ambiente herdado do Exchange Online dedicado, configure o acesso condicional ao Exchange local no Intune.</span><span class="sxs-lookup"><span data-stu-id="b96b2-106">To control email access to Exchange on-premises or to your legacy Exchange Online Dedicated environment, configure conditional access to Exchange on-premises in Intune.</span></span>

## <span data-ttu-id="b96b2-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b96b2-107">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

<span data-ttu-id="b96b2-108">Antes de poder configurar o acesso condicional, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b96b2-108">Before you can configure conditional access, verify the following:</span></span>

- <span data-ttu-id="b96b2-109">A versão do Exchange deve ser **Exchange 2010 SP1 ou posterior**.</span><span class="sxs-lookup"><span data-stu-id="b96b2-109">Your Exchange version must be **Exchange 2010 SP1 or later**.</span></span> <span data-ttu-id="b96b2-110">Há suporte para a matriz de CAS (Servidor de Acesso de Cliente) do servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="b96b2-110">Exchange server Client Access Server (CAS) array is supported.</span></span>

- <span data-ttu-id="b96b2-111">É preciso usar o [conector do Exchange local do Exchange Active Sync](exchange-connector-install.md), que conecta o Intune ao Exchange local.</span><span class="sxs-lookup"><span data-stu-id="b96b2-111">You must use the [Exchange Active Sync on-premises Exchange connector](exchange-connector-install.md), which connects Intune to on-premises Exchange.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="b96b2-112">O conector do Exchange local é específico ao seu locatário do Intune e não pode ser usado com nenhum outro locatário.</span><span class="sxs-lookup"><span data-stu-id="b96b2-112">The on-premises Exchange connector is specific to your Intune tenant and cannot be used with any other tenant.</span></span> <span data-ttu-id="b96b2-113">Você também deve garantir que o Exchange Connector do seu locatário esteja instalado em **apenas um computador**.</span><span class="sxs-lookup"><span data-stu-id="b96b2-113">You should also ensure that the exchange connector for your tenant is installed **on only one machine**.</span></span>

- <span data-ttu-id="b96b2-114">O conector pode ser instalado em qualquer computador, desde que o computador seja capaz de se comunicar com o servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="b96b2-114">The connector can be installed on any machine as long as that machine is able to communicate with the Exchange server.</span></span>

- <span data-ttu-id="b96b2-115">Esse conector dá suporte a **ambiente de CAS do Exchange**.</span><span class="sxs-lookup"><span data-stu-id="b96b2-115">The connector supports **Exchange CAS environment**.</span></span> <span data-ttu-id="b96b2-116">Você pode tecnicamente instalar o conector no servidor de CAS do Exchange diretamente se desejar, mas não é recomendável, pois ele aumenta a carga no servidor.</span><span class="sxs-lookup"><span data-stu-id="b96b2-116">You can technically install the connector on the Exchange CAS server directly if you wish to, but it is not recommended, as it will increase the load on the server.</span></span> <span data-ttu-id="b96b2-117">Ao configurar o conector, você deve configurá-lo para que ele se comunique com um dos servidores de CAS do Exchange.</span><span class="sxs-lookup"><span data-stu-id="b96b2-117">When configuring the connector, you must set it up to communicate to one of the Exchange CAS servers.</span></span>

- <span data-ttu-id="b96b2-118">O **Exchange ActiveSync** deve ser configurado com autenticação baseada em certificado ou em entrada de credenciais de usuário.</span><span class="sxs-lookup"><span data-stu-id="b96b2-118">**Exchange ActiveSync** must be configured with certificate based authentication, or user credential entry.</span></span>

- <span data-ttu-id="b96b2-119">Quando políticas de acesso condicionais são configuradas e direcionadas ao usuário, antes de um usuário se conectar ao email, o **dispositivo** usado deve:</span><span class="sxs-lookup"><span data-stu-id="b96b2-119">When conditional access policies are configured and targeted to a user, before a user can connect to their email, the **device** they use must be:</span></span>
    - <span data-ttu-id="b96b2-120">Estar **registrado** no Intune ou em um computador ingressado no domínio.</span><span class="sxs-lookup"><span data-stu-id="b96b2-120">Either **enrolled** with Intune or is a domain joined PC.</span></span>
    - <span data-ttu-id="b96b2-121">**Registrado no Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b96b2-121">**Registered in Azure Active Directory**.</span></span> <span data-ttu-id="b96b2-122">Além disso, a ID do Exchange ActiveSync do cliente deve estar registrada com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b96b2-122">Additionally, the client Exchange ActiveSync ID must be registered with Azure Active Directory.</span></span>
<br></br>
- <span data-ttu-id="b96b2-123">O AAD DRS será ativado automaticamente para clientes do Intune e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b96b2-123">AAD DRS will be activated automatically for Intune and Office 365 customers.</span></span> <span data-ttu-id="b96b2-124">Clientes que já tiverem implantado o Serviço de Registro de Dispositivos do ADFS não verão dispositivos registrados no seu Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="b96b2-124">Customers who have already deployed the ADFS Device Registration Service will not see registered devices in their on-premises Active Directory.</span></span> <span data-ttu-id="b96b2-125">**Isso não se aplica a computadores Windows e dispositivos do Windows Phone**.</span><span class="sxs-lookup"><span data-stu-id="b96b2-125">**This does not apply to Windows PCs and Windows Phone devices**.</span></span>

- <span data-ttu-id="b96b2-126">**Estar em conformidade** com qualquer política de conformidade do dispositivo implantada nesse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b96b2-126">**Compliant** with device compliance policies deployed to that device.</span></span>

- <span data-ttu-id="b96b2-127">Se o dispositivo não atender às configurações de acesso condicional, uma das mensagens a seguir será apresentara ao usuário quando ele fizer logon:</span><span class="sxs-lookup"><span data-stu-id="b96b2-127">If the device does not meet conditional access settings, the user is presented with one of the following messages when they log in:</span></span>
    - <span data-ttu-id="b96b2-128">Se o dispositivo não estiver registrado no Intune ou não estiver registrado no Azure Active Directory, será exibida uma mensagem com instruções sobre como instalar o aplicativo do Portal da Empresa, registrar o dispositivo e ativar o email.</span><span class="sxs-lookup"><span data-stu-id="b96b2-128">If the device is not enrolled with Intune, or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app, enroll the device, and activate email.</span></span> <span data-ttu-id="b96b2-129">Esse processo também associa a ID do Exchange ActiveSync do dispositivo ao registro do dispositivo no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b96b2-129">This process also associates the device's Exchange ActiveSync ID with the device record in Azure Active Directory.</span></span>
    - <span data-ttu-id="b96b2-130">Se o dispositivo não estiver em conformidade, será exibida uma mensagem que direcionará o usuário ao site do Portal da Empresa do Intune ou ao aplicativo Portal da Empresa, no qual ele poderá encontrar informações sobre o problema e como corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="b96b2-130">If the device is not compliant, a message is displayed that directs the user to the Intune Company Portal website, or the Company Portal app where they can find information about the problem and how to remediate it.</span></span>

### <span data-ttu-id="b96b2-131">Suporte para dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="b96b2-131">Support for mobile devices</span></span>
<a id="support-for-mobile-devices" class="xliff"></a>

- <span data-ttu-id="b96b2-132">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="b96b2-132">Windows Phone 8.1 and later</span></span>
- <span data-ttu-id="b96b2-133">Aplicativo de email nativo no iOS.</span><span class="sxs-lookup"><span data-stu-id="b96b2-133">Native email app on iOS.</span></span>
- <span data-ttu-id="b96b2-134">Clientes de email EAS, como Gmail no Android 4 ou versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="b96b2-134">EAS mail clients such as Gmail on Android 4 or later.</span></span>
- <span data-ttu-id="b96b2-135">Clientes de email EAS com **dispositivos Android for Work:** há suporte somente para os aplicativos **Gmail** e **Nine Work** do **perfil de trabalho** em dispositivos Android for Work.</span><span class="sxs-lookup"><span data-stu-id="b96b2-135">EAS mail clients **Android for Work devices:** Only **Gmail** and **Nine Work** apps in the **work profile** are supported on Android for Work devices.</span></span> <span data-ttu-id="b96b2-136">Para obter acesso condicional ao Android para Trabalho, é necessário implantar um perfil de email para os aplicativos Gmail ou Nine Work e implantá-los como uma instalação obrigatória.</span><span class="sxs-lookup"><span data-stu-id="b96b2-136">For conditional access to work with Android for Work, you must deploy an email profile for the Gmail or Nine Work app, and also deploy those apps as a required install.</span></span>

> [!NOTE]
> <span data-ttu-id="b96b2-137">Não há suporte para o aplicativo Microsoft Outlook no Android e iOS.</span><span class="sxs-lookup"><span data-stu-id="b96b2-137">Microsoft Outlook app for Android and iOS is not supported.</span></span> <span data-ttu-id="b96b2-138">O Android para Trabalho está em processo de distribuição entre os locatários do Intune e o processo continuará durante os próximos meses.</span><span class="sxs-lookup"><span data-stu-id="b96b2-138">Android for Work is currently being rolled out across Intune tenants over the next few months.</span></span>

### <span data-ttu-id="b96b2-139">Suporte para computadores</span><span class="sxs-lookup"><span data-stu-id="b96b2-139">Support for PCs</span></span>
<a id="support-for-pcs" class="xliff"></a>

<span data-ttu-id="b96b2-140">O aplicativo nativo de **Email** do Windows 8.1 e versões posteriores (quando registrado com Intune)</span><span class="sxs-lookup"><span data-stu-id="b96b2-140">The native **Mail** application on Windows 8.1 and later (when enrolled with Intune)</span></span>


## <span data-ttu-id="b96b2-141">Configurar o acesso local ao Exchange</span><span class="sxs-lookup"><span data-stu-id="b96b2-141">Configure Exchange on-premises access</span></span>
<a id="configure-exchange-on-premises-access" class="xliff"></a>

1. <span data-ttu-id="b96b2-142">Vá para o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais do Intune.</span><span class="sxs-lookup"><span data-stu-id="b96b2-142">Go to the [Azure portal](https://portal.azure.com/), and sign in with your Intune credentials.</span></span>

2. <span data-ttu-id="b96b2-143">Quando entrar com êxito, você verá o **Painel do Azure**.</span><span class="sxs-lookup"><span data-stu-id="b96b2-143">After you've successfully signed in, you see the **Azure Dashboard**.</span></span>

3. <span data-ttu-id="b96b2-144">Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="b96b2-144">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

4. <span data-ttu-id="b96b2-145">Escolha **Intune** e você verá o **Painel do Intune**.</span><span class="sxs-lookup"><span data-stu-id="b96b2-145">Choose **Intune**, you see the **Intune Dashboard**.</span></span>

5. <span data-ttu-id="b96b2-146">Escolha **Acesso Local** e</span><span class="sxs-lookup"><span data-stu-id="b96b2-146">Choose **On-Premise Access**, then choose</span></span>

6. <span data-ttu-id="b96b2-147">A folha **Local** mostra o status da política de acesso condicional e os dispositivos que são afetados por ele.</span><span class="sxs-lookup"><span data-stu-id="b96b2-147">The **On-premises** blade shows the status of the conditional access policy and the devices that are affected by it.</span></span>

7. <span data-ttu-id="b96b2-148">Em **Gerenciar**, escolha **Acesso ao Exchange local**.</span><span class="sxs-lookup"><span data-stu-id="b96b2-148">Under **Manage**, choose **Exchange on-premises access**.</span></span>

8. <span data-ttu-id="b96b2-149">Na folha **Acesso local do Exchange**, escolha **Sim** para habilitar o controle de acesso local do Exchange.</span><span class="sxs-lookup"><span data-stu-id="b96b2-149">On the **Exchange on-premises access** blade, choose **Yes** to enable Exchange on-premises access control.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b96b2-150">Se você não tiver configurado o conector local do Exchange Active Sync, essa opção estará desabilitada.</span><span class="sxs-lookup"><span data-stu-id="b96b2-150">If you have not configured the Exchange Active Sync on-premises connector, this option will be disabled.</span></span>  <span data-ttu-id="b96b2-151">Você primeiro deve instalar e configurar esse conector antes de habilitar o acesso condicional para o Exchange local.</span><span class="sxs-lookup"><span data-stu-id="b96b2-151">You must first install and configure this connector before enabling conditional access for Exchange on-premises.</span></span> <span data-ttu-id="b96b2-152">Para obter mais detalhes, consulte [Instalar o Intune On-premises Exchange Connector](exchange-connector-install.md)</span><span class="sxs-lookup"><span data-stu-id="b96b2-152">For more details, see [Install the Intune On-premises Exchange Connector](exchange-connector-install.md)</span></span>

9. <span data-ttu-id="b96b2-153">Em **Atribuição**, escolha **Grupos Incluídos**.</span><span class="sxs-lookup"><span data-stu-id="b96b2-153">Under **Assignment**, choose **Groups Included**.</span></span>  <span data-ttu-id="b96b2-154">Use o grupo de usuários de segurança que deve ter acesso condicional aplicado.</span><span class="sxs-lookup"><span data-stu-id="b96b2-154">Use the security user group that should have conditional access applied to it.</span></span> <span data-ttu-id="b96b2-155">Isso exigiria que os usuários registrem seus dispositivos no Intune e estejam em conformidade com os perfis de conformidade.</span><span class="sxs-lookup"><span data-stu-id="b96b2-155">This would require the users to enroll their devices in Intune and be compliant with the compliance profiles.</span></span>

10. <span data-ttu-id="b96b2-156">Se você desejar excluir certos grupos de usuários, poderá fazer isso escolhendo **Grupos Excluídos** e selecionando um grupo de usuários que você quer isentar da exigência de registro e conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b96b2-156">If you want to exclude a certain groups of users, you can do so by choosing **Groups Excluded** and selecting a user group that you want to be exempt from requiring device enrollment and compliance.</span></span>

11. <span data-ttu-id="b96b2-157">Em **Configurações**, escolha **Notificações do usuário** para modificar a mensagem de email padrão.</span><span class="sxs-lookup"><span data-stu-id="b96b2-157">Under **Settings**, choose **User notifications** to modify the default email message.</span></span> <span data-ttu-id="b96b2-158">Esta mensagem é enviada para os usuários cujo dispositivo não está em conformidade e que desejam acessar o Exchange local.</span><span class="sxs-lookup"><span data-stu-id="b96b2-158">This message is sent to users if their device is not compliant and they want to access Exchange on-premises.</span></span> <span data-ttu-id="b96b2-159">O modelo de mensagem usa a linguagem de marcação.</span><span class="sxs-lookup"><span data-stu-id="b96b2-159">The message template uses Markup language.</span></span>  <span data-ttu-id="b96b2-160">Você também verá a versão prévia da aparência da mensagem conforme você digita.</span><span class="sxs-lookup"><span data-stu-id="b96b2-160">You will also see the preview of how the message looks as you type.</span></span>
    > [!TIP]
    > <span data-ttu-id="b96b2-161">Para saber mais sobre a linguagem de marcação, consulte este [artigo](https://en.wikipedia.org/wiki/Markup_language) da Wikipédia.</span><span class="sxs-lookup"><span data-stu-id="b96b2-161">To learn more about Markup language see this Wikipedia [article](https://en.wikipedia.org/wiki/Markup_language).</span></span>

12. <span data-ttu-id="b96b2-162">Na folha **Configurações de acesso avançado do Exchange Active Sync**, defina a regra padrão global para acesso de dispositivos não gerenciados pelo Intune e para regras de nível de plataforma conforme descrito nas próximas duas etapas.</span><span class="sxs-lookup"><span data-stu-id="b96b2-162">On the **Advanced Exchange Active Sync access settings** blade, set the global default rule for access from devices that are not managed by Intune, and for platform-level rules as described in the next two steps.</span></span>

13. <span data-ttu-id="b96b2-163">Para um dispositivo que não é afetado pelo acesso condicional ou por outras regras, você pode optar por permitir que ele acesse o Exchange ou bloqueá-lo.</span><span class="sxs-lookup"><span data-stu-id="b96b2-163">For a device that is not affected by conditional access or other rules, you can choose to allow it to access Exchange, or block it.</span></span>
  - <span data-ttu-id="b96b2-164">Quando você define esta opção para permitir o acesso, todos os dispositivos serão capazes de acessar o Exchange local imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b96b2-164">When you set this to allow access, all devices will be able to access Exchange on-premises immediately.</span></span>  <span data-ttu-id="b96b2-165">Dispositivos que pertencem aos usuários nos **Grupos Incluídos** serão bloqueados se forem avaliados posteriormente como não compatível com as políticas de conformidade ou não forem registrados no Intune.</span><span class="sxs-lookup"><span data-stu-id="b96b2-165">Devices that belong to the users in the **Groups Included**, are blocked if they are subsequently evaluated as not compliant with the compliant policies or not enrolled in Intune.</span></span>
  - <span data-ttu-id="b96b2-166">Quando você define esta opção para bloquear o acesso, todos os dispositivos serão imediatamente impedidos de acessar o Exchange local inicialmente.</span><span class="sxs-lookup"><span data-stu-id="b96b2-166">When you set this to block access, all devices will be immediately blocked from accessing Exchange on-premises initially.</span></span>  <span data-ttu-id="b96b2-167">Dispositivos que pertencem aos usuários dos **Grupos Incluídos** obterão acesso depois que o dispositivo for registrado no Intune e avaliado como em conformidade.</span><span class="sxs-lookup"><span data-stu-id="b96b2-167">Devices that belong to users in the **Groups Included** will get access once the device is enrolled in Intune and is evaluated as compliant.</span></span> <span data-ttu-id="b96b2-168">Em dispositivos Android que não executam o Samsung KNOX Standard, eles sempre serão bloqueados, pois não dão suporte a essa configuração.</span><span class="sxs-lookup"><span data-stu-id="b96b2-168">On Android devices that do not run Samsung KNOX standard will always be blocked as they do not support this setting.</span></span>
<br></br>
14. <span data-ttu-id="b96b2-169">Em **Exceções de plataforma de dispositivo**, escolha **Adicionar** para especificar as plataformas.</span><span class="sxs-lookup"><span data-stu-id="b96b2-169">Under **Device platform exceptions**, choose **Add** to specify the platforms.</span></span> <span data-ttu-id="b96b2-170">Se a configuração **Acesso de dispositivo não gerenciado** for definida como **Bloqueado**, os dispositivos que estão registrados e em conformidade serão permitidos mesmo se houver uma exceção de plataforma a ser bloqueada.</span><span class="sxs-lookup"><span data-stu-id="b96b2-170">If the **unmanaged device access** setting is set to **blocked**, devices that are enrolled and compliant will be allowed even if there is a platform exception to block.</span></span> <span data-ttu-id="b96b2-171">Escolha **OK** para salvar as configurações.</span><span class="sxs-lookup"><span data-stu-id="b96b2-171">Choose **Ok** to save the settings.</span></span>

15. <span data-ttu-id="b96b2-172">Na folha **Local**, clique em **Salvar** para salvar a política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="b96b2-172">On the **On-premises** blade, click **Save** to save the conditional access policy.</span></span>

## <span data-ttu-id="b96b2-173">Criar políticas de acesso condicional do Azure AD no Intune</span><span class="sxs-lookup"><span data-stu-id="b96b2-173">Create Azure AD Conditional access policies in Intune</span></span>
<a id="create-azure-ad-conditional-access-policies-in-intune" class="xliff"></a>

<span data-ttu-id="b96b2-174">A partir da versão 1704 do Intune, os administradores podem criar políticas de acesso condicional do Azure AD no portal do Intune no Azure, que oferece conveniência, de modo que você não precise alternar entre as cargas de trabalho do Azure e do Intune.</span><span class="sxs-lookup"><span data-stu-id="b96b2-174">Beginning with Intune 1704 release, admins can create Azure AD conditional access policies from the Intune Azure portal, which gives convenience so you don't need to switch between the Azure and Intune workloads.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b96b2-175">Você precisa ter uma licença Premium do Azure AD para criar políticas de acesso condicional do Azure AD no portal do Intune no Azure.</span><span class="sxs-lookup"><span data-stu-id="b96b2-175">You need to have an Azure AD Premium license to create Azure AD conditional access policies from the Intune Azure portal.</span></span>

### <span data-ttu-id="b96b2-176">Para criar uma política de acesso condicional do Azure AD</span><span class="sxs-lookup"><span data-stu-id="b96b2-176">To create Azure AD conditional access policy</span></span>
<a id="to-create-azure-ad-conditional-access-policy" class="xliff"></a>

1. <span data-ttu-id="b96b2-177">No **Painel do Intune**, escolha **Acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="b96b2-177">In the **Intune Dashboard**, choose **Conditional access**.</span></span>

2. <span data-ttu-id="b96b2-178">No **Painel de controle de Acesso condicional**, escolha **Acesso condicional no Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b96b2-178">In the **Conditional access dashboard**, choose **Conditional access in Azure Active Directory**.</span></span>

3. <span data-ttu-id="b96b2-179">Escolha **Nova política** para criar a nova política de acesso condicional do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b96b2-179">Choose **New policy** to create your new Azure AD conditional access policy.</span></span>

    ![Políticas de acesso condicional do Azure AD](./media/Azure-AD-CA-Intune.png)

## <span data-ttu-id="b96b2-181">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b96b2-181">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="b96b2-182">Acesso condicional no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b96b2-182">Conditional Access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)