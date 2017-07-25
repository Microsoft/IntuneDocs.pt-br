---
title: Gerenciamento de dispositivos do Exchange ActiveSync
description: "Gerenciar dispositivos móveis com o gerenciamento do Exchange ActiveSync (EAS) usando o conector do Exchange"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8982072b93c22e0294b6e454d597e0aa5bbb7b71
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="fe84e-103">Gerenciamento de dispositivos móveis do Exchange ActiveSync com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fe84e-103">Exchange ActiveSync mobile device management with Microsoft Intune</span></span>
<a id="exchange-activesync-mobile-device-management-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="fe84e-104">Para o Microsoft Intune gerenciar dispositivos móveis diretamente, os dispositivos devem ser [registrados no Intune](prerequisites-for-enrollment.md).</span><span class="sxs-lookup"><span data-stu-id="fe84e-104">For Microsoft Intune to directly manage mobile devices, devices must be [enrolled in Intune](prerequisites-for-enrollment.md).</span></span> <span data-ttu-id="fe84e-105">Como alternativa, os administradores podem habilitar uma solução de gerenciamento mais limitada que usa o gerenciamento do EAS (Exchange ActiveSync) com um conector do Exchange.</span><span class="sxs-lookup"><span data-stu-id="fe84e-105">As an alternative, admins can enable a more limited management solution that uses Exchange ActiveSync (EAS) management with an Exchange connector.</span></span> <span data-ttu-id="fe84e-106">Dispositivos podem ser gerenciados nos servidores Exchange locais ou no Exchange Online usando o Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="fe84e-106">Devices can be managed with either on-premises Exchange servers or Exchange Online using Office 365.</span></span> <span data-ttu-id="fe84e-107">O Intune dá suporte apenas a uma conexão do conector do Exchange de qualquer tipo por assinatura.</span><span class="sxs-lookup"><span data-stu-id="fe84e-107">Intune supports only one Exchange connector connection of any type per subscription.</span></span>

## <span data-ttu-id="fe84e-108">Regras de acesso do Exchange para dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="fe84e-108">Exchange access rules for mobile devices</span></span>
<a id="exchange-access-rules-for-mobile-devices" class="xliff"></a> ##

<span data-ttu-id="fe84e-109">O Exchange precisa de um conjunto de regras que define o que acontece quando os dispositivos móveis tentam se conectar ao EAS.</span><span class="sxs-lookup"><span data-stu-id="fe84e-109">Exchange needs a set of rules that defines what happens when mobile devices attempt to connect to EAS.</span></span> <span data-ttu-id="fe84e-110">Essas regras são gerenciadas no console de administração do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe84e-110">These rules are managed in the Intune administration console.</span></span>

[<span data-ttu-id="fe84e-111">Regras de acesso do Exchange para dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="fe84e-111">Exchange access rules for mobile devices</span></span>](exchange-access-rules-for-mobile-devices.md)

## <span data-ttu-id="fe84e-112">Problemas com o Exchange Connector</span><span class="sxs-lookup"><span data-stu-id="fe84e-112">Install the Exchange connector</span></span>
<a id="install-the-exchange-connector" class="xliff"></a>
<span data-ttu-id="fe84e-113">O Exchange Connector permite gerenciar a implantação do Exchange no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe84e-113">The Exchange connector lets you manage your Exchange deployment in the Intune console.</span></span> <span data-ttu-id="fe84e-114">Primeiro instale e configure o conector do Intune para Exchange apropriado.</span><span class="sxs-lookup"><span data-stu-id="fe84e-114">You must first install and set up the appropriate Intune-to-Exchange connector.</span></span> <span data-ttu-id="fe84e-115">Escolha a opção apropriada com base em se o servidor Exchange é local ou hospedado como um serviço em nuvem:</span><span class="sxs-lookup"><span data-stu-id="fe84e-115">Choose the appropriate option based on whether your Exchange server is on-premises or hosted as a service in the cloud:</span></span>

-   [<span data-ttu-id="fe84e-116">Configurar o Intune para o Exchange Online ou novos ambientes do Exchange Online Dedicated</span><span class="sxs-lookup"><span data-stu-id="fe84e-116">Configure the Intune for Exchange Online or new Exchange Online Dedicated environments</span></span>](intune-service-to-service-exchange-connector.md)
-   [<span data-ttu-id="fe84e-117">Instalar o conector do Intune para servidores do Exchange locais e ambientes do Exchange Online Dedicated herdados</span><span class="sxs-lookup"><span data-stu-id="fe84e-117">Install the Intune connector for on-premises Exchange servers and legacy Exchange Online Dedicated environments</span></span>](intune-on-premises-exchange-connector.md)


## <span data-ttu-id="fe84e-118">Aplicar política a dispositivos móveis gerenciados pelo Exchange</span><span class="sxs-lookup"><span data-stu-id="fe84e-118">Apply policy for Exchange-managed mobile devices</span></span>
<a id="apply-policy-for-exchange-managed-mobile-devices" class="xliff"></a>
<span data-ttu-id="fe84e-119">O console do Intune pode ser usado para gerenciar [configurações de política EAS](exchange-activesync-policy-settings-in-microsoft-intune.md) e [restringir o acesso aos recursos da empresa](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="fe84e-119">The Intune console can be used to manage [EAS policy settings](exchange-activesync-policy-settings-in-microsoft-intune.md) and to [restrict access to company resources](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span></span> <span data-ttu-id="fe84e-120">Para obter uma lista de recursos e configurações de política do Exchange ActiveSync com suporte de dispositivos móveis específicos, consulte [Tabela de Comparação do Cliente Exchange ActiveSync](http://go.microsoft.com/fwlink/?LinkId=247270).</span><span class="sxs-lookup"><span data-stu-id="fe84e-120">For a list of Exchange ActiveSync policy settings and features that specific mobile devices support, see [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270).</span></span>

> [!NOTE]
> <span data-ttu-id="fe84e-121">Após conectar o Intune a um ambiente do Microsoft Exchange, a política EAS de todos os usuários gerenciados por meio do Intune será redefinida para a política padrão atual no Microsoft Exchange Server, a menos que haja uma política mais específica definida no Intune.</span><span class="sxs-lookup"><span data-stu-id="fe84e-121">After connecting Intune to a Microsoft Exchange environment, the EAS policy for all users managed through Intune will be reset to the current default policy on the Microsoft Exchange server, unless a more specific policy is defined within Intune.</span></span>

## <span data-ttu-id="fe84e-122">Apagar os dados da empresa de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="fe84e-122">Wipe company data from mobile devices</span></span>
<a id="wipe-company-data-from-mobile-devices" class="xliff"></a>
<span data-ttu-id="fe84e-123">Por fim, você pode [apagar os dados da empresa dos dispositivos móveis gerenciados EAS](wipe-for-exchange-managed-mobile-devices.md) quando eles não estão mais em uso ou se os dispositivos forem perdidos ou roubados.</span><span class="sxs-lookup"><span data-stu-id="fe84e-123">Finally, you can [wipe company data from EAS-managed mobile devices](wipe-for-exchange-managed-mobile-devices.md) when they are no longer in use, or if devices are lost or stolen.</span></span>
