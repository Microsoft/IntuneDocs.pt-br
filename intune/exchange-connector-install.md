---
title: Configurar o Exchange Connector para o EAS local com o Intune
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune no Azure: Exchange ActiveSync MDM – Use a ferramenta Connector para habilitar a comunicação entre o Intune e o Exchange Server local"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9f4a310078a30f7dfefe66a9aba60cc74ad4e29b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="3c790-103">Configurar o Exchange Connector local do Intune na versão prévia do Microsoft Intune no Azure</span><span class="sxs-lookup"><span data-stu-id="3c790-103">Set up the Intune on-premises Exchange Connector in Microsoft Intune Azure preview</span></span>
<a id="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure-preview" class="xliff"></a>

<span data-ttu-id="3c790-104">Os ambientes do Exchange Server local podem usar o conector do Exchange local do Intune para gerenciar o acesso de dispositivos a caixas de correio do Exchange local, levando em conta se os dispositivos estão registrados no Intune e em conformidade com as políticas de conformidade do dispositivo do Intune.</span><span class="sxs-lookup"><span data-stu-id="3c790-104">On-premises Exchange Server environments can use the Intune on-premises Exchange connector to manage devices access to on-premises Exchange mailboxes based on whether or not the devices are enrolled into Intune and compliant with Intune device compliance policies.</span></span> <span data-ttu-id="3c790-105">O Exchange Connector local também é responsável pela descoberta de dispositivos móveis que se conectam a Exchange Servers locais, com a sincronização do registro existente do EAS (Exchange Active Sync) com o Intune.</span><span class="sxs-lookup"><span data-stu-id="3c790-105">The on-premises Exchange connector is also responsible for discovering mobile devices that connect to on-premises Exchange Servers by synchronizing the existing Exchange Active Sync (EAS) record with Intune.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c790-106">O Intune dá suporte apenas a uma conexão do Exchange Connector local de qualquer tipo por assinatura.</span><span class="sxs-lookup"><span data-stu-id="3c790-106">Intune only supports one on-premises Exchange Connector connection of any type per subscription.</span></span>

<span data-ttu-id="3c790-107">Para configurar uma conexão que habilita o Microsoft Intune a se comunicar com o Exchange Server local, você precisa seguir as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="3c790-107">To set up a connection that enables Microsoft Intune to communicate with the on-premises Exchange Server, you need to follow the steps below:</span></span>

1.  <span data-ttu-id="3c790-108">Baixar o Exchange Connector local do Intune no portal do Intune.</span><span class="sxs-lookup"><span data-stu-id="3c790-108">Download the Intune on-premises Exchange Connector from the Intune portal.</span></span>
2.  <span data-ttu-id="3c790-109">Instalar e configurar o Exchange Connector local do Intune.</span><span class="sxs-lookup"><span data-stu-id="3c790-109">Install and configure the Intune on-premises Exchange connector.</span></span>
3.  <span data-ttu-id="3c790-110">Validar a conexão do Exchange.</span><span class="sxs-lookup"><span data-stu-id="3c790-110">Validate the Exchange connection.</span></span>

## <span data-ttu-id="3c790-111">Requisitos do Exchange Connector Local</span><span class="sxs-lookup"><span data-stu-id="3c790-111">On-premises Exchange Connector requirements</span></span>
<a id="on-premises-exchange-connector-requirements" class="xliff"></a>
<span data-ttu-id="3c790-112">A tabela a seguir lista os requisitos para o computador no qual o Exchange Connector Local será instalado.</span><span class="sxs-lookup"><span data-stu-id="3c790-112">The following table lists the requirements for the computer on which you install the On-premises Exchange Connector.</span></span>

|<span data-ttu-id="3c790-113">Requisito</span><span class="sxs-lookup"><span data-stu-id="3c790-113">Requirement</span></span>|<span data-ttu-id="3c790-114">Mais informações</span><span class="sxs-lookup"><span data-stu-id="3c790-114">More information</span></span>|
|---------------|--------------------|
|<span data-ttu-id="3c790-115">Sistemas operacionais</span><span class="sxs-lookup"><span data-stu-id="3c790-115">Operating systems</span></span>|<span data-ttu-id="3c790-116">O Intune dá suporte ao Exchange Connector Local em um computador que executa qualquer edição do Windows Server 2008 SP2 64 bits, do Windows Server 2008 R2, do Windows Server 2012 ou do Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="3c790-116">Intune supports the On-premises Exchange Connector on a computer that runs any edition of Windows Server 2008 SP2 64-bit, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2.</span></span><br /><br /><span data-ttu-id="3c790-117">O Connector não tem suporte em instalações Server Core.</span><span class="sxs-lookup"><span data-stu-id="3c790-117">The Connector is not supported on any Server Core installation.</span></span>|
|<span data-ttu-id="3c790-118">Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="3c790-118">Microsoft Exchange</span></span>|<span data-ttu-id="3c790-119">O Connector Local requer o Microsoft Exchange 2010 SP1 ou posterior, ou o Exchange Online Dedicado herdado.</span><span class="sxs-lookup"><span data-stu-id="3c790-119">On-premises Connectors require Microsoft Exchange 2010 SP1 or later or legacy Exchange Online Dedicated.</span></span> <span data-ttu-id="3c790-120">Para determinar se o seu ambiente do Exchange Online Dedicated está na configuração **nova** ou **herdada**, entre em contato com seu gerente de conta.</span><span class="sxs-lookup"><span data-stu-id="3c790-120">To determine if your Exchange Online Dedicated environment is in the **new** or **legacy** configuration, contact your account manager.</span></span>|
|<span data-ttu-id="3c790-121">Autoridade de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="3c790-121">Mobile device management authority</span></span>| <span data-ttu-id="3c790-122">[Defina a autoridade de gerenciamento de dispositivo móvel para o Intune](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set).</span><span class="sxs-lookup"><span data-stu-id="3c790-122">[Set the mobile device management authority to Intune](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set).</span></span>|
|<span data-ttu-id="3c790-123">Hardware</span><span class="sxs-lookup"><span data-stu-id="3c790-123">Hardware</span></span>|<span data-ttu-id="3c790-124">O computador em que você instala o conector requer uma CPU de 1,6 GHz com 2 GB de RAM e 10 GB de espaço livre em disco.</span><span class="sxs-lookup"><span data-stu-id="3c790-124">The computer on which you install the connector requires a 1.6 GHz CPU with 2 GB of RAM and 10 GB of free disk space.</span></span>|<span data-ttu-id="3c790-125">users-permissions-add.md</span><span class="sxs-lookup"><span data-stu-id="3c790-125">users-permissions-add.md</span></span>
|<span data-ttu-id="3c790-126">Sincronização do Active Directory</span><span class="sxs-lookup"><span data-stu-id="3c790-126">Active Directory synchronization</span></span>|<span data-ttu-id="3c790-127">Antes de usar qualquer o Connector para conectar o Intune ao Exchange Server, é necessário [configurar a sincronização do Active Directory](users-permissions-add.md) para que os usuários e grupos de segurança locais sejam sincronizados com a instância do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3c790-127">Before you can use Connector to connect Intune to your Exchange Server, you must [set up Active Directory synchronization](users-permissions-add.md) so that your local users and security groups are synchronized with your instance of Azure Active Directory.</span></span>|
|<span data-ttu-id="3c790-128">Software adicional</span><span class="sxs-lookup"><span data-stu-id="3c790-128">Additional software</span></span>|<span data-ttu-id="3c790-129">Uma instalação completa do Microsoft .NET Framework 4.5 e do Windows PowerShell 2.0 deve ser feita no computador que hospeda o conector.</span><span class="sxs-lookup"><span data-stu-id="3c790-129">A full installation of Microsoft .NET Framework 4.5 and Windows PowerShell 2.0 must be installed on the computer that hosts the connector.</span></span>|
|<span data-ttu-id="3c790-130">Rede</span><span class="sxs-lookup"><span data-stu-id="3c790-130">Network</span></span>|<span data-ttu-id="3c790-131">O computador no qual o conector será instalado deve estar em um domínio que tenha uma relação de confiança com o domínio que hospeda o Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="3c790-131">The computer on which you install the connector must be in a domain that has a trust relationship to the domain that hosts your Exchange Server.</span></span><br /><br /><span data-ttu-id="3c790-132">O computador precisa de configurações para habilitá-lo a acessar o serviço Intune por meio dos firewalls e servidores proxy por Portas 80 e 443.</span><span class="sxs-lookup"><span data-stu-id="3c790-132">The computer requires configurations to enable it to access the Intune service through firewalls and proxy servers over Ports 80 and 443.</span></span> <span data-ttu-id="3c790-133">Os domínios usados pelo Intune incluem manage.microsoft.com, &#42;manage.microsoft.com e &#42;.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3c790-133">Domains that are used by Intune include manage.microsoft.com, &#42;manage.microsoft.com, and &#42;.manage.microsoft.com.</span></span>|


### <span data-ttu-id="3c790-134">Requisitos de cmdlets do Exchange</span><span class="sxs-lookup"><span data-stu-id="3c790-134">Exchange cmdlet requirements</span></span>
<a id="exchange-cmdlet-requirements" class="xliff"></a>

<span data-ttu-id="3c790-135">É preciso criar uma conta de usuário do Active Directory que seja usada pelo Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="3c790-135">You must create an Active Directory user account that is used by the Intune Exchange Connector.</span></span> <span data-ttu-id="3c790-136">A conta deve ter permissão para executar os seguintes cmdlets do Windows PowerShell Exchange necessários:</span><span class="sxs-lookup"><span data-stu-id="3c790-136">The account must have permission to run the following required Windows PowerShell Exchange cmdlets:</span></span>


 -   <span data-ttu-id="3c790-137">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span><span class="sxs-lookup"><span data-stu-id="3c790-137">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span></span>
 -   <span data-ttu-id="3c790-138">Get-CasMailbox, Set-CasMailbox</span><span class="sxs-lookup"><span data-stu-id="3c790-138">Get-CasMailbox, Set-CasMailbox</span></span>
 -   <span data-ttu-id="3c790-139">Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy</span><span class="sxs-lookup"><span data-stu-id="3c790-139">Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy</span></span>
 -   <span data-ttu-id="3c790-140">Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule</span><span class="sxs-lookup"><span data-stu-id="3c790-140">Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule</span></span>
 -   <span data-ttu-id="3c790-141">Get-ActiveSyncDeviceStatistics</span><span class="sxs-lookup"><span data-stu-id="3c790-141">Get-ActiveSyncDeviceStatistics</span></span>
 -   <span data-ttu-id="3c790-142">Get-ActiveSyncDevice</span><span class="sxs-lookup"><span data-stu-id="3c790-142">Get-ActiveSyncDevice</span></span>
 -   <span data-ttu-id="3c790-143">Get-ExchangeServer</span><span class="sxs-lookup"><span data-stu-id="3c790-143">Get-ExchangeServer</span></span>
 -   <span data-ttu-id="3c790-144">Get-ActiveSyncDeviceClass</span><span class="sxs-lookup"><span data-stu-id="3c790-144">Get-ActiveSyncDeviceClass</span></span>
 -   <span data-ttu-id="3c790-145">Get-Recipient</span><span class="sxs-lookup"><span data-stu-id="3c790-145">Get-Recipient</span></span>
 -   <span data-ttu-id="3c790-146">Clear-ActiveSyncDevice, Remove-ActiveSyncDevice</span><span class="sxs-lookup"><span data-stu-id="3c790-146">Clear-ActiveSyncDevice, Remove-ActiveSyncDevice</span></span>
 -   <span data-ttu-id="3c790-147">Set-ADServerSettings</span><span class="sxs-lookup"><span data-stu-id="3c790-147">Set-ADServerSettings</span></span>
 -   <span data-ttu-id="3c790-148">Get-Command</span><span class="sxs-lookup"><span data-stu-id="3c790-148">Get-Command</span></span>

## <span data-ttu-id="3c790-149">Baixe o pacote de instalação de software do Exchange Connector Local</span><span class="sxs-lookup"><span data-stu-id="3c790-149">Download the On-premises Exchange Connector software installation package</span></span>
<a id="download-the-on-premises-exchange-connector-software-installation-package" class="xliff"></a>

1. <span data-ttu-id="3c790-150">Em um sistema operacional Windows Server com suporte para o Exchange Connector Local, abra o [portal do Azure](http://portal.azure.com) e entre com uma conta de usuário que é um administrador no servidor Exchange local e que tem uma licença para usar o Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="3c790-150">On a supported Windows Server operating system for the On-premises Exchange Connector, open the [Azure portal](http://portal.azure.com) and sign in with a user account that is an administrator in the on-premises Exchange server, and that has a license to use Exchange Server.</span></span>

2. <span data-ttu-id="3c790-151">Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="3c790-151">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="3c790-152">Escolha **Intune**. O Painel do Intune é aberto. Escolha **Acesso local**.</span><span class="sxs-lookup"><span data-stu-id="3c790-152">Choose **Intune**, the Intune Dashboard opens, choose **On-premises access**.</span></span>

4. <span data-ttu-id="3c790-153">Na folha **Acesso local – Conector do Exchange ActiveSync**, na seção **Configuração**, escolha **Baixar o conector local**.</span><span class="sxs-lookup"><span data-stu-id="3c790-153">On the **On-premises access - Exchange ActiveSync connector** blade, from the **Setup** section, choose **Download the on-premises connector**.</span></span>

5.  <span data-ttu-id="3c790-154">O Exchange Connector Local vem em uma pasta compactada (.zip) que pode ser aberta ou salva.</span><span class="sxs-lookup"><span data-stu-id="3c790-154">The On-premises Exchange Connector is contained in a compressed (.zip) folder that can be opened or saved.</span></span> <span data-ttu-id="3c790-155">Na caixa de diálogo **Download de Arquivos**, clique em **Salvar** para armazenar a pasta compactada em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="3c790-155">In the **File Download** dialog box, choose **Save** to store the compressed folder to a secure location.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3c790-156">Não renomeie nem mova os arquivos que estão na pasta do Exchange Connector local.</span><span class="sxs-lookup"><span data-stu-id="3c790-156">Do not rename or move the files that are in the on-premises Exchange Connector folder.</span></span> <span data-ttu-id="3c790-157">Mover ou renomear o conteúdo da pasta causará falha na instalação do Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="3c790-157">Moving or renaming the folder's contents will cause the Exchange Connector installation to fail.</span></span>

## <span data-ttu-id="3c790-158">Instalar e configurar o Exchange Connector Local do Intune</span><span class="sxs-lookup"><span data-stu-id="3c790-158">Install and configure the Intune On-premises Exchange Connector</span></span>
<a id="install-and-configure-the-intune-on-premises-exchange-connector" class="xliff"></a>
<span data-ttu-id="3c790-159">Execute as seguintes etapas para instalar o Exchange Connector Local do Intune.</span><span class="sxs-lookup"><span data-stu-id="3c790-159">Perform the following steps to install the Intune On-premises Exchange Connector.</span></span> <span data-ttu-id="3c790-160">O Exchange Connector Local pode ser instalado somente uma vez por assinatura do Intune e somente em um computador.</span><span class="sxs-lookup"><span data-stu-id="3c790-160">The On-premises Exchange Connector can only be installed once per Intune subscription, and only on one computer.</span></span> <span data-ttu-id="3c790-161">Se você tentar configurar um Exchange Connector Local adicional, a nova conexão substituirá a original.</span><span class="sxs-lookup"><span data-stu-id="3c790-161">If you try to configure an additional On-premises Exchange Connector, the new connection will replace the original one.</span></span>

1.  <span data-ttu-id="3c790-162">Em um sistema operacional com suporte para o Connector Local, extraia os arquivos em **Exchange_Connector_Setup.zip** para um local seguro.</span><span class="sxs-lookup"><span data-stu-id="3c790-162">On a supported operating system for the On-premises Connector, extract the files in **Exchange_Connector_Setup.zip** to a secure location.</span></span>

2.  <span data-ttu-id="3c790-163">Depois que os arquivos forem extraídos, abra a pasta extraída e clique duas vezes em **Exchange_Connector_Setup.exe** para instalar o Exchange Connector Local.</span><span class="sxs-lookup"><span data-stu-id="3c790-163">After the files are extracted, open the extracted folder and double-click **Exchange_Connector_Setup.exe** to install the On-premises Exchange Connector.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3c790-164">Se a pasta de destino não for um local seguro, exclua o arquivo de certificado **WindowsIntune.accountcert** após instalar o Connector Local.</span><span class="sxs-lookup"><span data-stu-id="3c790-164">If the destination folder is not a secure location, you should delete the certificate file **WindowsIntune.accountcert** after you install the On-premises Connector.</span></span>

3.  <span data-ttu-id="3c790-165">Na caixa de diálogo **Microsoft Intune Exchange Connector**, selecione **Microsoft Exchange Server Local** ou **Microsoft Exchange Server Hospedado**.</span><span class="sxs-lookup"><span data-stu-id="3c790-165">In the **Microsoft Intune Exchange Connector** dialog box, select either **On-premises Microsoft Exchange Server** or **Hosted Microsoft Exchange Server**.</span></span>

  ![Escolha o tipo de Exchange Server](./media/intune-sa-exchange-connector-config.png)

  <span data-ttu-id="3c790-167">Para um Exchange Server Local, forneça o nome do servidor ou um nome de domínio totalmente qualificado do Exchange Server que hospeda a função de **Servidor de Acesso para Cliente**.</span><span class="sxs-lookup"><span data-stu-id="3c790-167">For an On-premises Exchange server, provide either the server name or the fully-qualified domain name of the Exchange server that hosts the **Client Access Server** role.</span></span>

  <span data-ttu-id="3c790-168">Para um Exchange Server hospedado, forneça o endereço do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="3c790-168">For a hosted Exchange server, provide the Exchange server address.</span></span> <span data-ttu-id="3c790-169">Para encontrar o URL do Exchange Server Hospedado:</span><span class="sxs-lookup"><span data-stu-id="3c790-169">To find the hosted Exchange server URL:</span></span>

    1. <span data-ttu-id="3c790-170">Abra o Outlook Web App para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="3c790-170">Open the Outlook Web App for Office 365.</span></span>

    2. <span data-ttu-id="3c790-171">Selecione o ícone **?**</span><span class="sxs-lookup"><span data-stu-id="3c790-171">Choose the **?**</span></span> <span data-ttu-id="3c790-172">no canto superior esquerdo e selecione **Sobre**.</span><span class="sxs-lookup"><span data-stu-id="3c790-172">icon at the upper left, and then select **About**.</span></span>

    3. <span data-ttu-id="3c790-173">Localize o valor **Servidor Externo POP** .</span><span class="sxs-lookup"><span data-stu-id="3c790-173">Locate the **POP External Server** value.</span></span>

    4. <span data-ttu-id="3c790-174">Clique em **Servidor Proxy** para especificar as configurações do servidor proxy para seu Exchange Server hospedado.</span><span class="sxs-lookup"><span data-stu-id="3c790-174">Choose **Proxy Server** to specify proxy server settings for your hosted Exchange server.</span></span>
        1. <span data-ttu-id="3c790-175">Selecione **Usar um servidor proxy ao sincronizar informações do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="3c790-175">Select **Use a proxy server when synchronizing mobile device information**.</span></span>

        2. <span data-ttu-id="3c790-176">Insira o **nome do servidor proxy** e o **número da porta** a serem usados para acessar o servidor.</span><span class="sxs-lookup"><span data-stu-id="3c790-176">Enter the **proxy server name** and the **port number** to be used to access the server.</span></span>

        3. <span data-ttu-id="3c790-177">Se for necessário fornecer as credenciais para acessar o servidor proxy, selecione **Usar credenciais para se conectar ao servidor proxy**.</span><span class="sxs-lookup"><span data-stu-id="3c790-177">If it's necessary to provide user credentials to access the proxy server, select **Use credentials to connect to the proxy server**.</span></span> <span data-ttu-id="3c790-178">Em seguida, digite o **domínio\usuário** e a **senha**.</span><span class="sxs-lookup"><span data-stu-id="3c790-178">Then enter the **domain\user** and the **password**.</span></span>

        4. <span data-ttu-id="3c790-179">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c790-179">Choose **OK**.</span></span>

    5. <span data-ttu-id="3c790-180">Nos campos **Usuário (Domínio\usuário)** e **Senha**, insira as credenciais necessárias para se conectar ao Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="3c790-180">In the **User (Domain\user)** and **Password** fields, enter the credentials that are necessary to connect to your Exchange server.</span></span>

    6.  <span data-ttu-id="3c790-181">Forneça as credenciais administrativas necessárias para enviar notificações para a caixa de entrada do Exchange Server do usuário.</span><span class="sxs-lookup"><span data-stu-id="3c790-181">Provide the necessary administrative credentials to send notifications to a user’s Exchange Server mailbox.</span></span> <span data-ttu-id="3c790-182">Você pode configurar essas notificações com políticas de Acesso Condicional no Intune.</span><span class="sxs-lookup"><span data-stu-id="3c790-182">You can configure these notifications with Conditional Access policies in Intune.</span></span>

        <span data-ttu-id="3c790-183">Verifique se o serviço Descoberta Automática e os Serviços Web do Exchange estão configurados no Servidor de Acesso para Cliente do Exchange.</span><span class="sxs-lookup"><span data-stu-id="3c790-183">Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access Server.</span></span> <span data-ttu-id="3c790-184">Para obter mais informações, consulte [Servidor de Acesso para Cliente](https://technet.microsoft.com/library/dd298114.aspx).</span><span class="sxs-lookup"><span data-stu-id="3c790-184">For more information, see [Client Access server](https://technet.microsoft.com/library/dd298114.aspx).</span></span>

    7.  <span data-ttu-id="3c790-185">No campo **Senha**, forneça a senha da conta para habilitar o Intune a acessar o Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="3c790-185">In the **Password** field, provide the password for this account to enable Intune to access the Exchange Server.</span></span>

    8. <span data-ttu-id="3c790-186">Selecione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="3c790-186">Choose **Connect**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3c790-187">Podem ser necessários alguns minutos para que a conexão seja configurada.</span><span class="sxs-lookup"><span data-stu-id="3c790-187">It might take a few minutes for the connection to be configured.</span></span>

<span data-ttu-id="3c790-188">Durante a configuração, o Exchange Connector armazena as configurações de proxy para habilitar o acesso à Internet.</span><span class="sxs-lookup"><span data-stu-id="3c790-188">During configuration, the Exchange Connector stores your proxy settings to enable access to the Internet.</span></span> <span data-ttu-id="3c790-189">Se as configurações de proxy forem alteradas, você precisará reconfigurar o Exchange Connector para aplicar as configurações de proxy atualizadas ao Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="3c790-189">If your proxy settings change, you will have to reconfigure the Exchange Connector to apply the updated proxy settings to the Exchange Connector.</span></span>

<span data-ttu-id="3c790-190">Após o Exchange Connector configurar a conexão, os dispositivos móveis associados aos usuários que são gerenciados no Exchange Connector são automaticamente sincronizados e adicionados ao Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="3c790-190">After the Exchange Connector sets up the connection, mobile devices that are associated with users that are managed in Exchange Connector are automatically synchronized and added to the Exchange Connector.</span></span> <span data-ttu-id="3c790-191">Pode levar algum tempo até que a sincronização seja concluída.</span><span class="sxs-lookup"><span data-stu-id="3c790-191">This synchronization might take some time to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="3c790-192">Se você tiver instalado o Exchange Connector Local e se em algum momento a conexão com o Exchange for excluída, você deverá desinstalar o Exchange Connector Local do computador em que ele foi instalado.</span><span class="sxs-lookup"><span data-stu-id="3c790-192">If you have installed the On-premises Exchange Connector, and if at some point you delete the Exchange connection, you must uninstall the On-premises Exchange Connector from the computer onto which it was installed.</span></span>

## <span data-ttu-id="3c790-193">Validar a conexão do Exchange</span><span class="sxs-lookup"><span data-stu-id="3c790-193">Validate the Exchange connection</span></span>
<a id="validate-the-exchange-connection" class="xliff"></a>

<span data-ttu-id="3c790-194">Após configurar o Exchange Connector com êxito, você pode exibir o status da conexão e a última tentativa de sincronização bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="3c790-194">After you have successfully configured the Exchange Connector, you can view the status of the connection and the last successful synchronization attempt.</span></span> <span data-ttu-id="3c790-195">Para validar a conexão do Exchange Connector:</span><span class="sxs-lookup"><span data-stu-id="3c790-195">To validate the Exchange Connector connection:</span></span>

- <span data-ttu-id="3c790-196">No Painel do Intune, escolha **Acesso local**.</span><span class="sxs-lookup"><span data-stu-id="3c790-196">On the Intune Dashboard, choose **On-premises access**.</span></span> <span data-ttu-id="3c790-197">Em **Gerenciar**, selecione **Acesso ao Exchange Local** para verificar o status da conexão.</span><span class="sxs-lookup"><span data-stu-id="3c790-197">Under **Manage**, select **Exchange on-premises access** to verify the connection status.</span></span>

<span data-ttu-id="3c790-198">Você também pode verificar a hora e data da última tentativa de sincronização bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="3c790-198">You can also check the time and date of the last successful synchronization attempt.</span></span>

## <span data-ttu-id="3c790-199">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3c790-199">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="3c790-200">Criar uma política de acesso condicional para o Exchange local</span><span class="sxs-lookup"><span data-stu-id="3c790-200">Create a conditional access policy for Exchange on-premises</span></span>](conditional-access-exchange-create.md)
