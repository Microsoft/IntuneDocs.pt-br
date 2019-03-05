---
title: Instalar o software cliente do computador
description: Use este guia para ajudá-lo a ter os computadores Windows gerenciados pelo software cliente do Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
ms.date: 07/13/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 48079adfd8ff2f635ebf63370da62f7e428dcb40
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238499"
---
# <a name="install-the-intune-software-client-on-windows-pcs"></a>Instalar o cliente de software Intune em computadores Windows

[!INCLUDE [classic-portal](includes/classic-portal.md)]

> [!NOTE]
> Use o Microsoft Intune para gerenciar computadores Windows como [dispositivos móveis com o MDM (gerenciamento de dispositivo móvel)](windows-enroll.md) ou como computadores com o cliente de software do Intune, conforme descrito abaixo. No entanto, a Microsoft recomenda que os clientes usem a [solução de gerenciamento MDM](windows-enroll.md) sempre que possível. Para saber mais, confira [Comparar o gerenciamento de computadores Windows como computadores ou dispositivos móveis](pc-management-comparison.md) 


Computadores Windows podem ser registrados instalando o software cliente do Intune. É possível instalar o software cliente do Intune usando os seguintes métodos:

- Pelo administrador de TI, usando um destes métodos: instalação manual, política de grupo ou instalação incluída em uma imagem de disco

- Por usuários finais, instalando o software cliente manualmente

O software cliente do Intune conta com o software mínimo necessário para registrar o PC no gerenciamento do Intune. Depois de registrar um PC, o software cliente do Intune baixa o software cliente completo que é necessário para o gerenciamento do PC.

Esta série de downloads reduz o impacto sobre a largura de banda da rede e diminui o tempo necessário para registrar inicialmente o computador no Intune. Ela também garante que o cliente tenha o software mais recente disponível após a conclusão do download do segundo.

Uma licença do Intune permite que a instalação do software cliente do Intune em até cinco computadores.

## <a name="download-the-intune-client-software"></a>Baixe o software cliente do Intune

Todos os métodos, exceto quando os próprios usuários instalam o software cliente do Intune, exigem que os administradores de TI baixem primeiro o software a fim de implantá-lo posteriormente para os usuários finais.

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Administração** &gt; **Download de Software Cliente**.

   ![Baixe o Intune no computador cliente](./media/https://docs.microsoft.com/intune/media/install-the-windows-pc-client/pc-sa-client-download.png)

2. Na página **Download de Software Cliente**, clique em **Baixar Software Cliente**. Em seguida, salve o pacote **Microsoft_Intune_Setup.zip** que contém o software em um local seguro na sua rede.

   O pacote de instalação do software cliente do Intune contém informações exclusivas e específicas sobre sua conta, que estão disponíveis por meio de um certificado inserido. Se usuários não autorizados obtiverem acesso ao pacote de instalação, eles poderão registrar computadores na conta representada por seu certificado integrado e poderão obter acesso aos recursos da empresa.

3. Extraia o conteúdo do pacote de instalação para o local seguro na sua rede.

    > [!IMPORTANT]
    > Não renomeie ou remova o arquivo **ACCOUNTCERT** extraído. Caso contrário, ocorrerá uma falha na instalação do software cliente.

## <a name="deploy-the-client-software-manually"></a>Implante manualmente o software cliente

Nos computadores em que o software cliente será instalado, vá para a pasta na qual os arquivos de instalação do software cliente foram colocados. Em seguida, execute **Microsoft_Intune_Setup.exe** para instalar o software cliente.

> [!NOTE]
> O status da instalação será exibido ao passar o mouse sobre o ícone na barra de tarefas no computador cliente.

## <a name="deploy-the-client-software-by-using-group-policy"></a>Implante o software cliente usando a Política de Grupo

1.  Na pasta que contém os arquivos **Microsoft_Intune_Setup.exe** e **MicrosoftIntune.accountcert**, execute o seguinte comando para extrair os programas de instalação baseados no Windows Installer para computadores de 32 e 64 bits:

    ```
    Microsoft_Intune_Setup.exe/Extract <destination folder>
    ```

2.  Copie os arquivos **Microsoft_Intune_x86.msi**, **Microsoft_Intune_x64.msi** e **MicrosoftIntune.accountcert** para uma localização da rede que possa ser acessada por todos os computadores nos quais o software cliente será instalado.

    > [!IMPORTANT]
    > Não separe ou renomeie os arquivos ou ocorrerá uma falha na instalação do software cliente.

3.  Use a Política de grupo para implantar o software nos computadores da sua rede.

    Para obter mais informações sobre como usar a Política de Grupo para implantar software automaticamente, consulte [Política de Grupo para Iniciantes](https://technet.microsoft.com/library/hh147307.aspx).

## <a name="deploy-the-client-software-as-part-of-an-image"></a>Implante o software cliente como parte de uma imagem
É possível implantar o software cliente do Intune em computadores como parte de uma imagem do sistema operacional, usando o seguinte procedimento como guia:

1.  Copie os arquivos de instalação do cliente **Microsoft_Intune_Setup.exe** e **MicrosoftIntune.accountcert** na pasta **%Systemdrive%\Temp\Microsoft_Intune_Setup** no computador de referência.

2.  Crie a entrada de registro **WindowsIntuneEnrollPending** , adicionando o seguinte comando ao script **SetupComplete.cmd** :

    ```
    %windir%\system32\reg.exe add HKEY_LOCAL_MACHINE\Software\Microsoft\Onlinemanagement\Deployment /v
    WindowsIntuneEnrollPending /t REG_DWORD /d 1
    ```

3.  Adicione o seguinte comando a **setupcomplete.cmd** para executar o pacote de registro com o argumento de linha de comando /PrepareEnroll:

    ```
    %systemdrive%\temp\Microsoft_Intune_Setup\Microsoft_Intune_Setup.exe /PrepareEnroll
    ```
    > [!TIP]
    > O script **SetupComplete.cmd** permite que a Instalação do Windows efetue modificações no sistema antes que um usuário faça logon. O argumento de linha de comando **/PrepareEnroll** prepara um computador definido como destino de forma que ele seja automaticamente registrado no Intune após a conclusão da Instalação do Windows.

4.  Coloque o **SetupComplete.cmd** na pasta **%Windir%\Setup\Scripts** do computador de referência.

5.  Capture uma imagem do computador de referência e implante-a nos computadores de destino.

    Quando o computador definido como destino for reiniciado após a conclusão da instalação do Windows, a chave do Registro **WindowsIntuneEnrollPending** será criada. O pacote de registro verifica se o computador está registrado. Se o computador estiver inscrito, nenhuma outra ação adicional será executada. Se o computador não estiver registrado, o pacote de registro criará uma Tarefa de registro automática do Microsoft Intune.

    Quando a tarefa de Registro automático do Intune for executada no próximo horário agendado, ela verificará a existência do valor do registro **WindowsIntuneEnrollPending** e tentará registrar o computador definido como destino no Intune. Se a inscrição falhar por algum motivo, haverá uma nova tentativa na próxima vez que a tarefa for executada. As tentativas continuam por um mês.

    A tarefa de registro automático do Intune, o valor do Registro **WindowsIntuneEnrollPending** e o certificado da conta serão excluídos do computador definido como destino quando o registro for concluído com êxito ou depois de um mês (o que ocorrer primeiro).

## <a name="instruct-users-to-self-enroll"></a>Instrua os usuários a se registrarem por conta própria

Os usuários podem instalar o software cliente do Intune visitando o [site do Portal da Empresa](https://portal.manage.microsoft.com). As informações exatas que os usuários visualizam no portal da Web podem variar, de acordo com a Autoridade de MDM da sua conta e a plataforma e versão do computador do usuário.

Se os usuários ainda não tiverem recebido uma licença do Intune ou se a autoridade de MDM da organização não tiver sido definida para o Intune, as opções de registro não serão exibidas aos usuários.

Se os usuários tiverem recebido uma licença do Intune e a autoridade de MDM da organização tiver sido definida para o Intune:

- Os usuários de computador do Windows 7 ou Windows 8 podem ver APENAS a opção de registro no Intune baixando e instalando o software cliente do computador exclusivo de sua organização.

- Os usuários de do Windows 8.1 ou Windows 10 têm duas opções de registro:

  -  **Inscrever o PC como um dispositivo móvel**: Os usuários clicam no botão **Saiba mais sobre como se registrar** e recebem instruções sobre como registrar seu PC como um dispositivo móvel. Esse botão é exibido em destaque, porque o registro do MDM é considerado padrão e a opção de registro preferida. No entanto, a opção de MDM não é aplicável a esse tópico, que aborda somente a instalação do software cliente.
  - **Inscrever o PC usando o software cliente do Intune**: Você precisará pedir que os usuários selecionem o link **Clique aqui para baixá-lo**, que leva à instalação do software cliente.

A tabela a seguir resume as opções.

  ![Opções de registro padrão por plataforma](./media/install-the-windows-pc-client/default-enrollment-options-table.png)

As capturas de tela a seguir mostram o que os usuários veem ao registrar seus dispositivos usando o software cliente.

Primeiro, solicita-se que os usuários identifiquem ou registrem seu dispositivo.

  ![identificar ou registrar dispositivo](./media/install-the-windows-pc-client/identify-device-or-enroll.png)

Para que os usuários instalem o software cliente do PC, você deverá pedir que eles selecionem o link **Clique aqui para baixá-lo**, que permite aos usuários baixar o software cliente do PC e os conduz pelo processo de instalação. O botão **Saiba mais sobre como se registrar** leva os usuários para a documentação sobre como se registrar usando o registro do MDM, algo que não é relevante para essas instruções do software cliente.

  ![selecione o link Clique aqui para baixá-lo](./media/install-the-windows-pc-client/enroll-your-windows-device.png)

Quando os usuários clicarem no link, eles verão o botão **Baixar Software**, o qual eles devem selecionar para iniciar a instalação do software cliente do PC.

  ![selecionar o botão de Baixar Software](./media/install-the-windows-pc-client/download-pc-client-software.png)

Em seguida, pede-se aos usuários que insiram suas credenciais corporativas.

  ![Entre usando as suas credenciais](./media/install-the-windows-pc-client/sign-in-to-intune.png)

Os usuários são levados para a página de boas-vindas da instalação.

  ![Página de boas-vindas da instalação do cliente do PC](./media/install-the-windows-pc-client/welcome-to-pc-agent-install-wizard.png)

Os usuários devem clicar em **Avançar** para iniciar a instalação.

  ![Página de boas-vindas da instalação do cliente do PC](./media/install-the-windows-pc-client/welcome-to-pc-agent-install-wizard.png)

Quando a instalação for concluída, os usuários devem clicar em **Concluir**.

  ![Concluir a instalação do cliente do PC](./media/install-the-windows-pc-client/completed-the-setup-wizard.png)

Se os usuários tentarem registrar seu PC como um dispositivo móvel depois de ter feito o registro usando o software cliente do Intune no PC, eles verão a tela de erro a seguir.

  ![Tela mostrada se PC já for registrado](./media/install-the-windows-pc-client/page-shown-if-pc-already-enrolled.png)

## <a name="monitor-and-validate-successful-client-deployment"></a>Monitorar e validar a implantação com êxito do cliente
Use um dos procedimentos a seguir para ajudá-lo a monitorar e a validar a implantação do cliente com êxito.

### <a name="to-verify-the-installation-of-the-client-software-from-the-microsoft-intune-administrator-console"></a>Para verificar a instalação do software cliente usando o console de administrador do Microsoft Intune

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Computadores**.

2.  Na lista, encontre os computadores que se comunicam com o Intune ou procure um computador gerenciado específico, digitando o nome do computador (ou qualquer parte do nome) na caixa **Pesquisar dispositivos**.

3.  Examine o status do computador no painel inferior do console. Resolva todos os erros.

### <a name="to-create-a-computer-inventory-report-to-display-all-enrolled-computers"></a>Para criar um relatório de inventário do computador para exibir todos os computadores registrados

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Relatórios** &gt; **Relatórios de Inventário do Computador**.

2.  Na página **Criar Novo Relatório**, deixe todos os campos com os valores padrão (a menos que deseje aplicar filtros) e clique em **Exibir Relatório**.

3.  A página **Relatório de inventário do computador** é aberta em uma nova janela e exibe todos os computadores registrados com sucesso no Intune.

    > [!TIP]
    > Clique em qualquer cabeçalho de coluna no relatório para classificar a lista pelo conteúdo dessa coluna.

## <a name="uninstall-the-windows-client-software"></a>Desinstalar o software cliente do Windows

Há duas maneiras de cancelar o registro de software cliente do Windows:

- No console de administração do Intune (método recomendado)
- De um prompt de comando no cliente

### <a name="unenroll-by-using-the-intune-admin-console"></a>Cancelar o registro usando o console de administração do Intune

Para cancelar o registro do cliente de software usando o console de administração do Intune, vá para **Grupos** > **Todos os Computadores** > **Dispositivos**. Clique com o botão direito do mouse no cliente e selecione **Desativar/Apagar**.

### <a name="unenroll-by-using-a-command-prompt-on-the-client"></a>Cancelar o registro usando um prompt de comando no cliente

Usando um prompt de comandos com privilégios elevados, execute um dos comandos a seguir.

**Método 1**:

    "C:\Program Files\Microsoft\OnlineManagement\Common\ProvisioningUtil.exe" /UninstallAgents /MicrosoftIntune

**Método 2** Observe que todos esses agentes são instalados em cada SKU do Windows:

    wmic product where name="Microsoft Endpoint Protection Management Components" call uninstall
    wmic product where name="Microsoft Intune Notification Service" call uninstall
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall
    wmic product where name="Microsoft Online Management Policy Agent" call uninstall
    wmic product where name="Microsoft Policy Platform" call uninstall
    wmic product where name="Microsoft Security Client" call uninstall
    wmic product where name="Microsoft Online Management Client" call uninstall
    wmic product where name="Microsoft Online Management Client Service" call uninstall
    wmic product where name="Microsoft Easy Assist v2" call uninstall
    wmic product where name="Microsoft Intune Monitoring Agent" call uninstall
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall
    wmic product where name="Windows Firewall Configuration Provider" call uninstall
    wmic product where name="Microsoft Intune Center" call uninstall
    wmic product where name="Microsoft Online Management Update Manager" call uninstall
    wmic product where name="Microsoft Online Management Agent Installer" call uninstall
    wmic product where name="Microsoft Intune" call uninstall
    wmic product where name="Windows Endpoint Protection Management Components" call uninstall
    wmic product where name="Windows Intune Notification Service" call uninstall
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall
    wmic product where name="Windows Online Management Policy Agent" call uninstall
    wmic product where name="Windows Policy Platform" call uninstall
    wmic product where name="Windows Security Client" call uninstall
    wmic product where name="Windows Online Management Client" call uninstall
    wmic product where name="Windows Online Management Client Service" call uninstall
    wmic product where name="Windows Easy Assist v2" call uninstall
    wmic product where name="Windows Intune Monitoring Agent" call uninstall
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall
    wmic product where name="Windows Firewall Configuration Provider" call uninstall
    wmic product where name="Windows Intune Center" call uninstall
    wmic product where name="Windows Online Management Update Manager" call uninstall
    wmic product where name="Windows Online Management Agent Installer" call uninstall
    wmic product where name="Windows Intune" call uninstall

> [!TIP]
> O cancelamento de registro do cliente deixará um registro do lado do serviço obsoleto para o cliente afetado. O processo de cancelamento de registro é assíncrono e há nove agentes para desinstalação, portanto, pode demorar até 30 minutos para concluir.

### <a name="check-the-unenrollment-status"></a>Verificar o status do cancelamento de registro

Verifique o "%ProgramFiles%\Microsoft\OnlineManagement" e certifique-se de que somente os diretórios a seguir sejam exibidos à esquerda:

- AgentInstaller
- Logs
- Updates
- Comum

### <a name="remove-the-onlinemanagement-folder"></a>Remover a pasta OnlineManagement

O processo de cancelamento de registro não remove a pasta OnlineManagement. Aguarde 30 minutos após a desinstalação e, em seguida, execute este comando. Se você o executar muito cedo, a desinstalação poderá ser deixada em um estado desconhecido. Para remover a pasta, inicie um prompt elevado e execute:

    "rd /s /q %ProgramFiles%\Microsoft\OnlineManagement".

### <a name="next-steps"></a>Próximas etapas
[Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
