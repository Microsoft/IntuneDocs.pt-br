---
title: Exchange Connector para o EAS local
description: Use a ferramenta do Connector para habilitar a comunicação entre o console de administração do Intune e o Exchange Server Local para MDM do Exchange ActiveSync.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/29/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 41ff4212-a6f5-4374-8731-631f7560cff1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 96d61ccae4e70a3e99da70a0ef19218ddbd218f3
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="install-the-intune-on-premises-exchange-connector"></a>Instalar o Exchange Connector Local do Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]


Para configurar uma conexão que habilita o Microsoft Intune a se comunicar com o Exchange Server que hospeda as caixas de correio dos dispositivos móveis, você precisa baixar e configurar o Exchange Connector Local do console de administração do Intune. O Intune dá suporte apenas a uma conexão do Exchange Connector de qualquer tipo por assinatura.

## <a name="on-premises-exchange-connector-requirements"></a>Requisitos do Exchange Connector Local
A tabela a seguir lista os requisitos para o computador no qual o Exchange Connector Local será instalado.

|Requisito|Mais informações|
|---------------|--------------------|
|Sistemas operacionais|O Intune dá suporte ao Exchange Connector Local em um computador que executa qualquer edição do Windows Server 2008 SP2 64 bits, do Windows Server 2008 R2, do Windows Server 2012 ou do Windows Server 2012 R2.<br /><br />O Connector não tem suporte em instalações Server Core.|
|Microsoft Exchange|O Connector Local requer o Microsoft Exchange 2010 SP1 ou posterior, ou o Exchange Online Dedicado herdado. Para determinar se o seu ambiente do Exchange Online Dedicated está na configuração **nova** ou **herdada**, entre em contato com seu gerente de conta.|
|Autoridade de gerenciamento de dispositivo móvel| [Defina a autoridade de gerenciamento de dispositivo móvel para o Intune](prerequisites-for-enrollment.md#step-2-set-mdm-authority).|
|Hardware|O computador em que você instala o conector requer uma CPU de 1,6 GHz com 2 GB de RAM e 10 GB de espaço livre em disco.|/intune/users-permissions-add
|Sincronização do Active Directory|Antes de usar qualquer o Connector para conectar o Intune ao Exchange Server, é necessário [configurar a sincronização do Active Directory](/intune/users-permissions-add) para que os usuários e grupos de segurança locais sejam sincronizados com a instância do Azure Active Directory.|
|Software adicional|Uma instalação completa do Microsoft .NET Framework 4.5 e do Windows PowerShell 2.0 deve ser feita no computador que hospeda o conector.|
|Rede|O computador no qual o conector será instalado deve estar em um domínio que tenha uma relação de confiança com o domínio que hospeda o Exchange Server.<br /><br />O computador precisa de configurações para habilitá-lo a acessar o serviço Intune por meio dos firewalls e servidores proxy por Portas 80 e 443. Os domínios usados pelo Intune incluem manage.microsoft.com, &#42;manage.microsoft.com e &#42;.manage.microsoft.com.|


### <a name="exchange-cmdlet-requirements"></a>Requisitos de cmdlets do Exchange

É preciso criar uma conta de usuário do Active Directory que seja usada pelo Exchange Connector. A conta deve ter permissão para executar os seguintes cmdlets do Windows PowerShell Exchange necessários:


 -   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 -   Get-CasMailbox, Set-CasMailbox
 -   Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
 -   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 -   Get-ActiveSyncDeviceStatistics
 -   Get-ActiveSyncDevice
 -   Get-ExchangeServer
 -   Get-ActiveSyncDeviceClass
 -   Get-Recipient
 -   Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
 -   Set-ADServerSettings
 -   Get-Command

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Baixe o pacote de instalação de software do Exchange Connector Local

1. Em um sistema operacional Windows Server compatível para o Exchange Connector Local, abra o [console de administração do Microsoft Intune](https://manage.microsoft.com) (https://manage.microsoft.com) com uma conta de usuário que seja um administrador no locatário do Exchange e que tenha uma licença para usar o Exchange Server.
![Abra a configuração da Conexão com o Exchange](../media/ExchangeConnector.gif)

2.  No painel de atalhos do espaço de trabalho, escolha **Admin**>**Gerenciamento de Dispositivo Móvel** > **Microsoft Exchange**>**Configurar Conexão com o Exchange**.

3.  Na página **Configurar a Conexão do Exchange**, clique em **Baixar o On-Premises Connector**.

4.  O Exchange Connector Local vem em uma pasta compactada (.zip) que pode ser aberta ou salva. Na caixa de diálogo **Download de Arquivos**, clique em **Salvar** para armazenar a pasta compactada em um local seguro.

> [!IMPORTANT]
> Não renomeie ou mova os arquivos que estão dentro da pasta do Exchange Connector Local. Mover ou renomear o conteúdo da pasta causará falha na instalação.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Instalar e configurar o Exchange Connector Local do Intune
Execute as seguintes etapas para instalar o Exchange Connector Local do Intune. O Exchange Connector Local pode ser instalado somente uma vez por assinatura do Intune e somente em um computador. Se você tentar configurar um Exchange Connector Local adicional, a nova conexão substituirá a original.

1.  Em um sistema operacional com suporte para o Connector Local, extraia os arquivos em **Exchange_Connector_Setup.zip** para um local seguro.

2.  Depois que os arquivos forem extraídos, abra a pasta extraída e clique duas vezes em **Exchange_Connector_Setup.exe** para instalar o Exchange Connector Local.

    > [!IMPORTANT]
    > Se a pasta de destino não for um local seguro, exclua o arquivo de certificado **WindowsIntune.accountcert** após instalar o Connector Local.

3.  Na caixa de diálogo **Microsoft Intune Exchange Connector**, selecione **Microsoft Exchange Server Local** ou **Microsoft Exchange Server Hospedado**.

  ![Escolha o tipo de Exchange Server](../media/IntuneSA1dconfigureExchConnector.png)

  Para um Exchange Server Local, forneça o nome do servidor ou um nome de domínio totalmente qualificado do Exchange Server que hospeda a função de **Servidor de Acesso para Cliente**.

  Para um Exchange Server hospedado, forneça o endereço do Exchange Server. Para encontrar o URL do Exchange Server Hospedado:

    1. Abra o Outlook Web App para o Office 365.

    2. Selecione o ícone **?** no canto superior esquerdo e selecione **Sobre**.

    3. Localize o valor **Servidor Externo POP** .

    4. Clique em **Servidor Proxy** para especificar as configurações do servidor proxy para seu Exchange Server hospedado.
        1. Selecione **Usar um servidor proxy ao sincronizar informações do dispositivo móvel**.

        2. Insira o **nome do servidor proxy** e o **número da porta** a serem usados para acessar o servidor.

        3. Se for necessário fornecer as credenciais para acessar o servidor proxy, selecione **Usar credenciais para se conectar ao servidor proxy**. Em seguida, digite o **domínio\usuário** e a **senha**.

        4. Selecione **OK**.

    5. Nos campos **Usuário (Domínio\usuário)** e **Senha**, insira as credenciais necessárias para se conectar ao Exchange Server.

    6.  Forneça as credenciais administrativas necessárias para enviar notificações para a caixa de entrada do Exchange Server do usuário. Você pode configurar essas notificações com políticas de Acesso Condicional no Intune.

        Verifique se o serviço Descoberta Automática e os Serviços Web do Exchange estão configurados no Servidor de Acesso para Cliente do Exchange. Para obter mais informações, consulte [Servidor de Acesso para Cliente](https://technet.microsoft.com/library/dd298114.aspx).

    7.  No campo **Senha**, forneça a senha da conta para habilitar o Intune a acessar o Exchange Server.

    8. Selecione **Conectar**.

Podem ser necessários alguns minutos para que a conexão seja configurada.

Durante a configuração, o Exchange Connector armazena as configurações de proxy para habilitar o acesso à Internet. Se as configurações de proxy forem alteradas, você precisará reconfigurar o Exchange Connector para aplicar as configurações de proxy atualizadas ao Exchange Connector.

Após o Exchange Connector configurar a conexão, os dispositivos móveis associados aos usuários que são gerenciados no Exchange Connector são automaticamente sincronizados e adicionados ao Exchange Connector. Pode levar algum tempo até que a sincronização seja concluída.

> [!NOTE]
> Se você tiver instalado o Exchange Connector Local e se em algum momento a conexão com o Exchange for excluída, você deverá desinstalar o Exchange Connector Local do computador em que ele foi instalado.

## <a name="validate-the-exchange-connection"></a>Validar a conexão do Exchange

Após configurar o Exchange Connector com êxito, você pode exibir o status da conexão e a última tentativa de sincronização bem-sucedida. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha o espaço de trabalho **ADMIN**. m **Gerenciamento de Dispositivo Móvel**, escolha **Microsoft Exchange** e confirme se os detalhes fornecidos aparecem em **Informações sobre a Conexão com o Exchange**.


Você também pode verificar a hora e data da última tentativa de sincronização bem-sucedida.
