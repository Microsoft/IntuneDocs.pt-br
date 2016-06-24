---
# required metadata

title: Implantar aplicativos | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
---
# Implantar aplicativos no Microsoft Intune

Use as informações neste tópico para ajudá-lo a implantar aplicativos no Microsoft Intune.


## Implantar um aplicativo
Neste procedimento, você implantará o aplicativo para os usuários ou dispositivos selecionados.

### Para implantar um aplicativo

1. No [Console do administrador do Microsoft Intune](https://manage.microsoft.com), clique em **Aplicativos** &gt; **Aplicativos** para exibir a lista dos aplicativos gerenciados por você.

2.  Selecione o aplicativo que deseja implantar e clique em **Gerenciar Implantação**.

3.  Na caixa de diálogo *&lt;nome do aplicativo&gt;*, primeiro, na página **Selecionar Grupos** página, escolha os grupos de usuário ou dispositivos para os quais você deseja implantar o aplicativo.

4.  Na página **Ação de Implantação**, configure o seguinte:

    - **Aprovação** - Escolha se a implantação será:
        - **Necessário** (instalação obrigatória)
        - **Disponível** (usuários instalam por meio do portal da empresa, sob demanda)
        - **Não Aplicável** (o aplicativo não está instalado nem é mostrado no portal da empresa)
        - **Desinstalar** (o aplicativo será desinstalado dos dispositivos de destino),
    - **Data Limite** - Para as instalações necessárias, escolha quando o aplicativo será implantado. Você pode escolher entre os valores predefinidos ou selecionar **Personalizado** para configurar seu próprio prazo.

5. Se o aplicativo que você está implantando puder ser configurado por uma política de gerenciamento de aplicativo móvel, a página **Gerenciamento de Aplicativo Móvel** será exibida. Nessa página, escolha a política de gerenciamento de aplicativo móvel que você deseja associar a esse aplicativo.

    [Veja quais aplicativos da Microsoft são compatíveis com políticas de gerenciamento de aplicativo móvel.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. Se o aplicativo que você está implantando for compatível com perfis de VPN do Intune, a página **Perfil de VPN** será exibida. Nessa página, você pode optar por associar aplicativos iOS a um perfil de VPN implantado por você anteriormente. A conexão VPN será aberta automaticamente quando o aplicativo for iniciado. Para disponibilizar um perfil VPN, ele deve ter a configuração de perfil **VPN por aplicativo** habilitada.
 Para obter informações sobre como configurar perfis de VPN, incluindo suporte para associar perfis de aplicativos, consulte [Help users connect to their work using VPN profiles with Microsoft Intune](vpn-connections-in-microsoft-intune.md) (Ajudar os usuários a se conectarem aos seus trabalhos usando perfis de VPN com o Microsoft Intune).

## Exemplo

Neste exemplo, você implantou o aplicativo como **Disponível** em um dispositivo iOS.
O aplicativo será exibido no portal da empresa no dispositivo dos usuários, de onde eles poderão instalar o aplicativo. Por exemplo, nesta captura de tela, o aplicativo Bing para iOS foi implantado usando o tipo de instalação **Link Externo** com um ícone personalizado e a opção **Exibir como um aplicativo em destaque e realçá-lo no portal de empresa** foi selecionado.
    ![Aplicativo disponível no iOS](./media/available-install-on-iOS.png)

Se você implantou o aplicativo como **Necessário** em um dispositivo iOS, o usuário receberá uma notificação de que um aplicativo está pronto para ser instalado. Por exemplo, nesta captura de tela, o aplicativo Pastas de Trabalho para iOS foi implantado usando o tipo de instalação **Aplicativo iOS gerenciado da Windows Store**.
    ![Aplicativo necessário no iOS](./media/iOS-Required-install.PNG)

## Próximas etapas

Depois de implantar um aplicativo, monitore seu andamento. Para obter mais informações, consulte [Monitor apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md) (Monitorar aplicativos no Microsoft Intune).


<!--HONumber=Jun16_HO2-->


