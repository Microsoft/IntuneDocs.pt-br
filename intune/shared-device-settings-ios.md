---
title: Definições de configuração de dispositivo compartilhado do Microsoft Intune para iOS
titlesuffix: ''
description: Conheça as configurações do Microsoft Intune que você pode usar para exibir informações na tela de bloqueio de dispositivos iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7c735486ad93bd76350435861482505a1ab0d30a
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31834220"
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Definições de configuração de dispositivo compartilhado para exibir mensagens na tela de bloqueio do dispositivo iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações do Microsoft Intune que você pode usar para exibir informações na tela de bloqueio de dispositivos iOS.

As definições de configuração de dispositivo compartilhado permitem que você especifique um texto opcional que será exibido na janela de logon e na tela de bloqueio. Por exemplo, uma mensagem “Se perdido, devolver a” e Informações de Etiqueta do Ativo. 

>[!IMPORTANT]
> Esse recurso tem suporte em dispositivos supervisionados executando o iOS 9.3 e posterior.

## <a name="create-shared-device-settings"></a>Criar configurações de dispositivo compartilhado

1. Do [Intune no Portal do Azure](https://portal.azure.com), navegue até os [**Recursos do dispositivo** na área de configuração do dispositivo](device-features-configure.md). 
1. No painel **Recursos do dispositivo**, escolha **Configuração do dispositivo compartilhado (somente supervisionado)**.
2. No painel **Configuração de dispositivo compartilhado (somente supervisionado)**, defina as seguintes configurações:
    - **Informações de marca do ativo** - insira informações sobre a marca do ativo do dispositivo. Por exemplo: **Pertencente a Contoso Corp**. As informações inseridas são aplicadas a todos os dispositivos aos quais você atribui esse perfil.
    - **Nota de rodapé de tela de bloqueio** – Se o dispositivo for perdido ou roubado, insira uma observação que pode ajudar a reaver o dispositivo. Por exemplo: **Se encontrado, entre em contato com ‘número’**.
3. Após terminar, escolha **OK** até retornar para o painel **Criar perfil** e selecione **Criar**. 


## <a name="next-steps"></a>Próximas etapas

Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos. Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
