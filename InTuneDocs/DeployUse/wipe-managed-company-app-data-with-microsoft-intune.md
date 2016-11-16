---
title: Apagar dados de aplicativos de empresa gerenciados | Microsoft Intune
description: "Saiba como você pode remover seletivamente os dados da empresa de dispositivos remotamente."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 11/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8cde3ffb3be8656d5f256e16eb71ed4aaa7ceb5b
ms.openlocfilehash: 4718d61f9d76a903ffc1820c77fc755d1ca1707b


---

# <a name="wipe-managed-company-app-data-with-microsoft-intune"></a>Apagar dados de aplicativos de empresa gerenciados com o Microsoft Intune
Quando um dispositivo é perdido ou roubado ou quando um funcionário sai da empresa, você quer ter certeza de que os dados dos aplicativos da empresa sejam removidos do dispositivo. No entanto, talvez você não queira remover dados pessoais do dispositivo, principalmente quando se trata de um dispositivo que pertence a um funcionário.

Para remover de maneira seletiva os dados dos aplicativos da empresa, crie uma solicitação de apagamento usando as etapas descritas na seção **Criar uma solicitação de apagamento** deste tópico.  Após a solicitação ser concluída, na próxima vez que o aplicativo for executado no dispositivo, os dados da empresa serão removidos do aplicativo.
>[!NOTE]
> Contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos. Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. Atualmente, isso é aplicável somente ao aplicativo Microsoft Outlook.



## <a name="create-a-wipe-request"></a>Criar uma solicitação de apagamento

1.  Na folha **Gerenciamento de aplicativo móvel do Intune**, clique no bloco **Solicitações para apagar**.

    ![Captura de tela da folha Gerenciamento de aplicativo móvel do Intune com bloco Resumo](../media/AppManagement/AzurePortal_MAM_WipeRequests.png)

2.  Clique em **Nova solicitação de apagamento**.

    ![Captura de tela da folha Nova solicitação para apagar](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

3.  Na folha **Nova solicitação para apagar**, escolha **Usuário** para abrir a folha **Usuário** e selecione o usuário cujos dados de aplicativo você deseja apagar.

4.  Escolha **Dispositivo**.  Isso abre a folha **Dispositivo** , que lista todos os dispositivos associados ao usuário selecionado.  Selecione o dispositivo que deseja apagar.

5.  Agora você está de volta à folha **Nova solicitação para apagar**. Escolha **OK** para fazer uma solicitação de apagamento. O serviço cria e controla uma solicitação de apagamento separada para cada aplicativo protegido no dispositivo.


![Captura de tela do bloco Solicitações para apagar ](../media/AppManagement/AzurePortal_MAM_WipeRequestsSummary.png)

## <a name="monitor-your-wipe-requests"></a>Monitorar suas solicitações de apagamento
A folha **Gerenciamento de aplicativos móveis do Intune** tem um relatório resumido no bloco **Solicitação de apagamento** .  Ele exibe o status geral e inclui o número de solicitações pendentes e falhas. Você pode obter mais detalhes ao seguir as etapas descritas abaixo:

1.  Na folha **Gerenciamento de aplicativo móvel do Intune**, escolha o bloco **Solicitação para apagar** para abrir a folha **Solicitação para apagar**.

2.  Na folha **Solicitação de apagamento** , você pode ver a lista de suas solicitações agrupadas por usuário.  Como o sistema cria uma solicitação de apagamento para cada aplicativo protegido em execução no dispositivo, você poderá ver várias solicitações de um usuário.  O status indica se uma solicitação de apagamento ainda está **pendente**, com **falha**ou **bem-sucedida**.

O usuário deve abrir o aplicativo para que o apagamento ocorra, e ele pode durar até 30 minutos após a criação da solicitação. 

Apagamentos com status pendente são exibidos até serem excluídos manualmente.  Para excluir manualmente uma solicitação de apagamento, clique com o botão direito do mouse e escolha Excluir.

### <a name="see-also"></a>Consulte também
[Proteger dados de aplicativo usando políticas de gerenciamento de aplicativo móvel](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Usando o Portal do Azure](azure-portal-for-microsoft-intune-mam-policies.md)



<!--HONumber=Nov16_HO2-->


