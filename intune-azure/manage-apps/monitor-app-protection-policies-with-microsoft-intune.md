---
title: "Como monitorar políticas de proteção de aplicativo | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: veja quantos usuários têm a política e faça uma busca detalhada para encontrar mais detalhes."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 482ae5f9adab39670b15c10f20883ef9684b2525
ms.openlocfilehash: 6f121487aa369838a46d7c7dce16ad9259dd6f31


---

# <a name="how-to-monitor-app-protection-policies"></a>Como monitorar as políticas de proteção de aplicativo
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

**Se você não estiver na versão prévia do Intune no Azure**, este tópico explicará [como criar políticas de proteção de aplicativo](https://docs.microsoft.com/en-us/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) no console do Intune clássico.


É possível monitorar o status de conformidade das políticas de MAM (gerenciamento de aplicativo móvel) que você aplicou aos usuários na folha de proteção do aplicativo do Intune no [Portal do Azure](https://portal.azure.com). Você poderá encontrar informações sobre os usuários afetados pelas políticas de MAM, seu status de conformidade e quaisquer problemas que os usuários possam encontrar.

Há três locais diferentes para monitorar o status de conformidade:

-   Exibição de Resumo

-   Exibição detalhada

-   Exibição de Relatórios

## <a name="summary-view"></a>Exibição de Resumo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Gerenciar aplicativos**.
4. Na carga de trabalho **Gerenciar aplicativos**, escolha **Monitorar** > **Status do usuário da proteção de aplicativo**, para ver a exibição de resumo:

![Bloco de Resumo da folha de gerenciamento de aplicativos móveis do Intune](../media/app-protection-user-status-summary.png)

-   **Usuários**: o número total de usuários da sua empresa que usam os aplicativos que estão associados à política.

-   **GERENCIADO PELA POLÍTICA**: este é o número de usuários que usaram pelo menos um dos aplicativos no contexto de trabalho.

-   **SEM POLÍTICA**: o número de usuários que estão usando os aplicativos associados à política, mas que não são afetados pela política. Você pode considerar adicionar esses usuários à política.

- **Usuários sinalizados**: o número de usuários que estão tendo problemas. Atualmente, apenas usuários com dispositivos com jailbreak são relatados em **Usuários sinalizados**.


## <a name="detailed-view"></a>Exibição detalhada
Você pode obter a exibição detalhada do resumo escolhendo os blocos **Status do usuário** (com base na plataforma do sistema operacional) e **Usuários sinalizados**.

### <a name="user-status"></a>Status do usuário
Você pode pesquisar por um único usuário e verificar o status de conformidade dele. A folha **Relatório de aplicativo** exibe as seguintes informações para um usuário selecionado:
- Dispositivos que estão associados à conta de usuário

- Aplicativos com política de MAM no dispositivo

- Status:

  - **Check-in**: a política foi implantada para o usuário e o aplicativo foi usado no contexto de trabalho pelo menos uma vez.

  - **Check-in não realizado**: a política foi implantada para o usuário, mas o aplicativo ainda não foi usado no contexto de trabalho.

>[!NOTE]
> Se os usuários pesquisados não tiverem a política de MAM implantada neles, você verá uma mensagem informando que o usuário não é alvo de nenhuma política de MAM.

Para ver o relatório para um usuário, siga estas etapas:

1.  Para selecionar um usuário, escolha o bloco **Resumo**.

    ![Captura de tela 3](../media/MAM-reporting-6.png)

2. Na folha **Relatório de aplicativo** que é aberta, escolha **Selecionar usuário** para pesquisar por um usuário do Azure Active Directory.

    ![Selecione a opção de usuário na folha Relatório de aplicativo](../media/MAM-reporting-2.png)

3. Selecione um usuário da lista. Você verá os detalhes do status de conformidade para esse usuário.

### <a name="flagged-users"></a>Usuários sinalizados
A exibição detalhada mostra a mensagem de erro, o aplicativo que foi acessado quando o erro ocorreu, a plataforma do sistema operacional dispositivo afetada e o carimbo de data/hora.

## <a name="reporting-view"></a>Exibição de Relatórios

Você pode encontrar os mesmos relatórios da exibição detalhada e relatórios adicionais para ajudá-lo com o status de conformidade de política de MAM:

![Captura de tela&4;](../media/MAM-reporting-7.png)

-   **App protection user report (Relatório de usuário da proteção do aplicativo):** descreve as mesmas informações que podem ser encontradas no relatório **Status do usuário** na exibição detalhada acima.

-   **Relatório de aplicativo de proteção do aplicativo:** fornece dois status de proteção de aplicativo diferentes que os administradores podem selecionar antes de gerar o relatório. Os status podem ser protegidos ou não protegidos.

    -   Status do usuário para a atividade de MAM gerenciada (protegido): este relatório descreve a atividade de cada aplicativo MAM gerenciado, por usuário.

        -   Ele mostra todos os aplicativos alvo das políticas de MAM para cada usuário e divide o status de cada aplicativo como com check-in feito nas políticas de MAM ou que eram alvo de uma política de MAM, mas nunca foi feito o check-in do aplicativo.
<br></br>
    -   Status do usuário para a atividade de MAM não gerenciada (desprotegido): este relatório descreve a atividade de aplicativos habilitados para MAM atualmente não gerenciados, por usuário. Isso pode acontecer de acordo com os seguintes motivos:

        -   Esses aplicativos estão sendo usados por um usuário ou um aplicativo que no momento não é alvo de uma política de MAM.

        -   Todos os aplicativos têm o check-in feito, mas não estão recebendo nenhuma política de MAM.

![Captura de tela&2;](../media/MAM-reporting-4.png)

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

* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-android-apps.md)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-ios-apps.md)



<!--HONumber=Feb17_HO2-->


