---
title: Configurações de email para dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
description: Crie um perfil de email de configuração de dispositivo que usa os servidores Exchange e recupera atributos do Azure Active Directory. Você também pode habilitar SSL, autenticar usuários com certificados ou nome de usuário/senha e sincronizar o email em dispositivos iOS usando o Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2d27e90655e54051d73989202d2bc849a66208f5
ms.sourcegitcommit: 488be75cbee88455b33c68a3ec2acb864d461bf8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "41910795"
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

- **Atributo de endereço de email do AAD**: escolha como o endereço de email para o usuário é gerado. Selecione **nome UPN** (`user1@contoso.com` ou `user1`) para usar o nome da entidade completo como o endereço de email, ou **Endereço SMTP primário** (`user1@contoso.com`) para usar o endereço SMTP primário para entrar no Exchange.
- **Método de autenticação**: selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email. Não há suporte para a autenticação multifator do Azure.
  - Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS de cliente criado anteriormente para ser usado para autenticar a conexão do Exchange.
- **SSL**: **habilite** para usar a comunicação do protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.
- **S/MIME**: **habilite o S/MIME** para enviar emails de saída usando a autenticação S/MIME. Quando essa opção está habilitada, você também pode criptografar o email para destinatários que podem receber emails criptografados e descriptografar as mensagens de email recebidas dos remetentes.
  - Se você selecionou **Certificado**, selecione um perfil de certificado PKCS criado anteriormente para autenticar a conexão do Exchange e/ou criptografar trocas de email.
- **Quantidade de emails a serem sincronizados**: escolha o número de dias de email que você deseja sincronizar. Ou selecione **Ilimitado** para sincronizar todos os emails disponíveis.
- **Permitir que as mensagens sejam movidas para outras contas de email**: a opção **Habilitar** permite que os usuários movam mensagens de email entre contas diferentes configuradas em seus dispositivos.
- **Permitir o envio de email em aplicativos de terceiros**: a opção **Habilitar** permite que o usuário selecione esse perfil como a conta padrão para envio de email e permita que aplicativos de terceiros abram o email no aplicativo de email nativo, por exemplo, para anexar arquivos ao email.
- **Sincronizar endereços de email usados recentemente**: a opção **Habilitar** permite que os usuários sincronizem a lista de endereços de email usados recentemente no dispositivo com o servidor.

## <a name="next-steps"></a>Próximas etapas
[Definir as configurações de email no Intune](email-settings-configure.md)
