---
title: Ver perfis de dispositivo com o Microsoft Intune – Azure | Microsoft Docs
description: Exiba e gerencie os detalhes do perfil de configuração do dispositivo no Microsoft Intune, veja um gráfico do número de dispositivos atribuídos a um perfil e saiba quais dispositivos têm perfis atribuídos ou implantados. Também é possível solucionar problemas de perfis com conflitos de configuração.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: dc3a9620532951bd78e545e87b0d43dd6be3efe5
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186589"
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Monitorar perfis de dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Intune inclui alguns recursos no portal do Azure para ajudar a monitorar e gerenciar seus perfis de configuração do dispositivo. Por exemplo, você pode verificar o status de um perfil, ver quais dispositivos estão atribuídos e atualizar as propriedades de um perfil.

## <a name="view-existing-profiles"></a>Exibir os perfis existentes

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** > **Perfis**.

Todos os perfis existentes são listados, incluem detalhes, como a plataforma, e mostram se o perfil está atribuído a todos os dispositivos.

## <a name="view-details-on-a-profile"></a>Exibir detalhes sobre um perfil

Depois de criar o perfil do seu dispositivo, o Intune fornece gráficos. Esses gráficos exibem o status de um perfil como sendo atribuído com êxito a dispositivos, ou se o perfil mostra um conflito.

1. Selecione um perfil existente. Por exemplo, selecione um perfil do macOS.
2. Selecione a guia **Visão geral**.

    O gráfico superior mostra o número de dispositivos atribuídos ao perfil de dispositivo específico. Por exemplo, se o perfil do dispositivo de configuração se aplicar a dispositivos macOS, o gráfico listará a contagem de dispositivos macOS.

    Ele também mostra o número de dispositivos para outras plataformas que recebem o mesmo perfil de dispositivo. Por exemplo, ele mostra a contagem de dispositivos não macOS.

    ![Exibir o número de dispositivos atribuídos ao perfil de dispositivo](./media/device-configuration-profile-graphical-chart.png)

    O gráfico inferior mostra o número de usuários atribuídos ao perfil de dispositivo específico. Por exemplo, se o perfil do dispositivo de configuração se aplicar a usuários do macOS, o gráfico listará a contagem dos usuários macOS.

3. Selecione o círculo no gráfico superior. **Status do dispositivo** é aberto.

    São listados os dispositivos atribuídos ao perfil, e mostra se o perfil é implantado com êxito. Observe também que ele lista apenas os dispositivos com a plataforma específica (por exemplo, macOS).

    Feche os detalhes de **Status do dispositivo**.

4. Selecione o círculo no gráfico inferior. O **Status do usuário** é aberto. 

    Os usuários designados ao perfil são listados, e é mostrado se o perfil é implantado com êxito. Observe também que ele lista apenas os usuários com a plataforma específica (por exemplo, macOS).

    Feche os detalhes de **Status do usuário**.

5. De volta à lista **Perfis**, selecione um perfil específico. Você também pode alterar as propriedades existentes:
  - **Propriedades**: altere o nome ou atualize quaisquer configurações existentes.
  - **Atribuições de**: inclua ou exclua dispositivos aos quais a política deve ser aplicada. Escolha **Grupos Selecionados** para escolher grupos específicos.
  - **Status do dispositivo**: são listados os dispositivos atribuídos ao perfil, e mostra se o perfil é implantado com êxito. Você pode selecionar um dispositivo específico para obter mais detalhes, incluindo os aplicativos instalados.
  - **Status do usuário**: lista os nomes de usuários com dispositivos afetados por esse perfil e se o perfil foi implantado com êxito. Você pode selecionar um usuário específico para obter ainda mais detalhes.
  - **Status por configuração**: filtra a saída mostrando as configurações individuais dentro do perfil e mostra se a configuração foi aplicada com êxito.

## <a name="view-conflicts"></a>Exibir conflitos

Em **Dispositivos** > **Todos os dispositivos**, você pode ver todas as configurações que estão causando conflitos. Quando houver um conflito, também serão mostrados todos os perfis de configuração que contêm essa configuração. Os administradores podem usar esse recurso para ajudar a solucionar problemas e a corrigir as discrepâncias em relação aos perfis.

1. No Intune, selecione **Dispositivos** > **Todos os Dispositivos** > selecione um dispositivo existente na lista. O usuário final pode obter o nome do dispositivo no aplicativo Portal da Empresa.
2. Selecione **Configuração do dispositivo**. São listadas todas as políticas de configuração que se aplicam ao dispositivo.
3. Selecione a política. São exibidas todas as configurações nessa política que se aplicam ao dispositivo. Se algum dispositivo tiver um estado **Conflito**, selecione essa linha. Na nova janela, são exibidos todos os perfis e os nomes dos perfis cuja configuração está causando o conflito.

Agora que você sabe qual é a configuração em conflito e quais são as políticas que incluem essa configuração, será mais fácil resolver o conflito. 

## <a name="next-steps"></a>Próximas etapas
[Atribuir perfis de usuário e dispositivo](device-profile-assign.md)  
[Problemas comuns e resoluções com perfis de dispositivo](device-profile-troubleshoot.md)