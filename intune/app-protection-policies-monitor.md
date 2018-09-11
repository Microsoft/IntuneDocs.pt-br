---
title: Como monitorar as políticas de proteção de aplicativo
titleSuffix: Microsoft Intune
description: Monitore o status de conformidade das políticas de gerenciamento de aplicativo móvel no Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b7dea97ef74489e3caae7433e8ebbe2b9ed39aa3
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43330034"
---
# <a name="how-to-monitor-app-protection-policies"></a>Como monitorar as políticas de proteção de aplicativo
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**Se você não estiver no Portal do Azure**, este tópico explicará [como criar políticas de proteção de aplicativo](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) no Portal Clássico do Intune.


Monitore o status de conformidade das políticas de MAM (gerenciamento de aplicativo móvel) que você aplicou aos usuários no painel de proteção de aplicativo do Intune no [Portal do Azure](https://portal.azure.com). Encontre informações sobre os usuários afetados pelas políticas de MAM, os status de conformidade e quaisquer problemas que os eles possam encontrar.

Há três locais diferentes para monitorar o status de conformidade:

-   Exibição de Resumo

-   Exibição detalhada

-   Exibição de Relatórios

## <a name="summary-view"></a>Exibição de Resumo

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Aplicativos clientes**.
4. Na carga de trabalho **Aplicativos clientes**, escolha **Monitorar** > **Status de proteção do aplicativo**, para ver a exibição resumida:

![Bloco de Resumo do painel de gerenciamento de aplicativos móveis do Intune](./media/app-protection-user-status-summary.png)

-   **Usuários**: o número total de usuários da sua empresa que usam um aplicativo associado à política em um contexto de trabalho.

-   **GERENCIADO POR POLÍTICA**: o número de usuários que usaram um aplicativo que tem uma política atribuída a eles em um contexto de trabalho.

-   **Nenhuma política**: o número de usuários que estão usando um aplicativo que não é afetado por nenhuma política em um contexto de trabalho. Você pode considerar adicionar esses usuários à política.
    > [!NOTE]
    > Se você tem várias políticas por plataforma, um usuário é considerado gerenciado por política quando tem pelo menos uma política atribuída a ele.

- **Usuários sinalizados**: o número de usuários que estão tendo problemas. Atualmente, apenas usuários com dispositivos com jailbreak são relatados em **Usuários sinalizados**.


## <a name="detailed-view"></a>Exibição detalhada
Você pode obter a exibição detalhada do resumo escolhendo os blocos **Status do usuário** (com base na plataforma do sistema operacional) e **Usuários sinalizados**.

### <a name="user-status"></a>Status do usuário
Você pode pesquisar por um único usuário e verificar o status de conformidade dele. O painel **Relatório de aplicativo** mostra as seguintes informações de um usuário selecionado:
- Dispositivos que estão associados à conta de usuário

- Aplicativos com política de MAM no dispositivo

- Status:

  - **Check-in**: a política foi implantada para o usuário e o aplicativo foi usado no contexto de trabalho pelo menos uma vez.

  - **Check-in não realizado**: a política foi implantada para o usuário, mas o aplicativo ainda não foi usado no contexto de trabalho.

>[!NOTE]
> Se os usuários pesquisados não tiverem a política de MAM implantada, você verá uma mensagem informando que o usuário não é direcionado por nenhuma política de MAM.

Para ver o relatório para um usuário, siga estas etapas:

1.  Para selecionar um usuário, escolha o bloco **Resumo**.

    ![Captura de tela realçando o bloco Resumo na folha de Configurações do gerenciamento de aplicativos móveis do Intune](./media/MAM-reporting-6.png)

2. No painel **Relatório de aplicativo** que é aberto, escolha **Selecionar usuário** para pesquisar um usuário do Azure Active Directory.

    ![Captura de tela realçando a opção Selecionar usuário no painel Relatório de aplicativo](./media/MAM-reporting-2.png)

3. Selecione um usuário da lista. Você pode ver os detalhes do status de conformidade desse usuário.

### <a name="flagged-users"></a>Usuários sinalizados
A exibição detalhada mostra a mensagem de erro, o aplicativo que foi acessado quando o erro ocorreu, a plataforma do sistema operacional dispositivo afetada e o carimbo de data/hora.

## <a name="reporting-view"></a>Exibição de Relatórios

Você pode encontrar os mesmos relatórios da exibição detalhada e relatórios adicionais para ajudá-lo com o status de conformidade de política de MAM:

![Captura de tela realçando dois relatórios disponíveis no painel Configurações](./media/MAM-reporting-7.png)

-   **App protection user report (Relatório de usuário da proteção do aplicativo):** descreve as mesmas informações que podem ser encontradas no relatório **Status do usuário** na exibição detalhada acima.

-   **Relatório de aplicativo de proteção do aplicativo:** fornece dois status de proteção de aplicativo diferentes que os administradores podem selecionar antes de gerar o relatório. Os status podem ser protegidos ou não protegidos.

    -   Status do usuário para a atividade de MAM gerenciada (protegido): este relatório descreve a atividade de cada aplicativo MAM gerenciado, por usuário.

        -   Ele mostra todos os aplicativos alvo das políticas de MAM para cada usuário e divide o status de cada aplicativo como com check-in feito nas políticas de MAM ou que eram alvo de uma política de MAM, mas nunca foi feito o check-in do aplicativo.
<br></br>
    -   Status do usuário para a atividade de MAM não gerenciada (desprotegido): este relatório descreve a atividade de aplicativos habilitados para MAM atualmente não gerenciados, por usuário. Isso pode acontecer de acordo com os seguintes motivos:

        -   Esses aplicativos estão sendo usados por um usuário ou um aplicativo que no momento não é alvo de uma política de MAM.

        -   Todos os aplicativos têm o check-in feito, mas não estão recebendo nenhuma política de MAM.

![Captura de tela mostrando uma folha Relatório de aplicativo de um usuário, com uma tabela de detalhes de três aplicativos registrados](./media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Agrupamento de tabela

Depois que os dados do **Relatório do usuário de proteção de aplicativo** aparecerem, você poderá agregar os dados fazendo o seguinte:

- **Resultado da validação:** os dados aparecem agrupados pelo status de proteção do aplicativo, que pode ser êxito, aviso ou falha.
- **Nome do aplicativo:** os dados aparecem agrupados por aplicativos (o nome real do aplicativo) com falha, aviso ou êxito.

## <a name="export-app-protection-activities-to-csv"></a>Exportar as atividades de proteção do aplicativo para CSV

Você pode exportar todas as atividades de política de proteção de aplicativo para um único arquivo .csv. Isso pode ser útil para analisar todos os status de proteção de aplicativo relatados dos usuários.

Siga estas etapas para gerar o relatório de proteção do aplicativo:

1. No painel Gerenciamento de aplicativo móvel do Intune, escolha **Relatório de proteção de aplicativo**.

    ![Captura de tela realçando o link de download da Proteção de aplicativo no painel de gerenciamento de aplicativos móveis do Intune](./media/app-protection-report-csv-2.png)

2. Escolha Sim para salvar o relatório, escolha Salvar como e selecione a pasta na qual você deseja salvar o relatório.

    ![Captura de tela da caixa de confirmação Salvar relatório](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Consulte também
[Gerenciar a transferência de dados entre aplicativos iOS](data-transfer-between-apps-manage-ios.md)

* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-android.md)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-ios.md)
