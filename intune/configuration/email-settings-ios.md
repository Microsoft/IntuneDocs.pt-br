---
title: Definir configurações de email para dispositivos iOS/iPadOS no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações de email que você pode definir e adicionar a dispositivos iOS e iPadOS no Microsoft Intune, incluindo o uso de servidores Exchange e a obtenção de atributos do Azure Active Directory. Você também pode habilitar o SSL, autenticar usuários com certificados ou nome de usuário/senha e sincronizar o email em dispositivos iOS/iPadOS usando perfis de configuração do dispositivo no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0ea06c50b1da237d4a822e80a8085b3b51913cec
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512799"
---
# <a name="add-e-mail-settings-for-ios-and-ipados-devices-in-microsoft-intune"></a>Adicionar configurações de email para dispositivos iOS e iPadOS no Microsoft Intune

No Microsoft Intune, você pode criar e configurar o email para se conectar a um servidor de email, escolher como os usuários são autenticados, usar o S/MIME para criptografia, entre outros.

Este artigo lista e descreve todas as configurações de email disponíveis para dispositivos que executam o iOS/iPadOS. Você pode criar um perfil de configuração do dispositivo para efetuar push ou implantar essas configurações de email nos dispositivos iOS/iPadOS.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](../email-settings-configure.md).

> [!NOTE]
> Essas configurações estão disponíveis para todos os tipos de registro. Para obter mais informações sobre os tipos de registro, confira [Registro do iOS/iPadOS](../ios-enroll.md).

## <a name="exchange-activesync-account-settings"></a>Configurações de conta do Exchange ActiveSync

- **Servidor de email**: insira o nome do host do servidor Exchange.
- **Nome da conta**: insira o nome de exibição da conta de email. Esse nome é exibido aos usuários em seus dispositivos.
- **Atributo de nome de usuário do AAD**: esse nome é o atributo que o Intune obtém do AAD (Azure Active Directory). O Intune gera dinamicamente o nome de usuário que é usado por esse perfil. Suas opções:
  - **Nome principal de usuário**: obtém o nome, como `user1` ou `user1@contoso.com`
  - **Endereço SMTP primário**: Obtém o nome no formato de endereço de email, como `user1@contoso.com`
  - **Nome da conta sAM**: Requer o domínio, como `domain\user1`. Insira também:  
    - **Fonte de nome de domínio do usuário**: escolha **AAD** (Azure Active Directory) ou **Personalizado**.
      - **AAD**: obtenha os atributos do Azure AD. Insira também:
        - **Atributo de nome de domínio do usuário do AAD**: opte por obter o atributo **Nome de domínio completo** (`contoso.com`) ou **Nome NetBIOS** (`contoso`) do usuário.

      - **Personalizado**: obtenha os atributos de um nome de domínio personalizado. Insira também:
        - **Nome de domínio personalizado a ser usado**: insira um valor que o Intune usará para o nome de domínio, como `contoso.com` ou `contoso`.

- **Atributo de endereço de email do AAD**: escolha como o endereço de email do usuário é gerado. Suas opções:
  - **Nome principal do usuário**: use o nome completo da entidade de segurança, como `user1@contoso.com` ou `user1`, como o endereço de email.
  - **Endereço SMTP primário**: use o endereço SMTP primário, como `user1@contoso.com`, para entrar no Exchange.
- **Método de autenticação**: escolha como os usuários são autenticados no servidor de email. Suas opções:
  - **Certificado**: selecione um perfil de certificado SCEP ou PKCS de cliente criado anteriormente para autenticar a conexão do Exchange. Essa opção fornece a experiência mais segura e direta para seus usuários.
  - **Nome de usuário e senha**: é solicitado que os usuários insiram seu nome de usuário e senha.
  - **Credencial derivada**: use um certificado derivado do cartão inteligente de um usuário. Para obter mais informações, confira [Usar credenciais derivadas no Microsoft Intune](../protect/derived-credentials.md).

  >[!NOTE]
  > A autenticação multifator do Azure não é compatível.
  
- **SSL**: A opção **Habilitar** usa a comunicação do protocolo SSL ao enviar e receber emails e ao se comunicar com o Exchange Server.
- **OAuth**: A opção **Habilitar** usa a comunicação do OAuth (Open Authorization) ao enviar e receber emails e ao se comunicar com o Exchange. Se o servidor OAuth usa a autenticação de certificado, escolha **Certificado** como o **Método de autenticação** e inclua o certificado com o perfil. Caso contrário, escolha **Nome de usuário e senha** como o **Método de autenticação**. Ao usar o OAuth, certifique-se de:

  - Confirmar se sua solução de email é compatível com OAuth antes de direcionar esse perfil para seus usuários. O Office 365 Exchange Online é compatível com o OAuth. O Exchange local e outras soluções de parceiros ou terceiros podem não ser compatíveis com o OAuth. O Exchange local pode ser configurado para Autenticação Moderna (confira a postagem no blog [Announcing Hybrid Modern Authentication for Exchange On-Premises](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/) (Anunciando a Autenticação Moderna Híbrida para Exchange local)).

    Se o perfil de email usa Oauth e o serviço de email não é compatível com ele, a opção **Digitar Senha Novamente** aparece quebrada. Por exemplo, nada acontece quando o usuário seleciona **Digitar Senha Novamente** nas configurações de dispositivo da Apple.

  - Quando o OAuth está habilitado, os usuários finais têm uma experiência de entrada de email de “Autenticação Moderna” diferente compatível com a MFA (autenticação multifator). 

  - Algumas organizações desabilitam a capacidade do usuário final realizar o [acesso a aplicativo de autoatendimento](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access). Nesse cenário, a entrada de Autenticação Moderna pode falhar até um Administrador criar o aplicativo empresarial “Contas do iOS” e conceder aos usuários o acesso ao aplicativo no Azure AD.

    A ação padrão é adicionar um aplicativo usando o recurso [Painel de Acesso do Aplicativo](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **Adicionar Aplicativo** **sem aprovação de negócios**. Para obter mais informações, confira [atribuir usuários aos aplicativos](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > Quando você habilita o OAuth, acontece o seguinte:  
  > 1. Os dispositivos já direcionados recebem um novo perfil.
  > 2. Os usuários finais devem inserir suas credenciais novamente.

## <a name="exchange-activesync-profile-configuration"></a>Configuração de perfil do Exchange ActiveSync

> [!IMPORTANT]
> Definir essas configurações implanta um novo perfil no dispositivo, mesmo quando um perfil de email existente é atualizado para incluir essas configurações. É solicitado que os usuários insiram a senha de sua conta do Exchange ActiveSync. Essas configurações entram em vigor quando a senha é inserida.

- **Dados do Exchange a serem sincronizados**: ao usar o Exchange ActiveSync, escolha os serviços do Exchange que são sincronizados no dispositivo: Calendário, Contatos, Lembretes, Anotações e Email. Suas opções:
  - **Todos os dados** (padrão): a sincronização é habilitada para todos os serviços.
  - **Somente email**: a sincronização é habilitada somente para o Email. A sincronização fica desabilitada para os outros serviços.
  - **Somente calendário**: a sincronização é habilitada somente para o Calendário. A sincronização fica desabilitada para os outros serviços.
  - **Somente Calendário e Contatos**: a sincronização é habilitada somente para o Calendário e os Contatos. A sincronização fica desabilitada para os outros serviços.
  - **Somente Contatos**: a sincronização é habilitada somente para os Contatos. A sincronização fica desabilitada para os outros serviços.

  Esse recurso aplica-se a:  
  - iOS 13.0 e mais recente
  - iPadOS 13.0 e versões mais recentes

- **Permitir que os usuários alterem as configurações de sincronização**: escolha se os usuários podem alterar as configurações do Exchange ActiveSync para os serviços do Exchange no dispositivo: Calendário, Contatos, Lembretes, Anotações e Email. Suas opções:

  - **Sim** (padrão): os usuários podem alterar o comportamento de sincronização de todos os serviços. Escolher **Sim** permite alterações em *todos* os serviços.
  - **Não**: os usuários não podem alterar as configurações de sincronização de todos os serviços. Escolher **Não** impede alterações em *todos* os serviços.

  > [!TIP]
  > Se você tiver definido a configuração **Dados do Exchange a serem sincronizados** para sincronizar apenas alguns serviços, recomendamos selecionar **Não** para essa configuração. Escolher **Não** impede que os usuários alterem o serviço do Exchange que é sincronizado.

  Esse recurso aplica-se a:  
  - iOS 13.0 e mais recente
  - iPadOS 13.0 e versões mais recentes

## <a name="exchange-activesync-email-settings"></a>Configurações de email do Exchange ActiveSync

- **S/MIME**: S/MIME usa certificados de email que fornecem segurança extra para suas comunicações por email com assinatura, criptografia e descriptografia. Ao usar o S/MIME com uma mensagem de email, você confirma a autenticidade do remetente, bem como a integridade e a confidencialidade da mensagem.

  Suas opções:

  - **Desabilitar S/MIME** (padrão): não usa um certificado de email S/MIME para assinar, criptografar ou descriptografar emails.
  - **Habilitar S/MIME**: permite que os usuários entrem e/ou criptografem emails no aplicativo de email nativo do iOS/iPadOS. Insira também:

    - **Autenticação S/MIME habilitada**: **Desabilitar** (padrão) não permite que os usuários assinem a mensagem digitalmente. **Habilitar** permite que os usuários assinem digitalmente um email de saída para a conta que você inseriu. A assinatura ajuda os usuários que recebem mensagens a ter certeza de que a mensagem é proveniente do remetente específico, não de alguém que finge ser o remetente.
      - **Permitir que o usuário altere a configuração**: **Habilitar** permite que os usuários alterem as opções de assinatura. **Desabilitar** (padrão) impede que os usuários alterem a assinatura e os obriga a usar a assinatura configurada.
      - **Tipo de certificado de autenticação**: suas opções:
        - **Não configurado**: o Intune não atualiza nem altera essa configuração.
        - **Nenhum**: como administrador, você não força um certificado específico. Selecione essa opção para que os usuários possam escolher seu próprio certificado.
        - **Credencial derivada**: use um certificado derivado do cartão inteligente de um usuário. Para obter mais informações, confira [Usar credenciais derivadas no Microsoft Intune](../protect/derived-credentials.md).
        - **Certificados**: Selecione um perfil de certificado PKCS ou SCEP existente que é usado para assinar mensagens de email.
      - **Permitir que o usuário altere a configuração**: **Habilitar** permite que os usuários alterem o certificado de autenticação. **Desabilitar** (padrão) impede que os usuários alterem o certificado de autenticação e força os usuários a usar o certificado configurado.

        Esse recurso aplica-se a:  
        - iOS 12 e versões mais recentes
        - iPadOS 12 e versões mais recentes

    - **Criptografar por padrão**: A opção **Habilitar** criptografa todas as mensagens como o comportamento padrão. **Desabilitar** (padrão) não criptografa todas as mensagens como o comportamento padrão.
      - **Permitir que o usuário altere a configuração**: **Habilitar** permite que os usuários alterem o comportamento de criptografia padrão. **Desabilitar** impede que os usuários alterem o comportamento padrão de criptografia e força os usuários a usar a configuração definida.

        Esse recurso aplica-se a:  
        - iOS 12 e versões mais recentes
        - iPadOS 12 e versões mais recentes

    - **Forçar criptografia por mensagem**: A criptografia por mensagem permite que os usuários escolham quais emails serão criptografados antes de serem enviados.

      **Habilitar** mostra a opção de criptografia por mensagem durante a criação de um email. Os usuários podem optar por aceitar ou recusar a criptografia por mensagem. Se a configuração **Criptografar por padrão** estiver habilitada, a habilitação da criptografia por mensagem permitirá que os usuários recusem a criptografia por mensagem.

      **Desabilitar** (padrão) impede a exibição da opção de criptografia por mensagem. Se a configuração **Criptografar por padrão** também estiver desabilitada, a habilitação da criptografia por mensagem permitirá que os usuários aceitem a criptografia por mensagem.

      - **Tipo de certificado de criptografia**: suas opções:
        - **Não configurado**: o Intune não atualiza nem altera essa configuração.
        - **Nenhum**: como administrador, você não força um certificado específico. Selecione essa opção para que os usuários possam escolher seu próprio certificado.
        - **Credencial derivada**: use um certificado derivado do cartão inteligente de um usuário. Para obter mais informações, confira [Usar credenciais derivadas no Microsoft Intune](../protect/derived-credentials.md).
        - **Certificados**: Selecione um perfil de certificado PKCS ou SCEP existente que é usado para assinar mensagens de email.
      - **Permitir que o usuário altere a configuração**: **Habilitar** permite que os usuários alterem o certificado de criptografia. **Desabilitar** (padrão) impede que os usuários alterem o certificado de criptografia e força os usuários a usar o certificado configurado.

        Esse recurso aplica-se a:  
        - iOS 12 e versões mais recentes
        - iPadOS 12 e versões mais recentes

- **Quantidade de emails para sincronizar**: Escolha o número de dias de emails que deseja sincronizar. Ou selecione **Ilimitado** para sincronizar todos os emails disponíveis.
- **Permitir que as mensagens sejam movidas para outras contas de email**: **Habilitar** (padrão) permite que os usuários movam mensagens de email entre contas diferentes configuradas em seus dispositivos.
- **Permitir que os emails sejam enviados de aplicativos de terceiros**: **Habilitar** (padrão) permite que os usuários selecionem este perfil como a conta padrão para envio de emails. Ele permite que aplicativos de terceiros abram o email no aplicativo de email nativo, como anexar arquivos ao email.
- **Sincronizar endereços de email usados recentemente**: **Habilitar** (padrão) permite que os usuários sincronizem a lista de endereços de email usados recentemente no dispositivo com o servidor.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](../device-profile-assign.md) e [monitore seu status](../device-profile-monitor.md).

Defina configurações de email em dispositivos [Android](../email-settings-android.md), [Android Enterprise](../email-settings-android-enterprise.md), [Windows 10](email-settings-windows-10.md) e [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
