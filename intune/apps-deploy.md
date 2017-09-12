---
title: Como atribuir aplicativos aos grupos
titlesuffix: Azure portal
description: "Depois de adicionar um aplicativo ao Intune, ele deverá ser atribuído a grupos de usuários ou dispositivos."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 51abb6daad11b9d6036396dcc5a5ce8f2a2c4ac4
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Como atribuir aplicativos a grupos com o Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Depois de adicionar um aplicativo ao Intune, ele poderá ser atribuído para usuários e dispositivos.

Aplicativos podem ser atribuídos aos dispositivos sejam eles gerenciados pelo Intune ou não. Use a tabela a seguir para ajudar a compreender as várias opções para atribuir aplicativos a usuários e dispositivos:

||||
|-|-|-|-|
|&nbsp;|Dispositivos registrados com o Intune|Dispositivos não registrados com o Intune|
|Atribuir a usuários|Sim|Sim|
|Atribuir a dispositivos|Sim|Não|
|Atribuir aplicativos encapsulados ou aqueles que incorporam o SDK do Intune (para políticas de proteção de aplicativo)|Sim|Sim|
|Atribuir aplicativos conforme a disponibilidade|Sim|Sim|
|Atribuir aplicativos conforme necessário|Sim|Não|
|Desinstalar aplicativos|Sim|Não|
|Os usuários finais instalam aplicativos disponíveis do aplicativo de Portal da Empresa|Sim|Não|
|Os usuários finais instalam aplicativos disponíveis do Portal da Empresa baseado na Web|Sim|Sim|

> [!NOTE]
> No momento, é possível atribuir aplicativos iOS e Android (tanto linha de negócios quanto comprados na loja) a dispositivos que não são registrados com o Intune.

## <a name="how-to-assign-an-app"></a>Como atribuir um aplicativo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1. Na carga de trabalho **Aplicativos Móveis**, escolha **Gerenciar** > **Aplicativos**.
2. Na folha da lista de aplicativos, escolha o aplicativo que você deseja atribuir.
3. Na folha <*nome do aplicativo*> – **Visão Geral**, escolha **Gerenciar** > **Atribuições**.
4. Escolha **Selecionar Grupos** e, na folha **Selecionar grupos**, escolha os grupos do Azure AD aos quais você deseja atribuir o aplicativo.
5. Para cada aplicativo que você escolher, selecione um **tipo de atribuição** para o aplicativo dentre:
    - **Disponível** – Os usuários instalam o aplicativo no site ou aplicativo do Portal da Empresa.
    - **Não Aplicável** – O aplicativo não é instalado nem é mostrado no Portal da Empresa.
    - **Obrigatório** – O aplicativo é instalado nos dispositivos dos grupos selecionados.
    - **Desinstalar** – O aplicativo é desinstalado dos dispositivos nos grupos selecionados.
    - **Disponível com ou sem registro** – Atribua este aplicativo a grupos de usuários cujos dispositivos não são registrados com o Intune.
6. **Apenas para aplicativos iOS** – se você tiver criado perfil da VPN do iOS que contém configurações de VPN por aplicativo, você poderá selecioná-lo em **VPN**. Quando o aplicativo é executado, a conexão VPN é aberta. Para obter mais informações, consulte [Configurações de VPN para dispositivos iOS](vpn-settings-ios.md).
6. Quando terminar, escolha **Salvar**.

Agora o aplicativo foi atribuído ao grupo selecionado.

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Como são resolvidos os conflitos entre as intenções de aplicativo

Às vezes, o mesmo aplicativo é atribuído a vários grupos, mas com intenções diferentes. Nesses casos, use essa tabela para entender a intenção resultante.

||||
|-|-|-|
|Intenção do grupo 1|Intenção do grupo 2|Intenção resultante|
|Necessário para o usuário|Disponível para o usuário|Necessária e Disponível|
|Necessário para o usuário|Não Disponível para o Usuário|Necessária|
|Necessário para o usuário|Desinstalação do usuário|Necessária|
|Disponível para o usuário|Não Disponível para o Usuário|Não disponível|
|Disponível para o usuário|Desinstalação do usuário|Desinstalar|
|Não Disponível para o Usuário|Desinstalação do usuário|Desinstalar
|Necessário para o usuário|Necessário para o dispositivo|Ambos, mas o Gateway trata como necessário 
|Necessário para o usuário|Desinstalação do dispositivo|Ambos, mas o Gateway resolve como necessário 
|Disponível para o usuário|Necessário para o dispositivo|Ambos, mas o Gateway resolve como necessário (Necessário e Disponível)
|Disponível para o usuário|Desinstalação do dispositivo|Ambos, mas o Gateway resolve como Disponível.<br>O aplicativo aparece no Portal da Empresa.<br>Se o aplicativo já estiver instalado (como aplicativo necessário com intenção anterior), então o aplicativo será desinstalado.<br>Contudo, se o usuário clicar em instalar no portal da empresa, então o aplicativo será instalado e a intenção de desinstalar não é cumprida.|
|Não Disponível para o Usuário|Necessário para o dispositivo|Necessária|
|Não Disponível para o Usuário|Desinstalação do dispositivo|Desinstalar|
|Desinstalação do usuário|Necessário para o dispositivo|Ambos, mas o Gateway resolve como Necessário|
|Desinstalação do usuário|Desinstalação do dispositivo|Ambos, mas o Gateway resolve como Desinstalação|
|Necessário para o dispositivo|Desinstalação do dispositivo|Necessária|
|Necessário e Disponível para o usuário|Disponível para o usuário|Necessária e Disponível|
|Necessário e Disponível para o usuário|Desinstalação do usuário|Necessária e Disponível|
|Necessário e Disponível para o usuário|Não Disponível para o Usuário|Necessária e Disponível|
|Necessário e Disponível para o usuário|Necessário para o dispositivo|Ambos Necessário e Disponível
|Necessário e Disponível para o usuário|Não disponível para o dispositivo|Necessária e Disponível|
|Necessário e Disponível para o usuário|Desinstalação do dispositivo|Ambos, mas o gateway resolve como necessário. Necessário + Disponível
|Não Disponível para o Usuário|Não disponível para o dispositivo|Não disponível|
|Disponível para o usuário|Não disponível para o dispositivo|Disponível|
|Necessário para o usuário|Não disponível para o dispositivo|Necessária|
|Disponível para o Usuário Sem Registro|Necessário e disponível para o usuário|Necessária e Disponível
|Disponível para o usuário sem registro|Necessário para o usuário|Necessária
|Disponível para o usuário sem registro|Não disponível para o usuário|Não disponível
|Disponível para o usuário sem registro|Disponível para o usuário|Disponível|
|Disponível para o usuário sem registro|Necessário para o dispositivo|Necessário e Disponível sem registro|
|Disponível para o usuário sem registro|Não disponível para o dispositivo|Disponível sem registro|
|Disponível para o usuário sem registro|Desinstalação do dispositivo|Desinstalação e Disponível sem registro.<br>Se o usuário não instalou o aplicativo do portal da empresa, a desinstalação é cumprida.<br>Se o usuário instalar o aplicativo do portal da empresa, a instalação terá prioridade sobre a desinstalação.|

>[!NOTE]
>Apenas para aplicativos da loja do iOS gerenciados, quando você os adiciona ao Intune e os atribui como Necessários, eles são criados automaticamente com as intenções Necessária e Disponível.

## <a name="next-steps"></a>Próximas etapas

Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.
