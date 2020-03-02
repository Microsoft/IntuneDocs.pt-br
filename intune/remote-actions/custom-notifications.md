---
title: Enviar notificações personalizadas aos usuários com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Usar o Intune para criar e enviar notificações por push personalizadas para usuários de dispositivos iOS/iPadOS e Android
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/25/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5195ee83efb68cea061e69f5cad49e9d43458450
ms.sourcegitcommit: 29f3ba071c9348686d3ad6f3b8864d8557e05b97
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77609362"
---
# <a name="send-custom-notifications-in-intune"></a>Enviar notificações personalizadas no Intune  

Use o Microsoft Intune para enviar notificações personalizadas aos usuários de dispositivos iOS/iPadOS e Android gerenciados. Essas mensagens são exibidas como notificações por push padrão dos aplicativos Portal da Empresa e Microsoft Intune no dispositivo de um usuário, assim como são exibidas as notificações de outros aplicativos no dispositivo. As notificações personalizadas do Intune não são compatíveis com dispositivos macOS e Windows.   

As mensagens de notificação personalizadas incluem um título curto e um corpo de mensagem com 500 caracteres ou menos. Essas mensagens podem ser personalizadas para qualquer finalidade de comunicação geral.

### <a name="what-the-notification-looks-like-on-an-iosipados-device"></a>Como é a notificação em um dispositivo iOS/iPadOS

Se o aplicativo Portal da Empresa estiver aberto em um dispositivo iOS/iPadOS, a notificação será parecida com a captura de tela a seguir:

> [!div class="mx-imgBorder"]
> ![Notificação de Teste do Portal da Empresa no iOS/iPadOS](./media/custom-notifications/105046-1.png)

Se o dispositivo estiver bloqueado, a notificação se parecerá com a captura de tela a seguir:

> [!div class="mx-imgBorder"]
> ![Notificação de Teste em Dispositivo iOS/iPadOS Bloqueado](./media/custom-notifications/105046-2.png)

### <a name="what-the-notification-looks-like-on-an-android-device"></a>Como é a notificação em um dispositivo Android

Se o aplicativo Portal da Empresa estiver aberto em um dispositivo Android, a notificação se parecerá com a captura de tela a seguir:

> [!div class="mx-imgBorder"]
> ![Notificação de Teste no Android](./media/custom-notifications/105046-3.png)

## <a name="common-scenarios-for-sending-custom-notifications"></a>Cenários comuns para enviar notificações personalizadas  

- Notifique todos os funcionários de uma alteração no agendamento, como a criação de fechamentos devido ao clima severo.
- Envie uma notificação ao usuário de um único dispositivo para comunicar uma solicitação urgente, como reiniciar o dispositivo para concluir a instalação de uma atualização.

## <a name="considerations-for-using-custom-notifications"></a>Considerações sobre o uso de notificações personalizadas

**Configuração do dispositivo**

- Os dispositivos ter os aplicativos Portal da Empresa ou Microsoft Intune instalados antes que os usuários possam receber notificações personalizadas. Também precisam ter permissões configuradas para permitir que os aplicativos Portal da Empresa ou Microsoft Intune enviem notificações por push. Se necessário, os aplicativos Portal da Empresa e Microsoft Intune podem solicitar que os usuários permitam notificações.
- No Android, o Google Play Services é uma dependência necessária.
- O dispositivo deve ser inscrito como MDM.

**Permissões**:

- Para enviar notificações para grupos, sua conta deve ter a seguinte permissão RBAC no Intune: *Organização* > **Atualizar**.
- Para enviar notificações para um dispositivo, sua conta deve ter a seguinte permissão RBAC no Intune: *Tarefas remotas* > **Enviar notificações personalizadas**.

**Como criar notificações**:
 
- Para criar uma mensagem, use uma conta que seja atribuída a uma função do Intune que inclua a permissão correta, conforme descrito na seção *Permissões* anterior. Para atribuir permissões a um usuário, confira [Atribuições de função](../fundamentals/role-based-access-control.md#role-assignments).
- As notificações personalizadas são limitadas a títulos de 50 caracteres e a mensagens de 500 caracteres.  
- O Intune não salva o texto de notificações personalizadas enviadas anteriormente. Para reenviar uma mensagem, você precisa recriar essa mensagem.  
- Você só pode enviar até 25 mensagens para grupos por hora. Essa restrição está no nível do locatário. Essa limitação não se aplica ao envio de notificações para dispositivos individuais.
- Você só pode enviar até 25 mensagens para grupos por hora. Essa restrição está no nível do locatário. Essa limitação não se aplica ao envio de notificações para indivíduos.
- Ao enviar mensagens para dispositivos individuais, você pode enviar apenas 10 mensagens por hora para o mesmo dispositivo.
- Você pode enviar notificações para usuários em grupos. Ao enviar notificações para grupos, cada notificação pode ser direcionada a até 25 grupos diretamente. Os grupos aninhados não são contados nesse total. Ao enviar uma notificação para um grupo, as mensagens são direcionadas apenas aos usuários no grupo e são enviadas para cada dispositivo iOS ou Android que o usuário registrou. Ao direcionar a notificação, os dispositivos no grupo serão ignorados.
- Você pode enviar notificações para um único dispositivo. Em vez de usar grupos, você seleciona um dispositivo e, em seguida, usa uma [ação remota de dispositivo](device-management.md#available-device-actions) para enviar a notificação personalizada.  

**Entrega**:

- O Intune envia mensagens aos usuários pelos aplicativos Portal da Empresa ou Microsoft Intune, que criam a notificação por push. Os usuários não precisam estar conectados ao aplicativo para que a notificação seja enviada por push no dispositivo, mas o dispositivo precisa ter sido registrado pelo usuário ao qual a notificação se destina.
- O Intune e os aplicativos Portal da Empresa e Microsoft Intune não podem garantir a entrega de uma notificação personalizada. As notificações personalizadas poderão ser exibidas após várias horas de atraso, se forem exibidas; portanto, não deverão ser usadas para mensagens urgentes.  
- As mensagens de notificação personalizadas do Intune são exibidas em dispositivos como notificações por push padrão. Se o aplicativo Portal da Empresa estiver aberto em um dispositivo iOS quando ele receber a notificação, a notificação será exibida no aplicativo em vez de como uma notificação por push do sistema.  
- As notificações personalizadas podem estar visíveis nas telas de bloqueio em dispositivos iOS/iPadOS e Android, dependendo das configurações do dispositivo.  
- Em dispositivos Android, outros aplicativos podem ter acesso aos dados nas notificações personalizadas. Não os use para comunicações confidenciais.  
- Os usuários de um dispositivo que recentemente teve o registro cancelado ou os usuários que foram removidos de um grupo ainda podem receber uma notificação personalizada que é enviada posteriormente a esse grupo.  Da mesma forma, se você adicionar um usuário a um grupo depois que uma notificação personalizada for enviada para o grupo, será possível que o usuário recém-adicionado receba essa mensagem de notificação enviada anteriormente.  

## <a name="send-a-custom-notification-to-groups"></a>Enviar uma notificação personalizada para grupos

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) com uma conta que tenha permissões para criar e enviar notificações e acesse **Administração de locatário** > **Notificações personalizadas**.  

2. Na guia Informações Básicas, especifique as informações a seguir e, em seguida, selecione **Avançar** para continuar.  
   - **Título** – especifique um título para essa notificação. Os títulos são limitados a 50 caracteres.  
   - **Corpo** – especifique a mensagem. As mensagens são limitadas a 500 caracteres.

   ![Criar uma notificação personalizada](./media/custom-notifications/custom-notifications.png)  

3. Na guia **Atribuições**, selecione os grupos aos quais deseja enviar essa notificação personalizada e, em seguida, selecione Avançar para continuar. Enviar uma notificação para um grupo a destinará apenas aos usuários desse grupo; a notificação vai para todos os dispositivos iOS e Android registrados por esse usuário.

4. Na guia **Examinar + Criar**, examine as informações e, quando estiver pronto para enviar a notificação, selecione **Criar**.  

O Intune processa as mensagens que você cria imediatamente. A única confirmação de que a mensagem foi enviada é a notificação do Intune que confirma que a notificação personalizada foi enviada.  

![Confirmação de uma notificação enviada](./media/custom-notifications/notification-sent.png)  

O Intune não acompanha as notificações personalizadas que você envia, e os dispositivos não registram em log o recebimento fora do centro de notificações do dispositivo. Se um usuário solicitar suporte dentro do Portal da Empresa ou do aplicativo do Intune, a notificação poderá estar contida em um log de diagnóstico temporário.

## <a name="send-a-custom-notification-to-a-single-device"></a>Enviar uma notificação personalizada para um único dispositivo

1. Entre no [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) com uma conta que tenha permissões para criar e enviar notificações e acesse **Dispositivos** > **Todos os dispositivos**.

2. Clique duas vezes no nome do dispositivo gerenciado para o qual você deseja enviar uma notificação para abrir a página *Visão geral* desse dispositivo.

3. Na página **Visão geral** do dispositivo, selecione a ação do dispositivo **Enviar uma Notificação Personalizada** para abrir o painel *Enviar uma Notificação Personalizada*. Se essa opção não estiver disponível, marque a opção **...** (reticências) no canto superior direito da página e escolha **Enviar Notificação Personalizada**.

4. No painel **Enviar Notificação Personalizada**, especifique os seguintes detalhes da mensagem:  

   - **Título** – especifique um título para essa notificação. Os títulos são limitados a 50 caracteres.  
   - **Corpo** – especifique a mensagem. As mensagens são limitadas a 500 caracteres.  

5. Selecione **Enviar** para enviar a notificação personalizada para o dispositivo. Ao contrário das notificações enviadas para grupos, você não configura uma atribuição nem revisa a mensagem antes de enviá-la.  

O Intune processa a mensagem imediatamente. A única confirmação de que a mensagem foi enviada é a notificação do Intune que você receberá no console, que exibe o texto da mensagem que você enviou.  

## <a name="receive-a-custom-notification"></a>Receber uma notificação personalizada

Em um dispositivo, os usuários veem mensagens de notificação personalizadas enviadas pelo Intune como uma notificação por push padrão dos aplicativos Portal da Empresa ou Microsoft Intune. Essas notificações são semelhantes às notificações por push que os usuários recebem de outros aplicativos no dispositivo.  

Em dispositivos iOS/iPadOS, se o aplicativo Portal da Empresa estiver aberto quando a notificação for recebida, a notificação será exibida no aplicativo em vez de ser uma notificação por push.  

A notificação permanecerá até que o usuário a descarte.  

## <a name="next-steps"></a>Próximas etapas

[Gerenciar dispositivos](device-management.md)
