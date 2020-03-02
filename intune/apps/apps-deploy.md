---
title: Atribuir aplicativos a grupos no Microsoft Intune
titleSuffix: ''
description: Saiba como atribuir um aplicativo Intune a grupos de usuários ou dispositivos.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cee415174d68f3e6c9e72f0f0e06aa0d5d80ad91
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511847"
---
# <a name="assign-apps-to-groups-with-microsoft-intune"></a>Atribuir aplicativos a grupos com o Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Depois de [adicionar um aplicativo](apps-add.md) ao Microsoft Intune, é possível atribuí-lo a usuários e dispositivos. É importante observar que você pode atribuir um aplicativo a um dispositivo seja ou não esse dispositivo gerenciado pelo Intune.

> [!NOTE]
> Não há suporte para a intenção de implantação disponível para grupos de dispositivos, há suporte apenas para os grupos de usuários.

A tabela a seguir lista as várias opções para atribuir aplicativos para usuários e dispositivos:

|   | Dispositivos registrados com o Intune | Dispositivos não registrados com o Intune |
|-------------------------------------------------------------------------------------------|------------------------------|----------------------------------|
| Atribuir a usuários | Sim | Sim |
| Atribuir a dispositivos | Sim | Não |
| Atribuir aplicativos encapsulados ou aplicativos que incorporam o SDK do Intune (para políticas de proteção de aplicativo) | Sim | Sim |
| Atribuir aplicativos conforme a disponibilidade | Sim | Sim |
| Atribuir aplicativos conforme necessário | Sim | Não |
| Desinstalar aplicativos | Sim | Não |
| Receber atualizações de aplicativos do Intune | Sim | Não |
| Os usuários finais instalam aplicativos disponíveis do aplicativo do Portal da Empresa | Sim | Não |
| Os usuários finais instalam aplicativos disponíveis do Portal da Empresa baseado na Web | Sim | Sim |

> [!NOTE]
> No momento, é possível atribuir aplicativos iOS/iPadOS e Android (tanto aplicativos de linha de negócios quanto comprados na loja) a dispositivos que não estão inscritos no Intune.
>
> Para receber atualizações de aplicativo em dispositivos que não estão inscritos no Intune, os usuários de dispositivos devem navegar até o Portal da Empresa da organização e instalar manualmente as atualizações de aplicativo.

## <a name="assign-an-app"></a>Atribuir um aplicativo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos**.
3. No painel **Aplicativos**, selecione o aplicativo que você deseja atribuir.
4. Na seção **Gerenciar** do menu, selecione **Atribuições**.
5. Selecione **Adicionar Grupo** para abrir o painel **Adicionar grupo** relacionado ao aplicativo.
6. Para o aplicativo específico, selecione um **tipo de atribuição**:
   - **Disponível para dispositivos registrados**: Atribua o aplicativo aos grupos de usuários que podem instalar o aplicativo no site ou do aplicativo Portal da Empresa.
   - **Disponível com ou sem registro**: Atribua este aplicativo a grupos de usuários cujos dispositivos não estão registrados no Intune. É necessário atribuir uma licença do Intune a esses usuários, consulte [Licenças do Intune](../fundamentals/licenses.md).
   - **Obrigatório**: O aplicativo é instalado nos dispositivos dos grupos selecionados. Algumas plataformas podem ter solicitações adicionais para o usuário final confirmar antes do início da instalação do aplicativo.
   - **Desinstalar**: O aplicativo é desinstalado dos dispositivos nos grupos selecionados se o Intune tiver instalado anteriormente o aplicativo no dispositivo por meio de uma atribuição "Disponível para dispositivos registrados" ou "Obrigatória" usando a mesma implantação. Links da Web não podem ser removidos após a implantação.

     > [!NOTE]
     > **Somente para aplicativos iOS/iPadOS**:
     > - Para configurar o que acorre com os aplicativos gerenciados quando os dispositivos deixam de ser gerenciados, você pode selecionar a configuração pretendida em **Desinstalar ao remover o dispositivo**. Para saber mais, confira o tópico [Configuração de desinstalação para aplicativos iOS/iPadOS gerenciados](apps-deploy.md#app-uninstall-setting-for-ios-managed-apps).
     > - Se você tiver criado um perfil VPN do iOS/iPadOS contendo configurações de VPN por aplicativo, poderá selecioná-lo em **VPN**. Quando o aplicativo é executado, a conexão VPN é aberta. Para obter mais informações, confira [Configurações de VPN para dispositivos iOS/iPadOS](../vpn-settings-ios.md).
     >
     > **Somente para aplicativos Android**: Se você implantar um aplicativo Android como **Disponível com ou sem registro**, o status de relatório ficará disponível apenas em dispositivos registrados.
     >
     > Sobre **Disponível para dispositivos registrados**: o aplicativo só será exibido como disponível se o usuário conectado ao Portal da Empresa for o usuário primário que registrou o dispositivo e se o aplicativo for aplicável ao dispositivo.

7. Para selecionar os grupos de usuários afetados por esta atribuição de aplicativo, selecione **Grupos Incluídos**.
8. Depois de selecionar um ou mais grupos a serem incluídos, clique em **Selecionar**.
9. No painel **Atribuir**, selecione **OK** para concluir a seleção de grupos incluídos.
10. Se desejar que alguns grupos de usuários não sejam afetados por esta atribuição de aplicativo, selecione **Excluir Grupos**.
11. Se você tiver escolhido excluir algum grupo, em **Selecionar Grupos**, escolha **Selecionar**.
12. No painel **Adicionar grupo**, selecione **OK**.
13. No painel **Atribuições** do aplicativo, selecione **Salvar**.

Agora o aplicativo foi atribuído aos grupos selecionados. Para obter mais informações de como incluir e excluir atribuições de aplicativo, confira [Incluir e excluir atribuições de aplicativo](apps-inc-exl-assignments.md).

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Como são resolvidos os conflitos entre as intenções de aplicativo

Em várias tentativas de atribuição de aplicativo, um único grupo é impedido de ser definido como destino. No entanto, se um usuário ou dispositivo for membro de vários grupos atribuídos com diferentes intenções, isso resultará em um conflito. Recomendamos não criar conflitos de atribuição para aplicativos.
As informações na tabela a seguir podem ajudar você a entender a intenção resultante quando ocorre um conflito:

| Intenção do grupo 1 | Intenção do grupo 2 | Intenção resultante |
|-----------------------------------|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Necessário para o usuário|Disponível para o usuário|Necessária e Disponível|
|Necessário para o usuário|Desinstalação do usuário|Necessária|
|Disponível para o usuário|Desinstalação do usuário|Desinstalar|
|Necessário para o usuário|Necessário para o dispositivo|Ambos existem, mas o Intune trata como Obrigatório
|Necessário para o usuário|Desinstalação do dispositivo|Ambos existem, mas o Intune resolve como Obrigatório
|Disponível para o usuário|Necessário para o dispositivo|Ambos existem, mas o Intune resolve como Obrigatório (Obrigatório e Disponível)
|Disponível para o usuário|Desinstalação do dispositivo|Ambos existem, mas o Intune resolve como Disponível.<br><br>O aplicativo aparece no Portal da Empresa.<br><br>Se o aplicativo já estiver instalado (como aplicativo obrigatório com intenção anterior), ele será desinstalado.<br><br>Se o usuário selecionar **Instalar do Portal da Empresa**, o aplicativo será instalado e a intenção de desinstalação não será cumprida.|
|Desinstalação do usuário|Necessário para o dispositivo|Ambos existem, mas o Intune resolve como Obrigatório|
|Desinstalação do usuário|Desinstalação do dispositivo|Ambos existem, mas o Intune resolve como Desinstalar|
|Necessário para o dispositivo|Desinstalação do dispositivo|Necessária|
|Necessário e disponível para o usuário|Disponível para o usuário|Necessária e Disponível|
|Necessário e disponível para o usuário|Desinstalação do usuário|Necessária e Disponível|
|Necessário e disponível para o usuário|Necessário para o dispositivo|Ambos existem, Obrigatório e Disponível
|Necessário e disponível para o usuário|Desinstalação do dispositivo|Ambos existem, mas o Intune resolve como Obrigatório (Obrigatório e Disponível)
|Disponível para o usuário sem registro|Necessário e disponível para o usuário|Necessária e Disponível
|Disponível para o usuário sem registro|Necessário para o usuário|Necessária
|Disponível para o usuário sem registro|Disponível para o usuário|Disponível|
|Disponível para o usuário sem registro|Necessário para o dispositivo|Necessário e Disponível sem registro|
|Disponível para o usuário sem registro|Desinstalação do dispositivo|Desinstalação e Disponível sem registro.<br><br>Se o usuário não tiver instalado o aplicativo do Portal da Empresa, a desinstalação será cumprida.<br><br>Se o usuário instalar o aplicativo do Portal da Empresa, a instalação terá prioridade sobre a desinstalação.|

> [!NOTE]
> Apenas para aplicativos gerenciados da loja do iOS, quando você os adiciona ao Microsoft Intune e os atribui como **Obrigatório**, eles são criados automaticamente com as intenções **Obrigatório** e **Disponível**.<br><br>
> Aplicativos da iOS Store (não aplicativos VPP do iOS/iPadOS) que forem direcionados com intenção obrigatória serão impostos no dispositivo no momento do check-in do dispositivo e também serão exibidos no aplicativo do Portal da Empresa.<br><br>
> Quando ocorrem conflitos na configuração **Desinstalar ao remover o dispositivo**, o aplicativo não é removido do dispositivo quando o dispositivo deixa de ser gerenciado.

## <a name="managed-google-play-app-deployment-to-unmanaged-devices"></a>Implantação de aplicativo do Google Play Gerenciado em dispositivos não gerenciados
Para dispositivos Android em um cenário de implantação APP-WE (Política de Proteção de Aplicativo sem registro) não registrado, é possível usar o Google Play Gerenciado para implantar aplicativos da loja e aplicativos de LOB (linha de negócios) para os usuários. Os aplicativos do Google Play Gerenciado direcionados como **Disponíveis com ou sem registro** serão exibidos no aplicativo da Play Store no dispositivo do usuário final, e não no aplicativo Portal da Empresa. O usuário final procurará e instalará aplicativos implantados dessa maneira do aplicativo Play. Como os aplicativos estão sendo instalados do Google Play Gerenciado, o usuário final não precisará alterar as configurações do dispositivo para permitir a instalação do aplicativo de fontes desconhecidas, o que significa que os dispositivos ficarão mais seguros. Se o desenvolvedor do aplicativo publicar no Play uma nova versão do aplicativo instalado no dispositivo do usuário, o aplicativo será atualizado automaticamente pelo Play. 

Etapas para atribuição de um aplicativo do Google Play Gerenciado em dispositivos não gerenciados:

1. Conecte seu locatário do Intune no Google Play gerenciado. Se já tiver feito isso para gerenciar os dispositivos de perfil de trabalho, dedicados ou totalmente gerenciados do Android Enterprise, você não precisará fazê-lo novamente.
2. Adicione aplicativos do Google Play gerenciado ao seu console do Intune.
3. Direcione aplicativos do Google Play gerenciados como **Disponíveis com ou sem registro** ao grupo de usuários desejado. Os direcionamentos de aplicativo **Obrigatório** e **Desinstalar** não têm suporte para dispositivos não registrados.
4. Atribuir uma Política de Proteção de Aplicativo ao grupo de usuário.
5. Na próxima vez em que o usuário final abrir o aplicativo Portal da Empresa, ele verá uma mensagem indicando que há aplicativos disponíveis no aplicativo da Play Store.  O usuário pode tocar nessa notificação para acessar diretamente o aplicativo da Play e ver os aplicativos corporativos, ou pode navegar até o aplicativo da Play Store separadamente.
6. O usuário final pode expandir o menu de contexto dentro do aplicativo da Play Store e alternar entre sua conta pessoal do Google (onde estão seus aplicativos pessoais) e sua conta de trabalho (onde estão aplicativos da loja e LOB direcionados a eles). Os usuários finais instalam os aplicativos tocando em Instalar no aplicativo da Play Store.

Quando um apagamento seletivo do APP é emitido no console do Intune, a conta de trabalho é automaticamente removida do aplicativo do Play Store, e o usuário final não verá mais os aplicativos de trabalho no catálogo de aplicativos da Play Store. Quando a conta de trabalho for removida de um dispositivo, os aplicativos instalados da Play Store permanecerão instalados no dispositivo e não serão desinstalados. 

## <a name="app-uninstall-setting-for-ios-managed-apps"></a>Configuração de desinstalação para aplicativos iOS gerenciados
Para dispositivos iOS/iPadOS, você pode escolher o que acontece com os aplicativos gerenciados ao cancelar o registro do dispositivo no Microsoft Intune ou ao remover o perfil de gerenciamento usando a configuração **Desinstalar ao remover o dispositivo**. Essa configuração se aplicará aos aplicativos somente depois que o dispositivo for registrado e os aplicativos forem instalados como gerenciados. Não é possível definir a configuração para links ou aplicativos Web. Somente os dados protegidos pelo MAM (Gerenciamento de aplicativo móvel) são removidos após a desativação por uma Limpeza Seletiva de Aplicativo.

Os valores padrão dessa configuração são preenchidos previamente para novas atribuições da seguinte maneira:

|Tipo de aplicativo para iOS | Configuração padrão para "Desinstalar ao remover o dispositivo" |
|--------------------|----------------|
| Aplicativo de linha de negócios | Sim |
| Aplicativo da Store | Não |
| Aplicativo VPP | Não |
| Aplicativo interno | Não |

>[!NOTE]
>**Tipos de atribuições "disponíveis":** se você estiver atualizando essa configuração para grupos que estejam como "disponível para dispositivos registrados" ou "disponível com ou sem registro", os usuários que já tiverem o aplicativo gerenciado não obterão a configuração atualizada até que sincronizem o dispositivo com o Intune e reinstalem o aplicativo. 
>
>**Atribuições preexistentes:** as atribuições que já existiam antes da adição dessa configuração são imutáveis, e todos os aplicativos gerenciados serão removidos caso esse dispositivo seja removido do gerenciamento.

## <a name="next-steps"></a>Próximas etapas

Para saber mais sobre como monitorar as atribuições de aplicativo, consulte [Como monitorar aplicativos](apps-monitor.md).
