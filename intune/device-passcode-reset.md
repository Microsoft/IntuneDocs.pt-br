---
title: Redefinir e remover senhas de dispositivo com o Intune
titlesuffix: Azure portal
description: Saiba como redefinir e remover a senha nos dispositivos gerenciados com o Intune.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e1496d24fd9d3bb636a4eab00c254b753210f63
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2018
---
# <a name="reset-and-remove-the-passcode-on-intune-managed-devices"></a>Redefinir e remover a senha em dispositivos gerenciados pelo Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Os termos *remover* e *redefinir* são usados intercambiavelmente neste artigo.

A ação **Remover senha** gera uma nova senha para o dispositivo, que será exibida na folha <*nome do dispositivo*> **Visão Geral**.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Sem suporte
- Windows Phone – Com suporte do Windows Phone 8.1 à Atualização do Windows 10 para Criadores não ingressada no Azure AD, Atualização do Windows 10 para Criadores e versões posteriores
- iOS – Com suporte
- macOS – Sem suporte
- Android – Com suporte em versões anteriores ao Android 7. Não há suporte para o Android for Work.

## <a name="how-to-reset-a-passcode"></a>Como redefinir uma senha

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, selecione um dispositivo, escolha **...Mais** e, em seguida, escolha a ação remota de dispositivo **Remover senha**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos**, escolha **Ações do dispositivo**.
