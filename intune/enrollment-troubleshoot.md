---
title: Solucionar problemas de registro de dispositivo
titleSuffix: Intune on Azure
description: Saiba como solucionar problemas de registro de dispositivo.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c324c74e-e225-40ad-88b7-72a6d9ea09b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9b7af9168164f1cccf3feae5bbdfd8014f8c7c1f
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <span data-ttu-id="b8486-103">Solução de problemas de registro de dispositivo no Intune</span><span class="sxs-lookup"><span data-stu-id="b8486-103">Troubleshoot device enrollment in Intune</span></span>
<a id="troubleshoot-device-enrollment-in-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b8486-104">Este tópico fornece sugestões para solução de problemas de registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b8486-104">This topic provides suggestions for troubleshooting device enrollment issues.</span></span> <span data-ttu-id="b8486-105">Se essas informações não resolverem seu problema, confira [How to get support for Microsoft Intune](https://docs.microsoft.com/intune-classic/troubleshoot/get-support) (Como obter suporte para o Microsoft Intune) para encontrar outras formas de obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="b8486-105">If this information does not solve your problem, see [How to get support for Microsoft Intune](https://docs.microsoft.com/intune-classic/troubleshoot/get-support) to find more ways to get help.</span></span>


## <span data-ttu-id="b8486-106">Etapas para solução de problemas iniciais</span><span class="sxs-lookup"><span data-stu-id="b8486-106">Initial troubleshooting steps</span></span>
<a id="initial-troubleshooting-steps" class="xliff"></a>

<span data-ttu-id="b8486-107">Antes de iniciar a solução de problemas, verifique se você configurou o Intune corretamente para habilitar o registro.</span><span class="sxs-lookup"><span data-stu-id="b8486-107">Before you begin troubleshooting, ensure that you configured Intune correctly to enable enrollment.</span></span> <span data-ttu-id="b8486-108">Consulte [Registrar dispositivos Android e Standard Knox](android-enroll.md) para ver links para etapas de registro para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="b8486-108">See [Enroll Android and Standard Knox devices](android-enroll.md) for links to enrollment steps for each platform.</span></span>

<span data-ttu-id="b8486-109">Seus usuários de dispositivo gerenciado podem coletar logs de registro e diagnóstico para você examinar.</span><span class="sxs-lookup"><span data-stu-id="b8486-109">Your managed device users can collect enrollment and diagnostic logs for you to review.</span></span> <span data-ttu-id="b8486-110">As instruções para o usuário coletar logs são fornecidas em:</span><span class="sxs-lookup"><span data-stu-id="b8486-110">User instructions for collecting logs are provided in:</span></span>

- [<span data-ttu-id="b8486-111">Enviar erros de registro do Android ao seu administrador de TI</span><span class="sxs-lookup"><span data-stu-id="b8486-111">Send Android enrollment errors to your IT admin</span></span>](https://docs.microsoft.com/intune-user-help/send-enrollment-errors-to-your-it-admin-android)
- [<span data-ttu-id="b8486-112">Enviar erros do iOS para o administrador de TI</span><span class="sxs-lookup"><span data-stu-id="b8486-112">Send iOS errors to your IT admin</span></span>](https://docs.microsoft.com/intune-user-help/send-errors-to-your-it-admin-ios)

## <span data-ttu-id="b8486-113">Problemas gerais de registro</span><span class="sxs-lookup"><span data-stu-id="b8486-113">General enrollment issues</span></span>
<a id="general-enrollment-issues" class="xliff"></a>
<span data-ttu-id="b8486-114">Esses problemas podem ocorrer em todas as plataformas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b8486-114">These issues may occur on all device platforms.</span></span>

### <span data-ttu-id="b8486-115">Limite do dispositivo associado</span><span class="sxs-lookup"><span data-stu-id="b8486-115">Device cap reached</span></span>
<a id="device-cap-reached" class="xliff"></a>
<span data-ttu-id="b8486-116">**Problema:** um usuário recebe um erro no seu dispositivo durante o registro, como um erro **Portal da empresa temporariamente indisponível** em um dispositivo iOS, e o DMPdownloader.log no Configuration Manager contém o erro **DeviceCapReached**.</span><span class="sxs-lookup"><span data-stu-id="b8486-116">**Issue:** A user receives an error on their device during enrollment, such as a **Company Portal Temporarily Unavailable** error on an iOS device, and the DMPdownloader.log on Configuration Manager contains the error **DeviceCapReached**.</span></span>

<span data-ttu-id="b8486-117">**Resolução:**</span><span class="sxs-lookup"><span data-stu-id="b8486-117">**Resolution:**</span></span>

#### <span data-ttu-id="b8486-118">Verifique o número de dispositivos registrados e permitidos</span><span class="sxs-lookup"><span data-stu-id="b8486-118">Check number of devices enrolled and allowed</span></span>
<a id="check-number-of-devices-enrolled-and-allowed" class="xliff"></a>

<span data-ttu-id="b8486-119">No portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="b8486-119">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span> <span data-ttu-id="b8486-120">Na folha do Intune do Portal do Azure, vá para **Registrar dispositivos** > **Restrições de Registro** e valide se o usuário não tem mais do que o máximo permitido de 15 dispositivos atribuídos.</span><span class="sxs-lookup"><span data-stu-id="b8486-120">On the Intune blade of the Azure portal, go to **Enroll devices** > **Enrollment Restrictions** and validate that the user has no more than the allowable maximum of 15 devices assigned.</span></span>

<!--- Mobile device users can delete devices at the following URL: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/). --->

<span data-ttu-id="b8486-121">Os administradores podem excluir dispositivos no portal do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b8486-121">Administrators can delete devices in the Azure Active Directory portal.</span></span>

#### <span data-ttu-id="b8486-122">Para excluir dispositivos no portal do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="b8486-122">To delete devices in the Azure Active Directory portal</span></span>
<a id="to-delete-devices-in-the-azure-active-directory-portal" class="xliff"></a>

1.  <span data-ttu-id="b8486-123">Navegue até [http://aka.ms/accessaad](http://aka.ms/accessaad) ou clique em **Administrador** &gt; **Azure AD** de [https://portal.office.com](https://portal.office.com).</span><span class="sxs-lookup"><span data-stu-id="b8486-123">Browse to [http://aka.ms/accessaad](http://aka.ms/accessaad) or choose **Admin** &gt; **Azure AD** from [https://portal.office.com](https://portal.office.com).</span></span>

2.  <span data-ttu-id="b8486-124">Faça logon com sua ID da organização usando o link no lado esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="b8486-124">Log in with your Org ID using the link on the left side of the page.</span></span>

3.  <span data-ttu-id="b8486-125">Se não tiver uma, crie uma assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="b8486-125">Create an Azure Subscription if you don’t have one.</span></span> <span data-ttu-id="b8486-126">Isso não deverá exigir um cartão de crédito ou pagamento se você tiver uma conta paga (clique no link de assinatura **Register your free Azure Active Directory** [Registrar seu Azure Active Directory gratuito]).</span><span class="sxs-lookup"><span data-stu-id="b8486-126">This should not require a credit card or payment if you have a paid account (choose the **Register your free Azure Active Directory** subscription link).</span></span>

4.  <span data-ttu-id="b8486-127">Selecione **Active Directory** e selecione sua organização.</span><span class="sxs-lookup"><span data-stu-id="b8486-127">Select **Active Directory** and then select your organization.</span></span>

5.  <span data-ttu-id="b8486-128">Selecione a guia **Usuários** .</span><span class="sxs-lookup"><span data-stu-id="b8486-128">Select the **Users** tab.</span></span>

6.  <span data-ttu-id="b8486-129">Selecione o usuário cujos dispositivos que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="b8486-129">Select the user whose devices you want to delete.</span></span>

7.  <span data-ttu-id="b8486-130">Escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b8486-130">Choose **Devices**.</span></span>

8.  <span data-ttu-id="b8486-131">Remova os dispositivos conforme apropriado, como aqueles que não estão mais em uso, ou aqueles que têm definições imprecisas.</span><span class="sxs-lookup"><span data-stu-id="b8486-131">Remove devices as appropriate, such as those that are no longer in use, or those that have inaccurate definitions.</span></span>

> [!NOTE]

> <span data-ttu-id="b8486-132">Você pode evitar o limite de registro de dispositivo usando gerenciadores de registro do dispositivo, conforme descrito em [Registrar dispositivos usando o Gerenciador de registro de dispositivo](device-enrollment-manager-enroll.md).</span><span class="sxs-lookup"><span data-stu-id="b8486-132">You can avoid the device enrollment cap by using Device Enrollment Managers, as described in [Enroll devices using device enrollment manager](device-enrollment-manager-enroll.md).</span></span>
>
> <span data-ttu-id="b8486-133">Uma conta de usuário que é adicionada ao grupo de Gerenciadores de Registro de Dispositivos não conseguirá concluir o registro quando a política de acesso condicional for aplicada a esse logon de usuário específico.</span><span class="sxs-lookup"><span data-stu-id="b8486-133">A user account that is added to Device Enrollment Managers group will not be able to complete enrollment when Conditional Access policy is enforced for that specific user login.</span></span>

### <span data-ttu-id="b8486-134">Portal da empresa temporariamente indisponível</span><span class="sxs-lookup"><span data-stu-id="b8486-134">Company Portal Temporarily Unavailable</span></span>
<a id="company-portal-temporarily-unavailable" class="xliff"></a>
<span data-ttu-id="b8486-135">**Problema:** um usuário recebe um erro de **Portal da empresa temporariamente indisponível** no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b8486-135">**Issue:** A user receives a **Company Portal Temporarily Unavailable** error on their device.</span></span>

<span data-ttu-id="b8486-136">**Resolução:**</span><span class="sxs-lookup"><span data-stu-id="b8486-136">**Resolution:**</span></span>

1.  <span data-ttu-id="b8486-137">Remova o aplicativo de Portal da Empresa do Intune do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b8486-137">Remove the Intune Company Portal app from the device.</span></span>

2.  <span data-ttu-id="b8486-138">No dispositivo, abra o navegador, navegue até [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com), e tente algum logon de usuário.</span><span class="sxs-lookup"><span data-stu-id="b8486-138">On the device, open the browser, browse to [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com), and attempt a user login.</span></span>

3.  <span data-ttu-id="b8486-139">Se o usuário não conseguir efetuar logon, faça-o tentar outra rede.</span><span class="sxs-lookup"><span data-stu-id="b8486-139">If the user fails to log in, have them try another network.</span></span>

4.  <span data-ttu-id="b8486-140">Se isso falhar, confirme que as credenciais do usuário foram sincronizadas corretamente com o Active Directory do Azure.</span><span class="sxs-lookup"><span data-stu-id="b8486-140">If that fails, validate that the user’s credentials have synced correctly with Azure Active Directory.</span></span>

5.  <span data-ttu-id="b8486-141">Se o usuário fizer logon com êxito, um dispositivo iOS solicitará que você instale o aplicativo de Portal da Empresa do Intune e o registre.</span><span class="sxs-lookup"><span data-stu-id="b8486-141">If the user successfully logs in, an iOS device will prompt you to install the Intune Company Portal app and enroll.</span></span> <span data-ttu-id="b8486-142">Em um dispositivo Android, você precisará instalar manualmente o aplicativo de Portal da Empresa do Intune, e depois disso você poderá tentar novamente a inscrição.</span><span class="sxs-lookup"><span data-stu-id="b8486-142">On an Android device you will need to manually install the Intune Company Portal app, after which you can retry enrolling.</span></span>

### <span data-ttu-id="b8486-143">Autoridade MDM não definida</span><span class="sxs-lookup"><span data-stu-id="b8486-143">MDM authority not defined</span></span>
<a id="mdm-authority-not-defined" class="xliff"></a>
<span data-ttu-id="b8486-144">**Problema:** um usuário recebe um erro de **Autoridade MDM não definida**.</span><span class="sxs-lookup"><span data-stu-id="b8486-144">**Issue:** A user receives an **MDM authority not defined** error.</span></span>

<span data-ttu-id="b8486-145">**Resolução:**</span><span class="sxs-lookup"><span data-stu-id="b8486-145">**Resolution:**</span></span>

1.  <span data-ttu-id="b8486-146">Verifique se a Autoridade MDM foi definida corretamente para o tipo de serviço do Intune que está usando (isto é, Intune, Office 365 ou System Center Configuration Manager com Intune).</span><span class="sxs-lookup"><span data-stu-id="b8486-146">Verify that the MDM Authority has been set appropriately for the type of Intune service you are using (that is, Intune, Office 365, or System Center Configuration Manager with Intune).</span></span> <span data-ttu-id="b8486-147">Consulte [Definir a autoridade de gerenciamento de dispositivo móvel](mdm-authority-set.md) para ver instruções.</span><span class="sxs-lookup"><span data-stu-id="b8486-147">See [Set the mobile device management authority](mdm-authority-set.md) for instructions.</span></span>

    > [!NOTE]    
    > <span data-ttu-id="b8486-148">No Configuration Manager versão 1610 ou posterior e no Microsoft Intune versão 1705, você altera a autoridade de MDM sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes.</span><span class="sxs-lookup"><span data-stu-id="b8486-148">In Configuration Manager version 1610 or later and Microsoft Intune version 1705, you change the MDM authority without having to contact Microsoft Support, and without having to unenroll and reenroll your existing managed devices.</span></span> <span data-ttu-id="b8486-149">Para obter detalhes, consulte [O que fazer se você escolher a configuração incorreta de autoridade de MDM](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).</span><span class="sxs-lookup"><span data-stu-id="b8486-149">For details, see [What to do if you choose the wrong MDM authority setting](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).</span></span>

2.  <span data-ttu-id="b8486-150">Verifique se as credenciais do usuário foram sincronizadas corretamente com o Active Directory do Azure, verificando se seu UPN corresponde às informações do Active Directory no Portal da conta.</span><span class="sxs-lookup"><span data-stu-id="b8486-150">Verify that the user’s credentials have synced correctly with Azure Active Directory, by checking that their UPN matches the Active Directory information in the Account Portal.</span></span>
    <span data-ttu-id="b8486-151">Se o UPN não coincidir com as informações do Active Directory:</span><span class="sxs-lookup"><span data-stu-id="b8486-151">If the UPN does not match the Active Directory information:</span></span>

    1.  <span data-ttu-id="b8486-152">Desligue o DirSync no servidor local.</span><span class="sxs-lookup"><span data-stu-id="b8486-152">Turn off DirSync on the local server.</span></span>

    2.  <span data-ttu-id="b8486-153">Exclua o usuário incompatível da lista de usuários do **Portal de Contas do Intune** .</span><span class="sxs-lookup"><span data-stu-id="b8486-153">Delete the mismatched user from the **Intune Account Portal** user list.</span></span>

    3.  <span data-ttu-id="b8486-154">Aguarde cerca de uma hora para permitir que o serviço do Azure remova os dados incorretos.</span><span class="sxs-lookup"><span data-stu-id="b8486-154">Wait about one hour to allow the Azure service to remove the incorrect data.</span></span>

    4.  <span data-ttu-id="b8486-155">Ative o DirSync novamente e verifique se agora o usuário está sincronizado corretamente.</span><span class="sxs-lookup"><span data-stu-id="b8486-155">Turn on DirSync again and check if the user is now synced properly.</span></span>

3.  <span data-ttu-id="b8486-156">Em um cenário em que você estiver usando o System Center Configuration Manager com o Intune, verifique se o usuário tem uma ID de usuário de nuvem válida:</span><span class="sxs-lookup"><span data-stu-id="b8486-156">In a scenario where you are using System Center Configuration Manager with Intune, verify that the user has a valid Cloud User ID:</span></span>

    1.  <span data-ttu-id="b8486-157">Abra o SQL Management Studio.</span><span class="sxs-lookup"><span data-stu-id="b8486-157">Open SQL Management Studio.</span></span>

    2.  <span data-ttu-id="b8486-158">Conecte-se ao banco de dados apropriado.</span><span class="sxs-lookup"><span data-stu-id="b8486-158">Connect to the appropriate database.</span></span>

    3.  <span data-ttu-id="b8486-159">Abra a pasta de bancos de dados e localize e abra a pasta **CM_DBName**, em que DBName é o nome do banco de dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="b8486-159">Open the databases folder and find and open the **CM_DBName** folder, where DBName is the name of the customer database.</span></span>

    4.  <span data-ttu-id="b8486-160">Na parte superior, escolha **Nova Consulta** e execute as seguintes consultas:</span><span class="sxs-lookup"><span data-stu-id="b8486-160">At the top, choose **New Query**  and execute the following queries:</span></span>

        -   <span data-ttu-id="b8486-161">Para ver todos os usuários: `select * from [CM_ DBName].[dbo].[User_DISC]`</span><span class="sxs-lookup"><span data-stu-id="b8486-161">To see all users: `select * from [CM_ DBName].[dbo].[User_DISC]`</span></span>

        -   <span data-ttu-id="b8486-162">Para ver Usuários Específicos, use a seguinte consulta, em que %testuser1% representa username@domain.com para o usuário que você deseja pesquisar: `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`</span><span class="sxs-lookup"><span data-stu-id="b8486-162">To see Specific Users, use the following query, where %testuser1% represents username@domain.com for the user you want to look up: `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`</span></span>

        <span data-ttu-id="b8486-163">Depois de gravar a consulta, escolha **!Execute**.</span><span class="sxs-lookup"><span data-stu-id="b8486-163">After writing the query choose **!Execute**.</span></span>
        <span data-ttu-id="b8486-164">Após os resultados serem retornados, procure a ID do clouduser.</span><span class="sxs-lookup"><span data-stu-id="b8486-164">Once the results have been returned, look for the clouduser ID.</span></span>  <span data-ttu-id="b8486-165">Se nenhuma ID for encontrada, o usuário não está licenciado para usar o Intune.</span><span class="sxs-lookup"><span data-stu-id="b8486-165">If no ID is found, the user isn't licensed to use Intune.</span></span>

### <span data-ttu-id="b8486-166">Não é possível criar a política ou registrar os dispositivos se o nome da empresa contiver caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="b8486-166">Unable to create policy or enroll devices if the company name contains special characters</span></span>
<a id="unable-to-create-policy-or-enroll-devices-if-the-company-name-contains-special-characters" class="xliff"></a>
<span data-ttu-id="b8486-167">**Problema:** não é possível criar a política ou registrar os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b8486-167">**Issue:** You can't create policy or enroll devices.</span></span>

<span data-ttu-id="b8486-168">**Resolução:** no [Centro de administração do Office 365](https://portal.office.com/), remova os caracteres especiais do nome da empresa e salve as informações da empresa.</span><span class="sxs-lookup"><span data-stu-id="b8486-168">**Resolution:** In the [Office 365 admin center](https://portal.office.com/), remove the special characters from the company name and save the company information.</span></span>

### <span data-ttu-id="b8486-169">Não é possível entrar ou registrar dispositivos quando você tiver vários domínios verificados</span><span class="sxs-lookup"><span data-stu-id="b8486-169">Unable to log in or enroll devices when you have multiple verified domains</span></span>
<a id="unable-to-log-in-or-enroll-devices-when-you-have-multiple-verified-domains" class="xliff"></a>
<span data-ttu-id="b8486-170">**Problema:** quando você adiciona um segundo domínio verificado ao seu ADFS, os usuários com o sufixo de nome UPN do segundo domínio não poderão fazer logon nos portais ou registrar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b8486-170">**Issue:** When you add a second verified domain to your ADFS, users with the user principal name (UPN) suffix of the second domain may not be able to log into the portals or enroll devices.</span></span>


<span data-ttu-id="b8486-171">**Resolução:** os clientes do Microsoft Office 365 que utilizarem o logon único (SSO) por meio do AD FS 2.0 e tiverem vários domínios de nível superior para sufixos UPN de usuários em sua organização (por exemplo, @contoso.com ou @fabrikam.com) deverão implantar uma instância separada do Serviço de Federação AD FS 2.0 em cada sufixo.</span><span class="sxs-lookup"><span data-stu-id="b8486-171">**Resolution:** Microsoft Office 365 customers who utilize single sign-on (SSO) through AD FS 2.0 and have multiple top level domains for users' UPN suffixes within their organization (for example, @contoso.com or @fabrikam.com) are required to deploy a separate instance of the AD FS 2.0 Federation Service for each suffix.</span></span>  <span data-ttu-id="b8486-172">Agora, há um [pacote cumulativo de atualizações para o AD FS 2.0](http://support.microsoft.com/kb/2607496) que funciona em conjunto com o comutador **SupportMultipleDomain** para habilitar o servidor AD FS, para dar suporte a esse cenário sem a necessidade de exigir servidores AD FS 2.0 adicionais.</span><span class="sxs-lookup"><span data-stu-id="b8486-172">There is now a [rollup for AD FS 2.0](http://support.microsoft.com/kb/2607496) that works in conjunction with the **SupportMultipleDomain** switch to enable the AD FS server to support this scenario without requiring additional AD FS 2.0 servers.</span></span> <span data-ttu-id="b8486-173">Confira [este blog](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b8486-173">See [this blog](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/) for more information.</span></span>


## <span data-ttu-id="b8486-174">Problemas de Android</span><span class="sxs-lookup"><span data-stu-id="b8486-174">Android issues</span></span>
<a id="android-issues" class="xliff"></a>
### <span data-ttu-id="b8486-175">Os dispositivos apresentaram falha no check-in com o serviço do Intune e são exibidos como "Não íntegro" no console de administração do Intune</span><span class="sxs-lookup"><span data-stu-id="b8486-175">Devices fail to check in with the Intune service and display as "Unhealthy" in the Intune admin console</span></span>
<a id="devices-fail-to-check-in-with-the-intune-service-and-display-as-unhealthy-in-the-intune-admin-console" class="xliff"></a>
<span data-ttu-id="b8486-176">**Problema:** alguns dispositivos Samsung que estão executando versões do Android 4.4 e 5.x podem interromper a verificação com o serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="b8486-176">**Issue:** Some Samsung devices that are running Android versions 4.4.x and 5.x might stop checking in with the Intune service.</span></span> <span data-ttu-id="b8486-177">Se os dispositivos não fizerem o check-in:</span><span class="sxs-lookup"><span data-stu-id="b8486-177">If devices don't check in:</span></span>

- <span data-ttu-id="b8486-178">Eles não poderão receber políticas, aplicativos e comandos remotos do serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="b8486-178">They can't receive policy, apps, and remote commands from the Intune service.</span></span>
- <span data-ttu-id="b8486-179">Eles mostram um Estado de Gerenciamento **não íntegro** no console do administrador.</span><span class="sxs-lookup"><span data-stu-id="b8486-179">They show a Management State of **Unhealthy** in the administrator console.</span></span>
- <span data-ttu-id="b8486-180">Os usuários que são protegidos por políticas de acesso condicional podem perder o acesso aos recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="b8486-180">Users who are protected by conditional access policies might lose access to corporate resources.</span></span>

<span data-ttu-id="b8486-181">A Samsung confirmou que o software do Gerenciador Inteligente Samsung, que é fornecido em certos dispositivos Samsung, pode desativar o Portal da Empresa do Intune e seus componentes.</span><span class="sxs-lookup"><span data-stu-id="b8486-181">Samsung has confirmed that the Samsung Smart Manager software, which ships on certain Samsung devices, can deactivate the Intune Company Portal and its components.</span></span> <span data-ttu-id="b8486-182">Quando o Portal da Empresa está em um estado desativado, ele não pode ser executado em segundo plano e, portanto, não pode contatar o serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="b8486-182">When Company Portal is in a deactivated state, it can't run in the background and therefore can't contact the Intune service.</span></span>

<span data-ttu-id="b8486-183">**Resolução nº1:**</span><span class="sxs-lookup"><span data-stu-id="b8486-183">**Resolution #1:**</span></span>

<span data-ttu-id="b8486-184">Avise os usuários para iniciar o aplicativo do Portal da Empresa manualmente.</span><span class="sxs-lookup"><span data-stu-id="b8486-184">Tell your users to start the Company Portal app manually.</span></span> <span data-ttu-id="b8486-185">Depois que o aplicativo for reiniciado, o dispositivo faz o check-in no serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="b8486-185">Once the app restarts, the device checks in with the Intune service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8486-186">Abrir o aplicativo do Portal da Empresa manualmente é uma solução temporária, pois o Gerenciador Inteligente Samsung pode desativar o aplicativo do Portal da Empresa novamente.</span><span class="sxs-lookup"><span data-stu-id="b8486-186">Opening the Company Portal app manually is a temporary solution, because Samsung Smart Manager may deactivate the Company Portal app again.</span></span>

<span data-ttu-id="b8486-187">**Resolução nº2:**</span><span class="sxs-lookup"><span data-stu-id="b8486-187">**Resolution #2:**</span></span>

<span data-ttu-id="b8486-188">Peça aos usuários que tentem atualizar para o Android 6.0.</span><span class="sxs-lookup"><span data-stu-id="b8486-188">Tell your users to try upgrading to Android 6.0.</span></span> <span data-ttu-id="b8486-189">O problema de desativação não ocorre em dispositivos Android 6.0.</span><span class="sxs-lookup"><span data-stu-id="b8486-189">The deactivation issue doesn't occur on Android 6.0 devices.</span></span> <span data-ttu-id="b8486-190">Para verificar se uma atualização está disponível, os usuários podem ir até **Configurações** > **Sobre dispositivo** > **Baixar atualizações manualmente** e siga as instruções no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b8486-190">To check if an update is available, users can go to **Settings** > **About device** > **Download updates manually**, and follow the prompts on the device.</span></span>

<span data-ttu-id="b8486-191">**Resolução nº3:**</span><span class="sxs-lookup"><span data-stu-id="b8486-191">**Resolution #3:**</span></span>

<span data-ttu-id="b8486-192">Se a Resolução nº2 não funcionar, oriente os usuários a seguir estas etapas para fazer com que o Gerenciador Inteligente exclua o aplicativo do Portal da Empresa:</span><span class="sxs-lookup"><span data-stu-id="b8486-192">If Resolution #2 doesn't work, have your users follow these steps to make Smart Manager exclude the  Company Portal app:</span></span>

1. <span data-ttu-id="b8486-193">Inicie o aplicativo Gerenciador Inteligente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b8486-193">Launch the Smart Manager app on the device.</span></span>

  ![Selecione o ícone do Gerenciador Inteligente no dispositivo](./media/smart-manager-app-icon.png)

2. <span data-ttu-id="b8486-195">Escolha o bloco **Bateria**.</span><span class="sxs-lookup"><span data-stu-id="b8486-195">Choose the **Battery** tile.</span></span>

  ![Selecione o bloco Bateria](./media/smart-manager-battery-tile.png)

3. <span data-ttu-id="b8486-197">Em **Economia de energia do aplicativo** ou em **Otimização do aplicativo**, selecione **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b8486-197">Under **App power saving** or **App optimization**, select **Detail**.</span></span>

  ![Selecione Detalhes em Economia de energia do aplicativo ou em Otimização de aplicativo](./media/smart-manager-app-power-saving-detail.png)

4. <span data-ttu-id="b8486-199">Escolha **Portal da Empresa** na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b8486-199">Choose **Company Portal** from the list of apps.</span></span>

  ![Selecione o Portal da Empresa na lista de aplicativos](./media/smart-manager-company-portal.png)

5. <span data-ttu-id="b8486-201">Escolha **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="b8486-201">Choose **Turned off**.</span></span>

  ![Selecione Desativado na caixa de diálogo Otimização de aplicativo](./media/smart-manager-app-optimization-turned-off.png)

6. <span data-ttu-id="b8486-203">Em **Economia de energia do aplicativo** ou em **Otimização do aplicativo**, confirme se o Portal da Empresa está desativado.</span><span class="sxs-lookup"><span data-stu-id="b8486-203">Under **App power saving** or **App optimization**, confirm that Company Portal is turned off.</span></span>

  ![Verifique se o Portal da Empresa está desativado](./media/smart-manager-verify-comp-portal-turned-off.png)


### <span data-ttu-id="b8486-205">Falha na instalação do perfil</span><span class="sxs-lookup"><span data-stu-id="b8486-205">Profile installation failed</span></span>
<a id="profile-installation-failed" class="xliff"></a>
<span data-ttu-id="b8486-206">**Problema:** um usuário recebe um erro de **Falha na instalação de perfil** em um dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="b8486-206">**Issue:** A user receives a **Profile installation failed** error on an Android device.</span></span>

<span data-ttu-id="b8486-207">**Resolução:**</span><span class="sxs-lookup"><span data-stu-id="b8486-207">**Resolution:**</span></span>

1.  <span data-ttu-id="b8486-208">Confirme que foi atribuída ao usuário uma licença apropriada para a versão do serviço do Intune que você está usando.</span><span class="sxs-lookup"><span data-stu-id="b8486-208">Confirm that the user has been assigned an appropriate license for the version of the Intune service you are using.</span></span>

2.  <span data-ttu-id="b8486-209">Confirme se o dispositivo já não está registrado com outro provedor MDM ou se ele ainda não tem um perfil de gerenciamento instalado.</span><span class="sxs-lookup"><span data-stu-id="b8486-209">Confirm that the device is not already enrolled with another MDM provider or that it does not already have a management profile installed.</span></span>

3.  <span data-ttu-id="b8486-210">Confirme se o Chrome para Android é o navegador padrão e se os cookies estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="b8486-210">Confirm that Chrome for Android is the default browser and that cookies are enabled.</span></span>

### <span data-ttu-id="b8486-211">Problemas de certificado do Android</span><span class="sxs-lookup"><span data-stu-id="b8486-211">Android certificate issues</span></span>
<a id="android-certificate-issues" class="xliff"></a>

<span data-ttu-id="b8486-212">**Problema**: o usuário recebe a seguinte mensagem em seu dispositivo: *Não é possível se conectar porque o dispositivo não tem um certificado necessário.*</span><span class="sxs-lookup"><span data-stu-id="b8486-212">**Issue**: Users receive the following message on their device: *You cannot sign in because your device is missing a required certificate.*</span></span>

<span data-ttu-id="b8486-213">**Resolução 1**:</span><span class="sxs-lookup"><span data-stu-id="b8486-213">**Resolution 1**:</span></span>

<span data-ttu-id="b8486-214">Solicite aos usuários que sigam as instruções em [Falta ao dispositivo um certificado necessário](https://docs.microsoft.com/intune-user-help/your-device-is-missing-a-required-certificate-landing-android#your-device-is-missing-a-certificate-required-by-your-it-administrator).</span><span class="sxs-lookup"><span data-stu-id="b8486-214">Ask your users to follow the instructions in [Your device is missing a required certificate](https://docs.microsoft.com/intune-user-help/your-device-is-missing-a-required-certificate-landing-android#your-device-is-missing-a-certificate-required-by-your-it-administrator).</span></span> <span data-ttu-id="b8486-215">Se o erro persistir após os usuários seguirem essas instruções, tente a Resolução 2.</span><span class="sxs-lookup"><span data-stu-id="b8486-215">If the error still appears after users follow the instructions, try Resolution 2.</span></span>

<span data-ttu-id="b8486-216">**Resolução 2**:</span><span class="sxs-lookup"><span data-stu-id="b8486-216">**Resolution 2**:</span></span>

<span data-ttu-id="b8486-217">Se os usuários ainda virem o erro de ausência de certificado após inserir suas credenciais corporativas e serem redirecionados à experiência de logon federado, um certificado intermediário pode estar faltando no seu servidor de Serviços de Federação do Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="b8486-217">If users still see the missing certificate error after entering their corporate credentials and getting redirected for the federated login experience, an intermediate certificate may be missing from your Active Directory Federation Services (AD FS) server.</span></span>

<span data-ttu-id="b8486-218">O erro de certificado ocorre porque dispositivos Android exigem que certificados intermediários sejam incluídos em uma [saudação do servidor SSL](https://technet.microsoft.com/library/cc783349.aspx), mas, no momento, um servidor padrão do AD FS ou a instalação do servidor proxy do AD FS envia apenas o certificado SSL do serviço de AD FS na saudação de resposta do servidor SSL à uma saudação do cliente SSL.</span><span class="sxs-lookup"><span data-stu-id="b8486-218">The certificate error occurs because Android devices require intermediate certificates to be included in an [SSL Server hello](https://technet.microsoft.com/library/cc783349.aspx), but currently a default AD FS server or AD FS Proxy server installation sends only the AD FS’s service SSL certificate in the SSL server hello response to an SSL Client hello.</span></span>

<span data-ttu-id="b8486-219">Para corrigir o problema, importe os certificados para os Certificados Pessoais do Computador no servidor do AD FS ou proxies da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b8486-219">To fix the issue, import the certificates into the Computers Personal Certificates on the AD FS server or proxies as follows:</span></span>

1.  <span data-ttu-id="b8486-220">Nos servidores AD FS e proxy, inicie o console de Gerenciamento de Certificados do computador local clicando com o botão direito do mouse em **Iniciar**, escolhendo **Executar** e digitando **certlm.msc**.</span><span class="sxs-lookup"><span data-stu-id="b8486-220">On the ADFS and proxy servers, launch the Certificate Management console for the local computer by right-clicking the **Start** button, choosing **Run** and typing **certlm.msc**.</span></span>
2.  <span data-ttu-id="b8486-221">Expanda **Pessoal** e selecione **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="b8486-221">Expand **Personal** and select **Certificates**.</span></span>
3.  <span data-ttu-id="b8486-222">Localize o certificado da comunicação de serviço do AD FS (certificado assinado publicamente) e clique duas vezes para exibir suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="b8486-222">Find the certificate for your AD FS service communication (a publicly signed certificate), and double-click to view its properties.</span></span>
4.  <span data-ttu-id="b8486-223">Selecione a guia **Caminho de Certificação** para ver o(s) certificado(s) pai do certificado.</span><span class="sxs-lookup"><span data-stu-id="b8486-223">Select the **Certification Path** tab to see the certificate’s parent certificate/s.</span></span>
5.  <span data-ttu-id="b8486-224">Em cada certificado pai, selecione **Exibir Certificado**.</span><span class="sxs-lookup"><span data-stu-id="b8486-224">On each parent certificate, select **View Certificate**.</span></span>
6.  <span data-ttu-id="b8486-225">Selecione a guia **Detalhes** e escolha **Copiar para arquivo...**.</span><span class="sxs-lookup"><span data-stu-id="b8486-225">Select the **Details** tab and choose **Copy to file…**.</span></span>
7.  <span data-ttu-id="b8486-226">Siga as solicitações do assistente para exportar ou salvar a chave pública do certificado para o local de arquivo desejado.</span><span class="sxs-lookup"><span data-stu-id="b8486-226">Follow the wizard prompts to export or save the public key of the certificate to the desired file location.</span></span>
8.  <span data-ttu-id="b8486-227">Importe os certificados pai que foram exportados na Etapa 3 para Computador Local\Pessoal\Certificados clicando com o botão direito do mouse em **Certificados**, selecionado **Todas Tarefas** > **Importar** e seguindo as solicitações do assistente para importar o(s) certificado(s).</span><span class="sxs-lookup"><span data-stu-id="b8486-227">Import the parent certificates that were exported in Step 3 to Local Computer\Personal\Certificates by right-clicking **Certificates**, selecting **All Tasks** > **Import**, and then following the wizard prompts to import the certificate(s).</span></span>
9.  <span data-ttu-id="b8486-228">Reinicie os servidores AD FS.</span><span class="sxs-lookup"><span data-stu-id="b8486-228">Restart the AD FS servers.</span></span>
10. <span data-ttu-id="b8486-229">Repita as etapas acima em todos os servidores AD FS e proxy.</span><span class="sxs-lookup"><span data-stu-id="b8486-229">Repeat the above steps on all of your AD FS and proxy servers.</span></span>
<span data-ttu-id="b8486-230">Agora, o usuário deve ser capaz de entrar no Portal da Empresa no dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="b8486-230">The user should now be able to sign in to the Company Portal on the Android device.</span></span>

<span data-ttu-id="b8486-231">**Para validar a instalação correta do certificado**:</span><span class="sxs-lookup"><span data-stu-id="b8486-231">**To validate that the certificate installed correctly**:</span></span>

<span data-ttu-id="b8486-232">As etapas a seguir descrevem apenas um dos vários métodos e ferramentas que você pode usar para validar a instalação correta do certificado.</span><span class="sxs-lookup"><span data-stu-id="b8486-232">The follow steps describe just one of many methods and tools that you can use to validate that the certificate installed correctly.</span></span>

1. <span data-ttu-id="b8486-233">Vá para a [ferramenta gratuita do Digicert](ttps://www.digicert.com/help/).</span><span class="sxs-lookup"><span data-stu-id="b8486-233">Go to the [free Digicert tool](ttps://www.digicert.com/help/).</span></span>
2. <span data-ttu-id="b8486-234">Insira o nome de domínio totalmente qualificado do servidor AD FS (por exemplo, sts.contoso.com) e selecione **VERIFICAR SERVIDOR**.</span><span class="sxs-lookup"><span data-stu-id="b8486-234">Enter your AD FS server’s fully qualified domain name (e.g., sts.contoso.com) and select **CHECK SERVER**.</span></span>

<span data-ttu-id="b8486-235">Se o certificado do servidor estiver instalado corretamente, você verá todas as marcas de seleção nos resultados.</span><span class="sxs-lookup"><span data-stu-id="b8486-235">If the Server certificate is installed correctly, you see all check marks in the results.</span></span> <span data-ttu-id="b8486-236">Se o problema acima existir, você ver um “X” vermelho nas seções “Correspondências de Nome de Certificado” e “Certificado SSL instalado corretamente” do relatório.</span><span class="sxs-lookup"><span data-stu-id="b8486-236">If the problem above exists, you see a red X in the "Certificate Name Matches" and the “SSL Certificate is correctly Installed” sections of the report.</span></span>


## <span data-ttu-id="b8486-237">Problemas de iOS</span><span class="sxs-lookup"><span data-stu-id="b8486-237">iOS issues</span></span>
<a id="ios-issues" class="xliff"></a>

### <span data-ttu-id="b8486-238">Os dispositivos estão inativos ou o console de administração não pode se comunicar com eles</span><span class="sxs-lookup"><span data-stu-id="b8486-238">Devices are inactive or the admin console cannot communicate with them</span></span>
<a id="devices-are-inactive-or-the-admin-console-cannot-communicate-with-them" class="xliff"></a>
<span data-ttu-id="b8486-239">**Problema:** os dispositivos iOS não estão fazendo check-in no serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="b8486-239">**Issue:** iOS devices aren’t checking in with the Intune service.</span></span> <span data-ttu-id="b8486-240">Os dispositivos devem fazer o check-in no serviço periodicamente para manter o acesso aos recursos corporativos protegidos.</span><span class="sxs-lookup"><span data-stu-id="b8486-240">Devices must check in periodically with the service to maintain access to protected corporate resources.</span></span> <span data-ttu-id="b8486-241">Se os dispositivos não fizerem o check-in:</span><span class="sxs-lookup"><span data-stu-id="b8486-241">If devices don’t check in:</span></span>

- <span data-ttu-id="b8486-242">Eles não poderão receber políticas, aplicativos e comandos remotos do serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="b8486-242">They can't receive policy, apps, and remote commands from the Intune service.</span></span>
- <span data-ttu-id="b8486-243">Eles mostram um Estado de Gerenciamento **não íntegro** no console do administrador.</span><span class="sxs-lookup"><span data-stu-id="b8486-243">They show a Management State of **Unhealthy** in the administrator console.</span></span>
- <span data-ttu-id="b8486-244">Os usuários que são protegidos por políticas de acesso condicional podem perder o acesso aos recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="b8486-244">Users who are protected by conditional access policies might lose access to corporate resources.</span></span>

<span data-ttu-id="b8486-245">**Resolução:** compartilhe as seguintes resoluções com seus usuários finais para ajudá-los a recuperar o acesso aos recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="b8486-245">**Resolution:** Share the following resolutions with your end users to help them regain access to corporate resources.</span></span>

<span data-ttu-id="b8486-246">Quando os usuários iniciarem o aplicativo do Portal da Empresa do iOS, ele poderá informar se o dispositivo perdeu contato com o Intune.</span><span class="sxs-lookup"><span data-stu-id="b8486-246">When users start the iOS Company Portal app, it can tell if their device has lost contact with Intune.</span></span> <span data-ttu-id="b8486-247">Se detectar que não há nenhum contato, ele tenta automaticamente a sincronização com o Intune para se reconectar e os usuários verão a notificação embutida **Tentando sincronizar...**</span><span class="sxs-lookup"><span data-stu-id="b8486-247">If it detects that there is no contact, it automatically tries to sync with Intune to reconnect, and users will see the **Trying to sync…**</span></span> <span data-ttu-id="b8486-248">.</span><span class="sxs-lookup"><span data-stu-id="b8486-248">inline notification.</span></span>

  ![Notificação Tentando sincronizar](./media/ios_cp_app_trying_to_sync_notification.png)

<span data-ttu-id="b8486-250">Se a sincronização for bem-sucedida, você verá uma notificação embutida **Sincronização bem-sucedida** no aplicativo do Portal da Empresa do iOS, indicando que o dispositivo está em um estado íntegro.</span><span class="sxs-lookup"><span data-stu-id="b8486-250">If the sync is successful, you see a **Sync successful** inline notification in the iOS Company Portal app, indicating that your device is in a healthy state.</span></span>

  ![Notificação Sincronização bem-sucedida](./media/ios_cp_app_sync_successful_notification.png)

<span data-ttu-id="b8486-252">Se a sincronização não for bem-sucedida, os usuários verão uma notificação embutida **Não é possível sincronizar** no aplicativo do Portal da Empresa do iOS.</span><span class="sxs-lookup"><span data-stu-id="b8486-252">If the sync is unsuccessful, users see an **Unable to sync** inline notification in the iOS Company Portal app.</span></span>

  ![Não é possível sincronizar a notificação](./media/ios_cp_app_unable_to_sync_notification.png)

<span data-ttu-id="b8486-254">Para corrigir o problema, os usuários devem selecionar o botão **Configurar**, que está à direita da notificação **Não é possível sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="b8486-254">To fix the issue, users must select the **Set up** button, which is to the right of the **Unable to sync** notification.</span></span> <span data-ttu-id="b8486-255">O botão Configurar leva os usuários para a tela de fluxo Configuração do Acesso da Empresa, em que eles podem seguir os prompts para registrar seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b8486-255">The Set up button takes users to the Company Access Setup flow screen, where they can follow the prompts to enroll their device.</span></span>

  ![Tela de Configuração de Acesso da Empresa](./media/ios_cp_app_company_access_setup.png)

<span data-ttu-id="b8486-257">Depois de registrado, os dispositivos retornam ao estado íntegro e recuperam o acesso aos recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="b8486-257">Once enrolled, the devices return to a healthy state and regain access to company resources.</span></span>

### <span data-ttu-id="b8486-258">Falha na instalação do perfil</span><span class="sxs-lookup"><span data-stu-id="b8486-258">Profile installation failed</span></span>
<a id="profile-installation-failed" class="xliff"></a>
<span data-ttu-id="b8486-259">**Problema:** um usuário recebe um erro de **Falha na instalação de perfil** em um dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="b8486-259">**Issue:** A user receives a **Profile installation failed** error on an iOS device.</span></span>

### <span data-ttu-id="b8486-260">Etapas de solução de problemas para falhas na instalação de perfil</span><span class="sxs-lookup"><span data-stu-id="b8486-260">Troubleshooting steps for failed profile installation</span></span>
<a id="troubleshooting-steps-for-failed-profile-installation" class="xliff"></a>

1.  <span data-ttu-id="b8486-261">Confirme que foi atribuída ao usuário uma licença apropriada para a versão do serviço do Intune que você está usando.</span><span class="sxs-lookup"><span data-stu-id="b8486-261">Confirm that the user has been assigned an appropriate license for the version of the Intune service you are using.</span></span>

2.  <span data-ttu-id="b8486-262">Confirme se o dispositivo já não está registrado com outro provedor MDM ou se ele ainda não tem um perfil de gerenciamento instalado.</span><span class="sxs-lookup"><span data-stu-id="b8486-262">Confirm that the device is not already enrolled with another MDM provider or that it does not already have a management profile installed.</span></span>

3.  <span data-ttu-id="b8486-263">Navegue até [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) e tente instalar o perfil quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="b8486-263">Navigate to [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) and try to install the profile when prompted.</span></span>

4.  <span data-ttu-id="b8486-264">Confirme se o Safari para iOS é o navegador padrão e se os cookies estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="b8486-264">Confirm that Safari for iOS is the default browser and that cookies are enabled.</span></span>

### <span data-ttu-id="b8486-265">Os dispositivos iOS registrados não aparecem no console ao usar o System Center Configuration Manager com o Intune</span><span class="sxs-lookup"><span data-stu-id="b8486-265">Enrolled iOS device doesn't appear in console when using System Center Configuration Manager with Intune</span></span>
<a id="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune" class="xliff"></a>
<span data-ttu-id="b8486-266">**Problema:** o usuário registra um dispositivo iOS, mas ele não aparece no console de administração do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b8486-266">**Issue:** User enrolls iOS device but it does not appear in the Configuration Manager admin console.</span></span> <span data-ttu-id="b8486-267">O dispositivo não indica que ele foi registrado.</span><span class="sxs-lookup"><span data-stu-id="b8486-267">The device does not indicate that it's been enrolled.</span></span> <span data-ttu-id="b8486-268">Possíveis causas:</span><span class="sxs-lookup"><span data-stu-id="b8486-268">Possible causes:</span></span>

- <span data-ttu-id="b8486-269">Você pode ter registrado seu conector Intune em uma conta e, então, ter registrado o dispositivo em outra conta.</span><span class="sxs-lookup"><span data-stu-id="b8486-269">You may have enrolled your Intune Connector into one account, and then enrolled it into another account.</span></span>
- <span data-ttu-id="b8486-270">Você pode ter baixado o certificado MDM de uma conta e o usado em outra conta.</span><span class="sxs-lookup"><span data-stu-id="b8486-270">You may have downloaded the MDM certificate from one account and used it on another account.</span></span>


<span data-ttu-id="b8486-271">**Resolução:** execute as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="b8486-271">**Resolution:** Perform the following steps:</span></span>

1. <span data-ttu-id="b8486-272">Desabilite o iOS dentro do conector do Windows Intune.</span><span class="sxs-lookup"><span data-stu-id="b8486-272">Disable iOS inside of the Windows Intune Connector.</span></span>
    1. <span data-ttu-id="b8486-273">Clique com o botão direito do mouse na assinatura do Intune e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b8486-273">Right-click the Intune subscription and select **Properties**.</span></span>
    1. <span data-ttu-id="b8486-274">Na guia "iOS", desmarque a opção "Habilitar registro do iOS".</span><span class="sxs-lookup"><span data-stu-id="b8486-274">On the "iOS" tab, uncheck "Enable iOS Enrollment".</span></span>



2. <span data-ttu-id="b8486-275">No SQL, execute as etapas a seguir no banco de dados do CAS</span><span class="sxs-lookup"><span data-stu-id="b8486-275">In SQL, run the following steps on the CAS DB</span></span>

    1. <span data-ttu-id="b8486-276">atualizar o SC_ClientComponent_Property set Value2 = '', em que Nome é igual a '%APNS%'</span><span class="sxs-lookup"><span data-stu-id="b8486-276">update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'</span></span>
    1. <span data-ttu-id="b8486-277">excluir do MDMPolicy, em que PolicyType = 7</span><span class="sxs-lookup"><span data-stu-id="b8486-277">delete from MDMPolicy where PolicyType = 7</span></span>
    1. <span data-ttu-id="b8486-278">excluir do MDMPolicyAssignment, em que PolicyType = 7</span><span class="sxs-lookup"><span data-stu-id="b8486-278">delete from MDMPolicyAssignment where PolicyType = 7</span></span>
    1. <span data-ttu-id="b8486-279">atualizar o SC_ClientComponent_Property set Value2 = '', em que Nome é igual a '%APNS%'</span><span class="sxs-lookup"><span data-stu-id="b8486-279">update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'</span></span>
    1. <span data-ttu-id="b8486-280">excluir do MDMPolicy, em que PolicyType = 11</span><span class="sxs-lookup"><span data-stu-id="b8486-280">delete from MDMPolicy where PolicyType = 11</span></span>
    1. <span data-ttu-id="b8486-281">excluir do MDMPolicyAssignment, em que PolicyType = 11</span><span class="sxs-lookup"><span data-stu-id="b8486-281">delete from MDMPolicyAssignment where PolicyType = 11</span></span>
    1. <span data-ttu-id="b8486-282">EXCLUIR Drs_Signals</span><span class="sxs-lookup"><span data-stu-id="b8486-282">DELETE Drs_Signals</span></span>
3. <span data-ttu-id="b8486-283">Reinicie o serviço SMS Executive ou o servidor CM.</span><span class="sxs-lookup"><span data-stu-id="b8486-283">Restart the SMS Executive Service or restart the CM Server.</span></span>

4. <span data-ttu-id="b8486-284">Obtenha um novo certificado APN e carregue-o.</span><span class="sxs-lookup"><span data-stu-id="b8486-284">Get a new APN certificate and upload it.</span></span> <span data-ttu-id="b8486-285">Para fazer isso, clique com o botão direito do mouse na assinatura do Intune no painel esquerdo do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b8486-285">To do that, right-click the Intune subscription in the left pane of Configuration Manager.</span></span> <span data-ttu-id="b8486-286">Selecione a opção **Criar solicitação de certificado APNs** e siga as instruções.</span><span class="sxs-lookup"><span data-stu-id="b8486-286">Select **Create APNs certificate request** and follow the instructions.</span></span>
5.
## <span data-ttu-id="b8486-287">Problemas ao usar o System Center Configuration Manager com o Intune</span><span class="sxs-lookup"><span data-stu-id="b8486-287">Issues when using System Center Configuration Manager with Intune</span></span>
<a id="issues-when-using-system-center-configuration-manager-with-intune" class="xliff"></a>

### <span data-ttu-id="b8486-288">Dispositivos móveis desaparecem</span><span class="sxs-lookup"><span data-stu-id="b8486-288">Mobile devices disappear</span></span>
<a id="mobile-devices-disappear" class="xliff"></a>

<span data-ttu-id="b8486-289">**Problema:** após registrar com êxito um dispositivo móvel no Configuration Manager, ele desaparece da coleção de dispositivos móveis, mas o dispositivo ainda tem o Perfil de gerenciamento e é listado no Gateway de CSS.</span><span class="sxs-lookup"><span data-stu-id="b8486-289">**Issue:** After successfully enrolling a mobile device to Configuration Manager, the device disappears from the mobile device collection, but the device still has the Management Profile and is listed in CSS Gateway.</span></span>

<span data-ttu-id="b8486-290">**Resolução:** isso pode ocorrer se você usa um processo personalizado para remover dispositivos não ingressados no domínio ou porque o usuário desativou o dispositivo da assinatura.</span><span class="sxs-lookup"><span data-stu-id="b8486-290">**Resolution:** This issue might occur if you use you have a custom process removing non-domain-joined devices, or because the user has retired the device from the subscription.</span></span> <span data-ttu-id="b8486-291">Para validar e verificar qual conta de usuário ou processo removeu o dispositivo do console do Configuration Manager, execute as seguintes etapas para verificar como o dispositivo foi removido.</span><span class="sxs-lookup"><span data-stu-id="b8486-291">To validate and check which process or user account removed the device from the Configuration Manager console, perform the following steps to check how the device was removed.</span></span>

1.  <span data-ttu-id="b8486-292">No console de administração do Configuration Manager, selecione **Monitoramento** &gt; **Status do Sistema** &gt; **Consultas de Mensagem de Status**.</span><span class="sxs-lookup"><span data-stu-id="b8486-292">In the Configuration Manager admin console, select **Monitoring** &gt; **System Status** &gt; **Status Message Queries**.</span></span>

2.  <span data-ttu-id="b8486-293">Clique com o botão direito do mouse em **Recursos Membros da Coleção Excluídos Manualmente** e selecione **Mostrar Mensagens**.</span><span class="sxs-lookup"><span data-stu-id="b8486-293">Right-click **Collection Member Resources Manually Deleted** and select **Show Messages**.</span></span>

3.  <span data-ttu-id="b8486-294">Escolha uma data/hora apropriada ou as últimas 12 horas.</span><span class="sxs-lookup"><span data-stu-id="b8486-294">Choose an appropriate time/date or the last 12 hours.</span></span>

4.  <span data-ttu-id="b8486-295">Localize o dispositivo em questão e examine como o dispositivo foi removido.</span><span class="sxs-lookup"><span data-stu-id="b8486-295">Find the device in question and review how the device was removed.</span></span> <span data-ttu-id="b8486-296">O exemplo a seguir mostra que a conta SCCMInstall excluiu o dispositivo por meio de um aplicativo desconhecido.</span><span class="sxs-lookup"><span data-stu-id="b8486-296">The example below shows that the account SCCMInstall deleted the device via an Unknown Application.</span></span>

    ![Captura de tela para diagnóstico de exclusão do dispositivo](./media/cm-with-intune-unknown-app-deleted-device.png)

5.  <span data-ttu-id="b8486-298">Verifique se o Configuration Manager não tem uma tarefa agendada, script ou outro processo que poderia estar limpando automaticamente dispositivos móveis, fora do domínio ou relacionados.</span><span class="sxs-lookup"><span data-stu-id="b8486-298">Check that Configuration Manager does not have a scheduled task, script, or other process that could be automatically purging non-domain, mobile, or related devices.</span></span>




### <span data-ttu-id="b8486-299">Outros erros de registro do iOS</span><span class="sxs-lookup"><span data-stu-id="b8486-299">Other iOS enrollment errors</span></span>
<a id="other-ios-enrollment-errors" class="xliff"></a>

<span data-ttu-id="b8486-300">Você pode exibir uma lista de [Erros de registro do iOS](https://docs.microsoft.com/intune-user-help/you-see-errors-while-trying-to-enroll-your-device-in-intune-ios) que os usuários finais podem ver.</span><span class="sxs-lookup"><span data-stu-id="b8486-300">You can view a list of [iOS enrollment errors](https://docs.microsoft.com/intune-user-help/you-see-errors-while-trying-to-enroll-your-device-in-intune-ios) that end users might see.</span></span> <span data-ttu-id="b8486-301">A lista fornece informações sobre mensagens de erro que os usuários finais podem ver e as etapas que você seguir para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="b8486-301">The list provides information about error messages that end users might see and the steps that you take to resolve the issue.</span></span>

## <span data-ttu-id="b8486-302">Problemas do computador</span><span class="sxs-lookup"><span data-stu-id="b8486-302">PC  Issues</span></span>
<a id="pc--issues" class="xliff"></a>

### <span data-ttu-id="b8486-303">O computador já está registrado - erro hr 0x8007064c</span><span class="sxs-lookup"><span data-stu-id="b8486-303">The machine is already enrolled - Error hr 0x8007064c</span></span>
<a id="the-machine-is-already-enrolled---error-hr-0x8007064c" class="xliff"></a>
<span data-ttu-id="b8486-304">**Problema:** o registro falha com o erro **O computador já está registrado**.</span><span class="sxs-lookup"><span data-stu-id="b8486-304">**Issue:** Enrollment fails with the error **The machine is already enrolled**.</span></span> <span data-ttu-id="b8486-305">O log de registro mostra o erro **hr 0x8007064c**.</span><span class="sxs-lookup"><span data-stu-id="b8486-305">The enrollment log shows error **hr 0x8007064c**.</span></span>

<span data-ttu-id="b8486-306">Esse erro pode ocorrer porque o computador já foi registrado anteriormente ou tem a imagem clonada de um computador que tinha sido registrado.</span><span class="sxs-lookup"><span data-stu-id="b8486-306">This error might occur because the computer had been previously enrolled, or has the cloned image of a computer that had been enrolled.</span></span> <span data-ttu-id="b8486-307">O certificado de conta da conta anterior ainda está presente no computador.</span><span class="sxs-lookup"><span data-stu-id="b8486-307">The account certificate of the previous account is still present on the computer.</span></span>

<span data-ttu-id="b8486-308">**Resolução:**</span><span class="sxs-lookup"><span data-stu-id="b8486-308">**Resolution:**</span></span>

<span data-ttu-id="b8486-309">1.</span><span class="sxs-lookup"><span data-stu-id="b8486-309">1..</span></span> <span data-ttu-id="b8486-310">No menu **Iniciar**, digite **Executar** -> **MMC**.</span><span class="sxs-lookup"><span data-stu-id="b8486-310">From the **Start** menu, type **Run** -> **MMC**.</span></span>
1. <span data-ttu-id="b8486-311">Escolha **Arquivo** > **Adicionar/Remover Snap-ins**.</span><span class="sxs-lookup"><span data-stu-id="b8486-311">Choose **File** > **Add/ Remove Snap-ins**.</span></span>
1. <span data-ttu-id="b8486-312">Clique duas vezes em **Certificados**, escolha a **Conta de computador** > **Avançar** e selecione **Computador Local**.</span><span class="sxs-lookup"><span data-stu-id="b8486-312">Double-click **Certificates**, choose **Computer account** > **Next**, and select **Local Computer**.</span></span>
1. <span data-ttu-id="b8486-313">Clique duas vezes em **Certificados (computador local)** e escolha **Pessoal/Certificados**.</span><span class="sxs-lookup"><span data-stu-id="b8486-313">Double-click **Certificates (Local computer)** and choose **Personal/ Certificates**.</span></span>
1. <span data-ttu-id="b8486-314">Procure pelo certificado Intune emitido por Sc_Online_Issuing e exclua-o, se estiver presente.</span><span class="sxs-lookup"><span data-stu-id="b8486-314">Look for the Intune cert issued by Sc_Online_Issuing, and delete it, if present.</span></span>
1. <span data-ttu-id="b8486-315">Se a chave do Registro a seguir existir, exclua-a: existir: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey** e todas as subchaves.</span><span class="sxs-lookup"><span data-stu-id="b8486-315">If the following registry key exists, delete it: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey** and all sub keys.</span></span>
1. <span data-ttu-id="b8486-316">Tente registrar novamente.</span><span class="sxs-lookup"><span data-stu-id="b8486-316">Try to re-enroll.</span></span>
1. <span data-ttu-id="b8486-317">Se o computador ainda não conseguir realizar o registro, procure e exclua essa chave, se existir: **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95**.</span><span class="sxs-lookup"><span data-stu-id="b8486-317">If the PC still cannot enroll, look for and delete this key, if it exists: **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95**.</span></span>
1. <span data-ttu-id="b8486-318">Tente registrar novamente.</span><span class="sxs-lookup"><span data-stu-id="b8486-318">Try to re-enroll.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b8486-319">Nesta seção, o método ou tarefa contém etapas que descrevem como modificar o Registro.</span><span class="sxs-lookup"><span data-stu-id="b8486-319">This section, method, or task contains steps that tell you how to modify the registry.</span></span> <span data-ttu-id="b8486-320">No entanto, problemas graves podem ocorrer se você modificar o Registro incorretamente.</span><span class="sxs-lookup"><span data-stu-id="b8486-320">However, serious problems might occur if you modify the registry incorrectly.</span></span> <span data-ttu-id="b8486-321">Portanto, certifique-se de seguir estas etapas com cuidado.</span><span class="sxs-lookup"><span data-stu-id="b8486-321">Therefore, make sure that you follow these steps carefully.</span></span> <span data-ttu-id="b8486-322">Para maior proteção, faça backup do Registro antes de modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="b8486-322">For added protection, back up the registry before you modify it.</span></span> <span data-ttu-id="b8486-323">Assim, será possível restaurá-lo se houver algum problema.</span><span class="sxs-lookup"><span data-stu-id="b8486-323">Then, you can restore the registry if a problem occurs.</span></span>
    > <span data-ttu-id="b8486-324">Para obter mais informações sobre como fazer backup e restaurar o Registro, leia [Como fazer backup e restaurar o registro no Windows](https://support.microsoft.com/kb/322756).</span><span class="sxs-lookup"><span data-stu-id="b8486-324">For more information about how to back up and restore the registry, read [How to back up and restore the registry in Windows](https://support.microsoft.com/kb/322756).</span></span>

## <span data-ttu-id="b8486-325">Códigos de erro gerais de registro</span><span class="sxs-lookup"><span data-stu-id="b8486-325">General enrollment error codes</span></span>
<a id="general-enrollment-error-codes" class="xliff"></a>

|<span data-ttu-id="b8486-326">Código do erro</span><span class="sxs-lookup"><span data-stu-id="b8486-326">Error code</span></span>|<span data-ttu-id="b8486-327">Possível problema</span><span class="sxs-lookup"><span data-stu-id="b8486-327">Possible problem</span></span>|<span data-ttu-id="b8486-328">Resoluções sugeridas</span><span class="sxs-lookup"><span data-stu-id="b8486-328">Suggested resolution</span></span>|
|--------------|--------------------|----------------------------------------|
|<span data-ttu-id="b8486-329">0x80CF0437</span><span class="sxs-lookup"><span data-stu-id="b8486-329">0x80CF0437</span></span> |<span data-ttu-id="b8486-330">O relógio no computador cliente não está definido com a hora correta.</span><span class="sxs-lookup"><span data-stu-id="b8486-330">The clock on the client computer is not set to the correct time.</span></span>|<span data-ttu-id="b8486-331">Verifique se o relógio e o fuso horário do computador cliente estão definidos para a hora e o fuso horário corretos.</span><span class="sxs-lookup"><span data-stu-id="b8486-331">Make sure that the clock and the time zone on the client computer are set to the correct time and time zone.</span></span>|
|<span data-ttu-id="b8486-332">0x80240438, 0x80CF0438, 0x80CF402C</span><span class="sxs-lookup"><span data-stu-id="b8486-332">0x80240438, 0x80CF0438, 0x80CF402C</span></span>|<span data-ttu-id="b8486-333">Não é possível se conectar ao serviço Intune.</span><span class="sxs-lookup"><span data-stu-id="b8486-333">Cannot connect to the Intune service.</span></span> <span data-ttu-id="b8486-334">Verifique as configurações de proxy do cliente.</span><span class="sxs-lookup"><span data-stu-id="b8486-334">Check the client proxy settings.</span></span>|<span data-ttu-id="b8486-335">Verifique se a configuração de proxy no computador cliente tem suporte pelo Intune e se o computador tem acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="b8486-335">Verify that the proxy configuration on the client computer is supported by Intune, and that the client computer has Internet access.</span></span>|
|<span data-ttu-id="b8486-336">0x80240438, 0x80CF0438</span><span class="sxs-lookup"><span data-stu-id="b8486-336">0x80240438, 0x80CF0438</span></span>|<span data-ttu-id="b8486-337">As configurações de proxy no Internet Explorer e no Sistema Local não estão definidas.</span><span class="sxs-lookup"><span data-stu-id="b8486-337">Proxy settings in Internet Explorer and Local System are not configured.</span></span>|<span data-ttu-id="b8486-338">Não é possível se conectar ao serviço Intune.</span><span class="sxs-lookup"><span data-stu-id="b8486-338">Cannot connect to the Intune service.</span></span> <span data-ttu-id="b8486-339">Verifique as configurações de proxy do cliente, confirme se a configuração de proxy no computador cliente tem suporte no Intune e se o computador cliente tem acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="b8486-339">Check the client proxy settings and confirm that the proxy configuration on the client computer is supported by Intune, and that the client computer has Internet access.</span></span>|
|<span data-ttu-id="b8486-340">0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004</span><span class="sxs-lookup"><span data-stu-id="b8486-340">0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004</span></span>|<span data-ttu-id="b8486-341">O pacote de inscrição está desatualizado.</span><span class="sxs-lookup"><span data-stu-id="b8486-341">Enrollment package is out of date.</span></span>|<span data-ttu-id="b8486-342">Baixe e instale o pacote do software cliente atual no espaço de trabalho Administração.</span><span class="sxs-lookup"><span data-stu-id="b8486-342">Download and install the current client software package from the Administration workspace.</span></span>|
|<span data-ttu-id="b8486-343">0x80043002, 0x80CF3002</span><span class="sxs-lookup"><span data-stu-id="b8486-343">0x80043002, 0x80CF3002</span></span>|<span data-ttu-id="b8486-344">A conta está no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="b8486-344">Account is in maintenance mode.</span></span>|<span data-ttu-id="b8486-345">Não é possível inscrever novos computadores clientes quando a conta está no modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="b8486-345">You cannot enroll new client computers when the account is in maintenance mode.</span></span> <span data-ttu-id="b8486-346">Para exibir suas configurações de conta, entre na sua conta.</span><span class="sxs-lookup"><span data-stu-id="b8486-346">To view your account settings, sign in to your account.</span></span>|
|<span data-ttu-id="b8486-347">0x80043003, 0x80CF3003</span><span class="sxs-lookup"><span data-stu-id="b8486-347">0x80043003, 0x80CF3003</span></span>|<span data-ttu-id="b8486-348">A conta está excluída.</span><span class="sxs-lookup"><span data-stu-id="b8486-348">Account is deleted.</span></span>|<span data-ttu-id="b8486-349">Verifique se sua conta e assinatura do Intune continuam ativas.</span><span class="sxs-lookup"><span data-stu-id="b8486-349">Verify that your account and subscription to Intune is still active.</span></span> <span data-ttu-id="b8486-350">Para exibir suas configurações de conta, entre na sua conta.</span><span class="sxs-lookup"><span data-stu-id="b8486-350">To view your account settings, sign in to your account.</span></span>|
|<span data-ttu-id="b8486-351">0x80043005, 0x80CF3005</span><span class="sxs-lookup"><span data-stu-id="b8486-351">0x80043005, 0x80CF3005</span></span>|<span data-ttu-id="b8486-352">O computador cliente foi desativado.</span><span class="sxs-lookup"><span data-stu-id="b8486-352">The client computer has been retired.</span></span>|<span data-ttu-id="b8486-353">Aguarde algumas horas, remova do computador as versões mais antigas do software cliente e tente instalar novamente o software cliente.</span><span class="sxs-lookup"><span data-stu-id="b8486-353">Wait a few hours, remove any older versions of the client software from the computer, and then retry the client software installation.</span></span>|
|<span data-ttu-id="b8486-354">0x80043006, 0x80CF3006</span><span class="sxs-lookup"><span data-stu-id="b8486-354">0x80043006, 0x80CF3006</span></span>|<span data-ttu-id="b8486-355">O número máximo de estações permitidas para a conta foi atingido.</span><span class="sxs-lookup"><span data-stu-id="b8486-355">The maximum number of seats allowed for the account has been reached.</span></span>|<span data-ttu-id="b8486-356">Sua organização deve adquirir estações adicionais para poder inscrever mais computadores clientes no serviço.</span><span class="sxs-lookup"><span data-stu-id="b8486-356">Your organization must purchase additional seats before you can enroll more client computers in the service.</span></span>|
|<span data-ttu-id="b8486-357">0x80043007, 0x80CF3007</span><span class="sxs-lookup"><span data-stu-id="b8486-357">0x80043007, 0x80CF3007</span></span>|<span data-ttu-id="b8486-358">Não foi possível localizar o arquivo de certificado na mesma pasta do programa de instalação.</span><span class="sxs-lookup"><span data-stu-id="b8486-358">Could not find the certificate file in the same folder as the installer program.</span></span>|<span data-ttu-id="b8486-359">Extrai todos os arquivos antes de iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="b8486-359">Extract all files before you start the installation.</span></span> <span data-ttu-id="b8486-360">Não renomeie ou relocalize os arquivos extraídos: todos os arquivos devem existir na mesma pasta ou a instalação falhará.</span><span class="sxs-lookup"><span data-stu-id="b8486-360">Do not rename or relocate any of the extracted files: all files must exist in the same folder or the installation will fail.</span></span>|
|<span data-ttu-id="b8486-361">0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015</span><span class="sxs-lookup"><span data-stu-id="b8486-361">0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015</span></span>|<span data-ttu-id="b8486-362">O software não pode ser instalado porque uma reinicialização do computador cliente está pendente.</span><span class="sxs-lookup"><span data-stu-id="b8486-362">The software cannot be installed because a restart of the client computer is pending.</span></span>|<span data-ttu-id="b8486-363">Reinicie o computador e tente instalar novamente o software cliente.</span><span class="sxs-lookup"><span data-stu-id="b8486-363">Restart the computer and then retry the client software installation.</span></span>|
|<span data-ttu-id="b8486-364">0x80070032</span><span class="sxs-lookup"><span data-stu-id="b8486-364">0x80070032</span></span>|<span data-ttu-id="b8486-365">Um ou mais pré-requisitos de instalação do software cliente não foram encontrados no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="b8486-365">One or more prerequisites for installing the client software were not found on the client computer.</span></span>|<span data-ttu-id="b8486-366">Verifique se todas as atualizações necessárias estão instaladas no computador cliente e tente instalar novamente o software cliente.</span><span class="sxs-lookup"><span data-stu-id="b8486-366">Make sure that all required updates are installed on the client computer and then retry the client software installation.</span></span>|
|<span data-ttu-id="b8486-367">0x80043008, 0x80CF3008</span><span class="sxs-lookup"><span data-stu-id="b8486-367">0x80043008, 0x80CF3008</span></span>|<span data-ttu-id="b8486-368">Falha ao iniciar o serviço de atualizações do Microsoft Online Management.</span><span class="sxs-lookup"><span data-stu-id="b8486-368">Failed to start the Microsoft Online Management Updates service.</span></span>|<span data-ttu-id="b8486-369">Entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](https://docs.microsoft.com/intune-classic/troubleshoot/get-support) (Como obter suporte para o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="b8486-369">Contact Microsoft Support as described in [How to get support for Microsoft Intune](https://docs.microsoft.com/intune-classic/troubleshoot/get-support).</span></span>|
|<span data-ttu-id="b8486-370">0x80043009, 0x80CF3009</span><span class="sxs-lookup"><span data-stu-id="b8486-370">0x80043009, 0x80CF3009</span></span>|<span data-ttu-id="b8486-371">O computador cliente já está inscrito no serviço.</span><span class="sxs-lookup"><span data-stu-id="b8486-371">The client computer is already enrolled into the service.</span></span>|<span data-ttu-id="b8486-372">Você deve retirar o computador cliente antes de ser possível registrá-lo novamente no serviço.</span><span class="sxs-lookup"><span data-stu-id="b8486-372">You must retire the client computer before you can re-enroll it in the service.</span></span>|
|<span data-ttu-id="b8486-373">0x8004300B, 0x80CF300B</span><span class="sxs-lookup"><span data-stu-id="b8486-373">0x8004300B, 0x80CF300B</span></span>|<span data-ttu-id="b8486-374">O pacote de instalação do software cliente não pode ser executado porque a versão do Windows que está em execução no cliente não é suportada.</span><span class="sxs-lookup"><span data-stu-id="b8486-374">The client software installation package cannot run because the version of Windows that is running on the client is not supported.</span></span>|<span data-ttu-id="b8486-375">O Intune não dá suporte à versão do Windows em execução no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="b8486-375">Intune does not support the version of Windows that is running on the client computer.</span></span>|
|<span data-ttu-id="b8486-376">0xAB2</span><span class="sxs-lookup"><span data-stu-id="b8486-376">0xAB2</span></span>|<span data-ttu-id="b8486-377">O Windows Installer não pode acessar o tempo de uma ação personalizada de execução do VBScript.</span><span class="sxs-lookup"><span data-stu-id="b8486-377">The Windows Installer could not access VBScript run time for a custom action.</span></span>|<span data-ttu-id="b8486-378">Este erro é causado por uma ação personalizada que se baseia em bibliotecas de vínculo dinâmico (DLLs).</span><span class="sxs-lookup"><span data-stu-id="b8486-378">This error is caused by a custom action that is based on Dynamic-Link Libraries (DLLs).</span></span> <span data-ttu-id="b8486-379">Ao solucionar problemas de DLL, pode ser necessário usar as ferramentas descritas em [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues](https://support.microsoft.com/kb/198038) (Suporte da Microsoft KB198038: Ferramentas úteis para problemas de implantação e pacote).</span><span class="sxs-lookup"><span data-stu-id="b8486-379">When troubleshooting the DLL, you might have to use the tools that are described in [Microsoft Support KB198038: Useful Tools for Package and Deployment Issues](https://support.microsoft.com/kb/198038).</span></span>|
|<span data-ttu-id="b8486-380">0x80cf0440</span><span class="sxs-lookup"><span data-stu-id="b8486-380">0x80cf0440</span></span>|<span data-ttu-id="b8486-381">A conexão com o ponto de extremidade do serviço foi encerrada.</span><span class="sxs-lookup"><span data-stu-id="b8486-381">The connection to the service endpoint terminated.</span></span>|<span data-ttu-id="b8486-382">A conta de avaliação ou paga está suspensa.</span><span class="sxs-lookup"><span data-stu-id="b8486-382">Trial or paid account is suspended.</span></span> <span data-ttu-id="b8486-383">Criar uma nova conta de avaliação ou paga e registrar novamente.</span><span class="sxs-lookup"><span data-stu-id="b8486-383">Create a new trial or paid account and re-enroll.</span></span>|




### <span data-ttu-id="b8486-384">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b8486-384">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="b8486-385">Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](https://docs.microsoft.com/intune-classic/troubleshoot/get-support) (Como obter suporte para o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="b8486-385">If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](https://docs.microsoft.com/intune-classic/troubleshoot/get-support).</span></span>
