---
title: Como configurar o aplicativo do Portal da Empresa
titleSuffix: Intune on Azure
description: "Saiba como você pode aplicar a identidade visual específica à empresa ao aplicativo do Portal da Empresa do Intune. \""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ee3d77b74f2313a0746b041335865f1d967ad926
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <span data-ttu-id="1aac4-104">Como configurar o aplicativo Portal da Empresa do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1aac4-104">How to configure the Microsoft Intune Company Portal app</span></span>
<a id="how-to-configure-the-microsoft-intune-company-portal-app" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="1aac4-105">O Portal da Empresa do Microsoft Intune é o local em que os usuários acessam os dados da empresa e podem fazer tarefas comuns, como o registro de dispositivos, a instalação de aplicativos e a localização de informações de assistência do departamento de TI.</span><span class="sxs-lookup"><span data-stu-id="1aac4-105">The Microsoft Intune company portal is where users access company data and can do common tasks like enrolling devices, installing apps, and locating information for assistance from your IT department.</span></span>        

> [!Tip]        
> <span data-ttu-id="1aac4-106">Quando você personaliza o Portal da Empresa, as configurações se aplicam ao site do Portal da Empresa e aos aplicativos do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1aac4-106">When you customize the Company Portal, the configurations apply to both the Company Portal website and Company Portal apps.</span></span>       

<span data-ttu-id="1aac4-107">Personalizar o Portal da Empresa ajuda a fornecer uma experiência familiar e útil para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="1aac4-107">Customizing the Company Portal helps provide a familiar and helpful experience for your end users.</span></span> <span data-ttu-id="1aac4-108">Para isso, na carga de trabalho **Aplicativos móveis**, escolha **Configurar** > **Identidade Visual do Portal de Empresa** e defina as configurações necessárias.</span><span class="sxs-lookup"><span data-stu-id="1aac4-108">To do it, from the **Mobile apps** workload, choose  **Setup** > **Company Portal Branding**, then configure the required settings.</span></span>      

## <span data-ttu-id="1aac4-109">Declaração de privacidade e informações de contato de empresa</span><span class="sxs-lookup"><span data-stu-id="1aac4-109">Company contact information and privacy statement</span></span>
<a id="company-contact-information-and-privacy-statement" class="xliff"></a>        
<span data-ttu-id="1aac4-110">O nome da empresa é exibido como o título do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1aac4-110">The company name is displayed as the Company Portal title.</span></span> <span data-ttu-id="1aac4-111">Os detalhes e as informações de contato são exibidos para os usuários na tela **Contatar TI** do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1aac4-111">The contact information and details are displayed to users in the **Contact IT** screen of the Company Portal.</span></span> <span data-ttu-id="1aac4-112">A política de privacidade é exibida quando um usuário clica no link de privacidade.</span><span class="sxs-lookup"><span data-stu-id="1aac4-112">The privacy statement is displayed when a user clicks on the privacy link.</span></span>        


|<span data-ttu-id="1aac4-113">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="1aac4-113">Field name</span></span>|<span data-ttu-id="1aac4-114">Comprimento máx.</span><span class="sxs-lookup"><span data-stu-id="1aac4-114">Max length</span></span>|<span data-ttu-id="1aac4-115">Mais informações</span><span class="sxs-lookup"><span data-stu-id="1aac4-115">More information</span></span>|        
|-|-|-|     
|<span data-ttu-id="1aac4-116">**Nome da empresa**</span><span class="sxs-lookup"><span data-stu-id="1aac4-116">**Company name**</span></span>|<span data-ttu-id="1aac4-117">40</span><span class="sxs-lookup"><span data-stu-id="1aac4-117">40</span></span>|<span data-ttu-id="1aac4-118">Este é o nome exibido como título do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1aac4-118">This name is displayed as the title of the Company Portal.</span></span>|        
|<span data-ttu-id="1aac4-119">**Nome do contato do departamento de TI**</span><span class="sxs-lookup"><span data-stu-id="1aac4-119">**IT department contact name**</span></span>|<span data-ttu-id="1aac4-120">40</span><span class="sxs-lookup"><span data-stu-id="1aac4-120">40</span></span>|<span data-ttu-id="1aac4-121">Esse nome é exibido na página **Contatar TI**.</span><span class="sxs-lookup"><span data-stu-id="1aac4-121">This name is displayed on the **Contact IT** page.</span></span>|      
|<span data-ttu-id="1aac4-122">**Telefone do departamento de TI**</span><span class="sxs-lookup"><span data-stu-id="1aac4-122">**IT department phone number**</span></span>|<span data-ttu-id="1aac4-123">20</span><span class="sxs-lookup"><span data-stu-id="1aac4-123">20</span></span>|<span data-ttu-id="1aac4-124">Este número de contato é exibido na página **Contatar TI**.</span><span class="sxs-lookup"><span data-stu-id="1aac4-124">This contact number is displayed on the **Contact IT** page.</span></span>|        
|<span data-ttu-id="1aac4-125">Endereço de email do departamento de TI</span><span class="sxs-lookup"><span data-stu-id="1aac4-125">IT department email address</span></span>|<span data-ttu-id="1aac4-126">40</span><span class="sxs-lookup"><span data-stu-id="1aac4-126">40</span></span>|<span data-ttu-id="1aac4-127">Este endereço de contato é exibido na página **Contatar TI**.</span><span class="sxs-lookup"><span data-stu-id="1aac4-127">This contact address is displayed on the **Contact IT** page.</span></span> <span data-ttu-id="1aac4-128">Você deve inserir um endereço de email válido no formato **alias@domainname.com**.</span><span class="sxs-lookup"><span data-stu-id="1aac4-128">You must enter a valid email address in the format **alias@domainname.com**.</span></span>|     
|<span data-ttu-id="1aac4-129">**Informações adicionais**</span><span class="sxs-lookup"><span data-stu-id="1aac4-129">**Additional information**</span></span>|<span data-ttu-id="1aac4-130">120</span><span class="sxs-lookup"><span data-stu-id="1aac4-130">120</span></span>|<span data-ttu-id="1aac4-131">Exibido na página **Contatar TI**.</span><span class="sxs-lookup"><span data-stu-id="1aac4-131">Displayed on the **Contact IT** page.</span></span>|      
|<span data-ttu-id="1aac4-132">**URL da política de privacidade da empresa**</span><span class="sxs-lookup"><span data-stu-id="1aac4-132">**Company privacy statement URL**</span></span>|<span data-ttu-id="1aac4-133">79</span><span class="sxs-lookup"><span data-stu-id="1aac4-133">79</span></span>|<span data-ttu-id="1aac4-134">Você pode especificar a política de privacidade de sua própria empresa que será exibida quando os usuários clicarem nos links de privacidade do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1aac4-134">You can specify your own company privacy statement that appears when users click the privacy links from the Company Portal.</span></span> <span data-ttu-id="1aac4-135">Você deve digitar uma URL válida no formato **https://www.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="1aac4-135">You must enter a valid URL in the format **https://www.contoso.com**.</span></span>|        

## <span data-ttu-id="1aac4-136">Contatos de suporte</span><span class="sxs-lookup"><span data-stu-id="1aac4-136">Support contacts</span></span>
<a id="support-contacts" class="xliff"></a>     
<span data-ttu-id="1aac4-137">O site de suporte é exibido para os usuários no Portal da Empresa para que eles possam acessar o suporte online.</span><span class="sxs-lookup"><span data-stu-id="1aac4-137">The support website is displayed to users in the Company Portal to enable them to access online support.</span></span>        



|<span data-ttu-id="1aac4-138">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="1aac4-138">Field name</span></span>|<span data-ttu-id="1aac4-139">Comprimento máx.</span><span class="sxs-lookup"><span data-stu-id="1aac4-139">Max length</span></span>|<span data-ttu-id="1aac4-140">Mais informações</span><span class="sxs-lookup"><span data-stu-id="1aac4-140">More information</span></span>|        
|-|-|-|     
|<span data-ttu-id="1aac4-141">**URL do site de suporte**</span><span class="sxs-lookup"><span data-stu-id="1aac4-141">**Support website URL**</span></span>|<span data-ttu-id="1aac4-142">150</span><span class="sxs-lookup"><span data-stu-id="1aac4-142">150</span></span>|<span data-ttu-id="1aac4-143">Se tiver um site de suporte que queira que os usuários usem, especifique o URL aqui.</span><span class="sxs-lookup"><span data-stu-id="1aac4-143">If you have a support website that you want your users to use, specify the URL here.</span></span> <span data-ttu-id="1aac4-144">A URL deve estar no formato **https://www.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="1aac4-144">The URL must be in the format **https://www.contoso.com**.</span></span> <span data-ttu-id="1aac4-145">Se você não especificar uma URL, nada será exibido no site de suporte da página **Contatar TI**, no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1aac4-145">If you don't specify a URL, nothing is displayed for the support website on the **Contact IT** page in the Company Portal.</span></span>|        
|<span data-ttu-id="1aac4-146">**Nome do site de suporte**</span><span class="sxs-lookup"><span data-stu-id="1aac4-146">**Support website name**</span></span>|<span data-ttu-id="1aac4-147">40</span><span class="sxs-lookup"><span data-stu-id="1aac4-147">40</span></span>|<span data-ttu-id="1aac4-148">Este é o nome amigável exibido para a URL do site de suporte.</span><span class="sxs-lookup"><span data-stu-id="1aac4-148">This name is the friendly name that is displayed for the URL to the support website.</span></span> <span data-ttu-id="1aac4-149">Se você especificar uma URL do site de suporte e nenhum nome amigável, Ir para o site da TI será exibido na página **Contatar IT** do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1aac4-149">If you specify a support website URL and no friendly name, then Go to IT website is displayed on the **Contact IT** page in the Company Portal.</span></span>       

## <span data-ttu-id="1aac4-150">Personalização da identidade visual da empresa</span><span class="sxs-lookup"><span data-stu-id="1aac4-150">Company branding customization</span></span>
<a id="company-branding-customization" class="xliff"></a>       
<span data-ttu-id="1aac4-151">Você pode personalizar o Portal da Empresa com o logotipo e o nome da empresa, uma cor de tema e um segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1aac4-151">You can customize your Company Portal with your company logo, company name, theme color and background.</span></span>     



|<span data-ttu-id="1aac4-152">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="1aac4-152">Field name</span></span>|<span data-ttu-id="1aac4-153">Mais informações</span><span class="sxs-lookup"><span data-stu-id="1aac4-153">More information</span></span>|       
|-|-|       
|<span data-ttu-id="1aac4-154">**Cor de tema**</span><span class="sxs-lookup"><span data-stu-id="1aac4-154">**Theme color**</span></span>|<span data-ttu-id="1aac4-155">Selecione uma cor de tema para aplicar ao Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1aac4-155">Select a theme color to apply to the Company Portal.</span></span>|      
|<span data-ttu-id="1aac4-156">**Mostrar logotipo da empresa**</span><span class="sxs-lookup"><span data-stu-id="1aac4-156">**Show company logo**</span></span>|<span data-ttu-id="1aac4-157">Ao habilitar esta opção, você pode carregar o logotipo da empresa para ser exibido no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1aac4-157">When you enable this option, you can upload your company logo to show in your Company Portal.</span></span> <span data-ttu-id="1aac4-158">Você pode carregar dois logotipos: um que será exibido quando o segundo plano do Portal da Empresa for branco e outro que será exibido quando o segundo plano estiver usando a sua cor de tema selecionada.</span><span class="sxs-lookup"><span data-stu-id="1aac4-158">You can upload two logos: one logo that is displayed when the Company Portal background is white, and one logo that is displayed when the Company Portal background uses your selected theme color.</span></span> <span data-ttu-id="1aac4-159">Cada logotipo deve ser um tipo de arquivo .png ou .jpg e ter uma resolução máxima de 400 x 100 pixels e ter 750 KB ou menos em tamanho.</span><span class="sxs-lookup"><span data-stu-id="1aac4-159">Each logo must be a .png or .jpg file type and have a maximum resolution of 400 x 100 pixels and be 750 KB or less in size.</span></span><br><span data-ttu-id="1aac4-160">Também é possível mostrar o nome da empresa que você inseriu ao lado do logotipo carregado.</span><span class="sxs-lookup"><span data-stu-id="1aac4-160">You can also show the company name you entered next to the uploaded logo.</span></span>|      

<span data-ttu-id="1aac4-161">Depois de salvar suas alterações, você pode escolher **Visualizar as configurações no Portal da Web Intune** para ver a aparência de suas configurações.</span><span class="sxs-lookup"><span data-stu-id="1aac4-161">After you save your changes, you can choose **Preview your settings in the Intune Web Portal** to see how your configurations will look.</span></span>
