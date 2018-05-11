---
title: Ver perfis de dispositivo com o Microsoft Intune – Azure | Microsoft Docs
description: Exiba e gerencie os detalhes de perfil de configuração de dispositivo no Microsoft Intune e veja um gráfico do número de dispositivos atribuídos a um perfil e quais dispositivos têm perfis atribuídos ou implantados.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e1c2eb08db58940ed575b3dea011395edd6711fc
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2018
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Monitorar perfis de dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Intune inclui alguns recursos no portal do Azure para ajudar a monitorar e gerenciar seus perfis de configuração do dispositivo. Por exemplo, você pode verificar o status de um perfil, ver quais dispositivos estão atribuídos e atualizar as propriedades de um perfil.

## <a name="view-existing-profiles"></a>Exibir os perfis existentes

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** > **Perfis**.

Todos os perfis existentes são listados e incluem detalhes como a plataforma e se o perfil é atribuído a todos os dispositivos.

## <a name="view-details-on-a-profile"></a>Exibir detalhes sobre um perfil

Depois de criar o perfil do seu dispositivo, o Intune fornece gráficos. Esses gráficos exibem o status de um perfil como sendo atribuído com êxito a dispositivos, ou se o perfil mostra um conflito.

1. Selecione um perfil existente. Por exemplo, selecione um perfil do macOS.
2. Selecione a guia **Visão geral**.

    O gráfico mostra o número de dispositivos atribuídos ao perfil de dispositivo específico. Por exemplo, se o perfil do dispositivo de configuração se aplicar a dispositivos macOS, o gráfico listará a contagem de dispositivos macOS.

    Ele também mostra o número de dispositivos para outras plataformas que recebem o mesmo perfil de dispositivo. Por exemplo, ele mostra a contagem de dispositivos não macOS.

    ![Exibir o número de dispositivos atribuídos ao perfil de dispositivo](./media/device-configuration-profile-graphical-chart.png)

3. Selecione o círculo no gráfico. **Status do dispositivo** é aberto.

    São listados os dispositivos atribuídos ao perfil, e mostra se o perfil é implantado com êxito. Observe também que ele lista apenas os dispositivos com a plataforma específica (por exemplo, macOS).

    Feche os detalhes de status do dispositivo.

4. Nas propriedades do perfil (**Perfis** > selecionar um perfil específico), você também pode alterar as propriedades existentes:
  - **Propriedades**: altere o nome ou atualize quaisquer configurações existentes.
  - **Atribuições de**: inclua ou exclua dispositivos aos quais a política deve ser aplicada. Escolha **Grupos Selecionados** para escolher grupos específicos.
  - **Status do dispositivo**: são listados os dispositivos atribuídos ao perfil, e mostra se o perfil é implantado com êxito. Você pode selecionar um dispositivo específico para obter mais detalhes, incluindo os aplicativos instalados.
  - **Status do usuário**: lista os nomes de usuários com dispositivos afetados por esse perfil e se o perfil foi implantado com êxito. Você pode selecionar um usuário específico para obter ainda mais detalhes.
  - **Status por configuração**: filtra a saída mostrando as configurações individuais dentro do perfil e mostra se a configuração foi aplicada com êxito.

## <a name="next-steps"></a>Próximas etapas
[Atribuir perfis de usuário e dispositivo](device-profile-assign.md)  
[Problemas comuns e resoluções com perfis de dispositivo](device-profile-troubleshoot.md)