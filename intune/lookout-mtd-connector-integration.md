---
title: "Configurar a integração do Lookout com o Intune"
titleSuffix: Intune on Azure
description: Configurar sua assinatura do Lookout com o Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c6af49be38e760e14824eb380e4cf3467a695df8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="c2816-103">Configurar a integração da Defesa contra Ameaças Móveis do Lookout com o Intune</span><span class="sxs-lookup"><span data-stu-id="c2816-103">Set up your Lookout Mobile Threat Defense integration with Intune</span></span>
<a id="set-up-your-lookout-mobile-threat-defense-integration-with-intune" class="xliff"></a>

<span data-ttu-id="c2816-104">As etapas a seguir são necessárias para configurar a assinatura da Defesa contra Ameaças Móveis do Lookout:</span><span class="sxs-lookup"><span data-stu-id="c2816-104">The following steps are required to set up Lookout Mobile Threat Defense subscription:</span></span>

| #        |<span data-ttu-id="c2816-105">Etapa</span><span class="sxs-lookup"><span data-stu-id="c2816-105">Step</span></span>  |
| ------------- |:-------------|
| <span data-ttu-id="c2816-106">1</span><span class="sxs-lookup"><span data-stu-id="c2816-106">1</span></span> | [<span data-ttu-id="c2816-107">Coletar informações do Azure AD</span><span class="sxs-lookup"><span data-stu-id="c2816-107">Collect Azure AD information</span></span>](#collect-azure-ad-information) |
| <span data-ttu-id="c2816-108">2</span><span class="sxs-lookup"><span data-stu-id="c2816-108">2</span></span> | [<span data-ttu-id="c2816-109">Configurar sua assinatura</span><span class="sxs-lookup"><span data-stu-id="c2816-109">Configure your subscription</span></span>](#configure-your-subscription) |
| <span data-ttu-id="c2816-110">3</span><span class="sxs-lookup"><span data-stu-id="c2816-110">3</span></span> | [<span data-ttu-id="c2816-111">Configurar grupos de registro</span><span class="sxs-lookup"><span data-stu-id="c2816-111">Configure enrollment groups</span></span>](#configure-enrollment-groups) |
| <span data-ttu-id="c2816-112">4</span><span class="sxs-lookup"><span data-stu-id="c2816-112">4</span></span> | [<span data-ttu-id="c2816-113">Configurar a sincronização de estado</span><span class="sxs-lookup"><span data-stu-id="c2816-113">Configure state sync</span></span>](#configure-state-sync) |
| <span data-ttu-id="c2816-114">5</span><span class="sxs-lookup"><span data-stu-id="c2816-114">5</span></span> | [<span data-ttu-id="c2816-115">Configurar informações do destinatário do email de relatório de erros</span><span class="sxs-lookup"><span data-stu-id="c2816-115">Configure error report email recipient information</span></span>](#configure-error-report-email-recipient-information) |
| <span data-ttu-id="c2816-116">6</span><span class="sxs-lookup"><span data-stu-id="c2816-116">6</span></span> | [<span data-ttu-id="c2816-117">Definir configurações de registro</span><span class="sxs-lookup"><span data-stu-id="c2816-117">Configure enrollment settings</span></span>](#configure-enrollment-settings) |
| <span data-ttu-id="c2816-118">7</span><span class="sxs-lookup"><span data-stu-id="c2816-118">7</span></span> | [<span data-ttu-id="c2816-119">Configurar notificações por email</span><span class="sxs-lookup"><span data-stu-id="c2816-119">Configure email notifications</span></span>](#configure-email-notifications) |
| <span data-ttu-id="c2816-120">8</span><span class="sxs-lookup"><span data-stu-id="c2816-120">8</span></span> | [<span data-ttu-id="c2816-121">Configurar a classificação de ameaças</span><span class="sxs-lookup"><span data-stu-id="c2816-121">onfigure threat classification</span></span>](#configure-threat-classification) |
| <span data-ttu-id="c2816-122">9</span><span class="sxs-lookup"><span data-stu-id="c2816-122">9</span></span> | [<span data-ttu-id="c2816-123">Verificar o registro</span><span class="sxs-lookup"><span data-stu-id="c2816-123">Watching enrollment</span></span>](#watching-enrollment) |

> [!IMPORTANT]
> <span data-ttu-id="c2816-124">Um locatário existente do Lookout Mobile Endpoint Security que não está associado ao seu locatário do Azure AD não pode ser usado para a integração com o Azure AD e o Intune.</span><span class="sxs-lookup"><span data-stu-id="c2816-124">An existing Lookout Mobile Endpoint Security tenant that is not already associated with your Azure AD tenant cannot be used for the integration with Azure AD and Intune.</span></span> <span data-ttu-id="c2816-125">Contate o suporte do Lookout para criar um novo locatário do Lookout Mobile Endpoint Security.</span><span class="sxs-lookup"><span data-stu-id="c2816-125">Contact Lookout support to create a new Lookout Mobile Endpoint Security tenant.</span></span> <span data-ttu-id="c2816-126">Use o novo locatário para carregar os usuários do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c2816-126">Use the new tenant to onboard your Azure AD users.</span></span>

## <span data-ttu-id="c2816-127">Coletar informações do Azure AD</span><span class="sxs-lookup"><span data-stu-id="c2816-127">Collect Azure AD information</span></span>
<a id="collect-azure-ad-information" class="xliff"></a>
<span data-ttu-id="c2816-128">O locatário do Lookout Mobility Endpoint Security será associado à sua assinatura do Azure AD para integrar o Lookout com o Intune.</span><span class="sxs-lookup"><span data-stu-id="c2816-128">Your Lookout Mobility Endpoint Security tenant will be associated with your Azure AD subscription to integrate Lookout with Intune.</span></span> <span data-ttu-id="c2816-129">Para habilitar sua assinatura do serviço de Defesa contra Ameaças Móveis do Lookout, o suporte do Lookout (enterprisesupport@lookout.com) precisa das seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="c2816-129">To enable your Lookout Mobile Threat Defense service subscription, Lookout support (enterprisesupport@lookout.com) needs the following information:</span></span>

* <span data-ttu-id="c2816-130">**ID do locatário do Azure AD**</span><span class="sxs-lookup"><span data-stu-id="c2816-130">**Azure AD Tenant ID**</span></span>
* <span data-ttu-id="c2816-131">**ID do Objeto de Grupo do Azure AD** para acesso **completo** ao console do Lookout</span><span class="sxs-lookup"><span data-stu-id="c2816-131">**Azure AD Group Object ID** for **full** Lookout console access</span></span>
* <span data-ttu-id="c2816-132">**ID do objeto de grupo do Azure AD** para acesso **restrito** ao Lookout (opcional)</span><span class="sxs-lookup"><span data-stu-id="c2816-132">**Azure AD Group Object ID** for **restricted** Lookout console access (optional)</span></span>

<span data-ttu-id="c2816-133">Use as etapas a seguir para coletar as informações de que precisa para fornecer à equipe de suporte do Lookout.</span><span class="sxs-lookup"><span data-stu-id="c2816-133">Use the following steps to gather the information you need to give to the Lookout support team.</span></span>

1. <span data-ttu-id="c2816-134">Entre no [Portal do Azure](https://portal.azure.com) e selecione sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="c2816-134">Sign in to the [Azure portal](https://portal.azure.com) and select your subscription.</span></span> 

2. <span data-ttu-id="c2816-135">Ao escolher o nome de sua assinatura, a URL resultante incluirá a ID da assinatura.</span><span class="sxs-lookup"><span data-stu-id="c2816-135">When you choose the name of your subscription, the resulting URL includes the subscription ID.</span></span>  <span data-ttu-id="c2816-136">Se você tiver problemas para localizar sua ID da assinatura, consulte este [artigo do suporte da Microsoft](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b) para obter dicas sobre como encontrar sua ID de assinatura.</span><span class="sxs-lookup"><span data-stu-id="c2816-136">If you have any issues finding your subscription ID, see this [Microsoft support article](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b) for tips on finding your subscription ID.</span></span>

3. <span data-ttu-id="c2816-137">Encontre sua ID do Grupo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c2816-137">Find your Azure AD Group ID.</span></span> <span data-ttu-id="c2816-138">O console do Lookout dá suporte a 2 níveis de acesso:</span><span class="sxs-lookup"><span data-stu-id="c2816-138">The Lookout console supports 2 levels of access:</span></span>  
  * <span data-ttu-id="c2816-139">**Acesso completo:** o administrador do Azure AD pode criar um grupo de usuários que terá acesso completo e, opcionalmente, criar um grupo de usuários que terá acesso restrito.</span><span class="sxs-lookup"><span data-stu-id="c2816-139">**Full Access:** The Azure AD admin can create a group for users that will have Full Access and optionally create a group for users that will have Restricted Access.</span></span>  <span data-ttu-id="c2816-140">Somente os usuários nesses grupos poderão fazer logon no **console do Lookout**.</span><span class="sxs-lookup"><span data-stu-id="c2816-140">Only users in these groups will be able to login to the **Lookout console**.</span></span>
  * <span data-ttu-id="c2816-141">**Acesso restrito:** os usuários neste grupo não terão acesso a várias configurações e módulos relacionados ao registro do console do Lookout e terão acesso somente leitura ao módulo de **Política de segurança** do console do Lookout.</span><span class="sxs-lookup"><span data-stu-id="c2816-141">**Restricted Access:** The users in this group will have no access to several configuration and enrollment related modules of the Lookout console, and have read-only access to the **Security Policy** module of the Lookout console.</span></span>  

    > [!TIP] 
    > <span data-ttu-id="c2816-142">Para obter mais detalhes sobre as permissões, leia [este artigo](https://personal.support.lookout.com/hc/articles/114094105653) no site do Lookout.</span><span class="sxs-lookup"><span data-stu-id="c2816-142">For more details on the permissions, read [this article](https://personal.support.lookout.com/hc/articles/114094105653) on the Lookout website.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="c2816-143">A **ID de Objeto do Grupo** está na página **Propriedades** do grupo no **portal de gerenciamento do Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="c2816-143">The **Group Object ID** is on the **Properties** page of the group in the **Azure AD management portal**.</span></span>

4. <span data-ttu-id="c2816-144">Depois de obter essas informações, contate o suporte do Lookout (email: enterprisesupport@lookout.com).</span><span class="sxs-lookup"><span data-stu-id="c2816-144">Once you have gathered this information, contact Lookout support (email: enterprisesupport@lookout.com).</span></span> <span data-ttu-id="c2816-145">O suporte do Lookout trabalhará com seu contato principal para integrar sua assinatura e criar a conta do Lookout Enterprise, usando as informações coletadas.</span><span class="sxs-lookup"><span data-stu-id="c2816-145">Lookout Support will work with your primary contact to onboard your subscription and create your Lookout Enterprise account, using the information that you collected.</span></span>

## <span data-ttu-id="c2816-146">Configurar sua assinatura</span><span class="sxs-lookup"><span data-stu-id="c2816-146">Configure your subscription</span></span>
<a id="configure-your-subscription" class="xliff"></a>

1. <span data-ttu-id="c2816-147">Depois que o suporte do Lookout criar sua conta Lookout Enterprise, um email do Lookout será enviado para o contato principal de sua empresa com um link para a URL de logon: https://aad.lookout.com/les?action=consent.</span><span class="sxs-lookup"><span data-stu-id="c2816-147">After Lookout support creates your Lookout Enterprise account, an email from Lookout is sent to the primary contact for your company with a link to the login url:https://aad.lookout.com/les?action=consent.</span></span>

2.  <span data-ttu-id="c2816-148">O primeiro logon no console do Lookout deve ser feito com uma conta de usuário com a função Administrador Global do Azure AD para registrar seu locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c2816-148">The first login to the Lookout console must be by with a user account with the Azure AD role of Global Admin to register your Azure AD tenant.</span></span> <span data-ttu-id="c2816-149">Mais tarde, a conexão não exigirá esse nível de privilégio do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c2816-149">Later, sign in doesn't this level of Azure AD privilege.</span></span> <span data-ttu-id="c2816-150">Uma página de consentimento será exibida.</span><span class="sxs-lookup"><span data-stu-id="c2816-150">A consent page is displayed.</span></span> <span data-ttu-id="c2816-151">Escolha **Aceitar** para concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="c2816-151">Choose **Accept** to complete the registration.</span></span> <span data-ttu-id="c2816-152">Depois de aceita e consentir, você será redirecionado para o Console do Lookout.</span><span class="sxs-lookup"><span data-stu-id="c2816-152">Once you have accepted and consented, you are redirected to the Lookout Console.</span></span>

    ![captura de tela da página de primeiro logon do console do Lookout](./media/lookout_mtp_initial_login.png)
    > <span data-ttu-id="c2816-154">[OBERVAÇÃO] Consulte [Solucionar problemas de integração do Lookout](https://docs.microsoft.com/intune/troubleshoot/troubleshooting-lookout-integration) para obter ajuda com problemas de logon.</span><span class="sxs-lookup"><span data-stu-id="c2816-154">[NOTE] See [troubleshooting Lookout integration](https://docs.microsoft.com/intune/troubleshoot/troubleshooting-lookout-integration) for help with login problems.</span></span>

3.  <span data-ttu-id="c2816-155">No [Console do Lookout](https://aad.lookout.com), no módulo **Sistema**, escolha a guia **Conectores** e selecione **Intune**.</span><span class="sxs-lookup"><span data-stu-id="c2816-155">In the [Lookout Console](https://aad.lookout.com), from the **System** module, choose the **Connectors** tab, and select **Intune**.</span></span>

    ![captura de tela do console do Lookout com a guia Conectores aberta e a opção Intune realçada](./media/lookout_mtp_setup-intune-connector.png)

4.  <span data-ttu-id="c2816-157">Acesse **Conectores** > **Configurações de Conexão** e especifique a **Frequência de Pulsação** em minutos.</span><span class="sxs-lookup"><span data-stu-id="c2816-157">Go **Connectors** > **Connection Settings** and specify the **Heartbeat Frequency** in minutes.</span></span>

    ![captura de tela da guia Configurações de conexão mostrando a frequência de pulsação configurada](./media/lookout-mtp-connection-settings.png)

## <span data-ttu-id="c2816-159">Configurar grupos de registro</span><span class="sxs-lookup"><span data-stu-id="c2816-159">Configure enrollment groups</span></span>
<a id="configure-enrollment-groups" class="xliff"></a>
1. <span data-ttu-id="c2816-160">Como prática recomendada, crie um grupo de segurança do Azure AD no [Portal de Gerenciamento do Azure AD](https://manage.windowsazure.com) que contém um pequeno número de usuários para testar a integração do Lookout.</span><span class="sxs-lookup"><span data-stu-id="c2816-160">As a best practice, create an Azure AD security group in the [Azure AD management portal](https://manage.windowsazure.com) containing a small number of users to test Lookout integration.</span></span>

    > <span data-ttu-id="c2816-161">[OBSERVAÇÃO] Todos os dispositivos de usuários com suporte no Lookout e registrados pelo Intune em um grupo de registro no Azure AD identificados e com suporte são registrados e qualificados para ativação no console do Lookout MTD.</span><span class="sxs-lookup"><span data-stu-id="c2816-161">[NOTE] All the Lookout-supported, Intune-enrolled devices of users in an enrollment group in Azure AD that are identified and supported are enrolled and eligible for activation in Lookout MTD console.</span></span>

2. <span data-ttu-id="c2816-162">No [Console do Lookout](https://aad.lookout.com), no módulo **Sistema**, escolha a guia **Conectores** e selecione **Gerenciamento de Registro** para definir um conjunto de usuários cujos dispositivos devem ser registrados no Lookout.</span><span class="sxs-lookup"><span data-stu-id="c2816-162">In the [Lookout Console](https://aad.lookout.com), from the **System** module, choose the **Connectors** tab, and select **Enrollment Management** to define a set of users whose devices should be enrolled with Lookout.</span></span> <span data-ttu-id="c2816-163">Adicione o **Nome de Exibição** do grupo de segurança do Azure AD para o registro.</span><span class="sxs-lookup"><span data-stu-id="c2816-163">Add the Azure AD security group **Display Name** for enrollment.</span></span>
=======
# Configurar a integração da Defesa contra Ameaças Móveis do Lookout com o Intune
<a id="set-up-your-lookout-mobile-threat-defense-integration-with-intune" class="xliff"></a>

As etapas a seguir são necessárias para configurar a assinatura da Defesa contra Ameaças Móveis do Lookout:

| #        |Etapa  |
| ------------- |:-------------|
| 1 | [Coletar informações do Azure AD](#collect-azure-ad-information) |
| 2 | [Configurar sua assinatura](#configure-your-subscription) |
| 3 | [Configurar grupos de registro](#configure-enrollment-groups) |
| 4 | [Configurar a sincronização de estado](#configure-state-sync) |
| 5 | [Configurar informações do destinatário do email de relatório de erros](#configure-error-report-email-recipient-information) |
| 6 | [Definir configurações de registro](#configure-enrollment-settings) |
| 7 | [Configurar notificações por email](#configure-email-notifications) |
| 8 | [Configurar a classificação de ameaças](#configure-threat-classification) |
| 9 | [Verificar o registro](#watching-enrollment) |

> [!IMPORTANT]
> Um locatário existente do Lookout Mobile Endpoint Security que não está associado ao seu locatário do Azure AD não pode ser usado para a integração com o Azure AD e o Intune. Contate o suporte do Lookout para criar um novo locatário do Lookout Mobile Endpoint Security. Use o novo locatário para carregar os usuários do Azure AD.

## Coletar informações do Azure AD
<a id="collect-azure-ad-information" class="xliff"></a>
O locatário do Lookout Mobility Endpoint Security será associado à sua assinatura do Azure AD para integrar o Lookout com o Intune. Para habilitar sua assinatura do serviço de Defesa contra Ameaças Móveis do Lookout, o suporte do Lookout (enterprisesupport@lookout.com) precisa das seguintes informações:

* **ID do locatário do Azure AD**
* **ID do Objeto de Grupo do Azure AD** para acesso **completo** ao console do Lookout
* **ID do objeto de grupo do Azure AD** para acesso **restrito** ao Lookout (opcional)

Use as etapas a seguir para coletar as informações de que precisa para fornecer à equipe de suporte do Lookout.

1. Entre no [Portal do Azure](https://portal.azure.com) e selecione sua assinatura. 

2. Ao escolher o nome de sua assinatura, a URL resultante incluirá a ID da assinatura.  Se você tiver problemas para localizar sua ID da assinatura, consulte este [artigo do suporte da Microsoft](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b) para obter dicas sobre como encontrar sua ID de assinatura.

3. Encontre sua ID do Grupo do Azure AD. O console do Lookout dá suporte a 2 níveis de acesso:  
  * **Acesso completo:** o administrador do Azure AD pode criar um grupo de usuários que terá acesso completo e, opcionalmente, criar um grupo de usuários que terá acesso restrito.  Somente os usuários nesses grupos poderão fazer logon no **console do Lookout**.
  * **Acesso restrito:** os usuários neste grupo não terão acesso a várias configurações e módulos relacionados ao registro do console do Lookout e terão acesso somente leitura ao módulo de **Política de segurança** do console do Lookout.  

    > [!TIP] 
    > Para obter mais detalhes sobre as permissões, leia [este artigo](https://personal.support.lookout.com/hc/articles/114094105653) no site do Lookout.

    > [!NOTE] 
    > A **ID de Objeto do Grupo** está na página **Propriedades** do grupo no **portal de gerenciamento do Azure AD**.

4. Depois de obter essas informações, contate o suporte do Lookout (email: enterprisesupport@lookout.com). O suporte do Lookout trabalhará com seu contato principal para integrar sua assinatura e criar a conta do Lookout Enterprise, usando as informações coletadas.

## Configurar sua assinatura
<a id="configure-your-subscription" class="xliff"></a>

1. Depois que o suporte do Lookout criar sua conta Lookout Enterprise, um email do Lookout será enviado para o contato principal de sua empresa com um link para a URL de logon: https://aad.lookout.com/les?action=consent.

2.  O primeiro logon no console do Lookout deve ser feito com uma conta de usuário com a função Administrador Global do Azure AD para registrar seu locatário do Azure AD. Mais tarde, a conexão não exigirá esse nível de privilégio do Azure AD. Uma página de consentimento será exibida. Escolha **Aceitar** para concluir o registro. Depois de aceita e consentir, você será redirecionado para o Console do Lookout.

    ![captura de tela da página de primeiro logon do console do Lookout](./media/lookout_mtp_initial_login.png)
    > [OBERVAÇÃO] Consulte [Solucionar problemas de integração do Lookout](https://docs.microsoft.com/intune/troubleshoot/troubleshooting-lookout-integration) para obter ajuda com problemas de logon.

3.  No [Console do Lookout](https://aad.lookout.com), no módulo **Sistema**, escolha a guia **Conectores** e selecione **Intune**.

    ![captura de tela do console do Lookout com a guia Conectores aberta e a opção Intune realçada](./media/lookout_mtp_setup-intune-connector.png)

4.  Acesse **Conectores** > **Configurações de Conexão** e especifique a **Frequência de Pulsação** em minutos.

    ![captura de tela da guia Configurações de conexão mostrando a frequência de pulsação configurada](./media/lookout-mtp-connection-settings.png)

## Configurar grupos de registro
<a id="configure-enrollment-groups" class="xliff"></a>
1. Como prática recomendada, crie um grupo de segurança do Azure AD no [Portal de Gerenciamento do Azure AD](https://manage.windowsazure.com) que contém um pequeno número de usuários para testar a integração do Lookout.

    > [OBSERVAÇÃO] Todos os dispositivos de usuários com suporte no Lookout e registrados pelo Intune em um grupo de registro no Azure AD identificados e com suporte são registrados e qualificados para ativação no console do Lookout MTD.

2. No [Console do Lookout](https://aad.lookout.com), no módulo **Sistema**, escolha a guia **Conectores** e selecione **Gerenciamento de Registro** para definir um conjunto de usuários cujos dispositivos devem ser registrados no Lookout. Adicione o **Nome de Exibição** do grupo de segurança do Azure AD para o registro.
>>>>>>> live

    ![captura de tela da página de registro do conector do Intune](./media/lookout-mtp-enrollment.png)

    >[!IMPORTANT]
<<<<<<< HEAD
    > <span data-ttu-id="c2816-165">O **Nome de Exibição** diferencia maiúsculas de minúsculas, conforme mostrado nas **Propriedades** do grupo de segurança no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="c2816-165">The  **Display Name** is case sensitive as shown the in the **Properties** of the security group in the Azure portal.</span></span> <span data-ttu-id="c2816-166">Conforme mostrado na imagem abaixo, o **Nome de Exibição** do grupo de segurança tem minúsculas concatenadas, enquanto o título tem todas as letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c2816-166">As shown in the image below, the **Display Name** of the security group is camel case while the title is all lower case.</span></span> <span data-ttu-id="c2816-167">No console do Lookout, faça a correspondência de maiúsculas e minúsculas do **Nome de Exibição** do grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="c2816-167">In the Lookout console match the **Display Name** case for the security group.</span></span>
    ><span data-ttu-id="c2816-168">![captura de tela do portal do Azure, serviço do Azure Active Directory, página de propriedades](./media/aad-group-display-name.png)</span><span class="sxs-lookup"><span data-stu-id="c2816-168">![screenshot of the Azure portal, Azure Active Directory service, properties page](./media/aad-group-display-name.png)</span></span>

    >[!NOTE] 
    ><span data-ttu-id="c2816-169">A melhor prática é deixar o padrão (5 minutos) para o incremento de tempo para verificar se há novos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c2816-169">The best practice is to use the default (5 minutes) for the increment of time to check for new devices.</span></span> <span data-ttu-id="c2816-170">Limitações atuais, **O Lookout não consegue validar os nomes de exibição do grupo:** Verifique se o campo **NOME DE EXIBIÇÃO** no Portal do Azure corresponde exatamente ao grupo de segurança do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c2816-170">Current limitations, **Lookout cannot validate group display names:** Ensure the **DISPLAY NAME** field in the Azure portal exactly matches the Azure AD security group.</span></span> <span data-ttu-id="c2816-171">**Não há suporte para a criação de grupos aninhados:** os grupos de segurança do Azure AD usados no Lookout devem conter somente usuários.</span><span class="sxs-lookup"><span data-stu-id="c2816-171">**Creating nest groups is not supported:**  Azure AD security groups used in Lookout must contain users only.</span></span> <span data-ttu-id="c2816-172">Eles não podem conter outros grupos.</span><span class="sxs-lookup"><span data-stu-id="c2816-172">They cannot contain other groups.</span></span>

3.  <span data-ttu-id="c2816-173">Depois que um grupo for adicionado, na próxima vez que um usuário abrir o aplicativo Lookout for Work em seu dispositivo com suporte, o dispositivo estará ativado no Lookout.</span><span class="sxs-lookup"><span data-stu-id="c2816-173">Once a group is added, the next time a user opens the Lookout for Work app on their supported device, the device is activated in Lookout.</span></span>

4.  <span data-ttu-id="c2816-174">Quando estiver satisfeito com os resultados, estenda o registro para grupos de usuários adicionais.</span><span class="sxs-lookup"><span data-stu-id="c2816-174">Once you are satisfied with your results, extend enrollment to additional user groups.</span></span>

## <span data-ttu-id="c2816-175">Configurar a sincronização de estado</span><span class="sxs-lookup"><span data-stu-id="c2816-175">Configure state sync</span></span>
<a id="configure-state-sync" class="xliff"></a>
<span data-ttu-id="c2816-176">Na opção **Sincronização de Estado**, especifique o tipo de dados que deve ser enviado ao Intune.</span><span class="sxs-lookup"><span data-stu-id="c2816-176">In the **State Sync** option, specify the type of data that should be sent to Intune.</span></span>  <span data-ttu-id="c2816-177">O status do dispositivo e o status da ameaça são necessários para que a integração do Lookout com o Intune funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="c2816-177">Both device status and threat status are required for the Lookout Intune integration to work correctly.</span></span> <span data-ttu-id="c2816-178">Essas configurações são habilitadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="c2816-178">These settings are enabled by default.</span></span>

## <span data-ttu-id="c2816-179">Configurar informações do destinatário do email de relatório de erros</span><span class="sxs-lookup"><span data-stu-id="c2816-179">Configure error report email recipient information</span></span>
<a id="configure-error-report-email-recipient-information" class="xliff"></a>
<span data-ttu-id="c2816-180">Na opção **Gerenciamento de Erros**, insira o endereço de email que deve receber os relatórios de erros.</span><span class="sxs-lookup"><span data-stu-id="c2816-180">In the **Error Management** option, enter the email address that should receive the error reports.</span></span>

![captura de tela da página de gerenciamento de erros do conector do Intune](./media/lookout-mtp-connector-error-notifications.png)

## <span data-ttu-id="c2816-182">Definir configurações de registro</span><span class="sxs-lookup"><span data-stu-id="c2816-182">Configure enrollment settings</span></span>
<a id="configure-enrollment-settings" class="xliff"></a>
<span data-ttu-id="c2816-183">No módulo **Sistema**, na página **Conectores**, especifique o número de dias antes que um dispositivo seja considerado desconectado.</span><span class="sxs-lookup"><span data-stu-id="c2816-183">In the **System** module, on the **Connectors** page, specify the number of days before a device is considered as disconnected.</span></span>  <span data-ttu-id="c2816-184">Dispositivos desconectados são considerados não compatíveis e serão impedidos de acessar seus aplicativos da empresa com base nas políticas de acesso condicional do Intune.</span><span class="sxs-lookup"><span data-stu-id="c2816-184">Disconnected devices are considered as non-compliant and will be blocked from accessing your company applications based on the Intune conditional access policies.</span></span> <span data-ttu-id="c2816-185">Você pode especificar valores entre 1 e 90 dias.</span><span class="sxs-lookup"><span data-stu-id="c2816-185">You can specify values between 1 and 90 days.</span></span>

![Configurações de registro do Lookout](./media/lookout-console-enrollment-settings.png)

## <span data-ttu-id="c2816-187">Configurar notificações por email</span><span class="sxs-lookup"><span data-stu-id="c2816-187">Configure email notifications</span></span>
<a id="configure-email-notifications" class="xliff"></a>
<span data-ttu-id="c2816-188">Se desejar receber alertas de ameaças por email, conecte-se ao [console do Lookout](https://aad.lookout.com) com a conta de usuário que deverá receber as notificações.</span><span class="sxs-lookup"><span data-stu-id="c2816-188">If you want to receive email alerts for threats, sign in to the [Lookout console](https://aad.lookout.com) with the user account that should receive notifications.</span></span> <span data-ttu-id="c2816-189">Na guia **Preferências** do módulo **Sistema**, escolha os níveis de ameaças que devem emitir notificações e defina-os como **ATIVADO**.</span><span class="sxs-lookup"><span data-stu-id="c2816-189">On the **Preferences** tab of the **System** module, choose the threat levels that should  notifications and set them to **ON**.</span></span> <span data-ttu-id="c2816-190">Salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="c2816-190">Save your changes.</span></span>

<span data-ttu-id="c2816-191">![captura de tela da página Preferências com a conta de usuário exibida](./media/lookout-mtp-email-notifications.png) Se não quiser receber notificações por email, defina as notificações como **DESATIVADO** e salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="c2816-191">![screenshot of the preferences page with the user account displayed](./media/lookout-mtp-email-notifications.png) If you no longer want to receive email notifications, set the notifications to **OFF** and save your changes.</span></span>

### <span data-ttu-id="c2816-192">Configurar a classificação de ameaças</span><span class="sxs-lookup"><span data-stu-id="c2816-192">Configure threat classification</span></span>
<a id="configure-threat-classification" class="xliff"></a>
<span data-ttu-id="c2816-193">A Defesa contra Ameaças Móveis do Lookout classifica ameaças móveis de vários tipos.</span><span class="sxs-lookup"><span data-stu-id="c2816-193">Lookout Mobile Threat Defense classifies mobile threats of various types.</span></span> <span data-ttu-id="c2816-194">As [classificações de ameaças do Lookout](http://personal.support.lookout.com/hc/articles/114094130693) têm níveis de risco padrão associados a elas.</span><span class="sxs-lookup"><span data-stu-id="c2816-194">The [Lookout threat classifications](http://personal.support.lookout.com/hc/articles/114094130693) have default risk levels associated with them.</span></span> <span data-ttu-id="c2816-195">Elas podem ser alteradas a qualquer momento de acordo com os requisitos de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="c2816-195">These can be changed at any time to suit your company requirements.</span></span>
=======
    > O **Nome de Exibição** diferencia maiúsculas de minúsculas, conforme mostrado nas **Propriedades** do grupo de segurança no Portal do Azure. Conforme mostrado na imagem abaixo, o **Nome de Exibição** do grupo de segurança tem minúsculas concatenadas, enquanto o título tem todas as letras minúsculas. No console do Lookout, faça a correspondência de maiúsculas e minúsculas do **Nome de Exibição** do grupo de segurança.
    >![captura de tela do portal do Azure, serviço do Azure Active Directory, página de propriedades](./media/aad-group-display-name.png)

    >[!NOTE] 
    >A melhor prática é deixar o padrão (5 minutos) para o incremento de tempo para verificar se há novos dispositivos. Limitações atuais, **O Lookout não consegue validar os nomes de exibição do grupo:** Verifique se o campo **NOME DE EXIBIÇÃO** no Portal do Azure corresponde exatamente ao grupo de segurança do Azure AD. **Não há suporte para a criação de grupos aninhados:** os grupos de segurança do Azure AD usados no Lookout devem conter somente usuários. Eles não podem conter outros grupos.

3.  Depois que um grupo for adicionado, na próxima vez que um usuário abrir o aplicativo Lookout for Work em seu dispositivo com suporte, o dispositivo estará ativado no Lookout.

4.  Quando estiver satisfeito com os resultados, estenda o registro para grupos de usuários adicionais.

## Configurar a sincronização de estado
<a id="configure-state-sync" class="xliff"></a>
Na opção **Sincronização de Estado**, especifique o tipo de dados que deve ser enviado ao Intune.  O status do dispositivo e o status da ameaça são necessários para que a integração do Lookout com o Intune funcione corretamente. Essas configurações são habilitadas por padrão.

## Configurar informações do destinatário do email de relatório de erros
<a id="configure-error-report-email-recipient-information" class="xliff"></a>
Na opção **Gerenciamento de Erros**, insira o endereço de email que deve receber os relatórios de erros.

![captura de tela da página de gerenciamento de erros do conector do Intune](./media/lookout-mtp-connector-error-notifications.png)

## Definir configurações de registro
<a id="configure-enrollment-settings" class="xliff"></a>
No módulo **Sistema**, na página **Conectores**, especifique o número de dias antes que um dispositivo seja considerado desconectado.  Dispositivos desconectados são considerados não compatíveis e serão impedidos de acessar seus aplicativos da empresa com base nas políticas de acesso condicional do Intune. Você pode especificar valores entre 1 e 90 dias.

![Configurações de registro do Lookout](./media/lookout-console-enrollment-settings.png)

## Configurar notificações por email
<a id="configure-email-notifications" class="xliff"></a>
Se desejar receber alertas de ameaças por email, conecte-se ao [console do Lookout](https://aad.lookout.com) com a conta de usuário que deverá receber as notificações. Na guia **Preferências** do módulo **Sistema**, escolha os níveis de ameaças que devem emitir notificações e defina-os como **ATIVADO**. Salve as alterações.

![captura de tela da página Preferências com a conta de usuário exibida](./media/lookout-mtp-email-notifications.png) Se não quiser receber notificações por email, defina as notificações como **DESATIVADO** e salve as alterações.

### Configurar a classificação de ameaças
<a id="configure-threat-classification" class="xliff"></a>
A Defesa contra Ameaças Móveis do Lookout classifica ameaças móveis de vários tipos. As [classificações de ameaças do Lookout](http://personal.support.lookout.com/hc/articles/114094130693) têm níveis de risco padrão associados a elas. Elas podem ser alteradas a qualquer momento de acordo com os requisitos de sua empresa.
>>>>>>> live

![captura de tela da página de política mostrando ameaças e classificações](./media/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
<<<<<<< HEAD
> <span data-ttu-id="c2816-197">Os níveis de risco são um aspecto importante da Defesa contra Ameaças Móveis, porque a integração com o Intune calcula a conformidade do dispositivo de acordo com esses níveis de risco em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="c2816-197">Risk levels are an important aspect of Mobile Threat Defense because the Intune integration calculates device compliance according to these risk levels at runtime.</span></span> <span data-ttu-id="c2816-198">O administrador do Intune define uma regra na política para identificar um dispositivo que não está em conformidade se ele tem uma ameaça ativa com um nível mínimo de **Alto**, **Médio** ou **Baixo**.</span><span class="sxs-lookup"><span data-stu-id="c2816-198">The Intune administrator sets a rule in policy to identify a device as non-compliant if the device has an active threat with a minimum level of **High**, **Medium**, or **Low**.</span></span> <span data-ttu-id="c2816-199">A política de classificação de ameaças na Defesa contra Ameaças Móveis do Lookout alimenta diretamente o cálculo de conformidade no Intune.</span><span class="sxs-lookup"><span data-stu-id="c2816-199">The threat classification policy in Lookout Mobile Threat Defense directly drives the device compliance calculation in Intune.</span></span>

## <span data-ttu-id="c2816-200">Verificar o registro</span><span class="sxs-lookup"><span data-stu-id="c2816-200">Watching enrollment</span></span>
<a id="watching-enrollment" class="xliff"></a>
<span data-ttu-id="c2816-201">Quando a instalação estiver concluída, a Defesa contra Ameaças Móveis do Lookout começa a sondar o Azure AD em busca de dispositivos que correspondem aos grupos de registro especificados.</span><span class="sxs-lookup"><span data-stu-id="c2816-201">Once the setup is complete, Lookout Mobile Threat Defense starts to poll Azure AD for devices that correspond to the specified enrollment groups.</span></span>  <span data-ttu-id="c2816-202">Você pode encontrar informações sobre os dispositivos registrados no módulo Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c2816-202">You can find information about the devices enrolled on the Devices module.</span></span>  <span data-ttu-id="c2816-203">O status inicial dos dispositivos é mostrado como pendente.</span><span class="sxs-lookup"><span data-stu-id="c2816-203">The initial status for devices is shown as pending.</span></span>  <span data-ttu-id="c2816-204">O status do dispositivo será alterado quando o aplicativo Lookout for Work estiver instalado, aberto e ativado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2816-204">The device status changes once the Lookout for Work app is installed, opened, and activated on the device.</span></span>  <span data-ttu-id="c2816-205">Para ver detalhes sobre como fazer o aplicativo Lookout for Work ser enviado por push para o dispositivo, consulte o tópico [Adicionar aplicativos Lookout for Work com o Intune](mtd-apps-ios-app-configuration-policy-add-assign.md).</span><span class="sxs-lookup"><span data-stu-id="c2816-205">For details on how to get the Lookout for Work app pushed to the device, see the [Add Lookout for work apps with Intune](mtd-apps-ios-app-configuration-policy-add-assign.md) topic.</span></span>
## <span data-ttu-id="c2816-206">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c2816-206">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="c2816-207">Habilitar conexão do Lookout MTD no Intune</span><span class="sxs-lookup"><span data-stu-id="c2816-207">Enable Lookout MTD connection Intune</span></span>](mtd-connector-enable.md)
=======
> Os níveis de risco são um aspecto importante da Defesa contra Ameaças Móveis, porque a integração com o Intune calcula a conformidade do dispositivo de acordo com esses níveis de risco em tempo de execução. O administrador do Intune define uma regra na política para identificar um dispositivo que não está em conformidade se ele tem uma ameaça ativa com um nível mínimo de **Alto**, **Médio** ou **Baixo**. A política de classificação de ameaças na Defesa contra Ameaças Móveis do Lookout alimenta diretamente o cálculo de conformidade no Intune.

## Verificar o registro
<a id="watching-enrollment" class="xliff"></a>
Quando a instalação estiver concluída, a Defesa contra Ameaças Móveis do Lookout começa a sondar o Azure AD em busca de dispositivos que correspondem aos grupos de registro especificados.  Você pode encontrar informações sobre os dispositivos registrados no módulo Dispositivos.  O status inicial dos dispositivos é mostrado como pendente.  O status do dispositivo será alterado quando o aplicativo Lookout for Work estiver instalado, aberto e ativado no dispositivo.  Para ver detalhes sobre como fazer o aplicativo Lookout for Work ser enviado por push para o dispositivo, consulte o tópico [Adicionar aplicativos Lookout for Work com o Intune](mtd-apps-ios-app-configuration-policy-add-assign.md).
## Próximas etapas
<a id="next-steps" class="xliff"></a>
[Habilitar conexão do Lookout MTD no Intune](mtd-connector-enable.md)
>>>>>>> live
