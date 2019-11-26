---
title: Configurar email para dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações de email que podem ser definidas e adicionadas a dispositivos iOS no Microsoft Intune, incluindo o uso de Exchange Servers e a obtenção de atributos do Azure Active Directory. Você também pode habilitar o SSL, autenticar usuários com certificados ou nome de usuário/senha e sincronizar o email em dispositivos iOS usando perfis de configuração do dispositivo no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/12/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 73de0ac94ff02e43fe73ca6357f6008ba71e3b93
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390830"
---
# <a name="add-e-mail-settings-for-ios-devices-in-microsoft-intune"></a>Adicionar configurações de email para dispositivos iOS no Microsoft Intune

No Microsoft Intune, você pode criar e configurar o email para se conectar a um servidor de email, escolher como os usuários são autenticados, usar o S/MIME para criptografia, entre outros.

Este artigo lista e descreve todas as configurações de email disponíveis para dispositivos que executam o iOS. Você pode criar um perfil de configuração do dispositivo para enviar por push ou implantar essas configurações de email nos dispositivos iOS.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](../email-settings-configure.md).

> [!NOTE]
> Essas configurações estão disponíveis para todos os tipos de registro. Para obter mais informações sobre os tipos de registro, consulte [registro do IOS](../ios-enroll.md).

## <a name="exchange-activesync-account-settings"></a>Configurações de conta do Exchange ActiveSync

- **Servidor de email**: insira o nome do host do servidor Exchange.
- **Nome da conta**: insira o nome de exibição da conta de email. Esse nome é exibido aos usuários em seus dispositivos.
- **Atributo de nome de usuário do AAD**: esse nome é o atributo que o Intune obtém do AAD (Azure Active Directory). O Intune gera dinamicamente o nome de usuário que é usado por esse perfil. Suas opções:
  - **Nome UPN**: obtém o nome, como `user1` ou `user1@contoso.com`
  - **Endereço SMTP primário**: obtém o nome no formato de endereço de email, como `user1@contoso.com`
  - **Nome da conta sAM**: requer o domínio, como `domain\user1`. Insira também:  
    - **Fonte do nome de domínio do usuário**: escolha **AAD** (Azure Active Directory) ou **Personalizado**.
      - **AAD**: obter os atributos do Azure AD. Insira também:
        - **Atributo de nome de domínio do usuário do AAD**: opte por obter o **Nome de domínio completo** (`contoso.com`) ou o **Nome NetBIOS** (`contoso`) atributo do usuário.

      - **Personalizado**: Obtenha os atributos de um nome de domínio personalizado. Insira também:
        - **Nome de domínio personalizado a ser usado**: insira um valor que o Intune usará para o nome de domínio, como `contoso.com` ou `contoso`.

- **Atributo de endereço de email do AAD**: escolha como o endereço de email para o usuário é gerado. Suas opções:
  - **Nome UPN**: use o nome completo da entidade de segurança, como o endereço de email `user1@contoso.com` ou `user1`.
  - **Endereço SMTP primário**: use o endereço SMTP principal para entrar no Exchange, tal como `user1@contoso.com`.
- **Método de autenticação**: escolha como os usuários são autenticados no servidor de email. Suas opções:
  - **Certificado**, selecione um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão do Exchange. Essa opção fornece a experiência mais segura e direta para seus usuários.
  - **Nome de usuário e senha**: os usuários são solicitados a inserir seu nome de usuários e senha.
  - **Credencial derivada**: Use um certificado derivado do cartão inteligente de um usuário. Para obter mais informações, consulte [usar credenciais derivadas no Microsoft Intune](../protect/derived-credentials.md).

  >[!NOTE]
  > A autenticação multifator do Azure não é compatível.
  
- **SSL**: **Habilitar** usa a comunicação do protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.
- **OAuth**: **Habilitar** usa a comunicação do OAuth (Open Authorization) ao enviar e receber emails e ao se comunicar com o Exchange. Se o servidor OAuth usa a autenticação de certificado, escolha **Certificado** como o **Método de autenticação** e inclua o certificado com o perfil. Caso contrário, escolha **Nome de usuário e senha** como o **Método de autenticação**. Ao usar o OAuth, certifique-se de:

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
> A definição dessas configurações implanta um novo perfil no dispositivo, mesmo quando um perfil de email existente é atualizado para incluir essas configurações. Os usuários são solicitados a inserir sua senha de conta do Exchange ActiveSync. Essas configurações são afetadas quando a senha é inserida.

- **Trocar dados a serem sincronizados**: ao usar o Exchange ActiveSync, escolha os serviços do Exchange que são sincronizados no dispositivo: calendário, contatos, lembretes, anotações e email. Suas opções:
  - **Todos os dados** (padrão): a sincronização está habilitada para todos os serviços.
  - **Somente email**: a sincronização está habilitada somente para email. A sincronização está desabilitada para os outros serviços.
  - **Somente calendário**: a sincronização está habilitada somente para calendário. A sincronização está desabilitada para os outros serviços.
  - **Somente calendário e contatos**: a sincronização está habilitada somente para calendário e contatos. A sincronização está desabilitada para os outros serviços.
  - **Somente contatos**: a sincronização está habilitada somente para contatos. A sincronização está desabilitada para os outros serviços.

  Esse recurso aplica-se a:  
  - iOS 13.0 e mais recente
  - iPadOS 13.0 e versões mais recentes

- **Permitir que os usuários alterem as configurações de sincronização**: escolha se os usuários podem alterar as configurações do Exchange ActiveSync para os serviços do Exchange no dispositivo: calendário, contatos, lembretes, anotações e email. Suas opções:

  - **Sim** (padrão): os usuários podem alterar o comportamento de sincronização de todos os serviços. Escolher **Sim** permite alterações em *todos os* serviços.
  - **Não**: os usuários não podem alterar as configurações de sincronização de todos os serviços. Escolher **nenhum** bloco muda para *todos os* serviços.

  > [!TIP]
  > Se você tiver configurado a configuração **dados do Exchange para sincronização** para sincronizar apenas alguns serviços, recomendamos selecionar **não** para essa configuração. Escolher **não** impede que os usuários alterem o serviço do Exchange sincronizado.

  Esse recurso aplica-se a:  
  - iOS 13.0 e mais recente
  - iPadOS 13.0 e versões mais recentes

## <a name="exchange-activesync-email-settings"></a>Configurações de email do Exchange ActiveSync

- **S/MIME**: s/MIME usa certificados de email que fornecem segurança extra para suas comunicações de email assinando, criptografando e descriptografando. Ao usar o S/MIME com uma mensagem de email, você confirma a autenticidade do remetente, bem como a integridade e a confidencialidade da mensagem.

  Suas opções:

  - **Desabilitar S/MIME** (padrão): não usa um certificado de email S/MIME para assinar, criptografar ou descriptografar emails.
  - **Habilitar S/MIME**: permite que os usuários entrem e/ou criptografem emails no aplicativo de correio nativo do iOS. Insira também:

    - **Assinatura S/MIME habilitada**: **desabilitar** (padrão) não permite que os usuários assinem a mensagem digitalmente. **Habilitar** permite que os usuários assinem digitalmente um email de saída para a conta que você inseriu. A assinatura ajuda os usuários que recebem mensagens a ter certeza de que a mensagem é proveniente do remetente específico, não de alguém que finge ser o remetente.
      - **Permitir que o usuário altere a configuração**: **habilitar** permite que os usuários alterem as opções de assinatura. **Desabilitar** (padrão) impede que os usuários alterem a assinatura e obriga os usuários a usar a assinatura configurada.
      - **Tipo de certificado de autenticação**: suas opções:
        - **Não configurado**: o Intune não atualiza ou altera essa configuração.
        - **Nenhum**: como administrador, você não força um certificado específico. Selecione essa opção para que os usuários possam escolher seu próprio certificado.
        - **Credencial derivada**: Use um certificado derivado do cartão inteligente de um usuário. Para obter mais informações, consulte [usar credenciais derivadas no Microsoft Intune](../protect/derived-credentials.md).
        - **Certificados**: selecione um perfil de certificado PKCS ou SCEP existente que seja usado para assinar mensagens de email.
      - **Permitir que o usuário altere a configuração**: **habilitar** permite que os usuários alterem o certificado de autenticação. **Desabilitar** (padrão) impede que os usuários alterem o certificado de autenticação e força os usuários a usar o certificado configurado.

        Esse recurso aplica-se a:  
        - iOS 12 e versões mais recentes
        - iPadOS 12 e versões mais recentes

    - **Criptografar por padrão**: **habilita** todas as mensagens como o comportamento padrão. **Desabilitar** (padrão) não criptografa todas as mensagens como o comportamento padrão.
      - **Permitir ao usuário alterar a configuração**: escolha **Habilitar** para permitir que os usuários alterem o comportamento padrão de criptografia. **Desabilitar** impede que os usuários alterem o comportamento padrão de criptografia e força os usuários a usar a configuração definida.

        Esse recurso aplica-se a:  
        - iOS 12 e versões mais recentes
        - iPadOS 12 e versões mais recentes

    - **Forçar criptografia por mensagem**: a criptografia por mensagem permite que os usuários escolham quais emails serão criptografados antes de serem enviados.

      **Habilitar** mostra a opção de criptografia por mensagem durante a criação de um email. Os usuários podem optar por aceitar ou recusar a criptografia por mensagem. Se a configuração **Criptografar por padrão** estiver habilitada, a habilitação da criptografia por mensagem permitirá que os usuários recusem a criptografia por mensagem.

      **Desabilitar** (padrão) impede a exibição da opção de criptografia por mensagem. Se a configuração **Criptografar por padrão** também estiver desabilitada, a habilitação da criptografia por mensagem permitirá que os usuários aceitem a criptografia por mensagem.

      - **Tipo de certificado de criptografia**: suas opções:
        - **Não configurado**: o Intune não atualiza ou altera essa configuração.
        - **Nenhum**: como administrador, você não força um certificado específico. Selecione essa opção para que os usuários possam escolher seu próprio certificado.
        - **Credencial derivada**: Use um certificado derivado do cartão inteligente de um usuário. Para obter mais informações, consulte [usar credenciais derivadas no Microsoft Intune](../protect/derived-credentials.md).
        - **Certificados**: selecione um perfil de certificado PKCS ou SCEP existente que seja usado para assinar mensagens de email.
      - **Permitir que o usuário altere a configuração**: escolher **Habilitar** permitirá que os usuários alterem o certificado de criptografia. **Desabilitar** (padrão) impede que os usuários alterem o certificado de criptografia e força os usuários a usar o certificado configurado.

        Esse recurso aplica-se a:  
        - iOS 12 e versões mais recentes
        - iPadOS 12 e versões mais recentes

- **Quantidade de emails a serem sincronizados**: escolha o número de dias de email que você deseja sincronizar. Ou selecione **Ilimitado** para sincronizar todos os emails disponíveis.
- **Permitir que as mensagens sejam movidas para outras contas de email**: **Habilitar** (padrão) permite que os usuários movam mensagens de email entre contas diferentes que os usuários configuraram em seus dispositivos.
- **Permitir que o email seja enviado de aplicativos de terceiros**: **Habilitar** (padrão) permite aos usuários selecionar este perfil como a conta padrão para enviar email. Ele permite que aplicativos de terceiros abram o email no aplicativo de email nativo, como anexar arquivos ao email.
- **Sincronizar endereços de email usados recentemente**: a opção **Habilitar** (padrão) permite que os usuários sincronizem a lista de endereços de email usados recentemente no dispositivo com o servidor.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](../device-profile-assign.md) e [monitore seu status](../device-profile-monitor.md).

Defina configurações de email em dispositivos [Android](../email-settings-android.md), [Android Enterprise](../email-settings-android-enterprise.md), [Windows 10](email-settings-windows-10.md)e [Windows Phone 8,1](email-settings-windows-phone-8-1.md) .
