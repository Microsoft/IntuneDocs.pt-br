---
title: "Configurações de email do Intune para dispositivos Android e Android for Work"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para configurar as conexões de email em dispositivos Android."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4d3458cc-fcaa-4648-b13f-bf1f0616c1c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c1f80e09241609b420a186011ff8dd059f0dd8df
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="6f5eb-103">Configurações de perfil de email para dispositivos Android no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6f5eb-103">Email profile settings for Android  devices in Microsoft Intune</span></span>
<a id="email-profile-settings-for-android--devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="6f5eb-104">Como administrador do Intune, você pode criar e atribuir configurações de email aos seguintes dispositivos Android:</span><span class="sxs-lookup"><span data-stu-id="6f5eb-104">As an Intune admin, you can create and assign email settings to the following Android devices:</span></span>
- [<span data-ttu-id="6f5eb-105">Android Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="6f5eb-105">Android Samsung KNOX Standard</span></span>](#android-samsung-knox-standard-email-settings)
- [<span data-ttu-id="6f5eb-106">Android for Work</span><span class="sxs-lookup"><span data-stu-id="6f5eb-106">Android for Work</span></span>](#android-for-work-email-settings)

## <span data-ttu-id="6f5eb-107">Configurações de email do Android Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="6f5eb-107">Android Samsung KNOX Standard email settings</span></span>
<a id="android-samsung-knox-standard-email-settings" class="xliff"></a>
- <span data-ttu-id="6f5eb-108">**Servidor de email** – O nome do host do seu servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-108">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="6f5eb-109">**Nome da conta** – o nome de exibição da conta de email exibida aos usuários em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-109">**Account name** - The display name for the email account as it appears to users on their devices.</span></span>
- <span data-ttu-id="6f5eb-110">**Atributo de nome de usuário do AAD** – esse nome é o atributo no AD (Active Directory) ou no Azure AD usado para gerar o nome de usuário para esse perfil de email.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-110">**Username attribute from AAD** - This name is the attribute in Active Directory (AD) or Azure AD used to generate the username for this email profile.</span></span> <span data-ttu-id="6f5eb-111">Selecione o **Endereço SMTP Primário**, como o user1@contoso.com ou **Nome UPN**, como user1 ou user1@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-111">Select **Primary SMTP Address**, such as user1@contoso.com or **User Principal Name**, such as user1 or user1@contoso.com.</span></span>
- <span data-ttu-id="6f5eb-112">**Atributo de endereço de email do AAD** – Como o endereço de email do usuário em cada dispositivo cliente será gerado.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-112">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="6f5eb-113">Selecione **Endereço SMTP Primário** para usar o endereço SMTP primário para fazer logon no Exchange ou use o **nome UPN** para usar o nome da entidade completo como o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-113">Select **Primary SMTP Address** to use the primary SMTP address to log in to Exchange or use **User Principal Name** to use the full principal name as the email address.</span></span>
- <span data-ttu-id="6f5eb-114">**Método de autenticação** – Selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-114">**Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.</span></span>
    - <span data-ttu-id="6f5eb-115">Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS do cliente criado anteriormente para autenticar a conexão do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-115">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.</span></span>

### <span data-ttu-id="6f5eb-116">Configurações de segurança</span><span class="sxs-lookup"><span data-stu-id="6f5eb-116">Security settings</span></span>
<a id="security-settings" class="xliff"></a>

- <span data-ttu-id="6f5eb-117">**SSL** – Use a comunicação por protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-117">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>
- <span data-ttu-id="6f5eb-118">**S/MIME** – Envia emails de saída usando a criptografia S/MIME.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-118">**S/MIME** - Send outgoing email using S/MIME encryption.</span></span>
    - <span data-ttu-id="6f5eb-119">Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS do cliente criado anteriormente para autenticar a conexão do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-119">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.</span></span>

### <span data-ttu-id="6f5eb-120">Configurações de sincronização</span><span class="sxs-lookup"><span data-stu-id="6f5eb-120">Synchronization settings</span></span>
<a id="synchronization-settings" class="xliff"></a>

- <span data-ttu-id="6f5eb-121">**Quantidade de emails a ser sincronizada** – Escolha o número de dias de emails que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todas as mensagens disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-121">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="6f5eb-122">**Sincronizar agendamento** – selecione o agendamento conforme o qual os dispositivos sincronizam os dados do servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-122">**Sync schedule** - Select the schedule by which devices synchronize data from the Exchange server.</span></span> <span data-ttu-id="6f5eb-123">Você também pode selecionar **Conforme as mensagens chegam**, que sincroniza os dados quando eles chegam ou **Manual**, em que o usuário do dispositivo deve iniciar a sincronização.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-123">You can also select **As Messages arrive**, which synchronizes data when it arrives, or **Manual**, where the user of the device must initiate the synchronization.</span></span>

### <span data-ttu-id="6f5eb-124">Configurações de sincronização de conteúdo</span><span class="sxs-lookup"><span data-stu-id="6f5eb-124">Content sync settings</span></span>
<a id="content-sync-settings" class="xliff"></a>

- <span data-ttu-id="6f5eb-125">**Tipo de conteúdo a ser sincronizado** – Selecione os tipos de conteúdo que você deseja sincronizar dos dispositivos:</span><span class="sxs-lookup"><span data-stu-id="6f5eb-125">**Content type to sync** - Select the content types that you want to synchronize to devices from:</span></span>
    - <span data-ttu-id="6f5eb-126">**Contatos**</span><span class="sxs-lookup"><span data-stu-id="6f5eb-126">**Contacts**</span></span>
    - <span data-ttu-id="6f5eb-127">**Calendário**</span><span class="sxs-lookup"><span data-stu-id="6f5eb-127">**Calendar**</span></span>
    - <span data-ttu-id="6f5eb-128">**Tarefas**</span><span class="sxs-lookup"><span data-stu-id="6f5eb-128">**Tasks**</span></span>

## <span data-ttu-id="6f5eb-129">Configurações de email do Android for Work</span><span class="sxs-lookup"><span data-stu-id="6f5eb-129">Android for Work email settings</span></span>
<a id="android-for-work-email-settings" class="xliff"></a>

- <span data-ttu-id="6f5eb-130">**Aplicativo de email** – selecione **Gmail** ou **Nine Work**</span><span class="sxs-lookup"><span data-stu-id="6f5eb-130">**Email app** - Select either **Gmail** or **Nine Work**</span></span>
- <span data-ttu-id="6f5eb-131">**Servidor de email** – O nome do host do seu servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-131">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="6f5eb-132">**Atributo de nome de usuário do AAD** – esse nome é o atributo no AD (Active Directory) ou no Azure AD que será usado para gerar o nome de usuário para esse perfil de email.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-132">**Username attribute from AAD** - This name is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile.</span></span> <span data-ttu-id="6f5eb-133">Selecione o **Endereço SMTP Primário**, como o user1@contoso.com ou **Nome UPN**, como user1 ou user1@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-133">Select **Primary SMTP Address**, such as user1@contoso.com or **User Principal Name**, such as user1 or user1@contoso.com.</span></span>
- <span data-ttu-id="6f5eb-134">**Atributo de endereço de email do AAD** – Como o endereço de email do usuário em cada dispositivo cliente será gerado.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-134">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="6f5eb-135">Selecione **nome UPN** para usar o nome da entidade completo como o endereço de email ou **Nome de usuário**.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-135">Select **User Principal Name** to use the full principal name as the email address or **User name**.</span></span>
- <span data-ttu-id="6f5eb-136">**Método de autenticação** – Selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-136">**Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.</span></span>
    - <span data-ttu-id="6f5eb-137">Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS do cliente criado anteriormente para autenticar a conexão do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-137">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created to authenticate the Exchange connection.</span></span>
- <span data-ttu-id="6f5eb-138">**SSL** – Use a comunicação por protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-138">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>
- <span data-ttu-id="6f5eb-139">**Quantidade de emails a ser sincronizada** – Escolha o número de dias de emails que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todas as mensagens disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6f5eb-139">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="6f5eb-140">**Tipo de conteúdo a ser sincronizado** (somente Nine Work) – selecione os tipos de conteúdo que você deseja sincronizar com os dispositivos de:</span><span class="sxs-lookup"><span data-stu-id="6f5eb-140">**Content type to sync** (Nine Work only) - Select the content types that you want to synchronize to devices from:</span></span>
    - <span data-ttu-id="6f5eb-141">**Contatos**</span><span class="sxs-lookup"><span data-stu-id="6f5eb-141">**Contacts**</span></span>
    - <span data-ttu-id="6f5eb-142">**Calendário**</span><span class="sxs-lookup"><span data-stu-id="6f5eb-142">**Calendar**</span></span>
    - <span data-ttu-id="6f5eb-143">**Tarefas**</span><span class="sxs-lookup"><span data-stu-id="6f5eb-143">**Tasks**</span></span>
