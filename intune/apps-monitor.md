---
title: "Como monitorar informações e atribuições de aplicativo"
titlesuffix: Azure portal
description: "Depois de atribuir um aplicativo a usuários ou dispositivos, use essas informações para ajudar a monitorar seu status."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fbb1d3e11f8ba3e508a261981e461f35c99ca110
ms.sourcegitcommit: f8672ff73066c2d8bcb78c30f84fda8aa3057a1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Como monitorar atribuições e informações de aplicativo com o Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Intune fornece várias maneiras nas quais você pode monitorar as propriedades dos aplicativos que gerencia, além de seu status de atribuição.

1. Na carga de trabalho **Aplicativos Móveis**, escolha **Gerenciar** > **Aplicativos**.
2. Na lista da folha de aplicativos, escolha o aplicativo para o qual deseja ver informações. Em seguida, você verá a folha <*nome do aplicativo*> **Status de instalação do dispositivo**: ![folha de status de instalação do aplicativo.](./media/monitor-apps.png)

Em seguida, execute uma das ações a seguir para saber mais sobre seus aplicativos e suas atribuições.

## <a name="general"></a>Geral

- **Visão geral** - fornece uma visão geral básica do aplicativo e informações sobre o status de qualquer atribuição para o aplicativo. Você pode escolher um dos gráficos para abrir as folhas **Status de instalação do dispositivo** ou **Status de instalação do usuário** para obter informações mais detalhadas.

## <a name="manage"></a>Gerenciar

- **Propriedades** - permite exibir e alterar informações sobre o aplicativo selecionado. Para saber mais sobre as propriedades do aplicativo, veja [Como adicionar um aplicativo ao Microsoft Intune](apps-add.md).
- **Atribuições** - fornece informações sobre as atribuições para esse aplicativo. Para obter mais informações, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

## <a name="monitor"></a>Monitor

- **Status de instalação do dispositivo** - fornece informações detalhadas para cada dispositivo ao qual você atribuiu o aplicativo selecionado para incluir o nome do dispositivo, o sistema operacional, quando o dispositivo fez check-in por último no Intune e o status da instalação do aplicativo.
- **Status de instalação do usuário** – Fornece informações detalhadas para o usuário ao qual você atribuiu o aplicativo selecionado, incluindo o número de instalações do aplicativo que o usuário tem em todos os dispositivos e as informações sobre as falhas de instalação.