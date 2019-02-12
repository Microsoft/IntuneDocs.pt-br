---
title: Configurar o conector do Exchange no Local do Microsoft Intune | Microsoft Intune
description: Use o conector do Exchange local para gerenciar o acesso de dispositivo às caixas de correio do Exchange com base no registro do Intune e no EAS (Exchange Active Sync).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4481645781e21da4f433f5feae1d685efb73d412
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841412"
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure"></a>Configurar o conector do Exchange local do Intune no Microsoft Intune Azure

Em um ambiente do Exchange Server local, o acesso condicional do Intune pode ser usado para permitir ou bloquear o acesso a caixas de correio locais do Exchange. Use os conectores locais do Exchange Active Sync para conectar o Intune às suas organizações do Exchange e configurar o acesso condicional do Intune junto com as políticas de conformidade do dispositivo. Em seguida, quando um dispositivo tentar se conectar ao Exchange, o Intune determinará se o dispositivo está registrado no Intune e se está em conformidade. Para determinar quais dispositivos estão registrados no Intune, o conector do Exchange local mapeia registros EAS (Exchange Active Sync) no Exchange Server para registros do Intune. Para obter mais informações sobre como isso funciona, consulte [Quais são as maneiras comuns de usar o acesso condicional com o Intune?](conditional-access-intune-common-ways-use.md)

> [!IMPORTANT]
> Agora, o Intune é compatível com vários conectores do Exchange locais por assinatura. Se você tiver mais de uma organização do Exchange local, poderá configurar um conector separado para cada organização do Exchange.

Para configurar uma conexão que habilita o Microsoft Intune a se comunicar com o Exchange Server local, aqui estão as etapas gerais:

1.  Baixe o conector do Exchange local do Intune no Portal do Azure.
2.  Instale e configure o conector do Exchange em um computador na organização do Exchange local.
3.  Validar a conexão do Exchange.
4. Repita estas etapas para cada organização do Exchange que você deseja conectar ao Intune.

## <a name="intune-on-premises-exchange-connector-requirements"></a>Requisitos do conector do Exchange local do Intune
A tabela a seguir lista os requisitos para o computador no qual o conector do Exchange local será instalado.


|            Requisito             |                                                                                                                                                                                                        Mais informações                                                                                                                                                                                                        |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Sistemas operacionais          |                                                               O Intune é compatível como o conector do Exchange local em um computador que execute qualquer edição do Windows Server 2008 SP2 64 bits, do Windows Server 2008 R2, do Windows Server 2012, do Windows Server 2012 R2 ou do Windows Server 2016.<br /><br />O conector não é compatível com nenhuma instalação Server Core.                                                                |
|         Microsoft Exchange         |                                                                           Os conectores locais exigem o Microsoft Exchange 2010 SP3 ou posteriores ou o Exchange Online Dedicado herdado. Para determinar se o seu ambiente do Exchange Online Dedicated está na configuração <strong>nova</strong> ou <strong>herdada</strong>, entre em contato com seu gerente de conta.                                                                           |
| Autoridade de gerenciamento de dispositivo móvel |                                                                                                                              [Defina a autoridade de gerenciamento de dispositivo móvel para o Intune](mdm-authority-set.md).                                                                                                                               |
|              Hardware              |                                                                                                                                                     O computador em que você instala o conector requer uma CPU de 1,6 GHz com 2 GB de RAM e 10 GB de espaço livre em disco.                                                                                                                                                      |
|  Sincronização do Active Directory  |                                                                                      Antes de usar qualquer conector para conectar o Intune ao Exchange Server, é necessário [configurar a sincronização do Active Directory](users-add.md) para que os usuários e grupos de segurança locais sejam sincronizados com a instância do Azure Active Directory.                                                                                      |
|        Software adicional         |                                                                                                                                           Uma instalação completa do Microsoft .NET Framework 4.5 e do Windows PowerShell 2.0 deve ser feita no computador que hospeda o conector.                                                                                                                                           |
|              Rede               | O computador no qual o conector será instalado deve estar em um domínio que tenha uma relação de confiança com o domínio que hospeda o Exchange Server.<br /><br />O computador precisa de configurações para habilitá-lo a acessar o serviço Intune por meio dos firewalls e servidores proxy por Portas 80 e 443. Os domínios usados pelo Intune incluem manage.microsoft.com, &#42;manage.microsoft.com e &#42;.manage.microsoft.com. |

### <a name="exchange-cmdlet-requirements"></a>Requisitos de cmdlets do Exchange

É preciso criar uma conta de usuário do Active Directory que seja usada pelo conector do Exchange local. A conta deve ter permissão para executar os seguintes cmdlets do Windows PowerShell Exchange necessários:


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

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Baixe o pacote de instalação de software do conector do Exchange local

1. Em um sistema operacional Windows Server compatível para o conector do Exchange local, abra o [portal do Azure](https://portal.azure.com) e entre com uma conta de usuário que seja um administrador no Exchange Server local e que tenha licença para usar o Exchange Server.

2. Escolha **Todos os serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3. Escolha **Intune** e, quando o Painel do Intune se abrir, escolha **Acesso local**.

4. em **Configuração**, escolha **Conectores do Exchange ActiveSync** e, em seguida, escolha **Baixar o conector local**.

5.  O Exchange Connector local está em uma pasta compactada (.zip) que pode ser aberta ou salva. Na caixa de diálogo **Download de Arquivos**, clique em **Salvar** para armazenar a pasta compactada em um local seguro.

    > [!IMPORTANT]
    > Não renomeie nem mova os arquivos que estão na pasta do conector do Exchange local. Mover ou renomear o conteúdo da pasta causará falha na instalação do conector do Exchange.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Instalar e configurar o conector do Exchange local do Intune
Execute as seguintes etapas para instalar o conector do Exchange local do Intune. Se você tiver várias organizações do Exchange, repita essas etapas para cada conector do Exchange adicional que você deseja configurar.

1. Em um sistema operacional compatível com o conector do Exchange local, extraia os arquivos em **Exchange_Connector_Setup.zip** para um local seguro.

2. Depois que os arquivos forem extraídos, abra a pasta extraída e clique duas vezes em **Exchange_Connector_Setup.exe** para instalar o conector do Exchange Local.

   > [!IMPORTANT]
   > Se a pasta de destino não for um local seguro, exclua o arquivo de certificado **MicrosoftIntune. accountcert** ao terminar de instalar os conectores locais.

3. Na caixa de diálogo **Microsoft Intune Exchange Connector**, selecione **Microsoft Exchange Server Local** ou **Microsoft Exchange Server Hospedado**.

   ![Imagem mostrando onde escolher o tipo de Exchange Server](./media/intune-sa-exchange-connector-config.png)

   Para um Exchange Server local, forneça o nome do servidor ou um nome de domínio totalmente qualificado do Exchange Server que hospeda a função de **servidor Acesso para Cliente**.

   Para um Exchange Server hospedado, forneça o endereço do Exchange Server. Para encontrar o URL do Exchange Server Hospedado:

   1. Abra o Outlook na Web para o Office 365.

   2. Selecione o ícone **?** no canto superior esquerdo e selecione **Sobre**.

   3. Localize o valor **Servidor Externo POP** .

   4. Clique em **Servidor Proxy** para especificar as configurações do servidor proxy para seu Exchange Server hospedado.
       1. Selecione **Usar um servidor proxy ao sincronizar informações do dispositivo móvel**.

       2. Insira o **nome do servidor proxy** e o **número da porta** a serem usados para acessar o servidor.

       3. Se for necessário fornecer as credenciais para acessar o servidor proxy, selecione **Usar credenciais para se conectar ao servidor proxy**. Em seguida, digite o **domínio\usuário** e a **senha**.

       4. Selecione **OK**.

4. Nos campos **Usuário (Domínio\usuário)** e **Senha**, insira as credenciais necessárias para se conectar ao Exchange Server.

5. Forneça as credenciais necessárias para enviar notificações para a caixa de entrada do Exchange Server do usuário. Este usuário pode ser dedicado a apenas notificações. O usuário das notificações precisa de uma caixa de correio do Exchange para poder enviar notificações por email. Você pode configurar essas notificações com políticas de acesso condicional no Intune.  

       Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access Server. For more information, see [Client Access server](https://technet.microsoft.com/library/dd298114.aspx).

6. No campo **Senha**, forneça a senha da conta para habilitar o Intune a acessar o Exchange Server.

7. Selecione **Conectar**.

   > [!NOTE]
   > Podem ser necessários alguns minutos para que a conexão seja configurada.

Durante a configuração, o conector do Exchange armazena as configurações de proxy para habilitar o acesso à Internet. Se as configurações de proxy forem alteradas, você precisará reconfigurar o Exchange Connector para aplicar as configurações de proxy atualizadas a ele.

Após o conector do Exchange configurar a conexão, os dispositivos móveis associados aos usuários que são gerenciados no Exchange serão automaticamente sincronizados e adicionados ao conector do Exchange. Pode levar algum tempo até que a sincronização seja concluída.

> [!NOTE]
> Se o Exchange Connector local estiver instalado e a conexão com o Exchange for excluída em algum momento, você deverá desinstalar o Exchange Connector local do computador em que ele estava instalado.

## <a name="install-connectors-for-multiple-exchange-organizations"></a>Instalar conectores para várias organizações do Exchange
O Intune é compatível com vários conectores do Exchange locais por assinatura. Para um locatário com várias organizações do Exchange, você pode configurar um conector para cada organização do Exchange. Baixe a pasta de arquivos .zip de uma única vez e, em seguida, para cada organização do Exchange, siga as etapas na seção anterior para extrair e executar o programa de instalação em um servidor na organização.

Os recursos de alta disponibilidade, monitoramento e sincronização manual descritos nas seções a seguir têm suporte para cada organização do Exchange conectada ao Intune.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Suporte de alta disponibilidade do Exchange Connector local 
Depois que o Exchange Connector criar uma conexão com o Exchange usando o CAS especificado, o conector poderá descobrir outros CASs. Se o CAS principal ficar desabilitado, o conector realizará o failover para outro CAS, se houver um disponível, até que o CAS principal fique disponível. Esse recurso está ativado por padrão. Desligue esse recurso usando o seguinte procedimento:
1. No servidor em que o Exchange Connector está instalado, vá para %*ProgramData*%\Microsoft\Windows Intune Exchange Connector. 
2. Usando um editor de texto, abra **OnPremisesExchangeConnectorServiceConfiguration.xml**.
3. Altere &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; para &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt; para desabilitar o recurso.    


## <a name="monitor-the-exchange-connector-activity"></a>Monitorar a atividade de conector do Exchange

Após configurar os conectores do Exchange com êxito, você pode exibir o status das conexões e a última tentativa de sincronização bem-sucedida. Para validar as conexões do conector do Exchange:

1. No Painel do Intune, escolha **Acesso local**.
2. Em **Instalação**, selecione **Conectores do Exchange ActiveSync** para verificar o status de conexão para cada conector do Exchange.

Você também pode verificar a hora e data da última tentativa de sincronização bem-sucedida.

### <a name="system-center-operations-manager-management-pack"></a>Pacote de gerenciamento do System Center Operations Manager

Na versão 1710 do Intune em diante, você poderá usar o [pacote de gerenciamento do Operations Manager para Exchange Connector e Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Isso oferecerá diferentes maneiras de monitorar o conector do Exchange quando for necessário solucionar problemas.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Forçar manualmente uma sincronização rápida ou completa
Um Exchange Connector local sincroniza de modo automático os registros de dispositivo do EAS e do Intune regularmente. Se o status de conformidade de um dispositivo for alterado, o processo de sincronização automática atualizará regularmente os registros para que o acesso ao dispositivo possa ser bloqueado ou permitido adequadamente.

   - **Sincronização rápida** ocorre regularmente, várias vezes ao dia. Uma sincronização rápida recupera informações de dispositivo para usuários almejados por acesso condicional do Exchange local e licenciados pelo Intune que foram alterados desde a última sincronização.

   - **Sincronização completa** ocorre uma vez por dia por padrão. Uma sincronização completa recupera informações do dispositivo para todos os usuários almejados por acesso condicional do Exchange local e licenciados pelo Intune. Uma sincronização completa também recupera informações do servidor Exchange e garante que a configuração especificada pelo Intune no portal do Azure seja atualizada no servidor Exchange. 

Você pode forçar um conector a executar uma sincronização usando as opções de **Sincronização Rápida** ou **Sincronização Completa** no painel do Intune com as seguintes etapas:

   1. No Painel do Intune, escolha **Acesso local**.
   2. Em **instalação**, escolha **conectores do Exchange Active Sync**.
   3. Selecione o conector que você deseja sincronizar e, em seguida, escolha **Sincronização Rápida** ou **Sincronização Completa**.

## <a name="next-steps"></a>Próximas etapas
[Criar uma política de acesso condicional para o Exchange local](conditional-access-exchange-create.md)
