---
title: "Gerenciar dispositivos com o Intune| Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba como exibir dispositivos gerenciados com o Intune e executar várias operações neles."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 040c4e18d87110ab7380a64540d08127574a7c46
ms.openlocfilehash: 5a967cc1be387f83f95591186f786db61d3debcd


---

# <a name="what-is-device-management"></a>O que é o gerenciamento de dispositivo? 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A carga de trabalho **Dispositivos e grupos** fornece ideias sobre dispositivos gerenciados e permite que você execute tarefas remotas neles. Para acessar a carga de trabalho:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos e Grupos**.

    ![Carga de trabalho de dispositivos e grupos](./media/devices-and-groups-workload.png)

Agora, escolha uma das seguintes opções:

- **Visão geral** Obtenha informações sobre os dispositivos registrados e os sistemas operacionais que cada dispositivo executado.
- **Gerenciar** – Escolha **Todos os Dispositivos** para ver uma lista de todos os dispositivos gerenciados.
    Selecione um desses dispositivos na lista para abrir a folha <*nome do dispositivo*> **Visão geral** na qual você pode selecionar um destes:
    - **Visão geral** – Veja informações gerais sobre o dispositivo, incluindo informações sobre seu nome, proprietário, se ele é um dispositivo BYOD, quando foi seu último check-in e muito mais. Além disso, você pode executar as seguintes ações remotas no dispositivo (nem todas as ações têm suporte em todas as plataformas de dispositivo):
        - **Remover dados da empresa** – Remove somente os dados da empresa gerenciados pelo Intune. Não remove dados pessoais do dispositivo. O dispositivo não será mais gerenciado pelo Intune e não será capaz de acessar recursos corporativos (sem suporte para dispositivos Windows que fazem parte do Azure Active Directory).
        - **Redefinição de fábrica** – Retorna o dispositivo para suas configurações padrão. O dispositivo não será gerenciado pelo Intune e dados pessoais e da empresa serão removidos. Você não pode desfazer essa ação.
        - **Bloqueio remoto** – Bloqueia o dispositivo. O proprietário do dispositivo deve usar a senha para desbloqueá-lo. Você pode bloquear remotamente apenas um dispositivo que tenha um PIN ou senha definida.
        - **Redefinir senha** – Gera uma nova senha para o dispositivo que será exibida na folha <*nome do dispositivo*> **Visão geral**.
        - **Bypass de Bloqueio de Ativação** – Isso removerá o bloqueio de ativação de um dispositivo iOS sem a ID da Apple e a senha do usuário. Depois de fazer o bypass do bloqueio de ativação, o dispositivo ativa-o novamente quando inicia o aplicativo o Localizar Meu iPhone. Faça bypass do bloqueio de ativação apenas se você tiver acesso físico ao dispositivo.
        - **Modo de perda** – Se um dispositivo foi roubado, você pode habilitar o modo de perda. Ele permite especificar uma mensagem e um número de telefone que serão exibidos na tela de bloqueio do dispositivo.
        - **Reiniciar** – Faz com que o dispositivo seja reiniciado. O proprietário do dispositivo não será notificado automaticamente sobre a reinicialização, portanto ele pode perder trabalho.
        ![Visão geral do dispositivo](http://i.imgur.com/4Rx4VXm.png)
        
    - **Hardware** – Consulte informações mais detalhadas sobre o dispositivo, inclusive do espaço de armazenamento livre, modelo e fabricante e muito mais.
    ![Inventário de hardware de dispositivo gerenciado](./media/hardware-inventory.png)
    - **Aplicativos detectados** – Exibe uma lista de todos os aplicativos que o Intune encontrou instalados no dispositivo.
    ![Nó de aplicativos detectado](./media/detected-applications.png)
- **Monitorar** Escolha **Ações de Dispositivo** para ver uma lista de ações de dispositivo que foram realizadas em dispositivos gerenciados e o estado atual dessas ações.
![Monitorar ações do dispositivo](./media/monitor-device-actions.png)



<!--HONumber=Feb17_HO1-->


