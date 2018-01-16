---
title: Redefinir e remover senhas de dispositivo com o Intune
titlesuffix: Azure portal
description: Saiba como redefinir e remover a senha nos dispositivos gerenciados com o Intune.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3fdbb2fe6d52eaff8844ccfe14cef6c15a31cdff
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2018
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

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota de dispositivo **Remover senha**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.
