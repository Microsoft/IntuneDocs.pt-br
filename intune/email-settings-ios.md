---
title: "Configurações de email do Intune para dispositivos iOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para configurar as conexões de email em dispositivos iOS."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9f0fa6af-3669-439a-bd0d-75d8b1a0b135
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dcac410ae5c20b5942bf37f5eaa9a46205a4cc07
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="f8214-103">Configurações de perfil de email para dispositivos iOS no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f8214-103">Email profile settings for iOS devices in Microsoft Intune</span></span>
<a id="email-profile-settings-for-ios-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



- <span data-ttu-id="f8214-104">**Servidor de email** – O nome do host do seu servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="f8214-104">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="f8214-105">**Nome da conta** – O nome de exibição para a conta de email que será exibida aos usuários em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f8214-105">**Account name** - The display name for the email account as it will appear to users on their devices.</span></span>
- <span data-ttu-id="f8214-106">**Atributo de nome de usuário do AAD** – Esse é o atributo no AD (Active Directory) ou Azure AD, que será usado para gerar o nome de usuário para este perfil de email.</span><span class="sxs-lookup"><span data-stu-id="f8214-106">**Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile.</span></span> <span data-ttu-id="f8214-107">Selecione o **Endereço SMTP Primário**, como o **user1@contoso.com** ou **Nome UPN**, como **user1** ou **user1@contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="f8214-107">Select **Primary SMTP Address**, such as **user1@contoso.com** or **User Principal Name**, such as **user1** or **user1@contoso.com**.</span></span>
- <span data-ttu-id="f8214-108">**Atributo de endereço de email do AAD** – Como o endereço de email do usuário em cada dispositivo cliente será gerado.</span><span class="sxs-lookup"><span data-stu-id="f8214-108">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="f8214-109">Selecione **Endereço SMTP Primário** para usar o endereço SMTP primário para fazer logon no Exchange ou use **Nome UPN** para usar o nome da entidade completo como o endereço de email.</span><span class="sxs-lookup"><span data-stu-id="f8214-109">Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use **User Principal Name** to use the full principal name as the email address.</span></span>
- <span data-ttu-id="f8214-110">**Método de autenticação** – Selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.</span><span class="sxs-lookup"><span data-stu-id="f8214-110">**Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.</span></span>
    - <span data-ttu-id="f8214-111">Se você selecionou **Certificado**, escolha um cliente SCEP ou perfil de certificado PKCS criado anteriormente para ser usado para autenticar a conexão do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f8214-111">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created that will be used to authenticate the Exchange connection.</span></span>
- <span data-ttu-id="f8214-112">**SSL** – Use a comunicação por protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="f8214-112">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>
- <span data-ttu-id="f8214-113">**S/MIME** - Enviar email de saída usando a assinatura de S/MIME.</span><span class="sxs-lookup"><span data-stu-id="f8214-113">**S/MIME** - Send outgoing email using S/MIME signing.</span></span>
    - <span data-ttu-id="f8214-114">Se você selecionou **Certificado**, escolha um cliente SCEP ou perfil de certificado PKCS criado anteriormente para ser usado para autenticar a conexão do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f8214-114">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created that will be used to authenticate the Exchange connection.</span></span>
- <span data-ttu-id="f8214-115">**Quantidade de emails a ser sincronizada** – Escolha o número de dias de emails que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todas as mensagens disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f8214-115">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="f8214-116">**Permitir que as mensagens sejam movidas para outras contas de email** – Isso permite que os usuários movam mensagens de email entre contas diferentes que podem estar configuradas em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f8214-116">**Allow messages to be moved to other email accounts** - This allows users to move email messages between different accounts they have configured on their device.</span></span>
- <span data-ttu-id="f8214-117">**Permitir o envio de email de aplicativos de terceiros** – Permita que o usuário selecione este perfil como a conta padrão para enviar email e permitir que aplicativos de terceiros abram o email no aplicativo de email nativo, por exemplo, para anexar arquivos de email.</span><span class="sxs-lookup"><span data-stu-id="f8214-117">**Allow email to be sent from third party applications** - Allow the user to select this profile as the default account for sending email, and allow third-party applications to open email in the native email app, for example, to attach files to email.</span></span>
- <span data-ttu-id="f8214-118">**Sincronizar endereços de email usados recentemente** – Esse recurso permite que os usuários sincronizem a lista de endereços de email usados recentemente no dispositivo com o servidor.</span><span class="sxs-lookup"><span data-stu-id="f8214-118">**Synchronize recently used email addresses** - This feature allows users to synchronize the list of email addresses that have been recently used on the device with the server.</span></span>
