---
title: Como implantar aplicativos
description: Use as informações neste tópico para ajudá-lo a implantar aplicativos com o Microsoft Intune.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ed098a22da1def82c90fbb159d54be9b1a369ba8
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="deploy-apps-in-microsoft-intune"></a>Implantar aplicativos no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use as informações neste tópico para ajudá-lo a implantar aplicativos com o Microsoft Intune.


## <a name="deploy-an-app"></a>Implantar um aplicativo
Neste procedimento, você implantará o aplicativo para os grupos de dispositivos ou usuários selecionados.

### <a name="to-deploy-an-app"></a>Para implantar um aplicativo

1. No [Console do administração do Microsoft Intune](https://manage.microsoft.com), clique em **Aplicativos** &gt; **Aplicativos** para exibir a lista dos aplicativos gerenciados por você.

2.  Selecione o aplicativo que deseja implantar e clique em **Gerenciar Implantação**.

3.  Na caixa de diálogo *&lt;nome do aplicativo&gt;*, na página **Selecionar Grupos**, selecione os grupos de usuários ou de dispositivos nos quais deseja implantar o aplicativo.

4.  Na página **Ação de Implantação**, configure o seguinte:

    - **Aprovação** - Escolha se a implantação será:
        - **Necessário** (instalação obrigatória)
        - **Disponível** (usuários instalam por meio do portal da empresa, sob demanda)
        - **Não Aplicável** (o aplicativo não está instalado nem é mostrado no portal da empresa)
        - **Desinstalar** (o aplicativo é desinstalado dos dispositivos de destino)
    - **Data Limite** - Para as instalações necessárias, escolha quando implantar o aplicativo. Você pode escolher entre os valores predefinidos ou selecionar **Personalizado** para configurar seu próprio prazo.

5. Se o aplicativo que você está implantando puder ser configurado por uma política de gerenciamento de aplicativo móvel, a página **Gerenciamento de Aplicativo Móvel** será exibida. Nessa página, escolha a política de gerenciamento de aplicativo móvel que você deseja associar a esse aplicativo.

    [Veja quais aplicativos da Microsoft são compatíveis com políticas de gerenciamento de aplicativo móvel.](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx)

6. Se o aplicativo que você está implantando for compatível com perfis de VPN do Intune, a página **Perfil de VPN** será exibida. Nessa página, você pode optar por associar aplicativos iOS a um perfil de VPN implantado por você anteriormente. A conexão VPN é aberta automaticamente quando o aplicativo é iniciado. Para disponibilizar um perfil VPN, ele deve ter a configuração de perfil **VPN por aplicativo** habilitada.
 Para obter informações sobre como configurar perfis VPN, incluindo informações sobre como associar perfis a aplicativos, consulte [Conexões VPN no Microsoft Intune](vpn-connections-in-microsoft-intune.md).

<!---
>[!TIP]
>If an end user previously installed an iOS app and you now deploy it with a deployment action of **Available**, Intune will automatically begin to manage that app with no further action required by you, or the end-user.
--->

## <a name="example"></a>Exemplo

Neste exemplo, você implantou o aplicativo como **Disponível** em um dispositivo iOS.
O aplicativo é exibido em dispositivos dos usuários no portal da empresa e os usuários podem instalá-lo de lá.

Por exemplo, nesta captura de tela, o Bing para aplicativo iOS foi implantado usando o tipo de instalação **link externo** com um ícone personalizado. A opção **Exibir como um aplicativo em destaque e realçá-lo no portal de empresa** foi selecionada.  
![Aplicativo disponível para iOS](./media/available-install-on-iOS.png)

Se você implantou o aplicativo como **Necessário** em um dispositivo iOS, o usuário receberá uma notificação de que um aplicativo está pronto para ser instalado. Por exemplo, nesta captura de tela, o aplicativo Pastas de Trabalho para iOS foi implantado usando o tipo de instalação **Aplicativo iOS gerenciado da loja de aplicativos**.  
![Aplicativo necessário para iOS](./media/iOS-Required-install.PNG)

## <a name="next-steps"></a>Próximas etapas

Depois de implantar um aplicativo, você vai querer monitorar seu andamento. Para obter mais informações, consulte [Monitor apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md) (Monitorar aplicativos no Microsoft Intune).
