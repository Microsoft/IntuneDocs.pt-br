---
title: Criar perfil de dispositivo iOS ou macOS com o Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil de dispositivo iOS ou macOS e, em seguida, defina as configurações de AirPrint, de layout da tela inicial, de notificações do aplicativo, de dispositivo compartilhado, de logon único e de filtro de conteúdo da Web no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d887c7bc3c7e9ea8b6719993b5ba4909e9c18ea8
ms.sourcegitcommit: df8e2c052fafb2d5d4e9b4fcd831ae0ecf7f8d16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74992932"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Adicionar configurações de recursos do dispositivo iOS ou macOS no Intune

O Intune inclui muitos recursos e configurações que ajudam os administradores a controlarem dispositivos iOS e macOS. Por exemplo, os administradores podem:

- Permitir aos usuários acesso a impressoras AirPrint em sua rede
- Adicionar aplicativos e pastas à tela inicial, incluindo a adição de novas páginas
- Escolher se, e como, as notificações de aplicativo são exibidas
- Configurar a tela de bloqueio para mostrar uma mensagem ou a marca do ativo, especialmente para dispositivos compartilhados
- Conceder aos usuários uma experiência de logon único segura para compartilhar credenciais entre aplicativos
- Filtrar sites que usem linguagem adulta e permitir ou bloquear sites específicos

O Intune usa "perfis de configuração" para criar e personalizar essas configurações de acordo com as necessidades da sua organização. Após adicionar esses recursos em um perfil, efetue o push ou implante o perfil em dispositivos iOS e macOS em sua organização.

Este artigo descreve os diferentes recursos que você pode configurar e mostra como criar um perfil de configuração de dispositivo. Você também pode ver todas as configurações disponíveis para dispositivos [iOS](ios-device-features-settings.md) e [macOS](macos-device-features-settings.md).

## <a name="airprint"></a>AirPrint

O AirPrint é um recurso da Apple que possibilita que os dispositivos imprimam para arquivos usando uma rede sem fio. No Intune, é possível adicionar informações do AirPrint aos dispositivos.

Para obter uma lista das configurações possíveis no Intune, confira [AirPrint no iOS](ios-device-features-settings.md#airprint) e [AirPrint no macOS](macos-device-features-settings.md#airprint).

Para saber mais sobre o AirPrint, confira [Sobre o AirPrint](https://support.apple.com/HT201311) no site da Apple.

Aplica-se a:

- iOS 7.0 e versões mais recentes
- iPadOS 13.0 e versões mais recentes
- macOS 10.10 e versões mais recentes

## <a name="app-notifications"></a>Notificações de aplicativos

Escolha como os aplicativos em seus dispositivos iOS e iPad recebem notificações. Por exemplo, no Intune, envie notificações de aplicativo para que elas apareçam na Central de Notificações, sejam exibidas na tela de bloqueio ou reproduzam um som.

Para obter uma lista das configurações possíveis no Intune, confira [Notificações de aplicativo no iOS](ios-device-features-settings.md#app-notifications).

Para saber mais sobre esse recurso, confira [Notifications](https://developer.apple.com/notifications/) (Notificações) no site da Apple.

Aplica-se a:

- iOS 9.3 e versões mais recentes
- iPadOS 13.0 e versões mais recentes

## <a name="associated-domains"></a>Domínios associados

Os domínios associados possibilitam que você crie uma relação entre seus domínios, como `contoso.com`, e seus aplicativos. Esse recurso permite que você:

- Compartilhe dados e credenciais de conexão entre aplicativos e sites em sua organização.
- Use recursos de aplicativo baseados em seu site, como extensão de aplicativo de logon único, links universais e preenchimento automático de senha.

  Por exemplo, crie um domínio associado para permitir que o preenchimento automático de senha recomende credenciais, como uma senha, para sites associados ao seu aplicativo.

Para obter uma lista das configurações possíveis no Intune, confira [Domínios associados no macOS](macos-device-features-settings.md#associated-domains).

Para saber mais sobre esse recurso, confira [Setting Up an App’s Associated Domains](https://developer.apple.com/documentation/security/password_autofill/setting_up_an_app_s_associated_domains) (Configurar os domínios associados de um aplicativo) no site da Apple.

Aplica-se a:

- macOS 10.15 e mais recente

## <a name="home-screen-layout"></a>Layout da tela inicial

Essas configurações definem o layout do aplicativo e as pastas no dock e nas telas iniciais de dispositivos iOS e iPadOS. Você pode:

- Use as configurações de **Dock** para adicionar aplicativos ou pastas à tela. Por exemplo, mostre o Safari e o aplicativo Mail no dock do dispositivo.
- Adicione as **Páginas** que você deseja exibir na tela inicial, e os aplicativos que aparecerão em cada página. Por exemplo, adicione uma página **Contoso** e adicione o aplicativo Ajustes a essa página.

Para obter uma lista das configurações possíveis no Intune, confira [Layout da tela inicial no iOS](ios-device-features-settings.md#home-screen-layout).

Aplica-se a:

- iOS 9.3 e versões mais recentes
- iPadOS 13.0 e versões mais recentes

## <a name="lock-screen-message"></a>Mensagem da tela de bloqueio

Use essas configurações para mostrar uma mensagem ou um texto personalizado na janela de entrada e na tela de bloqueio. Por exemplo, insira uma mensagem "Em caso de perda, devolver a..." e mostre informações da tag do ativo.

Para obter uma lista das configurações possíveis no Intune, confira [Configurações de mensagem da tela de bloqueio no iOS](ios-device-features-settings.md#lock-screen-message).

Para saber mais sobre a mensagem da tela de bloqueio, confira [LockScreenMessage](https://developer.apple.com/documentation/devicemanagement/lockscreenmessage) no site da Apple.

Aplica-se a:

- iOS 9.3 e versões mais recentes
- iPadOS 13.0 e versões mais recentes

## <a name="login-items"></a>Itens de logon

Use esse recurso para escolher os aplicativos, aplicativos personalizados, arquivos e pastas que abrem quando os usuários entram nos dispositivos.

Para obter uma lista das configurações possíveis no Intune, confira [Itens de logon no macOS](macos-device-features-settings.md#login-items).

Aplica-se a:

- macOS 10.13 e versões mais recentes

## <a name="login-window"></a>Janela de logon

Controle a aparência da tela de logon e as funções disponíveis para os usuários antes de se conectarem. Por exemplo, adicione uma faixa com uma mensagem personalizada, escolha se o botão de suspensão é exibido e muito mais.

Para obter uma lista das configurações possíveis no Intune, confira [Janela de logon no macOS](macos-device-features-settings.md#login-window).

Aplica-se a:

- macOS 10.7 e versões mais recentes

## <a name="single-sign-on"></a>Logon único

A maioria dos aplicativos LOB (Linha de Negócios) exigem algum nível de autenticação de usuário para dar suporte à segurança. Em muitos casos, a autenticação exige que o usuário insira as mesmas credenciais várias vezes. Para melhorar a experiência do usuário, os desenvolvedores podem criar aplicativos que usam o logon único (SSO). O logon único reduz o número de vezes que um usuário precisa inserir credenciais.

Para usar o logon único, verifique se você tem:

- um aplicativo codificado para procurar o repositório de credenciais do usuário no logon único no dispositivo.
- Intune configurado para logon único de dispositivo iOS.

![Painel de logon único](./media/device-features-configure/sso-blade.png)

Para obter uma lista das configurações possíveis no Intune, confira [Logon único no iOS](ios-device-features-settings.md#single-sign-on).

Aplica-se a:

- iOS 7.0 e versões mais recentes
- iPadOS 13.0 e versões mais recentes

## <a name="single-sign-on-app-extension"></a>Extensão do aplicativo de logon único

Essas configurações definem uma extensão de aplicativo que habilita o SSO (logon único) para seus dispositivos iOS, iPadOS e macOS. A maioria dos aplicativos de linha de negócios e sites da organização exige algum nível de autenticação de usuário segura. Em muitos casos, a autenticação exige que os usuários insiram as mesmas credenciais repetidamente. Com o SSO, aos usuários podem acessar aplicativos e sites após inserirem suas credenciais uma vez. Após a entrada, os usuários podem acessar aplicativos e sites automaticamente ou usar o Face ID, o Touch ID ou a senha da Apple para obter acesso.

No Intune, use essas configurações para definir uma extensão de aplicativo de SSO criada por sua organização, seu provedor de identidade ou pela Apple. A extensão de aplicativo de SSO lida com a autenticação para seus usuários. Essas configurações definem as extensões de aplicativo de SSO do tipo de redirecionamento e do tipo de credencial.

- O tipo de redirecionamento é projetado para protocolos de autenticação modernos, como OAuth e SAML2.
- O tipo de credencial é projetado para fluxos de autenticação de desafio e resposta. Você pode escolher entre uma extensão de credencial específica do Kerberos fornecida pela Apple e uma extensão de credencial genérica.

Para obter uma lista das configurações possíveis no Intune, confira [Extensão de aplicativo SSO do iOS](ios-device-features-settings.md#single-sign-on-app-extension) e [Extensão de aplicativo SSO do macOS](macos-device-features-settings.md#single-sign-on-app-extension).

Para saber mais sobre como desenvolver uma extensão de aplicativo de SSO, assista a [SSO corporativo extensível](https://developer.apple.com/videos/play/tech-talks/301) no site da Apple. Para ler a descrição da Apple do recurso, visite [Configurações de conteúdo das extensões de logon único](https://support.apple.com/guide/mdm/single-sign-on-extensions-mdmfd9cdf845/web). 

> [!NOTE]
> O recurso **Extensão de aplicativo de logon único** é diferente do recurso **Logon único**:
>
> - As configurações da **Extensão de aplicativo de logon único** aplicam-se ao iPadOS 13.0 (e mais recente), ao iOS 13.0 (e mais recente) e ao macOS 10.15 (e mais recente). As configurações de **logon único** aplicam-se ao iPadOS 13.0 (e versões mais recentes) e ao iOS 7.0 (e versões mais recentes).
>
> - As configurações da **Extensão de aplicativo de logon único** definem extensões para uso por provedores de identidade ou organizações para fornecer uma experiência de logon empresarial perfeita. As configurações de **logon único** definem as informações de conta do Kerberos para quando os usuários acessam servidores ou aplicativos.
>
> - A **Extensão de aplicativo de logon único** usa o sistema operacional da Apple para se autenticar. Portanto, ela pode fornecer uma experiência do usuário final melhor do que aquela de **logon único**.
>
> - Do ponto de vista do desenvolvimento, com a **Extensão de aplicativo de logon único**, você pode usar qualquer tipo de SSO de credencial ou de redirecionamento. Com o **Logon único**, você só pode usar a autenticação SSO do Kerberos.
>
> - A **Extensão de aplicativo de logon único** do Kerberos foi desenvolvida pela Apple e é interna nas plataformas iOS 13.0 e posterior e macOS 10.15 e posterior. A extensão interna do Kerberos pode ser usada para registrar os usuários em log em aplicativos nativos e sites que dão suporte à autenticação Kerberos. O **logon único** não é uma implementação do Kerberos oferecida pela Apple.
>
> - A **Extensão de aplicativo de logon único** interna do Kerberos processa os desafios do Kerberos para páginas da Web e aplicativos, assim como o **logon único**. No entanto, a extensão interna do Kerberos dá suporte a alterações de senha e apresenta um comportamento melhor em redes corporativas. Ao decidir entre a **extensão de aplicativo de logon único** do Kerberos e o **logon único**, recomendamos o uso da extensão, devido às funcionalidades e ao desempenho aprimorados.

Aplica-se a:

- iOS 13.0 e mais recente
- iPadOS 13.0 e versões mais recentes
- macOS 10.15 e mais recente

## <a name="wallpaper"></a>Papel de parede

Adicione uma imagem .png, .jpg ou .jpeg personalizada aos seus dispositivos iOS supervisionados. Por exemplo, use o Intune para adicionar um logotipo da empresa à tela de bloqueio em seus dispositivos.

Para obter uma lista das configurações possíveis no Intune, confira [Papel de parede no iOS](ios-device-features-settings.md#wallpaper).

Aplica-se a:

- iOS
- iPadOS 13.0 e versões mais recentes

## <a name="web-content-filter"></a>Filtro de conteúdo da Web

Essas configurações podem usar o algoritmo de Filtro Automático interno da Apple para avaliar páginas da Web e bloquear conteúdo e linguagem adultos. Também é possível criar uma lista de links da Web permitidos e restritos. Por exemplo, você pode permitir apenas a abertura de sites da `contoso`.

Para obter uma lista das configurações possíveis no Intune, confira [Filtro de conteúdo Web no iOS](ios-device-features-settings.md#web-content-filter).

Aplica-se a:

- iOS 7.0 e versões mais recentes
- iPadOS 13.0 e versões mais recentes

## <a name="create-a-device-profile"></a>Criar um perfil de dispositivo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para a política. Nomeie suas políticas para que você possa identificá-las facilmente mais tarde. Por exemplo, um bom nome de política é **macOS: configurar tela de logon**.
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
