---
title: "Configurar um nome de domínio personalizado"
description: "Adicionar um nome de domínio personalizado para sua assinatura do Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1223d215058509a6a672c7a34bb22eee893b1350
ms.sourcegitcommit: b287025b1a0d09d41faf51cf98c34b676fa1d98e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2017
---
# <a name="configure-a-custom-domain-name"></a><span data-ttu-id="48c9a-103">Configurar um nome de domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="48c9a-103">Configure a custom domain name</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="48c9a-104">Este tópico informa os administradores como eles podem criar um DNS CNAME para simplificar e personalizar sua experiência de logon.</span><span class="sxs-lookup"><span data-stu-id="48c9a-104">This topic tells administrators how they can create a DNS CNAME to simplify and customize their logon experience.</span></span>

<<<<<<< HEAD
<span data-ttu-id="48c9a-105">Quando sua empresa se inscreve em um serviço baseado em nuvem da Microsoft como o Intune, você recebe um nome de domínio inicial hospedado no Azure Active Directory (AD), que é semelhante a **seudomínio.onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="48c9a-105">When your organization signs up for a Microsoft cloud-based service like Intune, you're given an initial domain name hosted in Azure Active Directory (AD) that looks like **your-domain.onmicrosoft.com**.</span></span> <span data-ttu-id="48c9a-106">Nesse exemplo, **seudomínio** é o nome de domínio que você escolheu ao se inscrever.</span><span class="sxs-lookup"><span data-stu-id="48c9a-106">In this example, **your-domain** is the domain name that you chose when you signed up.</span></span> <span data-ttu-id="48c9a-107">**onmicrosoft.com** é o sufixo atribuído às contas que você adiciona à sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="48c9a-107">**onmicrosoft.com** is the suffix assigned to the accounts you add to your subscription.</span></span> <span data-ttu-id="48c9a-108">Você pode configurar o domínio personalizado da organização para acessar o Intune, em vez de usar o nome de domínio fornecido com a sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="48c9a-108">You can configure your organization's custom domain to access Intune instead of the domain name provided with your subscription.</span></span>

<span data-ttu-id="48c9a-109">Antes de criar contas de usuário ou sincronizar seu Active Directory local, recomendamos fortemente que você decida se usará somente o domínio .onmicrosoft.com ou se adicionará um ou mais nomes de domínios personalizados.</span><span class="sxs-lookup"><span data-stu-id="48c9a-109">Before you create user accounts or synchronize your on-premises Active Directory, we strongly recommend that you decide whether to use only the .onmicrosoft.com domain or to add one or more of your custom domain names.</span></span> <span data-ttu-id="48c9a-110">Configure um domínio personalizado antes de adicionar usuários para simplificar o gerenciamento de usuários.</span><span class="sxs-lookup"><span data-stu-id="48c9a-110">Set up a custom domain before adding users to simplify user management.</span></span> <span data-ttu-id="48c9a-111">Isso permite que os usuários entrem com as credenciais que usam para acessar outros recursos do domínio.</span><span class="sxs-lookup"><span data-stu-id="48c9a-111">This lets users sign in with the credentials they use to access other domain resources.</span></span>
=======
Quando sua empresa se inscreve em um serviço baseado em nuvem da Microsoft como o Intune, você recebe um nome de domínio inicial hospedado no Azure Active Directory (AD), que é semelhante a **seudomínio.onmicrosoft.com**. Nesse exemplo, **seudomínio** é o nome de domínio que você escolheu ao se inscrever. **onmicrosoft.com** é o sufixo atribuído às contas que você adiciona à sua assinatura. Você pode configurar o domínio personalizado da organização para acessar o Intune, em vez de usar o nome de domínio fornecido com a sua assinatura.

Antes de criar contas de usuário ou sincronizar seu Active Directory local, recomendamos fortemente que você decida se usará somente o domínio .onmicrosoft.com ou se adicionará um ou mais nomes de domínios personalizados. Configure um domínio personalizado antes de adicionar usuários para simplificar o gerenciamento de usuários. Isso permite que os usuários entrem com as credenciais que usam para acessar outros recursos do domínio.
>>>>>>> live

<span data-ttu-id="48c9a-112">Ao assinar um serviço baseado em nuvem da Microsoft, sua instância desse serviço torna-se um [locatário do Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), que fornece serviços de identidade e diretório para o seu serviço baseado em nuvem.</span><span class="sxs-lookup"><span data-stu-id="48c9a-112">When you subscribe to a cloud-based service from Microsoft, your instance of that service becomes a Microsoft  [Azure AD tenant](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), which provides identity and directory services for your cloud-based service.</span></span> <span data-ttu-id="48c9a-113">Como as tarefas para configurar o Intune para usar o nome de domínio personalizado das organizações são as mesmas para os outros locatários do Azure AD, use as informações e procedimentos encontrados em [Adicionar seu domínio](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).</span><span class="sxs-lookup"><span data-stu-id="48c9a-113">And, because the tasks to configure Intune to use your organizations custom domain name are the same as for other Azure AD tenants, you can use the information and procedures found in [Add your domain](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).</span></span>

> [!TIP]
<<<<<<< HEAD
> <span data-ttu-id="48c9a-114">Para saber mais sobre os domínios personalizados, consulte [Visão geral conceitual dos nomes de domínio personalizados no Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).</span><span class="sxs-lookup"><span data-stu-id="48c9a-114">To learn more about custom domains, see [Conceptual overview of custom domain names in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).</span></span>

<span data-ttu-id="48c9a-115">Você não pode renomear nem remover o nome de domínio inicial onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="48c9a-115">You cannot rename or remove the initial onmicrosoft.com domain name.</span></span> <span data-ttu-id="48c9a-116">Você pode adicionar, verificar ou remover os nomes de domínio personalizados usados com o Intune para manter sua identidade de empresa limpa.</span><span class="sxs-lookup"><span data-stu-id="48c9a-116">You can add, verify or remove custom domain names used with Intune to keep your business identity clear.</span></span>
=======
> Para saber mais sobre os domínios personalizados, consulte [Visão geral conceitual dos nomes de domínio personalizados no Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

Você não pode renomear nem remover o nome de domínio inicial onmicrosoft.com. Você pode adicionar, verificar ou remover os nomes de domínio personalizados usados com o Intune para manter sua identidade de empresa limpa.
>>>>>>> live

## <a name="to-add-and-verify-your-custom-domain"></a><span data-ttu-id="48c9a-117">Para adicionar e verificar seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="48c9a-117">To add and verify your custom domain</span></span>

1. <span data-ttu-id="48c9a-118">Vá para [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx) e entre em sua conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="48c9a-118">Go to [Office 365 management portal](https://portal.office.com/Admin/Default.aspx) and sign into your administrator account.</span></span>

2. <span data-ttu-id="48c9a-119">No painel de navegação, escolha **Configurações** &gt; **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="48c9a-119">In the navigation pane, choose **Settings** &gt; **Domains**.</span></span>

<<<<<<< HEAD
3. <span data-ttu-id="48c9a-120">Escolha **Adicionar domínio** e digite o nome de domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="48c9a-120">Choose **Add domain**, and type your custom domain name.</span></span>
   <span data-ttu-id="48c9a-121">![Captura de tela do Office 365 Admin Center com a opção Configurações > Domínios selecionada e um novo nome de domínio sendo adicionado](./media/domain-custom-add.png)</span><span class="sxs-lookup"><span data-stu-id="48c9a-121">![Screenshot of Office 365 Admin Center with Settings > Domains selected and a new domain name being added](./media/domain-custom-add.png)</span></span>
4. <span data-ttu-id="48c9a-122">A caixa de diálogo **Verificar domínio** é aberta, fornecendo os valores para criar o registro TXT no seu provedor de hospedagem de DNS.</span><span class="sxs-lookup"><span data-stu-id="48c9a-122">The **Verify domain** dialog box opens giving you the values to create the TXT record in your DNS hosting provider.</span></span>
    - <span data-ttu-id="48c9a-123">**Usuários do GoDaddy**: o Portal de gerenciamento do Office 365 redireciona você para a página de logon do GoDaddy.</span><span class="sxs-lookup"><span data-stu-id="48c9a-123">**GoDaddy users**: Office 365 Management portal redirects you to GoDaddy's login page.</span></span> <span data-ttu-id="48c9a-124">Após inserir suas credenciais e aceitar o contrato de permissão de alteração de domínio, o registro TXT é criado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="48c9a-124">After you enter your credentials and accept the domain change permission agreement, the TXT record is created automatically.</span></span> <span data-ttu-id="48c9a-125">Como alternativa, [crie o registro TXT](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).</span><span class="sxs-lookup"><span data-stu-id="48c9a-125">You can alternatively [create the TXT record](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).</span></span>
    - <span data-ttu-id="48c9a-126">**Usuários do Register.com**: siga as [instruções passo a passo](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) para criar o registro TXT.</span><span class="sxs-lookup"><span data-stu-id="48c9a-126">**Register.com users**: Follow the [step-by-step instructions](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) to create the TXT record.</span></span>

<span data-ttu-id="48c9a-127">As etapas para adicionar e verificar um domínio personalizado também podem ser [executadas no Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).</span><span class="sxs-lookup"><span data-stu-id="48c9a-127">The steps to add and verify a custom domain can also be [performed in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).</span></span>
=======
3. Escolha **Adicionar domínio** e digite o nome de domínio personalizado.
   ![Captura de tela do Office 365 Admin Center com a opção Configurações > Domínios selecionada e um novo nome de domínio sendo adicionado](./media/domain-custom-add.png)
4. A caixa de diálogo **Verificar domínio** é aberta, fornecendo os valores para criar o registro TXT no seu provedor de hospedagem de DNS.
    - **Usuários do GoDaddy**: o Portal de gerenciamento do Office 365 redireciona você para a página de logon do GoDaddy. Após inserir suas credenciais e aceitar o contrato de permissão de alteração de domínio, o registro TXT é criado automaticamente. Como alternativa, [crie o registro TXT](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).
    - **Usuários do Register.com**: siga as [instruções passo a passo](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) para criar o registro TXT.
>>>>>>> live

<span data-ttu-id="48c9a-128">É possível saber mais [Sobre o domínio inicial onmicrosoft.com no Office 365](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A)</span><span class="sxs-lookup"><span data-stu-id="48c9a-128">You can learn more [about your initial onmicrosoft.com domain in Office 365](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A)</span></span>
