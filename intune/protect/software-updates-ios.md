---
title: Configurar políticas de atualização de software do iOS no Microsoft Intune – Azure | Microsoft Docs
description: No Microsoft Intune, crie ou adicione uma política de configuração para restringir quando as atualizações de software são instaladas automaticamente em dispositivos iOS gerenciados ou supervisionados pelo Intune. Você pode escolher a data e a hora em que as atualizações não são instaladas. Você também pode atribuir essa política a grupos, usuários ou dispositivos e verificar se há falhas de instalação.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 54e6cc0b3df95c74abf4b4ef1b827f8e121e3645
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726655"
---
# <a name="add-ios-software-update-policies-in-intune"></a>Adicionar políticas de atualização de software do iOS no Intune

As políticas de atualização de software permitem que você force os dispositivos iOS supervisionados a instalar automaticamente a última atualização de sistema operacional disponível. Ao configurar uma política, você pode adicionar os dias e as horas em que não deseja que os dispositivos instalem uma atualização.

Esse recurso aplica-se a:

- iOS 10.3 e posterior (supervisionado)

O dispositivo faz check-in no Intune aproximadamente a cada 8 horas. Se uma atualização está disponível e não está agendada para um horário restrito, o dispositivo baixa e instala a última atualização do sistema operacional. Não há nenhuma interação do usuário necessária para atualizar o dispositivo. A política não impede que um usuário atualize o sistema operacional manualmente.

## <a name="configure-the-policy"></a>Configurar a política

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Atualizações de software** > **Atualizar as políticas do iOS** > **Criar**.
3. Insira as seguintes configurações:

    - **Nome**: insira um nome para sua política de atualizações de software. Por exemplo, insira `iOS restricted update times`.
    - **Descrição**: insira uma descrição para sua política. Essa configuração é opcional, mas recomendada.

4. Selecione **Configurações > Configurar**. Insira as seguintes configurações:

    - **Selecionar horários para impedir instalações de atualizações**: especifique um período restrito quando as atualizações não são instaladas à força.
      - Não há suporte para bloqueios durante a noite e eles podem não funcionar. Por exemplo, não configure uma política com uma *Hora de início* sendo 20h e uma *Hora de término* sendo 6h.
      - Uma política que começa à meia-noite e termina à meia-noite é avaliada como 0 hora e não 24 horas, o que resulta em nenhuma restrição.

      Ao definir o período restrito, insira os seguintes detalhes:

      - **Dias**: escolha os dias da semana quando as atualizações não são instaladas. Por exemplo, marque segunda-feira, quarta-feira e sexta-feira para impedir a instalação das atualizações nesses dias.
      - **Fuso horário**: escolha um fuso horário.
      - **Hora de início**: escolha a hora de início do período restrito. Por exemplo, insira 5h para que as atualizações não sejam instaladas a partir de 5h.
      - **Hora de término**: escolha a hora de término do período restrito. Por exemplo, insira 1h para que as atualizações possam ser instaladas a partir de 1h.

    - **Atrasar a visibilidade de atualizações de software para usuários finais sem alterações em atualizações agendadas na política de atualização de software (dias)** : 

      **Se você quer atrasar a visibilidade de atualizações de software por um período específico em seus dispositivos iOS supervisionados, defina essas configurações em [Restrições do Dispositivo](../configuration/device-restrictions-ios.md#general). As políticas de atualização de software substituem todas as restrições do dispositivo. Se você tiver ambas definidas, a política de atualização de software sempre terá prioridade.

      > [!IMPORTANT]  
      > Uma política que tem uma *Hora de início* e uma *Hora de término* definidas como meia-noite é avaliada como 0 hora e não 24 horas. Isso resulta em nenhuma restrição.  

5. Selecione **OK** > **Criar** para salvar suas alterações e criar a política.

O perfil é criado e exibido na lista de políticas.

Para obter diretrizes da equipe de suporte do Intune, confira [Atrasar a visibilidade de atualizações de software no Intune para dispositivos supervisionados](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753).

> [!NOTE]
> O MDM da Apple não permite que você force um dispositivo a instalar atualizações em determinada hora ou data.

## <a name="change-the-restricted-times-for-the-policy"></a>Alterar as horas restritas da política

1. Em **Atualizações de software**, selecione **Políticas de atualização do iOS**.
2. Escolha uma política existente > **Propriedades**.
3. Atualize o horário restrito:

    1. Escolher os dias da semana
    2. Escolha o fuso horário ao qual essa política é aplicada
    3. Inserir a hora de início e de término para as horas não permitidas

    > [!NOTE]
    > Se a **Hora de início** e a **Hora de término** forem definidas como meia-noite, então o Intune não verificará se há restrições sobre quando instalar as atualizações. Isso significa que as configurações que você tem para **Selecionar horários para impedir instalações de atualizações** são ignoradas e as atualizações podem ser instaladas a qualquer momento.  

## <a name="assign-the-policy-to-users"></a>Atribuir a política a usuários

As políticas existentes são atribuídas a grupos, usuários ou dispositivos. Quando atribuída, a política é aplicada.

1. Em **Atualizações de software**, selecione **Políticas de atualização do iOS**.
2. Escolha uma política existente > **Atribuições**.
3. Selecione os grupos, os usuários ou os dispositivos do Azure Active Directory a serem incluídos ou excluídos dessa política.
4. Escolha **Salvar** para implantar a política nos grupos.

Os dispositivos usados pelos usuários afetados pela política são avaliados quanto à conformidade de atualizações. Essa política também é compatível com dispositivos sem usuários.

## <a name="monitor-device-installation-failures"></a>Monitorar falhas de instalação do dispositivo
<!-- 1352223 -->
**Atualizações de software** > **Falhas de instalação para dispositivos iOS** mostra uma lista de dispositivos iOS supervisionados que foram direcionados por uma política de atualização e que tentaram ser atualizados, mas que não conseguiram. Para cada dispositivo, você pode exibir o status do motivo pelo qual o dispositivo não foi atualizado automaticamente. Os dispositivos íntegros e atualizados não são mostrados na lista. Os dispositivos "atualizados" incluem a última atualização para a qual o dispositivo em si dá suporte.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](../configuration/device-profile-assign.md) e [monitorar seu status](../configuration/device-profile-monitor.md).
