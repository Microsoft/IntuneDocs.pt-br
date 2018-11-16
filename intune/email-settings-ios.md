---
title: Configurações de email para dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
description: Crie um perfil de email de configuração de dispositivo que usa os servidores Exchange e recupera atributos do Azure Active Directory. Você também pode habilitar SSL, autenticar usuários com certificados ou nome de usuário/senha e sincronizar o email em dispositivos iOS usando o Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a6fd10ab6a1e9dd7249e2ae1d4bf558d190276ed
ms.sourcegitcommit: b0ee8626191961dc07f9f7f9d8e6a5fb09c63350
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51505871"
---
# <a name="email-profile-settings-for-ios-devices---intune"></a>Configurações de perfil de email para dispositivos iOS – Intune

Use as configurações de perfil de email para configurar os dispositivos que executam iOS.

> [!IMPORTANT]
> Estamos fazendo algumas melhorias no recurso S/MIME descrito neste artigo. Como resultado, o recurso S/MIME foi temporariamente removido do Intune. Quando este recurso for liberado, removeremos esta nota.

## <a name="email-settings"></a>Configurações de email

- **Servidor de email**: insira o nome do host do servidor Exchange.
- **Nome da conta**: insira o nome de exibição da conta de email. Esse nome é exibido aos usuários em seus dispositivos.
- **Atributo de nome de usuário do AAD**: esse nome é o atributo que o Intune obtém do AAD (Azure Active Directory). O Intune gera dinamicamente o nome de usuário que é usado por esse perfil. Suas opções:
  - **Nome UPN**: obtém o nome, como `user1` ou `user1@contoso.com`
  - **Endereço SMTP primário**: obtém o nome no formato de endereço de email, como `user1@contoso.com`
  - **Nome da conta sAM**: requer o domínio, como `domain\user1`.

    Insira também:  
    - **Fonte do nome de domínio do usuário**: escolha **AAD** (Azure Active Directory) ou **Personalizado**.

      Ao escolher obter os atributos do **AAD**, insira:
      - **Atributo de nome de domínio do usuário do AAD**: escolha obter o atributo **Nome de domínio completo** ou **Nome NetBIOS** do usuário

      Ao escolher usar atributos **Personalizados**, insira:
      - **Nome de domínio personalizado a ser usado**: insira um valor que o Intune usará para o nome de domínio, como `contoso.com` ou `contoso`

- **Atributo de endereço de email do AAD**: escolha como o endereço de email para o usuário é gerado. Selecione **Nome UPN** (`user1@contoso.com` ou `user1`) para usar o nome completo da entidade de segurança como o endereço de email. Selecione **Endereço SMTP primário** (`user1@contoso.com`) para usar o endereço SMTP principal para entrar no Exchange.
- **Método de autenticação**: selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email. A autenticação multifator do Azure não é compatível.
  - Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS de cliente criado anteriormente para ser usado para autenticar a conexão do Exchange.
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

- **S/MIME**: **habilite o S/MIME** para enviar emails de saída usando a autenticação S/MIME. Quando essa opção está habilitada, você também pode criptografar o email para destinatários que podem receber emails criptografados e descriptografar as mensagens de email recebidas dos remetentes.
  - Se você selecionar **Certificado**, escolha um perfil de certificado PKCS existente para autenticar a conexão do Exchange e/ou criptografar trocas de email.
- **Quantidade de emails a serem sincronizados**: escolha o número de dias de email que você deseja sincronizar. Ou selecione **Ilimitado** para sincronizar todos os emails disponíveis.
- **Permitir que as mensagens sejam movidas para outras contas de email**: **Habilitar** permite que os usuários movam mensagens de email entre contas diferentes que os usuários configuraram em seus dispositivos.
- **Permitir que o email seja enviado de aplicativos de terceiros**: **Habilitar** permite aos usuários selecionar este perfil como a conta padrão para enviar email. Ele permite que aplicativos de terceiros abram o email no aplicativo de email nativo, como anexar arquivos ao email.
- **Sincronizar endereços de email usados recentemente**: a opção **Habilitar** permite que os usuários sincronizem a lista de endereços de email usados recentemente no dispositivo com o servidor.

## <a name="next-steps"></a>Próximas etapas
[Definir as configurações de email no Intune](email-settings-configure.md)
