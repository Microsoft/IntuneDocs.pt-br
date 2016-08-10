---
title: Tarefas comuns de gerenciamento de computadores Windows | Microsoft Intune
description: "Examine as tarefas deste tópico para saber como gerenciar seus computadores que executam o software cliente do computador do Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6ddb0fda0e818b09d274276076fd6310d29b99cb
ms.openlocfilehash: 8ce6b10478927177e5d6d8de0677cf06bed00f08


---

# Tarefas comuns de gerenciamento de computadores Windows com o cliente de computador do Microsoft Intune
Examine as tarefas deste tópico para saber como gerenciar seus computadores que executam o software cliente do computador do Intune. Se você ainda não tiver instalado o cliente em seus computadores, consulte [Install the Windows PC client with Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md) (Instalar o cliente do computador Windows com o Microsoft Intune).


## Usar políticas para simplificar o gerenciamento de computador
### Gerenciar o Firewall do Windows
As políticas simplificam a administração de configurações do Firewall do Windows em computadores gerenciados. Para obter detalhes, consulte [Help protect Windows PCs using Windows Firewall policies in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) (Ajude a proteger computadores Windows usando políticas de Firewall do Windows no Microsoft Intune).

### Gerenciar o Microsoft Intune Center
O Microsoft Intune Center permite que os usuários:

-   Obtenham aplicativos a partir do portal da empresa.

-   Procurem atualizações.

-   Gerencie o Endpoint Protection do Microsoft Intune.

-  Solicitem assistência remota.

O Microsoft Intune Center é instalado em todos os computadores gerenciados. Você pode definir as seguintes configurações em uma política do Intune e elas são exibidas para os usuários no Microsoft Intune Center:

|Configuração de política|Detalhes|
|------------------|--------------------|
|**Nome**|O nome do administrador que gerencia o computador.<br /><br />Comprimento máximo: 40 caracteres|
|**Número do telefone**|O número do telefone do administrador que gerencia o computador.<br /><br />Comprimento máximo: 20 caracteres|
|**Endereço de email**|O endereço de email do administrador que gerencia o computador.<br /><br />Comprimento máximo: 40 caracteres|
|**Nome do site**|O nome do site de suporte para os usuários.<br /><br />Comprimento máximo: 40 caracteres|
|**URL do site**|A URL do site de suporte.<br /><br />Comprimento máximo: 150 caracteres|
|**Anotações**|Uma observação que é exibida para os usuários.<br /><br />Comprimento máximo: 120 caracteres|

### Gerenciar configurações de atualização de software
Use as políticas para definir as configurações que os computadores gerenciados usam para procurar e baixar atualizações de software da Microsoft e de terceiros. Para mais informações, consulte [Keep Windows PCs up to date with software updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) (Manter computadores Windows atualizados com as atualizações de software no Microsoft Intune).

### Gerenciar configurações do Endpoint Protection
Use as políticas para definir as configurações do Endpoint Protection que você implantará depois nos computadores gerenciados. Isso inclui as agendas de verificação, ações a serem tomadas quando um malware for detectado e muito mais. Para obter mais informações, consulte [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) (Ajudar a proteger computadores Windows com o Endpoint Protection para Microsoft Intune).

## Exibir o inventário de hardware e software
O Intune coleta informações detalhadas sobre o hardware e o software dos computadores gerenciados. Use as informações nos procedimentos a seguir para aprender a criar:

-   Um relatório que relaciona as informações sobre os recursos de hardware dos computadores.

-   Um relatório que relaciona o software instalado em cada computador.

-   Como atualizar o inventário de um computador para garantir que os dados no relatório estejam atualizados.

### Para exibir informações sobre seus computadores

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Relatórios** &gt; **Relatórios de Inventário de Computador**.

2.  Na página **Criar novo relatório** , aceite os valores padrão ou personalize-os para filtrar os resultados que serão passados como retorno pelo relatório. Por exemplo, você pode selecionar que somente computadores que executem Windows 8.1 sejam exibidos no relatório.

3.  Escolha **Exibir Relatório** para abrir o **Relatório de Inventário do Computador** em uma nova janela.

    Você pode classificar o relatório com base em qualquer uma das colunas, como **Nome**, **Tipo de Chassi** ou **Fabricante** selecionando cada título de coluna.

### Para exibir o software instalado em seus computadores

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Relatórios** &gt; **Relatórios de Software Detectados**.

2.  Na página **Criar novo relatório** , aceite os valores padrão ou personalize-os para filtrar os resultados que serão passados como retorno pelo relatório. Por exemplo, você pode selecionar que apenas o software fornecido pela Microsoft seja exibido no relatório.

3.  Escolha **Exibir Relatório** para abrir o **Relatório de Software Detectado** em uma nova janela.

    O relatório pode ser classificado com base em qualquer uma das colunas, como **Nome**, **Editor** ou **Categoria** selecionando cada título de coluna. Você pode expandir as atualizações nessa lista para mostrar mais detalhes (como os computadores nos quais está instalado) clicando na seta de direção ao lado do item de lista.

### Para atualizar o inventário do computador e garantir que esteja atualizado

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contenha o computador para o qual deseja atualizar o inventário).

2.  Selecione um computador ou pressione e segure a tecla **Ctrl** para selecionar vários computadores.

3.  Na barra de tarefas, clique em **Tarefas Remotas** &gt; **Atualizar Inventário**.

4.  Para exibir o status da tarefa, selecione **Tarefas Remotas** no canto inferior direito da página.

    A caixa de diálogo **Status da tarefa** é exibida e mostra as tarefas remotas atuais, seus status, nome do dispositivo, todos os erros reportados e fornece um link para as informações sobre a solução problemas.


## Reiniciar remotamente um computador Windows

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contenha o computador que deseja reiniciar).

2.  Selecione um ou mais computadores e clique em **Tarefas Remotas** &gt; **Reiniciar Computador**.

3.  Para exibir o status da tarefa, selecione **Tarefas Remotas** no canto inferior direito da página.

4.  Na caixa de diálogo **Status da tarefa** , examine as tarefas remotas atuais, seus status, nome do dispositivo e todos os erros reportados.

## Desativar um computador

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contenha o computador que deseja desativar).

2.  Selecione os dispositivos que deseja desativar e escolha **Desativar/Apagar**.

Para refazer o registro de um computador no Intune, reinstale o software cliente no computador usando as informações no tópico [Install the Windows PC client with Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md) (Instalar o cliente do computador Windows com o Microsoft Intune).

Se um computador não puder se conectar ao Intune, será exibida uma mensagem no espaço de trabalho **Painel**.

Ao desativar um computador:

-   Ele é removido do inventário do Intune e a licença associada ao computador é disponibilizada para reutilização.

-   Seu status não é mais exibido no console do Intune.

-   O Intune remove o software cliente do computador. Se o computador não estiver conectado ao serviço do Intune, o software cliente será removido na próxima vez em que se conectar.

-   O Endpoint Protection do Microsoft Intune é removido do computador. Se o computador tiver outro aplicativo de ponto de extremidade instalado e estiver desabilitado, esse aplicativo poderá ser habilitado novamente depois que o Endpoint Protection do Microsoft Intune for removido para garantir que seus computadores estejam protegidos.

-   Todas as políticas são removidas do computador e os valores que foram definidos pela política serão alterados.

-   O computador não receberá mais atualizações de software ou de definição de malware do serviço do Intune.

-   Dependendo de como estiverem configurados, os computadores desativados poderão continuar a receber atualizações usando o Windows Server Update Services, Windows Update ou Microsoft Update.

    > [!IMPORTANT]
    > Se o software cliente tiver sido instalado com o uso de um GPO (Objeto de Política de Grupo), antes de remover o software cliente você deve remover o GPO para evitar que o software seja reinstalado.

    Se o cliente não desinstalar, leia [Troubleshoot Endpoint Protection](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) (Solucionar problemas de proteção de ponto de extremidade) para obter mais ajuda.

## Gerenciar a vinculação de usuário e dispositivo
Antes de implantar o software em um usuário, você deve vincular o usuário a um computador. Você pode vincular um usuário a vários computadores, mas cada computador pode ser vinculado a apenas um usuário. Os usuários são vinculados automaticamente a quaisquer computadores que se registram no Intune usando o portal da empresa.

### Para vincular um usuário a um computador

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contenha o computador que você deseja vincular a um usuário).

2.  Selecione o computador que deseja vincular a um usuário e escolha **Vincular Usuário**.

    A caixa de diálogo **Vincular Usuário** exibe uma lista de usuários disponíveis com o nome de exibição, ID de usuário e o número de computadores aos quais cada usuário está vinculado. Se um usuário já estiver vinculado ao computador selecionado, o nome e a ID desse usuário serão exibidos em **Usuário atual**. Se o computador não estiver vinculado a nenhum usuário, **Nenhum usuário** aparecerá em **Usuário atual**.

3.  Realize um dos seguintes procedimentos:

    -   Para deixar o computador vinculado ao usuário atual, se houver um, escolha **Cancelar**.

    -   Para remover o vínculo com o usuário atual, se houver, escolha **Remover link **&gt; **OK**.

    -   Para vincular o computador a um novo usuário, na lista **Todos os usuários** , selecione um usuário. Confirme se os dados do usuário estão corretos e escolha **OK**.

> [!TIP]
> Se você quiser restringir a capacidade dos usuários finais de vincular-se a computadores, habilite a opção **Restringir a Capacidade dos Usuários de Vincular-se a Computadores** na política **Configurações do Agente do Microsoft Intune**.

## Solicitar e fornecer assistência remota a computadores Windows que usam o software cliente do Intune

O Microsoft Intune pode usar o software do [TeamViewer](https://www.teamviewer.com) para permitir que os usuários de computadores que executam o software cliente do Intune obtenham ajuda da assistência remota por você. Quando um usuário solicita ajuda do Microsoft Intune Center, você será informado por um alerta, pode aceitar a solicitação e, em seguida, fornecer assistência.
Esta funcionalidade substitui a funcionalidade de Assistência Remota do Windows existente no Intune.


### Antes de começar

Antes de começar a estabelecer e responder às solicitações de assistência remota, você deve garantir que os seguintes pré-requisitos estão em vigor:

- Você deve ter se [inscrito para uma conta do TeamViewer](https://login.teamviewer.com/LogOn#register) fazer logon no site do TeamViewer.
- Computadores Windows que você deseja administrar devem ser [gerenciados pelo cliente do computador Windows](manage-windows-pcs-with-microsoft-intune.md)
- Todos os sistemas operacionais de computador Windows com suporte pelo Intune podem ser administrados.

### Configure o TeamViewer Connector

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador**.
2. No espaço de trabalho **Administrador**, escolha **TeamViewer**.
3. Na página **TeamViewer** em **TeamViewer Connector**, escolha **Habilitar**.
4. Na caixa de diálogo **Habilitar TeamViewer**, exiba e, em seguida, **Aceite** os termos de licença. Se você ainda não tem uma licença do TeamViewer, escolha **Comprar uma licença do TeamViewer**.
5. Depois que a janela do navegador do TeamViewer for aberta, entre no site com suas credenciais do TeamViewer.
6. No site do TeamViewer, leia e aceite as opções para permitir que o Intune se conecte com o TeamViewer.
7. No console do Intune, verifique se o item **TeamViewer Connector** é mostrado como **Habilitado**.


### Abrir uma solicitação de assistência remota (usuário final)

1. Em um cliente de computador Windows, abra o **Microsoft Intune Center**.
2. Em **Assistência Remota**, escolha **Solicitar Assistência Remota**.
3. Depois de aprovar a solicitação (veja abaixo), o TeamViewer abrirá no cliente. O usuário deve aceitar quaisquer mensagens indicando que o navegador da Web está tentando abrir o aplicativo TeamViewer.
4. O usuário vê uma mensagem perguntando se você pode controlar o seu computador. Eles devem aceitar esta mensagem para continuar.
5. Durante a sessão de assistência remota, o usuário vê uma janela que mostra a eles que estão conectados. Se eles fecharem esta janela, a sessão remota será encerrada.

### Responder a uma solicitação de assistência remota

1. Quando um usuário envia uma solicitação de assistência remota, você poderá exibi-la no espaço de trabalho **Alertas**, em **Monitoramento** > **Assistência Remota**. Por exemplo:
> ![Captura de tela de uma solicitação de assistência remota](./media/team-viewer.png)

<br>Se uma solicitação não for atendida por mais de 4 horas, ela será removida.
2. Para aceitar a solicitação, escolha **Aprovar solicitação e iniciar Assistência Remota**.
3. Na caixa de diálogo **Uma nova solicitação de assistência remota está pendente**, escolha **Aceitar a solicitação de assistência remota**. Se ainda não estiver instalado, o TeamViewer instalará todos os aplicativos necessários em seu computador.
4. O TeamViewer notifica o usuário final que você deseja assumir o controle do seu computador. Depois que o usuário aceitar a solicitação, uma janela do TeamViewer será aberta e você poderá controlar o computador.

Durante uma sessão de assistência remota, você poderá usar todos os comandos disponíveis do TeamViewer para controlar o computador remoto. Para obter ajuda com esses comandos, baixe o [Manual for remote control](http://www.teamviewer.com/en/support/documents/) (Manual para controle remoto) do site do TeamViewer.

### Feche a sessão de assistência remota

Do menu **Ações** da janela **TeamViewer**, escolha **Encerrar a Sessão**.



<!--HONumber=Aug16_HO1-->


