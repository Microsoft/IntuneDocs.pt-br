---
title: Configurar políticas de atualização de software do iOS/iPadOS no Microsoft Intune – Azure | Microsoft Docs
description: No Microsoft Intune, crie ou adicione uma política de configuração para restringir quando as atualizações de software são instaladas automaticamente em dispositivos iOS/iPadOS. Você pode escolher a data e a hora em que as atualizações não são instaladas. Você também pode atribuir essa política a grupos, usuários ou dispositivos e verificar se há falhas de instalação.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/20/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 77d4a90bb2eaa8434ff9c05362dcb0d7cb270651
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576159"
---
# <a name="add-iosipados-software-update-policies-in-intune"></a>Adicionar políticas de atualização de software do iOS/iPadOS no Intune

As políticas de atualização de software permitem que você force os dispositivos iOS/iPadOS supervisionados a instalar atualizações de SO automaticamente. Os dispositivos supervisionados são aqueles registrados pelo uso do Apple Business Manager ou do Apple School Manager. Ao configurar uma política para implantar atualizações, é possível:

- Escolher implantar a *atualização mais recente* disponível ou, se você não quiser implantar a atualização mais recente, escolher implantar uma atualização mais antiga pelo número de versão de atualização. Se você optar por implantar uma atualização mais antiga, também deverá definir uma política de configuração de dispositivo para restringir a visibilidade das atualizações de software.
- Especifique uma agenda que determine quando a atualização será instalada. Os agendamentos podem ser muito simples, como por exemplo instalar atualizações na próxima vez que o dispositivo fizer check-in, ou mais complexos, criando intervalos de data e hora durante os quais as atualizações podem ser instaladas ou impedidas de serem instaladas.

Esse recurso aplica-se a:

- iOS 10.3 e posterior (supervisionado)

Por padrão, os dispositivos fazem check-in no Intune em intervalos de aproximadamente oito horas. Se uma atualização estiver disponível por meio de uma política de atualização, o dispositivo baixará a atualização. Em seguida, o dispositivo instala a atualização no próximo check-in em sua configuração de agendamento. Embora o processo de atualização, normalmente, não envolva nenhuma interação do usuário, se o dispositivo tiver uma senha, o usuário precisará inseri-la para iniciar uma atualização de software. Os perfis não impedem que os usuários atualizem o sistema operacional manualmente. Os usuários podem ser impedidos de atualizar o sistema operacional manualmente com uma política de configuração de dispositivo para restringir a visibilidade das atualizações de software.

## <a name="configure-the-policy"></a>Configurar a política

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Escolha **Dispositivos** > **Atualizar políticas para iOS/iPadOS** > **Criar perfil**.
3. Na guia **Conceitos Básicos**, especifique um nome para esta política e uma descrição (opcional) e, em seguida, selecione **Avançar**.

   ![Guia Conceitos Básicos](./media/software-updates-ios/basics-tab.png)

4. Na guia **Atualizar configurações de política**, defina o seguinte:

   1. **Selecione a versão a ser instalada**. Você pode escolher:

      - *Última atualização*: isso implanta a atualização lançada mais recentemente para iOS/iPadOS.
      - Qualquer versão anterior que esteja disponível na caixa suspensa. Se você selecionar uma versão anterior, também deverá implantar uma política de configuração de dispositivo para atrasar a visibilidade das atualizações de software.

   2. **Tipo de agendamento**: configure o agendamento para esta política:

      - *Atualizar no próximo check-in*: a atualização será instalada no dispositivo na próxima vez que ela fizer check-in com o Intune. Essa é a opção mais simples e ela não tem configurações adicionais.
      - *Atualizar durante o horário agendado*: você configura uma ou mais janelas de tempo durante as quais a atualização será instalada após o check-in.
      - *Atualizar fora do horário agendado*: você configura uma ou mais janelas de tempo durante as quais as atualizações não serão instaladas após o check-in.

   3. **Agendamento semanal**: se você escolher um tipo de agendamento diferente de *atualizar no próximo check-in*, configure as seguintes opções:

      ![Exemplo de seleção para atualizar durante o horário agendado](./media/software-updates-ios/scheduled-time.png)

      - **Fuso horário**: escolha um fuso horário.
      - **Janela de tempo**: defina um ou mais blocos de tempo que são restritos quando as atualizações são instaladas. O efeito das opções a seguir depende do tipo de agendamento selecionado. Usando um dia de início e um dia de término, é possível usar blocos que se estendem de um dia para o outro. As opções incluem:

        - **Dia de início**: escolha o dia em que a janela de agendamento começa.
        - **Hora de início**: escolha a hora do dia em que a janela de agendamento começa. Por exemplo, se você selecionar 05:00 e tiver um tipo de agendamento de *Atualização durante o horário agendado*, 05:00 será o momento em que as atualizações poderão começar a ser instaladas. Se você escolher um tipo de agendamento de *Atualização fora de um horário agendado*, 05:00 será o início de um período de tempo durante o qual as atualizações não poderão ser instaladas.
        - **Dia de término**: escolha o dia em que a janela de agendamento termina.
        - **Hora de término**: escolha a hora do dia em que a janela de agendamento termina. Por exemplo, se você selecionar 01:00 e tiver um tipo de agendamento de *Atualização durante o horário agendado*, 01:00 será o momento em que as atualizações deixarão de poder ser instaladas. Se você escolher um tipo de agendamento de *Atualização fora de um horário agendado*, 01:00 será o início de um período de tempo durante o qual as atualizações poderão ser instaladas.

       Se você não configurar os horários para iniciar ou terminar, a configuração não resultará em nenhuma restrição e as atualizações poderão ser instaladas a qualquer momento.  

       > [!NOTE]
       > Para atrasar a visibilidade de atualizações de software por um período específico em seus dispositivos iOS/iPadOS supervisionados, defina essas configurações em [Restrições do Dispositivo](../configuration/device-restrictions-ios.md#general). As políticas de atualização de software substituem todas as restrições do dispositivo. Quando você define uma política de atualização de software e uma restrição para atrasar a visibilidade de atualizações de software, o dispositivo força uma atualização de software de acordo com a política. A restrição se aplica para que os usuários não vejam a opção de atualizar o próprio dispositivo e a atualização é enviada por push, conforme definido por sua política de atualização do iOS.

   Após definir as *Configurações da política de atualização*, selecione **Avançar**.

5. Na guia **Marcas de escopo**, selecione **+ Selecionar marcas de escopo** para abrir o painel *Selecionar marcas* se desejar aplicá-las à política de atualização.

   - No painel **Selecionar marcas**, escolha uma ou mais marcas e, em seguida, clique em **Selecionar** para adicioná-las à política e retorne ao painel *Marcas de escopo*.

   Quando estiver pronto, selecione **Avançar** para passar para *Atribuições*.

6. Na guia **Atribuições**, escolha **+ Selecionar grupos para incluir** e atribua a política de atualização a um ou mais grupos. Use **+ Selecionar grupos para excluir** a fim de ajustar a atribuição. Quando estiver pronto, selecione **Avançar** para continuar.

   Os dispositivos usados pelos usuários afetados pela política são avaliados quanto à conformidade de atualizações. Essa política também é compatível com dispositivos sem usuários.

7. Na guia **Examinar + criar**, examine as configurações e selecione **Criar** quando estiver pronto para salvar sua política de atualização de iOS/iPadOS. A nova política é exibida na lista de políticas de atualização para iOS/iPadOS.

Para obter diretrizes da equipe de suporte do Intune, confira [Atrasar a visibilidade de atualizações de software no Intune para dispositivos supervisionados](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753).

> [!NOTE]
> O MDM da Apple não permite que você force um dispositivo a instalar atualizações em determinada hora ou data. Você não pode usar as políticas de atualização de software do Intune para fazer o downgrade da versão do sistema operacional em um dispositivo.

## <a name="edit-a-policy"></a>Editar uma política

Você pode editar uma política existente, incluindo a alteração dos horários restritos:

1. Escolha **Dispositivos** > **Atualizar políticas para iOS**. Escolha a política que você deseja editar.

2. Ao exibir as **Propriedades** das políticas, selecione **Editar** para a página de política que você deseja modificar.

   ![Editar uma política](./media/software-updates-ios/edit-policy.png)

3. Depois de introduzir uma alteração, selecione **Examinar + salvar** > **Salvar** para salvar suas edições e retorne para as *Propriedades* das políticas.

> [!NOTE]
> Se a **Hora de início** e a **Hora de término** forem definidas como meia-noite, o Intune não verificará se há restrições sobre quando instalar as atualizações. Isso significa que as configurações que você tem para **Selecionar horários para impedir instalações de atualizações** são ignoradas e as atualizações podem ser instaladas a qualquer momento.

## <a name="monitor-device-installation-failures"></a>Monitorar falhas de instalação do dispositivo

<!-- 1352223 -->
**Atualizações de software** > **Falhas de instalação para dispositivos iOS** mostra uma lista de dispositivos iOS/iPadOS supervisionados que foram direcionados por uma política de atualização e que tentaram ser atualizados, mas que não conseguiram. Para cada dispositivo, você pode exibir o status do motivo pelo qual o dispositivo não foi atualizado automaticamente. Os dispositivos íntegros e atualizados não são mostrados na lista. Os dispositivos "atualizados" incluem a última atualização para a qual o dispositivo em si dá suporte.

## <a name="next-steps"></a>Próximas etapas

[Monitorar seu status](../configuration/device-profile-monitor.md).
