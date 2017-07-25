---
title: "Configurações de filtro de conteúdo da Web do Intune para dispositivos iOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações que você pode usar para permitir e bloquear o acesso a sites em dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 7/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16aa0f3c-8977-4495-9fbe-ca30ad278c9e
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1fb2ce8ed9db6ff808cac2ee8ff46ee865dbdf35
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
<<<<<<< HEAD
# <span data-ttu-id="a5205-103">Configurações de filtro de conteúdo da Web para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="a5205-103">Web content filter settings for iOS devices</span></span>
=======
# Configurações de filtro de conteúdo da Web para dispositivos iOS
>>>>>>> live
<a id="web-content-filter-settings-for-ios-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
<span data-ttu-id="a5205-104">Use essas configurações para definir as URLs que os usuários finais de navegadores da Web, em dispositivos iOS, podem ou não visitar.</span><span class="sxs-lookup"><span data-stu-id="a5205-104">Use these settings to configure URLs that end users of web browsers, on iOS devices, can, or cannot visit.</span></span> <span data-ttu-id="a5205-105">Existem dois métodos que você pode usar para configurar URLs:</span><span class="sxs-lookup"><span data-stu-id="a5205-105">There are two methods you can use to do configure URLs:</span></span>

- <span data-ttu-id="a5205-106">**Configurar URLs** – Use o filtro da Web interno da Apple que procura termos adultos como profanação ou linguagem pornográficas.</span><span class="sxs-lookup"><span data-stu-id="a5205-106">**Configure URLs** - Use Apple’s built-in web filter that looks for adult terms like profanity or sexually explicit language.</span></span> <span data-ttu-id="a5205-107">Essa função avalia cada página da Web conforme ela é carregada e tenta identificar e bloquear conteúdo inadequado.</span><span class="sxs-lookup"><span data-stu-id="a5205-107">This function evaluates each web page as it is loaded and attempts to identify and block unsuitable content.</span></span> <span data-ttu-id="a5205-108">Você também pode configurar as URLs que não serão verificadas pelo filtro ou URLs que serão sempre bloqueadas, independentemente das configurações do filtro.</span><span class="sxs-lookup"><span data-stu-id="a5205-108">You can also configure URLs that are not checked by the filter, or URLs that are blocked, regardless of the filter settings.</span></span>

- <span data-ttu-id="a5205-109">**Somente para sites específicos** (somente para o navegador da Web Safari somente) - essas URLs são adicionadas aos favoritos do navegador Safari.</span><span class="sxs-lookup"><span data-stu-id="a5205-109">**Specific websites only** (for the Safari web browser only) - These URLs are added to the Safari browser’s bookmarks.</span></span> <span data-ttu-id="a5205-110">O usuário **só** tem permissão para visitar esses sites; nenhum outro site pode ser acessado.</span><span class="sxs-lookup"><span data-stu-id="a5205-110">The user is **only** allowed to visit these sites; no other sites can be accessed.</span></span> <span data-ttu-id="a5205-111">Use essa opção somente se você conhecer a lista exata de URLs que os usuários podem acessar.</span><span class="sxs-lookup"><span data-stu-id="a5205-111">Use this option only if you know the exact list of URLs that users can access.</span></span>
<span data-ttu-id="a5205-112">Se você não especificar nenhuma URL, os usuários finais não poderão acessar nenhum site, exceto microsoft.com, microsoft.net e apple.com.</span><span class="sxs-lookup"><span data-stu-id="a5205-112">If you do not specify any URLs, then end users cannot access any websites except for microsoft.com, microsoft.net, and apple.com.</span></span>



## <span data-ttu-id="a5205-113">Introdução</span><span class="sxs-lookup"><span data-stu-id="a5205-113">Get started</span></span>
<a id="get-started" class="xliff"></a>

1. <span data-ttu-id="a5205-114">Na folha Recursos do dispositivo escolha **Filtro de Conteúdo da Web (somente supervisionado)**.</span><span class="sxs-lookup"><span data-stu-id="a5205-114">On the Device features blade, choose **Web Content Filter (supervised only)**.</span></span>
2. <span data-ttu-id="a5205-115">Na folha **Filtro de Conteúdo da Web**, escolha o **Tipo de filtro** que você deseja configurar:</span><span class="sxs-lookup"><span data-stu-id="a5205-115">On the **Web Content Filter** blade, choose the **Filter type** you want to configure from:</span></span>
    - <span data-ttu-id="a5205-116">**Não Configurado** - nenhuma filtragem será executada.</span><span class="sxs-lookup"><span data-stu-id="a5205-116">**Not Configured** - No filtering is performed.</span></span>
    - <span data-ttu-id="a5205-117">**Configurar URLs**</span><span class="sxs-lookup"><span data-stu-id="a5205-117">**Configure URLs**</span></span>
    - <span data-ttu-id="a5205-118">**Somente sites específicos**</span><span class="sxs-lookup"><span data-stu-id="a5205-118">**Specific websites only**</span></span>
3. <span data-ttu-id="a5205-119">Em seguida, dependendo do tipo de filtro que você estiver usando, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="a5205-119">Next, depending on the filter type you are using, use one of the following procedures:</span></span>


## <span data-ttu-id="a5205-120">Configurar URLs</span><span class="sxs-lookup"><span data-stu-id="a5205-120">Configure URLs</span></span>
<a id="configure-urls" class="xliff"></a>

1. <span data-ttu-id="a5205-121">Na folha **Filtro de Conteúdo da Web**, escolha uma das configurações a seguir, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="a5205-121">On the **Web Content Filter** blade, choose one of the following settings as required:</span></span>
    - <span data-ttu-id="a5205-122">**URLs Permitidas** - na folha **URLs Permitidas**, insira as URLs que você deseja permitir (ignorando o Filtro da Web da Apple) e escolha enter após cada uma.</span><span class="sxs-lookup"><span data-stu-id="a5205-122">**Permitted URLs** - On the **Permitted URLs** blade, enter the URLs you want to allow (bypassing the Apple web filter), and choose enter after each.</span></span>
    - <span data-ttu-id="a5205-123">**URLs Bloqueadas** - na folha **URLs Bloqueadas**, insira as URLs que você deseja bloquear (independentemente das configurações do Filtro da Web da Apple) e escolha enter após cada uma.</span><span class="sxs-lookup"><span data-stu-id="a5205-123">**Blocked URLs** - On the **Blocked URLs** blade, enter the URLs you want to block (regardless of the Apple web filter settings), and choose enter after each.</span></span>
2. <span data-ttu-id="a5205-124">Ao terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5205-124">When you are finished, click **OK**.</span></span>


## <span data-ttu-id="a5205-125">Somente sites específicos</span><span class="sxs-lookup"><span data-stu-id="a5205-125">Specific websites only</span></span>
<a id="specific-websites-only" class="xliff"></a>

1. <span data-ttu-id="a5205-126">Na folha **Filtro de Conteúdo da Web**, para cada site da Web que você deseja permitir, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a5205-126">On the **Web Content Filter** blade, for each web site you want to permit, configure the following settings:</span></span>
    - <span data-ttu-id="a5205-127">**URL** - insira a URL do site que você deseja permitir, por exemplo, **http://www.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="a5205-127">**URL** - Enter the URL of the website you want to permit, for example, **http://www.contoso.com**.</span></span>
    - <span data-ttu-id="a5205-128">**Caminho do Favorito** - insira o caminho até o local onde você deseja armazenar o favorito por exemplo **/Contoso/Aplicativos de Empresa**.</span><span class="sxs-lookup"><span data-stu-id="a5205-128">**Bookmark Path** - Enter the path to where you want to store the bookmark, for example **/Contoso/Business Apps**.</span></span> <span data-ttu-id="a5205-129">Se você não adicionar um indicador, ele será adicionado à pasta de indicadores padrão no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a5205-129">If you don't add a path, the bookmark is added to the default bookmark folder on the device.</span></span>
    - <span data-ttu-id="a5205-130">**Título** - insira um título descritivo para o favorito.</span><span class="sxs-lookup"><span data-stu-id="a5205-130">**Title** - Enter a descriptive title for the bookmark.</span></span>
2. <span data-ttu-id="a5205-131">Clique em **Adicionar** depois de inserir as informações para cada site.</span><span class="sxs-lookup"><span data-stu-id="a5205-131">Click **Add** after you enter the information for each website.</span></span>
3. <span data-ttu-id="a5205-132">Ao terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5205-132">When you are finished, click **OK**.</span></span>

>[!IMPORTANT] 
> <span data-ttu-id="a5205-133">As URLs a seguir têm permissão automática do Intune.</span><span class="sxs-lookup"><span data-stu-id="a5205-133">The following URLs are permitted automatically by Intune.</span></span>
> - <span data-ttu-id="a5205-134">www.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a5205-134">www.microsoft.com</span></span>
> - <span data-ttu-id="a5205-135">www.microsoft.net</span><span class="sxs-lookup"><span data-stu-id="a5205-135">www.microsoft.net</span></span>
> - <span data-ttu-id="a5205-136">www.apple.com</span><span class="sxs-lookup"><span data-stu-id="a5205-136">www.apple.com</span></span>

## <span data-ttu-id="a5205-137">Concluir</span><span class="sxs-lookup"><span data-stu-id="a5205-137">Finish up</span></span>
<a id="finish-up" class="xliff"></a>

<span data-ttu-id="a5205-138">Escolha **OK** para retornar à folha **Criar Perfil** e, em seguida, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="a5205-138">Choose **OK** to return to the **Create Profile** blade, and then choose **Create**.</span></span>

## <span data-ttu-id="a5205-139">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a5205-139">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="a5205-140">Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos.</span><span class="sxs-lookup"><span data-stu-id="a5205-140">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="a5205-141">Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="a5205-141">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>
=======
Use essas configurações para definir as URLs que os usuários finais de navegadores da Web, em dispositivos iOS, podem ou não visitar. Existem dois métodos que você pode usar para configurar URLs:

- **Configurar URLs** – Use o filtro da Web interno da Apple que procura termos adultos como profanação ou linguagem pornográficas. Essa função avalia cada página da Web conforme ela é carregada e tenta identificar e bloquear conteúdo inadequado. Você também pode configurar as URLs que não serão verificadas pelo filtro ou URLs que serão sempre bloqueadas, independentemente das configurações do filtro.

- **Somente para sites específicos** (somente para o navegador da Web Safari somente) - essas URLs são adicionadas aos favoritos do navegador Safari. O usuário **só** tem permissão para visitar esses sites; nenhum outro site pode ser acessado. Use essa opção somente se você conhecer a lista exata de URLs que os usuários podem acessar.
Se você não especificar nenhuma URL, os usuários finais não poderão acessar nenhum site, exceto microsoft.com, microsoft.net e apple.com.



## Introdução
<a id="get-started" class="xliff"></a>

1. Na folha Recursos do dispositivo escolha **Filtro de Conteúdo da Web (somente supervisionado)**.
2. Na folha **Filtro de Conteúdo da Web**, escolha o **Tipo de filtro** que você deseja configurar:
    - **Não Configurado** - nenhuma filtragem será executada.
    - **Configurar URLs**
    - **Somente sites específicos**
3. Em seguida, dependendo do tipo de filtro que você estiver usando, siga um destes procedimentos:


## Configurar URLs
<a id="configure-urls" class="xliff"></a>

1. Na folha **Filtro de Conteúdo da Web**, escolha uma das configurações a seguir, conforme necessário:
    - **URLs Permitidas** - na folha **URLs Permitidas**, insira as URLs que você deseja permitir (ignorando o Filtro da Web da Apple) e escolha enter após cada uma.
    - **URLs Bloqueadas** - na folha **URLs Bloqueadas**, insira as URLs que você deseja bloquear (independentemente das configurações do Filtro da Web da Apple) e escolha enter após cada uma.
2. Ao terminar, clique em **OK**.


## Somente sites específicos
<a id="specific-websites-only" class="xliff"></a>

1. Na folha **Filtro de Conteúdo da Web**, para cada site da Web que você deseja permitir, defina as seguintes configurações:
    - **URL** - insira a URL do site que você deseja permitir, por exemplo, **http://www.contoso.com**.
    - **Caminho do Favorito** - insira o caminho até o local onde você deseja armazenar o favorito por exemplo **/Contoso/Aplicativos de Empresa**. Se você não adicionar um indicador, ele será adicionado à pasta de indicadores padrão no dispositivo.
    - **Título** - insira um título descritivo para o favorito.
2. Clique em **Adicionar** depois de inserir as informações para cada site.
3. Ao terminar, clique em **OK**.

>[!IMPORTANT] 
> As URLs a seguir têm permissão automática do Intune.
> - www.microsoft.com
> - www.microsoft.net
> - www.apple.com

## Concluir
<a id="finish-up" class="xliff"></a>

Escolha **OK** para retornar à folha **Criar Perfil** e, em seguida, escolha **Criar**.

## Próximas etapas
<a id="next-steps" class="xliff"></a>

Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos. Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
>>>>>>> live
