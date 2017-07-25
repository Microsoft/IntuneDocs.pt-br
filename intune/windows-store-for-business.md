---
title: Gerenciar aplicativos da Windows Store para Empresas
titleSuffix: Intune on Azure
description: "Saiba como você pode sincronizar aplicativos no Intune da Windows Store para Empresas e, em seguida, atribui-los e acompanhá-los."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: de6ed7623e33a50bdf8452cbf1bad9c648b13d04
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="73bc9-103">Como gerenciar aplicativos adquiridos na Windows Store para Empresas com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="73bc9-103">How to manage apps you purchased from the Windows Store for Business with Microsoft Intune</span></span>
=======
# Como gerenciar aplicativos adquiridos na Windows Store para Empresas com o Microsoft Intune
>>>>>>> live
<a id="how-to-manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


<<<<<<< HEAD
<span data-ttu-id="73bc9-104">O [Windows Store para a Empresa](https://www.microsoft.com/business-store) fornece um local para encontrar e comprar aplicativos para sua organização, individualmente ou em um volume.</span><span class="sxs-lookup"><span data-stu-id="73bc9-104">The [Windows Store for Business](https://www.microsoft.com/business-store) gives you a place to find and purchase apps for your organization, individually, or in volume.</span></span> <span data-ttu-id="73bc9-105">Se conectar a loja ao Microsoft Intune, você pode gerenciar os aplicativos comprados com base no volume no portal do Intune.</span><span class="sxs-lookup"><span data-stu-id="73bc9-105">By connecting the store to Microsoft Intune, you can manage volume-purchased apps from the Intune portal.</span></span> <span data-ttu-id="73bc9-106">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="73bc9-106">For example:</span></span>
* <span data-ttu-id="73bc9-107">Você pode sincronizar a lista de aplicativos que você adquiriu do armazenamento com o Intune.</span><span class="sxs-lookup"><span data-stu-id="73bc9-107">You can synchronize the list of apps you have purchased from the store with Intune.</span></span>
* <span data-ttu-id="73bc9-108">Os aplicativos que são sincronizados aparecem no console de administração do Intune e você pode atribuí-los da mesma forma que outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="73bc9-108">Apps that are synchronized appear in the Intune administration console; you can assign these apps like any other apps.</span></span>
* <span data-ttu-id="73bc9-109">Você pode controlar quantas licenças estão disponíveis e quantas estão sendo usadas no console de administração do Intune.</span><span class="sxs-lookup"><span data-stu-id="73bc9-109">You can track how many licenses are available, and how many are being used in the Intune administration console.</span></span>
* <span data-ttu-id="73bc9-110">O Intune bloqueará a atribuição e a instalação de aplicativos caso haja um número insuficiente de licenças disponíveis.</span><span class="sxs-lookup"><span data-stu-id="73bc9-110">Intune blocks assignment and installation of apps if there are an insufficient number of licenses available.</span></span>

## <span data-ttu-id="73bc9-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="73bc9-111">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>

<span data-ttu-id="73bc9-112">Examine as seguintes informações antes de iniciar a sincronização e a atribuição de aplicativos da Windows Store for Business:</span><span class="sxs-lookup"><span data-stu-id="73bc9-112">Review the following information before you start syncing and assigning apps from the Windows Store for Business:</span></span>

- <span data-ttu-id="73bc9-113">Configure o Intune como a autoridade de gerenciamento de dispositivo móvel para sua organização.</span><span class="sxs-lookup"><span data-stu-id="73bc9-113">Configure Intune as the mobile device management authority for your organization.</span></span>
- <span data-ttu-id="73bc9-114">Você deve se inscrever para uma conta na Windows Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="73bc9-114">You must have signed up for an account on the Windows Store for Business.</span></span>
- <span data-ttu-id="73bc9-115">Depois que você tiver associado uma conta da Windows Business Store ao Intune, não será possível alterar para uma conta diferente no futuro.</span><span class="sxs-lookup"><span data-stu-id="73bc9-115">Once you have associated a Windows Business Store account with Intune, you cannot change to a different account in the future.</span></span>
- <span data-ttu-id="73bc9-116">Aplicativos adquiridos da loja não poderão ser adicionados ao Intune ou excluídos do Intune manualmente.</span><span class="sxs-lookup"><span data-stu-id="73bc9-116">Apps purchased from the store cannot be manually added to or deleted from Intune.</span></span> <span data-ttu-id="73bc9-117">Eles só poderão ser sincronizados com a Windows Store for Business.</span><span class="sxs-lookup"><span data-stu-id="73bc9-117">They can only be synchronized with the Windows Store for Business.</span></span>
- <span data-ttu-id="73bc9-118">O Intune sincroniza tanto aplicativos licenciados online quanto offline que você adquiriu na Windows Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="73bc9-118">Intune synchronizes both online and offline licensed apps you have purchased from the Windows Store for Business.</span></span>
- <span data-ttu-id="73bc9-119">Somente aplicativos offline gratuitos podem ser sincronizados com o Intune.</span><span class="sxs-lookup"><span data-stu-id="73bc9-119">Only offline apps that are free of charge can be synced to Intune.</span></span>
- <span data-ttu-id="73bc9-120">Para usar essa funcionalidade, os dispositivos devem estar ingressados no Active Directory Domain Services ou em um local de trabalho.</span><span class="sxs-lookup"><span data-stu-id="73bc9-120">To use this capability, devices must be joined to Active Directory Domain Services, or workplace-joined.</span></span>
- <span data-ttu-id="73bc9-121">Dispositivos registrados devem estar usando a versão 1511 do Windows 10 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="73bc9-121">Enrolled devices must be using the 1511 release of Windows 10 or later.</span></span>

## <span data-ttu-id="73bc9-122">Associe sua conta da Windows Store for Business ao Intune</span><span class="sxs-lookup"><span data-stu-id="73bc9-122">Associate your Windows Store for Business account with Intune</span></span>
<a id="associate-your-windows-store-for-business-account-with-intune" class="xliff"></a>
<span data-ttu-id="73bc9-123">Antes de habilitar a sincronização no console do Intune, você deve configurar sua conta de repositório para usar o Intune como uma ferramenta de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="73bc9-123">Before you enable synchronization in the Intune console, you must configure your store account to use Intune as a management tool:</span></span>
1. <span data-ttu-id="73bc9-124">Certifique-se de entrar no repositório de negócios usando a mesma conta de locatário usada para entrar no Intune.</span><span class="sxs-lookup"><span data-stu-id="73bc9-124">Ensure that you sign into the Business Store using the same tenant account you use to sign into Intune.</span></span>
2. <span data-ttu-id="73bc9-125">Na Business Store, escolha **Configurações** > **Ferramentas de gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="73bc9-125">In the Business Store, choose **Settings** > **Management tools**.</span></span>
3. <span data-ttu-id="73bc9-126">Na página Ferramentas de gerenciamento, escolha **Adicionar uma ferramenta de gerenciamento** e escolha **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="73bc9-126">On the Management tools page, choose **Add a management tool**, and choose **Microsoft Intune**.</span></span>

> [!NOTE]
> <span data-ttu-id="73bc9-127">Anteriormente, era possível associar apenas uma ferramenta de gerenciamento para atribuir a aplicativos com a Windows Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="73bc9-127">You could previously only associate one management tool to assign apps with the Windows Store for Business.</span></span> <span data-ttu-id="73bc9-128">Agora você pode associar várias ferramentas de gerenciamento com a loja, por exemplo, o Intune e o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="73bc9-128">You can now associate multiple management tools with the store, for example, Intune and Configuration Manager.</span></span>

<span data-ttu-id="73bc9-129">Agora você pode continuar e configurar a sincronização no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="73bc9-129">You can now continue, and set up synchronization in the Intune console.</span></span>

## <span data-ttu-id="73bc9-130">Configurar sincronização</span><span class="sxs-lookup"><span data-stu-id="73bc9-130">Configure synchronization</span></span>
<a id="configure-synchronization" class="xliff"></a>

1. <span data-ttu-id="73bc9-131">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="73bc9-131">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="73bc9-132">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="73bc9-132">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="73bc9-133">Na folha **Intune**, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="73bc9-133">On the **Intune** blade, choose **Mobile apps**.</span></span>
1. <span data-ttu-id="73bc9-134">Na folha **Aplicativos Móveis**, escolha **Instalação** > **Windows Store para Empresas**.</span><span class="sxs-lookup"><span data-stu-id="73bc9-134">On the **Mobile Apps** blade, choose **Setup** > **Windows Store for Business**.</span></span>
2. <span data-ttu-id="73bc9-135">Clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="73bc9-135">Click **Enable**.</span></span>
3. <span data-ttu-id="73bc9-136">Se você ainda não tiver feito isso, clique no link para inscrever-se na Windows Store para Empresas e associe sua conta como indicado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="73bc9-136">If you haven't already done so, click the link to sign up for the Windows Store for Business and associate your account as detailed previously.</span></span>
5. <span data-ttu-id="73bc9-137">Na lista suspensa **Idioma**, escolha o idioma em que os aplicativos da Windows Store para Empresas serão exibidos no Portal do Intune.</span><span class="sxs-lookup"><span data-stu-id="73bc9-137">From the **Language** drop-down list, choose the language in which apps from the Windows Store for Business is displayed in the Intune portal.</span></span> <span data-ttu-id="73bc9-138">Independentemente do idioma em que eles são exibidos, eles serão instalados no idioma do usuário final quando disponível.</span><span class="sxs-lookup"><span data-stu-id="73bc9-138">Regardless of the language in which they are displayed, they are installed in the end user's language when available.</span></span>
6. <span data-ttu-id="73bc9-139">Clique em **Sincronizar** para obter os aplicativos que você adquiriu da Windows Store no Intune.</span><span class="sxs-lookup"><span data-stu-id="73bc9-139">Click **Sync** to get the apps you've purchased from the Windows Store into Intune.</span></span>
=======
O [Windows Store para a Empresa](https://www.microsoft.com/business-store) fornece um local para encontrar e comprar aplicativos para sua organização, individualmente ou em um volume. Se conectar a loja ao Microsoft Intune, você pode gerenciar os aplicativos comprados com base no volume no portal do Intune. Por exemplo:
* Você pode sincronizar a lista de aplicativos que você adquiriu do armazenamento com o Intune.
* Os aplicativos que são sincronizados aparecem no console de administração do Intune e você pode atribuí-los da mesma forma que outros aplicativos.
* Você pode controlar quantas licenças estão disponíveis e quantas estão sendo usadas no console de administração do Intune.
* O Intune bloqueará a atribuição e a instalação de aplicativos caso haja um número insuficiente de licenças disponíveis.

## Antes de começar
<a id="before-you-start" class="xliff"></a>

Examine as seguintes informações antes de iniciar a sincronização e a atribuição de aplicativos da Windows Store for Business:

- Configure o Intune como a autoridade de gerenciamento de dispositivo móvel para sua organização.
- Você deve se inscrever para uma conta na Windows Store para Empresas.
- Depois que você tiver associado uma conta da Windows Business Store ao Intune, não será possível alterar para uma conta diferente no futuro.
- Aplicativos adquiridos da loja não poderão ser adicionados ao Intune ou excluídos do Intune manualmente. Eles só poderão ser sincronizados com a Windows Store for Business.
- O Intune sincroniza tanto aplicativos licenciados online quanto offline que você adquiriu na Windows Store para Empresas.
- Somente aplicativos offline gratuitos podem ser sincronizados com o Intune.
- Para usar essa funcionalidade, os dispositivos devem estar ingressados no Active Directory Domain Services ou em um local de trabalho.
- Dispositivos registrados devem estar usando a versão 1511 do Windows 10 ou posterior.

## Associe sua conta da Windows Store for Business ao Intune
<a id="associate-your-windows-store-for-business-account-with-intune" class="xliff"></a>
Antes de habilitar a sincronização no console do Intune, você deve configurar sua conta de repositório para usar o Intune como uma ferramenta de gerenciamento:
1. Certifique-se de entrar no repositório de negócios usando a mesma conta de locatário usada para entrar no Intune.
2. Na Business Store, escolha **Configurações** > **Ferramentas de gerenciamento**.
3. Na página Ferramentas de gerenciamento, escolha **Adicionar uma ferramenta de gerenciamento** e escolha **Microsoft Intune**.

> [!NOTE]
> Anteriormente, era possível associar apenas uma ferramenta de gerenciamento para atribuir a aplicativos com a Windows Store para Empresas. Agora você pode associar várias ferramentas de gerenciamento com a loja, por exemplo, o Intune e o Configuration Manager.
>>>>>>> live

## <span data-ttu-id="73bc9-140">Sincronizar aplicativos</span><span class="sxs-lookup"><span data-stu-id="73bc9-140">Synchronize apps</span></span>
<a id="synchronize-apps" class="xliff"></a>

<<<<<<< HEAD
1. <span data-ttu-id="73bc9-141">Na carga de trabalho **Aplicativos móveis**, escolha **Instalação** > **Windows Store para Empresas**.</span><span class="sxs-lookup"><span data-stu-id="73bc9-141">In the **Mobile apps** workload, choose **Setup** > **Windows Store for Business**.</span></span>
2. <span data-ttu-id="73bc9-142">Clique em **Sincronizar** para obter os aplicativos que você adquiriu da Windows Store no Intune.</span><span class="sxs-lookup"><span data-stu-id="73bc9-142">Click **Sync** to get the apps you've purchased from the Windows Store into Intune.</span></span>

## <span data-ttu-id="73bc9-143">Atribuir aplicativos</span><span class="sxs-lookup"><span data-stu-id="73bc9-143">Assign apps</span></span>
<a id="assign-apps" class="xliff"></a>

<span data-ttu-id="73bc9-144">Atribua aplicativos da loja da mesma maneira que você atribui qualquer aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="73bc9-144">You assign apps from the store in the same way you assign any other Intune app.</span></span> <span data-ttu-id="73bc9-145">Para obter mais informações, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="73bc9-145">For more information, see [How to assign apps to groups with Microsoft Intune](apps-deploy.md).</span></span> <span data-ttu-id="73bc9-146">No entanto, em vez de atribuir aplicativos da página **Todos os aplicativos**, atribua-os na página **Aplicativos licenciados**.</span><span class="sxs-lookup"><span data-stu-id="73bc9-146">However, instead of assigning apps from the **All Apps** page, you assign them from the **Licensed Apps** page.</span></span>
=======
## Configurar sincronização
<a id="configure-synchronization" class="xliff"></a>

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1. Na folha **Aplicativos Móveis**, escolha **Instalação** > **Windows Store para Empresas**.
2. Clique em **Habilitar**.
3. Se você ainda não tiver feito isso, clique no link para inscrever-se na Windows Store para Empresas e associe sua conta como indicado anteriormente.
5. Na lista suspensa **Idioma**, escolha o idioma em que os aplicativos da Windows Store para Empresas serão exibidos no Portal do Intune. Independentemente do idioma em que eles são exibidos, eles serão instalados no idioma do usuário final quando disponível.
6. Clique em **Sincronizar** para obter os aplicativos que você adquiriu da Windows Store no Intune.

## Sincronizar aplicativos
<a id="synchronize-apps" class="xliff"></a>
>>>>>>> live

<span data-ttu-id="73bc9-147">Aplicativos offline podem ser direcionados para grupos de usuários, grupos de dispositivos ou grupos de usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="73bc9-147">Offline apps can be targeted to user groups, device groups, or groups with users and devices.</span></span>
<span data-ttu-id="73bc9-148">Aplicativos offline podem ser instalados para um usuário específico em um dispositivo ou para todos os usuários de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="73bc9-148">Offline apps can be installed for a specific user on a device or for all users on a device.</span></span> 

<<<<<<< HEAD
=======
## Atribuir aplicativos
<a id="assign-apps" class="xliff"></a>
>>>>>>> live

<span data-ttu-id="73bc9-149">Quando você atribui um aplicativo da Windows Store para Empresas, uma licença é usada por cada usuário que instala o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="73bc9-149">When you assign a Windows Store for Business app, a license is used by each user who installs the app.</span></span> <span data-ttu-id="73bc9-150">Se você usar todas as licenças disponíveis para um aplicativo atribuído, não será possível atribuir mais cópias.</span><span class="sxs-lookup"><span data-stu-id="73bc9-150">If you use all of the available licenses for an assigned app, you cannot assign any more copies.</span></span> <span data-ttu-id="73bc9-151">Efetue uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="73bc9-151">Take one of the following actions:</span></span>
* <span data-ttu-id="73bc9-152">Desinstalar o aplicativo de alguns dispositivos.</span><span class="sxs-lookup"><span data-stu-id="73bc9-152">Uninstall the app from some devices.</span></span>
* <span data-ttu-id="73bc9-153">Reduza o escopo da atribuição atual para ser voltada apenas para os usuários para os quais você tem licenças suficientes.</span><span class="sxs-lookup"><span data-stu-id="73bc9-153">Reduce the scope of the current assignment, targeting only the users you have sufficient licenses for.</span></span>
* <span data-ttu-id="73bc9-154">Comprar mais cópias do aplicativo da Windows Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="73bc9-154">Buy more copies of the app from the Windows Store for Business.</span></span>

<<<<<<< HEAD

=======
Aplicativos offline podem ser direcionados para grupos de usuários, grupos de dispositivos ou grupos de usuários e dispositivos.
Aplicativos offline podem ser instalados para um usuário específico em um dispositivo ou para todos os usuários de um dispositivo. 


Quando você atribui um aplicativo da Windows Store para Empresas, uma licença é usada por cada usuário que instala o aplicativo. Se você usar todas as licenças disponíveis para um aplicativo atribuído, não será possível atribuir mais cópias. Efetue uma das seguintes ações:
* Desinstalar o aplicativo de alguns dispositivos.
* Reduza o escopo da atribuição atual para ser voltada apenas para os usuários para os quais você tem licenças suficientes.
* Comprar mais cópias do aplicativo da Windows Store para Empresas.


>>>>>>> live
