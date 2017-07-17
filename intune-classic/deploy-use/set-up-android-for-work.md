---
title: Configurar o Android for Work
description: "Habilite o MDM (gerenciamento de dispositivo móvel) para dispositivos Android for Work com o Microsoft Intune."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
ms.custom: intune-classic
ms.openlocfilehash: 852997044cef22901e8133d76f327e98b2a1ee72
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="ece6b-103">Habilite o registro de dispositivos Android for Work</span><span class="sxs-lookup"><span data-stu-id="ece6b-103">Enable enrollment of Android for Work devices</span></span>
<a id="enable-enrollment-of-android-for-work-devices" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ece6b-104">Para habilitar o gerenciamento de dispositivos Android for Work, você deve adicionar uma associação do Android for Work no Intune.</span><span class="sxs-lookup"><span data-stu-id="ece6b-104">To enable management of Android for Work devices, you must add an Android for Work binding to Intune.</span></span> <span data-ttu-id="ece6b-105">Para registrar dispositivos que dão suporte ao Android for Work registrados anteriormente como dispositivos Android regulares, é necessário cancelar os registros antigos e registrar os dispositivos novamente.</span><span class="sxs-lookup"><span data-stu-id="ece6b-105">To enroll devices that support Android for Work but were previously enrolled as regular Android devices, the devices must be unenrolled and then re-enrolled.</span></span>

## <span data-ttu-id="ece6b-106">Adicione a Associação do Android for Work para o Intune</span><span class="sxs-lookup"><span data-stu-id="ece6b-106">Add Android for Work Binding for Intune</span></span>
<a id="add-android-for-work-binding-for-intune" class="xliff"></a>

1. <span data-ttu-id="ece6b-107">**Configurar Intune**</span><span class="sxs-lookup"><span data-stu-id="ece6b-107">**Set up Intune**</span></span><br>
<span data-ttu-id="ece6b-108">Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de gerenciamento do dispositivo móvel](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-8#enable-device-enrollment) como **Microsoft Intune** e configure o MDM.</span><span class="sxs-lookup"><span data-stu-id="ece6b-108">If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-8#enable-device-enrollment) as **Microsoft Intune** and setting up MDM.</span></span>

2. <span data-ttu-id="ece6b-109">**Configurar a associação do Android for Work**</span><span class="sxs-lookup"><span data-stu-id="ece6b-109">**Configure Android for Work binding**</span></span><br>
    <span data-ttu-id="ece6b-110">Como administrador do Intune, abra o [Console de Administração do Microsoft Intune](https://manage.microsoft.com), acesse **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Android for Work** e clique em **Configurar** para abrir o site do Android for Work no Google Play.</span><span class="sxs-lookup"><span data-stu-id="ece6b-110">As an Intune administrator, open the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **Android for Work**, and click **Configure** to open Google Play's Android for Work website.</span></span> <span data-ttu-id="ece6b-111">Uma nova guia será aberta no navegador.</span><span class="sxs-lookup"><span data-stu-id="ece6b-111">This will open in a new tab in your browser.</span></span>

3. <span data-ttu-id="ece6b-112">**Faça logon no Google**</span><span class="sxs-lookup"><span data-stu-id="ece6b-112">**Log in to Google**</span></span><br>
   <span data-ttu-id="ece6b-113">Na página de entrada do Google, entre com a conta do Google que será associada a todas as tarefas de gerenciamento do Android for Work para o locatário.</span><span class="sxs-lookup"><span data-stu-id="ece6b-113">On Google's sign-in page, enter the Google account that will be associated with all Android for Work management tasks for this tenant.</span></span> <span data-ttu-id="ece6b-114">Essa é a conta do Google compartilhada entre os administradores de TI da sua organização que costumavam gerenciar e publicar aplicativos no console Play for Work.</span><span class="sxs-lookup"><span data-stu-id="ece6b-114">This is the Google account shared among your organization's IT admins that used to manage and publish apps in the Play for Work console.</span></span>

4. <span data-ttu-id="ece6b-115">**Forneça os detalhes da organização**</span><span class="sxs-lookup"><span data-stu-id="ece6b-115">**Provide organization details**</span></span><br>
   <span data-ttu-id="ece6b-116">Forneça o nome da empresa em **Nome da organização**.</span><span class="sxs-lookup"><span data-stu-id="ece6b-116">Provide your company's name for the **Organization name**.</span></span> <span data-ttu-id="ece6b-117">O **Microsoft Intune** deverá ser exibido para o *Provedor EMM (Enterprise Mobility Management)*.</span><span class="sxs-lookup"><span data-stu-id="ece6b-117">For **Enterprise mobility management (EMM) provider**, *Microsoft Intune* should be displayed.</span></span> <span data-ttu-id="ece6b-118">Aceite o acordo do Android for Work e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ece6b-118">Agree to the Android for Work agreement, and then click **Confirm**.</span></span> <span data-ttu-id="ece6b-119">Sua solicitação será processada.</span><span class="sxs-lookup"><span data-stu-id="ece6b-119">Your request will be processed.</span></span>

## <span data-ttu-id="ece6b-120">Especifique as Configurações de Registro do Android for Work</span><span class="sxs-lookup"><span data-stu-id="ece6b-120">Specify Android for Work Enrollment Settings</span></span>
<a id="specify-android-for-work-enrollment-settings" class="xliff"></a>
   <span data-ttu-id="ece6b-121">Há suporte para o Android for Work apenas em determinados dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="ece6b-121">Android for Work is only supported on certain Android devices.</span></span> <span data-ttu-id="ece6b-122">Consulte os [requisitos do Google para o Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window").</span><span class="sxs-lookup"><span data-stu-id="ece6b-122">See Google's [Android for Work requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window").</span></span>  <span data-ttu-id="ece6b-123">Qualquer dispositivo que dê suporte ao Android for Work também dará suporte ao gerenciamento de Android convencional.</span><span class="sxs-lookup"><span data-stu-id="ece6b-123">Any device that supports Android for Work will also support conventional Android management.</span></span>  <span data-ttu-id="ece6b-124">O Intune lhe permite especificar como devem ser gerenciados os dispositivos com suporte para o Android for Work:</span><span class="sxs-lookup"><span data-stu-id="ece6b-124">Intune lets you specify how devices that support Android for Work should be managed:</span></span>

   - <span data-ttu-id="ece6b-125">**Gerencie todos os dispositivos como Android** – Todos os dispositivos Android, incluindo dispositivos com suporte para o Android for Work, serão registrados como dispositivos Android convencionais.</span><span class="sxs-lookup"><span data-stu-id="ece6b-125">**Manage all devices as Android** - All Android devices, including devices that support Android for Work, will be enrolled as conventional Android devices.</span></span>
   - <span data-ttu-id="ece6b-126">**Gerencie dispositivos com suporte como Android for Work** – Todos os dispositivos com suporte para o Android for Work serão registrados como dispositivos Android for Work.</span><span class="sxs-lookup"><span data-stu-id="ece6b-126">**Manage supported devices as Android for Work** - All devices that support Android for Work are enrolled as Android for Work devices.</span></span> <span data-ttu-id="ece6b-127">Os dispositivos Android que não dão suporte ao Android for Work são registrados como dispositivos Android convencionais.</span><span class="sxs-lookup"><span data-stu-id="ece6b-127">Any Android device that does not support Android for Work is enrolled as a conventional Android device.</span></span>
   - <span data-ttu-id="ece6b-128">**Gerencie dispositivos com suporte para usuários somente nos grupos de usuários como Android for Work** – Permite direcionar o gerenciamento do Android for Work para um conjunto limitado de usuários.</span><span class="sxs-lookup"><span data-stu-id="ece6b-128">**Manage supported devices for users only in these user groups as Android for Work** - Lets you target Android for Work management to a limited set of users.</span></span> <span data-ttu-id="ece6b-129">Somente os membros dos grupos selecionados que registram um dispositivo que dá suporte ao Android for Work são registrados como dispositivos Android for Work.</span><span class="sxs-lookup"><span data-stu-id="ece6b-129">Only members of the selected groups who enroll a device that supports Android for Work are enrolled as Android for Work devices.</span></span> <span data-ttu-id="ece6b-130">Todos os outros são registrados como dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="ece6b-130">All others are enrolled as Android devices.</span></span> <span data-ttu-id="ece6b-131">Isso é útil durante os pilotos do Android for Work.</span><span class="sxs-lookup"><span data-stu-id="ece6b-131">This is useful during Android for Work pilots.</span></span>

## <span data-ttu-id="ece6b-132">Próximas etapas para o Android for Work</span><span class="sxs-lookup"><span data-stu-id="ece6b-132">Next steps for Android for Work</span></span>
<a id="next-steps-for-android-for-work" class="xliff"></a>
<span data-ttu-id="ece6b-133">Após a configuração da associação e das preferências do Android for Work, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ece6b-133">After configuring the Android for Work binding and settings, you can do the following:</span></span>
- [<span data-ttu-id="ece6b-134">Implante os aplicativos Android for Work</span><span class="sxs-lookup"><span data-stu-id="ece6b-134">Deploy Android for Work apps</span></span>](android-for-work-apps.md)
- [<span data-ttu-id="ece6b-135">Adicione as políticas de configuração do Android for Work</span><span class="sxs-lookup"><span data-stu-id="ece6b-135">Add Android for Work configuration policies</span></span>](android-for-work-policy-settings-in-microsoft-intune.md)

## <span data-ttu-id="ece6b-136">Desassociando sua conta administrativa do Android for Work</span><span class="sxs-lookup"><span data-stu-id="ece6b-136">Unbinding your Android for Work administrative account</span></span>
<a id="unbinding-your-android-for-work-administrative-account" class="xliff"></a>

<span data-ttu-id="ece6b-137">É possível desligar o registro e o gerenciamento do Android for Work.</span><span class="sxs-lookup"><span data-stu-id="ece6b-137">You can turn off Android for Work enrollment and management.</span></span> <span data-ttu-id="ece6b-138">Ao clicar em **Desassociar** no console de administração do Intune, todos os dispositivos Android para Trabalho registrados são removidos, bem como a relação entre a conta do Android para Trabalho e o Intune.</span><span class="sxs-lookup"><span data-stu-id="ece6b-138">Clicking **Unbind** in the Intune administration console removes all enrolled Android for Work devices from enrollment and removes the relationship between the Android for Work account and Intune.</span></span>

### <span data-ttu-id="ece6b-139">Como desassociar uma conta do Android for Work</span><span class="sxs-lookup"><span data-stu-id="ece6b-139">How to unbind an Android for Work account</span></span>
<a id="how-to-unbind-an-android-for-work-account" class="xliff"></a>

1. <span data-ttu-id="ece6b-140">**Desassociar a associação do Android for Work**</span><span class="sxs-lookup"><span data-stu-id="ece6b-140">**Unbind Android for Work binding**</span></span><br>
    <span data-ttu-id="ece6b-141">Como usuário administrativo, abra o [console de administração do Microsoft Intune](https://manage.microsoft.com), vá para **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Android for Work** e clique em **Desassociar**.</span><span class="sxs-lookup"><span data-stu-id="ece6b-141">As an administrative user, open the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **Android for Work**, and click **Unbind**.</span></span>

2. <span data-ttu-id="ece6b-142">**Aceite a exclusão da associação do Android for Work**</span><span class="sxs-lookup"><span data-stu-id="ece6b-142">**Agree to delete Android for Work binding**</span></span><br>
  <span data-ttu-id="ece6b-143">Clique em **Sim** para excluir a associação e cancelar o registro de todos os dispositivos Android for Work do Intune.</span><span class="sxs-lookup"><span data-stu-id="ece6b-143">Click **Yes** to delete the binding and unenroll all Android for Work devices from Intune.</span></span>
