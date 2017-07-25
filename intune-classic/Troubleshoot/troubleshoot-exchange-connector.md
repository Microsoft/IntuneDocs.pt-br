---
title: Solucionar problemas do Exchange Connector
description: Solucione problemas relacionados ao Intune Exchange Connector.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c5cb5465-fd8e-4524-83b9-ccdf3393b6dc
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ebcbcbc36c925b3c3d9600eb9a5039b70d7e056d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="b0b3c-103">Solução de problemas com o Exchange Connector</span><span class="sxs-lookup"><span data-stu-id="b0b3c-103">Troubleshoot the Exchange Connector</span></span>
<a id="troubleshoot-the-exchange-connector" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="b0b3c-104">Este tópico descreve como solucionar problemas que podem estar relacionados com o Intune Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-104">This topic describes how to troubleshoot issues that may be related to the Intune Exchange Connector.</span></span>

## <span data-ttu-id="b0b3c-105">Etapas para verificar a configuração do Connector</span><span class="sxs-lookup"><span data-stu-id="b0b3c-105">Steps for checking the Connector configuration</span></span>
<a id="steps-for-checking-the-connector-configuration" class="xliff"></a> 

<span data-ttu-id="b0b3c-106">Verifique a configuração do Exchange Connector e veja se o problema foi resolvido.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-106">Check the configuration of the Exchange Connector and then see if the problem has been resolved.</span></span>

- <span data-ttu-id="b0b3c-107">Certifique-se de especificar uma conta de notificação na instalação inicial do Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-107">Be sure to specify a notification account in the initial setup of the Exchange Connector.</span></span>
- <span data-ttu-id="b0b3c-108">A Conta de serviço do Exchange Connector deve ter as permissões apropriadas para executar os cmdlets do PowerShell usados pelo Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-108">The Exchange Connector Service Account must have the appropriate permissions to execute the PowerShell cmdlets used by the Exchange Connector.</span></span>
- <span data-ttu-id="b0b3c-109">Ao configurar o Exchange Connector, especifique um CAS (Servidor de Acesso para Cliente) que seja o mais próximo possível do servidor que hospeda o Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-109">When configuring the Exchange Connector, specify a Client Access Server (CAS) that is as close as possible to the server hosting the Exchange Connector.</span></span> <span data-ttu-id="b0b3c-110">A latência de comunicação entre o CAS e o Exchange Connector pode resultar em atrasos de descoberta de dispositivo, especialmente ao usar o O365 dedicado.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-110">Communication latency between the CAS and the Exchange Connector could result in device discovery delays, particularly when using O365 Dedicated.</span></span>
- <span data-ttu-id="b0b3c-111">Lembre-se de que há uma latência de tempo entre as sincronizações do Exchange Connector com o CAS do Exchange.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-111">Be aware that there is a time lag between Exchange Connector synchronizations with the Exchange CAS.</span></span> <span data-ttu-id="b0b3c-112">Uma sincronização completa ocorre uma vez por dia e uma sincronização de delta (rápida) ocorre a cada duas horas.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-112">A full sync takes place once a day, and a delta (quick) sync takes place every two hours.</span></span> <span data-ttu-id="b0b3c-113">Há a probabilidade que usuários com um dispositivo registrado recentemente sofram atraso na obtenção de acesso.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-113">There is a likelihood that a user with a newly-enrolled device will experience a delay in getting access.</span></span>
- 
## <span data-ttu-id="b0b3c-114">O dispositivo do Exchange ActiveSync não é descoberto no Exchange</span><span class="sxs-lookup"><span data-stu-id="b0b3c-114">Exchange ActiveSync device not discovered from Exchange</span></span>
<a id="exchange-activesync-device-not-discovered-from-exchange" class="xliff"></a>
<span data-ttu-id="b0b3c-115">Verifique se o Exchange Connector está sincronizando com o Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-115">Check to see if the Exchange Connector is syncing with the Exchange server.</span></span> <span data-ttu-id="b0b3c-116">Para fazer isso, localize os logs para uma sincronização completa ou delta.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-116">To do so, locate logs for a full sync or a delta sync.</span></span> <span data-ttu-id="b0b3c-117">Consulte Logs do Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-117">See Exchange Connector Logs.</span></span> <span data-ttu-id="b0b3c-118">Se uma sincronização completa ou delta tiver sido concluída com êxito desde que o dispositivo foi associado, você eliminou isso como origem do problema.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-118">If a full sync or delta sync has completed successfully since the device joined, you've eliminated this as the source of the issue.</span></span> <span data-ttu-id="b0b3c-119">Se nenhuma sincronização tiver sido feita, colete os logs de sincronização e anexe-os a sua solicitação de suporte.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-119">If no sync has taken place, collect the sync logs and attach them to your support request.</span></span>

- <span data-ttu-id="b0b3c-120">Se um usuário não tiver uma licença do Intune, o Exchange Connector não descobrirá seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-120">If a user doesn't have an Intune license, the Exchange connector won’t discover their devices.</span></span>
- <span data-ttu-id="b0b3c-121">Se o endereço SMTP primário de um usuário for diferente de seus UPN no AAD, o Exchange Connector não descobrirá os dispositivos desse usuário do Intune/AAD.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-121">If a user’s Primary SMTP address is different than their UPN in AAD, the Exchange Connector will not discover any devices for that Intune/AAD user.</span></span> <span data-ttu-id="b0b3c-122">Corrija o endereço SMTP primário.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-122">Fix the primary SMTP address.</span></span>
- <span data-ttu-id="b0b3c-123">Se o CAS com que o Exchange Connector se comunica durante um ciclo de descoberta for um CAS do Exchange 2010 e você tiver as caixas de correio do Exchange 2010 e 2013, o Exchange Connector não descobrirá os dispositivos de nenhum usuário do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-123">If the CAS that the Exchange Connector communicates with during a discovery cycle is an Exchange 2010 CAS and you have both Exchange 2010 and 2013 mailbox servers, the Exchange Connector will not discover any Exchange 2013 users’ devices.</span></span> <span data-ttu-id="b0b3c-124">Para resolver esse problema, configure o Exchange Connector para apontar para um CAS do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-124">To resolve this, configure the Exchange Connector to point to an Exchange 2013 CAS.</span></span>  <span data-ttu-id="b0b3c-125">Embora esse problema esteja relacionado principalmente a topologias do O365 dedicado, ainda é recomendável apontar para um CAS do Exchange 2013 em outras topologias como uma prática recomendada.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-125">Though this issue primarily concerns O365 Dedicated topologies, we still recommend pointing to an Exchange 2013 CAS in other topologies as a best practice.</span></span>
- <span data-ttu-id="b0b3c-126">Para ambientes do Exchange dedicado (O365 dedicado), você deve apontar o Exchange Connector para um CAS do Exchange 2013 (não 2010) no ambiente dedicado durante a configuração inicial, uma vez que ele se comunicará com este CAS somente ao executar cmdlets do Powershell.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-126">For Exchange Dedicated (O365 dedicated) environments, you must point the Exchange Connector to an Exchange 2013 (not 2010) CAS in the dedicated environment during the initial setup as it will only communicate with this CAS when executing Powershell cmdlets.</span></span>


## <span data-ttu-id="b0b3c-127">Usando o Powershell para obter mais dados sobre problemas do Exchange Connector</span><span class="sxs-lookup"><span data-stu-id="b0b3c-127">Using Powershell to get more data on Exchange Connector issues</span></span>
<a id="using-powershell-to-get-more-data-on-exchange-connector-issues" class="xliff"></a>
- <span data-ttu-id="b0b3c-128">Para obter uma lista de todos os dispositivos móveis para uma caixa de correio, use Get-ActiveSyncDeviceStatistics -mailbox mbx</span><span class="sxs-lookup"><span data-stu-id="b0b3c-128">To get a list of all mobile devices for a mailbox use Get-ActiveSyncDeviceStatistics -mailbox mbx</span></span>
- <span data-ttu-id="b0b3c-129">Para obter uma lista de endereços SMTP para uma caixa de correio, use Get-Mailbox -Identity user | select emailaddresses | fl.</span><span class="sxs-lookup"><span data-stu-id="b0b3c-129">To get a list of SMTP addresses for a mailbox use Get-Mailbox -Identity user | select emailaddresses | fl.</span></span>
- <span data-ttu-id="b0b3c-130">Para obter informações detalhadas sobre o estado de acesso a um dispositivo, use Get-CASMailbox <upn> | fl</span><span class="sxs-lookup"><span data-stu-id="b0b3c-130">To get detailed information about a device's access state use Get-CASMailbox <upn> | fl</span></span>

### <span data-ttu-id="b0b3c-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b0b3c-131">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="b0b3c-132">Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="b0b3c-132">If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>
