## <span data-ttu-id="74fa3-101">Habilitar o registro automático do Windows 10</span><span class="sxs-lookup"><span data-stu-id="74fa3-101">Enable Windows 10 automatic enrollment</span></span>
<a id="enable-windows-10-automatic-enrollment" class="xliff"></a>

<span data-ttu-id="74fa3-102">O registro automático permite que os usuários registrem seus dispositivos com Windows 10 no Intune ao adicionar a conta de trabalho a seus dispositivos pessoais, ou ao ingressar seus dispositivos corporativos ao Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="74fa3-102">Automatic enrollment lets users enroll their Windows 10 devices in Intune when adding their work account to their personally-owned devices or joining their corporate-owned devices to your Azure Active Directory.</span></span> <span data-ttu-id="74fa3-103">Em segundo plano, o dispositivo do usuário registra-se e ingressa no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="74fa3-103">In the background, the user's device registers and joins Azure Active Directory.</span></span> <span data-ttu-id="74fa3-104">Depois de registrado, o dispositivo é gerenciado com o Intune.</span><span class="sxs-lookup"><span data-stu-id="74fa3-104">Once registered, the device is managed with Intune.</span></span>

<span data-ttu-id="74fa3-105">**Pré-requisitos**</span><span class="sxs-lookup"><span data-stu-id="74fa3-105">**Prerequisites**</span></span>
- <span data-ttu-id="74fa3-106">Assinatura do Azure Active Directory Premium ([assinatura de avaliação](http://go.microsoft.com/fwlink/?LinkID=816845))</span><span class="sxs-lookup"><span data-stu-id="74fa3-106">Azure Active Directory Premium subscription ([trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845))</span></span>
- <span data-ttu-id="74fa3-107">Assinatura do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="74fa3-107">Microsoft Intune subscription</span></span>


### <span data-ttu-id="74fa3-108">Configurar o registro automático do MDM</span><span class="sxs-lookup"><span data-stu-id="74fa3-108">Configure automatic MDM enrollment</span></span>
<a id="configure-automatic-mdm-enrollment" class="xliff"></a>

1. <span data-ttu-id="74fa3-109">Entre no [Portal de Gerenciamento do Azure](https://portal.azure.com) (https://manage.windowsazure.com) e selecione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="74fa3-109">Sign in to the [Azure management portal](https://portal.azure.com) (https://manage.windowsazure.com), and select **Azure Active Directory**.</span></span>

  ![Captura de tela do portal do Azure](../media/auto-enroll-azure-main.png)

2. <span data-ttu-id="74fa3-111">Selecione **Mobilidade (MDM e MAM)**.</span><span class="sxs-lookup"><span data-stu-id="74fa3-111">Select **Mobility (MDM and MAM)**.</span></span>

  ![Captura de tela do portal do Azure](../media/auto-enroll-mdm.png)

3. <span data-ttu-id="74fa3-113">Selecione **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="74fa3-113">Select **Microsoft Intune**.</span></span>

  ![Captura de tela do portal do Azure](../media/auto-enroll-intune.png)

4. <span data-ttu-id="74fa3-115">Configure **Escopo de Usuário MDM**.</span><span class="sxs-lookup"><span data-stu-id="74fa3-115">Configure **MDM User scope**.</span></span> <span data-ttu-id="74fa3-116">Especifique quais dispositivos dos usuários devem ser gerenciados pelo Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="74fa3-116">Specify which users’ devices should be managed by Microsoft Intune.</span></span> <span data-ttu-id="74fa3-117">Os dispositivos do Windows 10 desses usuários serão automaticamente registrados para gerenciamento com o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="74fa3-117">These users’ Windows 10 devices will be automatically enrolled for management with Microsoft Intune.</span></span>

  - <span data-ttu-id="74fa3-118">**Nenhum**</span><span class="sxs-lookup"><span data-stu-id="74fa3-118">**None**</span></span>
  - <span data-ttu-id="74fa3-119">**Alguns**</span><span class="sxs-lookup"><span data-stu-id="74fa3-119">**Some**</span></span>
  - <span data-ttu-id="74fa3-120">**Todos**</span><span class="sxs-lookup"><span data-stu-id="74fa3-120">**All**</span></span>

   ![Captura de tela do portal do Azure](../media/auto-enroll-scope.png)

5. <span data-ttu-id="74fa3-122">Use os valores padrão para as seguintes URLs:</span><span class="sxs-lookup"><span data-stu-id="74fa3-122">Use the default values for the following URLs:</span></span>
    - <span data-ttu-id="74fa3-123">**URL dos Termos de uso do MDM**</span><span class="sxs-lookup"><span data-stu-id="74fa3-123">**MDM Terms of use URL**</span></span>
    - <span data-ttu-id="74fa3-124">**URL de Descoberta do MDM**</span><span class="sxs-lookup"><span data-stu-id="74fa3-124">**MDM Discovery URL**</span></span>
    - <span data-ttu-id="74fa3-125">**URL da Conformidade do MDM**</span><span class="sxs-lookup"><span data-stu-id="74fa3-125">**MDM Compliance URL**</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="74fa3-126">Se um usuário for membro de um grupo que tem ambos o registro automático de MDM e MAM habilitados e o usuário tentar ingressar no local de trabalho de seu dispositivo pessoal, somente MAM será habilitado.</span><span class="sxs-lookup"><span data-stu-id="74fa3-126">If a user is a member of a group that has both automatic MDM enrollment and MAM enabled, and the user tries to workplace join their personal device, then only MAM is enabled.</span></span> 

6. <span data-ttu-id="74fa3-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="74fa3-127">Select **Save**.</span></span>

<span data-ttu-id="74fa3-128">Por padrão, autenticação de dois fatores não está habilitada para o serviço.</span><span class="sxs-lookup"><span data-stu-id="74fa3-128">By default, two-factor authentication is not enabled for the service.</span></span> <span data-ttu-id="74fa3-129">No entanto, a autenticação de dois fatores é recomendável ao registrar um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74fa3-129">However, two-factor authentication is recommended when registering a device.</span></span> <span data-ttu-id="74fa3-130">Antes de solicitar a autenticação de dois fatores para esse serviço, você deve configurar um provedor de autenticação de dois fatores no Azure Active Directory e configurar suas contas de usuário para autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="74fa3-130">Before requiring two-factor authentication for this service, you must configure a two-factor authentication provider in Azure Active Directory and configure your user accounts for multi-factor authentication.</span></span> <span data-ttu-id="74fa3-131">Consulte [Guia de Introdução com o servidor de autenticação multifator do Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).</span><span class="sxs-lookup"><span data-stu-id="74fa3-131">See [Getting started with the Azure Multi-Factor Authentication Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).</span></span>
