---
title: "Adicionar os aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS"
description: "Adicione os aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS no Console clássico do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6d762e1aed998642db66908549b2d15d54601aed
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy"></a>Adicionar os aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Você precisa usar o Intune para adicionar e implantar os aplicativos Skycure de modo que os usuários finais possam receber notificações quando uma ameaça for identificada em seus dispositivos móveis e para receber orientação para corrigir essas ameaças.

Além disso, você precisa do [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), para que os usuários possam ter suas identidades verificadas pelo Azure AD, e da política de configuração de aplicativo do iOS, que sinaliza ao aplicativo para iOS do Skycure o uso do Intune e do SSO (Logon único) do Azure AD para que os usuários não precisem digitar o nome de usuário e a senha sempre que fizerem logon no aplicativo Skycure.

## <a name="before-you-begin"></a>Antes de começar

-   As etapas a seguir devem ser concluídas no [Portal Clássico do Intune](https://manage.microsoft.com/).

-   Use a conta do Azure AD configurada anteriormente no Console de Gerenciamento do Skycure, que deve ser a mesma conta usada para entrar no Portal Clássico do Intune.

-   O arquivo de integração do Skycure precisa estar pronto para uso. Este é o arquivo .zip baixado anteriormente do console de Gerenciamento do Skycure, que contém o arquivo **skycure\_configuration.plist** com os parâmetros da política de configuração de aplicativo do iOS.

-   Verifique se que você está familiarizado com o processo de:

    -   [Adicionar um aplicativo no Intune](/intune-classic/deploy-use/add-apps).

    -   [Adicionar uma política de configuração de aplicativo do iOS no Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-the-skycure-app-for-android"></a>Para adicionar o aplicativo Skycure para Android

1.  No Portal Clássico do Intune, escolha **Aplicativos** &gt; **Adicionar Aplicativos** para iniciar o Intune Software Publisher e clique em **Avançar**.

2.  Na página **Instalação do software** escolha **Link externo** e cole a [URL do aplicativo Skycure para Android](https://play.google.com/store/apps/details?id=com.skycure.skycure) em **Especificar a URL**.

    ![Especificar a URL do Intune Software Publisher](../media/mtp/skycure-add-apps-1.png)

3.  Na página **Descrição do software**, insira o **Publicador**, o **Nome** e a **Descrição**, selecione a opção **Exibir como um aplicativo em destaque e realçá-lo no portal da empresa**, depois clique em **Avançar**.

    ![Descrição do Software do Intune Software Publisher](../media/mtp/skycure-add-apps-2.png)

4.  Clique em **Carregar** e em **Fechar**.

## <a name="to-add-the-skycure-app-for-ios"></a>Para adicionar o aplicativo Skycure para iOS

1.  No Portal Clássico do Intune, escolha **Aplicativos** &gt; **Adicionar Aplicativos** para iniciar o Intune Software Publisher e clique em **Avançar**.

2.  Na página **Configuração do Software** escolha **Aplicativo iOS gerenciado da App Store** e cole a [URL do aplicativo Skycure para iOS](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) em **Especificar a URL**.

    ![Aplicativo iOS gerenciado do Intune Software Publisher](../media/mtp/skycure-add-apps-3.png)

3.  Na página **Descrição do software**, insira o **Publicador**, o **Nome** e a **Descrição**, selecione a opção **Exibir como um aplicativo em destaque e realçá-lo no portal da empresa**, depois clique em **Avançar**.

    ![Opções do Intune Software Publisher](../media/mtp/skycure-add-apps-4.png)

4.  Na página **Requisitos**, selecione a opção **Qualquer** em **Tipo de dispositivo móvel** e clique em **Avançar**.

5.  Clique em **Carregar** e em **Fechar**.

## <a name="to-add-the-microsoft-authenticator-app-for-ios"></a>Para adicionar o aplicativo Microsoft Authenticator para iOS

1.  No Portal Clássico do Intune, escolha **Aplicativos** &gt; **Adicionar Aplicativos** para iniciar o Intune Software Publisher e clique em **Avançar**.

2.  Na página **Configuração do Software** escolha **Aplicativo iOS gerenciado da App Store** e cole a [URL do aplicativo Microsoft Authenticator para iOS](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) em **Especificar a URL**.

    ![Aplicativo iOS gerenciado do Intune Software Publisher 2](../media/mtp/skycure-add-apps-5.png)

3.  Na página **Descrição do software**, insira o **Publicador**, o **Nome** e a **Descrição**, selecione a opção **Exibir como um aplicativo em destaque e realçá-lo no portal da empresa**, depois clique em **Avançar**.

    ![Aplicativo iOS gerenciado do Intune Software Publisher 3](../media/mtp/skycure-add-apps-6.png)

4.  Na página **Requisitos**, selecione a opção **Qualquer** em **Tipo de dispositivo móvel** e clique em **Avançar**.

5.  Clique em **Carregar** e em **Fechar**.

## <a name="to-add-the-skycure-ios-app-configuration-policy"></a>Para adicionar a política de configuração de aplicativo para iOS do Skycure

1.  No Portal Clássico do Intune, escolha **Política** &gt; **Visão geral &gt; Adicionar Política**.

2.  Na lista de políticas, expanda **iOS**, escolha **Política de Configuração do Aplicativo Móvel (iOS 8.0 e posterior)**, depois escolha **Criar Política**.

    ![Política de configuração de aplicativo iOS](../media/mtp/skycure-add-apps-7.png)

3.  Na seção **Geral** da página **Criar Política**, forneça um nome e uma descrição opcional para a política de configuração de aplicativo para iOS.

    a.  Abra o arquivo **skycure\_configuration.plist** usando um editor de texto como o bloco de notas, copie o conteúdo e cole-o no corpo da **Política de Configuração de Aplicativo Móvel**, escolha **Validar** e **Salvar Política**.

       ![Política de configuração de aplicativo iOS 2](../media/mtp/skycure-add-apps-8.png)

## <a name="next-steps"></a>Próximas etapas

[Implantar os aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração de aplicativo iOS](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)
