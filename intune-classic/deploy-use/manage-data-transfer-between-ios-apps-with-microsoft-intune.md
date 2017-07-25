---
title: "Gerenciar a transferência de dados entre aplicativos do iOS"
description: "Use este tópico para entender como você pode usar o recurso Open in do iOS e as políticas de gerenciamento de aplicativo móvel para gerenciar transferências de dados entre aplicativos."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 05975303bd45764d56f00986aea5aa30399893f9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="c0398-103">Gerenciar transferência de dados entre aplicativos iOS com Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c0398-103">Manage data transfer between iOS apps with Microsoft Intune</span></span>
<a id="manage-data-transfer-between-ios-apps-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <span data-ttu-id="c0398-104">Gerenciar aplicativos iOS</span><span class="sxs-lookup"><span data-stu-id="c0398-104">Manage iOS apps</span></span>
<a id="manage-ios-apps" class="xliff"></a>
<span data-ttu-id="c0398-105">Proteger os dados da sua empresa inclui garantir que as transferências de arquivos sejam restritas a aplicativos gerenciados por você.</span><span class="sxs-lookup"><span data-stu-id="c0398-105">Protecting your company data includes making sure that file transfers are restricted to apps that are managed by you.</span></span>  <span data-ttu-id="c0398-106">Você pode gerenciar aplicativos iOS das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="c0398-106">You can manage iOS apps in the following ways:</span></span>

-   <span data-ttu-id="c0398-107">Evite a perda de dados da empresa configurando uma política de proteção de aplicativo, que chamaremos de aplicativos **gerenciados por política** aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c0398-107">Prevent company data loss  by configuring an app protection policy for the apps, which we will refer to as **policy-managed**  apps.</span></span>

-   <span data-ttu-id="c0398-108">Você também pode implantar e gerenciar aplicativos pelo **canal MDM**.</span><span class="sxs-lookup"><span data-stu-id="c0398-108">You can also deploy and manage apps through the **MDM channel**.</span></span>  <span data-ttu-id="c0398-109">Isso requer que os dispositivos sejam registrados na solução MDM.</span><span class="sxs-lookup"><span data-stu-id="c0398-109">This requires that the devices are enrolled in the MDM solution.</span></span> <span data-ttu-id="c0398-110">Eles podem ser aplicativos **gerenciados por política** ou outros aplicativos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="c0398-110">These can be **policy-managed**  apps or other managed  apps.</span></span>

<span data-ttu-id="c0398-111">O recurso **Abrir em gerenciamento** para dispositivos iOS pode limitar as transferências de arquivo entre os aplicativos que são implantados por meio do canal **MDM**.</span><span class="sxs-lookup"><span data-stu-id="c0398-111">The **Open-in management** feature for iOS devices can limit file transfers between apps that are deployed through the **MDM channel**.</span></span> <span data-ttu-id="c0398-112">As restrições de Abrir em gerenciamento são definidas nas definições de configuração e implantadas usando o software de MDM.</span><span class="sxs-lookup"><span data-stu-id="c0398-112">Open-in management restrictions are set in configuration settings and deployed using your MDM solution.</span></span>  <span data-ttu-id="c0398-113">Quando o usuário instala o aplicativo implantado, são aplicadas restrições definidas por você.</span><span class="sxs-lookup"><span data-stu-id="c0398-113">When the user installs the deployed app, the restrictions you set are applied.</span></span>

##  <span data-ttu-id="c0398-114">Gerenciar a transferência de dados entre aplicativos do iOS</span><span class="sxs-lookup"><span data-stu-id="c0398-114">Manage data transfer between iOS apps</span></span>
<a id="manage-data-transfer-between-ios-apps" class="xliff"></a>
<span data-ttu-id="c0398-115">Políticas de proteção de aplicativo podem ser usadas com o recurso iOS **Abrir no gerenciamento** para proteger os dados da empresa das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="c0398-115">App protection policies can be used with the iOS **Open in management** feature to protect company data in the following ways:</span></span>

-   <span data-ttu-id="c0398-116">**Dispositivos de propriedade do funcionário não gerenciados por nenhuma solução de MDM:** você pode definir as [configurações de política de proteção de aplicativo](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) para **Permitir que o aplicativo transfira dados somente para aplicativos gerenciados**.</span><span class="sxs-lookup"><span data-stu-id="c0398-116">**Employee-owned devices not managed by any MDM solution:** You can set the [app protection policy setting](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) to **Allow app to transfer data to only managed apps**.</span></span> <span data-ttu-id="c0398-117">Quando o usuário final abrir um arquivo protegido em um aplicativo não gerenciado por política, o arquivo ficará ilegível.</span><span class="sxs-lookup"><span data-stu-id="c0398-117">When the end user opens a protected file in an app that is not policy-managed, the file is unreadable.</span></span>

-   <span data-ttu-id="c0398-118">**Dispositivos gerenciados pelo Intune:** para dispositivos registrados no Intune, transferência de dados entre aplicativos com as políticas de proteção de aplicativo e outros aplicativos do iOS gerenciado implantados por meio do Intune é permitida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c0398-118">**Devices managed by Intune:** For devices enrolled in Intune, data transfer between apps with app protection policies and other managed iOS apps deployed through Intune is allowed automatically.</span></span> <span data-ttu-id="c0398-119">Para permitir a transferência de dados entre aplicativos com as políticas de proteção de aplicativo, habilite a configuração **Permitir que o aplicativo transfira dados somente para aplicativos gerenciados**.</span><span class="sxs-lookup"><span data-stu-id="c0398-119">To allow data transfer between apps with app protection policies, enable the **Allow app to transfer data to only managed apps** setting.</span></span> <span data-ttu-id="c0398-120">Você pode usar o recurso **Aberto em gerenciamento** para controlar a transferência de dados entre aplicativos que são implantados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="c0398-120">You can use the **Open in management** feature to control data transfer between apps that are deployed through Intune.</span></span>   

-   <span data-ttu-id="c0398-121">**Dispositivos gerenciados por uma solução MDM de terceiro:** você pode restringir a transferência de dados somente para aplicativos gerenciados usando o recurso **Aberto em gerenciamento** do iOS.</span><span class="sxs-lookup"><span data-stu-id="c0398-121">**Devices managed by a third party MDM solution:** You can restrict data transfer to only managed apps by using the iOS **Open in management** feature.</span></span>
<span data-ttu-id="c0398-122">Para verificar se os aplicativos implantados usando a solução de MDM de terceiros também estão associados às políticas de proteção de aplicativo configuradas no Intune, você deverá definir a configuração de UPN do usuário conforme descrito no passo a passo [Definir configuração de UPN do usuário](#configure-user-upn-setting-for-third-party-emm).</span><span class="sxs-lookup"><span data-stu-id="c0398-122">To make sure that apps that you deploy using your third party MDM solution are also associated with the app protection policies you have configured in Intune, you must configure the user UPN setting as described in the [Configure user UPN setting](#configure-user-upn-setting-for-third-party-emm) walkthrough.</span></span>  <span data-ttu-id="c0398-123">Quando os aplicativos são implantados com a configuração de UPN do usuário, as políticas de proteção de aplicativo serão aplicadas ao aplicativo quando o usuário final entrar usando sua conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="c0398-123">When apps are deployed with the user UPN setting, the app protection policies are applied to the app when the end user signs-in using their work account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0398-124">A configuração de UPN do usuário só será necessária para aplicativos implantados para dispositivos gerenciados por um MDM de terceiro.</span><span class="sxs-lookup"><span data-stu-id="c0398-124">The user UPN setting is only required for apps deployed to devices managed by a third-party MDM.</span></span>  <span data-ttu-id="c0398-125">Para dispositivos gerenciados pelo Intune, essa configuração não é necessária.</span><span class="sxs-lookup"><span data-stu-id="c0398-125">For Intune-managed devices, this setting is not required.</span></span>

## <span data-ttu-id="c0398-126">Definir configuração de UPN do usuário para EMM de terceiros</span><span class="sxs-lookup"><span data-stu-id="c0398-126">Configure user UPN setting for third-party EMM</span></span>
<a id="configure-user-upn-setting-for-third-party-emm" class="xliff"></a>
<span data-ttu-id="c0398-127">Essa configuração de UPN do usuário é **necessária** para dispositivos gerenciados por uma solução EMM de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c0398-127">Configuring the user UPN setting is **required** for devices that are managed by a third-party EMM solution.</span></span> <span data-ttu-id="c0398-128">O procedimento descrito abaixo é um fluxo geral de como definir a configuração de UPN e experiência do usuário final resultante:</span><span class="sxs-lookup"><span data-stu-id="c0398-128">The procedure described below is a general flow on how to configure the UPN setting and the resulting end user experience:</span></span>


1.  <span data-ttu-id="c0398-129">No portal do Azure, [configure uma política de proteção de aplicativo](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) para a plataforma iOS.</span><span class="sxs-lookup"><span data-stu-id="c0398-129">In the Azure portal, [configure an app protection policy](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) for iOS platform.</span></span> <span data-ttu-id="c0398-130">Defina as configurações de política conforme os requisitos da sua empresa e selecione os aplicativos que devem ter essa política.</span><span class="sxs-lookup"><span data-stu-id="c0398-130">Configure policy settings per your company requirements and select the apps that should have this policy.</span></span>

2.  <span data-ttu-id="c0398-131">Implante os aplicativos e o perfil de email que você deseja gerenciar **por meio da solução MDM de terceiros** usando as etapas gerais abaixo.</span><span class="sxs-lookup"><span data-stu-id="c0398-131">Deploy the apps and the email profile that you want managed **through your third-party MDM solution** using the generalized steps below.</span></span> <span data-ttu-id="c0398-132">Essa experiência também é abordada no Exemplo 1.</span><span class="sxs-lookup"><span data-stu-id="c0398-132">This experience is also covered by Example 1.</span></span>

  1.  <span data-ttu-id="c0398-133">Implante o aplicativo com as seguintes configurações do aplicativo:</span><span class="sxs-lookup"><span data-stu-id="c0398-133">Deploy the app  with the following app configuration settings:</span></span>

      <span data-ttu-id="c0398-134">**key** = IntuneMAMUPN,  **value** = <username@company.com></span><span class="sxs-lookup"><span data-stu-id="c0398-134">**key** = IntuneMAMUPN,  **value** = <username@company.com></span></span>

      <span data-ttu-id="c0398-135">Exemplo: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]</span><span class="sxs-lookup"><span data-stu-id="c0398-135">Example: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]</span></span>

  2.  <span data-ttu-id="c0398-136">Implante Abrir na política de gerenciamento usando o provedor de MDM de terceiros para dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="c0398-136">Deploy the Open in management policy using your third-party MDM provider to enrolled devices.</span></span>


### <span data-ttu-id="c0398-137">Exemplo 1: experiência de Admin no console do MDM de terceiros</span><span class="sxs-lookup"><span data-stu-id="c0398-137">Example 1: Admin experience in third-party MDM console</span></span>
<a id="example-1-admin-experience-in-third-party-mdm-console" class="xliff"></a>

1. <span data-ttu-id="c0398-138">Vá para o console de administração do seu provedor MDM de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c0398-138">Go to the admin console of your third-party MDM provider.</span></span> <span data-ttu-id="c0398-139">Vá para a seção do console em que você implanta as definições de configuração de aplicativo para dispositivos iOS registrados.</span><span class="sxs-lookup"><span data-stu-id="c0398-139">Go to the section of the console in which you deploy application configuration settings to enrolled iOS devices.</span></span>

2. <span data-ttu-id="c0398-140">Na seção Configuração do Aplicativo, insira a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="c0398-140">In the Application Configuration section, enter the following setting:</span></span>

  <span data-ttu-id="c0398-141">**key** = IntuneMAMUPN,  **value** = <username@company.com></span><span class="sxs-lookup"><span data-stu-id="c0398-141">**key** = IntuneMAMUPN,  **value** = <username@company.com></span></span>

  <span data-ttu-id="c0398-142">A sintaxe exata do par chave/valor pode diferir com base no provedor de MDM de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c0398-142">The exact syntax of the key/value pair may differ based on your third-party MDM provider.</span></span> <span data-ttu-id="c0398-143">A tabela a seguir mostra exemplos de provedores de MDM de terceiros e os valores exatos que você deve digitar para o par chave/valor.</span><span class="sxs-lookup"><span data-stu-id="c0398-143">The table below shows examples of third-party MDM providers and the exact values you should enter for the key/value pair.</span></span>

|<span data-ttu-id="c0398-144">Provedor de MDM de terceiros</span><span class="sxs-lookup"><span data-stu-id="c0398-144">Third-party MDM provider</span></span>| <span data-ttu-id="c0398-145">Chave de Configuração</span><span class="sxs-lookup"><span data-stu-id="c0398-145">Configuration Key</span></span> | <span data-ttu-id="c0398-146">Tipo de valor</span><span class="sxs-lookup"><span data-stu-id="c0398-146">Value Type</span></span> | <span data-ttu-id="c0398-147">Valor da Configuração</span><span class="sxs-lookup"><span data-stu-id="c0398-147">Configuration Value</span></span>|
| ------- | ---- | ---- | ---- |
| <span data-ttu-id="c0398-148">VMware AirWatch</span><span class="sxs-lookup"><span data-stu-id="c0398-148">VMware AirWatch</span></span> | <span data-ttu-id="c0398-149">IntuneMAMUPN</span><span class="sxs-lookup"><span data-stu-id="c0398-149">IntuneMAMUPN</span></span> | <span data-ttu-id="c0398-150">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c0398-150">String</span></span> | <span data-ttu-id="c0398-151">{UserPrincipalName}</span><span class="sxs-lookup"><span data-stu-id="c0398-151">{UserPrincipalName}</span></span>|
| <span data-ttu-id="c0398-152">MobileIron Core</span><span class="sxs-lookup"><span data-stu-id="c0398-152">MobileIron Core</span></span> | <span data-ttu-id="c0398-153">IntuneMAMUPN</span><span class="sxs-lookup"><span data-stu-id="c0398-153">IntuneMAMUPN</span></span> | <span data-ttu-id="c0398-154">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c0398-154">String</span></span> | <span data-ttu-id="c0398-155">$EMAIL$ **ou** $USER_UPN$</span><span class="sxs-lookup"><span data-stu-id="c0398-155">$EMAIL$ **or** $USER_UPN$</span></span> |
| <span data-ttu-id="c0398-156">MobileIron Cloud</span><span class="sxs-lookup"><span data-stu-id="c0398-156">MobileIron Cloud</span></span> | <span data-ttu-id="c0398-157">IntuneMAMUPN</span><span class="sxs-lookup"><span data-stu-id="c0398-157">IntuneMAMUPN</span></span> | <span data-ttu-id="c0398-158">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c0398-158">String</span></span> | <span data-ttu-id="c0398-159">${userUPN} **ou** ${userEmailAddress}</span><span class="sxs-lookup"><span data-stu-id="c0398-159">${userUPN} **or** ${userEmailAddress}</span></span> |

### <span data-ttu-id="c0398-160">Exemplo 2: experiência do usuário final</span><span class="sxs-lookup"><span data-stu-id="c0398-160">Example 2: End-user experience</span></span>
<a id="example-2-end-user-experience" class="xliff"></a>

1.  <span data-ttu-id="c0398-161">O usuário final instala um aplicativo Microsoft Word no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c0398-161">End user installs Microsoft Word app on the device.</span></span>

2.  <span data-ttu-id="c0398-162">O usuário final inicia o aplicativo de email nativo gerenciado para acessar seus emails.</span><span class="sxs-lookup"><span data-stu-id="c0398-162">End user launches the managed native email app to access their email.</span></span>

3.  <span data-ttu-id="c0398-163">O usuário final tenta abrir o documento do email nativo no Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="c0398-163">End user tries to open document from native mail in Microsoft Word.</span></span>

4.  <span data-ttu-id="c0398-164">Quando o aplicativo Word é iniciado, o usuário final é solicitado a fazer logon usando sua conta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c0398-164">When the Word app launches, the end user is prompted to log in using their work account.</span></span>  <span data-ttu-id="c0398-165">Essa conta de trabalho que o usuário final insere quando solicitado deve corresponder à conta especificada nas definições de configuração de aplicativo para o aplicativo Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="c0398-165">This work account the end user enters when prompted should match account you specified in the configured in the app configuration settings for the Microsoft Word app.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0398-166">O usuário final pode adicionar outras contas pessoais ao Word para fazer seu trabalho pessoal e não ser afetado pelas políticas de proteção de aplicativo ao usar o aplicativo do Word em um contexto pessoal.</span><span class="sxs-lookup"><span data-stu-id="c0398-166">The end user can add other personal accounts to Word to do their personal work and not be affected by the app protection policies when using the Word app in a personal context.</span></span>

5.  <span data-ttu-id="c0398-167">Quando o logon for bem-sucedido, as configurações da política de proteção de aplicativo são aplicadas ao aplicativo Word.</span><span class="sxs-lookup"><span data-stu-id="c0398-167">When the login is successful, the app protection policy settings are applied to the Word app.</span></span>

6.  <span data-ttu-id="c0398-168">Agora, a transferência de arquivos deu certo e o documento foi marcado como identidade corporativa no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c0398-168">Now the file transfer has succeeded and the document is tagged as corporate identity in the app.</span></span> <span data-ttu-id="c0398-169">Além disso, o arquivo é tratado em um contexto de trabalho, e as configurações da política são aplicadas adequadamente.</span><span class="sxs-lookup"><span data-stu-id="c0398-169">In addition, the file is treated in a work context and the policy settings are applied accordingly.</span></span>

### <span data-ttu-id="c0398-170">Validar configuração de UPN do usuário para EMM de terceiros</span><span class="sxs-lookup"><span data-stu-id="c0398-170">Validate user UPN setting for third-party EMM</span></span>
<a id="validate-user-upn-setting-for-third-party-emm" class="xliff"></a>

<span data-ttu-id="c0398-171">Depois de definir a configuração de UPN do usuário, você deve validar a capacidade do aplicativo iOS para receber e atender à política de proteção de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="c0398-171">After configuring the user UPN setting, you should validate the iOS app's ability to receive and comply to Intune app protection policy.</span></span>

<span data-ttu-id="c0398-172">Por exemplo, a configuração de política **Exigir PIN do aplicativo** é fácil de testar visualmente em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c0398-172">For example, the **Require app PIN** policy setting is easy to visually test on a device.</span></span> <span data-ttu-id="c0398-173">Se a configuração de política estiver definida como **Sim**, o usuário final receberá um prompt para definir ou inserir um PIN durante a tentativa de acessar dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="c0398-173">If the policy setting is set to **Yes**, the end user should see a prompt to set or enter a PIN when attempting to access company data.</span></span>

<span data-ttu-id="c0398-174">Primeiro, [crie e implante uma política de proteção de aplicativo](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) no aplicativo iOS.</span><span class="sxs-lookup"><span data-stu-id="c0398-174">First,  [create and deploy an app protection policy](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) to the iOS app.</span></span> <span data-ttu-id="c0398-175">Consulte [Validar as políticas de proteção do aplicativo](validate-mobile-application-management.md) para obter mais informações sobre como testar a política de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c0398-175">See [Validate app protection policies](validate-mobile-application-management.md) for more information on how to test app protection policy.</span></span>



### <span data-ttu-id="c0398-176">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c0398-176">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="c0398-177">Proteger dados de aplicativo usando políticas de proteção de aplicativo com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c0398-177">Protect app data using app protection policies with Microsoft Intune</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
