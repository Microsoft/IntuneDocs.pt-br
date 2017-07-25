---
title: Apagar dados de aplicativos de empresa gerenciados
description: "Saiba como você pode remover seletivamente os dados da empresa de dispositivos remotamente."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7025bdd5d89e52f1c99f9cd834232daf324f3285
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="wipe-company-app-data-with-intune-mam"></a>Apagar dados de aplicativo da empresa com o Intune MAM

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Quando um dispositivo é perdido ou roubado ou quando um funcionário sai da empresa, você quer ter certeza de que os dados dos aplicativos da empresa sejam removidos do dispositivo. No entanto, talvez você não queira remover dados pessoais do dispositivo, principalmente quando se trata de um dispositivo que pertence a um funcionário.

Para remover seletivamente os dados de aplicativo da empresa, crie uma solicitação de apagamento usando as etapas neste tópico. Após a solicitação ser concluída, na próxima vez que o aplicativo for executado no dispositivo, os dados da empresa serão removidos do aplicativo.

>[!IMPORTANT]
> Contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos. Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. Atualmente, isso se aplica somente ao aplicativo Microsoft Outlook.

## <a name="create-a-wipe-request"></a>Criar uma solicitação de apagamento

1.  Entre no [Portal do Azure](https://portal.azure.com).

2.  Escolha **Mais Serviços**, digite **Intune** na caixa de texto de filtro e selecione **Proteção de Aplicativo do Intune**. A folha de Gerenciamento de aplicativos móveis do Intune é aberta.

    ![Captura de tela da folha Nova solicitação para apagar](../media/AppManagement/wipe-request-mam-main-blade.png)

2.  Na folha **Configurações**, escolha **Solicitações de apagamento**.

3.  Escolha **Nova solicitação de apagamento**. A folha **Nova solicitação de apagamento** é aberta.

    ![Captura de tela da folha Nova solicitação para apagar](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  Escolha **Usuário** para abrir a folha **Usuário** e selecione o usuário cujos dados de aplicativo você deseja apagar.

5.  Escolha **Dispositivo**. Isso abre a folha **Dispositivo** que lista todos os dispositivos associados ao usuário selecionado e também fornece duas colunas, o nome do dispositivo, que é um nome amigável definido pelo usuário, e o tipo e a plataforma do dispositivo. Selecione o dispositivo que deseja apagar.

6.  Você está de volta na folha **Nova solicitação para apagar**. Escolha **OK** para fazer uma solicitação de apagamento. 

O serviço cria e controla uma solicitação de apagamento separada para cada aplicativo protegido no dispositivo e o usuário associado à solicitação de apagamento.

>[!NOTE]
> Você também pode criar **Solicitações de apagamento** clicando no **bloco de Solicitação de apagamento** da folha de gerenciamento de aplicativos móveis do Intune.

## <a name="monitor-your-wipe-requests"></a>Monitorar suas solicitações de apagamento

É possível obter um relatório resumido que mostra o status geral da solicitação de apagamento e inclui o número de falhas e solicitações pendentes. Para obter mais detalhes, siga estas etapas:

1.  Na folha Gerenciamento de aplicativos móveis do Intune, clique no bloco **Solicitações de apagamento**.

2.  Na folha **Solicitação de apagamento**, escolha o bloco **Solicitação de apagamento** para abrir a folha **Solicitação de apagamento**.

3.  Na folha **Solicitação de apagamento**, você pode ver a lista de suas solicitações agrupadas por usuário. Como o sistema cria uma solicitação de apagamento para cada aplicativo protegido em execução no dispositivo, você poderá ver várias solicitações de um usuário. O status indica se uma solicitação de apagamento está **pendente**, com **falha**ou **bem-sucedida**.

    ![Captura de tela da folha Nova solicitação para apagar](../media/AppManagement/wipe-request-status-1.png)

Além disso, você poderá ver o nome e o tipo de dispositivo, o que pode ser útil ao ler os relatórios.

>[!IMPORTANT]
> O usuário deve abrir o aplicativo para que o apagamento ocorra, e ele pode durar até 30 minutos após a criação da solicitação.

## <a name="delete-a-wipe-request"></a>Excluir uma solicitação de apagamento

Apagamentos com status pendente são exibidos até serem excluídos manualmente.  Para excluir uma solicitação de apagamento manualmente

1.  Na folha Gerenciamento de aplicativos móveis do Intune, clique no bloco **Solicitações de apagamento**.

2.  Na folha **Solicitação de apagamento**, escolha o bloco **Solicitação de apagamento** para abrir a folha **Solicitação de apagamento**.

3.  Clique com o botão direito do mouse na solicitação de apagamento que você deseja excluir e escolha **Excluir solicitação de apagamento**.

    ![Captura de tela da folha Nova solicitação para apagar](../media/AppManagement/delete-wipe-request.png)

4.  Será solicitado que você confirme a exclusão, escolha **Sim** ou **Não** e clique em **OK**.


### <a name="see-also"></a>Consulte também
[Proteger dados de aplicativo usando políticas de gerenciamento de aplicativo móvel](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Usando o Portal do Azure](azure-portal-for-microsoft-intune-mam-policies.md)
