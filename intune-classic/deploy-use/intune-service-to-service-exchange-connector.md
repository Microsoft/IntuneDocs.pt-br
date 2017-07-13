---
title: Exchange Connector para o Exchange Online
description: "Conecte o Intune ao serviço Office 365 Exchange para dar suporte ao MDM (gerenciamento de dispositivo móvel) do Exchange ActiveSync."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c2f30e7827db280ba49fc49b6b7a00c9a8d9eade
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="3a593-103">Configurar o Service to Service Connector do Intune para o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3a593-103">Configure the Intune service to service connector for Exchange Online</span></span>
<a id="configure-the-intune-service-to-service-connector-for-exchange-online" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="3a593-104">Use essas informações para conectar o serviço Microsoft Intune e Exchange Online ou o novo Exchange Online Dedicado.</span><span class="sxs-lookup"><span data-stu-id="3a593-104">Use this information to connect Microsoft Intune and Exchange Online or the new Exchange Online Dedicated service.</span></span> <span data-ttu-id="3a593-105">Para determinar se o seu ambiente Exchange Online Dedicado está na versão **nova** ou **herdada**, entre em contato com seu gerente de conta.</span><span class="sxs-lookup"><span data-stu-id="3a593-105">To determine whether your Exchange Online Dedicated environment is the **new** or **legacy** version, contact your account manager.</span></span> <span data-ttu-id="3a593-106">O Intune oferece suporte apenas a uma conexão do conector do Exchange de qualquer tipo por assinatura.</span><span class="sxs-lookup"><span data-stu-id="3a593-106">Intune only supports one Exchange connector connection of any type per subscription.</span></span>

## <span data-ttu-id="3a593-107">Requisitos para o Service to Service Connector</span><span class="sxs-lookup"><span data-stu-id="3a593-107">Service to Service Connector requirements</span></span>
<a id="service-to-service-connector-requirements" class="xliff"></a>
<span data-ttu-id="3a593-108">O **Service to Service Connector** tem suporte apenas para o Exchange Online ou para o novo Exchange Online Dedicado e não tem requisitos de infraestrutura local.</span><span class="sxs-lookup"><span data-stu-id="3a593-108">The **Service to Service Connector** supports only Exchange Online or Exchange Online Dedicated and has no requirements for on-premises infrastructure.</span></span>

|<span data-ttu-id="3a593-109">Requisito</span><span class="sxs-lookup"><span data-stu-id="3a593-109">Requirement</span></span>|<span data-ttu-id="3a593-110">Mais informações</span><span class="sxs-lookup"><span data-stu-id="3a593-110">More information</span></span>|
|---------------|--------------------|
|<span data-ttu-id="3a593-111">Exchange Online configurado e em execução</span><span class="sxs-lookup"><span data-stu-id="3a593-111">Exchange Online configured and running</span></span>|[<span data-ttu-id="3a593-112">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3a593-112">Exchange Online</span></span>](https://technet.microsoft.com/library/jj200580.aspx) |
|<span data-ttu-id="3a593-113">Autoridade de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="3a593-113">Mobile device management authority</span></span>| [<span data-ttu-id="3a593-114">Configurar a autoridade de gerenciamento de dispositivo móvel para o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3a593-114">Set the mobile device management authority to Microsoft Intune</span></span>](prerequisites-for-enrollment.md#step-2-set-mdm-authority)|
|<span data-ttu-id="3a593-115">Versão do Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="3a593-115">Microsoft Exchange version</span></span>|<span data-ttu-id="3a593-116">Serviço Exchange Online ou o novo Exchange Online Dedicado</span><span class="sxs-lookup"><span data-stu-id="3a593-116">Exchange Online or the new Exchange Online Dedicated service</span></span>|<span data-ttu-id="3a593-117">/intune/users-permissions-add</span><span class="sxs-lookup"><span data-stu-id="3a593-117">/intune/users-permissions-add</span></span>
|<span data-ttu-id="3a593-118">Sincronização do Active Directory</span><span class="sxs-lookup"><span data-stu-id="3a593-118">Active Directory synchronization</span></span>|<span data-ttu-id="3a593-119">Antes de usar o Conector do Intune, é preciso [configurar a sincronização do Active Directory](/intune/users-permissions-add) para que os usuários e grupos de segurança locais sejam sincronizados com sua instância do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3a593-119">Before you can use the Intune Connector, you must [set up Active Directory synchronization](/intune/users-permissions-add) so that your local users and security groups are synchronized with your instance of Azure Active Directory.</span></span>|

### <span data-ttu-id="3a593-120">Requisitos de cmdlets do Exchange</span><span class="sxs-lookup"><span data-stu-id="3a593-120">Exchange cmdlet requirements</span></span>
<a id="exchange-cmdlet-requirements" class="xliff"></a>

<span data-ttu-id="3a593-121">Também é preciso criar uma conta de usuário do Exchange Online que seja usada pelo Intune Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="3a593-121">You must also create an Exchange Online user account that is used by the Intune Exchange Connector.</span></span> <span data-ttu-id="3a593-122">A conta deve ter permissão para usar o console de administração do Intune e executar os seguintes cmdlets necessários do Windows PowerShell Exchange:</span><span class="sxs-lookup"><span data-stu-id="3a593-122">The account must have permission to use the Intune administration console and to run the following required Windows PowerShell Exchange cmdlets:</span></span>

 - <span data-ttu-id="3a593-123">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span><span class="sxs-lookup"><span data-stu-id="3a593-123">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span></span>
 - <span data-ttu-id="3a593-124">Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy</span><span class="sxs-lookup"><span data-stu-id="3a593-124">Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy</span></span>
 - <span data-ttu-id="3a593-125">Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule</span><span class="sxs-lookup"><span data-stu-id="3a593-125">Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule</span></span>
 - <span data-ttu-id="3a593-126">Get-MobileDeviceStatistics</span><span class="sxs-lookup"><span data-stu-id="3a593-126">Get-MobileDeviceStatistics</span></span>
 - <span data-ttu-id="3a593-127">Get-MobileDevice</span><span class="sxs-lookup"><span data-stu-id="3a593-127">Get-MobileDevice</span></span>
 - <span data-ttu-id="3a593-128">Get-ActiveSyncDeviceClass</span><span class="sxs-lookup"><span data-stu-id="3a593-128">Get-ActiveSyncDeviceClass</span></span>

## <span data-ttu-id="3a593-129">Configurar o Conector de Serviço a Serviço</span><span class="sxs-lookup"><span data-stu-id="3a593-129">Set up the Service to Service Connector</span></span>
<a id="set-up-the-service-to-service-connector" class="xliff"></a>

1. <span data-ttu-id="3a593-130">Abra o [console de administração do Microsoft Intune](https://manage.microsoft.com) com uma conta de usuário com direitos de administrador do Exchange e permissões para os cmdlets [descritos acima](#exchange-cmdlet-requirements).</span><span class="sxs-lookup"><span data-stu-id="3a593-130">Open the [Microsoft Intune administration console](https://manage.microsoft.com) with a user account that has Exchange admin rights and permissions for the cmdlets [described earlier](#exchange-cmdlet-requirements).</span></span> <span data-ttu-id="3a593-131">O Microsoft Intune usa o endereço de email do usuário conectado no momento para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="3a593-131">Microsoft Intune uses the email address of the currently signed-in user to set up the connection.</span></span>

2.  <span data-ttu-id="3a593-132">No painel de atalhos do espaço de trabalho, selecione **ADMIN**>**Gerenciamento de Dispositivo Móvel** > **Microsoft Exchange** > **Configurar Conexão com o Exchange**.</span><span class="sxs-lookup"><span data-stu-id="3a593-132">In the workspace shortcuts pane, choose **ADMIN**>**Mobile Device Management** > **Microsoft Exchange** > **Set Up Exchange Connection**.</span></span>
<span data-ttu-id="3a593-133">![Configurar página do Service to Service Connector](../media/intunesa5cservicetoserviceconnector.png)</span><span class="sxs-lookup"><span data-stu-id="3a593-133">![Set up service to service connector page](../media/intunesa5cservicetoserviceconnector.png)</span></span>

3.  <span data-ttu-id="3a593-134">Na página **Configurar a Conexão do Exchange**, clique em **Configurar o Conector de Serviços**.</span><span class="sxs-lookup"><span data-stu-id="3a593-134">On the **Set Up Exchange Connection** page, choose **Set Up Service to Service Connector**.</span></span>


<span data-ttu-id="3a593-135">O Service to Service Connector configura e sincroniza automaticamente seu ambiente do Exchange Online ou do novo Exchange Online Dedicado.</span><span class="sxs-lookup"><span data-stu-id="3a593-135">The Service to Service Connector automatically configures and synchronizes your Exchange Online or new Exchange Online Dedicated environment.</span></span>

## <span data-ttu-id="3a593-136">Validar a sua conexão do Exchange</span><span class="sxs-lookup"><span data-stu-id="3a593-136">Validate your Exchange connection</span></span>
<a id="validate-your-exchange-connection" class="xliff"></a>

<span data-ttu-id="3a593-137">Após configurar com êxito o Exchange Connector, vá para o [console de administração do Microsoft Intune](https://manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3a593-137">After you have successfully configured the Exchange Connector, go to the [Microsoft Intune administration console](https://manage.microsoft.com).</span></span> <span data-ttu-id="3a593-138">Selecione **Admin**> **Gerenciamento de Dispositivo Móvel** > **Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="3a593-138">Choose **Admin**> **Mobile Device Management** > **Microsoft Exchange**.</span></span> <span data-ttu-id="3a593-139">Em seguida, confirme se os detalhes fornecidos aparecem em **Informações sobre Conexão com o Exchange**.</span><span class="sxs-lookup"><span data-stu-id="3a593-139">Then validate that the details you provided appear under **Exchange Connection Information**.</span></span>

<span data-ttu-id="3a593-140">Você também pode verificar a hora e data da última tentativa de sincronização bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="3a593-140">You can also check the time and date of the last successful synchronization attempt.</span></span>
