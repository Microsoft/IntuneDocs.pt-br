---
title: "Baixar a política de configuração de aplicativo do iOS para Skycure a ser usada com o Intune"
titleSuffix: Intune on Azure
description: "Baixe a política de configuração de aplicativo do iOS para Skycure a ser usada com o Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1bdc2ecf-32d0-4b6a-80b4-dbcdb9909010
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ffe1027e90203d4e300a2446f15e72cc5bf53973
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="2cb20-103">Baixar política de configuração de aplicativo iOS do Skycure</span><span class="sxs-lookup"><span data-stu-id="2cb20-103">Download Skycure iOS app configuration policy</span></span>
<a id="download-skycure-ios-app-configuration-policy" class="xliff"></a>

## <span data-ttu-id="2cb20-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2cb20-104">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

<span data-ttu-id="2cb20-105">Você precisa fazer logon no Console de Gerenciamento do Skycure para executar as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="2cb20-105">You need to log in to the Skycure Management Console to perform the next steps.</span></span>

> [!TIP] 
> <span data-ttu-id="2cb20-106">Se estiver usando o Microsoft Internet Explorer 11 ou o Edge, talvez seja necessário abrir o Console de gerenciamento do Skycure usando o modo privado.</span><span class="sxs-lookup"><span data-stu-id="2cb20-106">If using Microsoft Internet explorer 11 or Edge, you might need to open the Skycure Management console using In-Private mode.</span></span>

## <span data-ttu-id="2cb20-107">Para baixar a política de configuração de aplicativo do iOS</span><span class="sxs-lookup"><span data-stu-id="2cb20-107">To download the iOS app configuration policy</span></span>
<a id="to-download-the-ios-app-configuration-policy" class="xliff"></a>

1.  <span data-ttu-id="2cb20-108">Acesse o [Console de Gerenciamento do Skycure](https://aad.skycure.com).</span><span class="sxs-lookup"><span data-stu-id="2cb20-108">Go to [Skycure Management Console](https://aad.skycure.com).</span></span>

2.  <span data-ttu-id="2cb20-109">Insira suas **credenciais de administrador do Skycure** e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="2cb20-109">Enter your **Skycure admin credentials**, then click **Continue**.</span></span>

    ![Logon no Console de Gerenciamento do Skycure](./media/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="2cb20-111">O nome de usuário de administrador do Skycure é uma conta de email que deve ser uma conta de usuário válida no Azure Active Directory, caso contrário, o logon falhará.</span><span class="sxs-lookup"><span data-stu-id="2cb20-111">The Skycure admin username is an e-mail account that must be a valid user account in the Azure Active Directory, otherwise the login will fail.</span></span> <span data-ttu-id="2cb20-112">O Skycure usa o Azure Active Directory para autenticar seu nome de usuário de administrador usando SSO (Logon único).</span><span class="sxs-lookup"><span data-stu-id="2cb20-112">Skycure uses Azure Active Directory to authenticate its admin username using Single Sign On (SSO).</span></span>

3.  <span data-ttu-id="2cb20-113">Acesse **Configurações** &gt; **Integrações de Gerenciamento de Dispositivo** &gt; **Seleção de Integração EMM**, escolha **Microsoft Intune** e salve sua seleção.</span><span class="sxs-lookup"><span data-stu-id="2cb20-113">Go to **Settings** &gt; **Device Management Integrations** &gt; **EMM Integration Selection**, choose **Microsoft Intune**, then save your selection.</span></span>

4.  <span data-ttu-id="2cb20-114">Clique no link **Arquivos de configuração da integração** e salve o arquivo \*.zip gerado.</span><span class="sxs-lookup"><span data-stu-id="2cb20-114">Click on the **Integration setup files** link and save the generated \*.zip file.</span></span> <span data-ttu-id="2cb20-115">O arquivo .zip contém o arquivo **skycure\_configuration.plist**, que será usado para criar a política de configuração de aplicativo do iOS no console clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="2cb20-115">The .zip file contains the **skycure\_configuration.plist** file, which will be used to create the iOS app configuration policy in the Intune classic console.</span></span>

![Arquivos de configuração de integração do Skycure](./media/skycure-ios-app-2.png)

## <span data-ttu-id="2cb20-117">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="2cb20-117">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="2cb20-118">Adicionar e atribuir aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS</span><span class="sxs-lookup"><span data-stu-id="2cb20-118">Add and assign Skycure apps, Microsoft Authenticator app and the iOS configuration policy</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)
