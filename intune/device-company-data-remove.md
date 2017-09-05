---
title: Remover dados da empresa de dispositivos com o Intune
titleSuffix: Intune on Azure
description: Saiba como remover apenas os dados da empresa de dispositivos gerenciados com o Intune.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8074d6e7cc0a061a6708f8c8bfae1a4dfcb6daa3
ms.sourcegitcommit: 10e3ab2aeb79a1fb2243bef2748ccc003fdd4cc7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Remover dados da empresa de dispositivos gerenciados pelo Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Remover dados da empresa** remove somente os dados da empresa de dispositivos gerenciados pelo Intune. A ação não remove dados pessoais do dispositivo. Após a remoção, o dispositivo não será gerenciado pelo Intune e não poderá mais acessar os recursos corporativos.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Com suporte (sem suporte para dispositivos Windows associados ao Azure Active Directory)
- Windows Phone – Com suporte
- iOS – Com suporte
- macOS – Com suporte
- Android – Com suporte

## <a name="how-to-remove-company-data"></a>Como remover os dados da empresa

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota de dispositivo **Remover dados da empresa**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.
