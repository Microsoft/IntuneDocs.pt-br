---
title: Configurar o conector do Exchange local do Microsoft Intune
titleSuffix: Microsoft Intune
description: Use o conector do Exchange local para gerenciar o acesso de dispositivo às caixas de correio do Exchange com base no registro do Intune e no EAS (Exchange Active Sync).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f55ecd98e047dbf77e6e8eb58284577078e21a61
ms.sourcegitcommit: 614c4c36cfe544569db998e17e29feeaefbb7a2e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68427327"
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune"></a>Configurar o conector do Exchange local do Intune no Microsoft Intune
As informações deste artigo ajudarão você a instalar e monitorar o conector local do Exchange Active Sync para o Intune.  Use o conector do Exchange local do Intune com suas [políticas de acesso condicional para permitir ou bloquear o acesso às suas caixas de correio locais do Exchange](conditional-access-exchange-create.md). 

Quando um dispositivo tenta acessar o Exchange local, o conector do Exchange mapeia os registros do EAS (Exchange Active Sync) no Exchange Server para que os registros do Intune verifiquem se há registro de dispositivos com o Intune e se há conformidade com as políticas do seu dispositivo. Dependendo de suas políticas de acesso condicional, o dispositivo pode ter o acesso permitido ou bloqueado. Para saber mais, confira [Quais são as maneiras comuns de usar o acesso condicional com o Intune?](conditional-access-intune-common-ways-use.md)

O Intune dá suporte à instalação de vários conectores do Exchange local por assinatura. Se você tiver mais de uma organização do Exchange local, poderá configurar um conector separado para cada uma. No entanto, apenas um conector pode ser instalado para ser usado em cada organização do Exchange individual. 

Veja a seguir as etapas gerais para configurar uma conexão que permite que o Intune se comunique com o Exchange Server local:

1. Baixar o conector do Exchange local do Intune do portal do Intune.
2. Instale e configure o conector do Exchange em um computador na organização do Exchange local.
3. Validar a conexão do Exchange.
4. Repita essas etapas para cada organização adicional do Exchange que você deseja conectar ao Intune.

## <a name="intune-on-premises-exchange-connector-requirements"></a>Requisitos do conector do Exchange local do Intune
Será necessária uma conta com uma licença do Intune que possa ser usada pelo conector para se conectar ao Exchange. A conta é especificada quando você instala o conector.  

A tabela a seguir lista os requisitos para o computador no qual o conector do Exchange local será instalado.  

|  Requisito  |   Mais informações     |
|---------------|------------------------|
|  Sistemas operacionais        | O Intune é compatível como o conector do Exchange local em um computador que execute qualquer edição do Windows Server 2008 SP2 64 bits, do Windows Server 2008 R2, do Windows Server 2012, do Windows Server 2012 R2 ou do Windows Server 2016.<br /><br />O conector não é compatível com nenhuma instalação Server Core.  |
| Microsoft Exchange          | Os conectores locais exigem o Microsoft Exchange 2010 SP3 ou posteriores ou o Exchange Online Dedicado herdado. Para determinar se o seu ambiente do Exchange Online Dedicated está na configuração <strong>nova</strong> ou <strong>herdada</strong>, entre em contato com seu gerente de conta. |
| Autoridade de gerenciamento de dispositivo móvel           | [Defina a autoridade de gerenciamento de dispositivo móvel para o Intune](mdm-authority-set.md). |
| Hardware              | O computador em que você instala o conector requer uma CPU de 1,6 GHz com 2 GB de RAM e 10 GB de espaço livre em disco. |
|  Sincronização do Active Directory             | Antes de usar qualquer conector para conectar o Intune ao Exchange Server, é necessário [configurar a sincronização do Active Directory](users-add.md) para que os usuários e grupos de segurança locais sejam sincronizados com a instância do Azure Active Directory. |
| Software adicional         | Uma instalação completa do Microsoft .NET Framework 4.5 e do Windows PowerShell 2.0 deve ser feita no computador que hospeda o conector. |
| Rede               | O computador no qual o conector será instalado deve estar em um domínio que tenha uma relação de confiança com o domínio que hospeda o Exchange Server.<br /><br />O computador precisa de configurações para habilitá-lo a acessar o serviço Intune por meio dos firewalls e servidores proxy por Portas 80 e 443. Os domínios usados pelo Intune incluem manage.microsoft.com, &#42;manage.microsoft.com e &#42;.manage.microsoft.com. |

### <a name="exchange-cmdlet-requirements"></a>Requisitos de cmdlets do Exchange

Crie uma conta de usuário do Active Directory que será usada pelo conector do Exchange local. A conta deve ter permissão para executar os seguintes cmdlets do Windows PowerShell Exchange necessários:


- Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
- Get-CasMailbox, Set-CasMailbox
- Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
- Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
- Get-ActiveSyncDeviceStatistics
- Get-ActiveSyncDevice
- Get-ExchangeServer
- Get-ActiveSyncDeviceClass
- Get-Recipient
- Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
- Set-ADServerSettings
- Get-Command

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Baixe o pacote de instalação de software do conector do Exchange local

1. Em um sistema operacional Windows Server compatível para o conector do Exchange local, abra o [Portal do Azure](https://portal.azure.com) e entre com uma conta de usuário que seja um administrador no Exchange Server local e que tenha licença para usar o Exchange Server.

2. Acesse o **Intune** > **Acesso do Exchange**  

3. Em **Configuração**, escolha **conector local do Exchange ActiveSync** e selecione **Adicionar**.

4. Na página **Adicionar Conector**, selecione **Baixar o conector local**. O Exchange Connector local está em uma pasta compactada (.zip) que pode ser aberta ou salva. Na caixa de diálogo **Download de Arquivos**, clique em **Salvar** para armazenar a pasta compactada em um local seguro.

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

4. Nos campos **Usuário (Domínio\usuário)** e **Senha**, insira as credenciais necessárias para se conectar ao Exchange Server. A conta especificada deve ter uma licença para usar o Intune. 

5. Forneça as credenciais necessárias para enviar notificações para a caixa de entrada do Exchange Server do usuário. Este usuário pode ser dedicado a apenas notificações. O usuário de notificações precisa de uma caixa de correio do Exchange para enviar notificações por email. Você pode configurar essas notificações com políticas de Acesso Condicional no Intune.  

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
O Intune é compatível com vários conectores do Exchange locais por assinatura. Para um locatário com várias organizações do Exchange, é possível configurar um conector para cada organização do Exchange, mas apenas um único conector para qualquer organização individual. 

Se você instalar conectores para se conectar a várias organizações do Exchange, baixe a pasta .zip uma vez e reutilize esse mesmo download para cada conector instalado. Para cada conector adicional, siga as etapas na seção anterior para extrair e executar o programa de instalação em um servidor na organização do Exchange.

Há suporte para os recursos de alta disponibilidade, de monitoramento e de sincronização manual descritos nas seguintes seções para cada organização do Exchange que se conecta ao Intune.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Suporte de alta disponibilidade do Exchange Connector local 
Alta disponibilidade para o conector do Exchange local significa que, caso o CAS (servidor de Acesso para Cliente) do Exchange que o conector usa se tornar não disponível, o conector poderá alternar para usar um CAS diferente para essa organização do Exchange. O próprio conector do Exchange não é compatível com a alta disponibilidade. Se o conector falhar, não haverá failover automático e você deverá substituir esse conector [instalando um novo](#reinstall-the-on-premises-exchange-connector). 

Para realizar o failover, após o conector criar uma conexão bem-sucedida com o Exchange usando o CAS especificado, o conector descobrirá CASs adicionais para essa organização do Exchange. Conhecer outros CASs permitirá que o conector faça failover para outro CAS se algum estiver disponível até que o CAS principal fique disponível. Por padrão, a descoberta de outros CASs é habilitada. É possível desligar o failover usando o procedimento a seguir:  
1. No servidor em que o conector do Exchange está instalado, acesse %*ProgramData*%\Microsoft\Windows Intune Exchange Connector. 
2. Usando um editor de texto, abra **OnPremisesExchangeConnectorServiceConfiguration.xml**.
3. Altere &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; para &lt;IsCasFailoverEnabled&gt;**false**&lt;/IsCasFailoverEnabled&gt; para desabilitar o recurso.  
 
## <a name="optional-performance-tuning-for-the-exchange-connector"></a>Ajuste de desempenho opcional para o conector do Exchange  

Ao dar suporte a 5.000 ou mais dispositivos com o Exchange ActiveSync, você pode definir uma configuração opcional para melhorar o desempenho do conector. O aumento do desempenho é atingido habilitando o Exchange a usar várias instâncias de um runspace de comando do PowerShell. 

Antes de fazer essa alteração, verifique se a conta usada para executar o conector do Exchange não é usada para outros fins de gerenciamento do Exchange. Isso porque o Exchange tem um limite de 18 runspaces por conta, e a maioria deles será usada pelo conector. 

Essa alteração de desempenho não é adequada para conectores que são executados em um hardware mais antigo ou mais lento.  

1. No servidor em que o conector está instalado, abra o diretório de instalação dos conectores.  A localização padrão é *C:\ProgramData\Microsoft\Windows Intune Exchange Connector*. 
2. Edite o arquivo *OnPremisesExchangeConnectorServiceConfiguration.xml*.
3. Localize **EnableParallelCommandSupport** e defina o valor como **true**:  
     
   \<EnableParallelCommandSupport>true\</EnableParallelCommandSupport>
4. Salve o arquivo e reinicie o serviço Microsoft Intune Exchange Connector.

## <a name="reinstall-the-on-premises-exchange-connector"></a>Reinstalar o conector do Exchange local
Talvez seja necessário reinstalar um conector do Exchange. Como há suporte para que um único conector se conecte a cada organização do Exchange, se você instalar um segundo conector para uma organização, o novo conector instalado substituirá o conector original.

1. Use as etapas de [Instalar e configurar o conector do Exchange local do Intune](#install-and-configure-the-intune-on-premises-exchange-connector) para iniciar a instalação do novo conector. 
2. Quando solicitado, selecione **Substituir** para instalar o novo conector.  
   ![Prompt de configuração para substituir um conector](./media/exchange-connector-install/prompt-to-replace.png)

3. Continue usando as etapas do procedimento anterior e faça logon no Intune novamente.
4. Quando a tela final aparecer, selecione **Fechar** para concluir a instalação.  
   ![Concluir instalação](./media/exchange-connector-install/successful-reinstall.png)
 

## <a name="monitor-the-exchange-connector-activity"></a>Monitorar a atividade de conector do Exchange

Após configurar o conector do Exchange com êxito, será possível exibir o status das conexões e a última tentativa de sincronização bem-sucedida. Para validar a conexão do conector do Exchange:

1. No Painel do Intune, escolha **Acesso ao Exchange**.
2. Selecione **Acesso local do Exchange**, para verificar o status da conexão para cada conector do Exchange.

Você também pode verificar a hora e data da última tentativa de sincronização bem-sucedida.
--> 

### <a name="system-center-operations-manager-management-pack"></a>Pacote de gerenciamento do System Center Operations Manager

Na versão 1710 do Intune em diante, você poderá usar o [pacote de gerenciamento do Operations Manager para Exchange Connector e Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). Usar o pacote de gerenciamento oferecerá diferentes maneiras de monitorar o conector do Exchange quando for necessário solucionar problemas.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Forçar manualmente uma sincronização rápida ou completa
Um Exchange Connector local sincroniza de modo automático os registros de dispositivo do EAS e do Intune regularmente. Se o status de conformidade de um dispositivo for alterado, o processo de sincronização automática atualizará os registros regularmente para que o acesso ao dispositivo possa ser bloqueado ou permitido.

- **Sincronização rápida** ocorre regularmente, várias vezes ao dia. Uma sincronização rápida recupera informações de dispositivo para usuários direcionados ao acesso condicional do Exchange local e licenciados pelo Intune que foram alterados desde a última sincronização.

- **Sincronização completa** ocorre uma vez por dia por padrão. Uma sincronização completa recupera informações do dispositivo para todos os usuários direcionados ao acesso condicional do Exchange local e licenciados pelo Intune. Uma sincronização completa também recupera informações do servidor Exchange e garante que a configuração especificada pelo Intune no portal do Azure seja atualizada no servidor Exchange. 


Você pode forçar um conector a executar uma sincronização usando as opções de **Sincronização Rápida** ou **Sincronização Completa** no painel do Intune com as seguintes etapas:

   1. No Painel do Intune, escolha **Acesso ao Exchange**.
   2. Selecione **Acesso local ao Exchange**.
   3. Selecione o conector que você deseja sincronizar e, em seguida, escolha **Sincronização Rápida** ou **Sincronização Completa**.

## <a name="next-steps"></a>Próximas etapas
[Criar uma política de acesso condicional para o Exchange local](conditional-access-exchange-create.md)
