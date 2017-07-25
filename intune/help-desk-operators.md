---
title: "Portal de solução de problemas de suporte técnico"
titleSuffix: Intune on Azure
description: "A equipe de suporte técnico usa o portal de solução de problemas para resolver problemas técnicos dos usuários"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 7a61c3703cd1016ef63c8baa371c3a21dca127fc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="6837a-103">Ajudar os usuários com o portal de solução de problemas no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6837a-103">Help users with the Troubleshooting portal in Microsoft Intune</span></span>
=======
# Ajudar os usuários com o portal de solução de problemas no Microsoft Intune
>>>>>>> live
<a id="help-users-with-the-troubleshooting-portal-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
<span data-ttu-id="6837a-104">O portal de solução de problemas permite que os operadores de suporte técnico e os administradores do Intune exibam informações do usuário para resolver solicitações de ajuda do usuário.</span><span class="sxs-lookup"><span data-stu-id="6837a-104">The troubleshooting portal lets help desk operators and Intune administrators view user information to fix user help requests.</span></span> <span data-ttu-id="6837a-105">As organizações que incluem operadores de suporte técnico em sua equipe podem atribuir o **Operador do suporte técnico** a um grupo de usuários, o qual poderá usar a folha Solução de Problemas para ajudar os usuários.</span><span class="sxs-lookup"><span data-stu-id="6837a-105">Organizations that include help desk operators in their staff can assign the **Help desk operator** to a group of users, who can then use the Troubleshoot blade to help users.</span></span>

<span data-ttu-id="6837a-106">Por exemplo, quando um usuário contata o suporte com um problema técnico com o Intune, o operador do suporte técnico digita o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="6837a-106">For example, when a user contacts support with a technical issue with Intune, the help desk operator enters the user's name.</span></span> <span data-ttu-id="6837a-107">O Intune exibe informações pertinentes que podem ajudar a resolver muitos problemas de nível 1, como status do usuário, falha de instalação do aplicativo ou problemas de conformidade.</span><span class="sxs-lookup"><span data-stu-id="6837a-107">Intune displays pertinent information that can help resolve many tier-1 issues such as user status, app installation failure, or compliance issues.</span></span> <span data-ttu-id="6837a-108">Os problemas tratados podem incluir:</span><span class="sxs-lookup"><span data-stu-id="6837a-108">Issues addressed can include:</span></span>
- <span data-ttu-id="6837a-109">O dispositivo não está respondendo</span><span class="sxs-lookup"><span data-stu-id="6837a-109">Device not responding</span></span>
-   <span data-ttu-id="6837a-110">O dispositivo não consegue obter configurações de VPN ou Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6837a-110">Device not getting VPN or Wi-Fi settings</span></span>
-   <span data-ttu-id="6837a-111">Falha na instalação do aplicativo</span><span class="sxs-lookup"><span data-stu-id="6837a-111">App installation failure</span></span>


## <span data-ttu-id="6837a-112">Adicionar operadores de suporte técnico</span><span class="sxs-lookup"><span data-stu-id="6837a-112">Add help desk operators</span></span>
<a id="add-help-desk-operators" class="xliff"></a>
<span data-ttu-id="6837a-113">Um administrador do Intune pode atribuir a permissão de operador de suporte técnico para os usuários de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="6837a-113">An Intune administrator can assign help desk operator permission to users in two ways:</span></span>
- <span data-ttu-id="6837a-114">Atribuir a função **Operador do suporte técnico** interna</span><span class="sxs-lookup"><span data-stu-id="6837a-114">Assign the built-in **Help Desk Operator** role</span></span>
- <span data-ttu-id="6837a-115">Criar e atribuir uma função personalizada</span><span class="sxs-lookup"><span data-stu-id="6837a-115">Create and assign a custom role</span></span>

## <span data-ttu-id="6837a-116">Atribuir função de operador de suporte técnico</span><span class="sxs-lookup"><span data-stu-id="6837a-116">Assign help desk operator role</span></span>
<a id="assign-help-desk-operator-role" class="xliff"></a>
<span data-ttu-id="6837a-117">Como um administrador do Intune, você pode atribuir a função de Operador de suporte técnico para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="6837a-117">As an Intune admin, you can assign the Help Desk Operator role to a user group.</span></span> <span data-ttu-id="6837a-118">Membros desse grupo podem usar o portal de administração.</span><span class="sxs-lookup"><span data-stu-id="6837a-118">Members of that group can use the admin portal.</span></span> <span data-ttu-id="6837a-119">Cada operador de suporte técnico deve ter uma licença do Intune para acessar o Portal do Intune.</span><span class="sxs-lookup"><span data-stu-id="6837a-119">Each help desk operator must have an Intune license to access the Intune portal.</span></span> <span data-ttu-id="6837a-120">Saiba como [atribuir licenças do Intune](licenses-assign.md).</span><span class="sxs-lookup"><span data-stu-id="6837a-120">Learn how to [assign Intune licenses](licenses-assign.md).</span></span>

1. <span data-ttu-id="6837a-121">Como administrador do Intune, faça logon no Portal do Intune e selecione **Funções do Intune**.</span><span class="sxs-lookup"><span data-stu-id="6837a-121">As an Intune administrator, login to Intune portal, and select **Intune roles**.</span></span>
2. <span data-ttu-id="6837a-122">Na carga de trabalho **Funções do Intune**, selecione **Operador de Suporte Técnico** > **Atribuições** e selecione **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="6837a-122">On the **Intune roles** workload, select **Help Desk Operator** > **Assignments**, and then select **Assign**.</span></span>
  <span data-ttu-id="6837a-123">![Captura de tela do Portal do Intune que mostra as funções do Intune realçadas e uma lista de funções internas, incluindo Operador de suporte técnico, com Atribuições realçado e uma caixa vermelha ao redor de Atribuir](./media/help-desk-user-assign.png)</span><span class="sxs-lookup"><span data-stu-id="6837a-123">![Screenshot of Intune portal showing the Intune roles highlighted and a list of built-in roles including Help Desk Operator with Assignments highlighted and a red box around Assign](./media/help-desk-user-assign.png)</span></span>
3. <span data-ttu-id="6837a-124">Digite um **Nome de atribuição** (obrigatório), uma **Descrição da atribuição** (opcional) e atribua **Membros (Grupos)** e **Escopo (Grupos)**.</span><span class="sxs-lookup"><span data-stu-id="6837a-124">Type an **Assignment name** (required), an **Assignment description** (optional), and then assign **Members (Groups)** and **Scope (Groups)**.</span></span>
4. <span data-ttu-id="6837a-125">Os membros da função Operador de Suporte Técnico agora podem usar o portal de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="6837a-125">Members of the Help Desk Operator role can now use the troubleshooting portal.</span></span>

<span data-ttu-id="6837a-126">Para saber mais sobre as funções do Intune, confira [Funções do Intune (RBAC)](role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="6837a-126">For more information about Intune roles, see [Intune roles (RBAC)](role-based-access-control.md).</span></span>

## <span data-ttu-id="6837a-127">Criar uma função personalizada para solução de problemas</span><span class="sxs-lookup"><span data-stu-id="6837a-127">Create a custom role for troubleshooting</span></span>
<a id="create-a-custom-role-for-troubleshooting" class="xliff"></a>
<span data-ttu-id="6837a-128">Como um administrador do Intune, você pode criar uma função personalizada que permite aos usuários a usar o portal de solução de problemas com permissões adequadas para as necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6837a-128">As an Intune admin, you can create a custom role that lets users use the troubleshooting portal with permissions that suit your organization's needs.</span></span> <span data-ttu-id="6837a-129">Para saber mais sobre as funções do Intune, confira [Funções do Intune (RBAC)](role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="6837a-129">For more information about Intune roles, see [Intune roles (RBAC)](role-based-access-control.md).</span></span>

![Captura de tela do Portal do Intune que mostra as funções do Intune realçadas e uma lista de funções internas, incluindo Operador de suporte técnico](./media/help-desk-user-add.png)

<span data-ttu-id="6837a-131">Para usar o console do Intune para uma exibição de suporte técnico, uma função de suporte técnico personalizada deve ter as seguintes permissões:</span><span class="sxs-lookup"><span data-stu-id="6837a-131">To use the Intune console for a help-desk view, a custom help desk role should have the following permissions:</span></span>
- <span data-ttu-id="6837a-132">MobileApps: leitura</span><span class="sxs-lookup"><span data-stu-id="6837a-132">MobileApps: Read</span></span>
- <span data-ttu-id="6837a-133">ManagedApps: leitura</span><span class="sxs-lookup"><span data-stu-id="6837a-133">ManagedApps: Read</span></span>
- <span data-ttu-id="6837a-134">ManagedDevices: leitura</span><span class="sxs-lookup"><span data-stu-id="6837a-134">ManagedDevices: Read</span></span>
- <span data-ttu-id="6837a-135">Organization: leitura</span><span class="sxs-lookup"><span data-stu-id="6837a-135">Organization: Read</span></span>

## <span data-ttu-id="6837a-136">Acessar o portal de solução de problemas</span><span class="sxs-lookup"><span data-stu-id="6837a-136">Access the troubleshooting portal</span></span>
<a id="access-the-troubleshooting-portal" class="xliff"></a>

<span data-ttu-id="6837a-137">A equipe de suporte técnico e os administradores do Intune podem acessar o portal de solução de problemas de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="6837a-137">Help desk staff and Intune administrators can access the troubleshooting portal in two ways:</span></span>
- <span data-ttu-id="6837a-138">Abra [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) em um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="6837a-138">Open [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) in a web browser.</span></span>
- <span data-ttu-id="6837a-139">No Portal do Intune, acesse **Ajuda e Suporte** > **Solucionar Problemas**.</span><span class="sxs-lookup"><span data-stu-id="6837a-139">In the Intune portal, go **Help and Support** > **Troubleshoot**.</span></span>

![Captura de tela da carga de trabalho de solução de problemas do Microsoft Intune com o link Selecionar Usuário](media/help-desk-user.png)

## <span data-ttu-id="6837a-141">Usar o portal de solução de problemas</span><span class="sxs-lookup"><span data-stu-id="6837a-141">Use the troubleshooting portal</span></span>
<a id="use-the-troubleshooting-portal" class="xliff"></a>

<span data-ttu-id="6837a-142">No portal de solução de problemas, escolha **Selecionar Usuário** para exibir as informações dos usuários.</span><span class="sxs-lookup"><span data-stu-id="6837a-142">In the troubleshooting portal, you can choose **Select user** to view a users' information.</span></span> <span data-ttu-id="6837a-143">As informações do usuário podem ajudar você a entender o estado atual dos usuários e seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6837a-143">User information can help you understand the current state of users and their devices.</span></span> <span data-ttu-id="6837a-144">O portal de solução de problemas mostra os seguintes detalhes de solução de problemas:</span><span class="sxs-lookup"><span data-stu-id="6837a-144">The troubleshooting portal shows the following troubleshooting details:</span></span>
- <span data-ttu-id="6837a-145">**Status do locatário**</span><span class="sxs-lookup"><span data-stu-id="6837a-145">**Tenant status**</span></span>
- <span data-ttu-id="6837a-146">**Status do usuário**</span><span class="sxs-lookup"><span data-stu-id="6837a-146">**User status**</span></span>
- <span data-ttu-id="6837a-147">**Dispositivos** e ações de dispositivo</span><span class="sxs-lookup"><span data-stu-id="6837a-147">**Devices** and device actions</span></span>
- <span data-ttu-id="6837a-148">**Associação a um grupo**</span><span class="sxs-lookup"><span data-stu-id="6837a-148">**Group membership**</span></span>
- <span data-ttu-id="6837a-149">**Status de proteção de aplicativo**</span><span class="sxs-lookup"><span data-stu-id="6837a-149">**App protection status**</span></span>
=======
O portal de solução de problemas permite que os operadores de suporte técnico e os administradores do Intune exibam informações do usuário para resolver solicitações de ajuda do usuário. As organizações que incluem operadores de suporte técnico em sua equipe podem atribuir o **Operador do suporte técnico** a um grupo de usuários, o qual poderá usar a folha Solução de Problemas para ajudar os usuários.

Por exemplo, quando um usuário contata o suporte com um problema técnico com o Intune, o operador do suporte técnico digita o nome do usuário. O Intune exibe informações pertinentes que podem ajudar a resolver muitos problemas de nível 1, como status do usuário, falha de instalação do aplicativo ou problemas de conformidade. Os problemas tratados podem incluir:
- O dispositivo não está respondendo
-   O dispositivo não consegue obter configurações de VPN ou Wi-Fi
-   Falha na instalação do aplicativo


## Adicionar operadores de suporte técnico
<a id="add-help-desk-operators" class="xliff"></a>
Um administrador do Intune pode atribuir a permissão de operador de suporte técnico para os usuários de duas maneiras:
- Atribuir a função **Operador do suporte técnico** interna
- Criar e atribuir uma função personalizada

## Atribuir função de operador de suporte técnico
<a id="assign-help-desk-operator-role" class="xliff"></a>
Como um administrador do Intune, você pode atribuir a função de Operador de suporte técnico para um grupo de usuários. Membros desse grupo podem usar o portal de administração. Cada operador de suporte técnico deve ter uma licença do Intune para acessar o Portal do Intune. Saiba como [atribuir licenças do Intune](licenses-assign.md).

1. Como administrador do Intune, faça logon no Portal do Intune e selecione **Funções do Intune**.
2. Na carga de trabalho **Funções do Intune**, selecione **Operador de Suporte Técnico** > **Atribuições** e selecione **Atribuir**.
  ![Captura de tela do Portal do Intune que mostra as funções do Intune realçadas e uma lista de funções internas, incluindo Operador de suporte técnico, com Atribuições realçado e uma caixa vermelha ao redor de Atribuir](./media/help-desk-user-assign.png)
3. Digite um **Nome de atribuição** (obrigatório), uma **Descrição da atribuição** (opcional) e atribua **Membros (Grupos)** e **Escopo (Grupos)**.
4. Os membros da função Operador de Suporte Técnico agora podem usar o portal de solução de problemas.

Para saber mais sobre as funções do Intune, confira [Funções do Intune (RBAC)](role-based-access-control.md).

## Criar uma função personalizada para solução de problemas
<a id="create-a-custom-role-for-troubleshooting" class="xliff"></a>
Como um administrador do Intune, você pode criar uma função personalizada que permite aos usuários a usar o portal de solução de problemas com permissões adequadas para as necessidades da sua organização. Para saber mais sobre as funções do Intune, confira [Funções do Intune (RBAC)](role-based-access-control.md).

![Captura de tela do Portal do Intune que mostra as funções do Intune realçadas e uma lista de funções internas, incluindo Operador de suporte técnico](./media/help-desk-user-add.png)

Para usar o console do Intune para uma exibição de suporte técnico, uma função de suporte técnico personalizada deve ter as seguintes permissões:
- MobileApps: leitura
- ManagedApps: leitura
- ManagedDevices: leitura
- Organization: leitura

## Acessar o portal de solução de problemas
<a id="access-the-troubleshooting-portal" class="xliff"></a>

A equipe de suporte técnico e os administradores do Intune podem acessar o portal de solução de problemas de duas maneiras:
- Abra [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) em um navegador da Web.
- No Portal do Intune, acesse **Ajuda e Suporte** > **Solucionar Problemas**.

![Captura de tela da carga de trabalho de solução de problemas do Microsoft Intune com o link Selecionar Usuário](media/help-desk-user.png)

## Usar o portal de solução de problemas
<a id="use-the-troubleshooting-portal" class="xliff"></a>

No portal de solução de problemas, escolha **Selecionar Usuário** para exibir as informações dos usuários. As informações do usuário podem ajudar você a entender o estado atual dos usuários e seus dispositivos. O portal de solução de problemas mostra os seguintes detalhes de solução de problemas:
- **Status do locatário**
- **Status do usuário**
- **Dispositivos** e ações de dispositivo
- **Associação a um grupo**
- **Status de proteção de aplicativo**
>>>>>>> live
