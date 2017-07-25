---
title: "Gerenciar a transferência de dados entre aplicativos iOS"
titleSuffix: Intune on Azure
description: "Use este tópico para entender como você pode usar o recurso “Open-in” do iOS e as políticas de gerenciamento de aplicativo móvel para gerenciar transferências de dados entre aplicativos."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e3c588d2237f48501d78af364760acf1ef290639
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="75b8e-103">Como gerenciar a transferência de dados entre aplicativos iOS</span><span class="sxs-lookup"><span data-stu-id="75b8e-103">How to manage data transfer between iOS apps</span></span>
<a id="how-to-manage-data-transfer-between-ios-apps" class="xliff"></a>
## <span data-ttu-id="75b8e-104">Gerenciar aplicativos iOS</span><span class="sxs-lookup"><span data-stu-id="75b8e-104">Manage iOS apps</span></span>
<a id="manage-ios-apps" class="xliff"></a>
<span data-ttu-id="75b8e-105">Proteger os dados da sua empresa inclui garantir que as transferências de arquivos sejam restritas a aplicativos gerenciados por você.</span><span class="sxs-lookup"><span data-stu-id="75b8e-105">Protecting your company data includes making sure that file transfers are restricted to apps that are managed by you.</span></span>  <span data-ttu-id="75b8e-106">Você pode gerenciar aplicativos iOS das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="75b8e-106">You can manage iOS apps in the following ways:</span></span>

-   <span data-ttu-id="75b8e-107">Evite a perda de dados da empresa configurando uma política de proteção de aplicativo, que chamaremos de aplicativos **gerenciados por política** aplicativos.</span><span class="sxs-lookup"><span data-stu-id="75b8e-107">Prevent company data loss  by configuring an app protection policy for the apps, which we will refer to as **policy-managed**  apps.</span></span> <span data-ttu-id="75b8e-108">Consulte [todos os aplicativos orientados pelo Intune que você pode gerenciar com a política de proteção de aplicativo](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)</span><span class="sxs-lookup"><span data-stu-id="75b8e-108">See [all the Intune-enlightened apps you can manage with app protection policy](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)</span></span>

-   <span data-ttu-id="75b8e-109">Você também pode implantar e gerenciar aplicativos pelo **canal MDM**.</span><span class="sxs-lookup"><span data-stu-id="75b8e-109">You can also deploy and manage apps through the **MDM channel**.</span></span>  <span data-ttu-id="75b8e-110">Isso requer que os dispositivos sejam registrados na solução MDM.</span><span class="sxs-lookup"><span data-stu-id="75b8e-110">This requires that the devices are enrolled in the MDM solution.</span></span> <span data-ttu-id="75b8e-111">Eles podem ser aplicativos **gerenciados por política** ou outros aplicativos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="75b8e-111">These can be **policy-managed**  apps or other managed  apps.</span></span>

<span data-ttu-id="75b8e-112">O recurso **Abrir em gerenciamento** para dispositivos iOS pode limitar as transferências de arquivo entre os aplicativos que são implantados por meio do canal **MDM**.</span><span class="sxs-lookup"><span data-stu-id="75b8e-112">The **Open in management** feature for iOS devices can limit file transfers between apps that are deployed through the **MDM channel**.</span></span> <span data-ttu-id="75b8e-113">As restrições de Abrir em gerenciamento são definidas nas definições de configuração e implantadas usando o software de MDM.</span><span class="sxs-lookup"><span data-stu-id="75b8e-113">Open in management restrictions are set in configuration settings and deployed using your MDM solution.</span></span>  <span data-ttu-id="75b8e-114">Quando o usuário instala o aplicativo implantado, são aplicadas restrições definidas por você.</span><span class="sxs-lookup"><span data-stu-id="75b8e-114">When the user installs the deployed app, the restrictions you set are applied.</span></span>
##  <span data-ttu-id="75b8e-115">Usando a proteção do aplicativo com aplicativos iOS</span><span class="sxs-lookup"><span data-stu-id="75b8e-115">Using app protection with iOS apps</span></span>
<a id="using-app-protection-with-ios-apps" class="xliff"></a>
<span data-ttu-id="75b8e-116">Políticas de proteção de aplicativo podem ser usadas com o recurso iOS **Abrir no gerenciamento** para proteger os dados da empresa das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="75b8e-116">App protection policies can be used with the iOS **Open in management** feature to protect company data in the following ways:</span></span>

-   <span data-ttu-id="75b8e-117">**Dispositivos do funcionário não gerenciados por nenhuma solução de MDM:** defina as configurações de política de proteção de aplicativo como **Permitir que o aplicativo transfira dados somente para aplicativos Gerenciados por Política**.</span><span class="sxs-lookup"><span data-stu-id="75b8e-117">**Employee owned devices not managed by any MDM solution:** You can set the app protection policy settings to **Allow app to transfer data to only Policy Managed apps**.</span></span> <span data-ttu-id="75b8e-118">O comportamento do “Open-in” em um aplicativo Gerenciado por Política somente apresentará outros aplicativos Gerenciados por Política como uma opção de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="75b8e-118">The Open-In behavior in a Policy Managed app will only present other Policy Managed apps as an option for sharing.</span></span> <span data-ttu-id="75b8e-119">Se um usuário tentar enviar um arquivo protegido por política como um anexo no OneDrive no email nativo, esse arquivo ficará ilegível.</span><span class="sxs-lookup"><span data-stu-id="75b8e-119">If a user tries to send a policy protected file as an attachment from OneDrive in the native mail, that file will be unreadable.</span></span>

-   <span data-ttu-id="75b8e-120">**Dispositivos gerenciados pelo Intune:** para dispositivos registrados no Intune, transferência de dados entre aplicativos com as políticas de proteção de aplicativo e outros aplicativos do iOS gerenciado implantados por meio do Intune é permitida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="75b8e-120">**Devices managed by Intune:** For devices enrolled in Intune, data transfer between apps with app protection policies and other managed iOS apps deployed through Intune is allowed  automatically.</span></span> <span data-ttu-id="75b8e-121">Para permitir a transferência de dados entre aplicativos com as políticas de proteção de aplicativo, habilite a configuração **Permitir que o aplicativo transfira dados somente para aplicativos gerenciados**.</span><span class="sxs-lookup"><span data-stu-id="75b8e-121">To allow data transfer between apps with app protection policies, enable the **Allow app to transfer data to only managed apps** setting.</span></span> <span data-ttu-id="75b8e-122">Você pode usar o recurso **Aberto em gerenciamento** para controlar a transferência de dados entre aplicativos que são implantados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="75b8e-122">You can use the **Open in management** feature to control data transfer between apps that are deployed through Intune.</span></span>   

-   <span data-ttu-id="75b8e-123">**Dispositivos gerenciados por uma solução MDM de terceiro:** você pode restringir a transferência de dados somente para aplicativos gerenciados usando o recurso **Aberto em gerenciamento** do iOS.</span><span class="sxs-lookup"><span data-stu-id="75b8e-123">**Devices managed by a third party MDM solution:** You can restrict data transfer to only managed apps by using the iOS **Open in management** feature.</span></span>
<span data-ttu-id="75b8e-124">Para verificar se os aplicativos implantados usando a solução de MDM de terceiros também estão associados às políticas de proteção de aplicativo configuradas no Intune, você deverá definir a configuração de UPN do usuário conforme descrito no passo a passo [Definir configuração de UPN do usuário](#configure-user-upn-setting-for-third-party-emm).</span><span class="sxs-lookup"><span data-stu-id="75b8e-124">To make sure that apps that you deploy using your third party MDM solution are also associated with the app protection policies you have configured in Intune, you must configure the user UPN setting as described in the [Configure user UPN setting](#configure-user-upn-setting-for-third-party-emm) walkthrough.</span></span>  <span data-ttu-id="75b8e-125">Quando os aplicativos são implantados com a configuração de UPN do usuário, as políticas de proteção de aplicativo serão aplicadas ao aplicativo quando o usuário final entrar usando sua conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="75b8e-125">When apps are deployed with the user UPN setting, the app protection policies are applied to the app when the end user signs-in using their work account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75b8e-126">A configuração de UPN do usuário só será necessária para aplicativos implantados para dispositivos gerenciados por um MDM de terceiro.</span><span class="sxs-lookup"><span data-stu-id="75b8e-126">The user UPN setting is only required for apps deployed to devices managed by a third-party MDM.</span></span>  <span data-ttu-id="75b8e-127">Para dispositivos gerenciados pelo Intune, essa configuração não é necessária.</span><span class="sxs-lookup"><span data-stu-id="75b8e-127">For Intune-managed devices, this setting is not required.</span></span>


## <span data-ttu-id="75b8e-128">Definir configuração de UPN do usuário para EMM de terceiros</span><span class="sxs-lookup"><span data-stu-id="75b8e-128">Configure user UPN setting for third-party EMM</span></span>
<a id="configure-user-upn-setting-for-third-party-emm" class="xliff"></a>
<span data-ttu-id="75b8e-129">Essa configuração de UPN do usuário é **necessária** para dispositivos gerenciados por uma solução EMM de terceiros.</span><span class="sxs-lookup"><span data-stu-id="75b8e-129">Configuring the user UPN setting is **required** for devices that are managed by a third-party EMM solution.</span></span> <span data-ttu-id="75b8e-130">O procedimento descrito abaixo é um fluxo geral de como definir a configuração de UPN e a experiência resultante do usuário final:</span><span class="sxs-lookup"><span data-stu-id="75b8e-130">The procedure described below is a general flow on how to configure the UPN setting and the resulting end user experience:</span></span>


1.  <span data-ttu-id="75b8e-131">No [portal do Azure](https://portal.azure.com), [crie e atribua uma política de proteção de aplicativo](app-protection-policies.md) para iOS.</span><span class="sxs-lookup"><span data-stu-id="75b8e-131">In the [Azure portal](https://portal.azure.com), [create and assign an app protection policy](app-protection-policies.md) for iOS.</span></span> <span data-ttu-id="75b8e-132">Defina as configurações da política conforme os requisitos da sua empresa e selecione os aplicativos de iOS que devem ter essa política.</span><span class="sxs-lookup"><span data-stu-id="75b8e-132">Configure policy settings per your company requirements and select the iOS apps that should have this policy.</span></span>

2.  <span data-ttu-id="75b8e-133">Implante os aplicativos e o perfil de email que você deseja gerenciar **por meio da solução MDM de terceiros** usando as etapas gerais abaixo.</span><span class="sxs-lookup"><span data-stu-id="75b8e-133">Deploy the apps and the email profile that you want managed **through your third-party MDM solution** using the generalized steps below.</span></span> <span data-ttu-id="75b8e-134">Essa experiência também é abordada no Exemplo 1.</span><span class="sxs-lookup"><span data-stu-id="75b8e-134">This experience is also covered by Example 1.</span></span>

  1.  <span data-ttu-id="75b8e-135">Implante o aplicativo com as seguintes configurações do aplicativo:</span><span class="sxs-lookup"><span data-stu-id="75b8e-135">Deploy the app  with the following app configuration settings:</span></span>

      <span data-ttu-id="75b8e-136">**key** = IntuneMAMUPN,  **value** = <username@company.com></span><span class="sxs-lookup"><span data-stu-id="75b8e-136">**key** = IntuneMAMUPN,  **value** = <username@company.com></span></span>

      <span data-ttu-id="75b8e-137">Exemplo: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]</span><span class="sxs-lookup"><span data-stu-id="75b8e-137">Example: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]</span></span>

  2.  <span data-ttu-id="75b8e-138">Implante Abrir na política de gerenciamento usando o provedor de MDM de terceiros para dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="75b8e-138">Deploy the Open in management policy using your third-party MDM provider to enrolled devices.</span></span>


### <span data-ttu-id="75b8e-139">Exemplo 1: experiência de Admin no console do MDM de terceiros</span><span class="sxs-lookup"><span data-stu-id="75b8e-139">Example 1: Admin experience in third-party MDM console</span></span>
<a id="example-1-admin-experience-in-third-party-mdm-console" class="xliff"></a>

1. <span data-ttu-id="75b8e-140">Vá para o console de administração do seu provedor MDM de terceiros.</span><span class="sxs-lookup"><span data-stu-id="75b8e-140">Go to the admin console of your third-party MDM provider.</span></span> <span data-ttu-id="75b8e-141">Vá para a seção do console em que você implanta as definições de configuração de aplicativo para dispositivos iOS registrados.</span><span class="sxs-lookup"><span data-stu-id="75b8e-141">Go to the section of the console in which you deploy application configuration settings to enrolled iOS devices.</span></span>

2. <span data-ttu-id="75b8e-142">Na seção Configuração do Aplicativo, insira a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="75b8e-142">In the Application Configuration section, enter the following setting:</span></span>

  <span data-ttu-id="75b8e-143">**key** = IntuneMAMUPN,  **value** = <username@company.com></span><span class="sxs-lookup"><span data-stu-id="75b8e-143">**key** = IntuneMAMUPN,  **value** = <username@company.com></span></span>

  <span data-ttu-id="75b8e-144">A sintaxe exata do par chave/valor pode diferir com base no provedor de MDM de terceiros.</span><span class="sxs-lookup"><span data-stu-id="75b8e-144">The exact syntax of the key/value pair may differ based on your third-party MDM provider.</span></span> <span data-ttu-id="75b8e-145">A tabela a seguir mostra exemplos de provedores de MDM de terceiros e os valores exatos que você deve digitar para o par chave/valor.</span><span class="sxs-lookup"><span data-stu-id="75b8e-145">The table below shows examples of third-party MDM providers and the exact values you should enter for the key/value pair.</span></span>

|<span data-ttu-id="75b8e-146">Provedor de MDM de terceiros</span><span class="sxs-lookup"><span data-stu-id="75b8e-146">Third-party MDM provider</span></span>| <span data-ttu-id="75b8e-147">Chave de Configuração</span><span class="sxs-lookup"><span data-stu-id="75b8e-147">Configuration Key</span></span> | <span data-ttu-id="75b8e-148">Tipo de valor</span><span class="sxs-lookup"><span data-stu-id="75b8e-148">Value Type</span></span> | <span data-ttu-id="75b8e-149">Valor da Configuração</span><span class="sxs-lookup"><span data-stu-id="75b8e-149">Configuration Value</span></span>|
| ------- | ---- | ---- | ---- |
|<span data-ttu-id="75b8e-150">VMware AirWatch</span><span class="sxs-lookup"><span data-stu-id="75b8e-150">VMware AirWatch</span></span>| <span data-ttu-id="75b8e-151">IntuneMAMUPN</span><span class="sxs-lookup"><span data-stu-id="75b8e-151">IntuneMAMUPN</span></span> | <span data-ttu-id="75b8e-152">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="75b8e-152">String</span></span> | <span data-ttu-id="75b8e-153">{UserPrincipalName}</span><span class="sxs-lookup"><span data-stu-id="75b8e-153">{UserPrincipalName}</span></span>|
|<span data-ttu-id="75b8e-154">MobileIron</span><span class="sxs-lookup"><span data-stu-id="75b8e-154">MobileIron</span></span> | <span data-ttu-id="75b8e-155">IntuneMAMUPN</span><span class="sxs-lookup"><span data-stu-id="75b8e-155">IntuneMAMUPN</span></span> | <span data-ttu-id="75b8e-156">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="75b8e-156">String</span></span> | <span data-ttu-id="75b8e-157">${userUPN} **ou** ${userEmailAddress}</span><span class="sxs-lookup"><span data-stu-id="75b8e-157">${userUPN} **or** ${userEmailAddress}</span></span> |


### <span data-ttu-id="75b8e-158">Exemplo 2: experiência do usuário final</span><span class="sxs-lookup"><span data-stu-id="75b8e-158">Example 2: End-user experience</span></span>
<a id="example-2-end-user-experience" class="xliff"></a>

1.  <span data-ttu-id="75b8e-159">O usuário final instala um aplicativo Microsoft Word no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="75b8e-159">End user installs Microsoft Word app on the device.</span></span>

2.  <span data-ttu-id="75b8e-160">O usuário final inicia o aplicativo de email nativo gerenciado para acessar seus emails.</span><span class="sxs-lookup"><span data-stu-id="75b8e-160">End user launches the managed native email app to access their email.</span></span>

3.  <span data-ttu-id="75b8e-161">O usuário final tenta abrir o documento do email nativo no Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="75b8e-161">End user tries to open document from native mail in Microsoft Word.</span></span>

4.  <span data-ttu-id="75b8e-162">Quando o aplicativo Word é iniciado, o usuário final é solicitado a fazer logon usando sua conta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="75b8e-162">When the Word app launches, the end user is prompted to log in using their work account.</span></span>  <span data-ttu-id="75b8e-163">Essa conta de trabalho que o usuário final insere quando solicitado deve corresponder à conta especificada nas definições de configuração de aplicativo para o aplicativo Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="75b8e-163">This work account the end user enters when prompted should match account you specified in the configured in the app configuration settings for the Microsoft Word app.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75b8e-164">O usuário final pode adicionar outras contas pessoais ao Word para fazer seu trabalho pessoal e não ser afetado pelas políticas de proteção de aplicativo ao usar o aplicativo do Word em um contexto pessoal.</span><span class="sxs-lookup"><span data-stu-id="75b8e-164">The end user can add other personal accounts to Word to do their personal work and not be affected by the app protection policies when using the Word app in a personal context.</span></span>

5.  <span data-ttu-id="75b8e-165">Quando o logon for bem-sucedido, as configurações da política de proteção de aplicativo são aplicadas ao aplicativo Word.</span><span class="sxs-lookup"><span data-stu-id="75b8e-165">When the login is successful, the app protection policy settings are applied to the Word app.</span></span>

6.  <span data-ttu-id="75b8e-166">A transferência de dados é bem-sucedida e o documento é marcado como identidade corporativa no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="75b8e-166">Now the data transfer succeeds and the document is tagged with a corporate identity in the app.</span></span> <span data-ttu-id="75b8e-167">Além disso, os dados são tratados em um contexto de trabalho e as configurações da política são aplicadas de acordo.</span><span class="sxs-lookup"><span data-stu-id="75b8e-167">In addition, the data is treated in a work context and the policy settings are applied accordingly.</span></span>

### <span data-ttu-id="75b8e-168">Validar configuração de UPN do usuário para EMM de terceiros</span><span class="sxs-lookup"><span data-stu-id="75b8e-168">Validate user UPN setting for third-party EMM</span></span>
<a id="validate-user-upn-setting-for-third-party-emm" class="xliff"></a>

<span data-ttu-id="75b8e-169">Depois de definir a configuração de UPN do usuário, você deve validar a capacidade do aplicativo iOS para receber e atender à política de proteção de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="75b8e-169">After configuring the user UPN setting, you should validate the iOS app's ability to receive and comply to Intune app protection policy.</span></span>

<span data-ttu-id="75b8e-170">Por exemplo, a configuração de política **Exigir PIN do aplicativo** é fácil de testar visualmente em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="75b8e-170">For example, the **Require app PIN** policy setting is easy to visually test on a device.</span></span> <span data-ttu-id="75b8e-171">Se a configuração de política estiver definida como **Sim**, o usuário final receberá um prompt para definir ou inserir um PIN durante a tentativa de acessar dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="75b8e-171">If the policy setting is set to **Yes**, the end user should see a prompt to set or enter a PIN when attempting to access company data.</span></span>

<span data-ttu-id="75b8e-172">Primeiro, [crie e atribua uma política de proteção de aplicativo](app-protection-policies.md) no aplicativo iOS.</span><span class="sxs-lookup"><span data-stu-id="75b8e-172">First,  [create and assign an app protection policy](app-protection-policies.md) to the iOS app.</span></span> <span data-ttu-id="75b8e-173">Consulte [Validar as políticas de proteção do aplicativo](app-protection-policies-validate.md) para obter mais informações sobre como testar a política de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="75b8e-173">See [Validate app protection policies](app-protection-policies-validate.md) for more information on how to test app protection policy.</span></span>


### <span data-ttu-id="75b8e-174">Consulte também</span><span class="sxs-lookup"><span data-stu-id="75b8e-174">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="75b8e-175">O que é a política de proteção de aplicativo do Intune</span><span class="sxs-lookup"><span data-stu-id="75b8e-175">What is Intune app protection policy</span></span>](app-protection-policy.md)
