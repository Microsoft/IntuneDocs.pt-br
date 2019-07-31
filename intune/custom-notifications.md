---
title: Enviar notificações personalizadas aos usuários com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Usar o Intune para criar e enviar notificações por push personalizadas para usuários de dispositivos iOS e Android
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f938afb738e75789194db0c74fee56deb1476dbc
ms.sourcegitcommit: c715c93bb242f4fe44bbdf2fd585909854ed72b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68660390"
---
# <a name="send-custom-notifications-in-intune"></a>Enviar notificações personalizadas no Intune  

Use o Microsoft Intune para enviar notificações personalizadas aos usuários de dispositivos iOS e Android gerenciados. Essas mensagens são exibidas como notificações por push padrão do aplicativo Portal da Empresa no dispositivo de um usuário, assim como as notificações de outros aplicativos no dispositivo são exibidas. Não há suporte para notificações personalizadas do Intune em dispositivos Windows.   

As mensagens de notificação personalizadas incluem um título curto e um corpo da mensagem de 500 caracteres ou menos. Essas mensagens podem ser personalizadas para qualquer finalidade de comunicação geral.

## <a name="common-scenarios-for-sending-custom-notifications"></a>Cenários comuns para enviar notificações personalizadas  

- Use notificações personalizadas para alertar usuários específicos sobre um novo aplicativo que está disponível no Portal da Empresa.  
- Notifique todos os funcionários de uma alteração no agendamento, como a criação de fechamentos devido ao clima severo.  

## <a name="considerations-for-using-custom-notifications"></a>Considerações sobre o uso de notificações personalizadas  

**Configuração do dispositivo**:  
- Os dispositivos precisam ter o aplicativo Portal da Empresa instalado antes que os usuários possam receber notificações personalizadas. Eles também precisam ter as permissões configuradas para permitir que o aplicativo Portal da Empresa envie notificações por push. O Portal da Empresa solicitará que os usuários permitam notificações.  
- No Android, o Google Play Services é uma dependência necessária.  

**Como criar notificações**:  
- Para criar uma mensagem, use uma conta que seja atribuída a uma função do Intune que inclua a permissão **Atualizar** para a **Organização**. Para atribuir permissões a um usuário, confira [Atribuições de função](role-based-access-control.md#role-assignments)  
- As notificações personalizadas são limitadas a títulos de 50 caracteres e a mensagens de 500 caracteres.  
- O Intune não salva as mensagens enviadas. Para reenviar uma mensagem, você precisa recriar essa mensagem.  
- Você só pode enviar até 25 mensagens por hora. Essa restrição está no nível do locatário.  
- Cada notificação pode ser direcionada a até 25 grupos diretamente. Os grupos aninhados não são contados nesse total.  
- Os grupos podem incluir usuários ou dispositivos, mas as mensagens são enviadas somente aos usuários e para cada dispositivo iOS ou Android registrado pelo usuário.  

**Entrega**:  
- O Intune tenta realizar a entrega em até uma hora após o envio de uma notificação.  
- O Intune envia mensagens para o aplicativo Portal da Empresa dos usuários, que, em seguida, cria a notificação por push. Os usuários não precisam estar conectados ao aplicativo para que a notificação seja enviada por push no dispositivo.  
- O Intune e o aplicativo Portal da Empresa não podem garantir a entrega de uma notificação personalizada. As notificações personalizadas poderão ser exibidas após várias horas de atraso, se forem exibidas; portanto, não deverão ser usadas para mensagens urgentes.  
- As mensagens de notificação personalizadas do Intune são exibidas em dispositivos como notificações por push padrão. Se o aplicativo Portal da Empresa estiver aberto em um dispositivo iOS quando ele receber a notificação, a notificação será exibida no aplicativo em vez de ser uma notificação por push.  
- As notificações personalizadas podem estar visíveis nas telas de bloqueio em dispositivos iOS e Android, dependendo das configurações do dispositivo.  
- Em dispositivos Android, outros aplicativos podem ter acesso aos dados nas notificações personalizadas. Não os use para comunicações confidenciais.  
- Os usuários de um dispositivo que recentemente teve o registro cancelado ou os usuários que foram removidos de um grupo ainda podem receber uma notificação personalizada que é enviada posteriormente a esse grupo.  Da mesma forma, se você adicionar um usuário a um grupo depois que uma notificação personalizada for enviada para o grupo, será possível que o usuário recém-adicionado receba essa mensagem de notificação enviada anteriormente.  

## <a name="send-a-custom-notification"></a>Enviar uma notificação personalizada  

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) com uma conta que tenha permissões para criar e enviar notificações e acesse **Dispositivos** > **Enviar notificações personalizadas**.  

2. Na guia Informações Básicas, especifique as informações a seguir e, em seguida, selecione **Avançar** para continuar.  
   - **Título** – especifique um título para essa notificação. Os títulos são limitados a 50 caracteres.  
   - **Corpo** – especifique a mensagem. As mensagens são limitadas a 500 caracteres

   ![Criar uma notificação personalizada](./media/custom-notifications/custom-notifications.png)  

3. Na guia **Atribuições**, selecione os grupos aos quais deseja enviar essa notificação personalizada e, em seguida, selecione Avançar para continuar.  

4. Na guia **Examinar + Criar**, examine as informações e, quando estiver pronto para enviar a notificação, selecione **Criar**.  

O Intune processa as mensagens que você cria imediatamente. A única confirmação de que a mensagem foi enviada é a notificação do Intune que confirma que a notificação personalizada foi enviada.  

![Confirmação de uma notificação enviada](./media/custom-notifications/notification-sent.png)  

O Intune não acompanha as notificações personalizadas que você envia, e os dispositivos não registram em log o recebimento fora do centro de notificações do dispositivo.  

## <a name="receive-a-custom-notification"></a>Receber uma notificação personalizada  

Em um dispositivo, os usuários veem mensagens de notificação personalizadas que são enviadas pelo Intune como uma notificação por push padrão do aplicativo Portal da Empresa. Essas notificações são semelhantes às notificações por push que os usuários recebem de outros aplicativos no dispositivo.  

Em dispositivos iOS, se o aplicativo Portal da Empresa estiver aberto quando a notificação for recebida, a notificação será exibida no aplicativo em vez de ser uma notificação por push.  

A notificação permanecerá até que o usuário a descarte.  

## <a name="next-steps"></a>Próximas etapas  
[Gerenciar dispositivos](device-management.md)
