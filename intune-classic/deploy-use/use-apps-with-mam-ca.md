---
title: Usar aplicativos com AC de MAM
description: "Entenda como o AC para MAM pode ajudar a controlar os aplicativos que têm acesso aos serviços do O365."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ee407827c1c4eb7b113d29c301da0b9fa08fa86d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="7f657-103">O que esperar ao usar um aplicativo com AC baseado em aplicativo</span><span class="sxs-lookup"><span data-stu-id="7f657-103">What to expect when using an app with app-based CA</span></span>
<a id="what-to-expect-when-using-an-app-with-app-based-ca" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="7f657-104">O AC baseado em aplicativo verifica a identidade do aplicativo aprovado por meio de um aplicativo agente, que deve estar presente no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7f657-104">App-based CA verifies the identity of the approved application by means of a broker app that must be present on the device:</span></span>
*  <span data-ttu-id="7f657-105">No **iOS**, o **aplicativo Microsoft Authenticator** é o aplicativo agente.</span><span class="sxs-lookup"><span data-stu-id="7f657-105">On **iOS**, the **Azure Authenticator app** is the broker app.</span></span>
* <span data-ttu-id="7f657-106">No **Android**, o **aplicativo do Portal da Empresa do Intune** é o aplicativo agente.</span><span class="sxs-lookup"><span data-stu-id="7f657-106">On **Android**, the **Intune Company Portal app** is the broker app.</span></span> 

<span data-ttu-id="7f657-107">Quando os usuários finais entram pela primeira vez em um aplicativo em que há suporte para AC baseado em aplicativo, como o OneDrive ou o Outlook, eles são solicitados a instalar o aplicativo agente e a registrar o dispositivo com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7f657-107">End-users signing in for the first time, to an app that is supported by app-based CA, like OneDrive or Outlook, are prompted to install the broker app and register the device with Azure AD.</span></span> <span data-ttu-id="7f657-108">O registro de dispositivos no Azure AD (anteriormente conhecido como Ingresso no Local de Trabalho) criará um registro de dispositivo e um certificado no qual os tokens serão emitidos.</span><span class="sxs-lookup"><span data-stu-id="7f657-108">Device registration in Azure AD (previously known as Workplace Join) will create a device record and certificate against which tokens are issued.</span></span>  <span data-ttu-id="7f657-109">Esse processo **não** é igual ao **registro do MDM**.</span><span class="sxs-lookup"><span data-stu-id="7f657-109">This is **not** the same as **MDM enrollment**.</span></span> <span data-ttu-id="7f657-110">Não há perfis de gerenciamento ou políticas aplicadas e não há nenhum inventário de aplicativos do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7f657-110">There are no management profiles or policies that are applied, and there is no inventory taken of apps on the device.</span></span>  <span data-ttu-id="7f657-111">O processo de instalação do aplicativo agente e de registro do dispositivo só ocorrerá quando o aplicativo gerenciado for usado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="7f657-111">The process of installing the broker app and registering the device will only happen on the first use of a managed app.</span></span>

<span data-ttu-id="7f657-112">A seguir, temos uma lista de propriedades que são derivadas diretamente do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7f657-112">The following is a list of properties that are directly derived from the device:</span></span>

* <span data-ttu-id="7f657-113">alternativeSecurityIds (hash de chave pública e impressão digital do certificado do Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="7f657-113">alternativeSecurityIds (Azure Active Directory Certificate thumbprint and public key hash)</span></span>
* <span data-ttu-id="7f657-114">deviceOSType</span><span class="sxs-lookup"><span data-stu-id="7f657-114">deviceOSType</span></span>
* <span data-ttu-id="7f657-115">deviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="7f657-115">deviceOSVersion</span></span>
* <span data-ttu-id="7f657-116">displayName</span><span class="sxs-lookup"><span data-stu-id="7f657-116">displayName</span></span>

> [!NOTE]
> <span data-ttu-id="7f657-117">Em dispositivos Android:</span><span class="sxs-lookup"><span data-stu-id="7f657-117">On Android devices:</span></span>
  * <span data-ttu-id="7f657-118">É necessário que o aplicativo Portal da Empresa esteja instalado no dispositivo, mas o usuário final não precisa fazer logon no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7f657-118">It is required that the Company Portal app is installed on the device, but end-user is not required to log in into app.</span></span>
  * <span data-ttu-id="7f657-119">O registro do dispositivo deve ser feito por meio do aplicativo OneDrive ou Outlook.</span><span class="sxs-lookup"><span data-stu-id="7f657-119">Device registration must be done through the OneDrive or Outlook app.</span></span>

## <span data-ttu-id="7f657-120">Para remover um dispositivo do registro no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7f657-120">To remove a device from Azure AD registration.</span></span>
<a id="to-remove-a-device-from-azure-ad-registration" class="xliff"></a>
<span data-ttu-id="7f657-121">É possível remover o registro do dispositivo usando o console de administração do Azure AD, o que normalmente é feito pelo administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="7f657-121">You can remove the device registration either through the Azure AD admin console which is typically done by the IT admin.</span></span>  <span data-ttu-id="7f657-122">Isso também pode ser feito pelo usuário final no próprio dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7f657-122">It can also be done by the end-user on the device itself.</span></span>

* <span data-ttu-id="7f657-123">**Console de administração do Azure AD**: no console de administração do Azure AD**, exclua o dispositivo que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="7f657-123">**Azure AD admin console**: In the Azure AD admin console**, delete the device that you want to remove.</span></span>
* <span data-ttu-id="7f657-124">**Dispositivo iOS**: abra o aplicativo Microsoft Authenticator, passe o dedo para a esquerda na conta e escolha Cancelar registro.</span><span class="sxs-lookup"><span data-stu-id="7f657-124">**iOS device**: Open the Azure Authenticator app, swipe left on the account, and choose unregister.</span></span>  
* <span data-ttu-id="7f657-125">**Dispositivo Android**: desinstale o aplicativo do Portal da Empresa ou remova a conta das **Configurações do sistema**.</span><span class="sxs-lookup"><span data-stu-id="7f657-125">**Android device**: Uninstall the company portal app or remove the account from the **System settings**.</span></span>

## <span data-ttu-id="7f657-126">AC baseada em aplicativo com AC baseada em dispositivo</span><span class="sxs-lookup"><span data-stu-id="7f657-126">App-based CA with Device-based CA</span></span>
<a id="app-based-ca-with-device-based-ca" class="xliff"></a>  

<span data-ttu-id="7f657-127">Você pode configurar o [Acesso condicional baseado na conformidade do dispositivo](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**AC do Dispositivo**) no [console do administrador do Intune](https://manage.microsoft.com) ou no [console de gerenciamento do Azure AD Premium] (https://manage.windowsazure.com).</span><span class="sxs-lookup"><span data-stu-id="7f657-127">You can configure [Conditional access based on device compliance](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**Device CA**) on the [Intune administrator console](https://manage.microsoft.com) or the [Azure AD Premium management console] (https://manage.windowsazure.com).</span></span> <span data-ttu-id="7f657-128">O AC do dispositivo exige que os usuários se conectem ao Exchange Online somente por meio de dispositivos gerenciados pelo Intune que estejam em conformidade com a política de conformidade do dispositivo do Intune ou computadores de domínio associado.</span><span class="sxs-lookup"><span data-stu-id="7f657-128">Device CA require users to connect to Exchange Online only through Intune-managed  devices that are compliant with the Intune device compliance policy or domain-joined PCs.</span></span>  <span data-ttu-id="7f657-129">Se um usuário pertencer a um ou mais grupos de segurança destinados a políticas de AC baseado em aplicativo e de AC do dispositivo, o usuário deverá atender a um dos dois requisitos:</span><span class="sxs-lookup"><span data-stu-id="7f657-129">If a user belongs to one or more security groups that are targeted for both app-based CA and Device CA policies, the user must meet one of the two requirements:</span></span>
* <span data-ttu-id="7f657-130">O aplicativo usado para acessar o serviço é um aplicativo móvel com suporte</span><span class="sxs-lookup"><span data-stu-id="7f657-130">The app used to access the service is a mobile app that is supported by</span></span> 
* <span data-ttu-id="7f657-131">e o dispositivo no qual o aplicativo está sendo executado tem um **Autenticador iOS (para dispositivos iOS)** ou o **aplicativo do Portal da Empresa (para dispositivos Android)** instalado.</span><span class="sxs-lookup"><span data-stu-id="7f657-131">, and the device that the app is running on, has **iOS Authenticator (for iOS devices)**, or the **Company Portal app (for Android devices)** installed.</span></span>
* <span data-ttu-id="7f657-132">O dispositivo utilizado para acessar o serviço é **compatível e gerenciado pelo Intune** com a política de conformidade do dispositivo do Intune ou é um **computador de domínio associado**.</span><span class="sxs-lookup"><span data-stu-id="7f657-132">The device used to access the service is **Intune-managed and compliant** with the Intune device compliance policy, or it is a **domain-joined PC**.</span></span>  <span data-ttu-id="7f657-133">Aqui estão alguns exemplos para ajudar a ilustrar essa situação:</span><span class="sxs-lookup"><span data-stu-id="7f657-133">Here are some examples to help illustrate this:</span></span>
  * <span data-ttu-id="7f657-134">Se um usuário tentar se conectar por meio do **aplicativo de email nativo do iOS**, ele deverá usar um **dispositivo gerenciado e em conformidade**, pois não há suporte do AC baseado em aplicativo para o aplicativo de email nativo.</span><span class="sxs-lookup"><span data-stu-id="7f657-134">If a user tries to connect from the **native iOS email app**, he or she will be required to be on a **managed and compliant device** since the native mail app is not supported by app-based CA.</span></span>
  * <span data-ttu-id="7f657-135">Se um usuário tentar se conectar por meio de um **computador doméstico Windows**, a **política de AC do dispositivo** será aplicada, exigindo que o usuário use um computador de domínio associado.</span><span class="sxs-lookup"><span data-stu-id="7f657-135">If a user tries to connect from a **Windows home PC**, the **Device CA policy** will apply, requiring that the he or she must use a domain-joined PC.</span></span>

## <span data-ttu-id="7f657-136">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7f657-136">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="7f657-137">Criar uma política do Exchange Online para aplicativos MAM</span><span class="sxs-lookup"><span data-stu-id="7f657-137">Create an Exchange Online Policy for MAM apps</span></span>](mam-ca-for-exchange-online.md)

[<span data-ttu-id="7f657-138">Bloquear aplicativos que não têm autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="7f657-138">Block apps that do not have modern authentication</span></span>](block-apps-with-no-modern-authentication.md)

### <span data-ttu-id="7f657-139">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7f657-139">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="7f657-140">Proteger dados de aplicativo com as políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="7f657-140">Protect app data with app protection policies</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
