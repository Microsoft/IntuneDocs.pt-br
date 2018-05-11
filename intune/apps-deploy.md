---
title: Atribuir aplicativos a grupos no Microsoft Intune
titlesuffix: ''
description: Saiba como atribuir um aplicativo Intune a grupos de usuários ou dispositivos.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 99eb2c70994fcb2b6ed116530f4a82d8db7bcb9b
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2018
---
# <a name="assign-apps-to-groups-with-microsoft-intune"></a>Atribuir aplicativos a grupos com o Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Depois de adicionar um aplicativo no Microsoft Intune, é possível atribuí-lo a usuários e dispositivos.

Você pode atribuir um aplicativo a um dispositivo não importa se o dispositivo é gerenciado pelo Intune. 

A tabela a seguir lista as várias opções para atribuir aplicativos para usuários e dispositivos:

||||
|-|-|-|-|
|&nbsp;|**Dispositivos registrados com o Intune**|**Dispositivos não registrados com o Intune**|
|Atribuir a usuários|Sim|Sim|
|Atribuir a dispositivos|Sim|Não|
|Atribuir aplicativos encapsulados ou aplicativos que incorporam o SDK do Intune (para políticas de proteção de aplicativo)|Sim|Sim|
|Atribuir aplicativos conforme a disponibilidade|Sim|Sim|
|Atribuir aplicativos conforme necessário|Sim|Não|
|Desinstalar aplicativos|Sim|Não|
|Receber atualizações de aplicativos do Intune|Sim|Não|
|Os usuários finais instalam aplicativos disponíveis do aplicativo do Portal da Empresa|Sim|Não|
|Os usuários finais instalam aplicativos disponíveis do Portal da Empresa baseado na Web|Sim|Sim|

> [!NOTE]
> No momento, é possível atribuir aplicativos iOS e Android (tanto aplicativos de linha de negócios quanto comprados na loja) a dispositivos que não estão inscritos no Intune.
>
> Para receber atualizações de aplicativo em dispositivos que não estão inscritos no Intune, os usuários de dispositivos devem navegar até o Portal da Empresa da organização e instalar manualmente as atualizações de aplicativo.

## <a name="to-assign-an-app"></a>Para atribuir um aplicativo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No menu do **Intune**, selecione **Aplicativos móveis**.
4. Na seção **Gerenciar** do menu, selecione **Aplicativos**.
5. No painel **Aplicativos**, selecione o aplicativo que você deseja atribuir.
6. Na seção **Gerenciar** do menu, selecione **Atribuições**.
7. Selecione **Adicionar Grupo** para abrir o painel **Adicionar grupo** relacionado ao aplicativo.
8. Para o aplicativo específico, selecione um **tipo de atribuição**:
   - **Disponível para dispositivos inscritos**: os usuários instalam o aplicativo do site do aplicativo Portal da Empresa.
   - **Disponível com ou sem registro**: atribua este aplicativo a grupos de usuários cujos dispositivos não estão registrados no Intune. O tipo **Aplicativo Android for Work** tipo não dá suporte a essa opção. 
   - **Obrigatório**: o aplicativo é instalado nos dispositivos nos grupos selecionados.
   - **Desinstalar**: o aplicativo é desinstalado de dispositivos nos grupos selecionados.

     > [!NOTE]
     > **Somente para aplicativos iOS**: se você tiver criado um perfil VPN do iOS contendo configurações de VPN por aplicativo, poderá selecioná-lo em **VPN**. Quando o aplicativo é executado, a conexão VPN é aberta. Para obter mais informações, consulte [Configurações de VPN para dispositivos iOS](vpn-settings-ios.md).

9. Para selecionar os grupos de usuários afetados por esta atribuição de aplicativo, selecione **Grupos Incluídos**.
10. Depois de selecionar um ou mais grupos a serem incluídos, clique em **Selecionar**.
11. No painel **Atribuir**, selecione **OK** para concluir a seleção de grupos incluídos.
12. Se desejar que alguns grupos de usuários não sejam afetados por esta atribuição de aplicativo, selecione **Excluir Grupos**.
13. Se você tiver escolhido excluir algum grupo, em **Selecionar Grupos**, escolha **Selecionar**.
14. No painel **Adicionar grupo**, selecione **OK**.
15. No painel **Atribuições** do aplicativo, selecione **Salvar**.

Agora o aplicativo foi atribuído aos grupos selecionados. Para obter mais informações de como incluir e excluir atribuições de aplicativo, confira [Incluir e excluir atribuições de aplicativo](apps-inc-exl-assignments.md).

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Como são resolvidos os conflitos entre as intenções de aplicativo

Às vezes, o mesmo aplicativo é atribuído a vários grupos, mas com intenções diferentes. As informações na tabela a seguir podem ajudá-lo a entender a intenção resultante quando isso ocorre:

||||
|-|-|-|
|**Intenção do grupo 1**|**Intenção do grupo 2**|**Intenção resultante**|
|Necessário para o usuário|Disponível para o usuário|Necessária e Disponível|
|Necessário para o usuário|Não Disponível para o Usuário|Necessária|
|Necessário para o usuário|Desinstalação do usuário|Necessária|
|Disponível para o usuário|Não Disponível para o Usuário|Não disponível|
|Disponível para o usuário|Desinstalação do usuário|Desinstalar|
|Não Disponível para o Usuário|Desinstalação do usuário|Desinstalar
|Necessário para o usuário|Necessário para o dispositivo|Ambos existem, o Gateway trata como Obrigatório
|Necessário para o usuário|Desinstalação do dispositivo|Ambos existem, mas o Gateway resolve como Obrigatório
|Disponível para o usuário|Necessário para o dispositivo|Ambos, mas o Gateway resolve como Obrigatório (Obrigatório e Disponível)
|Disponível para o usuário|Desinstalação do dispositivo|Ambos existem, o Gateway resolve como Disponível.<br><br>O aplicativo aparece no Portal da Empresa.<br><br>Se o aplicativo já estiver instalado (como aplicativo obrigatório com intenção anterior), ele será desinstalado.<br><br>Se o usuário selecionar **Instalar do Portal da Empresa**, o aplicativo será instalado e a intenção de desinstalação não será cumprida.|
|Não Disponível para o Usuário|Necessário para o dispositivo|Necessária|
|Não Disponível para o Usuário|Desinstalação do dispositivo|Desinstalar|
|Desinstalação do usuário|Necessário para o dispositivo|Ambos existem, mas o Gateway resolve como Obrigatório|
|Desinstalação do usuário|Desinstalação do dispositivo|Ambos, mas o Gateway resolve como Desinstalação|
|Necessário para o dispositivo|Desinstalação do dispositivo|Necessária|
|Necessário e disponível para o usuário|Disponível para o usuário|Necessária e Disponível|
|Necessário e disponível para o usuário|Desinstalação do usuário|Necessária e Disponível|
|Necessário e disponível para o usuário|Não Disponível para o Usuário|Necessária e Disponível|
|Necessário e disponível para o usuário|Necessário para o dispositivo|Ambos existem, Obrigatório e Disponível
|Necessário e disponível para o usuário|Não disponível para o dispositivo|Necessária e Disponível|
|Necessário e disponível para o usuário|Desinstalação do dispositivo|Ambos, mas o Gateway resolve como Obrigatório (Obrigatório e Disponível)
|Não Disponível para o Usuário|Não disponível para o dispositivo|Não disponível|
|Disponível para o usuário|Não disponível para o dispositivo|Disponível|
|Necessário para o usuário|Não disponível para o dispositivo|Necessária|
|Disponível para o usuário sem registro|Necessário e disponível para o usuário|Necessária e Disponível
|Disponível para o usuário sem registro|Necessário para o usuário|Necessária
|Disponível para o usuário sem registro|Não Disponível para o Usuário|Não disponível
|Disponível para o usuário sem registro|Disponível para o usuário|Disponível|
|Disponível para o usuário sem registro|Necessário para o dispositivo|Necessário e Disponível sem registro|
|Disponível para o usuário sem registro|Não disponível para o dispositivo|Disponível sem registro|
|Disponível para o usuário sem registro|Desinstalação do dispositivo|Desinstalação e Disponível sem registro.<br><br>Se o usuário não tiver instalado o aplicativo do Portal da Empresa, a desinstalação será cumprida.<br><br>Se o usuário instalar o aplicativo do Portal da Empresa, a instalação terá prioridade sobre a desinstalação.|

> [!NOTE]
> Apenas para aplicativos gerenciados da loja do iOS, quando você os adiciona ao Microsoft Intune e os atribui como **Obrigatório**, eles são criados automaticamente com as intenções **Obrigatório** e **Disponível**.

## <a name="next-steps"></a>Próximas etapas

Para saber mais sobre como monitorar as atribuições de aplicativo, consulte [Como monitorar aplicativos](apps-monitor.md).
