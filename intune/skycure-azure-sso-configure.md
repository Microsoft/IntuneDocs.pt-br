---
title: "Configurar o Skycure para usar o logon único do Azure AD com o Intune"
titleSuffix: Intune on Azure
description: "Configurar o Skycure para usar o logon único do Azure AD com o Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0466ac4-4942-4c4c-b8af-996b597c701d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b2d8a79baf65208e87dbe85d8cc934e167710144
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="de0c6-103">Configurar o Skycure para usar o SSO (Logon único) do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="de0c6-103">Configure Skycure to use Azure Active Directory Single Sign On (SSO)</span></span>
<a id="configure-skycure-to-use-azure-active-directory-single-sign-on-sso" class="xliff"></a>

<span data-ttu-id="de0c6-104">O SSO do Azure AD é usado quando você integra o Intune com o Skycure.</span><span class="sxs-lookup"><span data-stu-id="de0c6-104">Azure AD SSO is used when you integrate Intune with Skycure.</span></span> <span data-ttu-id="de0c6-105">Estes são os principais benefícios:</span><span class="sxs-lookup"><span data-stu-id="de0c6-105">Here are the main benefits:</span></span>

-   <span data-ttu-id="de0c6-106">**Administradores** podem usar as mesmas credenciais sem precisar digitá-las novamente sempre que fizerem logon e saírem do Console de gerenciamento do Skycure e dos portais da Microsoft (Intune, Azure).</span><span class="sxs-lookup"><span data-stu-id="de0c6-106">**Admins** can use the same credentials without having to type it again every time they log in and out from the Microsoft portals (Intune, Azure) and Skycure Management console.</span></span>

-   <span data-ttu-id="de0c6-107">**Os usuários finais** podem usar as mesmas credenciais do Azure AD sem precisar digitá-las novamente sempre que fizerem logon e saírem dos aplicativos do Skycure.</span><span class="sxs-lookup"><span data-stu-id="de0c6-107">**End-users** can use the same Azure AD credentials without having to type it again every time they log in and out from the Skycure apps.</span></span>

<span data-ttu-id="de0c6-108">Veja abaixo as etapas para integrar o Skycure ao SSO (Logon único) do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="de0c6-108">Below are the steps to integrate Skycure with Azure Active Directory Single Sign On (SSO).</span></span>

## <span data-ttu-id="de0c6-109">Para recuperar a ID de locatário do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="de0c6-109">To retrieve the Azure Active Directory Tenant ID</span></span>
<a id="to-retrieve-the-azure-active-directory-tenant-id" class="xliff"></a>

<span data-ttu-id="de0c6-110">Você precisa recuperar a ID de locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="de0c6-110">You need to retrieve the Azure AD Tenant ID.</span></span>

1.  <span data-ttu-id="de0c6-111">Acesse o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="de0c6-111">Go to the [Azure portal](https://portal.azure.com/) and sign in with your credentials.</span></span>

2.  <span data-ttu-id="de0c6-112">No **Painel,** escolha **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="de0c6-112">You can see the **Dashboard,** choose **Azure Active Directory**.</span></span>

    ![Painel do Azure AD](./media/skycure-sso-1.png)

3.  <span data-ttu-id="de0c6-114">Na folha **Azure Active Directory** exibida, escolha **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="de0c6-114">The **Azure Active Directory** blade opens, choose **Properties**.</span></span>

    ![Folha Propriedades do Azure AD](./media/skycure-sso-2.png)

4.  <span data-ttu-id="de0c6-116">Clique no **ícone Copiar** sob a **ID de Diretório do Locatário** na folha **Propriedades do Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="de0c6-116">Click on the **Copy icon** under the **Tenant Directory ID** at **Azure Active Directory Properties** blade.</span></span>

5. <span data-ttu-id="de0c6-117">Cole o valor da ID de Diretório copiado em um arquivo de texto para usá-lo mais tarde.</span><span class="sxs-lookup"><span data-stu-id="de0c6-117">Paste the copied Directory ID value in a text file so you can use it later.</span></span> <span data-ttu-id="de0c6-118">O valor da ID de Diretório será solicitado posteriormente no processo de integração do Skycure e do Intune.</span><span class="sxs-lookup"><span data-stu-id="de0c6-118">The Directory ID value will be required later in the Skycure and Intune integration process.</span></span>

    ![Painel do Azure AD](./media/skycure-sso-3.png)

## <span data-ttu-id="de0c6-120">Permitir a comunicação do Skycure com o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="de0c6-120">Allow Skycure to communicate with Azure Active Directory</span></span>
<a id="allow-skycure-to-communicate-with-azure-active-directory" class="xliff"></a>

1.  <span data-ttu-id="de0c6-121">Insira a URL abaixo no navegador.</span><span class="sxs-lookup"><span data-stu-id="de0c6-121">Enter the below URL in your browser.</span></span> <span data-ttu-id="de0c6-122">Em vez de **DIRECTORY_ID**, insira sua ID de Locatário do Azure Active Directory copiada anteriormente no arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="de0c6-122">Instead of **DIRECTORY_ID**, enter your Azure Active Directory Tenant ID previously copied to the text file.</span></span>

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  <span data-ttu-id="de0c6-123">Você precisa fazer logon usando suas credenciais do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="de0c6-123">You need to login using your Azure Active Directory credentials.</span></span> <span data-ttu-id="de0c6-124">Clique em **Aceitar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="de0c6-124">Click **Accept** to continue.</span></span>

![Página de logon do Azure AD](./media/skycure-sso-4.png)

## <span data-ttu-id="de0c6-126">Criar um grupo de Segurança do Azure AD para Skycure (opcional)</span><span class="sxs-lookup"><span data-stu-id="de0c6-126">Create an Azure AD Security group for Skycure (optional)</span></span>
<a id="create-an-azure-ad-security-group-for-skycure-optional" class="xliff"></a>

<span data-ttu-id="de0c6-127">Talvez você queira criar um grupo de usuários dedicado que contêm usuários executando o Skycure (por exemplo, usuários do Skycure).</span><span class="sxs-lookup"><span data-stu-id="de0c6-127">You might want to create a dedicated user group which contain users running Skycure (e.g Skycure users).</span></span> <span data-ttu-id="de0c6-128">Isso pode ser útil ao analisar a atividade do Skycure por meio dos relatórios.</span><span class="sxs-lookup"><span data-stu-id="de0c6-128">This can be helpful when analyzing Skycure activity through the reports.</span></span>

-   <span data-ttu-id="de0c6-129">Saiba mais sobre [como criar um grupo e adicionar membros no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="de0c6-129">Learn more [how to create a group and add members in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span></span>

> [!NOTE] 
> <span data-ttu-id="de0c6-130">Você também pode usar um grupo de segurança existente do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="de0c6-130">You can also use an existing Azure AD security group.</span></span>

## <span data-ttu-id="de0c6-131">Configurar a conta do Azure AD para integrar o Intune ao Skycure</span><span class="sxs-lookup"><span data-stu-id="de0c6-131">Configure the Azure AD account to integrate Intune with Skycure</span></span>
<a id="configure-the-azure-ad-account-to-integrate-intune-with-skycure" class="xliff"></a>

1.  <span data-ttu-id="de0c6-132">No [Console de Gerenciamento do Skycure](https://aad.skycure.com/), insira a ID do Locatário do Azure Active Directory salva anteriormente no arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="de0c6-132">From the [Skycure Management Console](https://aad.skycure.com/), enter the Azure Active Directory Tenant ID previously saved in the text file.</span></span>

![Campo ID de Locatário do Azure AD no Console de Gerenciamento do Skycure](./media/skycure-sso-5.png)

> [!IMPORTANT] 
> <span data-ttu-id="de0c6-134">O Skycure valida se a ID de Locatário do Azure AD existe consultando o Azure AD. Após o Skycure encontrá-la, o administrador poderá prosseguir para a próxima etapa, que é a configuração Básica.</span><span class="sxs-lookup"><span data-stu-id="de0c6-134">Skycure validates if the Azure AD Tenant ID exists by querying Azure AD, once Skycure finds it, the admin can proceed to next step, which is the Basic setup.</span></span>

## <span data-ttu-id="de0c6-135">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="de0c6-135">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="de0c6-136">Baixar política de configuração de aplicativo iOS do Skycure</span><span class="sxs-lookup"><span data-stu-id="de0c6-136">Download Skycure iOS app configuration policy</span></span>](skycure-ios-app-configuration-policy-download.md)
