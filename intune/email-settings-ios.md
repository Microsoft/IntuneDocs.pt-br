---
title: Configurações de email para dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações de email que podem ser definidas e adicionadas a dispositivos iOS no Microsoft Intune, incluindo o uso de Exchange Servers e a obtenção de atributos do Azure Active Directory. Você também pode habilitar o SSL, autenticar usuários com certificados ou nome de usuário/senha e sincronizar o email em dispositivos iOS usando perfis de configuração do dispositivo no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: fd1f24c7114e21239d19ca2e99fc05d125e675d9
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55845767"
---
# <a name="email-profile-settings-for-ios-devices-in-intune"></a>Configurações de perfil de email para dispositivos iOS no Intune

No Microsoft Intune, você pode criar e configurar o email para se conectar a um servidor de email, escolher como os usuários são autenticados, usar o S/MIME para criptografia, entre outros.

Este artigo lista e descreve todas as configurações de email disponíveis para dispositivos que executam o iOS. Você pode criar um perfil de configuração do dispositivo para enviar por push ou implantar essas configurações de email nos dispositivos iOS.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](email-settings-configure.md#create-a-device-profile).

## <a name="email-settings"></a>Configurações de email

- **Servidor de email**: insira o nome do host do servidor Exchange.
- **Nome da conta**: insira o nome de exibição da conta de email. Esse nome é exibido aos usuários em seus dispositivos.
- **Atributo de nome de usuário do AAD**: esse nome é o atributo que o Intune obtém do AAD (Azure Active Directory). O Intune gera dinamicamente o nome de usuário que é usado por esse perfil. Suas opções:
  - **Nome principal de usuário**: obtém o nome, como `user1` ou `user1@contoso.com`
  - **Endereço SMTP primário**: Obtém o nome no formato de endereço de email, como `user1@contoso.com`
  - **Nome da conta sAM**: Requer o domínio, como `domain\user1`.

    Insira também:  
    - **Fonte de nome de domínio do usuário**: escolha **AAD** (Azure Active Directory) ou **Personalizado**.

      Ao escolher obter os atributos do **AAD**, insira:
      - **Atributo de nome de domínio do usuário do AAD**: escolha obter o atributo **Nome de domínio completo** ou o **Nome NetBIOS** do usuário

      Ao escolher usar atributos **Personalizados**, insira:
      - **Nome de domínio personalizado a ser usado**: insira um valor que o Intune usará para o nome de domínio, como `contoso.com` ou `contoso`

- **Atributo de endereço de email do AAD**: escolha como o endereço de email do usuário é gerado. Selecione **Nome UPN** (`user1@contoso.com` ou `user1`) para usar o nome completo da entidade de segurança como o endereço de email. Selecione **Endereço SMTP primário** (`user1@contoso.com`) para usar o endereço SMTP principal para entrar no Exchange.
- **Método de autenticação**: Selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email. A autenticação multifator do Azure não é compatível.
  - Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS de cliente criado anteriormente para ser usado para autenticar a conexão do Exchange.
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

- **S/MIME**: **Habilite o S/MIME** para permitir que os usuários assinem e/ou criptografem emails no aplicativo de email nativo do iOS. 

  Ao usar o S/MIME com uma mensagem de email, você confirma a autenticidade do remetente, bem como a integridade e a confidencialidade da mensagem.

  - **Assinatura S/MIME habilitada**: Escolha **Habilitar** para permitir que os usuários assinem digitalmente um email de saída para a conta que você inseriu. A assinatura ajuda os usuários que recebem mensagens a ter certeza de que a mensagem é proveniente do remetente específico, não de alguém que finge ser o remetente. A opção **Desabilitar** não permite que os usuários assinem digitalmente a mensagem.
    - **Permitir que o usuário altere a configuração**: Escolha **Habilitar** para permitir que os usuários alterem o comportamento da assinatura S/MIME. A opção **Desabilitar** impede que os usuários alterem a configuração de assinatura S/MIME definida. Disponível no iOS 12 e mais recente.

  - **Certificado de Assinatura S/MIME**: Selecione um perfil de certificado PKCS ou SCEP existente que é usado para assinar mensagens de email.
    - **Permitir que o usuário altere a configuração**: Escolha **Habilitar** para permitir que os usuários alterem o certificado de autenticação. A opção **Desabilitar** impede que os usuários alterem o certificado de autenticação e força os usuários a usar o certificado configurado. Disponível no iOS 12 e mais recente.

  - **Criptografar por padrão**: A opção **Habilitar** criptografa todas as mensagens como o comportamento padrão. A opção **Desabilitar** não criptografa todas as mensagens como o comportamento padrão.
    - **Permitir que o usuário altere a configuração**: Escolha **Habilitar** para permitir que os usuários alterem o comportamento padrão de criptografia. A opção **Desabilitar** impede que os usuários alterem o comportamento padrão de criptografia e força os usuários a usar a configuração definida. Disponível no iOS 12 e mais recente.

  - **Forçar criptografia por mensagem**: A criptografia por mensagem permite que os usuários escolham quais emails serão criptografados antes de serem enviados. Escolha **Habilitar** para mostrar a opção de criptografia por mensagem durante a criação de um email. Os usuários podem optar por aceitar ou recusar a criptografia por mensagem. A opção **Desabilitar** impede a exibição da opção de criptografia por mensagem.

    Se a configuração **Criptografar por padrão** estiver habilitada, a habilitação da criptografia por mensagem permitirá que os usuários recusem a criptografia por mensagem. Se a configuração **Criptografar por padrão** estiver desabilitada, a habilitação da criptografia por mensagem permitirá que os usuários aceitem a criptografia por mensagem.

  - **Certificado de Criptografia S/MIME**: Selecione um perfil de certificado PKCS ou SCEP existente que é usado para criptografar mensagens de email.
    - **Permitir que o usuário altere a configuração**: Escolha **Habilitar** para permitir que os usuários alterem o certificado de criptografia. A opção **Desabilitar** impede que os usuários alterem o certificado de criptografia e força os usuários a usar o certificado configurado. Disponível no iOS 12 e mais recente.
- **Quantidade de emails para sincronizar**: Escolha o número de dias de emails que deseja sincronizar. Ou selecione **Ilimitado** para sincronizar todos os emails disponíveis.
- **Permitir que as mensagens sejam movidas para outras contas de email**: A opção **Habilitar** permite que os usuários movam mensagens de email entre diferentes contas configuradas em seus dispositivos.
- **Permitir que os emails sejam enviados de aplicativos de terceiros**: A opção **Habilitar** permite que os usuários selecionem este perfil como a conta padrão para envio de emails. Ele permite que aplicativos de terceiros abram o email no aplicativo de email nativo, como anexar arquivos ao email.
- **Sincronizar endereços de email usados recentemente**: A opção **Habilitar** permite que os usuários sincronizem a lista de endereços de email usados recentemente no dispositivo com o servidor.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Defina configurações de email em dispositivos [Android](email-settings-android.md), [Windows 10](email-settings-windows-10.md) e [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
