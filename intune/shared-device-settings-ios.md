---
title: "Definições de configuração de dispositivo compartilhado do Intune para iOS"
titleSuffix: Intune Azure preview
description: "Visualização do Intune Azure: aprenda as configurações do Intune que você pode usar para exibir informações sobre a tela de bloqueio do dispositivo iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6a2aba8b2f062a3e06d517a572992b84fd977514
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Definições de configuração de dispositivo compartilhado para exibir mensagens na tela de bloqueio do dispositivo iOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

As definições de configuração de dispositivo compartilhado permitem que você especifique um texto opcional que será exibido na janela de logon e na tela de bloqueio (por exemplo, uma mensagem "Se perdido, devolver a" e Informações de Marca do Ativo). 

>[!IMPORTANT]
> Esse recurso tem suporte em dispositivos supervisionados executando o iOS 9.3 e posterior.

1. Na folha **Recursos do dispositivo** escolha **Configuração do dispositivo compartilhado (somente supervisionado)**.
2. Na folha **Configuração do dispositivo compartilhado (somente supervisionado)**, configure o seguinte:
    - **Informações de marca do ativo** - insira informações sobre a marca do ativo do dispositivo. Por exemplo: **Pertencente a Contoso Corp**. As informações inseridas serão aplicadas a todos os dispositivos aos quais você atribui esse perfil.
    - **Nota de rodapé de tela de bloqueio** - insira uma observação que pode ajudar a devolver o dispositivo, caso ele tenha sido perdido ou roubado. Por exemplo: **Se encontrado, entre em contato com o 'número'**.
3. Quando terminar, escolha **OK** em até voltar à folha **Criar Perfil**, depois escolha **Criar**. 

