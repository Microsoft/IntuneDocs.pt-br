## <span data-ttu-id="d2ade-101">Habilitar o registro automático do Windows 10</span><span class="sxs-lookup"><span data-stu-id="d2ade-101">Enable Windows 10 automatic enrollment</span></span>
<a id="enable-windows-10-automatic-enrollment" class="xliff"></a>

<span data-ttu-id="d2ade-102">O registro automático permite que os usuários registrem seus dispositivos com Windows 10 no Intune ao adicionar a conta de trabalho a seus dispositivos pessoais, ou ao ingressar seus dispositivos corporativos ao Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d2ade-102">Automatic enrollment lets users enroll their Windows 10 devices in Intune when adding their work account to their personally-owned devices or joining their corporate-owned devices to your Azure Active Directory.</span></span> <span data-ttu-id="d2ade-103">Em segundo plano, o dispositivo do usuário registra-se e ingressa no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d2ade-103">In the background, the user's device registers and joins Azure Active Directory.</span></span> <span data-ttu-id="d2ade-104">Depois de registrado, o dispositivo é gerenciado com o Intune.</span><span class="sxs-lookup"><span data-stu-id="d2ade-104">Once registered, the device is managed with Intune.</span></span>

<span data-ttu-id="d2ade-105">**Pré-requisitos**</span><span class="sxs-lookup"><span data-stu-id="d2ade-105">**Prerequisites**</span></span>
- <span data-ttu-id="d2ade-106">Assinatura do Azure Active Directory Premium ([assinatura de avaliação](http://go.microsoft.com/fwlink/?LinkID=816845))</span><span class="sxs-lookup"><span data-stu-id="d2ade-106">Azure Active Directory Premium subscription ([trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845))</span></span>
- <span data-ttu-id="d2ade-107">Assinatura do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d2ade-107">Microsoft Intune subscription</span></span>


### <span data-ttu-id="d2ade-108">Configurar o registro automático do MDM</span><span class="sxs-lookup"><span data-stu-id="d2ade-108">Configure automatic MDM enrollment</span></span>
<a id="configure-automatic-mdm-enrollment" class="xliff"></a>

1. <span data-ttu-id="d2ade-109">Entre no [Portal de Gerenciamento do Azure](https://portal.azure.com) (https://manage.windowsazure.com) e selecione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d2ade-109">Sign in to the [Azure management portal](https://portal.azure.com) (https://manage.windowsazure.com), and select **Azure Active Directory**.</span></span>

  ![Captura de tela do portal do Azure](../media/auto-enroll-azure-main.png)

2. <span data-ttu-id="d2ade-111">Selecione **Mobilidade (MDM e MAM)**.</span><span class="sxs-lookup"><span data-stu-id="d2ade-111">Select **Mobility (MDM and MAM)**.</span></span>

  ![Captura de tela do portal do Azure](../media/auto-enroll-mdm.png)

3. <span data-ttu-id="d2ade-113">Selecione **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="d2ade-113">Select **Microsoft Intune**.</span></span>

  ![Captura de tela do portal do Azure](../media/auto-enroll-intune.png)

4. <span data-ttu-id="d2ade-115">Configure **Escopo de Usuário MDM**.</span><span class="sxs-lookup"><span data-stu-id="d2ade-115">Configure **MDM User scope**.</span></span> <span data-ttu-id="d2ade-116">Especifique quais dispositivos dos usuários devem ser gerenciados pelo Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d2ade-116">Specify which users’ devices should be managed by Microsoft Intune.</span></span> <span data-ttu-id="d2ade-117">Os dispositivos do Windows 10 desses usuários serão automaticamente registrados para gerenciamento com o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="d2ade-117">These users’ Windows 10 devices will be automatically enrolled for management with Microsoft Intune.</span></span>

  - <span data-ttu-id="d2ade-118">**Nenhum**</span><span class="sxs-lookup"><span data-stu-id="d2ade-118">**None**</span></span>
  - <span data-ttu-id="d2ade-119">**Alguns**</span><span class="sxs-lookup"><span data-stu-id="d2ade-119">**Some**</span></span>
  - <span data-ttu-id="d2ade-120">**Todos**</span><span class="sxs-lookup"><span data-stu-id="d2ade-120">**All**</span></span>

 ![Captura de tela do portal do Azure](../media/auto-enroll-scope.png)

5. <span data-ttu-id="d2ade-122">Use os valores padrão para as seguintes URLs:</span><span class="sxs-lookup"><span data-stu-id="d2ade-122">Use the default values for the following URLs:</span></span>
  - <span data-ttu-id="d2ade-123">**URL dos Termos de uso do MDM**</span><span class="sxs-lookup"><span data-stu-id="d2ade-123">**MDM Terms of use URL**</span></span>
  - <span data-ttu-id="d2ade-124">**URL de Descoberta do MDM**</span><span class="sxs-lookup"><span data-stu-id="d2ade-124">**MDM Discovery URL**</span></span>
  - <span data-ttu-id="d2ade-125">**URL da Conformidade do MDM**</span><span class="sxs-lookup"><span data-stu-id="d2ade-125">**MDM Compliance URL**</span></span>

6. <span data-ttu-id="d2ade-126">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d2ade-126">Select **Save**.</span></span>

<span data-ttu-id="d2ade-127">Por padrão, autenticação de dois fatores não está habilitada para o serviço.</span><span class="sxs-lookup"><span data-stu-id="d2ade-127">By default, two-factor authentication is not enabled for the service.</span></span> <span data-ttu-id="d2ade-128">No entanto, a autenticação de dois fatores é recomendável ao registrar um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d2ade-128">However, two-factor authentication is recommended when registering a device.</span></span> <span data-ttu-id="d2ade-129">Antes de solicitar a autenticação de dois fatores para esse serviço, você deve configurar um provedor de autenticação de dois fatores no Azure Active Directory e configurar suas contas de usuário para autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="d2ade-129">Before requiring two-factor authentication for this service, you must configure a two-factor authentication provider in Azure Active Directory and configure your user accounts for multi-factor authentication.</span></span> <span data-ttu-id="d2ade-130">Consulte [Guia de Introdução com o servidor de autenticação multifator do Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).</span><span class="sxs-lookup"><span data-stu-id="d2ade-130">See [Getting started with the Azure Multi-Factor Authentication Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).</span></span>
