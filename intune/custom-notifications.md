---
title: Enviar notificações personalizadas aos usuários com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Usar o Intune para criar e enviar notificações por push personalizadas para usuários de dispositivos iOS e Android
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/10/2019
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
ms.openlocfilehash: bffbc96e945d522453c299717a6eb413354a4af4
ms.sourcegitcommit: 98f2597eec28c6096985d5a1acae72430c2afb1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70878043"
---
# <a name="send-custom-notifications-in-intune"></a>Enviar notificações personalizadas no Intune  

Use o Microsoft Intune para enviar notificações personalizadas aos usuários de dispositivos iOS e Android gerenciados. Essas mensagens são exibidas como notificações por push padrão dos aplicativos Portal da Empresa e Microsoft Intune no dispositivo de um usuário, assim como são exibidas as notificações de outros aplicativos no dispositivo. Não há suporte para notificações personalizadas do Intune em dispositivos Windows.   

As mensagens de notificação personalizadas incluem um título curto e um corpo da mensagem de 500 caracteres ou menos. Essas mensagens podem ser personalizadas para qualquer finalidade de comunicação geral.

## <a name="common-scenarios-for-sending-custom-notifications"></a>Cenários comuns para enviar notificações personalizadas  

- Use notificações personalizadas para alertar usuários específicos de que um novo aplicativo está disponível no Portal da Empresa.  
- Notifique todos os funcionários de uma alteração no agendamento, como a criação de fechamentos devido ao clima severo.  

## <a name="considerations-for-using-custom-notifications"></a>Considerações sobre o uso de notificações personalizadas  

**Configuração do dispositivo**:  
- Os dispositivos ter os aplicativos Portal da Empresa ou Microsoft Intune instalados antes que os usuários possam receber notificações personalizadas. Também precisam ter permissões configuradas para permitir que os aplicativos Portal da Empresa ou Microsoft Intune enviem notificações por push. Se necessário, os aplicativos Portal da Empresa e Microsoft Intune podem solicitar que os usuários permitam notificações.  
- No Android, o Google Play Services é uma dependência necessária.  
- O dispositivo deve ser inscrito como MDM.

**Como criar notificações**:  
- Para criar uma mensagem, use uma conta que seja atribuída a uma função do Intune que inclua a permissão **Atualizar** para a **Organização**. Para atribuir permissões a um usuário, confira [Atribuições de função](role-based-access-control.md#role-assignments)  
- As notificações personalizadas são limitadas a títulos de 50 caracteres e a mensagens de 500 caracteres.  
- O Intune não salva as mensagens enviadas. Para reenviar uma mensagem, você precisa recriar essa mensagem.  
- Você só pode enviar até 25 mensagens por hora. Essa restrição está no nível do locatário.  
- Cada notificação pode ser direcionada a até 25 grupos diretamente. Os grupos aninhados não são contados nesse total.  
- Os grupos podem incluir usuários ou dispositivos, mas as mensagens são enviadas somente aos usuários e para cada dispositivo iOS ou Android registrado pelo usuário.  

**Entrega**:  
- O Intune envia mensagens aos usuários pelos aplicativos Portal da Empresa ou Microsoft Intune, que criam a notificação por push. Os usuários não precisam estar conectados ao aplicativo para que a notificação seja enviada por push no dispositivo.  
- O Intune e os aplicativos Portal da Empresa e Microsoft Intune não podem garantir a entrega de uma notificação personalizada. As notificações personalizadas poderão ser exibidas após várias horas de atraso, se forem exibidas; portanto, não deverão ser usadas para mensagens urgentes.  
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

Em um dispositivo, os usuários veem mensagens de notificação personalizadas enviadas pelo Intune como uma notificação por push padrão dos aplicativos Portal da Empresa ou Microsoft Intune. Essas notificações são semelhantes às notificações por push que os usuários recebem de outros aplicativos no dispositivo.  

Em dispositivos iOS, se o aplicativo Portal da Empresa estiver aberto quando a notificação for recebida, a notificação será exibida no aplicativo em vez de ser uma notificação por push.  

A notificação permanecerá até que o usuário a descarte.  

## <a name="next-steps"></a>Próximas etapas  
[Gerenciar dispositivos](device-management.md)
