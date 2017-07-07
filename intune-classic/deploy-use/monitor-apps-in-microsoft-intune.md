---
title: "Monitorar implantações de aplicativo"
description: Saiba como monitorar aplicativos implantados com o Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5daad56d-71c8-455b-8a55-f8b33e279a8a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9255a9cb966ef02aba11e0a6aaf7caf7e808a41c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="monitor-app-deployments-in-microsoft-intune"></a>Monitorar implantações de aplicativo no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="monitor-an-app-deployment"></a>Monitorar uma implantação de aplicativo
Você pode ver os aplicativos gerenciados e o status de todas as implantações no console de administração do Intune. <!---App status is displayed in real-time. You don't have to wait for the device to check-in before you can see this.--->

### <a name="to-view-apps-that-you-manage-and-their-status"></a>Para exibir os aplicativos gerenciados e seu status
No espaço de trabalho **Aplicativos**, escolha o nó **Aplicativos** e escolha **Aplicativos**.

É exibida a lista de aplicativos gerenciados. Você pode escolher qualquer aplicativo para ver um status de instalação no painel inferior das janelas do console. Clique nesse status para ver mais detalhes. Por exemplo, se o status mostra **1 usuário tem este software disponível**, você pode escolher a mensagem para ver o nome do usuário.

> [!TIP]
> É possível usar a lista suspensa **Filtros** para mostrar apenas os aplicativos que atendem aos critérios especificados por você, como aplicativos cuja instalação falhou ou aplicativos que foram implantados com êxito.
>
> ![Exemplo de filtros de aplicativo](./media/app-filters.png)

Além disso, o espaço de trabalho **Painel** mostra uma visão geral do status de seus aplicativos. Se você clicar em qualquer lugar na visão geral, você será levado à lista de aplicativos.

## <a name="to-view-more-detailed-information-about-an-app"></a>Para exibir informações mais detalhadas sobre um aplicativo
Na lista de aplicativos, selecione qualquer aplicativo e escolha **Exibir Propriedades**.

Na página **Propriedades de Software** do aplicativo, clique em uma dessas guias: **Geral** – mostra informações gerais sobre o aplicativo e seu status de instalação, **Dispositivos** – mostra os dispositivos que instalaram com êxito uma implantação direcionada do aplicativo e **Usuários** – mostra os usuários cujos dispositivos instalaram com êxito uma implantação direcionada do aplicativo.

Assim como antes, você pode usar a lista suspensa **Filtros** para configurar os valores mostrados em cada uma das guias.
