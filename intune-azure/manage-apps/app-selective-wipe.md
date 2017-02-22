---
title: "Como apagar apenas dados corporativos de aplicativos | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba como apagar seletivamente os aplicativos com o Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 44aefa68761236b946f5ab1db678ecc4aa81e92b
ms.openlocfilehash: ab2f9d065a1c4b0e0a016ff6195742cd09965191

---

# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Como apagar somente dados corporativos de aplicativos gerenciados pelo Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Quando um dispositivo é perdido ou roubado ou quando um funcionário sai da empresa, você quer ter certeza de que os dados dos aplicativos da empresa sejam removidos do dispositivo. No entanto, talvez você não queira remover dados pessoais do dispositivo, principalmente quando se trata de um dispositivo que pertence a um funcionário.

Para remover seletivamente os dados de aplicativo da empresa, crie uma solicitação de apagamento usando as etapas neste tópico. Após a solicitação ser concluída, na próxima vez que o aplicativo for executado no dispositivo, os dados da empresa serão removidos do aplicativo.

>[!IMPORTANT]
> Contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos. Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. Atualmente, isso se aplica somente ao aplicativo Microsoft Outlook.

## <a name="create-a-wipe-request"></a>Criar uma solicitação de apagamento

1.  Entre no [Portal do Azure](https://portal.azure.com).

2.  Escolha **Mais Serviços**, digite **Intune** na caixa de texto de filtro e selecione **Intune**. A folha da versão prévia do Intune se abre, escolha a folha **Gerenciar aplicativos**.

    ![Captura de tela da folha Nova solicitação para apagar](../media/intune-azure-preview-blade.png)

3.  Na **folha Aplicativos Móveis**, escolha **Nova solicitação de apagamento**. A folha **Nova solicitação de apagamento** é aberta.

4.  Escolha **Nova solicitação de apagamento**. A folha **Nova solicitação de apagamento** é aberta.

    ![Captura de tela da folha Nova solicitação para apagar](../media/AzurePortal_MAM_NewWipeRequest.png)

5.  Escolha **Usuário** para abrir a folha **Usuário** e selecione o usuário cujos dados de aplicativo você deseja apagar.

6.  Escolha **Dispositivo**. Isso abre a folha **Dispositivo** que lista todos os dispositivos associados ao usuário selecionado e também fornece duas colunas, o nome do dispositivo, que é um nome amigável definido pelo usuário, e o tipo e a plataforma do dispositivo. Selecione o dispositivo que deseja apagar.

7.  Você está de volta na folha **Nova solicitação para apagar**. Escolha **OK** para fazer uma solicitação de apagamento. 

O serviço cria e controla uma solicitação de apagamento separada para cada aplicativo protegido no dispositivo e o usuário associado à solicitação de apagamento.

## <a name="monitor-your-wipe-requests"></a>Monitorar suas solicitações de apagamento

É possível obter um relatório resumido que mostra o status geral da solicitação de apagamento e inclui o número de falhas e solicitações pendentes. Para obter mais detalhes, siga estas etapas:

1.  Na folha **Aplicativos Móveis – Apagamento Seletivo de Aplicativo**, você pode ver a lista de suas solicitações agrupadas por usuários. Como o sistema cria uma solicitação de apagamento para cada aplicativo protegido em execução no dispositivo, você poderá ver várias solicitações de um usuário. O status indica se uma solicitação de apagamento está **pendente**, com **falha**ou **bem-sucedida**.

    ![Captura de tela da folha Nova solicitação para apagar](../media/wipe-request-status-1.png)

Além disso, você poderá ver o nome e o tipo de dispositivo, o que pode ser útil ao ler os relatórios.

>[!IMPORTANT]
> O usuário deve abrir o aplicativo para que o apagamento ocorra, e ele pode durar até 30 minutos após a criação da solicitação.

## <a name="delete-a-wipe-request"></a>Excluir uma solicitação de apagamento

Apagamentos com status pendente são exibidos até serem excluídos manualmente.  Para excluir uma solicitação de apagamento manualmente:

1.  Na folha **Solicitação de apagamento**, escolha o bloco **Solicitação de apagamento** para abrir a folha **Solicitação de apagamento**.

2.  Clique com o botão direito do mouse na solicitação de apagamento que você deseja excluir e escolha **Excluir solicitação de apagamento**.

    ![Captura de tela da folha Nova solicitação para apagar](../media/delete-wipe-request.png)

3.  Será solicitado que você confirme a exclusão, escolha **Sim** ou **Não** e clique em **OK**.

### <a name="see-also"></a>Consulte também
[O que é política de proteção de aplicativo](what-is-app-protection-policy.md)

[O que é gerenciamento de aplicativos](what-is-app-management.md)


<!--HONumber=Feb17_HO2-->


