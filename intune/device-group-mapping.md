---
title: Como usar categorias de dispositivo no Intune
titleSuffix: Intune on Azure
description: "Saiba como usar as categorias de dispositivos entre as quais os usuários podem escolher quando registram seus dispositivos no Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e7c46a0bab45223293b73f8eaa2f8b40850cd43
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="95d36-103">Mapear grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="95d36-103">Map device groups</span></span>
<a id="map-device-groups" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="95d36-104">Use as categorias de dispositivo do Microsoft Intune para adicionar dispositivos aos grupos automaticamente, com base nas categorias que você definir para facilitar o gerenciamento desses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="95d36-104">Use Microsoft Intune device categories to automatically add devices to groups based on categories that you define, in order to make it easier for you to manage those devices.</span></span>

<span data-ttu-id="95d36-105">Categorias de dispositivo usam o seguinte fluxo de trabalho:</span><span class="sxs-lookup"><span data-stu-id="95d36-105">Device categories use the following workflow:</span></span>
1. <span data-ttu-id="95d36-106">Crie categorias para os usuários escolherem quando registrarem seus dispositivos</span><span class="sxs-lookup"><span data-stu-id="95d36-106">Create categories that users will choose from when they enroll their device</span></span>
3. <span data-ttu-id="95d36-107">Quando os usuários finais de dispositivos iOS e Android registram seus dispositivos, eles devem escolher uma categoria na lista de categorias configuradas.</span><span class="sxs-lookup"><span data-stu-id="95d36-107">When end users of iOS and Android devices enroll their device, they must choose a category from the list of categories you configured.</span></span> <span data-ttu-id="95d36-108">Para atribuir uma categoria a um dispositivo Windows, os usuários finais devem usar o site do Portal da Empresa (consulte **Depois de configurar os grupos de dispositivos** neste tópico para obter mais detalhes).</span><span class="sxs-lookup"><span data-stu-id="95d36-108">To assign a category to a Windows device, end users must use the Company Portal website (see **After you configure device groups** in this topic for more details).</span></span>
4. <span data-ttu-id="95d36-109">Depois, é possível implantar políticas e aplicativos nesses grupos.</span><span class="sxs-lookup"><span data-stu-id="95d36-109">You can then deploy policies and apps to these groups.</span></span>

<span data-ttu-id="95d36-110">Você pode criar as categorias de dispositivo que desejar, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="95d36-110">You can create any device categories you want, for example:</span></span>
- <span data-ttu-id="95d36-111">Dispositivo de ponto de venda</span><span class="sxs-lookup"><span data-stu-id="95d36-111">Point of sale device</span></span>
- <span data-ttu-id="95d36-112">Dispositivo de demonstração</span><span class="sxs-lookup"><span data-stu-id="95d36-112">Demonstration device</span></span>
- <span data-ttu-id="95d36-113">Vendas</span><span class="sxs-lookup"><span data-stu-id="95d36-113">Sales</span></span>
- <span data-ttu-id="95d36-114">Contabilização</span><span class="sxs-lookup"><span data-stu-id="95d36-114">Accounting</span></span>
- <span data-ttu-id="95d36-115">Manager</span><span class="sxs-lookup"><span data-stu-id="95d36-115">Manager</span></span>

## <span data-ttu-id="95d36-116">Como definir categorias de dispositivo</span><span class="sxs-lookup"><span data-stu-id="95d36-116">How to configure device categories</span></span>
<a id="how-to-configure-device-categories" class="xliff"></a>

### <span data-ttu-id="95d36-117">Etapa 1 – Criar categorias de dispositivo na folha do Intune no Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="95d36-117">Step 1 - Create device categories in the Intune blade of the Azure portal</span></span>
<a id="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal" class="xliff"></a>
1. <span data-ttu-id="95d36-118">No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="95d36-118">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="95d36-119">Na folha **Intune**, escolha **Registrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="95d36-119">On the **Intune** blade, choose **Enroll devices**.</span></span>
3. <span data-ttu-id="95d36-120">Na folha **Registro**, escolha **Categorias de Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="95d36-120">In the **Enrollment** blade, choose **Device Categories**.</span></span>
4. <span data-ttu-id="95d36-121">Na página **Categorias de Dispositivo**, escolha **Criar** para adicionar uma nova categoria.</span><span class="sxs-lookup"><span data-stu-id="95d36-121">On the **Device Categories** page, choose **Create** to add a new category.</span></span>
5. <span data-ttu-id="95d36-122">Na folha seguinte, insira um **Nome** para a nova categoria e uma **Descrição** opcional.</span><span class="sxs-lookup"><span data-stu-id="95d36-122">In the next blade, enter a **Name** for the new category, and an optional **Description**.</span></span>
6. <span data-ttu-id="95d36-123">Quando terminar, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="95d36-123">When you are done, click **Create**.</span></span> <span data-ttu-id="95d36-124">Você verá a categoria que você acabou de criar na lista de categorias.</span><span class="sxs-lookup"><span data-stu-id="95d36-124">You’ll see the category you just created in the list of categories.</span></span>

<span data-ttu-id="95d36-125">Você usará o nome da categoria do dispositivo quando criar grupos de segurança do Azure Active Directory na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="95d36-125">You'll use the device category name when you create Azure Active Directory security groups in step 2.</span></span>

### <span data-ttu-id="95d36-126">Etapa 2 – Criar grupos de segurança do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="95d36-126">Step 2 - Create Azure Active Directory security groups</span></span>
<a id="step-2---create-azure-active-directory-security-groups" class="xliff"></a>
<span data-ttu-id="95d36-127">Nesta etapa, você criará grupos dinâmicos no portal do Azure com base na categoria do dispositivo e no nome da categoria do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="95d36-127">In this step, you'll create dynamic groups in the Azure portal based on the device category and device category name.</span></span>

<span data-ttu-id="95d36-128">Para continuar, consulte o tópico [Usar atributos para criar regras avançadas](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) na documentação do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="95d36-128">To continue, refer to the topic [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in the Azure Active Directory documentation.</span></span> 

<span data-ttu-id="95d36-129">Use as informações dessa seção para criar um grupo de dispositivos com uma regra avançada usando o atributo **deviceCategory**.</span><span class="sxs-lookup"><span data-stu-id="95d36-129">Use the information in this section to create a device group with an advanced rule using the **deviceCategory** attribute.</span></span> <span data-ttu-id="95d36-130">Por exemplo (**device.deviceCategory -eq** "*<the device category name you got from the Intune portal>*")</span><span class="sxs-lookup"><span data-stu-id="95d36-130">For example (**device.deviceCategory -eq** "*<the device category name you got from the Intune portal>*")</span></span>

<span data-ttu-id="95d36-131">Após configurar os grupos de dispositivos e quando os usuários registrarem seus dispositivos, eles verão uma lista de categorias que você configurou.</span><span class="sxs-lookup"><span data-stu-id="95d36-131">After you configure device groups, and users enroll their device, they are presented with a list of the categories you configured.</span></span> <span data-ttu-id="95d36-132">Depois que escolherem uma categoria e concluírem o registro, o dispositivo será adicionado ao grupo de segurança do Active Directory que corresponde à categoria escolhida.</span><span class="sxs-lookup"><span data-stu-id="95d36-132">After they choose a category and finish enrollment, their device is added to the Active Directory security group that corresponds with the category they chose.</span></span>

### <span data-ttu-id="95d36-133">Como exibir as categorias dos dispositivos que você gerencia</span><span class="sxs-lookup"><span data-stu-id="95d36-133">How to view the categories of devices you manage</span></span>
<a id="how-to-view-the-categories-of-devices-you-manage" class="xliff"></a>

1.  <span data-ttu-id="95d36-134">No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="95d36-134">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

2. <span data-ttu-id="95d36-135">Na folha do Intune do Portal do Azure, escolha **Dispositivos e Grupos**.</span><span class="sxs-lookup"><span data-stu-id="95d36-135">In the Intune blade of the Azure portal, choose **Devices and Groups**.</span></span>

3.  <span data-ttu-id="95d36-136">Em **Gerenciar**, clique em **Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="95d36-136">Under **Manage**, click **All devices**.</span></span>

4.  <span data-ttu-id="95d36-137">Na lista de dispositivos, examine a coluna **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="95d36-137">In the list of devices, examine the **Category** column.</span></span>

<span data-ttu-id="95d36-138">Se a coluna **Categoria** não for exibida, clique em **Colunas**, escolha **Categoria** na lista e clique **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="95d36-138">If the **Category** column isn’t displayed, click **Columns**, choose **Category** from the list, and then click **Apply**.</span></span>

### <span data-ttu-id="95d36-139">Para alterar a categoria de um dispositivo</span><span class="sxs-lookup"><span data-stu-id="95d36-139">To change the category of a device</span></span>
<a id="to-change-the-category-of-a-device" class="xliff"></a>

1. <span data-ttu-id="95d36-140">No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="95d36-140">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="95d36-141">Na folha **Intune**, escolha **Dispositivos e Grupos**.</span><span class="sxs-lookup"><span data-stu-id="95d36-141">On the **Intune** blade, choose **Devices & Groups**.</span></span>
4. <span data-ttu-id="95d36-142">Na folha **Dispositivos e Grupos**, escolha **Gerenciar** > **Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="95d36-142">On the **Devices and Groups** blade, choose **Manage** > **All devices**.</span></span>
5. <span data-ttu-id="95d36-143">Na lista de dispositivos, selecione o dispositivo desejado e, na folha de propriedades do dispositivo, escolha **Gerenciar** > **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="95d36-143">In the list of devices, choose the device you want, then, on the device properties blade, choose **Manage** > **Properties**.</span></span>
6. <span data-ttu-id="95d36-144">Na próxima folha, você pode alterar a **Categoria de dispositivo** do dispositivo selecionado para qualquer um dos nomes das categorias que você configurou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="95d36-144">On the next blade, you can change the **Device category** of the selected device to any of the category names you previously configured.</span></span>

## <span data-ttu-id="95d36-145">Depois de configurar os grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="95d36-145">After you configure device groups</span></span>
<a id="after-you-configure-device-groups" class="xliff"></a>

<span data-ttu-id="95d36-146">Quando os usuários finais de dispositivos iOS e Android registram seus dispositivos, eles devem escolher uma categoria na lista de categorias configuradas.</span><span class="sxs-lookup"><span data-stu-id="95d36-146">When end users of iOS and Android devices enroll their device, they must choose a category from the list of categories you configured.</span></span> <span data-ttu-id="95d36-147">Depois que eles escolherem uma categoria e concluírem o registro, o dispositivo será adicionado ao grupo de dispositivos do Intune ou ao grupo de segurança do Active Directory que corresponde à categoria escolhida.</span><span class="sxs-lookup"><span data-stu-id="95d36-147">After they choose a category and finish enrollment, their device is added to the Intune device group, or Active Directory security group that corresponds with the category they chose.</span></span>

<span data-ttu-id="95d36-148">Para atribuir uma categoria a um dispositivo Windows, os usuários finais devem usar o site do Portal da Empresa (portal.manage.microsoft.com) após o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="95d36-148">To assign a category to a Windows device, end users must use the Company Portal website (portal.manage.microsoft.com) after enrolling the device.</span></span> <span data-ttu-id="95d36-149">Em um dispositivo Windows, acesse o site e, em seguida, **Menu** > **Meus Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="95d36-149">On a Windows device, access the website and go to **Menu** > **My Devices**.</span></span> <span data-ttu-id="95d36-150">Escolha um dispositivo registrado listado na página e, depois, selecione uma categoria.</span><span class="sxs-lookup"><span data-stu-id="95d36-150">Choose an enrolled device listed on the page, then select a category.</span></span> 

<span data-ttu-id="95d36-151">Depois de escolher uma categoria, o dispositivo é adicionado automaticamente ao grupo correspondente que você criou.</span><span class="sxs-lookup"><span data-stu-id="95d36-151">After choosing a category, the device is automatically added to the corresponding group you created.</span></span> <span data-ttu-id="95d36-152">Se um dispositivo já estiver registrado antes da configuração de categorias, o usuário final verá uma notificação sobre o dispositivo no site do Portal da Empresa e deverá selecionar uma categoria na próxima vez que acessar o aplicativo do Portal da Empresa no iOS ou no Android.</span><span class="sxs-lookup"><span data-stu-id="95d36-152">If a device is already enrolled before you configure categories, the end user will see a notification about the device on the Company Portal website, and will be asked to select a category the next time they access the Company Portal app on iOS or Android.</span></span>

## <span data-ttu-id="95d36-153">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="95d36-153">Further information</span></span>
<a id="further-information" class="xliff"></a>
- <span data-ttu-id="95d36-154">Você pode editar uma categoria de dispositivo no Portal do Azure, mas se fizer isso, deverá atualizar manualmente todos os grupos de segurança do Azure Active Directory que fazem referência a essa categoria.</span><span class="sxs-lookup"><span data-stu-id="95d36-154">You can edit a device category in the Azure Portal, but if you do this, you must manually update any Azure Active Directory Security groups that reference this category.</span></span>

- <span data-ttu-id="95d36-155">Se você excluir uma categoria, todos os dispositivos que foram atribuídos a ela posteriormente exibirão o nome da categoria **Não atribuído**.</span><span class="sxs-lookup"><span data-stu-id="95d36-155">If you delete a category, any devices that were assigned to it will subsequently display the category name **Unassigned**.</span></span>


