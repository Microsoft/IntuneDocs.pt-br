---
title: "Regras de acesso do Exchange para dispositivos móveis gerenciados pelo Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: ef0b9901e340aec8b2b516f0180133e37833bf37


---

# Regras de acesso do Exchange para dispositivos móveis
As regras de acesso do Exchange para dispositivos móveis determinam o nível de acesso ao Exchange concedido a esses dispositivos. Essas configurações afetam todos os dispositivos móveis, incluindo aqueles não registrados no Microsoft Intune. Você pode começar definindo uma **Regra Padrão** que se aplicará a qualquer dispositivo móvel que não tenha uma regra personalizada aplicada a ele. A tabela a seguir contém os níveis de acesso gerenciados pelo Exchange ActiveSync:

|Nível de acesso|Descrição|
|----------------|---------------|
|**Permitir que todos os dispositivos móveis acessem o Exchange, a menos que uma regra personalizada diga o contrário**|No estado *permitir acesso*, um dispositivo móvel pode sincronizar por meio do Exchange ActiveSync e se conectar ao servidor Exchange para recuperar email e gerenciar calendário, contatos, tarefas e observações. Isso continuará desde que o dispositivo esteja em conformidade com a **Política de segurança do dispositivo móvel Intune** configurada, a menos que o usuário ou o dispositivo móvel específico tenha sido bloqueado pelo administrador do Exchange.|
|**Impedir que todos os dispositivos móveis acessem o Exchange, a menos que uma regra personalizada diga o contrário**|No estado *bloquear acesso*, os dispositivos móveis são bloqueados e não terão permissão para se conectar ao servidor do Exchange. Os dispositivos receberão um erro HTTP 403 Proibido. O usuário receberá uma mensagem de email do servidor Exchange informando que o dispositivo móvel foi impedido de acessar sua caixa de correio. Esta mensagem não pode estar no dispositivo móvel bloqueado. Você pode adicionar texto personalizado a essa mensagem, para fornecer instruções aos usuários cujos dispositivos estão bloqueados com a tarefa **Definir Notificação do Usuário**.|
|**Colocar em quarentena todos os dispositivos móveis para que eu possa decidir depois para cada dispositivo móvel individual, a menos que uma regra personalizada diga o contrário**|Quando um dispositivo móvel está em quarentena, ele tem permissão para se conectar ao servidor do Exchange. No entanto, ele recebe apenas acesso limitado aos dados. O usuário pode adicionar conteúdo às suas próprias pastas Calendário, Contatos, Tarefas e Anotações, mas o servidor não permitirá que o dispositivo recupere conteúdo da caixa de correio do usuário. O usuário receberá uma única mensagem de email informando que o dispositivo móvel foi colocado em quarentena. Essa mensagem é recebida no dispositivo e na caixa de correio do usuário. Você pode adicionar texto personalizado a essa mensagem, para fornecer instruções para os usuários cujos dispositivos estão em quarentena usando a tarefa **Definir Notificação do Usuário** .|

Uma estratégia de acesso é uma combinação de uma **Regra Padrão** e **Regras Personalizadas** que se aplicam a todos os dispositivos móveis conectados ao Exchange. A tabela a seguir lista algumas estratégias de acesso como exemplo.

|Estratégia de acesso|Descrição|
|-------------------|---------------|
|Lista de permissões|Você pode usar uma *lista de permissões* para conceder acesso a uma lista de dispositivos conhecidos e restringir o acesso a todo o resto. Para fazer isso, você deve criar regras personalizadas para que os dispositivos específicos que você deseja tenham permissão para acessar as caixas de correio dos usuários. Assim que criar essa regra, você deverá definir a regra de acesso padrão, para bloquear ou colocar em quarentena todos os outros dispositivos. Para adicionar um novo dispositivo à lista de permissões, crie uma nova regra personalizada|
|Lista de bloqueios|Você pode usar uma *lista de contatos bloqueados* para conceder acesso a todos os dispositivos por padrão, mas bloquear o acesso de um conjunto de dispositivos que você não deseja que acessem a organização. Crie uma lista de contatos bloqueados pela criação de regras personalizadas para bloquear os dispositivos que você não deseja sincronizar com caixas de correio da organização. A regra padrão deve ser configurada para permitir acesso a todos os dispositivos que não estejam explicitamente bloqueados pelas regras existentes. Para adicionar um novo dispositivo ou conjunto de dispositivos à lista de bloqueios, crie uma nova regra personalizada.|
|Listas mistas de permissões e bloqueios|Além de criar listas de permissões e bloqueios, você pode colocar em quarentena novos dispositivos móveis à medida que eles são inseridos na organização, enquanto são avaliados. Por exemplo, se você tem uma lista de bloqueio para dispositivos móveis que não são permitidos dentro de sua organização, e uma lista de permissões para os dispositivos móveis que são permitidos dentro da organização, você pode definir a regra padrão para a quarentena. Todos os outros dispositivos serão automaticamente colocados em quarentena. Isso permite que você descubra novos dispositivos à medida que são introduzidos na organização e decida se quer adicioná-los à lista de permissões ou à lista de contatos bloqueados.|
O procedimento a seguir descreve como criar uma regra personalizada.

## Criar uma regra de acesso padrão

1.  No [console de administração do Microsoft Intune](http://manage.microsoft.com) &gt; **Política** &gt; **Acesso do Exchange a Dispositivos Móveis**.

2.  Na lista **Regra Padrão** , selecione a regra de acesso que deseja aplicar a todos os dispositivos móveis não gerenciados por uma regra ou isenção pessoal. Selecione **Salvar**.

O procedimento a seguir descreve como criar uma regra personalizada.

## Criar uma regra de acesso personalizada

1. No [console de administração do Microsoft Intune](http://manage.microsoft.com) &gt; **Política** &gt; **Acesso do Exchange a Dispositivos Móveis**.

2.  Na lista **Regras Personalizadas**, clique em **Adicionar Regra** e crie uma regra personalizada. Selecione **Salvar**.



<!--HONumber=Jun16_HO4-->


