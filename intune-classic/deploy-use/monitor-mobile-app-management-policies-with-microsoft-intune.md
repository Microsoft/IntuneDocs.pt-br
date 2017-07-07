---
title: "Monitorar políticas de MAM com o Microsoft Intune"
description: "Veja quantos usuários têm a política e faça uma busca detalhada para encontrar mais informações."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c3c41f5e3b0fc81232b03fe547bee7f72fb427a0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="monitor-app-protection-policies-with-microsoft-intune"></a>Monitorar as políticas de proteção de aplicativo com o Microsoft Intune
É possível monitorar o status de conformidade das políticas de proteção de aplicativo que você aplicou aos usuários. Você poderá encontrar informações sobre os usuários afetados pelas políticas de proteção de aplicativo, seu status de conformidade e quaisquer problemas que os usuários possam encontrar.

Há três locais diferentes para monitorar o status de conformidade:

-   Exibição de Resumo

-   Exibição detalhada

-   Exibição de Relatórios

## <a name="summary-view"></a>Exibição de Resumo

Siga as três etapas abaixo para abrir a exibição de Resumo:

1. Acesse o [Portal do Azure](https://portal.azure.com) e insira suas credenciais.
2. Escolha **Mais Serviços** e digite **Intune** na caixa de texto de filtro.
3. Escolha **Proteção de Aplicativo do Intune**.

Na folha **Gerenciamento de aplicativo móvel do Intune**, você pode ver um resumo do status de conformidade:

![Bloco de Resumo da folha de gerenciamento de aplicativos móveis do Intune](../media/mam-azure-portal-user-status-summary.png)

-   **Usuários**: o número total de usuários da sua empresa que usam os aplicativos que estão associados à política.

-   **GERENCIADO PELA POLÍTICA**: este é o número de usuários que usaram pelo menos um dos aplicativos no contexto de trabalho.

-   **SEM POLÍTICA**: o número de usuários que estão usando os aplicativos associados à política, mas que não são afetados pela política. Você pode considerar adicionar esses usuários à política.

- **Usuários sinalizados**: o número de usuários que estão tendo problemas. Atualmente, apenas usuários com dispositivos com jailbreak são relatados em **Usuários sinalizados**.


## <a name="detailed-view"></a>Exibição detalhada
Você pode obter a exibição detalhada do resumo escolhendo os blocos **Status do usuário** (com base na plataforma do sistema operacional) e **Usuários sinalizados**.

### <a name="user-status"></a>Status do usuário
Você pode pesquisar por um único usuário e verificar o status de conformidade dele. A folha **Relatório de aplicativo** exibe as seguintes informações para um usuário selecionado:
- Dispositivos que estão associados à conta de usuário

- Aplicativos com uma política de proteção do aplicativo no dispositivo

- Status:

  - **Check-in**: a política foi implantada para o usuário e o aplicativo foi usado no contexto de trabalho pelo menos uma vez.

  - **Check-in não realizado**: a política foi implantada para o usuário, mas o aplicativo ainda não foi usado no contexto de trabalho.

>[!NOTE]
> Se os usuários pesquisados não tiverem a política de proteção de aplicativo implantada, você verá uma mensagem informando que o usuário não é alvo de nenhuma política.

Para ver o relatório para um usuário, siga estas etapas:

1.  Para selecionar um usuário, escolha o bloco **Resumo**.

    ![Captura de tela 3](../media/MAM-reporting-6.png)

2. Na folha **Relatório de aplicativo** que é aberta, escolha **Selecionar usuário** para pesquisar por um usuário do Azure Active Directory.

    ![Selecione a opção de usuário na folha Relatório de aplicativo](../media/MAM-reporting-2.png)

3. Selecione um usuário da lista. Você verá os detalhes do status de conformidade para esse usuário.

### <a name="flagged-users"></a>Usuários sinalizados
A exibição detalhada mostra a mensagem de erro, o aplicativo que foi acessado quando o erro ocorreu, a plataforma do sistema operacional dispositivo afetada e o carimbo de data/hora.

## <a name="reporting-view"></a>Exibição de Relatórios

Você pode encontrar os mesmos relatórios da exibição detalhada e relatórios adicionais para ajudá-lo com o status de conformidade de política de proteção do aplicativo:

![Captura de tela 4](../media/MAM-reporting-7.png)

-   **App protection user report (Relatório de usuário da proteção do aplicativo):** descreve as mesmas informações que podem ser encontradas no relatório **Status do usuário** na exibição detalhada acima.

-   **Relatório de aplicativo de proteção do aplicativo:** fornece dois status de proteção de aplicativo diferentes que os administradores podem selecionar antes de gerar o relatório. Os status podem ser protegidos ou não protegidos.

    -   Status do usuário para a atividade de MAM gerenciada (protegido): este relatório descreve a atividade de cada aplicativo MAM gerenciado, por usuário.

        -   Ele mostra todos os aplicativos alvo das políticas de proteção de aplicativo para cada usuário e dividem o status de cada aplicativo como com check-in feito nas políticas de proteção do aplicativo ou que eram alvo de uma política de proteção do aplicativo mas o check-in nunca foi feito.
<br></br>
    -   Status do usuário para a atividade de MAM não gerenciada (desprotegido): este relatório descreve a atividade de aplicativos habilitados para MAM atualmente não gerenciados, por usuário. Isso pode acontecer de acordo com os seguintes motivos:

        -   Esses aplicativos estão sendo usados por um usuário ou um aplicativo que, no momento, não é alvo de uma política de proteção de aplicativo.

        -   Todos os aplicativos têm o check-in feito, mas não estão recebendo nenhuma política de proteção de aplicativo.

![Captura de tela 2](../media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Agrupamento de tabela

Depois que os dados do **Relatório do usuário de proteção de aplicativo** aparecerem, você poderá agregar os dados fazendo o seguinte:

- **Resultado da validação:** os dados aparecem agrupados pelo status de proteção do aplicativo, que pode ser êxito, aviso ou falha.
- **Nome do aplicativo:** os dados aparecem agrupados por aplicativos (o nome real do aplicativo) com falha, aviso ou êxito.

## <a name="export-app-protection-activities-to-csv"></a>Exportar as atividades de proteção do aplicativo para CSV

Você pode exportar todas as atividades de política de proteção de aplicativo para um único arquivo .csv. Isso pode ser útil para analisar todos os status de proteção de aplicativo relatados dos usuários.

Siga estas etapas para gerar o relatório de proteção do aplicativo:

1. Na folha Gerenciamento de aplicativo móvel do Intune, escolha Relatório de proteção de aplicativo.

    ![Captura de tela-6](../media/app-protection-report-csv-2.png)

2. Escolha Sim para salvar o relatório, escolha Salvar como e selecione a pasta na qual você deseja salvar o relatório.

    ![Captura de tela-7](../media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Consulte também
[Gerenciar a transferência de dados entre aplicativos iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](/intune/end-user-mam-apps-android)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](/intune/end-user-mam-apps-ios)
