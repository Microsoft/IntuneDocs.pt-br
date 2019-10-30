---
title: Ver perfis de dispositivo com o Microsoft Intune – Azure | Microsoft Docs
description: Exiba e gerencie os detalhes do perfil de configuração do dispositivo no Microsoft Intune, veja um gráfico do número de dispositivos atribuídos a um perfil e saiba quais dispositivos têm perfis atribuídos ou implantados. Também é possível solucionar problemas de perfis com conflitos de configuração.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: karthib
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a1c68421bf7c5dea0d93d45e0cbb748204d0f66b
ms.sourcegitcommit: c2e62f1ebdf75599c8e544287123c602f0f15f2b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72749390"
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Monitorar perfis de dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Intune inclui alguns recursos para ajudar a monitorar e gerenciar seus perfis de configuração do dispositivo. Por exemplo, você pode verificar o status de um perfil, ver quais dispositivos estão atribuídos e atualizar as propriedades de um perfil.

## <a name="view-existing-profiles"></a>Exibir os perfis existentes

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Perfis**.

Todos os perfis existentes são listados, incluem detalhes, como a plataforma, e mostram se o perfil está atribuído a todos os dispositivos.

## <a name="view-details-on-a-profile"></a>Exibir detalhes sobre um perfil

Depois de criar o perfil do seu dispositivo, o Intune fornece gráficos. Esses gráficos exibem o status de um perfil como sendo atribuído com êxito a dispositivos, ou se o perfil mostra um conflito.

1. Selecione um perfil existente. Por exemplo, selecione um perfil do macOS.
2. Selecione a guia **Visão geral**.

    O gráfico superior mostra o número de dispositivos atribuídos ao perfil de dispositivo. Por exemplo, se o perfil do dispositivo de configuração se aplicar a dispositivos macOS, o gráfico listará a contagem de dispositivos macOS.

    Ele também mostra o número de dispositivos para outras plataformas que recebem o mesmo perfil de dispositivo. Por exemplo, ele mostra a contagem de dispositivos não macOS.

    ![Exibir o número de dispositivos atribuídos ao perfil de dispositivo](./media/device-profile-monitor/device-configuration-profile-graphical-chart.png)

    O gráfico inferior mostra o número de usuários atribuídos ao perfil de dispositivo. Por exemplo, se o perfil do dispositivo de configuração se aplicar a usuários do macOS, o gráfico listará a contagem dos usuários macOS.

3. Selecione o círculo no gráfico superior. **Status do dispositivo** é aberto.

    São listados os dispositivos atribuídos ao perfil, e mostra se o perfil é implantado com êxito. Observe também que ele lista apenas os dispositivos com a plataforma específica (por exemplo, macOS).

    Feche os detalhes de **Status do dispositivo**.

4. Selecione o círculo no gráfico inferior. O **Status do usuário** é aberto. 

    Os usuários designados ao perfil são listados, e é mostrado se o perfil é implantado com êxito. Observe também que ele lista apenas os usuários com a plataforma específica (por exemplo, macOS).

    Feche os detalhes de **Status do usuário**.

5. De volta à lista **Perfis**, selecione um perfil específico. Você também pode alterar as propriedades existentes:
    - **Propriedades**: altere o nome ou atualize quaisquer configurações existentes.
    - **Atribuições**: inclua ou exclua dispositivos aos quais a política deve ser aplicada. Escolha **Grupos Selecionados** para escolher grupos específicos.
    - **Status do dispositivo**: São listados os dispositivos atribuídos ao perfil, e mostra se o perfil é implantado com êxito. Você pode selecionar um dispositivo específico para obter mais detalhes, incluindo os aplicativos instalados.
    - **Status de usuário**: lista os nomes de usuários com dispositivos afetados por esse perfil e se o perfil foi implantado com êxito. Você pode selecionar um usuário específico para obter ainda mais detalhes.
    - **Status por configuração**: filtra a saída mostrando as configurações individuais dentro do perfil e mostra se a configuração foi aplicada com êxito.

## <a name="view-conflicts"></a>Exibir conflitos

Em **Dispositivos** > **Todos os dispositivos**, você pode ver todas as configurações que estão causando conflitos. Quando houver um conflito, você também verá todos os perfis de configuração que contêm essa configuração. Os administradores podem usar esse recurso para ajudar a solucionar problemas e a corrigir as discrepâncias em relação aos perfis.

1. No Intune, selecione **Dispositivos** > **Todos os Dispositivos** > selecione um dispositivo existente na lista. O usuário final pode obter o nome do dispositivo no aplicativo Portal da Empresa.
2. Selecione **Configuração do dispositivo**. São listadas todas as políticas de configuração que se aplicam ao dispositivo.
3. Selecione a política. São exibidas todas as configurações nessa política que se aplicam ao dispositivo. Se algum dispositivo tiver um estado **Conflito**, selecione essa linha. Na nova janela, são exibidos todos os perfis e os nomes dos perfis cuja configuração está causando o conflito.

Agora que você sabe qual é a configuração em conflito e quais são as políticas que incluem essa configuração, será mais fácil resolver o conflito. 

## <a name="device-firmware-configuration-interface-profile-reporting"></a>Relatórios de perfil da Interface de Configuração do Firmware do Dispositivo

> [!WARNING]
> O monitoramento de perfis da DFCI está sendo criado no momento. Enquanto a DFCI está em versão prévia pública, os dados de monitoramento podem estar ausentes ou incompletos.

Os perfis da DFCI são relatados por configuração, assim como outros perfis de configuração de dispositivo. Dependendo do suporte do fabricante para a DFCI, algumas configurações poderão não se aplicar.

Com as configurações de perfil da DFCI, você pode ver os seguintes estados:

- **Em conformidade**: esse estado mostra quando um valor de configuração no perfil corresponde à configuração no dispositivo. Esse estado pode ocorrer nos seguintes cenários:

  - O perfil da DFCI configurou com êxito a configuração no perfil.
  - O dispositivo não tem o recurso de hardware controlado pela configuração e a configuração do perfil está **Desabilitada**.
  - A UEFI não permite que a DFCI desabilite o recurso e a configuração do perfil está **Habilitada**.
  - O dispositivo não tem o hardware para desabilitar o recurso e a configuração do perfil está **Habilitada**.

- **Não Aplicável**: esse estado mostra quando um valor de configuração no perfil está **Habilitada**, e a configuração correspondente no dispositivo não foi encontrada. Esse estado poderá acontecer se o hardware do dispositivo não tiver o recurso.

- **Fora de conformidade**: esse estado mostra quando um valor de configuração no perfil não corresponde à configuração no dispositivo. Esse estado pode ocorrer nos seguintes cenários:

  - A UEFI não permite que a DFCI desabilite uma configuração e a configuração do perfil está **Desabilitada**.
  - O dispositivo não tem o hardware para desabilitar o recurso e a configuração do perfil está **Desabilitada**.
  - O dispositivo não tem a versão mais recente do firmware da DFCI.
  - A DFCI foi desabilitada antes de ser registrada no Intune usando um controle "recusar" local no menu da UEFI.
  - O dispositivo foi registrado no Intune fora do registro do Autopilot.
  - O dispositivo não foi registrado no Autopilot por um CSP da Microsoft ou foi registrado diretamente pelo OEM.

## <a name="next-steps"></a>Próximas etapas

[Perguntas, problemas e resoluções comuns com perfis de dispositivo](device-profile-troubleshoot.md)  
[Solucionar problemas de políticas e de perfis e no Intune](troubleshoot-policies-in-microsoft-intune.md)
