---
title: "Configurações de email do Intune para dispositivos Windows 10"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para configurar as conexões de email em dispositivos Windows 10."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ffafbd0-4b5d-4c86-a46b-611f9b7a58e5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 121c21d49d3639925ef0abcdc55cb599ed276778
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1d42f-103">Configurações de perfil de email para dispositivos Windows 10 no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1d42f-103">Email profile settings for Windows 10 devices in Microsoft Intune</span></span>
<a id="email-profile-settings-for-windows-10-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



- <span data-ttu-id="1d42f-104">**Servidor de email** – O nome do host do seu servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="1d42f-104">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="1d42f-105">**Nome da conta** – O nome de exibição para a conta de email que será exibida aos usuários em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1d42f-105">**Account name** - The display name for the email account as it will appear to users on their devices.</span></span>
- <span data-ttu-id="1d42f-106">**Atributo de nome de usuário do AAD** – Esse é o atributo no AD (Active Directory) ou Azure AD, que será usado para gerar o nome de usuário para este perfil de email.</span><span class="sxs-lookup"><span data-stu-id="1d42f-106">**Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile.</span></span> <span data-ttu-id="1d42f-107">Selecione o **Endereço SMTP Primário**, como o **user1@contoso.com** ou **Nome UPN**, como **user1** ou **user1@contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="1d42f-107">Select **Primary SMTP Address**, such as **user1@contoso.com** or **User Principal Name**, such as **user1** or **user1@contoso.com**.</span></span>
- <span data-ttu-id="1d42f-108">**Atributo de endereço de email do AAD** – Como o endereço de email do usuário em cada dispositivo cliente será gerado.</span><span class="sxs-lookup"><span data-stu-id="1d42f-108">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="1d42f-109">Selecione **Endereço SMTP Primário** para usar o endereço SMTP primário para fazer logon no Exchange ou use **Nome UPN** para usar o nome da entidade completo como o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="1d42f-109">Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use **User Principal Name** to use the full principal name as the email address.</span></span>


## <span data-ttu-id="1d42f-110">Configurações de segurança</span><span class="sxs-lookup"><span data-stu-id="1d42f-110">Security settings</span></span>
<a id="security-settings" class="xliff"></a>

- <span data-ttu-id="1d42f-111">**SSL** – Use a comunicação por protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="1d42f-111">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>



## <span data-ttu-id="1d42f-112">Configurações de sincronização</span><span class="sxs-lookup"><span data-stu-id="1d42f-112">Synchronization settings</span></span>
<a id="synchronization-settings" class="xliff"></a>

- <span data-ttu-id="1d42f-113">**Quantidade de emails a ser sincronizada** – Escolha o número de dias de emails que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todas as mensagens disponíveis.</span><span class="sxs-lookup"><span data-stu-id="1d42f-113">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="1d42f-114">**Sincronizar agendamento** – Selecione o agendamento pelo qual os dispositivos sincronizarão os dados do servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="1d42f-114">**Sync schedule** - Select the schedule by which devices will synchronize data from the Exchange server.</span></span> <span data-ttu-id="1d42f-115">Você também pode selecionar **Conforme as mensagens chegam**, que sincroniza os dados assim que eles chegam, ou **Manual**, em que o usuário do dispositivo deve iniciar a sincronização.</span><span class="sxs-lookup"><span data-stu-id="1d42f-115">You can also select **As Messages arrive**, which synchronizes data as soon as it arrives, or **Manual**, where the user of the device must initiate the synchronization.</span></span>

## <span data-ttu-id="1d42f-116">Configurações de sincronização de conteúdo</span><span class="sxs-lookup"><span data-stu-id="1d42f-116">Content sync settings</span></span>
<a id="content-sync-settings" class="xliff"></a>

- <span data-ttu-id="1d42f-117">**Tipo de conteúdo a ser sincronizado** – Selecione os tipos de conteúdo que você deseja sincronizar dos dispositivos:</span><span class="sxs-lookup"><span data-stu-id="1d42f-117">**Content type to sync** - Select the content types that you want to synchronize to devices from:</span></span>
    - <span data-ttu-id="1d42f-118">**Contatos**</span><span class="sxs-lookup"><span data-stu-id="1d42f-118">**Contacts**</span></span>
    - <span data-ttu-id="1d42f-119">**Calendário**</span><span class="sxs-lookup"><span data-stu-id="1d42f-119">**Calendar**</span></span>
    - <span data-ttu-id="1d42f-120">**Tarefas**</span><span class="sxs-lookup"><span data-stu-id="1d42f-120">**Tasks**</span></span>
