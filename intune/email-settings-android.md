---
title: Configurações de email do Android no Microsoft Intune – Azure | Microsoft Docs
description: Crie um perfil de email de configuração de dispositivo que use servidores Exchange e recupere atributos do Azure Active Directory. Habilite o SSL ou SMIME, autentique usuários com certificados ou nome de usuário/senha e sincronize emails e agendas nos dispositivos Samsung Knox do Android usando o Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 53f1c95fdbdd9d779fb339e4820a3e7000573e60
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57236899"
---
# <a name="android-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Configurações de dispositivo do Android para configurar o email, a autenticação e a sincronização no Intune

Este artigo lista e descreve as diferentes configurações de email que você pode controlar em dispositivos Samsung Knox do Android no Intune. Como parte da solução MDM (gerenciamento de dispositivo móvel), use essas configurações para definir um servidor de email, usar o SSL para criptografar emails e muito mais.

Como administrador do Intune, você pode criar e atribuir configurações de email aos dispositivos Samsung Knox Standard do Android.

Para saber mais sobre perfis de email no Intune, confira [definir as configurações de email](email-settings-configure.md).

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](email-settings-configure.md#create-a-device-profile).

## <a name="android-samsung-knox"></a>Android (Samsung KNOX)

- **Servidor de email**: insira o nome do host do servidor Exchange. Por exemplo, insira `outlook.office365.com`.
- **Nome da conta**: insira o nome de exibição da conta de email. Esse nome é exibido aos usuários em seus dispositivos.
- **Atributo de nome de usuário do AAD**: Esse nome é o atributo que o Intune obtém do Azure AD (Azure Active Directory). O Intune gera dinamicamente o nome de usuário que é usado por esse perfil. Suas opções:
  - **Nome principal de usuário**: obtém o nome, como `user1` ou `user1@contoso.com`
  - **Nome de usuário**: obtém apenas o nome, como `user1`
  - **Nome da conta sAM**: Requer o domínio, como `domain\user1`. O nome da conta sAM só é usado com dispositivos Android.

    Insira também:  
    - **Fonte de nome de domínio do usuário**: escolha **AAD** (Azure Active Directory) ou **Personalizado**.

      Ao escolher obter os atributos do **AAD**, insira:
      - **Atributo de nome de domínio do usuário do AAD**: escolha obter o atributo **Nome de domínio completo** ou o **Nome NetBIOS** do usuário

      Ao escolher usar atributos **Personalizados**, insira:
      - **Nome de domínio personalizado a ser usado**: insira um valor que o Intune usará para o nome de domínio, como `contoso.com` ou `contoso`

- **Atributo de endereço de email do AAD**: Esse nome é o atributo de email que o Intune obtém do Azure AD. O Intune gera dinamicamente o endereço de email que é usado por esse perfil. Suas opções:
  - **Nome principal de usuário**:  Use o nome principal completo, como `user1@contoso.com` ou `user1`, como o endereço de email.
  - **Endereço SMTP primário**: Use o endereço SMTP primário, como `user1@contoso.com`, para entrar no Exchange.

- **Método de autenticação**: Selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.
  - Se você selecionar **Certificado**, selecione um perfil de certificado SCEP ou PKCS de cliente que você já criou para autenticar a conexão com o Exchange.

### <a name="security-settings"></a>Configurações de segurança

- **SSL**: Use comunicação SSL (protocolo SSL) ao enviar e receber emails e se comunicar com o Exchange Server.
- **S/MIME**: Enviar email de saída usando a criptografia de S/MIME.
  - Se você selecionar **Certificado**, selecione um perfil de certificado SCEP ou PKCS de cliente que você já criou para autenticar a conexão com o Exchange.

### <a name="synchronization-settings"></a>Configurações de sincronização

- **Quantidade de emails para sincronizar**: escolha o número de dias de email que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todos os emails disponíveis.
- **Sincronizar agendamento**: selecione o agendamento para que os dispositivos sincronizem os dados do servidor Exchange. Você também pode selecionar **Conforme as mensagens chegam**, que sincroniza os dados quando eles chegam ou **Manual**, em que o usuário do dispositivo deve iniciar a sincronização.

### <a name="content-sync-settings"></a>Configurações de sincronização de conteúdo

- **Tipo de conteúdo a ser sincronizado**: Selecione os tipos de conteúdo que você deseja sincronizar aos dispositivos. **Não configurado** desabilita essa configuração. Quando definido como **Não configurado**, se um usuário final habilitar a sincronização no dispositivo, a sincronização será desabilitada novamente quando o dispositivo for sincronizado com o Intune, pois a política será reforçada. 

  Você pode sincronizar o conteúdo a seguir:  
  - **Contatos**: Escolha **Habilitar** para permitir que os usuários finais sincronizem contatos para seus dispositivos.
  - **Calendário**: Escolha **Habilitar** para permitir que os usuários finais sincronizem o calendário com seus dispositivos.
  - **Tarefas**: Escolha **Habilitar** para permitir que os usuários finais sincronizem tarefas com seus dispositivos.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

Você também pode criar perfis de email para o [Android Enterprise – perfil de trabalho](email-settings-android-enterprise.md), [iOS](email-settings-ios.md), [Windows 10 e posterior](email-settings-windows-10.md) e [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
