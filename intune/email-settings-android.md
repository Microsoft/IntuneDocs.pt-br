---
title: Configurações de email para dispositivos Android e de perfil de trabalho Android no Microsoft Intune – Azure | Microsoft Docs
description: Crie um perfil de email de configuração de dispositivo que usa servidores Exchange e recupera atributos do Azure Active Directory. Você também pode habilitar SSL ou SMIME, autenticar usuários com certificados ou nome de usuário/senha e sincronizar email e agendas nos dispositivos Android e de perfil de trabalho Android usando o Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b8ab8dfadb113d81922119a54aefcac43d15b5a1
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187422"
---
# <a name="email-profile-settings-for-devices-running-android-and-android-enterprise---intune"></a>Configurações de perfil de email para dispositivos que executam Android e Android Enterprise – Intune

Use as configurações de perfil de email para configurar os dispositivos que executam Android.

Como administrador do Intune, você pode criar e atribuir configurações de email aos seguintes dispositivos Android:

- Android Samsung Knox Standard
- Android Enterprise

## <a name="android-samsung-knox"></a>Android (Samsung KNOX)

- **Servidor de email**: insira o nome do host do servidor Exchange.
- **Nome da conta**: insira o nome de exibição da conta de email. Esse nome é exibido aos usuários em seus dispositivos.
- **Atributo de nome de usuário do AAD**: esse nome é o atributo que o Intune obtém do AAD (Azure Active Directory). O Intune gera dinamicamente o nome de usuário que é usado por esse perfil. Suas opções:
  - **Nome UPN**: obtém o nome, como `user1` ou `user1@contoso.com`
  - **Nome de usuário**: obtém apenas o nome, como `user1`
  - **Nome da conta sAM**: requer o domínio, como `domain\user1`. O nome da conta sAM pode ser usado apenas com dispositivos Android. Não há suporte para o Android Enterprise.

    Insira também:  
    - **Fonte do nome de domínio do usuário**: escolha **AAD** (Azure Active Directory) ou **Personalizado**.

      Ao escolher obter os atributos do **AAD**, insira:
      - **Atributo de nome de domínio do usuário do AAD**: escolha obter o atributo **Nome de domínio completo** ou **Nome NetBIOS** do usuário

      Ao escolher usar atributos **Personalizados**, insira:
      - **Nome de domínio personalizado a ser usado**: insira um valor que o Intune usará para o nome de domínio, como `contoso.com` ou `contoso`

- **Atributo de endereço de email do AAD**: escolha como o endereço de email para o usuário é gerado. Selecione **nome UPN** (`user1@contoso.com` ou `user1`) para usar o nome da entidade completo como o endereço de email, ou **Endereço SMTP primário** (`user1@contoso.com`) para usar o endereço SMTP primário para entrar no Exchange.

- **Método de autenticação**: selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.
  - Se você selecionar **Certificado**, selecione um perfil de certificado SCEP ou PKCS de cliente que você já criou para autenticar a conexão com o Exchange.

### <a name="security-settings"></a>Configurações de segurança

- **SSL**: use a comunicação do protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.
- **S/MIME**: envie emails de saída usando a criptografia S/MIME.
  - Se você selecionar **Certificado**, selecione um perfil de certificado SCEP ou PKCS de cliente que você já criou para autenticar a conexão com o Exchange.

### <a name="synchronization-settings"></a>Configurações de sincronização

- **Quantidade de emails a serem sincronizados**: escolha o número de dias de emails que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todos os emails disponíveis.
- **Sincronizar agendamento**: selecione o agendamento para que os dispositivos sincronizem os dados do servidor Exchange. Você também pode selecionar **Conforme as mensagens chegam**, que sincroniza os dados quando eles chegam ou **Manual**, em que o usuário do dispositivo deve iniciar a sincronização.

### <a name="content-sync-settings"></a>Configurações de sincronização de conteúdo

- **Tipo de conteúdo a ser sincronizado**: selecione os tipos de conteúdo que você deseja sincronizar com os dispositivos de:
  - **Contatos**
  - **Calendário**
  - **Tarefas**

## <a name="android-enterprise"></a>Android Enterprise

- **Aplicativo de email**: selecione **Gmail** ou **Nine Work**
- **Servidor de email**: o nome do host do servidor Exchange.
- **Atributo de nome de usuário do AAD**: esse nome é o atributo no AD (Active Directory) ou no Azure AD, que é usado para gerar o nome de usuário para este perfil de email. Selecione o **Endereço SMTP Primário**, como o user1@contoso.com ou **Nome UPN**, como user1 ou user1@contoso.com.
- **Atributo de endereço de email do AAD**: como o endereço de email do usuário em cada dispositivo é gerado. Selecione **nome UPN** para usar o nome da entidade completo como o endereço de email ou **Nome de usuário**.
- **Método de autenticação**: selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.
  - Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS do cliente criado anteriormente para autenticar a conexão do Exchange.
- **SSL**: use a comunicação do protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.
- **Quantidade de emails a serem sincronizados**: escolha o número de dias de emails que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todos os emails disponíveis.
- **Tipo de conteúdo a ser sincronizado** (somente Nine Work): selecione os tipos de conteúdo que você deseja sincronizar com os dispositivos de:
  - **Contatos**
  - **Calendário**
  - **Tarefas**

## <a name="next-steps"></a>Próximas etapas
[Definir as configurações de email no Intune](email-settings-configure.md)
