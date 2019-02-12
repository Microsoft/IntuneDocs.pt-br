---
title: Configurações de email para dispositivos Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Crie um perfil de email de configuração de dispositivo que usa os servidores Exchange e recupera atributos do Azure Active Directory. Você também pode habilitar o SSL e sincronizar o email e as agendas em dispositivos Windows 10 usando o Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a631ff93ed135ebbf389059c08f52b3df90e4295
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55838930"
---
# <a name="email-profile-settings-for-devices-running-windows-10---intune"></a>Configurações de perfil de email para dispositivos que executam o Windows 10 – Intune

Use as configurações de perfil de email para configurar o aplicativo de Email nos dispositivos que executam o Windows 10.

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

- **Atributo de endereço de email do AAD**: escolha como o endereço de email do usuário é gerado. Selecione **nome UPN** (`user1@contoso.com` ou `user1`) para usar o nome da entidade completo como o endereço de email, ou **Endereço SMTP primário** (`user1@contoso.com`) para usar o endereço SMTP primário para entrar no Exchange.

## <a name="security-settings"></a>Configurações de segurança

- **SSL**: Use comunicação SSL (protocolo SSL) ao enviar e receber emails e se comunicar com o Exchange Server.

## <a name="synchronization-settings"></a>Configurações de sincronização

- **Quantidade de emails para sincronizar**: Escolha o número de dias de emails que deseja sincronizar. Ou selecione **Ilimitado** para sincronizar todos os emails disponíveis.
- **Sincronizar agendamento**: Selecione o agendamento para que os dispositivos sincronizem os dados do servidor Exchange. Também é possível selecionar a opção **Conforme as mensagens chegam**, que sincroniza os dados assim que eles chegam, ou **Manual**, em que o usuário do dispositivo precisa iniciar a sincronização.

## <a name="content-sync-settings"></a>Configurações de sincronização de conteúdo

- **Tipo de conteúdo a ser sincronizado**: selecione os tipos de conteúdo que você deseja sincronizar com dispositivos para:
  - **Contatos**
  - **Calendário**
  - **Tarefas**

## <a name="next-steps"></a>Próximas etapas
[Definir as configurações de email no Intune](email-settings-configure.md)
