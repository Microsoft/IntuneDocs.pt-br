---
title: Como monitorar as políticas de proteção de aplicativo
titleSuffix: Microsoft Intune
description: Monitore o status de conformidade das políticas de gerenciamento de aplicativo móvel no Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/08/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: f86ebd91125ec60d2ad0a28b47f5ac01fb62e8e2
ms.sourcegitcommit: e9ba1280b95565a5c5674b825881655d0303e688
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54297291"
---
# <a name="how-to-monitor-app-protection-policies"></a>Como monitorar as políticas de proteção de aplicativo
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Monitore o status de conformidade das políticas de MAM (gerenciamento de aplicativo móvel) que você aplicou aos usuários no painel de proteção de aplicativo do Intune no [Portal do Azure](https://portal.azure.com). Encontre informações sobre os usuários afetados pelas políticas de MAM, os status de conformidade e quaisquer problemas que os eles possam encontrar.

Há três locais diferentes para monitorar o status de conformidade:

-   Exibição de Resumo

-   Exibição detalhada

-   Exibição de Relatórios

> [!NOTE]
> Saiba mais sobre como criar políticas de proteção de aplicativos em [Como criar e atribuir políticas de proteção de aplicativo](app-protection-policies.md).

## <a name="summary-view"></a>Exibição de Resumo

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Aplicativos clientes**.
4. Na carga de trabalho **Aplicativos cliente**, escolha **Status de proteção do aplicativo** na seção **Monitorar** para ver a exibição resumida:

![Bloco de Resumo do painel de gerenciamento de aplicativos móveis do Intune](./media/app-protection-user-status-summary.png)

-   **Usuários atribuídos**: O número total de usuários atribuídos em sua empresa que estão usando um aplicativo associado a uma política em um contexto de trabalho e que estão protegidos e licenciados, bem como os usuários atribuídos que não estão protegidos nem licenciados.
-   **Usuários sinalizados**: O número de usuários que estão tendo problemas. Os dispositivos com jailbreak são relatados em **Usuários sinalizados**.
-   **Status do usuário para iOS** e **Status do usuário para Android**: O número de usuários que usaram um aplicativo que tem uma política atribuída a eles em um contexto de trabalho para a plataforma relacionada. Essas informações mostram o número de usuários gerenciados pela política, bem como o número de usuários que estão usando um aplicativo que não é direcionado por nenhuma política em um contexto de trabalho. Você pode considerar adicionar esses usuários à política.

    > [!NOTE]
    > Se você tem várias políticas por plataforma, um usuário é considerado gerenciado por política quando tem pelo menos uma política atribuída a ele.

## <a name="detailed-view"></a>Exibição detalhada
Você pode obter a exibição detalhada do resumo escolhendo os blocos **Status do usuário** (com base na plataforma do sistema operacional) e **Usuários sinalizados**.

### <a name="user-status"></a>Status do usuário
Você pode pesquisar por um único usuário e verificar o status de conformidade dele. O painel **Relatório de aplicativo** mostra as seguintes informações de um usuário selecionado:
- Dispositivos que estão associados à conta de usuário

- Aplicativos com política de MAM no dispositivo

- Status:

  - **Com check-in**: A política foi implantada para o usuário e o aplicativo foi usado no contexto de trabalho pelo menos uma vez.

  - **Sem check-in**: A política foi implantada para o usuário, mas o aplicativo não foi usado no contexto de trabalho desde então.

>[!NOTE]
> Se os usuários pesquisados não tiverem a política de MAM implantada, você verá uma mensagem informando que o usuário não é direcionado por nenhuma política de MAM.

Para ver o relatório para um usuário, siga estas etapas:

1.  Para selecionar um usuário, escolha o bloco de resumo **Status do usuário**.

    ![Captura de tela do bloco Resumo do gerenciamento de aplicativo móvel do Intune](./media/MAM-reporting-6.png)

2. No painel **Relatório de aplicativo** que é aberto, escolha **Selecionar usuário** para pesquisar um usuário do Azure Active Directory.

    ![Captura de tela da opção Selecionar usuário no painel Relatório de aplicativo](./media/MAM-reporting-2.png)

3. Selecione um usuário da lista. Você pode ver os detalhes do status de conformidade desse usuário.

### <a name="flagged-users"></a>Usuários sinalizados
A exibição detalhada mostra a mensagem de erro, o aplicativo que foi acessado quando o erro ocorreu, a plataforma do sistema operacional dispositivo afetada e o carimbo de data/hora.

## <a name="reporting-view"></a>Exibição de Relatórios

Encontre os mesmos relatórios na folha **Status de proteção do aplicativo**.

> [!NOTE]
> O Intune fornece campos adicionais de relatórios do dispositivo, incluindo a ID de Registro do Aplicativo, o fabricante do Android, o modelo e a versão do patch de segurança, bem como o modelo do iOS. No Intune, esses campos estão disponíveis pela seleção de **Aplicativos cliente** > **Status de proteção do aplicativo** e escolha de **Relatório de Proteção do Aplicativo: iOS, Android**. Além disso, esses parâmetros ajudam a configurar a lista **Permissão** para o fabricante do dispositivo (Android), a lista **Permissão** para o modelo do dispositivo (Android e iOS) e a configuração de versão mínima do patch de segurança do Android. 

Relatórios adicionais estão disponíveis para ajudá-lo com o status de conformidade da política de MAM. Para exibir esses relatórios, selecione **Aplicativos cliente** > **Status de proteção do aplicativo** > **Relatórios**. 

A folha **Relatórios** fornece vários relatórios com base no usuário e no aplicativo, incluindo os seguintes:


-   **Relatório de usuário**: Esse relatório apresenta as mesmas informações que podem ser encontradas no relatório **Status do usuário** na seção Exibição detalhada acima.

-   **Relatório de aplicativo**: Esse relatório fornece dois status de proteção do aplicativo diferentes que os administradores podem selecionar antes de gerar o relatório. Os status podem ser protegidos ou não protegidos.

    -   Status do usuário para a atividade de MAM gerenciado (Protegido): Esse relatório descreve a atividade de cada aplicativo MAM gerenciado, por usuário.

        -   Ele mostra todos os aplicativos alvo das políticas de MAM para cada usuário e divide o status de cada aplicativo como com check-in feito nas políticas de MAM ou que eram alvo de uma política de MAM, mas nunca foi feito o check-in do aplicativo.
<br><br>
    -   Status do usuário para a atividade de MAM não gerenciado (Desprotegido): Esse relatório descreve a atividade de aplicativos habilitados para MAM atualmente não gerenciados, por usuário. Isso pode acontecer de acordo com os seguintes motivos:

        -   Esses aplicativos estão sendo usados por um usuário ou um aplicativo que no momento não é alvo de uma política de MAM.

        -   Todos os aplicativos têm o check-in feito, mas não estão recebendo nenhuma política de MAM.

![Captura de tela da folha Relatório de aplicativo de um usuário com detalhes de três aplicativos](./media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Agrupamento de tabela

Depois que os dados do **Relatório do usuário de proteção de aplicativo** aparecerem, você poderá agregar os dados fazendo o seguinte:

- **Resultado da validação:** Os dados aparecem agrupados pelo status de proteção de aplicativo, que pode ser falha, aviso ou êxito.
- **Nome do aplicativo:** Os dados aparecem agrupados por aplicativos (o nome real do aplicativo) com falha, aviso ou êxito.

## <a name="export-app-protection-activities-to-csv"></a>Exportar as atividades de proteção do aplicativo para CSV

Você pode exportar todas as atividades de política de proteção de aplicativo para um único arquivo .csv. Isso pode ser útil para analisar todos os status de proteção de aplicativo relatados dos usuários.

Siga estas etapas para gerar o relatório de proteção do aplicativo:

1. No painel Gerenciamento de aplicativo móvel do Intune, escolha **Relatório de proteção de aplicativo**.

    ![Captura de tela do link de download da Proteção de aplicativo](./media/app-protection-report-csv-2.png)

2. Escolha Sim para salvar o relatório, escolha Salvar como e selecione a pasta na qual você deseja salvar o relatório.

    ![Captura de tela da caixa de confirmação Salvar relatório](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Consulte também
[Gerenciar a transferência de dados entre aplicativos iOS](data-transfer-between-apps-manage-ios.md)

* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-android.md)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-ios.md)
