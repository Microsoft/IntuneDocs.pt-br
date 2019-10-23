---
title: Configurar um conector do Intune ao Exchange da Microsoft
titleSuffix: Microsoft Intune
description: Use o conector do Intune ao Exchange local para gerenciar o acesso de dispositivo às caixas de correio do Exchange com base no registro do Intune e no EAS (Exchange Active Sync).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 30b5debc6e1ab113a08d8930f96f6cbc9bf12b48
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509528"
---
# <a name="set-up-the-on-premises-intune-exchange-connector"></a>Configurar o conector do Intune ao Exchange local
Para ajudar a proteger o acesso ao Exchange, o Intune conta com um componente local que é conhecido como o conector do Intune ao Exchange da Microsoft. Esse conector também é chamado de *conector local do Exchange ActiveSync* em alguns locais do console do Intune. 

As informações neste artigo podem ajudar você a instalar e monitorar o conector do Intune ao Exchange. Você pode usar o conector com suas [políticas de acesso condicional](conditional-access-exchange-create.md) para permitir ou bloquear o acesso às suas caixas de correio locais do Exchange. 

O conector é instalado e executado em seu hardware local. Ele descobre os dispositivos que se conectam ao Exchange, comunicando informações do dispositivo ao serviço do Intune. O conector permite ou bloqueia dispositivos com base no fato de os dispositivos estarem registrados e em conformidade. Essas comunicações usam o protocolo HTTPS.

Quando um dispositivo tenta acessar o Exchange Server local, o conector do Exchange mapeia os registros do EAS (Exchange Active Sync) no Exchange Server para os registros do Intune a fim de garantir que o dispositivo esteja registrado no o Intune e em há conformidade com as políticas do seu dispositivo. Dependendo de suas políticas de Acesso Condicional, o dispositivo pode ser permitido ou bloqueado. Para saber mais, confira [Quais são as maneiras comuns de usar o acesso condicional com o Intune?](conditional-access-intune-common-ways-use.md)

As operações *descobrir* e *permitir e bloquear* são feitas usando cmdlets padrão do Exchange PowerShell. Essas operações usam a conta de serviço fornecida inicialmente na instalação do conector do Exchange. 

O Intune dá suporte à instalação de vários conectores do Intune Exchange por assinatura. Se você tiver mais de uma organização do Exchange local, poderá configurar um conector separado para cada uma. No entanto, apenas um conector pode ser instalado para cada organização do Exchange.  

Siga estas etapas gerais para configurar uma conexão que permita que o Intune se comunique com o Exchange Server local:

1. Baixe o conector local no portal do Intune.
2. Instale e configure o conector do Exchange em um computador na organização do Exchange local.
3. Validar a conexão do Exchange.
4. Repita essas etapas para cada organização adicional do Exchange que você deseja conectar ao Intune.

## <a name="intune-exchange-connector-requirements"></a>Requisitos do conector do Intune ao Exchange

Para se conectar ao Exchange, é necessário uma conta com uma licença do Intune que o conector possa usar. Você especifica a conta ao instalar o conector.  

A tabela a seguir lista os requisitos para o computador no qual o conector do Intune ao Exchange será instalado.  

|  Requisito  |   Mais informações     |
|---------------|------------------------|
|  Sistemas operacionais        | O Intune é compatível com o conector do Intune ao Exchange em um computador que execute qualquer edição do Windows Server 2008 SP2 64 bits, do Windows Server 2008 R2, do Windows Server 2012, do Windows Server 2012 R2 ou do Windows Server 2016.<br /><br />O conector não é compatível com nenhuma instalação Server Core.  |
| Microsoft Exchange          | Os conectores locais exigem o Microsoft Exchange 2010 SP3 ou posteriores ou o Exchange Online Dedicado herdado. Para determinar se o seu ambiente do Exchange Online Dedicated está na configuração *nova* ou *herdada*, entre em contato com seu gerente de conta. |
| Autoridade de gerenciamento de dispositivo móvel           | [Defina a autoridade de gerenciamento de dispositivo móvel para o Intune](../fundamentals/mdm-authority-set.md). |
| Hardware              | O computador em que você instala o conector requer uma CPU de 1,6 GHz com 2 GB de RAM e 10 GB de espaço livre em disco. |
|  Sincronização do Active Directory             | Antes de usar o conector para conectar o Intune ao Exchange Server, [configure a sincronização do Active Directory](../fundamentals/users-add.md). Os usuários e grupos de segurança locais devem ser sincronizados com sua instância do Azure Active Directory. |
| Software adicional         | O computador que hospeda o conector deve ter uma instalação completa do Microsoft .NET Framework 4.5 e do Windows PowerShell 2.0. |
| Rede               | O computador no qual o conector será instalado deve estar em um domínio que tenha uma relação de confiança com o domínio que hospeda o Exchange Server.<br /><br />Configure o computador para permitir que ele acesse o serviço do Intune por meio dos firewalls e servidores proxy pelas portas 80 e 443. O Intune usa estes domínios: <br> – manage.microsoft.com <br> - \*manage.microsoft.com<br> - \*.manage.microsoft.com <br><br> O conector do Intune ao Exchange se comunica com os seguintes serviços: <br> – Serviço do Intune: HTTPS porta 443 <br> – CAS (Servidor de Acesso para Cliente) do Exchange: Serviço WinRM porta 443<br> – Descoberta Automática do Exchange 443<br> – EWS (Serviços Web do Exchange) 443  |

### <a name="exchange-cmdlet-requirements"></a>Requisitos de cmdlets do Exchange

Crie uma conta de usuário no Active Directory para o conector do Intune ao Exchange. A conta deve ter permissão para executar os seguintes cmdlets do Windows PowerShell Exchange:  

- `Get-ActiveSyncOrganizationSettings`, `Set-ActiveSyncOrganizationSettings`
- `Get-CasMailbox`, `Set-CasMailbox`
- `Get-ActiveSyncMailboxPolicy`, `Set-ActiveSyncMailboxPolicy`, `New-ActiveSyncMailboxPolicy`, `Remove-ActiveSyncMailboxPolicy`
- `Get-ActiveSyncDeviceAccessRule`, `Set-ActiveSyncDeviceAccessRule`, `New-ActiveSyncDeviceAccessRule`, `Remove-ActiveSyncDeviceAccessRule`
- `Get-ActiveSyncDeviceStatistics`
- `Get-ActiveSyncDevice`
- `Get-ExchangeServer`
- `Get-ActiveSyncDeviceClass`
- `Get-Recipient`
- `Clear-ActiveSyncDevice`, `Remove-ActiveSyncDevice`
- `Set-ADServerSettings`
- `Get-Command`

## <a name="download-the-installation-package"></a>Baixar o pacote de instalação

1. Em um servidor Windows com suporte ao conector do Intune ao Exchange, entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973). Use uma conta que seja um administrador no Exchange Server local e que tenha uma licença para usar o Exchange Server.

2. Acesse o **Intune** > **Acesso do Exchange**.  

3. Em **Configuração**, escolha **Conector local do Exchange ActiveSync** e selecione **Adicionar**.

4. Na página **Adicionar Conector**, selecione **Baixar o conector local**. O conector do Intune ao Exchange está em uma pasta compactada (.zip) que pode ser aberta ou salva. Na caixa de diálogo **Download de Arquivos**, escolha **Salvar** para armazenar a pasta compactada em um local seguro.


## <a name="install-and-configure-the-intune-exchange-connector"></a>Instalar e configurar o conector do Intune ao Exchange

Siga estas etapas para instalar o conector do Intune ao Exchange. Se você tiver várias organizações do Exchange, repita estas etapas para cada conector do Exchange que você deseja configurar.

1. Em um sistema operacional compatível com o conector do Intune ao Exchange, extraia os arquivos em **Exchange_Connector_Setup.zip** para um local seguro.
   > [!IMPORTANT]
   > Não renomeie ou mova os arquivos que estão na pasta *Exchange_Connector_Setup*. Essas alterações podem causar falha na instalação do conector.

2. Depois que os arquivos forem extraídos, abra a pasta extraída e clique duas vezes em **Exchange_Connector_Setup.exe** para instalar o conector.

   > [!IMPORTANT]
   > Se a pasta de destino não for um local seguro, exclua o arquivo de certificado *MicrosoftIntune.accountcert* ao concluir a instalação dos conectores locais.

3. Na caixa de diálogo **Microsoft Intune Exchange Connector**, selecione **Microsoft Exchange Server Local** ou **Microsoft Exchange Server Hospedado**.

   ![Imagem mostrando onde escolher o tipo de Exchange Server](./media/exchange-connector-install/intune-sa-exchange-connector-config.png)

   Para um Exchange Server local, forneça o nome do servidor ou um nome de domínio totalmente qualificado do Exchange Server que hospeda a função de **servidor Acesso para Cliente**.

   Para um Exchange Server hospedado, forneça o endereço do Exchange Server. Para encontrar o URL do Exchange Server Hospedado:

   1. Abra o Outlook para Office 365.

   2. Selecione o ícone **?** no canto superior esquerdo e selecione **Sobre**.

   3. Localize o valor **Servidor Externo POP** .

   4. Clique em **Servidor Proxy** para especificar as configurações do servidor proxy para seu Exchange Server hospedado.

       1. Selecione **Usar um servidor proxy ao sincronizar informações do dispositivo móvel**.

       1. Insira o **nome do servidor proxy** e o **número da porta** a serem usados para acessar o servidor.

       1. Se forem necessárias credenciais de usuário para acessar o servidor proxy, selecione **Usar credenciais para se conectar ao servidor proxy**. Em seguida, digite o **domínio\usuário** e a **senha**.

       1. Selecione **OK**.

4. Nos campos **Usuário (domínio\usuário)** e **Senha**, insira as credenciais para se conectar ao Exchange Server. A conta especificada deve ter uma licença para usar o Intune. 

5. Forneça as credenciais para enviar notificações à caixa de entrada do Exchange Server do usuário. Este usuário pode ser dedicado a apenas notificações. O usuário de notificações precisa de uma caixa de correio do Exchange para enviar notificações por email. Você pode configurar essas notificações usando as políticas de acesso condicional no Intune.  

   Garanta que o serviço Descoberta Automática e os Serviços Web do Exchange estejam configurados no CAS do Exchange. Para obter mais informações, consulte [Servidor de Acesso para Cliente](https://technet.microsoft.com/library/dd298114.aspx).

6. No campo **Senha**, forneça a senha da conta para habilitar o Intune a acessar o Exchange Server.

   > [!NOTE]
   > A conta usada para entrar no locatário precisa ser pelo menos um Administrador de serviços do Intune. Sem essa conta de administrador, você receberá uma falha de conexão com o erro "O servidor remoto retornou um erro: (400) Solicitação incorreta".

7. Selecione **Conectar**.

   > [!NOTE]
   > Pode levar alguns minutos para configurar a conexão.

Durante a configuração, o conector do Exchange armazena as configurações de proxy para habilitar o acesso à Internet. Se as configurações de proxy forem alteradas, reconfigure o conector do Exchange para aplicar as configurações de proxy atualizadas a ele.

Após o conector do Exchange configurar a conexão, os dispositivos móveis associados aos usuários que são gerenciados no Exchange serão automaticamente sincronizados e adicionados ao conector do Exchange. Pode levar algum tempo até terminar a sincronização.

> [!NOTE]
> Se você instalar o conector do Intune ao Exchange e, posteriormente, precisar excluir a conexão do Exchange, será necessário desinstalar o conector do computador no qual foi instalado.



## <a name="install-connectors-for-multiple-exchange-organizations"></a>Instalar conectores para várias organizações do Exchange

O Intune é compatível com vários conectores do Intune Exchange por assinatura. Para um locatário com várias organizações do Exchange, você pode configurar apenas um conector para cada organização do Exchange. 

Para instalar conectores para conexão a várias organizações do Exchange, baixe uma vez a pasta .zip. Reutilize esse mesmo arquivo baixado para cada conector que você instalar. Para cada conector adicional, siga as etapas na seção anterior para extrair e executar o programa de instalação em um servidor na organização do Exchange.

Cada organização do Exchange que se conecta ao Intune é compatível com alta disponibilidade, monitoramento e sincronização manual. As seções a seguir descrevem esses recursos.

## <a name="on-premises-intune-exchange-connector-high-availability-support"></a>Suporte a alta disponibilidade do conector do Intune ao Exchange local  

Para o conector local, alta disponibilidade significa que, se o CAS do Exchange que o conector usa se tornar indisponível, o conector poderá mudar para um CAS diferente naquela organização do Exchange. O conector do Exchange em si não é compatível com alta disponibilidade. Se o conector falhar, não haverá failover automático. Você deve [instalar um novo conector](#reinstall-the-intune-exchange-connector) para substituir o conector com falha. 

Para fazer failover, o conector usa o CAS especificado para criar uma conexão bem-sucedida com o Exchange. Em seguida, ele descobre os CASs adicionais daquela organização do Exchange. Essa descoberta permite que o conector faça failover para outro CAS caso algum esteja disponível, até que o CAS principal fique disponível. 

Por padrão, a descoberta de outros CASs é habilitada. Se você precisar desativar o failover:  
1. No servidor em que o conector do Exchange está instalado, acesse **%*ProgramData*%\Microsoft\Windows Intune Exchange Connector**. 
2. Usando um editor de texto, abra **OnPremisesExchangeConnectorServiceConfiguration.xml**.
3. Altere **\<IsCasFailoverEnabled>*true*\</IsCasFailoverEnabled>** para **\<IsCasFailoverEnabled>*false*\</IsCasFailoverEnabled>** .  
 
## <a name="performance-tune-the-exchange-connector-optional"></a>Ajustar o desempenho do conector do Exchange (opcional)

Quando o Exchange ActiveSync dá suporte a 5.000 dispositivos ou mais, você pode definir uma configuração opcional para melhorar o desempenho do conector. Você aumenta o desempenho habilitando o Exchange para usar várias instâncias de um espaço de execução de comando do PowerShell. 

Antes de fazer essa alteração, verifique se a conta usada para executar o conector do Exchange não é usada para outros fins de gerenciamento do Exchange. Uma conta do Exchange tem um número limitado de espaços de execução, e o conector usará a maioria deles. 

O ajuste de desempenho não é adequado para conectores executados em um hardware mais antigo ou mais lento.  

Para melhorar o desempenho do conector do Exchange: 

1. No servidor em que o conector está instalado, abra o diretório de instalação do conector.  A localização padrão é *C:\ProgramData\Microsoft\Windows Intune Exchange Connector*. 
2. Edite o arquivo *OnPremisesExchangeConnectorServiceConfiguration.xml*.
3. Localize **EnableParallelCommandSupport** e defina o valor como **true**:  
     
   \<EnableParallelCommandSupport>true\</EnableParallelCommandSupport>
4. Salve o arquivo e reinicie o serviço Microsoft Intune Exchange Connector.

## <a name="reinstall-the-intune-exchange-connector"></a>Reinstalar o conector do Intune ao Exchange

Talvez seja necessário reinstalar um conector do Intune ao Exchange. Como apenas um conector pode se conectar a cada organização do Exchange, se você instalar um segundo conector para a organização, o novo conector instalado substituirá o conector original.

1. Para instalar o novo conector, siga as etapas na seção [Instalar e configurar o conector do Exchange](#install-and-configure-the-intune-exchange-connector). 
2. Quando solicitado, selecione **Substituir** para instalar o novo conector.  
   ![Aviso de configuração para substituir um conector](./media/exchange-connector-install/prompt-to-replace.png)

3. Continue com as etapas da seção [Instalar e configurar o conector do Intune](#install-and-configure-the-intune-exchange-connector) e entre novamente no Intune.
4. Na janela final, selecione **Fechar** para concluir a instalação.  
   ![Concluir a instalação](./media/exchange-connector-install/successful-reinstall.png)
 

## <a name="monitor-an-exchange-connector"></a>Monitorar um conector do Exchange

Após você configurar o conector do Exchange com êxito, será possível exibir o status das conexões e a última tentativa de sincronização bem-sucedida. 

Para validar a conexão do conector do Exchange:

1. No Painel do Intune, escolha **Acesso ao Exchange**.
2. Selecione **Acesso local do Exchange**, para verificar o status da conexão para cada conector do Exchange.

Você também pode verificar a hora e data da última tentativa de sincronização bem-sucedida.

Na versão 1710 do Intune em diante, você poderá usar o [pacote de gerenciamento do System Center Operations Manager para Exchange Connector e Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True). O pacote de gerenciamento oferece diferentes maneiras de monitorar o conector do Exchange quando for necessário solucionar problemas.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Forçar manualmente uma sincronização rápida ou completa

Um conector do Intune ao Exchange sincroniza de modo automático os registros de dispositivo do EAS e do Intune regularmente. Se o status de conformidade de um dispositivo for alterado, o processo de sincronização automática atualizará os registros regularmente para que o acesso ao dispositivo possa ser bloqueado ou permitido.

- Uma **sincronização rápida** ocorre regularmente, várias vezes ao dia. Uma sincronização rápida recupera informações de dispositivo para usuários do Exchange local e licenciados no Intune direcionados ao acesso condicional e que foram alterados desde a última sincronização.

- Uma **sincronização completa** ocorre uma vez por dia por padrão. Uma sincronização completa recupera informações do dispositivo para todos os usuários do Exchange local e licenciados no Intune direcionados ao acesso condicional. Uma sincronização completa também recupera informações do servidor Exchange e garante que a configuração que o Intune especifica no portal do Azure seja atualizada no Exchange Server. 


Você pode forçar um conector a executar uma sincronização usando as opções de **Sincronização Rápida** ou **Sincronização Completa** no painel do Intune:

   1. No Painel do Intune, escolha **Acesso ao Exchange**.
   2. Selecione **Acesso local ao Exchange**.
   3. Selecione o conector que você deseja sincronizar e, em seguida, escolha **Sincronização Rápida** ou **Sincronização Completa**.

## <a name="next-steps"></a>Próximas etapas

Criar uma [política de Acesso Condicional para os servidores Exchange locais](conditional-access-exchange-create.md).
