---
title: "Configurações de restrição de dispositivo do Intune para macOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações e as funcionalidades do dispositivo em dispositivos macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 716ca0a2041bdd2ecfadd180999a09f80373cb2a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="678ee-103">Configurações de restrição de dispositivo macOS no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="678ee-103">macOS device restriction settings in Microsoft Intune</span></span>
<a id="macos-device-restriction-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="678ee-104">Use essas configurações para gerenciar dispositivos macOS em um perfil de restrição de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="678ee-104">Use these settings to manage macOS devices in a device restriction profile.</span></span>

## <span data-ttu-id="678ee-105">Senha</span><span class="sxs-lookup"><span data-stu-id="678ee-105">Password</span></span>
<a id="password" class="xliff"></a>
-   <span data-ttu-id="678ee-106">**Senha obrigatória** – Exigir que o usuário final insira uma senha para acessar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="678ee-106">**Password required** - Require the end user to enter a password to access the device.</span></span>
    -   <span data-ttu-id="678ee-107">**Tipo de senha necessária** – Especifique se a senha usada pode ser apenas Numérica ou se deve ser Alfanumérica (conter letras e números).</span><span class="sxs-lookup"><span data-stu-id="678ee-107">**Required password type** - Specify whether the password can be Numeric only, or whether it must be Alphanumeric (contain letters and numbers).</span></span> <span data-ttu-id="678ee-108">Essa configuração só tem suporte no Mac OS X versão 10.10.3 e posterior.</span><span class="sxs-lookup"><span data-stu-id="678ee-108">This setting is supported only on Mac OS X version 10.10.3 and later.</span></span>
    -   <span data-ttu-id="678ee-109">**Número de caracteres não alfanuméricos na senha** – Especifique o número de caracteres complexos necessários na senha (**0** a **4**).</span><span class="sxs-lookup"><span data-stu-id="678ee-109">**Number of non-alphanumeric characters in password** - Specify the number of complex characters required in the password (**0** to **4**).</span></span><br><span data-ttu-id="678ee-110">Um caractere complexo é um símbolo, como **?**</span><span class="sxs-lookup"><span data-stu-id="678ee-110">A complex character is a symbol, like **?**</span></span>
    -   <span data-ttu-id="678ee-111">**Tamanho mínimo da senha** – Insira o tamanho mínimo da senha que um usuário deve configurar (entre **4** e **16** caracteres).</span><span class="sxs-lookup"><span data-stu-id="678ee-111">**Minimum password length** - Enter the minimum length of password a user must configure (between **4** and **16** characters).</span></span>
    -   <span data-ttu-id="678ee-112">**Senhas simples** – Permita o uso de senhas simples como **0000** ou **1234**.</span><span class="sxs-lookup"><span data-stu-id="678ee-112">**Simple passwords** - Allow the use of simple passwords such as **0000** or **1234**.</span></span>
    -   <span data-ttu-id="678ee-113">**Máximo de minutos após o bloqueio de tela antes da senha ser exigida** – Especifique quanto tempo o computador deverá ficar inativo antes da senha ser necessária para desbloqueá-lo.</span><span class="sxs-lookup"><span data-stu-id="678ee-113">**Maximum minutes after screen lock before password is required** - Specify how long the computer must be inactive before a password is required to unlock it.</span></span>
    -   <span data-ttu-id="678ee-114">**Máximo de minutos de inatividade para o bloqueio de tela** – Especifique o período que um computador deve permanecer ocioso antes da tela ser bloqueada.</span><span class="sxs-lookup"><span data-stu-id="678ee-114">**Maximum minutes of inactivity until screen locks** - Specify the length of time that the computer must be idle before the screen locks.</span></span>
    -   <span data-ttu-id="678ee-115">**Expiração de senha (dias)** – Especifique o número de dias que precisam transcorrer antes que o usuário precise alterar a senha (de **1** a **255** dias).</span><span class="sxs-lookup"><span data-stu-id="678ee-115">**Password expiration (days)** - Specify how many days elapse before the user must change the password (**1** to **255** days).</span></span>
    -   <span data-ttu-id="678ee-116">**Impedir a reutilização de senhas anteriores** – Especifique o número de senhas usadas anteriormente que não podem ser reutilizadas (de **1** a **24**).</span><span class="sxs-lookup"><span data-stu-id="678ee-116">**Prevent reuse of previous passwords** - Specify the number of previously used passwords that cannot be reused (**1** to **24**).</span></span>

## <span data-ttu-id="678ee-117">Aplicativos restritos</span><span class="sxs-lookup"><span data-stu-id="678ee-117">Restricted apps</span></span>
<a id="restricted-apps" class="xliff"></a>

<span data-ttu-id="678ee-118">Na lista de aplicativos restritos, você pode configurar uma das seguintes listas:</span><span class="sxs-lookup"><span data-stu-id="678ee-118">In the restricted apps list, you can configure one of the following lists:</span></span>

<span data-ttu-id="678ee-119">Uma lista de **Aplicativos proibidos** – Listar os aplicativos (não gerenciados pelo Intune) que os usuários não têm permissão para instalar e executar.</span><span class="sxs-lookup"><span data-stu-id="678ee-119">A **Prohibited apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.</span></span>
<span data-ttu-id="678ee-120">Uma lista de **Aplicativos aprovados** – Listar os aplicativos que os usuários têm permissão para instalar.</span><span class="sxs-lookup"><span data-stu-id="678ee-120">An **Approved apps** list - List the apps that users are allowed to install.</span></span> <span data-ttu-id="678ee-121">Para permanecer compatível, os usuários não devem instalar aplicativos que não estão listados.</span><span class="sxs-lookup"><span data-stu-id="678ee-121">To remain compliant, users must not install apps that are not listed.</span></span> <span data-ttu-id="678ee-122">Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="678ee-122">Apps that are managed by Intune are automatically allowed.</span></span>
=======
# Configurações de restrição de dispositivo macOS no Microsoft Intune
<a id="macos-device-restriction-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use essas configurações para gerenciar dispositivos macOS em um perfil de restrição de dispositivo.

## Senha
<a id="password" class="xliff"></a>
-   **Senha obrigatória** – Exigir que o usuário final insira uma senha para acessar o dispositivo.
    -   **Tipo de senha necessária** – Especifique se a senha usada pode ser apenas Numérica ou se deve ser Alfanumérica (conter letras e números). Essa configuração só tem suporte no Mac OS X versão 10.10.3 e posterior.
    -   **Número de caracteres não alfanuméricos na senha** – Especifique o número de caracteres complexos necessários na senha (**0** a **4**).<br>Um caractere complexo é um símbolo, como **?**
    -   **Tamanho mínimo da senha** – Insira o tamanho mínimo da senha que um usuário deve configurar (entre **4** e **16** caracteres).
    -   **Senhas simples** – Permita o uso de senhas simples como **0000** ou **1234**.
    -   **Máximo de minutos após o bloqueio de tela antes da senha ser exigida** – Especifique quanto tempo o computador deverá ficar inativo antes da senha ser necessária para desbloqueá-lo.
    -   **Máximo de minutos de inatividade para o bloqueio de tela** – Especifique o período que um computador deve permanecer ocioso antes da tela ser bloqueada.
    -   **Expiração de senha (dias)** – Especifique o número de dias que precisam transcorrer antes que o usuário precise alterar a senha (de **1** a **255** dias).
    -   **Impedir a reutilização de senhas anteriores** – Especifique o número de senhas usadas anteriormente que não podem ser reutilizadas (de **1** a **24**).

## Aplicativos restritos
<a id="restricted-apps" class="xliff"></a>
>>>>>>> live

<span data-ttu-id="678ee-123">Para configurar a lista, clique em **Adicionar**, especifique um nome de sua preferência, o editor do aplicativo (opcional) e a ID do pacote do aplicativo (por exemplo *com.apple.calculator*).</span><span class="sxs-lookup"><span data-stu-id="678ee-123">To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the bundle ID of the app (for example *com.apple.calculator*).</span></span>

## <span data-ttu-id="678ee-124">Domínios</span><span class="sxs-lookup"><span data-stu-id="678ee-124">Domains</span></span>
<a id="domains" class="xliff"></a>

### <span data-ttu-id="678ee-125">Domínios de email desmarcados</span><span class="sxs-lookup"><span data-stu-id="678ee-125">Unmarked email domains</span></span>
<a id="unmarked-email-domains" class="xliff"></a>

<<<<<<< HEAD
<span data-ttu-id="678ee-126">No campo **URL do Domínio de Email**, adicione uma ou mais URLs à lista.</span><span class="sxs-lookup"><span data-stu-id="678ee-126">In the **Email Domain URL** field, add one or more URLs to the list.</span></span> <span data-ttu-id="678ee-127">Quando os usuários finais receberem um email de um domínio diferente daqueles configurados por você, o email será marcado como não confiável no aplicativo Mail do iOS.</span><span class="sxs-lookup"><span data-stu-id="678ee-127">When end users receive an email from a domain other than one you configured, the email is marked as untrusted in the iOS Mail app.</span></span>
=======
## Domínios
<a id="domains" class="xliff"></a>

### Domínios de email desmarcados
<a id="unmarked-email-domains" class="xliff"></a>

No campo **URL do Domínio de Email**, adicione uma ou mais URLs à lista. Quando os usuários finais receberem um email de um domínio diferente daqueles configurados por você, o email será marcado como não confiável no aplicativo Mail do iOS.
>>>>>>> live

