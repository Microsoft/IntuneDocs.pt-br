---
title: "Regras de acesso do Exchange para dispositivos móveis"
description: "Regras de acesso do Exchange ActiveSync para permitir ou bloquear conexões de dispositivo com o EAS"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a57b1f51fabfdc8896ecbb5bfbe6422f40672b18
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="exchange-access-rules-for-mobile-devices"></a>Regras de acesso do Exchange para dispositivos móveis

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As regras de acesso do Exchange para dispositivos móveis determinam o nível de acesso que esses dispositivos têm ao Exchange ActiveSync. Essas configurações afetam todos os dispositivos móveis, incluindo aqueles não registrados no Microsoft Intune. Você pode começar definindo uma **Regra Padrão** que se aplica a qualquer dispositivo móvel que não tenha uma regra personalizada aplicada a ele.

A tabela a seguir contém os níveis de acesso gerenciados pelo Exchange ActiveSync:

|Nível de acesso|Descrição|
|----------------|---------------|
|**Permitir que os dispositivos acessem o Exchange**|No estado *permitir acesso*, um dispositivo móvel pode sincronizar por meio do Exchange ActiveSync e se conectar ao servidor Exchange para recuperar email e gerenciar calendário, contatos, tarefas e observações. Isso continuará desde que o dispositivo esteja em conformidade com a política de caixa de correio do Exchange ActiveSync configurada no Exchange, a menos que o usuário ou o dispositivo móvel específico tenha sido bloqueado pelo administrador do Exchange.|
|**Bloquear o acesso dos dispositivos ao Exchange**|No estado *bloquear acesso*, os dispositivos móveis são bloqueados e não tem permissão para se conectar ao servidor do Exchange. Os dispositivos recebem um erro HTTP 403 Proibido. O usuário recebe uma mensagem de email do servidor Exchange informando que o dispositivo móvel foi impedido de acessar sua caixa de correio. Esta mensagem não pode estar no dispositivo móvel bloqueado. Usando a tarefa **Definir Notificação do Usuário**você pode adicionar texto personalizado a essa mensagem a fim de fornecer instruções aos usuários cujos dispositivos estão bloqueados. |
|**Colocar os dispositivos em quarentena para permiti-los ou bloqueá-los mais tarde**|Quando um dispositivo móvel está em quarentena, ele tem permissão para se conectar ao servidor do Exchange. No entanto, ele recebe apenas acesso limitado aos dados. O usuário pode adicionar conteúdo às suas próprias pastas Calendário, Contatos, Tarefas e Anotações, mas o servidor não permite que o dispositivo recupere conteúdo da caixa de correio do usuário. O usuário recebe uma única mensagem de email informando que o dispositivo móvel foi colocado em quarentena. Essa mensagem é enviada ao dispositivo e à caixa de correio do usuário. Usando a tarefa **Definir Notificação do Usuário**, você pode adicionar texto personalizado a essa mensagem, para fornecer instruções para os usuários cujos dispositivos estão em quarentena.|

Uma estratégia de acesso é uma combinação de uma **Regra Padrão** e **Exceções de Plataforma** que se aplicam a todos os dispositivos móveis conectados ao Exchange. A tabela a seguir lista alguns exemplos de estratégia de acesso.

|Estratégia de acesso|Descrição|
|-------------------|---------------|
|Lista de permissões|Você pode usar uma *lista de permissões* para conceder acesso a uma lista de dispositivos conhecidos e restringir o acesso a todos os outros dispositivos. Para fazer isso, você deve criar regras personalizadas para as plataformas de dispositivos com permissão para acessar as caixas de correio dos usuários. Assim que criar essa regra, você deverá definir a regra de acesso padrão, para bloquear ou colocar em quarentena todos os outros dispositivos. Para adicionar um novo dispositivo à lista de permissões, crie uma nova regra personalizada.|
|Lista de bloqueios|Você pode usar uma *lista de contatos bloqueados* para conceder acesso a todos os dispositivos por padrão, mas bloquear o acesso de um conjunto de dispositivos que você não deseja que acessem a organização. Crie uma lista de contatos bloqueados pela criação de regras personalizadas para bloquear as plataformas de dispositivos que você não deseja sincronizar com caixas de correio da organização. Recomendamos a configuração da regra padrão para permitir acesso a todos os dispositivos que não estejam explicitamente bloqueados pelas regras existentes. Para adicionar um novo dispositivo ou conjunto de dispositivos à lista de bloqueios, crie uma nova regra personalizada.|
|Listas mistas de permissões e bloqueios|Além de criar listas de permissões e bloqueios, você pode colocar em quarentena novos dispositivos móveis à medida que eles são inseridos na organização, enquanto são avaliados. Por exemplo, se você tem uma lista de bloqueio para dispositivos móveis que não são permitidos dentro de sua organização, e uma lista de permissões para os dispositivos móveis que são permitidos dentro da organização, você pode definir a regra padrão para a quarentena. Todos os outros dispositivos são colocados automaticamente em quarentena. Isso permite que você descubra novos dispositivos à medida que são introduzidos na organização e decida se quer adicioná-los à lista de permissões ou de bloqueio.|
O procedimento a seguir descreve como criar uma regra personalizada.

## <a name="create-a-default-access-rule"></a>Criar uma regra de acesso padrão

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** &gt; **Exchange ActiveSync**.

2.  Na lista **Regra Padrão**, selecione a regra de acesso que você quer aplicar a todos os dispositivos móveis não gerenciados por uma regra ou isenção pessoal. Selecione **Salvar**.

O procedimento a seguir descreve como criar uma regra personalizada:

## <a name="create-a-custom-access-rule"></a>Criar uma regra de acesso personalizada

1. No [console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** &gt; **Exchange ActiveSync**.

2.  Na lista **Exceções de Plataforma**, escolha **Adicionar Regra** e crie uma regra personalizada. Selecione **Salvar**.
