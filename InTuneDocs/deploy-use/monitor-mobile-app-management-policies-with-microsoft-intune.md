---
title: "Monitorar políticas de MAM com o Microsoft Intune | Microsoft Intune"
description: "Veja quantos usuários têm a política e faça uma busca detalhada para encontrar mais informações."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 487fe778bae73c2ac5564f90c21328932060f576


---

# <a name="monitor-mobile-app-management-policies-with-microsoft-intune"></a>Monitorar as políticas de gerenciamento de aplicativos móveis com o Microsoft Intune
Depois de configurar uma política de MAM (gerenciamento de dispositivo móvel) e aplicá-la aos usuários, você pode monitorar o status de conformidade no [portal do Azure](https://portal.azure.com). O portal do Azure inclui informações sobre os usuários afetados pela política, o status de conformidade e os problemas que os usuários possam encontrar.
## <a name="summary-view"></a>Exibição de Resumo
Na folha **Gerenciamento de aplicativo móvel do Intune**, você pode ver um resumo do status de conformidade:


![Bloco de Resumo da folha de gerenciamento de aplicativos móveis do Intune](../media/mam-azure-portal-user-status-summary.png)

-   **Usuários**: o número total de usuários da sua empresa que usam os aplicativos que estão associados à política.

-   **GERENCIADO PELA POLÍTICA**: este é o número de usuários que usaram pelo menos um dos aplicativos no contexto de trabalho.

-   **SEM POLÍTICA**: o número de usuários que estão usando os aplicativos associados à política, mas que não são afetados pela política. Você pode considerar adicionar esses usuários à política.

- **Usuários sinalizados**: o número de usuários que estão tendo problemas. Atualmente, apenas usuários com dispositivos com jailbreak são relatados em **Usuários sinalizados**.


## <a name="detailed-view"></a>Exibição detalhada
Você pode obter a exibição detalhada do resumo escolhendo os blocos **Status do usuário** e **Usuários sinalizados**.

### <a name="user-status"></a>Status do usuário
Você pode pesquisar por um único usuário e verificar o status de conformidade dele. A folha **Relatório de aplicativo** exibe as seguintes informações para um usuário selecionado:
- Dispositivos que estão associados à conta de usuário

- Aplicativos com política de MAM no dispositivo

- Status:

  - **Check-in**: a política foi implantada para o usuário e o aplicativo foi usado no contexto de trabalho pelo menos uma vez.

  - **Check-in não realizado**: a política foi implantada para o usuário, mas o aplicativo ainda não foi usado no contexto de trabalho.

>[!NOTE]
> Se o usuário pesquisado não tiver a política de MAM implantada nele, você verá uma mensagem informando que o usuário não é alvo de nenhuma política de aplicativo.

Para ver o relatório para um usuário, siga estas etapas:

1.  Para selecionar um usuário, escolha o bloco **Resumo** ou a opção **RELATÓRIO DE APLICATIVO PELO USUÁRIO** na folha **Configurações**:

    ![Opção de relatório de aplicativo na folha Configurações](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

2. Na folha **Relatório de aplicativo** que é aberta, escolha **Selecionar usuário** para pesquisar por um usuário do Azure Active Directory.

    ![Selecione a opção de usuário na folha Relatório de aplicativo](../media/mam-azure-portal-app-reporting-select-user.png)

3. Selecione um usuário da lista. Você verá os detalhes do status de conformidade para esse usuário.

    ![Detalhes de relatório do aplicativo](../media/mam-azure-portal-app-reporting-by-user.png)

### <a name="flagged-users"></a>Usuários sinalizados
A exibição detalhada exibe a mensagem de erro, o aplicativo que foi acessado quando o erro ocorreu, a plataforma do dispositivo e um carimbo de hora.  

### <a name="see-also"></a>Consulte também
[Gerenciar a transferência de dados entre aplicativos iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [O que esperar quando seu aplicativo Android é gerenciado por políticas de MAM](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de MAM](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


