---
title: "Definições de configuração de dispositivo compartilhado do Intune para iOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para exibir informações na tela de bloqueio de dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61bb1f8c7a9b6c92c128f32910f2ad8d390b6c64
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
# Definições de configuração de dispositivo compartilhado para exibir mensagens na tela de bloqueio do dispositivo iOS
<a id="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

As definições de configuração de dispositivo compartilhado permitem que você especifique um texto opcional que será exibido na janela de logon e na tela de bloqueio. Por exemplo, uma mensagem “Se perdido, devolver a” e Informações de Etiqueta do Ativo. 

>[!IMPORTANT]
> Esse recurso tem suporte em dispositivos supervisionados executando o iOS 9.3 e posterior.

## Criar configurações de dispositivo compartilhado
<a id="create-shared-device-settings" class="xliff"></a>

1. Na folha **Recursos do dispositivo**, escolha **Configuração do dispositivo compartilhado (somente supervisionado)**.
2. Na folha **Configuração de dispositivo compartilhado (somente supervisionado)**, defina as seguintes configurações:
    - **Informações de marca do ativo** - insira informações sobre a marca do ativo do dispositivo. Por exemplo: **Pertencente a Contoso Corp**. As informações inseridas são aplicadas a todos os dispositivos aos quais você atribui esse perfil.
    - **Nota de rodapé de tela de bloqueio** – Se o dispositivo for perdido ou roubado, insira uma observação que pode ajudar a reaver o dispositivo. Por exemplo: **Se encontrado, entre em contato com ‘número’**.
3. Quando terminar, escolha **OK** em até voltar à folha **Criar Perfil**, depois escolha **Criar**. 


## Próximas etapas
<a id="next-steps" class="xliff"></a>

Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos. Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
