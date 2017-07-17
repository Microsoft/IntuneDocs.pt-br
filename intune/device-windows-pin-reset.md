---
title: Redefinir senha em dispositivos Windows com o Intune
titleSuffix: Intune on Azure
description: "Saiba como usar o Intune para redefinir a senha em dispositivos do Windows integrados com o Serviço de Redefinição do PIN da Microsoft.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3688eef68fc9dcfced976db02c8d50126fa30da8
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2017
---
# <span data-ttu-id="3e7e2-103">Redefinir a senha em dispositivos Windows integrado com o Serviço de Redefinição de PIN da Microsoft usando o Intune</span><span class="sxs-lookup"><span data-stu-id="3e7e2-103">Reset the passcode on Windows devices integrated with the Microsoft PIN Reset Service using Intune</span></span>
<a id="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune" class="xliff"></a>

<span data-ttu-id="3e7e2-104">A capacidade de redefinição de senha para dispositivos Windows integra-se com o Serviço de Redefinição de PIN da Microsoft para permitir que você gere uma nova senha para dispositivos que executam o Windows 10 Mobile.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-104">The reset passcode capability for Windows devices integrates with the Microsoft Pin Reset Service to let you generate a new passcode for devices that run Windows 10 Mobile.</span></span> <span data-ttu-id="3e7e2-105">Os dispositivos devem executar a Atualização do Windows 10 para Criadores ou posterior.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-105">The devices must be running the Windows 10 Creators Update, or later.</span></span>


## <span data-ttu-id="3e7e2-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3e7e2-106">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>

<span data-ttu-id="3e7e2-107">Antes de redefinir remotamente a senha em dispositivos Windows que você pode gerenciar, integre o serviço de redefinição do PIN para seu locatário do Intune e configure os dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-107">Before you can remotely reset the passcode on Windows devices you can manage, you must onboard the PIN reset service to your Intune tenant, and configure devices you manage.</span></span> <span data-ttu-id="3e7e2-108">Siga estas instruções para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="3e7e2-108">Follow these instructions to get that set up:</span></span>

### <span data-ttu-id="3e7e2-109">Conecte o Intune ao serviço de redefinição de PIN</span><span class="sxs-lookup"><span data-stu-id="3e7e2-109">Connect Intune with the PIN reset service</span></span>
<a id="connect-intune-with-the-pin-reset-service" class="xliff"></a>

1. <span data-ttu-id="3e7e2-110">Visite o [site de integração do Serviço de Redefinição de PIN da Microsoft](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) e entre usando a conta de administrador de locatário que você usa para gerenciar seu locatário do Intune.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-110">Visit [Microsoft PIN Reset Service Integration website](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent), and sign in using the tenant administrator account you use to manage your Intune tenant.</span></span>
2. <span data-ttu-id="3e7e2-111">Após fazer logon, clique em **Aceitar** para dar consentimento para o serviço de redefinição de PIN acessar sua conta.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-111">After you log in, click **Accept** to give consent for the PIN reset service to access your account.</span></span><br><span data-ttu-id="3e7e2-112">
![Página de permissões do serviço de redefinição de PIN](./media/pin-reset-service-application.png)</span><span class="sxs-lookup"><span data-stu-id="3e7e2-112">
![PIN reset service permissions page](./media/pin-reset-service-application.png)</span></span>
3. <span data-ttu-id="3e7e2-113">No Portal do Azure, você pode verificar se o Intune e o serviço de redefinição de PIN foram integrados dos aplicativos Enterprise – Todas as folhas de aplicativos conforme mostrado na seguinte captura de tela:</span><span class="sxs-lookup"><span data-stu-id="3e7e2-113">In the Azure portal, you can verify that Intune and the PIN reset service were integrated from the Enterprise applications - All applications blade as shown in the following screenshot:</span></span><br><span data-ttu-id="3e7e2-114">
![Aplicativo do serviço de redefinição de PIN no Azure](./media/pin-reset-service-home-screen.png)</span><span class="sxs-lookup"><span data-stu-id="3e7e2-114">
![PIN reset service application in Azure](./media/pin-reset-service-home-screen.png)</span></span>
4. <span data-ttu-id="3e7e2-115">Faça logon [neste site](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) usando as credenciais de administrador de locatário do Intune e escolha **Aceitar** novamente para dar consentimento para o serviço acessar sua conta.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-115">Log in to [this website](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) using your Intune tenant admin credentials and, again, choose **Accept** to give consent for the service to access your account.</span></span>

### <span data-ttu-id="3e7e2-116">Configurar os dispositivos do Windows para usar a redefinição de PIN</span><span class="sxs-lookup"><span data-stu-id="3e7e2-116">Configure Windows devices to use PIN reset</span></span>
<a id="configure-windows-devices-to-use-pin-reset" class="xliff"></a>

<span data-ttu-id="3e7e2-117">Para configurar a redefinição de PIN nos dispositivos Windows que você gerencia, use uma [política de dispositivo personalizado do Intune Windows 10](custom-settings-windows-10.md) para habilitar o recurso.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-117">To configure PIN reset on Windows devices you manage, use an [Intune Windows 10 custom device policy](custom-settings-windows-10.md) to enable the feature.</span></span> <span data-ttu-id="3e7e2-118">Configure a política usando os seguintes CSPs (provedores de serviços de configuração) de política do Windows:</span><span class="sxs-lookup"><span data-stu-id="3e7e2-118">Configure the policy using the following Windows policy configuration service providers (CSPs):</span></span>


- <span data-ttu-id="3e7e2-119">**Para usuários** - **./User/Vendor/MSFT/PassportForWork/<tenant ID>/Policies/EnablePinRecovery**</span><span class="sxs-lookup"><span data-stu-id="3e7e2-119">**For users** - **./User/Vendor/MSFT/PassportForWork/<tenant ID>/Policies/EnablePinRecovery**</span></span>
- <span data-ttu-id="3e7e2-120">**Para dispositivos** - **./Device/Vendor/MSFT/PassportForWork/<tenant ID>/Policies/EnablePinRecovery**</span><span class="sxs-lookup"><span data-stu-id="3e7e2-120">**For devices** - **./Device/Vendor/MSFT/PassportForWork/<tenant ID>/Policies/EnablePinRecovery**</span></span>

<span data-ttu-id="3e7e2-121">Ambos os valores para esses CSPs devem ser definidos como **True**.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-121">The values for these CSPs must both be set to **True**.</span></span>

## <span data-ttu-id="3e7e2-122">Etapas para redefinir a senha</span><span class="sxs-lookup"><span data-stu-id="3e7e2-122">Steps to reset the passcode</span></span>
<a id="steps-to-reset-the-passcode" class="xliff"></a>

1. <span data-ttu-id="3e7e2-123">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-123">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="3e7e2-124">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-124">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="3e7e2-125">Na folha **Intune**, escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-125">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="3e7e2-126">Na folha **Dispositivos**, escolha **Gerenciar** > **Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-126">On the **Devices** blade, choose **Manage** > **All devices**.</span></span>
5. <span data-ttu-id="3e7e2-127">Selecione o dispositivo para o qual você deseja redefinir a senha e, na folha de propriedades do dispositivo, escolha **Nova senha**.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-127">Select the device for which you want to reset the passcode, and then, on the device properties blade, choose **New passcode**.</span></span>
6. <span data-ttu-id="3e7e2-128">Na confirmação que aparece, escolha **Sim**.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-128">From the confirmation that appears, choose **Yes**.</span></span> <span data-ttu-id="3e7e2-129">A senha é gerada e exibida no portal pelos próximos sete dias.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-129">The passcode is generated, and is displayed in the portal for the next seven days.</span></span>

## <span data-ttu-id="3e7e2-130">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3e7e2-130">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="3e7e2-131">Se a redefinição de senha falhar, é fornecido um link no portal para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3e7e2-131">If the passcode reset fails, a link is provided in the portal to get more information.</span></span>


