---
title: "Fazer logoff do usuário de um dispositivo iOS com o Intune"
titlesuffix: Azure portal
description: "Saiba como fazer logoff do usuário atual de um dispositivo iOS com o Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 72518a997434b9f2b5e234162b9d76736102d6de
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a>Fazer logoff do usuário atual em dispositivos iOS gerenciados pelo Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


A ação **Fazer logoff do usuário atual** faz logoff do usuário atual em um dispositivo iPad compartilhado que está configurado para gerenciar o aplicativo Classroom para iOS com um [perfil de educação do iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Sem suporte
- Windows Phone – Sem suporte
- iOS – Com suporte no iOS 9.3 e versões posteriores (apenas em dispositivos iPad compartilhados)
- macOS – Sem suporte
- Android – Sem suporte

## <a name="how-to-logout-the-current-user"></a>Como fazer logoff do usuário atual

1.  Entre no portal do Azure.
2.  Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3.  Na folha **Intune**, escolha **Dispositivos**.
4.  Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5.  Na lista de dispositivos gerenciados, escolha um dispositivo iOS e, em seguida, selecione a ação remota do dispositivo **Fazer logoff do usuário atual**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.
