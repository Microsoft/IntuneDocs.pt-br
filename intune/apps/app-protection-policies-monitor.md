---
title: Como monitorar as políticas de proteção de aplicativo
titleSuffix: Microsoft Intune
description: Este tópico descreve como monitorar políticas de proteção de aplicativo no Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 000b1d04dd3f520b55b1d33545a8803e23bf8965
ms.sourcegitcommit: 0d6f323152ec62f7d383891cce12ea0a4289cd8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72889588"
---
# <a name="how-to-monitor-app-protection-policies"></a>Como monitorar as políticas de proteção de aplicativo
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

É possível monitorar o status de conformidade das políticas de MAM (gerenciamento de aplicativo móvel) que você aplicou aos usuários no painel de proteção do aplicativo do Intune no [Portal do Azure](https://portal.azure.com). Além disso, você pode encontrar informações sobre os usuários afetados pelas políticas de MAM, o status de conformidade da política de MAM e problemas que podem estar ocorrendo para os usuários.

Existem três locais diferentes em que as políticas de proteção de aplicativo podem ser monitoradas:
- Exibição de Resumo
- Exibição detalhada
- Exibição de Relatórios

> [!NOTE]
> Para obter mais informações, confira [Como criar e atribuir políticas de proteção de aplicativo](app-protection-policies.md).

O período de retenção dos dados de proteção do aplicativo é de 90 dias. Todas as instâncias de aplicativos que fizeram check-in no serviço MAM nos últimos 90 dias são incluídas no relatório de status de proteção do aplicativo. Uma *instância de aplicativo* é um usuário + aplicativo + dispositivo exclusivo. 

## <a name="summary-view"></a>Exibição de Resumo

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel **Intune**, escolha **Aplicativos clientes**.
4. Para ver a exibição resumida, na carga de trabalho de **Aplicativos clientes**, em **Monitorar**, escolha **Status de proteção do aplicativo**.

   ![Captura de tela do bloco de resumo no painel de gerenciamento de aplicativos móveis do Intune](./media/app-protection-policies-monitor/app-protection-user-status-summary.png)

- **Usuários atribuídos**: O número total de usuários atribuídos em sua empresa que estão usando um aplicativo associado a uma política em um contexto de trabalho e que estão protegidos e licenciados, bem como os usuários atribuídos que não estão protegidos nem licenciados.
- **Usuários sinalizados**: Número de usuários que estão enfrentando problemas com seus dispositivos. Dispositivos em que foi feito jailbreak (iOS) e root (Android) são relatados em **Usuários sinalizados**. Usuários que têm dispositivos sinalizados pela verificação de atestado de dispositivos do Google SafetyNet (se ativado pelo administrador de TI) também serão indicados aqui. 
- **Usuários com aplicativos potencialmente nocivos**: O número de usuários que podem ter um aplicativo nocivo em seu dispositivo Android detectado pelo Google Play Protect. 
- **Status do usuário para iOS** e **Status do usuário para Android**: O número de usuários que usaram um aplicativo que tem uma política atribuída a eles em um contexto de trabalho para a plataforma relacionada. Essas informações mostram o número de usuários gerenciados pela política, bem como o número de usuários que estão usando um aplicativo que não é direcionado por nenhuma política em um contexto de trabalho. Você pode considerar adicionar esses usuários à política.
- **Principais aplicativos iOS protegidos**: tendo como base os aplicativos iOS mais usados, essas informações mostram o número de aplicativos iOS protegidos e desprotegidos.
- **Principais aplicativos Android protegidos**: tendo como base os aplicativos Android mais usados, essas informações mostram o número de aplicativos Android protegidos e desprotegidos.
- **Principais aplicativos iOS configurados sem registro**: tendo como base os aplicativos iOS mais usados para dispositivos não registrados, essas informações mostram o número de aplicativos iOS configurados.
- **Principais aplicativos Android configurados sem registro**: tendo como base os aplicativos Android mais usados para dispositivos não registrados, essas informações mostram o número de aplicativos Android configurados.

    > [!NOTE]
    > Se você tem várias políticas por plataforma, um usuário é considerado gerenciado por política quando tem pelo menos uma política atribuída a ele.

## <a name="detailed-view"></a>Exibição detalhada
Para obter a exibição detalhada do resumo, escolha os blocos **Status do usuário** (com base na plataforma do sistema operacional do dispositivo), **Usuários com aplicativos potencialmente nocivos** e **Usuários sinalizados**.

### <a name="user-status"></a>Status do usuário
Você pode pesquisar por um único usuário e verificar o status de conformidade dele. O painel **Relatório de aplicativo** mostra as seguintes informações de um usuário selecionado:
- **Ícone**: Exibe se o status do aplicativo está atualizado.
- **Nome do Aplicativo**: O nome do aplicativo.
- **Nome do Dispositivo**: Dispositivos que estão associados à conta do usuário.
- **Tipo de dispositivo**: o tipo de dispositivo ou sistema operacional que o dispositivo está executando.
- **Políticas**: as políticas associadas ao aplicativo.
- **Status**:
  - **Com check-in**: A política foi implantada para o usuário e o aplicativo foi usado no contexto de trabalho pelo menos uma vez.
  - **Sem check-in**: A política foi implantada para o usuário, mas o aplicativo não foi usado no contexto de trabalho desde então.
- **Última Sincronização**: momento em que o aplicativo foi sincronizado pela última vez com o Intune. 

>[!NOTE]
> A coluna **Última Sincronização** representa o mesmo valor no relatório de status do usuário no console e no relatório de Política de proteção de aplicativos [.csv exportável](https://docs.microsoft.com/intune/app-protection-policies-monitor#export-app-protection-activities). A diferença corresponde a um pequeno atraso na sincronização entre o valor nos dois relatórios. 
>
> O horário mencionado em Última Sincronização se refere à última vez que o Intune viu a instância do aplicativo. No momento em que um usuário final inicializa um aplicativo, este pode ou não se comunicar com o serviço de Proteção de Aplicativo do Intune, dependendo da última vez em que o usuário se conectou. Confira [os intervalos de repetição de check-in da Política de proteção de aplicativos ](https://docs.microsoft.com/en-us/intune/app-protection-policy-delivery). Se um usuário final não tiver usado esse aplicativo específico no último intervalo de check-in (normalmente, a cada 30 minutos para uso ativo) e inicializar o aplicativo:
>
> - O relatório .csv exportável da Política de Proteção de Aplicativos apresentará o horário mais recente entre de 1 (mínimo) e 30 minutos (máximo).
> - O relatório de status do usuário apresentará o horário mais recente instantaneamente.
>
> Por exemplo, suponhamos que um usuário final de destino e licenciado inicialize um aplicativo protegido às 12:00:
> - Se este for o primeiro login, isso significa que o usuário foi desconectado antes e não possui um registro de instância de aplicativo no Intune. Após o login, o usuário obtém um novo registro de instância do aplicativo e pode fazer o check-in imediatamente (com os mesmos atrasos listados anteriormente para check-ins futuros). Portanto, o horário da última sincronização será indicado como 12:00 no relatório de status do usuário e como 12:01 (ou 12:30, no pior cenário) no relatório da Política de proteção de aplicativos. 
> - Se o usuário estiver iniciando o aplicativo, o horário da última sincronização relatada dependerá do último check-in feito pelo usuário.


Para ver o relatório para um usuário, siga estas etapas:

1. Para selecionar um usuário, escolha o bloco de resumo **Status do usuário**.

    ![Captura de tela do bloco Resumo do gerenciamento de aplicativo móvel do Intune](./media/app-protection-policies-monitor/MAM-reporting-6.png)

2. No painel **Relatório de aplicativo**, escolha **Selecionar usuário** para pesquisar um usuário do Azure Active Directory.

    ![Captura de tela da opção Selecionar usuário no painel Relatório de aplicativo](./media/app-protection-policies-monitor/MAM-reporting-2.png)

3. Selecione um usuário da lista. Você pode ver os detalhes do status de conformidade desse usuário.

>[!NOTE]
> Se os usuários pesquisados não tiverem a política de MAM implantada, você verá uma mensagem informando que o usuário não é direcionado por nenhuma política de MAM.

### <a name="flagged-users"></a>Usuários sinalizados
A exibição detalhada mostra a mensagem de erro, o aplicativo que foi acessado quando o erro ocorreu, a plataforma do sistema operacional dispositivo afetada e o carimbo de data/hora. O erro geralmente corresponde a dispositivos com jailbreak (iOS) ou raiz (Android). Além disso, usuários com dispositivos sinalizados pela verificação de inicialização condicional do “atestado de dispositivo do SafetyNet” também serão indicados aqui com seus respectivos motivos, conforme relatado pelo Google. Para que um usuário seja removido do relatório, o status do dispositivo em si precisa ser alterado, o que acontece após a próxima verificação de detecção de raiz (ou verificação de jailbreak/verificação SafetyNet) que precisa relatar um resultado positivo. Se o dispositivo for realmente corrigido, a atualização no relatório Usuários sinalizados ocorrerá quando a folha for recarregada.

### <a name="users-with-potentially-harmful-apps"></a>Usuários com aplicativos potencialmente nocivos
A exibição detalhada mostra:

- O usuário.
- A ID do pacote do aplicativo.
- Se o aplicativo está habilitado para MAM.
- A categoria de ameaça.
- O email.
- O nome do dispositivo.
- O carimbo de data/hora.

Usuários com dispositivos sinalizados com **Exigir verificação de ameaças em aplicativos** pela verificação de inicialização condicional são indicados aqui com a categoria de ameaça, conforme relatado pelo Google. Se houver aplicativos descritos neste relatório que estejam sendo implantados pelo Microsoft Intune, contate o desenvolvedor do aplicativo e/ou remova a atribuição do aplicativo para os usuários finais. 

## <a name="reporting-view"></a>Exibição de Relatórios

Você pode encontrar os mesmos relatórios no canto superior da folha **Status de proteção do aplicativo**.

> [!NOTE]
> O Intune fornece campos adicionais de relatório do dispositivo, incluindo ID de Registro do Aplicativo, fabricante do Android, modelo e versão do patch de segurança, bem como modelo do iOS. No Intune, esses campos podem ser acessados selecionando **Aplicativos clientes** > **Status de proteção do aplicativo** > **Relatório de Proteção do Aplicativo: iOS, Android**. Além disso, esses parâmetros ajudam a configurar a lista de **Permissão** do fabricante do dispositivo (Android), a lista de **Permissão** do modelo do dispositivo (Android e iOS) e a configuração de versão mínima do patch de segurança do Android. 

Relatórios adicionais estão disponíveis para ajudá-lo com o status de conformidade da política de MAM. Para exibir esses relatórios, selecione **Aplicativos cliente** > **Status de proteção do aplicativo** > **Relatórios**. 

A folha **Relatórios** fornece vários relatórios com base no usuário e no aplicativo, incluindo os seguintes:

- **Relatório de usuário**: Esse relatório apresenta as mesmas informações que podem ser encontradas no relatório **Status do usuário** na seção [Exibição detalhada](app-protection-policies-monitor.md#detailed-view) acima.

- **Relatório de aplicativo**: Além de selecionar a plataforma e o aplicativo, esse relatório fornece dois status de proteção do aplicativo diferentes que você pode selecionar antes de gerar o relatório. Os status podem ser **Protegidos** ou **Desprotegidos**.

  - O status do usuário para a atividade de MAM gerenciado (**Protegido**): Esse relatório descreve a atividade de cada aplicativo MAM gerenciado, por usuário. Ele mostra todos os aplicativos direcionados pelas políticas de MAM para cada usuário e o status de cada aplicativo conforme verificado nas políticas de MAM. O relatório também inclui o status de cada aplicativo que foi direcionado com uma política de MAM, mas nunca foi verificado.
  - O status do usuário para a atividade de MAM não gerenciado (**Desprotegido**): Esse relatório descreve a atividade de aplicativos habilitados para MAM atualmente não gerenciados, por usuário. Isso pode acontecer porque:
    - Esses aplicativos estão sendo usados por um usuário ou um aplicativo que não é direcionado atualmente pela política de MAM.
    - Todos os aplicativos têm o check-in feito, mas não estão recebendo nenhuma política de MAM.

    ![Captura de tela da folha Relatório de aplicativo de um usuário, com detalhes de três aplicativos](./media/app-protection-policies-monitor/MAM-reporting-4.png)

- **Relatório de configuração do usuário**: Com base em um usuário escolhido, esse relatório fornece detalhes sobre as configurações de aplicativos que o usuário recebeu.
- **Relatório de configuração do aplicativo**: com base na plataforma e no aplicativo escolhidos, esse relatório fornece detalhes sobre os usuários que receberam configurações para o aplicativo escolhido.
- **Relatório de aprendizagem do aplicativo para a Proteção de Informações do Windows**: este relatório mostra quais aplicativos estão tentando ultrapassar os limites da política.
- **Aprendizagem de site para a Proteção de Informações do Windows**: este relatório mostra quais sites estão tentando ultrapassar os limites da política.

## <a name="table-grouping"></a>Agrupamento de tabela

Depois que os dados do **Relatório do usuário de proteção de aplicativo** são exibidos, é possível agregá-los fazendo o seguinte:

- **Resultado da validação**: os dados são agrupados pelo status de proteção de aplicativo, que pode ser "falha", "aviso" ou "êxito".
- **Nome do aplicativo**: os dados são agrupados pelo nome real do aplicativo. Novamente, o status pode ser "falha", "aviso" ou "êxito".

## <a name="export-app-protection-activities"></a>Exportar as atividades de proteção do aplicativo

Você pode exportar todas as atividades de política de proteção de aplicativo para um único arquivo .csv. Isso pode ser útil para analisar todos os status de proteção de aplicativo relatados dos usuários.

Siga estas etapas para gerar o relatório de proteção do aplicativo:

1. No painel Gerenciamento de aplicativo móvel do Intune, escolha **Relatório de proteção de aplicativo**.

    ![Captura de tela do link de download da Proteção de aplicativo](./media/app-protection-policies-monitor/app-protection-report-csv-2.png)

2. Selecione **Sim** para salvar seu relatório e, em seguida, escolha **Salvar como**. Selecione a pasta na qual você deseja salvar o relatório.

    ![Captura de tela da caixa de confirmação Salvar relatório](./media/app-protection-policies-monitor/app-protection-report-csv-1.png)

## <a name="see-also"></a>Consulte também
- [Gerenciar a transferência de dados entre aplicativos iOS](data-transfer-between-apps-manage-ios.md)
- [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](../fundamentals/end-user-mam-apps-android.md)
- [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](../fundamentals/end-user-mam-apps-ios.md)
