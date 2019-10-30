---
title: Configurar políticas de atualização de software do iOS no Microsoft Intune – Azure | Microsoft Docs
description: No Microsoft Intune, crie ou adicione uma política de configuração para restringir quando as atualizações de software são instaladas automaticamente em dispositivos iOS. Você pode escolher a data e a hora em que as atualizações não são instaladas. Você também pode atribuir essa política a grupos, usuários ou dispositivos e verificar se há falhas de instalação.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: ada1f6e5292684803fbea40430cdd43d61796746
ms.sourcegitcommit: 1a5b185acd27954b10b6d59409d82eb80fd71284
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72681350"
---
# <a name="add-ios-software-update-policies-in-intune"></a>Adicionar políticas de atualização de software do iOS no Intune

As políticas de atualização de software permitem que você force os dispositivos iOS supervisionados a instalar automaticamente a última atualização de sistema operacional disponível. Ao configurar uma política, você pode adicionar os dias e as horas em que não deseja que os dispositivos instalem uma atualização.

Esse recurso aplica-se a:

- iOS 10.3 e posterior (supervisionado)

O dispositivo faz check-in no Intune aproximadamente a cada 8 horas. Se uma atualização está disponível, o dispositivo a baixa e a instala, exceto durante horários restritos. Não há nenhuma interação do usuário necessária para atualizar o dispositivo. A política não impede que um usuário atualize o sistema operacional manualmente.

## <a name="configure-the-policy"></a>Configurar a política

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Atualizações de software** > **Atualizar as políticas do iOS** > **Criar**.
3. Na guia **Conceitos Básicos**, especifique um nome para esta política e uma descrição (opcional) e, em seguida, selecione **Avançar**.

   ![Guia Conceitos Básicos](./media/software-updates-ios/basics-tab.png) 

4. Na guia **Atualizar configurações da política**, especifique um período restrito quando as atualizações não são instaladas à força.  
   - Não há suporte para bloqueios durante a noite e eles podem não funcionar. Por exemplo, não configure uma política com uma *Hora de início* sendo 20h e uma *Hora de término* sendo 6h.
   - Uma política que começa à meia-noite e termina à meia-noite é avaliada como 0 hora, e não 24 horas. Essa configuração resulta em nenhuma restrição.

   Ao definir o período restrito, insira os seguintes detalhes:

   - **Dias**: escolha os dias da semana quando as atualizações não são instaladas. Por exemplo, marque segunda-feira, quarta-feira e sexta-feira para impedir a instalação das atualizações nesses dias.
   - **Fuso horário**: escolha um fuso horário.
   - **Hora de início**: escolha a hora de início do período restrito. Por exemplo, insira 5h para que as atualizações não sejam instaladas a partir de 5h.
   - **Hora de término**: escolha a hora de término do período restrito. Por exemplo, insira 1h para que as atualizações possam ser instaladas a partir de 1h.
  
   > [!IMPORTANT]  
   > Uma política que tem uma *Hora de início* e uma *Hora de término* definidas como meia-noite é avaliada como 0 hora e não 24 horas. Isso resulta em nenhuma restrição.  
    
   Para atrasar a visibilidade de atualizações de software por um período específico em seus dispositivos iOS supervisionados, defina essas configurações em [Restrições do Dispositivo](../configuration/device-restrictions-ios.md#general). As políticas de atualização de software substituem todas as restrições do dispositivo. Quando você define uma política de atualização de software e uma restrição para atrasar a visibilidade de atualizações de software, o dispositivo força uma atualização de software de acordo com a política. A restrição se aplica para que os usuários não vejam a opção de atualizar o próprio dispositivo e a atualização é enviada por push na primeira janela de tempo, conforme definido por sua política de atualização do iOS.

   Após definir as *Configurações da política de atualização*, selecione **Avançar**. 

5. Na guia **Marcas de escopo**, selecione **+ Selecionar marcas de escopo** para abrir o painel *Selecionar marcas* se desejar aplicá-las à política de atualização.
   
   - No painel **Selecionar marcas**, escolha uma ou mais marcas e, em seguida, clique em **Selecionar** para adicioná-las à política e retorne ao painel *Marcas de escopo*.  

   Quando estiver pronto, selecione **Avançar** para passar para *Atribuições*.

6. Na guia **Atribuições**, escolha **+ Selecionar grupos para incluir** e atribua a política de atualização a um ou mais grupos. Use **+ Selecionar grupos para excluir** a fim de ajustar a atribuição. Quando estiver pronto, selecione **Avançar** para continuar. 

   Os dispositivos usados pelos usuários afetados pela política são avaliados quanto à conformidade de atualizações. Essa política também é compatível com dispositivos sem usuários.

7. Na guia **Examinar + criar**, examine as configurações e selecione **Criar** quando estiver pronto para salvar sua política de atualização de iOS. A nova política é exibida na lista de políticas de atualização para iOS.


Para obter diretrizes da equipe de suporte do Intune, confira [Atrasar a visibilidade de atualizações de software no Intune para dispositivos supervisionados](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753).

> [!NOTE]
> O MDM da Apple não permite que você force um dispositivo a instalar atualizações em determinada hora ou data.

## <a name="edit-a-policy"></a>Editar uma política
Você pode editar uma política existente, incluindo a alteração dos horários restritos:

1. Em **Atualizações de software**, selecione **Atualizar políticas para iOS** e selecione a política que você deseja editar.

2. Ao exibir as **Propriedades** das políticas, selecione **Editar** para a página de política que você deseja modificar.  
   ![Editar uma política](./media/software-updates-ios/edit-policy.png)   

3. Depois de introduzir uma alteração, selecione **Examinar + salvar** > **Salvar** para salvar suas edições e retorne para as *Propriedades* das políticas.  
 
> [!NOTE]
> Se a **Hora de início** e a **Hora de término** forem definidas como meia-noite, o Intune não verificará se há restrições sobre quando instalar as atualizações. Isso significa que as configurações que você tem para **Selecionar horários para impedir instalações de atualizações** são ignoradas e as atualizações podem ser instaladas a qualquer momento.  


## <a name="monitor-device-installation-failures"></a>Monitorar falhas de instalação do dispositivo
<!-- 1352223 -->
**Atualizações de software** > **Falhas de instalação para dispositivos iOS** mostra uma lista de dispositivos iOS supervisionados que foram direcionados por uma política de atualização e que tentaram ser atualizados, mas que não conseguiram. Para cada dispositivo, você pode exibir o status do motivo pelo qual o dispositivo não foi atualizado automaticamente. Os dispositivos íntegros e atualizados não são mostrados na lista. Os dispositivos "atualizados" incluem a última atualização para a qual o dispositivo em si dá suporte.

## <a name="next-steps"></a>Próximas etapas

[Monitorar seu status](../configuration/device-profile-monitor.md).
