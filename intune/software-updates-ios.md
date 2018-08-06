---
title: Configurar políticas de atualização de software do iOS no Microsoft Intune – Azure | Microsoft Docs
description: No Microsoft Intune, crie ou adicione uma política de configuração para restringir quando as atualizações de software são instaladas automaticamente em dispositivos iOS gerenciados ou supervisionados pelo Intune. Você pode escolher a data e a hora em que as atualizações não são instaladas. Você também pode atribuir essa política a grupos, usuários ou dispositivos e verificar se há falhas de instalação.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.openlocfilehash: b9cc34b2fa45ae447a015f1b3105081041bd0afe
ms.sourcegitcommit: 0a2e737c5520c1a1dec5d732e5df52b5614b27e1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2018
ms.locfileid: "39268831"
---
# <a name="configure-ios-update-policies-in-intune"></a>Configurar políticas de atualização do iOS no Intune

As políticas de atualização de software permitem que você force os dispositivos iOS supervisionados a instalar automaticamente a última atualização de sistema operacional disponível. Esse recurso só está disponível para dispositivos supervisionados. Ao configurar uma política, você pode adicionar os dias e as horas em que não deseja que os dispositivos instalem uma atualização. 

O dispositivo faz check-in no Intune aproximadamente a cada 8 horas. Se uma atualização está disponível e não está agendada para um horário restrito, o dispositivo baixa e instala a última atualização do sistema operacional. Não há nenhuma interação do usuário necessária para atualizar o dispositivo. A política não impede que um usuário atualize o sistema operacional manualmente.

Esse recurso dá suporte aos dispositivos que executam o iOS 10.3 e posterior.

## <a name="configure-the-policy"></a>Configurar a política
1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Atualizações de software** > **Atualizar as políticas do iOS** > **Criar**.
4. Insira um nome e uma descrição para a política.
5. Selecione **Configurações**. 

    Insira os detalhes de quando os dispositivos iOS não são forçados a instalar as últimas atualizações. Essas configurações criam um período de tempo restrito. É possível configurar os dias da semana, o fuso horário, a hora de início e a hora de término.

6. Selecione **OK** para salvar suas alterações. Selecione **Criar** para criar a política.

O perfil é criado e exibido na lista de políticas. O MDM da Apple não permite que você force um dispositivo a instalar atualizações em determinada hora ou data. 

## <a name="change-the-restricted-times-for-the-policy"></a>Alterar as horas restritas da política

1. Em **Atualizações de software**, selecione **Políticas de atualização do iOS**.
2. Escolha uma política existente > **Propriedades**.
3. Atualize o horário restrito:

    1. Escolher os dias da semana
    2. Escolha o fuso horário ao qual essa política é aplicada
    3. Inserir a hora de início e de término para as horas não permitidas

    > [!NOTE]
    > Se a **Hora de início** e a **Hora de término** são definidas como 00h, a verificação de horário de manutenção é desativada.

## <a name="assign-the-policy-to-users"></a>Atribuir a política a usuários

As políticas existentes são atribuídas a grupos, usuários ou dispositivos. Quando atribuída, a política é aplicada.

1. Em **Atualizações de software**, selecione **Políticas de atualização do iOS**.
2. Escolha uma política existente > **Atribuições**. 
3. Selecione os grupos, os usuários ou os dispositivos do Azure Active Directory a serem incluídos ou excluídos dessa política.
4. Escolha **Salvar** para implantar a política nos grupos.

Os dispositivos usados pelos usuários afetados pela política são avaliados quanto à conformidade de atualizações. Essa política também é compatível com dispositivos sem usuários.

## <a name="monitor-device-installation-failures"></a>Monitorar falhas de instalação do dispositivo
<!-- 1352223 -->
**Atualizações de software** > **Falhas de instalação em dispositivos iOS** mostra uma lista de dispositivos iOS supervisionados direcionados por uma política de atualização, para os quais houve a tentativa de uma atualização e que não puderam ser atualizados. Para cada dispositivo, você pode exibir o status do motivo pelo qual o dispositivo não foi atualizado automaticamente. Os dispositivos íntegros e atualizados não são mostrados na lista. Os dispositivos "atualizados" incluem a última atualização para a qual o dispositivo em si dá suporte.

