---
title: Como atribuir aplicativos a grupos no Microsoft Intune
titlesuffix: 
description: "Depois de adicionar um aplicativo ao Microsoft Intune, ele deverá ser atribuído a grupos de usuários ou dispositivos."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eba329be463fbf0593638bd4cf41c404a17f9cc0
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Como atribuir aplicativos a grupos com o Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Depois de adicionar um aplicativo no Microsoft Intune, é possível atribuí-lo a usuários e dispositivos.

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
|Receber atualizações de aplicativos do Intune|Sim|Não|
|Os usuários finais instalam aplicativos disponíveis do aplicativo de Portal da Empresa|Sim|Não|
|Os usuários finais instalam aplicativos disponíveis do Portal da Empresa baseado na Web|Sim|Sim|

> [!NOTE]
> No momento, é possível atribuir aplicativos iOS e Android (tanto linha de negócios quanto comprados na loja) a dispositivos que não são registrados com o Intune.<br></br><br></br>
> Para receber atualizações de aplicativo em dispositivos que não estão registrados com o Intune, os usuários de dispositivos devem navegar até o portal da empresa e instalar manualmente as atualizações de aplicativo.

## <a name="how-to-assign-an-app"></a>Como atribuir um aplicativo

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1. Na carga de trabalho **Aplicativos móveis**, escolha **Aplicativos** na seção **Gerenciar**.
2. Na folha da lista de aplicativos, escolha o aplicativo que você deseja atribuir.
3. Na folha **Visão geral** específica do aplicativo, escolha **Atribuições** na seção **Gerenciar**.
4. Escolha **Adicionar Grupo** para exibir a folha **Adicionar grupo** relacionada ao aplicativo.
5. Para o aplicativo específico, escolha um **tipo de atribuição** para o aplicativo como:
    - **Disponível para dispositivos registrados** – Os usuários instalam o aplicativo no site ou aplicativo Portal da Empresa.
    - **Disponível com ou sem registro** – Atribua este aplicativo a grupos de usuários cujos dispositivos não são registrados com o Intune. Observe que o tipo **Aplicativo Android for Work** não é compatível com essa opção. 
    - **Obrigatório** – O aplicativo é instalado nos dispositivos dos grupos selecionados.
    - **Desinstalar** – O aplicativo é desinstalado dos dispositivos nos grupos selecionados.

    > [!NOTE]
    > **Apenas para aplicativos iOS** – se você tiver criado perfil da VPN do iOS que contém configurações de VPN por aplicativo, você poderá selecioná-lo em **VPN**. Quando o aplicativo é executado, a conexão VPN é aberta. Para obter mais informações, consulte [Configurações de VPN para dispositivos iOS](vpn-settings-ios.md).

6. Selecione **Grupos Incluídos** para escolher os grupos de usuários que serão afetados por esta atribuição de aplicativo.
7. Clique em **Selecionar** depois de selecionar um ou mais grupos a serem incluídos.
8. Clique em **OK** na folha **Atribuir** para concluir a seleção do grupo incluído.
9. Clique em **Excluir Grupos** se desejar que alguns grupos de usuários não sejam afetados por esta atribuição de aplicativo.
10. Se você optar por excluir algum grupo, clique em **Selecionar** na folha **Selecionar grupos**.
11. Clique em **OK** na folha **Adicionar grupo**.
12. Clique em **Salvar** na folha **Atribuições** de aplicativo para salvar suas atribuições.

Agora o aplicativo foi atribuído ao grupo selecionado. Para obter mais informações de como incluir e excluir atribuições de aplicativo, confira [Incluir e excluir atribuições de aplicativo](apps-inc-exl-assignments.md).

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
>Apenas para aplicativos gerenciados da loja do iOS, quando você os adiciona ao Microsoft Intune e os atribui como **Necessários**, eles são criados automaticamente com as intenções **Necessário** e **Disponível**

## <a name="next-steps"></a>Próximas etapas

Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.
