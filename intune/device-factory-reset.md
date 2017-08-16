---
title: "Redefinir os dispositivos para as configurações de fábrica com o Intune"
titleSuffix: Intune on Azure
description: "Saiba como redefinir os dispositivos gerenciados com o Intune para suas configurações de fábrica."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8eff9b53-eef2-4c50-8aee-556bc49d69f2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44f69179f76c8d5eeca1594485ca3a9c1b036188
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/09/2017
---
# <a name="reset-intune-managed-devices-to-factory-settings"></a>Redefinir os dispositivos gerenciados pelo Intune para as configurações de fábrica


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A opção **Redefinir configurações de fábrica** retorna o dispositivo para suas configurações padrão. O dispositivo não será gerenciado pelo Intune e os dados pessoais e da empresa serão removidos. Você não pode desfazer essa ação.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Com suporte no Windows 8.1 e versões posteriores (dispositivos não gerenciados por EAS)
- Windows Phone – Com suporte
- iOS – Com suporte
- macOS – Sem suporte
- Android – Com suporte (não há suporte para o Android for Work)

## <a name="how-to-reset-a-device-to-factory-settings"></a>Como redefinir um dispositivo para as configurações de fábrica

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota de dispositivo **Redefinir configurações de fábrica**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.

