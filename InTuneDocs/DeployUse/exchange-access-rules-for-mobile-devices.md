---
title: "Regras de acesso do Exchange para dispositivos móveis | Microsoft Intune"
description: "Regras de acesso do Exchange ActiveSync para permitir ou bloquear conexões de dispositivo com o EAS"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c49e19e8c478af252d7b59c380d5500a57b71db5
ms.openlocfilehash: 7714a338d02afedde2ac090964e4d18d4410a80e


---

# Regras de acesso do Exchange para dispositivos móveis
As regras de acesso do Exchange para dispositivos móveis determinam o nível de acesso que esses dispositivos têm ao Exchange ActiveSync. Essas configurações afetam todos os dispositivos móveis, incluindo aqueles não registrados no Microsoft Intune. Você pode começar definindo uma **Regra Padrão** que se aplicará a qualquer dispositivo móvel que não tenha uma regra personalizada aplicada a ele. A tabela a seguir contém os níveis de acesso gerenciados pelo Exchange ActiveSync:

|Nível de acesso|Descrição|
|----------------|---------------|
|**Permitir que os dispositivos acessem o Exchange**|No estado *permitir acesso*, um dispositivo móvel pode sincronizar por meio do Exchange ActiveSync e se conectar ao servidor Exchange para recuperar email e gerenciar calendário, contatos, tarefas e observações. Isso continuará desde que o dispositivo esteja em conformidade com a política de caixa de correio do Exchange ActiveSync configurada no Exchange, a menos que o usuário ou o dispositivo móvel específico tenha sido bloqueado pelo administrador do Exchange.|
|**Bloquear o acesso dos dispositivos móveis ao Exchange**|No estado *bloquear acesso*, os dispositivos móveis são bloqueados e não terão permissão para se conectar ao servidor do Exchange. Os dispositivos receberão um erro HTTP 403 Proibido. O usuário receberá uma mensagem de email do servidor Exchange informando que o dispositivo móvel foi impedido de acessar sua caixa de correio. Esta mensagem não pode estar no dispositivo móvel bloqueado. Você pode adicionar texto personalizado a essa mensagem, para fornecer instruções aos usuários cujos dispositivos estão bloqueados com a tarefa **Definir Notificação do Usuário**.|
|**Colocar os dispositivos móveis em quarentena para que você possa permiti-los ou bloqueá-los mais tarde**|Quando um dispositivo móvel está em quarentena, ele tem permissão para se conectar ao servidor do Exchange. No entanto, ele recebe apenas acesso limitado aos dados. O usuário pode adicionar conteúdo às suas próprias pastas Calendário, Contatos, Tarefas e Anotações, mas o servidor não permitirá que o dispositivo recupere conteúdo da caixa de correio do usuário. O usuário receberá uma única mensagem de email informando que o dispositivo móvel foi colocado em quarentena. Essa mensagem é recebida no dispositivo e na caixa de correio do usuário. Você pode adicionar texto personalizado a essa mensagem, para fornecer instruções para os usuários cujos dispositivos estão em quarentena usando a tarefa **Definir Notificação do Usuário** .|

Uma estratégia de acesso é uma combinação de uma **Regra Padrão** e **Exceções de Plataforma** que se aplicam a todos os dispositivos móveis conectados ao Exchange. A tabela a seguir lista algumas estratégias de acesso como exemplo.

|Estratégia de acesso|Descrição|
|-------------------|---------------|
|Lista de permissões|Você pode usar uma *lista de permissões* para conceder acesso a uma lista de dispositivos conhecidos e restringir o acesso a todo o resto. Para fazer isso, você deve criar regras personalizadas para as plataformas de dispositivos com permissão para acessar as caixas de correio dos usuários. Assim que criar essa regra, você deverá definir a regra de acesso padrão, para bloquear ou colocar em quarentena todos os outros dispositivos. Para adicionar um novo dispositivo à lista de permissões, crie uma nova regra personalizada|
|Lista de bloqueios|Você pode usar uma *lista de contatos bloqueados* para conceder acesso a todos os dispositivos por padrão, mas bloquear o acesso de um conjunto de dispositivos que você não deseja que acessem a organização. Crie uma lista de contatos bloqueados pela criação de regras personalizadas para bloquear as plataformas de dispositivos que você não deseja sincronizar com caixas de correio da organização. A regra padrão deve ser configurada para permitir acesso a todos os dispositivos que não estejam explicitamente bloqueados pelas regras existentes. Para adicionar um novo dispositivo ou conjunto de dispositivos à lista de bloqueios, crie uma nova regra personalizada.|
|Listas mistas de permissões e bloqueios|Além de criar listas de permissões e bloqueios, você pode colocar em quarentena novos dispositivos móveis à medida que eles são inseridos na organização, enquanto são avaliados. Por exemplo, se você tem uma lista de bloqueio para dispositivos móveis que não são permitidos dentro de sua organização, e uma lista de permissões para os dispositivos móveis que são permitidos dentro da organização, você pode definir a regra padrão para a quarentena. Todos os outros dispositivos serão automaticamente colocados em quarentena. Isso permite que você descubra novos dispositivos à medida que são introduzidos na organização e decida se quer adicioná-los à lista de permissões ou à lista de contatos bloqueados.|
O procedimento a seguir descreve como criar uma regra personalizada.

## Criar uma regra de acesso padrão

1.  No [console de administração do Microsoft Intune](http://manage.microsoft.com) &gt; **Política** &gt; **Exchange ActiveSync**.

2.  Na lista **Regra Padrão** , selecione a regra de acesso que deseja aplicar a todos os dispositivos móveis não gerenciados por uma regra ou isenção pessoal. Selecione **Salvar**.

O procedimento a seguir descreve como criar uma regra personalizada.

## Criar uma regra de acesso personalizada

1. No [console de administração do Microsoft Intune](http://manage.microsoft.com) &gt; **Política** &gt; **Exchange ActiveSync**.

2.  Na lista **Exceções de Plataforma**, escolha **Adicionar Regra** e crie uma regra personalizada. Selecione **Salvar**.



<!--HONumber=Aug16_HO1-->


