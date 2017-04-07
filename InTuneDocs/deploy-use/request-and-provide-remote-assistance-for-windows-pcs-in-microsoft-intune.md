---
title: "Solicitar e fornecer assistência remota para computadores Windows | Microsoft Docs"
description: "Descreve as etapas administrativas do usuário final e do administrador de TI para fornecer assistência remota para áreas de trabalho do Windows gerenciadas como computadores e iniciar um computador remotamente."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2654491-5144-408a-a45a-644eb91ac1bb
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 10dd2caa9ce1b96424f55e373e904a778390eb15
ms.openlocfilehash: 628875c2f874c824761befd9886d7f7987c045df
ms.lasthandoff: 12/16/2016


---

# <a name="request-and-provide-remote-assistance-for-windows-pcs"></a>Solicitar e fornecer assistência remota para computadores Windows

As informações descritas neste tópico se aplicam somente a áreas de trabalho do Windows que estão sendo gerenciadas como computadores por meio do cliente de software do Intune.

O Intune pode usar o software [TeamViewer](https://www.teamviewer.com), adquirido separadamente, para permitir que você dê assistência remota para os usuários que executam o cliente de software do Intune. Quando um usuário solicita ajuda do Microsoft Intune Center, você será informado por um alerta, pode aceitar a solicitação e, em seguida, fornecer assistência. Esta funcionalidade substitui a funcionalidade de Assistência Remota do Windows existente no Intune.


## <a name="before-you-start"></a>Antes de começar

Antes de começar a estabelecer e responder às solicitações de assistência remota, verifique se os seguintes pré-requisitos estão em vigor:

- Você deve ter se [inscrito para uma conta do TeamViewer](https://login.teamviewer.com/LogOn#register) fazer logon no site do TeamViewer.
- Os computadores Windows que você deseja administrar devem ser [gerenciados pelo cliente de software do Windows](manage-windows-pcs-with-microsoft-intune.md)
- Todos os sistemas operacionais de computador Windows com suporte pelo Intune podem ser administrados.

## <a name="configure-the-teamviewer-connector"></a>Configure o TeamViewer Connector

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador**.
2. No espaço de trabalho **Administrador**, escolha **TeamViewer**.
3. Na página **TeamViewer** em **TeamViewer Connector**, escolha **Habilitar**.
4. Na caixa de diálogo **Habilitar TeamViewer**, exiba e, em seguida, **Aceite** os termos de licença. Se você ainda não tem uma licença do TeamViewer, escolha **Comprar uma licença do TeamViewer**.
5. Depois que a janela do navegador do TeamViewer for aberta, entre no site com suas credenciais do TeamViewer.
6. No site do TeamViewer, leia e aceite as opções para permitir que o Intune se conecte com o TeamViewer.
7. No console do Intune, verifique se o item **TeamViewer Connector** é mostrado como **Habilitado**.


## <a name="open-a-remote-assistance-request-end-user"></a>Abrir uma solicitação de assistência remota (usuário final)

1. Em um cliente de computador Windows, abra o **Microsoft Intune Center**.
2. Em **Assistência Remota**, escolha **Solicitar Assistência Remota**.
3. Depois de aprovar a solicitação (veja abaixo), o TeamViewer abrirá no cliente. O usuário deve aceitar quaisquer mensagens indicando que o navegador da Web está tentando abrir o aplicativo TeamViewer.
4. O usuário vê uma mensagem perguntando se você pode controlar o seu computador. Eles devem aceitar esta mensagem para continuar.
5. Durante a sessão de assistência remota, o usuário vê uma janela que mostra a eles que estão conectados. Se eles fecharem esta janela, a sessão remota será encerrada.

## <a name="respond-to-a-remote-assistance-request"></a>Responder a uma solicitação de assistência remota

1. Quando um usuário envia uma solicitação de assistência remota, você poderá exibi-la no espaço de trabalho **Alertas**, em **Monitoramento** > **Assistência Remota**. Por exemplo:
> ![Captura de tela de uma solicitação de assistência remota](./media/team-viewer.png)

<br>Se uma solicitação não for atendida por mais de 4 horas, ela será removida.
2. Para aceitar a solicitação, escolha **Aprovar solicitação e iniciar Assistência Remota**.
3. Na caixa de diálogo **Uma nova solicitação de assistência remota está pendente**, escolha **Aceitar a solicitação de assistência remota**. Se ele ainda não estiver instalado, o TeamViewer instalará todos os aplicativos necessários no computador.
4. O TeamViewer notifica o usuário final que você deseja assumir o controle do seu computador. Depois que o usuário aceitar a solicitação, uma janela do TeamViewer será aberta e você poderá controlar o computador.

Durante uma sessão de assistência remota, você poderá usar todos os comandos disponíveis do TeamViewer para controlar o computador remoto. Para obter ajuda com esses comandos, baixe o [Manual for remote control](http://www.teamviewer.com/en/support/documents/) (Manual para controle remoto) do site do TeamViewer.

## <a name="close-the-remote-assistance-session"></a>Feche a sessão de assistência remota

Do menu **Ações** da janela **TeamViewer**, escolha **Encerrar a Sessão**.

## <a name="remotely-restart-a-windows-pc"></a>Reiniciar remotamente um computador Windows
Ao ajudar os usuários com problemas, talvez seja necessário reiniciar remotamente os computadores de tempos em tempos. Use as etapas a seguir para reiniciar remotamente um computador Windows.

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contém o computador que você deseja reiniciar).

2.  Selecione um ou mais computadores e escolha **Tarefas Remotas** &gt; **Reiniciar o Computador**.

3.  Para exibir o status da tarefa, selecione **Tarefas Remotas** no canto inferior direito da página.

4.  Na caixa de diálogo **Status da tarefa** , examine as tarefas remotas atuais, seus status, nome do dispositivo e todos os erros reportados.

### <a name="see-also"></a>Consulte também

[Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
