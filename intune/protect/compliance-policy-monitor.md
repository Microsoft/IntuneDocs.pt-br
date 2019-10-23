---
title: Monitorar as políticas de conformidade do dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Use o painel de conformidade de dispositivos para monitorar a conformidade geral dos dispositivos, exibir relatórios e exibir a conformidade dos dispositivos por política e por configuração.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 131e3e54ae4794ff552daff8f40bf218783a039a
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504703"
---
# <a name="monitor-intune-device-compliance-policies"></a>Monitorar as políticas de conformidade do Dispositivo do Intune

Os relatórios de conformidade ajudam a examinar a conformidade do dispositivo e solucionar problemas relacionados à conformidade em sua organização. Usando esses relatórios, você pode exibir informações sobre:

- Os estados de conformidade geral dos dispositivos
- Os status de conformidade de uma configuração individual
- O status de conformidade de uma política individual
- Análise detalhada dos dispositivos individuais para exibir as configurações e políticas específicas que afetam o dispositivo

## <a name="open-the-compliance-dashboard"></a>Abrir painel de conformidade

Abra o **painel de conformidade do dispositivo do Intune**:

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Selecione **Conformidade do dispositivo** > **Visão geral**. O **Painel de conformidade do dispositivo** será aberto.

> [!IMPORTANT]
> Os dispositivos devem ser registrados no Intune para receber as políticas de conformidade do dispositivo.

## <a name="dashboard-overview"></a>Visão geral do painel

Quando o painel for aberto, você poderá obter uma visão geral por meio de todos os relatórios de conformidade. Nesses relatórios, você pode visualizar e verificar:

- A conformidade geral do dispositivo
- Conformidade do dispositivo por política
- Conformidade do dispositivo por configuração
- Status de proteção do aplicativo
- Status do agente de ameaça

![Imagem do painel mostrando o painel de conformidade dos dispositivos e os diferentes relatórios](./media/compliance-policy-monitor/idc-1.png)

Ao se aprofundar nesse relatório, você também pode visualizar as políticas e configurações de conformidade específicas que se aplicam a um dispositivo específico, incluindo o estado de conformidade de cada configuração.

### <a name="device-compliance-status-report"></a>Relatório de status de conformidade dos dispositivos

O gráfico mostra os estados de conformidade de todos os dispositivos registrados no Intune. Os estados de conformidade do dispositivo são mantidos em dois bancos de dados diferentes: Intune e Azure Active Directory. 

> [!IMPORTANT]
> O Intune segue o agendamento de check-in do dispositivo para todas as avaliações de conformidade no dispositivo. [Saiba mais sobre o agendamento de check-in do dispositivo](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Descrições dos diferentes estados da política de conformidade dos dispositivos:

- **Em conformidade**: o dispositivo aplicou com êxito uma ou mais configurações da política de conformidade de dispositivos.

- **Período de cortesia:** uma ou mais configurações da política de conformidade de dispositivos aplicam-se ao dispositivo. Porém, o usuário ainda não aplicou as políticas. Isso significa que o dispositivo não está em conformidade, mas está no período de cortesia definido pelo administrador.

  - Saiba mais sobre [Ações para dispositivos fora de conformidade](actions-for-noncompliance.md).

- **Não avaliado**: um estado inicial para dispositivos registrados recentemente. As possíveis razões para esse estado incluem:

  - Dispositivos que não estão atribuídos a uma política de conformidade e não têm um gatilho para verificar a conformidade
  - Dispositivos que ainda não fizeram check-in desde que a política de conformidade foi atualizada pela última vez
  - Dispositivos não associados a um usuário específico, como:
    - Dispositivos iOS comprados por meio do DEP (Programa de registro de dispositivos) da Apple que não têm afinidade de usuário
    - Dispositivos dedicados com Android Enterprise ou quiosque do Android
  - Dispositivos registrados com uma conta de gerenciador de registro do dispositivo (DEM)

- **Fora de conformidade:** o dispositivo não conseguiu aplicar uma ou mais configurações da política de conformidade de dispositivos. Ou o usuário não está em conformidade com as políticas.

- **Dispositivo não sincronizado:** o dispositivo não conseguiu relatar seu status da política de conformidade de dispositivo por um dos seguintes motivos:

  - **Desconhecido**: o dispositivo está offline ou falhou ao se comunicar com o Intune ou o Azure AD por outras razões.

  - **Erro**: o dispositivo falhou ao se comunicar com o Intune e o Azure AD, e recebeu uma mensagem de erro com o motivo.

> [!IMPORTANT]
> Os dispositivos que são registrados no Intune, mas não recebem nenhuma política de conformidade de dispositivo, são incluídos neste relatório no bucket **Compatível**.

#### <a name="drill-down-for-more-details"></a>Analisar detalhadamente para obter mais detalhes

No gráfico **Status de conformidade dos dispositivos**, selecione um status. Por exemplo, selecione o status **Não está em conformidade**:

![Escolha o status de não conformidade](./media/compliance-policy-monitor/select-not-compliant-status.png)

Essa opção mostra mais detalhes sobre os dispositivos nesse estado, incluindo a plataforma do sistema operacional, a data do último check-in e muito mais. 

![Imagem do painel mostrando mais detalhes do dispositivo nesse estado específico](./media/compliance-policy-monitor/drill-down-details.png)

Se quiser ver todos os dispositivos pertencentes a um usuário específico, você também poderá filtrar o relatório de gráfico, digitando o email do usuário.

#### <a name="filter-and-columns"></a>Filtro e colunas

![Selecione Filtro e Coluna para alterar os resultados no gráfico](./media/compliance-policy-monitor/filter-columns.png)

Quando você selecionar o botão **Filtro**, o submenu do filtro será aberto com mais opções, incluindo o estado de conformidade, os dispositivos com jailbreak e muito mais. **Aplique** o filtro para atualizar os resultados.

Usa a propriedade **Colunas** para adicionar ou remover colunas da saída do gráfico. Por exemplo, **Nome UPN** pode mostrar o endereço de email registrado no dispositivo. **Aplique** as colunas para atualizar os resultados.

#### <a name="device-details"></a>Detalhes do dispositivo

No gráfico, selecione um dispositivo específico e, em seguida, selecione **Conformidade do dispositivo**:

![Escolha um dispositivo específico e, em seguida, Conformidade do Dispositivo para ver as políticas de conformidade aplicadas](./media/compliance-policy-monitor/see-policies-applied-specific-device.png)

Essa opção fornece mais detalhes sobre as configurações da política de conformidade de dispositivos aplicadas a esse dispositivo. Quando você seleciona a política específica, são mostradas todas as configurações na política.

### <a name="devices-without-compliance-policy"></a>Dispositivos sem política de conformidade
Em **Conformidade do dispositivo** > **Visão Geral**, o relatório também identifica dispositivos que não têm políticas de conformidade atribuídas:

![Consulte os dispositivos sem nenhuma política de conformidade](./media/compliance-policy-monitor/devices-without-policies.png)

Quando você seleciona o bloco, ele mostra todos os dispositivos que não têm uma política de conformidade. Ele também mostra o usuário do dispositivo, o status de implantação da política e o modelo do dispositivo.

#### <a name="what-you-need-to-know"></a>O que você precisa saber

- Na configuração de segurança **Marcar dispositivos sem nenhuma política de conformidade atribuída como**, é importante identificar os dispositivos que não têm uma política de conformidade. Em seguida, poderá atribuir pelo menos uma política de conformidade a eles.

  A configuração de segurança pode ser definida no portal do Intune. Selecione **Conformidade do dispositivo** > **Configurações da política de conformidade**. Em seguida, defina **Marcar dispositivos sem nenhuma política de conformidade atribuída como** para **Em conformidade** ou **Fora de conformidade**. 

  Leia mais sobre esse [aprimoramento de segurança no serviço do Intune](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

- Os usuários que recebem alguma política de conformidade de qualquer tipo não aparecem no relatório, independentemente da plataforma do dispositivo. Por exemplo, se você atribuir uma política de conformidade do Windows para um usuário com um dispositivo Android, o dispositivo não aparecerá no relatório. No entanto, o Intune considera que o dispositivo Android não está em conformidade. Para evitar problemas, recomendamos criar políticas para cada plataforma de dispositivo e implantá-las para todos os usuários.

### <a name="per-policy-device-compliance-report"></a>Relatório de conformidade do dispositivo por política

O relatório **Conformidade dos dispositivos** > **Conformidade com a política** mostra as políticas e o número de dispositivos que estão em conformidade e fora de conformidade. 

![Veja uma lista da política e quantos dispositivos em conformidade e fora de conformidade há para essa política](./media/compliance-policy-monitor/idc-8.png)

Ao selecionar uma política específica, você pode ver o **status de conformidade**, o **alias de email do usuário**, o **modelo de dispositivo** e o **local** de cada dispositivo de destino dessa política de conformidade.

## <a name="setting-compliance-report"></a>Relatório de conformidade de configuração

O relatório **Conformidade dos dispositivos** > **Conformidade com a configuração** mostra, para cada configuração de conformidade, o número total de dispositivos em cada estado de conformidade. Ele mostra todas as configurações da política de conformidade de dispositivos de todas as políticas de conformidade, as plataformas às quais as configurações de política são aplicadas e o número de dispositivos fora de conformidade.

![Veja uma lista de todas as configurações nas diferentes políticas](./media/compliance-policy-monitor/idc-10.png)

Ao selecionar uma configuração específica, você pode ver o **status de conformidade**, o **alias de email do usuário**, o **modelo de dispositivo** e o **local** de cada dispositivo de destino dessa configuração.

> [!NOTE]
> É possível atribuir uma política a um dispositivo e a um usuário no mesmo dispositivo. Em alguns cenários, um dispositivo pode ser sincronizado antes da entrada do usuário, como quando o dispositivo é reinicializado. A conformidade pode avaliar esse usuário e mostrar o dispositivo como não compatível. Esse comportamento também pode mostrar a Conta do Sistema como um usuário não compatível.
>
> Esse é um problema conhecido de dispositivos Windows 10 com vários usuários. Todas as alterações ou atualizações desse comportamento são anunciadas em [Em desenvolvimento](../fundamentals/in-development.md) e/ou em [Novidades](../fundamentals/whats-new.md).

## <a name="view-status-of-device-policies"></a>Exibir o status de políticas de dispositivo

Você pode verificar os diferentes estados de suas políticas por plataforma. Por exemplo, você tem uma política de conformidade do macOS. E você deseja ver os dispositivos que são afetados por essa política e saber se há conflitos ou falhas.

Esse recurso está incluído no relatório de status do dispositivo:

1. Selecione **Conformidade do dispositivo** > **Políticas**. Uma lista de políticas é exibida, incluindo a plataforma, se a política está atribuída e mais detalhes.
2. Selecione uma política > **Visão geral**. Nessa exibição, a atribuição de política inclui os seguintes status:

    - Bem-sucedido: a política é aplicada
    - Erro: houve falha na aplicação da política. A mensagem normalmente é exibida com um código de erro vinculado a uma explicação. 
    - Conflito: duas configurações foram aplicadas ao mesmo dispositivo e o Intune não pode classificar o conflito. Um administrador deve verificar o problema.
    - Pendente: o dispositivo ainda não fez check-in no Intune para receber a política. 
    - Não aplicável: o dispositivo não pode receber a política. Por exemplo, a política atualiza uma configuração específica para iOS 11.1, mas o dispositivo usa iOS 10. 

3. Para ver detalhes sobre os dispositivos que usam essa política, selecione um dos status. Por exemplo, selecione **Bem-sucedido**. Na próxima janela, são listados detalhes do dispositivo específicos, como o nome do dispositivo e o status de implantação.

## <a name="how-intune-resolves-policy-conflicts"></a>Como o Intune resolve conflitos de política
Podem ocorrer conflitos de política quando várias políticas do Intune são aplicadas a um dispositivo. Se as configurações de política se sobrepuserem, o Intune resolverá os conflitos usando as seguintes regras:

- Se as configurações conflitantes forem de uma política de configuração do Intune e de uma política de conformidade, as configurações na política de conformidade têm precedência sobre as configurações na política de configuração. Isso acontece mesmo que as configurações na política de configuração sejam mais seguras.

- Se você tiver implantado várias políticas de conformidade, o Intune usará a mais segura entre elas.
