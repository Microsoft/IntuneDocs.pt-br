---
title: Registrar dispositivos Android no Intune
titleSuffix: Intune on Azure
description: Saiba como registrar dispositivos Android no Intune.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 295315dae52662c386055747862717b85ed4b877
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="ade30-103">Registrar dispositivos Android</span><span class="sxs-lookup"><span data-stu-id="ade30-103">Enroll Android devices</span></span>
=======
# Registrar dispositivos Android
>>>>>>> live
<a id="enroll-android-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
<span data-ttu-id="ade30-104">Como administrador do Intune, o Intune permite que você gerencie dispositivos Android, incluindo dispositivos Samsung Knox Standard.</span><span class="sxs-lookup"><span data-stu-id="ade30-104">As an Intune administrator, Intune lets you manage Android devices, including Samsung Knox Standard devices.</span></span> <span data-ttu-id="ade30-105">Você também pode gerenciar o perfil de trabalho em dispositivos [Android for Work](#enable-enrollment-of-android-for-work-devices).</span><span class="sxs-lookup"><span data-stu-id="ade30-105">You can also manage the work profile on devices [Android for Work devices](#enable-enrollment-of-android-for-work-devices).</span></span>

<span data-ttu-id="ade30-106">Há suporte para dispositivos que executam o Samsung KNOX Standard para o gerenciamento de vários usuários pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="ade30-106">Devices that run Samsung KNOX Standard, are supported for multi-user management by Intune.</span></span> <span data-ttu-id="ade30-107">Isso significa que os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure AD, o dispositivo é gerenciado centralmente independentemente de estar ou não em uso.</span><span class="sxs-lookup"><span data-stu-id="ade30-107">This means that end users can sign in and out of the device with their Azure AD credentials, the device is centrally managed whether it’s in use or not.</span></span> <span data-ttu-id="ade30-108">Quando os usuários finais entram, eles têm acesso a aplicativos e, além disso, obtêm todas as políticas aplicadas a eles.</span><span class="sxs-lookup"><span data-stu-id="ade30-108">When end users sign-in, they have access to apps and additionally get any policies applied to them.</span></span> <span data-ttu-id="ade30-109">Quando os usuários saem, todos os dados do aplicativo são removidos.</span><span class="sxs-lookup"><span data-stu-id="ade30-109">When users sign out, all app data is cleared.</span></span>

## <span data-ttu-id="ade30-110">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="ade30-110">Prerequisite</span></span>
<a id="prerequisite" class="xliff"></a>

<span data-ttu-id="ade30-111">Você deve definir a autoridade MDM como **Microsoft Intune** para se preparar para gerenciar dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="ade30-111">You must set the MDM authority to **Microsoft Intune** to prepare to manage mobile devices.</span></span> <span data-ttu-id="ade30-112">Consulte [Definir a autoridade MDM](mdm-authority-set.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="ade30-112">See [Set the MDM authority](mdm-authority-set.md) for instructions.</span></span> <span data-ttu-id="ade30-113">Você define esse item apenas uma vez, na primeira vez que configurar o Intune para gerenciamento de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="ade30-113">You set this item only once, when you are first setting up Intune for mobile device management.</span></span>

## <span data-ttu-id="ade30-114">Configurar registro do Android</span><span class="sxs-lookup"><span data-stu-id="ade30-114">Set up Android enrollment</span></span>
<a id="set-up-android-enrollment" class="xliff"></a>

<span data-ttu-id="ade30-115">Por padrão, o Intune é configurado para permitir o registro de dispositivos Android e Samsung Knox Standard.</span><span class="sxs-lookup"><span data-stu-id="ade30-115">By default, Intune allows enrollment of Android and Samsung Knox Standard devices.</span></span>

<span data-ttu-id="ade30-116">Para bloquear o registro de dispositivos Android ou para bloquear o registro somente de dispositivos Android de propriedade pessoal, consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md).</span><span class="sxs-lookup"><span data-stu-id="ade30-116">To block Android devices, or to block only personally owned Android devices from enrollment, see [Set device type restrictions](enrollment-restrictions-set.md).</span></span>

<span data-ttu-id="ade30-117">Para habilitar o gerenciamento de dispositivos, os usuários devem registrar seus dispositivos baixando o aplicativo do Portal da Empresa do Intune, que está disponível no Google Play e, em seguida, abrindo o aplicativo e seguindo as instruções de registro.</span><span class="sxs-lookup"><span data-stu-id="ade30-117">To enable device management, your users must enroll their devices by downloading the Intune Company Portal app, which is available from Google Play, and then opening the app and following the prompts to enroll.</span></span> <span data-ttu-id="ade30-118">Quando os dispositivos Android são gerenciados, você pode [atribuir políticas de conformidade](compliance-policy-create-android.md), [gerenciar aplicativos](app-management.md)e muito mais.</span><span class="sxs-lookup"><span data-stu-id="ade30-118">Once Android devices are managed, you [assign compliance policies](compliance-policy-create-android.md), [manage apps](app-management.md), and more.</span></span>

## <span data-ttu-id="ade30-119">Habilite o registro de dispositivos Android for Work</span><span class="sxs-lookup"><span data-stu-id="ade30-119">Enable enrollment of Android for Work devices</span></span>
<a id="enable-enrollment-of-android-for-work-devices" class="xliff"></a>

<span data-ttu-id="ade30-120">Para habilitar o gerenciamento do perfil de trabalho em dispositivos que dão [suporte a Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), você deverá adicionar uma associação do Android for Work no Intune.</span><span class="sxs-lookup"><span data-stu-id="ade30-120">To enable management of the work profile on devices that [support Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), you must add an Android for Work binding to Intune.</span></span> <span data-ttu-id="ade30-121">Para registrar dispositivos que dão suporte ao Android for Work registrados anteriormente como dispositivos Android regulares, é necessário cancelar os registros antigos e registrar os dispositivos novamente.</span><span class="sxs-lookup"><span data-stu-id="ade30-121">To enroll devices that support Android for Work but were previously enrolled as regular Android devices, the devices must be unenrolled and then re-enrolled.</span></span>

## <span data-ttu-id="ade30-122">Adicione a Associação do Android for Work para o Intune</span><span class="sxs-lookup"><span data-stu-id="ade30-122">Add Android for Work Binding for Intune</span></span>
<a id="add-android-for-work-binding-for-intune" class="xliff"></a>

1. <span data-ttu-id="ade30-123">**Configurar o MDM do Intune**</span><span class="sxs-lookup"><span data-stu-id="ade30-123">**Set up Intune MDM**</span></span><br>
<span data-ttu-id="ade30-124">Se você ainda não o fez, prepare-se para o gerenciamento de dispositivo móvel ao [configurar a autoridade de gerenciamento do dispositivo móvel](mdm-authority-set.md) como **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="ade30-124">If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](mdm-authority-set.md) as **Microsoft Intune**.</span></span>

2. <span data-ttu-id="ade30-125">**Configurar a associação do Android for Work**</span><span class="sxs-lookup"><span data-stu-id="ade30-125">**Configure Android for Work binding**</span></span><br>
    <span data-ttu-id="ade30-126">Como administrador do Intune, no Portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="ade30-126">As an Intune administrator, in the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

    1. <span data-ttu-id="ade30-127">Na folha do **Intune**, escolha **Registro de dispositivo**, > **Android for Work** e clique em **Configurar** para abrir o site do Android for Work no Google Play.</span><span class="sxs-lookup"><span data-stu-id="ade30-127">On the **Intune** blade, choose **Device enrollment**, > **Android for Work Enrollment**, and click **Configure** to open Google Play's Android for Work website.</span></span> <span data-ttu-id="ade30-128">Uma nova guia será aberta no navegador.</span><span class="sxs-lookup"><span data-stu-id="ade30-128">This will open in a new tab in your browser.</span></span>
  <span data-ttu-id="ade30-129">![Captura de tela mostrando link para configurar a associação do Android for Work](./media/android-work-bind.png)</span><span class="sxs-lookup"><span data-stu-id="ade30-129">![Screenshot showing link to Configure the Android for Work binding](./media/android-work-bind.png)</span></span>

    2. <span data-ttu-id="ade30-130">**Faça logon no Google**</span><span class="sxs-lookup"><span data-stu-id="ade30-130">**Log in to Google**</span></span><br>
   <span data-ttu-id="ade30-131">Na página de entrada do Google, entre com a conta do Google que será associada a todas as tarefas de gerenciamento do Android for Work para o locatário.</span><span class="sxs-lookup"><span data-stu-id="ade30-131">On Google's sign-in page, enter the Google account that will be associated with all Android for Work management tasks for this tenant.</span></span> <span data-ttu-id="ade30-132">Essa é a conta do Google compartilhada entre os administradores de TI da sua organização que costumavam gerenciar e publicar aplicativos no console Play for Work.</span><span class="sxs-lookup"><span data-stu-id="ade30-132">This is the Google account shared among your organization's IT admins that used to manage and publish apps in the Play for Work console.</span></span>

    3. <span data-ttu-id="ade30-133">**Forneça os detalhes da organização**</span><span class="sxs-lookup"><span data-stu-id="ade30-133">**Provide organization details**</span></span><br>
   <span data-ttu-id="ade30-134">Forneça o nome da empresa em **Nome da organização**.</span><span class="sxs-lookup"><span data-stu-id="ade30-134">Provide your company's name for the **Organization name**.</span></span> <span data-ttu-id="ade30-135">O **Microsoft Intune** deverá ser exibido para o *Provedor EMM (Enterprise Mobility Management)*.</span><span class="sxs-lookup"><span data-stu-id="ade30-135">For **Enterprise mobility management (EMM) provider**, *Microsoft Intune* should be displayed.</span></span> <span data-ttu-id="ade30-136">Aceite o acordo do Android for Work e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ade30-136">Agree to the Android for Work agreement, and then click **Confirm**.</span></span> <span data-ttu-id="ade30-137">Sua solicitação será processada.</span><span class="sxs-lookup"><span data-stu-id="ade30-137">Your request will be processed.</span></span>

## <span data-ttu-id="ade30-138">Especifique as Configurações de Registro do Android for Work</span><span class="sxs-lookup"><span data-stu-id="ade30-138">Specify Android for Work Enrollment Settings</span></span>
<a id="specify-android-for-work-enrollment-settings" class="xliff"></a>
   <span data-ttu-id="ade30-139">Há suporte para o Android for Work apenas em determinados dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="ade30-139">Android for Work is only supported on certain Android devices.</span></span> <span data-ttu-id="ade30-140">Consulte os [requisitos do Google para o Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window").</span><span class="sxs-lookup"><span data-stu-id="ade30-140">See Google's [Android for Work requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window").</span></span> <span data-ttu-id="ade30-141">Qualquer dispositivo que dê suporte ao Android for Work também dará suporte ao gerenciamento de Android convencional.</span><span class="sxs-lookup"><span data-stu-id="ade30-141">Any device that supports Android for Work will also support conventional Android management.</span></span>  <span data-ttu-id="ade30-142">O Intune lhe permite especificar como devem ser gerenciados os dispositivos com suporte para o Android for Work:</span><span class="sxs-lookup"><span data-stu-id="ade30-142">Intune lets you specify how devices that support Android for Work should be managed:</span></span>

   - <span data-ttu-id="ade30-143">**Gerencie todos os dispositivos como Android** – Todos os dispositivos Android, incluindo dispositivos com suporte para o Android for Work, serão registrados como dispositivos Android convencionais.</span><span class="sxs-lookup"><span data-stu-id="ade30-143">**Manage all devices as Android** - All Android devices, including devices that support Android for Work, will be enrolled as conventional Android devices.</span></span>
   - <span data-ttu-id="ade30-144">**Gerencie dispositivos com suporte como Android for Work** – Todos os dispositivos com suporte para o Android for Work serão registrados como dispositivos Android for Work.</span><span class="sxs-lookup"><span data-stu-id="ade30-144">**Manage supported devices as Android for Work** - All devices that support Android for Work are enrolled as Android for Work devices.</span></span> <span data-ttu-id="ade30-145">Os dispositivos Android que não dão suporte ao Android for Work são registrados como dispositivos Android convencionais.</span><span class="sxs-lookup"><span data-stu-id="ade30-145">Any Android device that does not support Android for Work is enrolled as a conventional Android device.</span></span>
   - <span data-ttu-id="ade30-146">**Gerencie dispositivos com suporte para usuários somente nos grupos de usuários como Android for Work** – Permite direcionar o gerenciamento do Android for Work para um conjunto limitado de usuários.</span><span class="sxs-lookup"><span data-stu-id="ade30-146">**Manage supported devices for users only in these user groups as Android for Work** - Lets you target Android for Work management to a limited set of users.</span></span> <span data-ttu-id="ade30-147">Somente os membros dos grupos selecionados que registram um dispositivo que dá suporte ao Android for Work são registrados como dispositivos Android for Work.</span><span class="sxs-lookup"><span data-stu-id="ade30-147">Only members of the selected groups who enroll a device that supports Android for Work are enrolled as Android for Work devices.</span></span> <span data-ttu-id="ade30-148">Todos os outros são registrados como dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="ade30-148">All others are enrolled as Android devices.</span></span> <span data-ttu-id="ade30-149">Isso é útil durante os pilotos do Android for Work.</span><span class="sxs-lookup"><span data-stu-id="ade30-149">This is useful during Android for Work pilots.</span></span>
=======
Como administrador do Intune, o Intune permite que você gerencie dispositivos Android, incluindo dispositivos Samsung Knox Standard. Você também pode gerenciar o perfil de trabalho em dispositivos [Android for Work](#enable-enrollment-of-android-for-work-devices).

Há suporte para dispositivos que executam o Samsung KNOX Standard para o gerenciamento de vários usuários pelo Intune. Isso significa que os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure AD, o dispositivo é gerenciado centralmente independentemente de estar ou não em uso. Quando os usuários finais entram, eles têm acesso a aplicativos e, além disso, obtêm todas as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.

## Pré-requisito
<a id="prerequisite" class="xliff"></a>

Você deve definir a autoridade MDM como **Microsoft Intune** para se preparar para gerenciar dispositivos móveis. Consulte [Definir a autoridade MDM](mdm-authority-set.md) para obter instruções. Você define esse item apenas uma vez, na primeira vez que configurar o Intune para gerenciamento de dispositivo móvel.

## Configurar registro do Android
<a id="set-up-android-enrollment" class="xliff"></a>

Por padrão, o Intune é configurado para permitir o registro de dispositivos Android e Samsung Knox Standard.

Para bloquear o registro de dispositivos Android ou para bloquear o registro somente de dispositivos Android de propriedade pessoal, consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md).

Para habilitar o gerenciamento de dispositivos, os usuários devem registrar seus dispositivos baixando o aplicativo do Portal da Empresa do Intune, que está disponível no Google Play e, em seguida, abrindo o aplicativo e seguindo as instruções de registro. Quando os dispositivos Android são gerenciados, você pode [atribuir políticas de conformidade](compliance-policy-create-android.md), [gerenciar aplicativos](app-management.md)e muito mais.

## Habilite o registro de dispositivos Android for Work
<a id="enable-enrollment-of-android-for-work-devices" class="xliff"></a>

Para habilitar o gerenciamento do perfil de trabalho em dispositivos que dão [suporte a Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), você deverá adicionar uma associação do Android for Work no Intune. Para registrar dispositivos que dão suporte ao Android for Work registrados anteriormente como dispositivos Android regulares, é necessário cancelar os registros antigos e registrar os dispositivos novamente.

## Adicione a Associação do Android for Work para o Intune
<a id="add-android-for-work-binding-for-intune" class="xliff"></a>

1. **Configurar o MDM do Intune**<br>
Se você ainda não o fez, prepare-se para o gerenciamento de dispositivo móvel ao [configurar a autoridade de gerenciamento do dispositivo móvel](mdm-authority-set.md) como **Microsoft Intune**.

2. **Configurar a associação do Android for Work**<br>
    Como administrador do Intune, no Portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

    1. Na folha do **Intune**, escolha **Registro de dispositivo**, > **Android for Work** e clique em **Configurar** para abrir o site do Android for Work no Google Play. Uma nova guia será aberta no navegador.
  ![Captura de tela mostrando link para configurar a associação do Android for Work](./media/android-work-bind.png)

    2. **Faça logon no Google**<br>
   Na página de entrada do Google, entre com a conta do Google que será associada a todas as tarefas de gerenciamento do Android for Work para o locatário. Essa é a conta do Google compartilhada entre os administradores de TI da sua organização que costumavam gerenciar e publicar aplicativos no console Play for Work.

    3. **Forneça os detalhes da organização**<br>
   Forneça o nome da empresa em **Nome da organização**. O **Microsoft Intune** deverá ser exibido para o *Provedor EMM (Enterprise Mobility Management)*. Aceite o acordo do Android for Work e clique em **Confirmar**. Sua solicitação será processada.

## Especifique as Configurações de Registro do Android for Work
<a id="specify-android-for-work-enrollment-settings" class="xliff"></a>
   Há suporte para o Android for Work apenas em determinados dispositivos Android. Consulte os [requisitos do Google para o Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window"). Qualquer dispositivo que dê suporte ao Android for Work também dará suporte ao gerenciamento de Android convencional.  O Intune lhe permite especificar como devem ser gerenciados os dispositivos com suporte para o Android for Work:

   - **Gerencie todos os dispositivos como Android** – Todos os dispositivos Android, incluindo dispositivos com suporte para o Android for Work, serão registrados como dispositivos Android convencionais.
   - **Gerencie dispositivos com suporte como Android for Work** – Todos os dispositivos com suporte para o Android for Work serão registrados como dispositivos Android for Work. Os dispositivos Android que não dão suporte ao Android for Work são registrados como dispositivos Android convencionais.
   - **Gerencie dispositivos com suporte para usuários somente nos grupos de usuários como Android for Work** – Permite direcionar o gerenciamento do Android for Work para um conjunto limitado de usuários. Somente os membros dos grupos selecionados que registram um dispositivo que dá suporte ao Android for Work são registrados como dispositivos Android for Work. Todos os outros são registrados como dispositivos Android. Isso é útil durante os pilotos do Android for Work.
>>>>>>> live

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

<<<<<<< HEAD
## <span data-ttu-id="ade30-150">Informe aos usuários como registrar seus dispositivos para acessar os recursos da empresa</span><span class="sxs-lookup"><span data-stu-id="ade30-150">Tell your users how to enroll their devices to access company resources</span></span>
<a id="tell-your-users-how-to-enroll-their-devices-to-access-company-resources" class="xliff"></a>

<span data-ttu-id="ade30-151">Você precisará pedir aos usuários finais que entrem no Google Play para baixar o aplicativo Portal da Empresa do Intune e, em seguida, abram o aplicativo e sigam os prompts para registrar seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ade30-151">You'll need to tell your end users to go to Google Play to download the Intune Company Portal app, and then open the app and follow the prompts to enroll their device.</span></span> <span data-ttu-id="ade30-152">O aplicativo orienta os usuários pelo processo de registro, explicando o que os usuários podem esperar e o que os administradores de TI podem e não podem ver em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ade30-152">The app guides users through the enrollment process, explaining what users can expect and what IT administrators can and can't see on their devices.</span></span>

<span data-ttu-id="ade30-153">Você também pode enviar a eles um link com as etapas do registro online: [Registrar seu dispositivo Android no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).</span><span class="sxs-lookup"><span data-stu-id="ade30-153">You can also send them a link to online enrollment steps: [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).</span></span>

<span data-ttu-id="ade30-154">Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:</span><span class="sxs-lookup"><span data-stu-id="ade30-154">For information about other end-user tasks, see these articles:</span></span>

- [<span data-ttu-id="ade30-155">Recursos sobre a experiência do usuário final com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ade30-155">Resources about the end-user experience with Microsoft Intune</span></span>](end-user-educate.md)
- [<span data-ttu-id="ade30-156">Usando seu dispositivo Android com o Intune</span><span class="sxs-lookup"><span data-stu-id="ade30-156">Using your Android device with Intune</span></span>](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <span data-ttu-id="ade30-157">Desassociando sua conta administrativa do Android for Work</span><span class="sxs-lookup"><span data-stu-id="ade30-157">Unbinding your Android for Work administrative account</span></span>
<a id="unbinding-your-android-for-work-administrative-account" class="xliff"></a>

<span data-ttu-id="ade30-158">É possível desligar o registro e o gerenciamento do Android for Work.</span><span class="sxs-lookup"><span data-stu-id="ade30-158">You can turn off Android for Work enrollment and management.</span></span> <span data-ttu-id="ade30-159">Ao clicar em **Desassociar** no console de administração do Intune, todos os dispositivos Android para Trabalho registrados são removidos, bem como a relação entre a conta do Android para Trabalho e o Intune.</span><span class="sxs-lookup"><span data-stu-id="ade30-159">Clicking **Unbind** in the Intune administration console removes all enrolled Android for Work devices from enrollment and removes the relationship between the Android for Work account and Intune.</span></span>

### <span data-ttu-id="ade30-160">Como desassociar uma conta do Android for Work</span><span class="sxs-lookup"><span data-stu-id="ade30-160">How to unbind an Android for Work account</span></span>
<a id="how-to-unbind-an-android-for-work-account" class="xliff"></a>

1. <span data-ttu-id="ade30-161">**Desassociar a associação do Android for Work**</span><span class="sxs-lookup"><span data-stu-id="ade30-161">**Unbind Android for Work binding**</span></span><br>
    <span data-ttu-id="ade30-162">Como administrador do Intune, no Portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="ade30-162">AAs an Intune administrator, in the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>  <span data-ttu-id="ade30-163">Na folha **Intune**, escolha **Registro de dispositivo**, > **Registro do Android for Work** e clique em **Desassociar**.</span><span class="sxs-lookup"><span data-stu-id="ade30-163">On the **Intune** blade, choose **Device enrollment**, > **Android for Work Enrollment**, and click **Unbind**.</span></span>

2. <span data-ttu-id="ade30-164">**Aceite a exclusão da associação do Android for Work**</span><span class="sxs-lookup"><span data-stu-id="ade30-164">**Agree to delete Android for Work binding**</span></span><br>
  <span data-ttu-id="ade30-165">Clique em **Sim** para excluir a associação e cancelar o registro de todos os dispositivos Android for Work do Intune.</span><span class="sxs-lookup"><span data-stu-id="ade30-165">Click **Yes** to delete the binding and unenroll all Android for Work devices from Intune.</span></span>
=======
## Informe aos usuários como registrar seus dispositivos para acessar os recursos da empresa
<a id="tell-your-users-how-to-enroll-their-devices-to-access-company-resources" class="xliff"></a>

Você precisará pedir aos usuários finais que entrem no Google Play para baixar o aplicativo Portal da Empresa do Intune e, em seguida, abram o aplicativo e sigam os prompts para registrar seus dispositivos. O aplicativo orienta os usuários pelo processo de registro, explicando o que os usuários podem esperar e o que os administradores de TI podem e não podem ver em seus dispositivos.

Você também pode enviar a eles um link com as etapas do registro online: [Registrar seu dispositivo Android no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:

- [Recursos sobre a experiência do usuário final com o Microsoft Intune](end-user-educate.md)
- [Usando seu dispositivo Android com o Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## Desassociando sua conta administrativa do Android for Work
<a id="unbinding-your-android-for-work-administrative-account" class="xliff"></a>

É possível desligar o registro e o gerenciamento do Android for Work. Ao clicar em **Desassociar** no console de administração do Intune, todos os dispositivos Android para Trabalho registrados são removidos, bem como a relação entre a conta do Android para Trabalho e o Intune.

### Como desassociar uma conta do Android for Work
<a id="how-to-unbind-an-android-for-work-account" class="xliff"></a>

1. **Desassociar a associação do Android for Work**<br>
    Como administrador do Intune, no Portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.  Na folha **Intune**, escolha **Registro de dispositivo**, > **Registro do Android for Work** e clique em **Desassociar**.

2. **Aceite a exclusão da associação do Android for Work**<br>
  Clique em **Sim** para excluir a associação e cancelar o registro de todos os dispositivos Android for Work do Intune.
>>>>>>> live
