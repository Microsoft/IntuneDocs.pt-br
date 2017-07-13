---
title: "Dicas de solução de problemas gerais"
description: Recursos gerais para ajudar a resolver problemas com o Intune.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d348cc2850864206552bf53ab1beec9b9cb55bab
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="d47f0-103">Dicas de solução de problemas gerais para o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d47f0-103">General troubleshooting tips for Microsoft Intune</span></span>
<a id="general-troubleshooting-tips-for-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="d47f0-104">Após implantar o Microsoft Intune, você poderá ter problemas com a configuração ou com os dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="d47f0-104">After you deploy Microsoft Intune, you might encounter problems with your configuration or with client devices.</span></span> <span data-ttu-id="d47f0-105">Use os seguintes recursos para descobrir o que está causando o problema e resolvê-lo.</span><span class="sxs-lookup"><span data-stu-id="d47f0-105">Use the following resources to help you discover what's causing the problem so you can resolve it.</span></span>

> [!NOTE]
> <span data-ttu-id="d47f0-106">Para criar uma solicitação de suporte ou para exibir uma solicitação, [visite o Centro de administração do Office 365](https://portal.office.com/admin/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="d47f0-106">To create a support request, or to view an existing request, [visit the Office 365 admin center](https://portal.office.com/admin/default.aspx).</span></span> <span data-ttu-id="d47f0-107">Para obter mais informações sobre opções de suporte, consulte [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="d47f0-107">For more information about support options, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>

## <span data-ttu-id="d47f0-108">Definir o problema</span><span class="sxs-lookup"><span data-stu-id="d47f0-108">Define the problem</span></span>
<a id="define-the-problem" class="xliff"></a>

-   <span data-ttu-id="d47f0-109">Qual é o comportamento?</span><span class="sxs-lookup"><span data-stu-id="d47f0-109">What is the behavior?</span></span>

-   <span data-ttu-id="d47f0-110">Quem passa por esse comportamento e em quais plataformas e dispositivos?</span><span class="sxs-lookup"><span data-stu-id="d47f0-110">Who experiences this behavior, and on what platforms and devices?</span></span>

-   <span data-ttu-id="d47f0-111">O dispositivo funcionou corretamente anteriormente?</span><span class="sxs-lookup"><span data-stu-id="d47f0-111">Did the device work properly previously?</span></span>

-   <span data-ttu-id="d47f0-112">Quais alterações você fez no Intune ou na configuração do dispositivo?</span><span class="sxs-lookup"><span data-stu-id="d47f0-112">What changes did you make to the Intune or device configuration?</span></span>

-   <span data-ttu-id="d47f0-113">Outras alterações foram feitas ao ambiente no qual você opera, em vez de alterações de configuração?</span><span class="sxs-lookup"><span data-stu-id="d47f0-113">Were other changes were made to the environment in which you operate, other than configuration changes?</span></span>

-   <span data-ttu-id="d47f0-114">Com qual frequência esse problema ocorre? É esporádicas ou consistente?</span><span class="sxs-lookup"><span data-stu-id="d47f0-114">How frequently does this problem occur, and is it sporadic or consistent?</span></span>

-   <span data-ttu-id="d47f0-115">O usuário poderia estar enfrentando um problema de autenticação?</span><span class="sxs-lookup"><span data-stu-id="d47f0-115">Could the user be experiencing an authentication issue?</span></span> <span data-ttu-id="d47f0-116">Se essa for uma possibilidade, verifique se o usuário pode entrar em outros serviços que usam o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d47f0-116">If this is a possiblity, see if the user can sign in to other services that use Azure Active Directory.</span></span> <span data-ttu-id="d47f0-117">Verifique também se o usuário pode entrar em um dispositivo diferente.</span><span class="sxs-lookup"><span data-stu-id="d47f0-117">Also, see if the user can sign in from a different device.</span></span>

-   <span data-ttu-id="d47f0-118">Você verificou o status do serviço?</span><span class="sxs-lookup"><span data-stu-id="d47f0-118">Have you checked the service status?</span></span> <span data-ttu-id="d47f0-119">Você pode monitorar a integridade do serviço Intune no [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx).</span><span class="sxs-lookup"><span data-stu-id="d47f0-119">You can monitor Intune service health in the [Office 365 management portal](https://portal.office.com/Admin/Default.aspx).</span></span> <span data-ttu-id="d47f0-120">Escolha **Integridade do Serviço** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="d47f0-120">Choose **Service Health** in the left pane.</span></span>

## <span data-ttu-id="d47f0-121">Coletar dados disponíveis</span><span class="sxs-lookup"><span data-stu-id="d47f0-121">Collect available data</span></span>
<a id="collect-available-data" class="xliff"></a>

-   <span data-ttu-id="d47f0-122">Os recursos a seguir podem ajudá-lo a aprender a coletar logs de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="d47f0-122">The following resources can help you learn how to collect device logs:</span></span>
  - [<span data-ttu-id="d47f0-123">Enviar logs de dados de diagnóstico do Android para o administrador de TI usando um cabo USB</span><span class="sxs-lookup"><span data-stu-id="d47f0-123">Send Android diagnostic data logs to your IT administrator using a USB cable</span></span>](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [<span data-ttu-id="d47f0-124">Enviar logs de dados de diagnóstico do Android para o administrador de TI usando o email</span><span class="sxs-lookup"><span data-stu-id="d47f0-124">Send Android diagnostic data logs to your IT administrator using email</span></span>](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [<span data-ttu-id="d47f0-125">Enviar erros de registro do Android para o administrador de TI</span><span class="sxs-lookup"><span data-stu-id="d47f0-125">Send Android enrollment errors to your IT administrator</span></span>](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)
  - [<span data-ttu-id="d47f0-126">Enviar erros de registro do iOS para o administrador de TI</span><span class="sxs-lookup"><span data-stu-id="d47f0-126">Send iOS enrollment errors to your IT administrator</span></span>](/intune-user-help/send-errors-to-your-it-admin-ios)

-   <span data-ttu-id="d47f0-127">Com os dados de console de administração (por exemplo, para problemas de implementação de política), examine a política desejada e o status dessa política, conforme descrito em [Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="d47f0-127">With admin console data (for example, for policy implementation issues), examine the intended policy and the status of that policy, as described in [Use groups to manage users and devices with Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).</span></span>

## <span data-ttu-id="d47f0-128">Pesquisar a solução</span><span class="sxs-lookup"><span data-stu-id="d47f0-128">Research the solution</span></span>
<a id="research-the-solution" class="xliff"></a>

-   <span data-ttu-id="d47f0-129">Pesquise uma solução na Web.</span><span class="sxs-lookup"><span data-stu-id="d47f0-129">Search the Web for a solution.</span></span> <span data-ttu-id="d47f0-130">Por exemplo, se você receber o erro 0x80073CF0, pesquise por **technet intune 0x80073cf0** na Web e localize o artigo [Solucionar problemas de implantação de aplicativo no Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="d47f0-130">For example, if you receive the error 0x80073CF0, search for **technet intune 0x80073cf0** on the Web, and you'll find the article [Troubleshoot app deployment problems in Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md).</span></span> <span data-ttu-id="d47f0-131">Esse artigo oferece sugestões para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="d47f0-131">This article offers suggestions for addressing this error.</span></span>

-   <span data-ttu-id="d47f0-132">Pesquise uma resposta no [Fórum TechNet do Intune](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).</span><span class="sxs-lookup"><span data-stu-id="d47f0-132">Search for an answer in the [Intune TechNet forum](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).</span></span>  <span data-ttu-id="d47f0-133">Se o problema não tiver sido resolvido anteriormente, poste a pergunta para ver quais sugestões a comunidade pode dar.</span><span class="sxs-lookup"><span data-stu-id="d47f0-133">If the issue hasn't been previously addressed, post the question to see what suggestions the community might have.</span></span>

-   <span data-ttu-id="d47f0-134">Abrir uma solicitação de suporte.</span><span class="sxs-lookup"><span data-stu-id="d47f0-134">Open a support request.</span></span> <span data-ttu-id="d47f0-135">O Suporte do Intune estará mais capacitado para ajudá-lo a resolver um problema quando você o tiver definido e coletado os dados disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d47f0-135">Intune Support will be better able to help you resolve an issue after you've defined the problem and have collected the available data.</span></span>

    <span data-ttu-id="d47f0-136">Para criar uma solicitação de suporte [visite o centro de administração do Office 365](https://portal.office.com/admin/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="d47f0-136">To create a support request, [visit the Office 365 admin center](https://portal.office.com/admin/default.aspx).</span></span> <span data-ttu-id="d47f0-137">Para obter mais informações sobre opções de suporte, consulte [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="d47f0-137">For more information about support options, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>

## <span data-ttu-id="d47f0-138">Encontre os recursos da comunidade</span><span class="sxs-lookup"><span data-stu-id="d47f0-138">Find community resources</span></span>
<a id="find-community-resources" class="xliff"></a>
<span data-ttu-id="d47f0-139">Você pode encontrar outras informações úteis nestes recursos da comunidade:</span><span class="sxs-lookup"><span data-stu-id="d47f0-139">You can find other helpful information in these community resources:</span></span>

-   <span data-ttu-id="d47f0-140">O [Guia de Sobrevivência do Microsoft Intune](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) contém links para vários recursos que podem ajudá-lo a configurar, manter e solucionar problemas do Intune.</span><span class="sxs-lookup"><span data-stu-id="d47f0-140">The [Microsoft Intune Survival Guide](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) contains links to many resources that can help you configure, maintain, and troubleshoot Intune.</span></span>

-   [<span data-ttu-id="d47f0-141">O blog do Intune</span><span class="sxs-lookup"><span data-stu-id="d47f0-141">The Intune blog</span></span>](http://blogs.technet.com/b/windowsintune/)

-   [<span data-ttu-id="d47f0-142">Siga o Intune no Twitter</span><span class="sxs-lookup"><span data-stu-id="d47f0-142">Follow Intune on Twitter</span></span>](https://twitter.com/MSIntune)

-   [<span data-ttu-id="d47f0-143">Os fóruns do Intune</span><span class="sxs-lookup"><span data-stu-id="d47f0-143">The Intune forums</span></span>](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### <span data-ttu-id="d47f0-144">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d47f0-144">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="d47f0-145">Os tópicos listados abaixo contêm soluções de problemas específicos.</span><span class="sxs-lookup"><span data-stu-id="d47f0-145">The following topics have troubleshooting help for specific issues.</span></span> <span data-ttu-id="d47f0-146">Se essas informações não ajudarem, contate o Suporte da Microsoft conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="d47f0-146">If that information doesn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>

[<span data-ttu-id="d47f0-147">Solucionar problemas do Endpoint Protection no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d47f0-147">Troubleshoot Endpoint Protection in Microsoft Intune</span></span>](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[<span data-ttu-id="d47f0-148">Solucionar problemas de acesso ao recurso da empresa com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d47f0-148">Troubleshoot company resource access problems with Microsoft Intune</span></span>](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[<span data-ttu-id="d47f0-149">Solucionar problemas de implantação de aplicativo no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d47f0-149">Troubleshoot app deployment problems in Microsoft Intune</span></span>](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[<span data-ttu-id="d47f0-150">Solucionar problemas de registro de dispositivo no Intune</span><span class="sxs-lookup"><span data-stu-id="d47f0-150">Troubleshoot device enrollment in Intune</span></span>](troubleshoot-device-enrollment-in-intune.md)

[<span data-ttu-id="d47f0-151">Solucionar problemas com políticas no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d47f0-151">Troubleshoot policies in Microsoft Intune</span></span>](troubleshoot-policies-in-microsoft-intune.md)

[<span data-ttu-id="d47f0-152">Solucionar problemas de instalação do cliente no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d47f0-152">Troubleshoot client setup in Microsoft Intune</span></span>](troubleshoot-client-setup-in-microsoft-intune.md)

[<span data-ttu-id="d47f0-153">Solucionar problemas de atualização de software no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d47f0-153">Troubleshoot software updates in Microsoft Intune</span></span>](troubleshoot-software-updates-in-microsoft-intune.md)
