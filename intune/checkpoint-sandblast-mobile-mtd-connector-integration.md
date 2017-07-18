---
title: "Configurar a integração do Check Point SandBlast com o Intune"
titleSuffix: Intune on Azure
description: "Configurar a integração do Check Point SandBlast com o Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1e9b1576-b239-48cc-a672-da6b5fb7be0a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eaeaa7eef50b24a1d0b8cc104a673b8676bb7734
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2017
---
# <a name="integrate-check-point-sandblast-mobile-with-intune"></a><span data-ttu-id="96a21-103">Integrar O Check Point SandBlast Mobile com o Intune</span><span class="sxs-lookup"><span data-stu-id="96a21-103">Integrate Check Point SandBlast Mobile with Intune</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="96a21-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="96a21-104">Before you begin</span></span>

> [!NOTE] 
> <span data-ttu-id="96a21-105">As etapas a seguir precisam ser tomadas no [console do Check Point SandBlast Mobile MTD](https://intune-4.eu1.locsec.net/).</span><span class="sxs-lookup"><span data-stu-id="96a21-105">The steps below need to be taken in the [Check Point SandBlast Mobile MTD console](https://intune-4.eu1.locsec.net/).</span></span>

<span data-ttu-id="96a21-106">Antes de iniciar o processo de integração do Check Point SandBlast Mobile com o Intune, verifique se que você tem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="96a21-106">Before starting the process of integrating Check Point SandBlast Mobile with Intune, make sure you have the following:</span></span>

-   <span data-ttu-id="96a21-107">Assinatura do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="96a21-107">Microsoft Intune subscription</span></span>

-   <span data-ttu-id="96a21-108">Credenciais de administrador do Azure Active Directory para conceder as seguintes permissões:</span><span class="sxs-lookup"><span data-stu-id="96a21-108">Azure Active Directory admin credentials to grant the following permissions:</span></span>

    -   <span data-ttu-id="96a21-109">Entrada e leitura de perfil do usuário</span><span class="sxs-lookup"><span data-stu-id="96a21-109">Sign in and read user profile</span></span>

    -   <span data-ttu-id="96a21-110">Acessar diretório como o usuário conectado</span><span class="sxs-lookup"><span data-stu-id="96a21-110">Access the directory as the signed-in user</span></span>

    -   <span data-ttu-id="96a21-111">Ler dados do diretório</span><span class="sxs-lookup"><span data-stu-id="96a21-111">Read directory data</span></span>

    -   <span data-ttu-id="96a21-112">Enviar informações do dispositivo para o Intune</span><span class="sxs-lookup"><span data-stu-id="96a21-112">Send device information to Intune</span></span>

-   <span data-ttu-id="96a21-113">Credenciais de administrador para acessar o console de verificar o console de MTD do Check Point SandBlast Mobile.</span><span class="sxs-lookup"><span data-stu-id="96a21-113">Admin credentials to access Check Point SandBlast Mobile MTD console.</span></span>

### <a name="check-point-sandblast-app-authorization"></a><span data-ttu-id="96a21-114">Autorização de aplicativo do Check Point SandBlast</span><span class="sxs-lookup"><span data-stu-id="96a21-114">Check Point SandBlast app authorization</span></span>

<span data-ttu-id="96a21-115">O processo de autorização do aplicativo do Check Point SandBlast consiste no seguinte:</span><span class="sxs-lookup"><span data-stu-id="96a21-115">The Check Point SandBlast app authorization process consists of the following:</span></span>

-   <span data-ttu-id="96a21-116">Permitir que o serviço Check Point SandBlast Mobile comunique informações relacionadas ao estado de integridade do dispositivo de volta para o Intune.</span><span class="sxs-lookup"><span data-stu-id="96a21-116">Allow the Check Point SandBlast Mobile service to communicate information related to device health state back to Intune.</span></span>

-   <span data-ttu-id="96a21-117">O CheckPoint SandBlast Mobile sincroniza-se com a associação de Grupo de Registro do Azure AD para popular o banco de dados do respectivo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="96a21-117">CheckPoint SandBlast Mobile syncs with Azure AD Enrollment Group membership to populate its device’s database.</span></span>

-   <span data-ttu-id="96a21-118">Permitir que o console de administração do Check Point SandBlast use o SSO (logon único) do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="96a21-118">Allow Check Point SandBlast admin console to use Azure AD Single Sign On (SSO).</span></span>

-   <span data-ttu-id="96a21-119">Permitir que o aplicativo Check Point SandBlast Mobile entre usando o SSO do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="96a21-119">Allow the Check Point SandBlast Mobile app to sign in using Azure AD SSO.</span></span>

## <a name="to-set-up-check-point-sandblast-mobile-integration"></a><span data-ttu-id="96a21-120">Para configurar a integração do Check Point SandBlast Mobile</span><span class="sxs-lookup"><span data-stu-id="96a21-120">To set up Check Point SandBlast Mobile integration</span></span>

1.  <span data-ttu-id="96a21-121">Vá para o [console do Check Point SandBlast Mobile MTD](https://intune-4.eu1.locsec.net/) e entre com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="96a21-121">Go to [Check Point SandBlast Mobile MTD console](https://intune-4.eu1.locsec.net/) and sign in with your credentials.</span></span>

2.  <span data-ttu-id="96a21-122">Clique na guia **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="96a21-122">Click on the **Settings** tab.</span></span>

3.  <span data-ttu-id="96a21-123">Escolha **Gerenciamento de dispositivo**, seguido de **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="96a21-123">Choose **Device management**, then **Settings**.</span></span>

4.  <span data-ttu-id="96a21-124">Escolha **Microsoft Intune** na lista suspensa **Serviço MDM**.</span><span class="sxs-lookup"><span data-stu-id="96a21-124">Choose **Microsoft Intune** from the **MDM Service** drop-down list.</span></span>

5.  <span data-ttu-id="96a21-125">Depois de configurar o Microsoft Intune como o serviço MDM, a janela **Configuração do Microsoft Intune** aparece; escolha **Adicionar à minha organização** para cada plataforma de dispositivo (iOS, Android e Windows) para autorizar o Check Point SandBlast Mobile a se comunicar com o Intune e o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="96a21-125">Once you set Microsoft Intune as the MDM Service, the **Microsoft Intune Configuration** window pops up, choose the **Add to my organization** for each device platform: iOS, Android and Windows to authorize Check Point SandBlast Mobile to communicate with Intune and Azure AD.</span></span>

    ![Configuração do Intune de MTD da Check Point](./media/checkpoint-MTD-1.PNG)

    > [!IMPORTANT]
    > <span data-ttu-id="96a21-127">Você deve adicionar todas as plataformas de dispositivo para prosseguir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="96a21-127">You must add all device platforms to proceed to the next step.</span></span>

6.  <span data-ttu-id="96a21-128">Escolha **Aceitar** para autorizar o aplicativo Check Point SandBlast Mobile a se comunicar com o Intune e o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="96a21-128">Choose **Accept** to authorize the Check Point SandBlast Mobile app to communicate with Intune and Azure Active Directory.</span></span>

7.  <span data-ttu-id="96a21-129">Depois que de habilitar todas as plataformas de dispositivo, você precisa inserir o grupo de segurança do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="96a21-129">Once you enabled all device platforms, you need to enter the Azure AD security group.</span></span>

8.  <span data-ttu-id="96a21-130">Escolha **Verificar** e, uma vez que o grupo de segurança do Azure AD é verificado com êxito, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="96a21-130">Choose **Verify**, once the Azure AD security group is successfully verified, choose **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="96a21-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="96a21-131">Next steps</span></span>

- [<span data-ttu-id="96a21-132">Habilitar o Check Point SandBlast Mobile com o Intune</span><span class="sxs-lookup"><span data-stu-id="96a21-132">Enable Check Point SandBlast Mobile connector with Intune</span></span>](mtd-connector-enable.md)