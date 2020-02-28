---
title: Configurações de email do Android Enterprise no Microsoft Intune – Azure | Microsoft Docs
description: Crie perfis de email de configuração de dispositivo que use servidores Exchange e recupere atributos do Azure Active Directory. Habilite o SSL ou SMIME, autentique usuários com certificados ou nome de usuário/senha e sincronize emails e agendas nos dispositivos de perfil de trabalho do Android usando o Microsoft Intune.
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
ms.reviewer: maholdaa
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 978ddf279dc221a56fddaf99da4dbb2377a93c24
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511146"
---
# <a name="android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Configurações de dispositivo do Android Enterprise para configurar o email, a autenticação e a sincronização no Intune



Este artigo lista e descreve as diferentes configurações de email que você pode controlar em dispositivos Android Enterprise. Como parte da solução MDM (gerenciamento de dispositivo móvel), use essas configurações para definir um servidor de email, usar o SSL para criptografar emails e muito mais.

Como administrador do Intune, você pode criar e atribuir configurações de email a dispositivos Android Enterprise no perfil de trabalho.

Para saber mais sobre perfis de email no Intune, confira [definir as configurações de email](email-settings-configure.md).

## <a name="before-you-begin"></a>Antes de começar

Crie um [perfil de configuração de dispositivo](email-settings-configure.md#create-a-device-profile) (escolha o perfil de trabalho) ou crie uma [política de configuração de aplicativos](../apps/app-configuration-policies-use-android.md).

## <a name="android-enterprise"></a>Android Enterprise

- **Aplicativo de email**: selecione **Gmail** ou **Nine Work**
- **Servidor de email**: o nome do host do servidor Exchange. Por exemplo, insira `outlook.office365.com`.
- **Atributo de nome de usuário do AAD**: Esse nome é o atributo que o Intune obtém do Azure AD (Azure Active Directory). O Intune gera dinamicamente o nome de usuário que é usado por esse perfil. Suas opções:

  - **Nome principal de usuário**: obtém o nome, como `user1` ou `user1@contoso.com`
  - **Nome de usuário**: obtém apenas o nome, como `user1`

- **Atributo de endereço de email do AAD**: Esse nome é o atributo de email que o Intune obtém do Azure AD. O Intune gera dinamicamente o endereço de email que é usado por esse perfil. Suas opções:
  - **Nome principal de usuário**:  Use o nome principal completo, como `user1@contoso.com` ou `user1`, como o endereço de email.
  - **Endereço SMTP primário**: Use o endereço SMTP primário, como `user1@contoso.com`, para entrar no Exchange.

- **Método de autenticação**: Escolha **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.
  - Se você selecionar **Certificado**, selecione um perfil de certificado SCEP ou PKCS de cliente que você já criou para autenticar a conexão com o Exchange.
- **SSL**: Escolha **Habilitar** para usar a comunicação do protocolo SSL (Secure Sockets Layer) ao enviar e receber emails e ao se comunicar com o servidor do Exchange.
- **Quantidade de emails para sincronizar**: Escolha o tempo de email que você deseja sincronizar. Ou escolha **Ilimitado** para sincronizar todos os emails disponíveis.
- **Tipo de conteúdo para sincronizar** (somente Nine Work): Escolha quais dados você deseja sincronizar nos dispositivos. Suas opções:
  - **Contatos**: Escolha **Habilitar** para permitir que os usuários finais sincronizem contatos para seus dispositivos.
  - **Calendário**: Escolha **Habilitar** para permitir que os usuários finais sincronizem o calendário com seus dispositivos.
  - **Tarefas**: Escolha **Habilitar** para permitir que os usuários finais sincronizem tarefas com seus dispositivos.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

Você também pode criar perfis de email para dispositivos [Samsung Knox do Android](email-settings-android.md), [iOS/iPadOS](email-settings-ios.md), [Windows 10 e posterior](email-settings-windows-10.md) e [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
