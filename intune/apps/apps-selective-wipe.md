---
title: Como apagar apenas dados corporativos de aplicativos
titleSuffix: Microsoft Intune
description: Saiba como apagar seletivamente somente os dados corporativos dos aplicativos gerenciados pelo Intune com o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/27/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 66319fab8449ac1832f7796fbfdd470d2a52e88a
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77781267"
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Como apagar somente dados corporativos de aplicativos gerenciados pelo Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Quando um dispositivo é perdido ou roubado ou quando um funcionário sai da empresa, você quer ter certeza de que os dados dos aplicativos da empresa sejam removidos do dispositivo. No entanto, talvez você não queira remover dados pessoais do dispositivo, principalmente quando se trata de um dispositivo que pertence a um funcionário.

>[!NOTE]
> As plataformas Android, iOS/iPadOS e Windows 10 são as únicas plataformas compatíveis no momento para apagar dados corporativos dos aplicativos gerenciados do Intune. Os aplicativos gerenciados do Intune são aplicativos que incluem o SDK de Aplicativo do Intune e têm uma conta de usuário licenciada para sua organização. A implantação de Políticas de Proteção de Aplicativo não precisa habilitar o apagamento seletivo do aplicativo.

Para remover seletivamente os dados de aplicativo da empresa, crie uma solicitação de apagamento usando as etapas neste tópico. Após a solicitação ser concluída, na próxima vez que o aplicativo for executado no dispositivo, os dados da empresa serão removidos do aplicativo. Além de criar uma solicitação de apagamento, você poderá configurar um apagamento seletivo dos dados da organização como uma nova ação quando as condições de configurações de acesso de APP (Políticas de Proteção de Aplicativos) não forem atendidas. Esse recurso ajuda a proteger e remover os dados confidenciais da organização automaticamente dos aplicativos, com base em critérios pré-configurados.

>[!IMPORTANT]
> Contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos. Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados. Atualmente, isso se aplica somente ao aplicativo Microsoft Outlook.

## <a name="deployed-wip-policies-without-user-enrollment"></a>Políticas de WIP implantadas sem o registro do usuário
Políticas de WIP (Proteção de Informações do Windows) podem ser implantadas sem que os usuários do MDM registrem o dispositivo com Windows 10. Essa configuração permite que as empresas protejam seus documentos corporativos com base na configuração do WIP, enquanto permitem que o usuário mantenha o gerenciamento dos seus próprios dispositivos Windows. Depois que os documentos forem protegidos com uma política de WIP, os dados protegidos poderão ser apagados seletivamente por um administrador do Intune. Selecionando o usuário e o dispositivo, e enviando uma solicitação de apagamento, todos os dados protegidos por meio da política de WIP ficarão inutilizáveis. No Intune, no portal do Azure, selecione **Aplicativo de cliente** > **Apagamento seletivo do aplicativo**. Para obter mais informações, consulte [Criar e implantar a política de proteção de aplicativo WIP (Proteção de Informações do Windows) com o Intune](windows-information-protection-policy-create.md).

## <a name="create-a-wipe-request"></a>Criar uma solicitação de apagamento

1. Entre no [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Apagamento seletivo de aplicativo** > **Criar solicitação de apagamento**.<br>
   O painel **Criar solicitação de apagamento** é exibido.
3. Clique em **Selecionar usuário**, escolha o usuário cujos dados de aplicativo você deseja apagar e clique em **Selecionar** na parte inferior do painel **Selecionar usuário**.

    ![Captura de tela do painel "Selecionar usuário"](./media/apps-selective-wipe/apps-selective-wipe-01.png)

4. Clique em **Selecione o dispositivo**, escolha o dispositivo e clique em **Selecionar** na parte inferior do painel **Selecionar dispositivo**.

    ![Captura de tela do painel "Criar solicitação de apagamento" onde o dispositivo está selecionado](./media/apps-selective-wipe/apps-selective-wipe-02.png)

5. Clique em **Criar** para fazer uma solicitação de apagamento.

O serviço cria e controla uma solicitação de apagamento separada para cada aplicativo protegido no dispositivo e o usuário associado à solicitação de apagamento.

   ![Captura de tela do painel "Aplicativos do cliente – apagamento seletivo de aplicativos"](./media/apps-selective-wipe/apps-selective-wipe-03.png)

## <a name="monitor-your-wipe-requests"></a>Monitorar suas solicitações de apagamento

É possível obter um relatório resumido que mostra o status geral da solicitação de apagamento e inclui o número de falhas e solicitações pendentes. Para obter mais detalhes, siga estas etapas:

1. No painel **Aplicativos** > **Apagamento seletivo de aplicativo**, você pode ver a lista de suas solicitações agrupadas por usuários. Como o sistema cria uma solicitação de apagamento para cada aplicativo protegido em execução no dispositivo, você poderá ver várias solicitações de um usuário. O status indica se uma solicitação de apagamento está **pendente**, com **falha**ou **bem-sucedida**.

    ![Captura de tela do status da solicitação de apagamento no painel Limpeza seletiva de aplicativo](./media/apps-selective-wipe/wipe-request-status-1.png)

Além disso, você pode ver o nome e o tipo de dispositivo, o que pode ser útil durante a leitura dos relatórios.

>[!IMPORTANT]
> O usuário deve abrir o aplicativo para que o apagamento ocorra, e ele pode durar até 30 minutos após a criação da solicitação.

## <a name="delete-a-wipe-request"></a>Excluir uma solicitação de apagamento

Apagamentos com status pendente são exibidos até serem excluídos manualmente. Para excluir uma solicitação de apagamento manualmente:

1. No painel **Aplicativos Cliente – apagamento seletivo do aplicativo**.

2. Na lista, clique com o botão direito do mouse na solicitação de apagamento que você deseja excluir e escolha **Excluir solicitação de apagamento**.

    ![Captura de tela da lista de solicitação de apagamento no painel Limpeza seletiva de aplicativo](./media/apps-selective-wipe/delete-wipe-request.png)

3. Será solicitado que você confirme a exclusão, escolha **Sim** ou **Não** e clique em **OK**.

## <a name="see-also"></a>Consulte também
[O que é política de proteção de aplicativo](app-protection-policy.md)

[O que é gerenciamento de aplicativos](app-management.md)
