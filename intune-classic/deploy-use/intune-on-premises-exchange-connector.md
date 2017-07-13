---
title: Exchange Connector para o EAS local
description: "Use a ferramenta do Connector para habilitar a comunicação entre o console de administração do Intune e o Exchange Server Local para MDM do Exchange ActiveSync."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41ff4212-a6f5-4374-8731-631f7560cff1
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c820a7071340599be161dd92441720f1eb7e9ff7
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="91fad-103">Instalar o Exchange Connector Local do Intune</span><span class="sxs-lookup"><span data-stu-id="91fad-103">Install the Intune On-premises Exchange Connector</span></span>
<a id="install-the-intune-on-premises-exchange-connector" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]


<span data-ttu-id="91fad-104">Para configurar uma conexão que habilita o Microsoft Intune a se comunicar com o Exchange Server que hospeda as caixas de correio dos dispositivos móveis, você precisa baixar e configurar o Exchange Connector Local do console de administração do Intune.</span><span class="sxs-lookup"><span data-stu-id="91fad-104">To set up a connection that enables Microsoft Intune to communicate with the Exchange Server that hosts the mailboxes for the mobile devices, you must download and configure the On-premises Exchange Connector from the Intune administration console.</span></span> <span data-ttu-id="91fad-105">O Intune dá suporte apenas a uma conexão do Exchange Connector de qualquer tipo por assinatura.</span><span class="sxs-lookup"><span data-stu-id="91fad-105">Intune only supports one Exchange Connector connection of any type per subscription.</span></span>

## <span data-ttu-id="91fad-106">Requisitos do Exchange Connector Local</span><span class="sxs-lookup"><span data-stu-id="91fad-106">On-premises Exchange Connector requirements</span></span>
<a id="on-premises-exchange-connector-requirements" class="xliff"></a>
<span data-ttu-id="91fad-107">A tabela a seguir lista os requisitos para o computador no qual o Exchange Connector Local será instalado.</span><span class="sxs-lookup"><span data-stu-id="91fad-107">The following table lists the requirements for the computer on which you install the On-premises Exchange Connector.</span></span>

|<span data-ttu-id="91fad-108">Requisito</span><span class="sxs-lookup"><span data-stu-id="91fad-108">Requirement</span></span>|<span data-ttu-id="91fad-109">Mais informações</span><span class="sxs-lookup"><span data-stu-id="91fad-109">More information</span></span>|
|---------------|--------------------|
|<span data-ttu-id="91fad-110">Sistemas operacionais</span><span class="sxs-lookup"><span data-stu-id="91fad-110">Operating systems</span></span>|<span data-ttu-id="91fad-111">O Intune dá suporte ao Exchange Connector Local em um computador que executa qualquer edição do Windows Server 2008 SP2 64 bits, do Windows Server 2008 R2, do Windows Server 2012 ou do Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="91fad-111">Intune supports the On-premises Exchange Connector on a computer that runs any edition of Windows Server 2008 SP2 64-bit, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2.</span></span><br /><br /><span data-ttu-id="91fad-112">O Connector não tem suporte em instalações Server Core.</span><span class="sxs-lookup"><span data-stu-id="91fad-112">The Connector is not supported on any Server Core installation.</span></span>|
|<span data-ttu-id="91fad-113">Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="91fad-113">Microsoft Exchange</span></span>|<span data-ttu-id="91fad-114">O Connector Local requer o Microsoft Exchange 2010 SP1 ou posterior, ou o Exchange Online Dedicado herdado.</span><span class="sxs-lookup"><span data-stu-id="91fad-114">On-premises Connectors require Microsoft Exchange 2010 SP1 or later or legacy Exchange Online Dedicated.</span></span> <span data-ttu-id="91fad-115">Para determinar se o seu ambiente do Exchange Online Dedicated está na configuração **nova** ou **herdada**, entre em contato com seu gerente de conta.</span><span class="sxs-lookup"><span data-stu-id="91fad-115">To determine if your Exchange Online Dedicated environment is in the **new** or **legacy** configuration, contact your account manager.</span></span>|
|<span data-ttu-id="91fad-116">Autoridade de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="91fad-116">Mobile device management authority</span></span>| <span data-ttu-id="91fad-117">[Defina a autoridade de gerenciamento de dispositivo móvel para o Intune](prerequisites-for-enrollment.md#step-2-set-mdm-authority).</span><span class="sxs-lookup"><span data-stu-id="91fad-117">[Set the mobile device management authority to Intune](prerequisites-for-enrollment.md#step-2-set-mdm-authority).</span></span>|
|<span data-ttu-id="91fad-118">Hardware</span><span class="sxs-lookup"><span data-stu-id="91fad-118">Hardware</span></span>|<span data-ttu-id="91fad-119">O computador em que você instala o conector requer uma CPU de 1,6 GHz com 2 GB de RAM e 10 GB de espaço livre em disco.</span><span class="sxs-lookup"><span data-stu-id="91fad-119">The computer on which you install the connector requires a 1.6 GHz CPU with 2 GB of RAM and 10 GB of free disk space.</span></span>|<span data-ttu-id="91fad-120">/intune/users-permissions-add</span><span class="sxs-lookup"><span data-stu-id="91fad-120">/intune/users-permissions-add</span></span>
|<span data-ttu-id="91fad-121">Sincronização do Active Directory</span><span class="sxs-lookup"><span data-stu-id="91fad-121">Active Directory synchronization</span></span>|<span data-ttu-id="91fad-122">Antes de usar qualquer o Connector para conectar o Intune ao Exchange Server, é necessário [configurar a sincronização do Active Directory](/intune/users-permissions-add) para que os usuários e grupos de segurança locais sejam sincronizados com a instância do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="91fad-122">Before you can use Connector to connect Intune to your Exchange Server, you must [set up Active Directory synchronization](/intune/users-permissions-add) so that your local users and security groups are synchronized with your instance of Azure Active Directory.</span></span>|
|<span data-ttu-id="91fad-123">Software adicional</span><span class="sxs-lookup"><span data-stu-id="91fad-123">Additional software</span></span>|<span data-ttu-id="91fad-124">Uma instalação completa do Microsoft .NET Framework 4.5 e do Windows PowerShell 2.0 deve ser feita no computador que hospeda o conector.</span><span class="sxs-lookup"><span data-stu-id="91fad-124">A full installation of Microsoft .NET Framework 4.5 and Windows PowerShell 2.0 must be installed on the computer that hosts the connector.</span></span>|
|<span data-ttu-id="91fad-125">Rede</span><span class="sxs-lookup"><span data-stu-id="91fad-125">Network</span></span>|<span data-ttu-id="91fad-126">O computador no qual o conector será instalado deve estar em um domínio que tenha uma relação de confiança com o domínio que hospeda o Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="91fad-126">The computer on which you install the connector must be in a domain that has a trust relationship to the domain that hosts your Exchange Server.</span></span><br /><br /><span data-ttu-id="91fad-127">O computador precisa de configurações para habilitá-lo a acessar o serviço Intune por meio dos firewalls e servidores proxy por Portas 80 e 443.</span><span class="sxs-lookup"><span data-stu-id="91fad-127">The computer requires configurations to enable it to access the Intune service through firewalls and proxy servers over Ports 80 and 443.</span></span> <span data-ttu-id="91fad-128">Os domínios usados pelo Intune incluem manage.microsoft.com, &#42;manage.microsoft.com e &#42;.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="91fad-128">Domains that are used by Intune include manage.microsoft.com, &#42;manage.microsoft.com, and &#42;.manage.microsoft.com.</span></span>|


### <span data-ttu-id="91fad-129">Requisitos de cmdlets do Exchange</span><span class="sxs-lookup"><span data-stu-id="91fad-129">Exchange cmdlet requirements</span></span>
<a id="exchange-cmdlet-requirements" class="xliff"></a>

<span data-ttu-id="91fad-130">É preciso criar uma conta de usuário do Active Directory que seja usada pelo Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="91fad-130">You must create an Active Directory user account that is used by the Intune Exchange Connector.</span></span> <span data-ttu-id="91fad-131">A conta deve ter permissão para executar os seguintes cmdlets do Windows PowerShell Exchange necessários:</span><span class="sxs-lookup"><span data-stu-id="91fad-131">The account must have permission to run the following required Windows PowerShell Exchange cmdlets:</span></span>


 -   <span data-ttu-id="91fad-132">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span><span class="sxs-lookup"><span data-stu-id="91fad-132">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span></span>
 -   <span data-ttu-id="91fad-133">Get-CasMailbox, Set-CasMailbox</span><span class="sxs-lookup"><span data-stu-id="91fad-133">Get-CasMailbox, Set-CasMailbox</span></span>
 -   <span data-ttu-id="91fad-134">Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy</span><span class="sxs-lookup"><span data-stu-id="91fad-134">Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy</span></span>
 -   <span data-ttu-id="91fad-135">Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule</span><span class="sxs-lookup"><span data-stu-id="91fad-135">Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule</span></span>
 -   <span data-ttu-id="91fad-136">Get-ActiveSyncDeviceStatistics</span><span class="sxs-lookup"><span data-stu-id="91fad-136">Get-ActiveSyncDeviceStatistics</span></span>
 -   <span data-ttu-id="91fad-137">Get-ActiveSyncDevice</span><span class="sxs-lookup"><span data-stu-id="91fad-137">Get-ActiveSyncDevice</span></span>
 -   <span data-ttu-id="91fad-138">Get-ExchangeServer</span><span class="sxs-lookup"><span data-stu-id="91fad-138">Get-ExchangeServer</span></span>
 -   <span data-ttu-id="91fad-139">Get-ActiveSyncDeviceClass</span><span class="sxs-lookup"><span data-stu-id="91fad-139">Get-ActiveSyncDeviceClass</span></span>
 -   <span data-ttu-id="91fad-140">Get-Recipient</span><span class="sxs-lookup"><span data-stu-id="91fad-140">Get-Recipient</span></span>
 -   <span data-ttu-id="91fad-141">Clear-ActiveSyncDevice, Remove-ActiveSyncDevice</span><span class="sxs-lookup"><span data-stu-id="91fad-141">Clear-ActiveSyncDevice, Remove-ActiveSyncDevice</span></span>
 -   <span data-ttu-id="91fad-142">Set-ADServerSettings</span><span class="sxs-lookup"><span data-stu-id="91fad-142">Set-ADServerSettings</span></span>
 -   <span data-ttu-id="91fad-143">Get-Command</span><span class="sxs-lookup"><span data-stu-id="91fad-143">Get-Command</span></span>

## <span data-ttu-id="91fad-144">Baixe o pacote de instalação de software do Exchange Connector Local</span><span class="sxs-lookup"><span data-stu-id="91fad-144">Download the On-premises Exchange Connector software installation package</span></span>
<a id="download-the-on-premises-exchange-connector-software-installation-package" class="xliff"></a>

1. <span data-ttu-id="91fad-145">Em um sistema operacional Windows Server com suporte para o Exchange Connector Local, abra o [console de administração do Microsoft Intune](https://manage.microsoft.com) (https://manage.microsoft.com) com uma conta de usuário que seja um administrador no locatário do Exchange e que tenha uma licença para usar o Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="91fad-145">On a supported Windows Server operating system for the On-premises Exchange Connector, open the [Microsoft Intune administration console](https://manage.microsoft.com) (https://manage.microsoft.com) with a user account that is an administrator in the Exchange tenant and that has a license to use Exchange Server.</span></span>
<span data-ttu-id="91fad-146">![Abra a configuração da Conexão com o Exchange](../media/ExchangeConnector.gif)</span><span class="sxs-lookup"><span data-stu-id="91fad-146">![Open set up Exchange Connection](../media/ExchangeConnector.gif)</span></span>

2.  <span data-ttu-id="91fad-147">No painel de atalhos do espaço de trabalho, escolha **Admin**>**Gerenciamento de Dispositivo Móvel** > **Microsoft Exchange**>**Configurar Conexão com o Exchange**.</span><span class="sxs-lookup"><span data-stu-id="91fad-147">In the workspace shortcuts pane, choose **Admin**>**Mobile Device Management** > **Microsoft Exchange**>**Setup Exchange Connection**.</span></span>

3.  <span data-ttu-id="91fad-148">Na página **Configurar a Conexão do Exchange**, clique em **Baixar o On-Premises Connector**.</span><span class="sxs-lookup"><span data-stu-id="91fad-148">On the **Setup Exchange Connection** page, choose **Download On-Premises Connector**.</span></span>

4.  <span data-ttu-id="91fad-149">O Exchange Connector Local vem em uma pasta compactada (.zip) que pode ser aberta ou salva.</span><span class="sxs-lookup"><span data-stu-id="91fad-149">The On-premises Exchange Connector is contained in a compressed (.zip) folder that can be opened or saved.</span></span> <span data-ttu-id="91fad-150">Na caixa de diálogo **Download de Arquivos**, clique em **Salvar** para armazenar a pasta compactada em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="91fad-150">In the **File Download** dialog box, choose **Save** to store the compressed folder to a secure location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91fad-151">Não renomeie ou mova os arquivos que estão dentro da pasta do Exchange Connector Local.</span><span class="sxs-lookup"><span data-stu-id="91fad-151">Do not rename or move the files that are in the On-premises Exchange Connector folder.</span></span> <span data-ttu-id="91fad-152">Mover ou renomear o conteúdo da pasta causará falha na instalação.</span><span class="sxs-lookup"><span data-stu-id="91fad-152">Moving or renaming the folder's contents will cause the installation to fail.</span></span>

## <span data-ttu-id="91fad-153">Instalar e configurar o Exchange Connector Local do Intune</span><span class="sxs-lookup"><span data-stu-id="91fad-153">Install and configure the Intune On-premises Exchange Connector</span></span>
<a id="install-and-configure-the-intune-on-premises-exchange-connector" class="xliff"></a>
<span data-ttu-id="91fad-154">Execute as seguintes etapas para instalar o Exchange Connector Local do Intune.</span><span class="sxs-lookup"><span data-stu-id="91fad-154">Perform the following steps to install the Intune On-premises Exchange Connector.</span></span> <span data-ttu-id="91fad-155">O Exchange Connector Local pode ser instalado somente uma vez por assinatura do Intune e somente em um computador.</span><span class="sxs-lookup"><span data-stu-id="91fad-155">The On-premises Exchange Connector can only be installed once per Intune subscription, and only on one computer.</span></span> <span data-ttu-id="91fad-156">Se você tentar configurar um Exchange Connector Local adicional, a nova conexão substituirá a original.</span><span class="sxs-lookup"><span data-stu-id="91fad-156">If you try to configure an additional On-premises Exchange Connector, the new connection will replace the original one.</span></span>

1.  <span data-ttu-id="91fad-157">Em um sistema operacional com suporte para o Connector Local, extraia os arquivos em **Exchange_Connector_Setup.zip** para um local seguro.</span><span class="sxs-lookup"><span data-stu-id="91fad-157">On a supported operating system for the On-premises Connector, extract the files in **Exchange_Connector_Setup.zip** to a secure location.</span></span>

2.  <span data-ttu-id="91fad-158">Depois que os arquivos forem extraídos, abra a pasta extraída e clique duas vezes em **Exchange_Connector_Setup.exe** para instalar o Exchange Connector Local.</span><span class="sxs-lookup"><span data-stu-id="91fad-158">After the files are extracted, open the extracted folder and double-click **Exchange_Connector_Setup.exe** to install the On-premises Exchange Connector.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="91fad-159">Se a pasta de destino não for um local seguro, exclua o arquivo de certificado **WindowsIntune.accountcert** após instalar o Connector Local.</span><span class="sxs-lookup"><span data-stu-id="91fad-159">If the destination folder is not a secure location, you should delete the certificate file **WindowsIntune.accountcert** after you install the On-premises Connector.</span></span>

3.  <span data-ttu-id="91fad-160">Na caixa de diálogo **Microsoft Intune Exchange Connector**, selecione **Microsoft Exchange Server Local** ou **Microsoft Exchange Server Hospedado**.</span><span class="sxs-lookup"><span data-stu-id="91fad-160">In the **Microsoft Intune Exchange Connector** dialog box, select either **On-premises Microsoft Exchange Server** or **Hosted Microsoft Exchange Server**.</span></span>

  ![Escolha o tipo de Exchange Server](../media/IntuneSA1dconfigureExchConnector.png)

  <span data-ttu-id="91fad-162">Para um Exchange Server Local, forneça o nome do servidor ou um nome de domínio totalmente qualificado do Exchange Server que hospeda a função de **Servidor de Acesso para Cliente**.</span><span class="sxs-lookup"><span data-stu-id="91fad-162">For an On-premises Exchange server, provide either the server name or the fully-qualified domain name of the Exchange server that hosts the **Client Access Server** role.</span></span>

  <span data-ttu-id="91fad-163">Para um Exchange Server hospedado, forneça o endereço do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="91fad-163">For a hosted Exchange server, provide the Exchange server address.</span></span> <span data-ttu-id="91fad-164">Para encontrar o URL do Exchange Server Hospedado:</span><span class="sxs-lookup"><span data-stu-id="91fad-164">To find the hosted Exchange server URL:</span></span>

    1. <span data-ttu-id="91fad-165">Abra o Outlook Web App para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="91fad-165">Open the Outlook Web App for Office 365.</span></span>

    2. <span data-ttu-id="91fad-166">Selecione o ícone **?**</span><span class="sxs-lookup"><span data-stu-id="91fad-166">Choose the **?**</span></span> <span data-ttu-id="91fad-167">no canto superior esquerdo e selecione **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="91fad-167">icon at the upper left, and then select **About**.</span></span>

    3. <span data-ttu-id="91fad-168">Localize o valor **Servidor Externo POP** .</span><span class="sxs-lookup"><span data-stu-id="91fad-168">Locate the **POP External Server** value.</span></span>

    4. <span data-ttu-id="91fad-169">Clique em **Servidor Proxy** para especificar as configurações do servidor proxy para seu Exchange Server hospedado.</span><span class="sxs-lookup"><span data-stu-id="91fad-169">Choose **Proxy Server** to specify proxy server settings for your hosted Exchange server.</span></span>
        1. <span data-ttu-id="91fad-170">Selecione **Usar um servidor proxy ao sincronizar informações do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="91fad-170">Select **Use a proxy server when synchronizing mobile device information**.</span></span>

        2. <span data-ttu-id="91fad-171">Insira o **nome do servidor proxy** e o **número da porta** a serem usados para acessar o servidor.</span><span class="sxs-lookup"><span data-stu-id="91fad-171">Enter the **proxy server name** and the **port number** to be used to access the server.</span></span>

        3. <span data-ttu-id="91fad-172">Se for necessário fornecer as credenciais para acessar o servidor proxy, selecione **Usar credenciais para se conectar ao servidor proxy**.</span><span class="sxs-lookup"><span data-stu-id="91fad-172">If it's necessary to provide user credentials to access the proxy server, select **Use credentials to connect to the proxy server**.</span></span> <span data-ttu-id="91fad-173">Em seguida, digite o **domínio\usuário** e a **senha**.</span><span class="sxs-lookup"><span data-stu-id="91fad-173">Then enter the **domain\user** and the **password**.</span></span>

        4. <span data-ttu-id="91fad-174">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="91fad-174">Choose **OK**.</span></span>

    5. <span data-ttu-id="91fad-175">Nos campos **Usuário (Domínio\usuário)** e **Senha**, insira as credenciais necessárias para se conectar ao Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="91fad-175">In the **User (Domain\user)** and **Password** fields, enter the credentials that are necessary to connect to your Exchange server.</span></span>

    6.  <span data-ttu-id="91fad-176">Forneça as credenciais administrativas necessárias para enviar notificações para a caixa de entrada do Exchange Server do usuário.</span><span class="sxs-lookup"><span data-stu-id="91fad-176">Provide the necessary administrative credentials to send notifications to a user’s Exchange Server mailbox.</span></span> <span data-ttu-id="91fad-177">Você pode configurar essas notificações com políticas de Acesso Condicional no Intune.</span><span class="sxs-lookup"><span data-stu-id="91fad-177">You can configure these notifications with Conditional Access policies in Intune.</span></span>

        <span data-ttu-id="91fad-178">Verifique se o serviço Descoberta Automática e os Serviços Web do Exchange estão configurados no Servidor de Acesso para Cliente do Exchange.</span><span class="sxs-lookup"><span data-stu-id="91fad-178">Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access Server.</span></span> <span data-ttu-id="91fad-179">Para obter mais informações, consulte [Servidor de Acesso para Cliente](https://technet.microsoft.com/library/dd298114.aspx).</span><span class="sxs-lookup"><span data-stu-id="91fad-179">For more information, see [Client Access server](https://technet.microsoft.com/library/dd298114.aspx).</span></span>

    7.  <span data-ttu-id="91fad-180">No campo **Senha**, forneça a senha da conta para habilitar o Intune a acessar o Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="91fad-180">In the **Password** field, provide the password for this account to enable Intune to access the Exchange Server.</span></span>

    8. <span data-ttu-id="91fad-181">Selecione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="91fad-181">Choose **Connect**.</span></span>

<span data-ttu-id="91fad-182">Podem ser necessários alguns minutos para que a conexão seja configurada.</span><span class="sxs-lookup"><span data-stu-id="91fad-182">It might take a few minutes for the connection to be configured.</span></span>

<span data-ttu-id="91fad-183">Durante a configuração, o Exchange Connector armazena as configurações de proxy para habilitar o acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="91fad-183">During configuration, the Exchange Connector stores your proxy settings to enable access to the Internet.</span></span> <span data-ttu-id="91fad-184">Se as configurações de proxy forem alteradas, você precisará reconfigurar o Exchange Connector para aplicar as configurações de proxy atualizadas ao Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="91fad-184">If your proxy settings change, you will have to reconfigure the Exchange Connector to apply the updated proxy settings to the Exchange Connector.</span></span>

<span data-ttu-id="91fad-185">Após o Exchange Connector configurar a conexão, os dispositivos móveis associados aos usuários que são gerenciados no Exchange Connector são automaticamente sincronizados e adicionados ao Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="91fad-185">After the Exchange Connector sets up the connection, mobile devices that are associated with users that are managed in Exchange Connector are automatically synchronized and added to the Exchange Connector.</span></span> <span data-ttu-id="91fad-186">Pode levar algum tempo até que a sincronização seja concluída.</span><span class="sxs-lookup"><span data-stu-id="91fad-186">This synchronization might take some time to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="91fad-187">Se você tiver instalado o Exchange Connector Local e se em algum momento a conexão com o Exchange for excluída, você deverá desinstalar o Exchange Connector Local do computador em que ele foi instalado.</span><span class="sxs-lookup"><span data-stu-id="91fad-187">If you have installed the On-premises Exchange Connector, and if at some point you delete the Exchange connection, you must uninstall the On-premises Exchange Connector from the computer onto which it was installed.</span></span>

## <span data-ttu-id="91fad-188">Validar a conexão do Exchange</span><span class="sxs-lookup"><span data-stu-id="91fad-188">Validate the Exchange connection</span></span>
<a id="validate-the-exchange-connection" class="xliff"></a>

<span data-ttu-id="91fad-189">Após configurar o Exchange Connector com êxito, você pode exibir o status da conexão e a última tentativa de sincronização bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="91fad-189">After you have successfully configured the Exchange Connector, you can view the status of the connection and the last successful synchronization attempt.</span></span> <span data-ttu-id="91fad-190">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha o espaço de trabalho **ADMIN**.</span><span class="sxs-lookup"><span data-stu-id="91fad-190">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose the **ADMIN** workspace.</span></span> <span data-ttu-id="91fad-191">m **Gerenciamento de Dispositivo Móvel**, escolha **Microsoft Exchange** e confirme se os detalhes fornecidos aparecem em **Informações sobre a Conexão com o Exchange**.</span><span class="sxs-lookup"><span data-stu-id="91fad-191">Under **Mobile Device Management**, choose **Microsoft Exchange**, and then validate that the details you provided appear under **Exchange Connection Information**.</span></span>


<span data-ttu-id="91fad-192">Você também pode verificar a hora e data da última tentativa de sincronização bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="91fad-192">You can also check the time and date of the last successful synchronization attempt.</span></span>
