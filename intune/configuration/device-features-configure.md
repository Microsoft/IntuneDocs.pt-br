---
title: Criar perfil de dispositivo iOS ou macOS com o Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil de dispositivo iOS ou macOS e, em seguida, defina as configurações de AirPrint, de layout da tela inicial, de notificações do aplicativo, de dispositivo compartilhado, de logon único e de filtro de conteúdo da Web no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 83328652c366eea6e1a3cbb81ea4979d8844a96b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724185"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Adicionar configurações de recursos do dispositivo iOS ou macOS no Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Intune inclui muitos recursos e configurações que ajudam os administradores a controlarem dispositivos iOS e macOS. Por exemplo, os administradores podem:

- Permitir aos usuários acesso a impressoras AirPrint em sua rede
- Adicionar aplicativos e pastas à tela inicial, incluindo a adição de novas páginas
- Escolher se, e como, as notificações de aplicativo são exibidas
- Configurar a tela de bloqueio para mostrar uma mensagem ou a marca do ativo, especialmente para dispositivos compartilhados
- Conceder aos usuários uma experiência de logon único segura para compartilhar credenciais entre aplicativos
- Filtrar sites que usem linguagem adulta e permitir ou bloquear sites específicos

O Intune usa "perfis de configuração" para criar e personalizar essas configurações de acordo com as necessidades da sua organização. Depois de adicionar esses recursos em um perfil, efetue push ou implante o perfil em dispositivos iOS e macOS em sua organização.

Este artigo descreve os diferentes recursos que você pode configurar e mostra como criar um perfil de configuração de dispositivo. Você também pode ver todas as configurações disponíveis para dispositivos [iOS](ios-device-features-settings.md) e [macOS](macos-device-features-settings.md).

## <a name="airprint"></a>AirPrint

O AirPrint é um recurso da Apple que permite que os dispositivos imprimam como arquivos usando uma rede sem fio. No Intune, você pode adicionar informações do AirPrint aos dispositivos.

Para obter uma lista das configurações possíveis no Intune, confira [AirPrint no iOS](ios-device-features-settings.md#airprint) e [AirPrint no macOS](macos-device-features-settings.md#airprint).

Para saber mais sobre o AirPrint, confira [Sobre o AirPrint](https://support.apple.com/HT201311) no site da Apple.

Aplica-se a:

- iOS 7.0 e mais recente
- iPadOS 13.0 e mais recente
- macOS 10.10 e mais recente

## <a name="app-notifications"></a>Notificações de aplicativos

Escolha como os aplicativos em seus dispositivos iOS e iPad recebem notificações. Por exemplo, no Intune, envie notificações de aplicativo para que elas apareçam no centro de notificações, sejam exibidas na tela de bloqueio ou reproduzam um som.

Para obter uma lista das configurações possíveis no Intune, confira [Notificações de aplicativo no iOS](ios-device-features-settings.md#app-notifications).

Para saber mais sobre esse recurso, confira [Notifications](https://developer.apple.com/notifications/) (Notificações) no site da Apple.

Aplica-se a:

- iOS 9.3 e mais recente
- iPadOS 13.0 e mais recente

## <a name="associated-domains"></a>Domínios associados

Os domínios associados permitem que você crie uma relação entre seus domínios, como `contoso.com`, e seus aplicativos. Esse recurso permite que você:

- Compartilhe dados e credenciais de conexão entre aplicativos e sites em sua organização.
- Use recursos de aplicativo baseados em seu site, como extensão de aplicativo de logon único, links universais e preenchimento automático de senha.

  Por exemplo, crie um domínio associado para permitir que o preenchimento automático de senha recomende credenciais, como uma senha, para sites associados ao seu aplicativo.

Para obter uma lista das configurações possíveis no Intune, confira [Domínios associados no macOS](macos-device-features-settings.md#associated-domains).

Para saber mais sobre esse recurso, confira [Setting Up an App’s Associated Domains](https://developer.apple.com/documentation/security/password_autofill/setting_up_an_app_s_associated_domains) (Configurar os domínios associados de um aplicativo) no site da Apple.

Aplica-se a:

- macOS 10.15 e mais recente

## <a name="home-screen-layout"></a>Layout da tela inicial

Essas configurações definem o layout do aplicativo e as pastas no dock e nas telas iniciais de dispositivos iOS e iPadOS. Você pode:

- Usar as configurações de **Dock** para adicionar aplicativos ou pastas à tela. Por exemplo, mostre o Safari e o aplicativo Email no dock do dispositivo.
- Adicione as **Páginas** que você deseja exibir na tela inicial e os aplicativos que aparecerão em cada página. Por exemplo, adicione uma página **Contoso** e adicione o aplicativo Configurações a essa página.

Para obter uma lista das configurações possíveis no Intune, confira [Layout da tela inicial no iOS](ios-device-features-settings.md#home-screen-layout).

Aplica-se a:

- iOS 9.3 e mais recente
- iPadOS 13.0 e mais recente

## <a name="lock-screen-message"></a>Mensagem da tela de bloqueio

Use essas configurações para mostrar uma mensagem ou um texto personalizado na janela de entrada e na tela de bloqueio. Por exemplo, insira uma mensagem "Em caso de perda, devolver a" e mostre informações da tag do ativo.

Para obter uma lista das configurações possíveis no Intune, confira [Configurações de mensagem da tela de bloqueio no iOS](ios-device-features-settings.md#lock-screen-message).

Para saber mais sobre a mensagem da tela de bloqueio, confira [LockScreenMessage](https://developer.apple.com/documentation/devicemanagement/lockscreenmessage) no site da Apple.

Aplica-se a:

- iOS 9.3 e mais recente
- iPadOS 13.0 e mais recente

## <a name="login-items"></a>Itens de logon

Use esse recurso para escolher os aplicativos, aplicativos personalizados, arquivos e pastas que serão abertos quando os usuários entrarem nos dispositivos. 

Para obter uma lista das configurações possíveis no Intune, confira [Itens de logon no macOS](macos-device-features-settings.md#login-items).

Aplica-se a:

- macOS 10.13 e mais recente

## <a name="login-window"></a>Janela de logon

Controle a aparência da tela de logon e as funções disponíveis para os usuários antes de se conectarem. Por exemplo, adicione uma faixa com uma mensagem personalizada, escolha se o botão de suspensão é mostrado e muito mais.

Para obter uma lista das configurações possíveis no Intune, confira [Janela de logon no macOS](macos-device-features-settings.md#login-window).

Aplica-se a:

- macOS 10.7 e mais recente

## <a name="single-sign-on"></a>Logon único

A maioria dos aplicativos LOB (Linha de Negócios) exigem algum nível de autenticação de usuário para dar suporte à segurança. Em muitos casos, a autenticação exige que o usuário insira as mesmas credenciais várias vezes. Para melhorar a experiência do usuário, os desenvolvedores podem criar aplicativos que usam o logon único (SSO). O logon único reduz o número de vezes que um usuário precisa inserir credenciais.

Para usar o logon único, verifique se você tem:

- um aplicativo codificado para procurar o repositório de credenciais do usuário no logon único no dispositivo.
- Intune configurado para logon único de dispositivo iOS.

![Painel de logon único](./media/device-features-configure/sso-blade.png)

Para obter uma lista das configurações possíveis no Intune, confira [Logon único no iOS](ios-device-features-settings.md#single-sign-on).

Aplica-se a:

- iOS 7.0 e mais recente
- iPadOS 13.0 e mais recente

## <a name="single-sign-on-app-extension"></a>Extensão do aplicativo de logon único

Essas configurações definem uma extensão de aplicativo que habilita o SSO (logon único) para seus dispositivos iOS, iPadOS e macOS. A maioria dos aplicativos de LOB (linha de negócios) e sites da organização exige algum nível de autenticação de usuário segura. Em muitos casos, a autenticação exige que os usuários insiram as mesmas credenciais repetidamente. O SSO dá aos usuários acesso a aplicativos e sites depois que eles inserem suas credenciais uma vez. Após a entrada, os usuários podem acessar aplicativos e sites automaticamente ou usar o Face ID, o Touch ID ou a senha da Apple para obter acesso.

No Intune, use essas configurações para definir a extensão Kerberos interna da Apple ou para configurar uma extensão do aplicativo SSO criada por sua organização. A extensão do aplicativo SSO trata da autenticação para seus usuários. Essas configurações definem as extensões de aplicativo SSO do tipo credencial, que são projetadas para fluxos de autenticação de desafio e resposta. Você pode escolher entre uma extensão de credencial específica do Kerberos fornecida pela Apple e uma extensão de credencial genérica.

Para obter uma lista das configurações possíveis no Intune, confira [Extensão de aplicativo SSO do iOS](ios-device-features-settings.md#single-sign-on-app-extension) e [Extensão de aplicativo SSO do macOS](macos-device-features-settings.md#single-sign-on-app-extension).

Para saber mais sobre como desenvolver uma extensão de aplicativo SSO, assista a [Extensible Enterprise SSO (SSO corporativo extensível)](https://developer.apple.com/videos/play/tech-talks/301) no site da Apple.

> [!NOTE]
> O recurso **Extensão de aplicativo de logon único** é diferente do recurso **Logon único**:
>
> - As configurações da **extensão de aplicativo de logon único** se aplicam ao iPadOS 13.0 (e versão mais recente) e ao iOS 13.0 (e versão mais recente). As configurações de **logon único** se aplicam ao iPadOS 13.0 (e versão mais recente) e ao iOS 7.0 (e versão mais recente).
> - Uma **Extensão de aplicativo de logon único** trata da autenticação no sistema operacional. No **Logon único**, um aplicativo específico trata da autenticação.
> - Quando usam a **Extensão de aplicativo de logon único**, os usuários entram em aplicativos e sites silenciosamente, ou com o Face ID, o Touch ID ou a senha ou o PIN da Apple. Quando usam o **Logon único**, os usuários entram em aplicativos e sites por meio de outro aplicativo.
>
>    A **Extensão de aplicativo de logon único** usa o sistema operacional da Apple para se autenticar. Portanto, ela pode fornecer uma melhor experiência do usuário final.
>
> - Do ponto de vista do desenvolvimento, a **extensão de aplicativo de logon único** pode usar qualquer tipo de autenticação SSO de credencial. Com o **Logon único**, você só pode usar a autenticação SSO do Kerberos.  

Aplica-se a:

- iOS 13.0 e mais recente
- iPadOS 13.0 e mais recente
- macOS 10.15 e mais recente

## <a name="wallpaper"></a>Papel de parede

Adicione uma imagem .png, .jpg ou .jpeg personalizada aos seus dispositivos iOS supervisionados. Por exemplo, use o Intune para adicionar um logotipo da empresa à tela de bloqueio em seus dispositivos.

Para obter uma lista das configurações possíveis no Intune, confira [Papel de parede no iOS](ios-device-features-settings.md#wallpaper).

Aplica-se a:

- iOS
- iPadOS 13.0 e mais recente

## <a name="web-content-filter"></a>Filtro de conteúdo da Web

Essas configurações podem usar o algoritmo de filtro automático interno da Apple para avaliar páginas da Web e bloquear conteúdo e linguagem adultos. Você também pode criar uma lista de links da Web permitidos e restritos. Por exemplo, você pode permitir que apenas sites da `contoso` sejam abertos.

Para obter uma lista das configurações possíveis no Intune, confira [Filtro de conteúdo Web no iOS](ios-device-features-settings.md#web-content-filter).

Aplica-se a:

- iOS 7.0 e mais recente
- iPadOS 13.0 e mais recente

## <a name="create-a-device-profile"></a>Criar um perfil de dispositivo

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para a política. Nomeie suas políticas para que você possa identificá-las facilmente mais tarde. Por exemplo, um bom nome de política é **macOS: configura tela de logon**.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Escolha a plataforma dos dispositivos. Suas opções:  
        - **iOS/iPadOS**
        - **macOS**
    - **Tipo de perfil**: Selecione **Recursos do dispositivo**.

4. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Escolha sua plataforma para ver as configurações detalhadas:

    - [iOS/iPadOS](ios-device-features-settings.md)
    - [macOS](macos-device-features-settings.md)

5. Quando terminar, selecione **OK** > **Criar** para salvar suas alterações.

O perfil é criado e exibido na lista de perfis. [Atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

## <a name="next-steps"></a>Próximas etapas

Depois que o perfil é criado, ele está pronto para ser atribuído. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Exiba todas as configurações de recurso de dispositivo para dispositivos [iOS](ios-device-features-settings.md) e [macOS](macos-device-features-settings.md).