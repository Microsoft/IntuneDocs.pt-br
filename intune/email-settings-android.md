---
title: Configurações de email do Android e Android Enterprise no Microsoft Intune – Azure | Microsoft Docs
description: Crie um perfil de email de configuração de dispositivo que use servidores Exchange e recupere atributos do Azure Active Directory. Habilite SSL ou SMIME, autentique usuários com certificados ou nome de usuário/senha e sincronize email e agendas nos dispositivos Android e de perfil de trabalho Android usando o Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/15/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: b96363d679a6f09327bf9a1b46421e786d1956a8
ms.sourcegitcommit: 912aee714432c4a1e8efeee253ca2be4f972adaa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54316875"
---
# <a name="android-and-android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Configurações de dispositivo do Android e Android Enterprise para configurar o email, a autenticação e a sincronização no Intune

Este artigo lista e descreve as diferentes configurações de email que você pode controlar em dispositivos Android e Android Enterprise. Como parte da solução MDM (gerenciamento de dispositivo móvel), use essas configurações para definir um servidor de email, usar o SSL para criptografar emails e muito mais.

Como administrador do Intune, você pode criar e atribuir configurações de email aos seguintes dispositivos Android:

- Android Samsung Knox Standard
- Android Enterprise

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](email-settings-configure.md).

## <a name="android-samsung-knox"></a>Android (Samsung KNOX)

- **Servidor de email**: insira o nome do host do servidor Exchange.
- **Nome da conta**: insira o nome de exibição da conta de email. Esse nome é exibido aos usuários em seus dispositivos.
- **Atributo de nome de usuário do AAD**: esse nome é o atributo que o Intune obtém do AAD (Azure Active Directory). O Intune gera dinamicamente o nome de usuário que é usado por esse perfil. Suas opções:
  - **Nome principal de usuário**: obtém o nome, como `user1` ou `user1@contoso.com`
  - **Nome de usuário**: obtém apenas o nome, como `user1`
  - **Nome da conta sAM**: Requer o domínio, como `domain\user1`. O nome da conta sAM pode ser usado apenas com dispositivos Android. Não há suporte para o Android Enterprise.

    Insira também:  
    - **Fonte de nome de domínio do usuário**: escolha **AAD** (Azure Active Directory) ou **Personalizado**.

      Ao escolher obter os atributos do **AAD**, insira:
      - **Atributo de nome de domínio do usuário do AAD**: escolha obter o atributo **Nome de domínio completo** ou o **Nome NetBIOS** do usuário

      Ao escolher usar atributos **Personalizados**, insira:
      - **Nome de domínio personalizado a ser usado**: insira um valor que o Intune usará para o nome de domínio, como `contoso.com` ou `contoso`

- **Atributo de endereço de email do AAD**: escolha como o endereço de email do usuário é gerado. Selecione **nome UPN** (`user1@contoso.com` ou `user1`) para usar o nome da entidade completo como o endereço de email, ou **Endereço SMTP primário** (`user1@contoso.com`) para usar o endereço SMTP primário para entrar no Exchange.

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
  - **Contatos**
  - **Calendário**
  - **Tarefas**

## <a name="android-enterprise"></a>Android Enterprise

- **Aplicativo de email**: selecione **Gmail** ou **Nine Work**
- **Servidor de email**: o nome do host do servidor Exchange.
- **Atributo de nome de usuário do AAD**: Esse nome é o atributo no AD (Active Directory) ou no Azure AD, que é usado para gerar o nome de usuário para este perfil de email. Selecione o **Endereço SMTP Primário**, como o user1@contoso.com ou **Nome UPN**, como user1 ou user1@contoso.com.
- **Atributo de endereço de email do AAD**: Como o endereço de email do usuário em cada dispositivo é gerado. Selecione **nome UPN** para usar o nome da entidade completo como o endereço de email ou **Nome de usuário**.
- **Método de autenticação**: Selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.
  - Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS do cliente criado anteriormente para autenticar a conexão do Exchange.
- **SSL**: Use comunicação SSL (protocolo SSL) ao enviar e receber emails e se comunicar com o Exchange Server.
- **Quantidade de emails para sincronizar**: escolha o número de dias de email que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todos os emails disponíveis.
- **Tipo de conteúdo para sincronizar** (somente Nine Work): Selecione os tipos de conteúdo que você deseja sincronizar aos dispositivos. **Não configurado** desabilita essa configuração. Quando definido como **Não configurado**, se um usuário final habilitar a sincronização no dispositivo, a sincronização será desabilitada novamente quando o dispositivo for sincronizado com o Intune, pois a política será reforçada. 

  Você pode sincronizar o conteúdo a seguir: 
  - **Contatos**
  - **Calendário**
  - **Tarefas**

## <a name="next-steps"></a>Próximas etapas
[Definir as configurações de email no Intune](email-settings-configure.md)
