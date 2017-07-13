---
title: "Solucionar problemas de políticas"
description: "Solucione problemas de configuração de política."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 00f3487ed7f9fe920d89f449703723bfe80eb109
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="46aff-103">Solução de problemas com políticas no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="46aff-103">Troubleshoot policies in Microsoft Intune</span></span>
<a id="troubleshoot-policies-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="46aff-104">Se você estiver tendo problemas ao implantar e gerenciar políticas do Intune, comece aqui.</span><span class="sxs-lookup"><span data-stu-id="46aff-104">If you are having problems deploying and managing Intune policies, start here.</span></span> <span data-ttu-id="46aff-105">Este tópico contém alguns problemas comuns que podem ocorrer, juntamente com as soluções.</span><span class="sxs-lookup"><span data-stu-id="46aff-105">This topic contains some common problems you might encounter together with solutions.</span></span>

## <span data-ttu-id="46aff-106">Problemas gerais</span><span class="sxs-lookup"><span data-stu-id="46aff-106">General Issues</span></span>
<a id="general-issues" class="xliff"></a>

### <span data-ttu-id="46aff-107">Uma política implantada foi aplicada ao dispositivo?</span><span class="sxs-lookup"><span data-stu-id="46aff-107">Was a deployed policy applied to the device?</span></span>
<a id="was-a-deployed-policy-applied-to-the-device" class="xliff"></a>
<span data-ttu-id="46aff-108">**Problema:** você não tem certeza se uma política foi aplicada corretamente.</span><span class="sxs-lookup"><span data-stu-id="46aff-108">**Issue:** You are unsure if a policy was correctly applied.</span></span>

<span data-ttu-id="46aff-109">No console de administração do Intune, cada dispositivo tem uma guia de política em **Propriedades do Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="46aff-109">In the Intune admin console every device has a policy tab under **Device Properties**.</span></span> <span data-ttu-id="46aff-110">Cada política tem um **Valor Pretendido** e um **Status**.</span><span class="sxs-lookup"><span data-stu-id="46aff-110">Each policy has an **Intended Value** and a **Status**.</span></span> <span data-ttu-id="46aff-111">O valor pretendido é o que você quis realizar ao atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="46aff-111">The intended value is what you meant to achieve when assigning the policy.</span></span> <span data-ttu-id="46aff-112">O status é o que realmente é aplicado quando todas as politicas que se aplicam ao dispositivo, bem como as restrições e requisitos de hardware e sistema operacional, são consideradas em conjunto.</span><span class="sxs-lookup"><span data-stu-id="46aff-112">The status is what is actually applied when all of the policies that apply to the device, as well as the restrictions and requirements of the hardware and the operating system, are considered together.</span></span> <span data-ttu-id="46aff-113">Os status possíveis são:</span><span class="sxs-lookup"><span data-stu-id="46aff-113">Possible statuses are:</span></span>

-   <span data-ttu-id="46aff-114">**Conformidade**: o dispositivo recebeu a política e relatórios do serviço de que está de acordo com a configuração.</span><span class="sxs-lookup"><span data-stu-id="46aff-114">**Conforms**: the device has received the policy and reports to the service that it  conforms to the setting.</span></span>

-   <span data-ttu-id="46aff-115">**Não aplicável**: a configuração de política não é aplicável.</span><span class="sxs-lookup"><span data-stu-id="46aff-115">**Not applicable**: The policy setting is not applicable.</span></span> <span data-ttu-id="46aff-116">Por exemplo, configurações de email para dispositivos iOS não se aplicariam a um dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="46aff-116">For example,  email settings for iOS devices would not apply to an Android device.</span></span>

-   <span data-ttu-id="46aff-117">**Pendente**: a política foi enviada para o dispositivo, mas não relatou seu status para o serviço.</span><span class="sxs-lookup"><span data-stu-id="46aff-117">**Pending**: The policy was sent to the device, but hasn't reported status to the service.</span></span> <span data-ttu-id="46aff-118">Por exemplo, a criptografia no Android exige que o usuário habilite a criptografia e, portanto, pode estar pendente.</span><span class="sxs-lookup"><span data-stu-id="46aff-118">For example, encryption on Android requires the user to enable encryption and might therefore be pending.</span></span>

<span data-ttu-id="46aff-119">Na captura de tela abaixo, você pode ver dois exemplos claros:</span><span class="sxs-lookup"><span data-stu-id="46aff-119">In the screenshot below you can see two clear examples:</span></span>

-   <span data-ttu-id="46aff-120">**Permitir senhas simples** é definido como **Sim**, conforme mostrado na coluna **Valor Pretendido**, mas o **Status** é **Não aplicável**.</span><span class="sxs-lookup"><span data-stu-id="46aff-120">**Allow simple passwords** is set to **Yes**, as shown in the **Intended Value** column, but its **Status** is **Not applicable**.</span></span> <span data-ttu-id="46aff-121">Isso ocorre porque senhas simples não têm suporte para dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="46aff-121">This is because simple passwords are not supported for Android devices.</span></span>

-   <span data-ttu-id="46aff-122">Da mesma forma, o item de política expandido **Configurações de email para dispositivos iOS** não é aplicado a esse dispositivo, pois se trata de um dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="46aff-122">Similarly, the expanded policy item **Email settings for iOS devices** is not applied to this device, as it is an Android device.</span></span>

![Política de dispositivo Intune](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> <span data-ttu-id="46aff-124">Lembre-se de que, quando duas políticas com diferentes níveis de restrição aplicam-se ao mesmo dispositivo ou usuário, a política mais restritiva se aplica na prática.</span><span class="sxs-lookup"><span data-stu-id="46aff-124">Remember that when two policies with different levels of restriction apply to the same device or user, the more restrictive policy applies in practice.</span></span>


## <span data-ttu-id="46aff-125">Problemas com dispositivos registrados</span><span class="sxs-lookup"><span data-stu-id="46aff-125">Issues with enrolled devices</span></span>
<a id="issues-with-enrolled-devices" class="xliff"></a>

### <span data-ttu-id="46aff-126">Alerta: falha ao salvar regras de acesso ao Exchange</span><span class="sxs-lookup"><span data-stu-id="46aff-126">Alert: Saving of Access Rules to Exchange has Failed</span></span>
<a id="alert-saving-of-access-rules-to-exchange-has-failed" class="xliff"></a>
<span data-ttu-id="46aff-127">**Problema**: você recebe o alerta **Falha ao salvar as regras de acesso ao Exchange** no console do administrador.</span><span class="sxs-lookup"><span data-stu-id="46aff-127">**Issue**: You receive the alert **Saving of Access Rules to Exchange has Failed**  in the admin console.</span></span>

<span data-ttu-id="46aff-128">Se você criou as políticas no espaço de trabalho de Políticas do Exchange local, no Console de administração, mas estiver usando o O365, as configurações definidas para a política não serão impostas pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="46aff-128">If you  created policies in the Exchange On-Premises Policy workspace under the Admin Console but are using O365, the configured policy settings are not enforced by Intune.</span></span> <span data-ttu-id="46aff-129">Observe a origem da política no alerta.</span><span class="sxs-lookup"><span data-stu-id="46aff-129">Note the policy source from the alert.</span></span>  <span data-ttu-id="46aff-130">No espaço de trabalho de Política do Exchange local, exclua as regras herdadas, pois elas são regras globais do Exchange no Intune para o Exchange local e não são relevantes para o O365.</span><span class="sxs-lookup"><span data-stu-id="46aff-130">Under the Exchange On-premises Policy workspace delete the legacy rules, as these are Global Exchange rules within Intune for on-premises Exchange, and are not relevant to O365.</span></span> <span data-ttu-id="46aff-131">Em seguida, crie uma nova política para o O365.</span><span class="sxs-lookup"><span data-stu-id="46aff-131">Then, create new policy for O365.</span></span>

### <span data-ttu-id="46aff-132">Não é possível alterar a política de segurança para vários dispositivos registrados</span><span class="sxs-lookup"><span data-stu-id="46aff-132">Cannot change security policy for various enrolled devices</span></span>
<a id="cannot-change-security-policy-for-various-enrolled-devices" class="xliff"></a>
<span data-ttu-id="46aff-133">Dispositivos Windows Phone não permitem que políticas de segurança definidas por meio do MDM ou EAS sejam reduzidas em termos de segurança após terem sido configuradas.</span><span class="sxs-lookup"><span data-stu-id="46aff-133">Windows Phone devices do not allow security policies set via MDM or EAS to be reduced in security once you've set them.</span></span> <span data-ttu-id="46aff-134">Por exemplo, você define um **Número mínimo de caracteres de senha** para 8 e tenta reduzi-lo a 4.</span><span class="sxs-lookup"><span data-stu-id="46aff-134">For example, you set a **Minimum number of character password** to 8  then try to reduce it to 4.</span></span> <span data-ttu-id="46aff-135">A política mais restritiva já foi aplicada ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="46aff-135">The more restrictive policy has already been applied to the device.</span></span>

<span data-ttu-id="46aff-136">Dependendo da plataforma do dispositivo, se você quiser alterar a política para um valor menos seguro, pode ser necessário redefinir as políticas de segurança.</span><span class="sxs-lookup"><span data-stu-id="46aff-136">Depending on the device platform, if you want to change the policy  to a less secure value you may need to reset security policies.</span></span>
<span data-ttu-id="46aff-137">Por exemplo, no Windows, na área de trabalho, passe o dedo da direita para a esquerda para abrir a barra **Botões** e escolha **Configurações** &gt; **Painel de Controle**.</span><span class="sxs-lookup"><span data-stu-id="46aff-137">For example, in Windows,  on the desktop swipe in from right to open the **Charms** bar and choose  **Settings** &gt; **Control Panel**.</span></span>  <span data-ttu-id="46aff-138">Selecione o miniaplicativo **Contas de Usuário**.</span><span class="sxs-lookup"><span data-stu-id="46aff-138">Select the **User Accounts** applet.</span></span>
<span data-ttu-id="46aff-139">No menu de navegação à esquerda, há um link **Redefinir Políticas de Segurança** na parte inferior.</span><span class="sxs-lookup"><span data-stu-id="46aff-139">In the left hand navigation menu, there is a **Reset Security Policies** link at the bottom.</span></span> <span data-ttu-id="46aff-140">Escolha-o e clique no botão **Redefinir Políticas**.</span><span class="sxs-lookup"><span data-stu-id="46aff-140">Choose it and then choose the **Reset Policies** button.</span></span>
<span data-ttu-id="46aff-141">Outros dispositivos MDM, como Android, Windows Phone 8.1 e posterior e iOS, precisarão ser desativados e registrados novamente no serviço para que você possa aplicar uma política menos restritiva.</span><span class="sxs-lookup"><span data-stu-id="46aff-141">Other MDM devices, such as Android, Windows Phone 8.1 and later, and iOS, may need to be retired and re-enrolled back into the service for you to be able to apply a less restrictive policy.</span></span>

## <span data-ttu-id="46aff-142">Problemas com computadores que executam o cliente de software do Intune</span><span class="sxs-lookup"><span data-stu-id="46aff-142">Issues with PCs that run the Intune software client</span></span>
<a id="issues-with-pcs-that-run-the-intune-software-client" class="xliff"></a>

### <span data-ttu-id="46aff-143">Erros relacionados à política do Microsoft Intune em policyplatform.log</span><span class="sxs-lookup"><span data-stu-id="46aff-143">Microsoft Intune policy-related errors in policyplatform.log</span></span>
<a id="microsoft-intune-policy-related-errors-in-policyplatformlog" class="xliff"></a>
<span data-ttu-id="46aff-144">Para computadores com Windows gerenciados com o cliente de software do Intune, erros de política no arquivo policyplatform.log podem ser o resultado de configurações não padrão no UAC (Controle de Conta de Usuário) do Windows no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="46aff-144">For Windows PCs managed with the Intune software client, policy errors in the policyplatform.log file may be the result of non-default settings in the Windows User Account Control (UAC) on the device.</span></span> <span data-ttu-id="46aff-145">Algumas configurações de UAC não padrão podem afetar as instalações de cliente do Microsoft Intune e a execução da política.</span><span class="sxs-lookup"><span data-stu-id="46aff-145">Some non-default UAC settings can affect Microsoft Intune client installations and policy execution.</span></span>

#### <span data-ttu-id="46aff-146">Para resolver problemas do UAC</span><span class="sxs-lookup"><span data-stu-id="46aff-146">To resolve UAC issues</span></span>
<a id="to-resolve-uac-issues" class="xliff"></a>

1.  <span data-ttu-id="46aff-147">Desative o computador, conforme descrito em [Retire devices from Microsoft Intune management](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management) (Desativar dispositivos do gerenciamento do Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="46aff-147">Retire the computer, as described in [Retire devices from Microsoft Intune management](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).</span></span>

2.  <span data-ttu-id="46aff-148">Espere 20 minutos para o software cliente ser removido.</span><span class="sxs-lookup"><span data-stu-id="46aff-148">Wait 20 minutes for the client software to be removed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="46aff-149">Não tente remover o cliente em Programas e Recursos.</span><span class="sxs-lookup"><span data-stu-id="46aff-149">Do not attempt to remove the client from Programs and Features.</span></span>

3.  <span data-ttu-id="46aff-150">No menu Iniciar, digite **UAC** para abrir as configurações de Controle de Conta de Usuário.</span><span class="sxs-lookup"><span data-stu-id="46aff-150">On the start menu type **UAC** to open the User Account Control settings.</span></span>

4.  <span data-ttu-id="46aff-151">Mova o controle deslizante de notificação para a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="46aff-151">Move  the notification slider to the default setting.</span></span>

### <span data-ttu-id="46aff-152">ERRO: Não é possível obter o valor do computador, 0x80041013</span><span class="sxs-lookup"><span data-stu-id="46aff-152">ERROR: Cannot obtain the value from the computer, 0x80041013</span></span>
<a id="error-cannot-obtain-the-value-from-the-computer-0x80041013" class="xliff"></a>
<span data-ttu-id="46aff-153">Isso poderá ocorrer se a hora do sistema local estiver fora de sincronia por cinco minutos ou mais.</span><span class="sxs-lookup"><span data-stu-id="46aff-153">This can occur if the time on the local system is out of sync by five minutes or more.</span></span> <span data-ttu-id="46aff-154">Se a hora no computador local estiver fora de sincronia, transações seguras falharão porque os carimbos de data/hora serão inválidos.</span><span class="sxs-lookup"><span data-stu-id="46aff-154">If the time on the local computer is out of sync, secure transactions will fail because the time stamps will be invalid.</span></span>

<span data-ttu-id="46aff-155">Para resolver esse problema, defina a hora do sistema local o mais próximo possível do horário da Internet ou do horário definido nos controladores de domínio na rede.</span><span class="sxs-lookup"><span data-stu-id="46aff-155">To resolve this issue, set the local system time as close as possible to Internet time, or to the time set on the domain controllers on the network.</span></span>








### <span data-ttu-id="46aff-156">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="46aff-156">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="46aff-157">Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="46aff-157">If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>
