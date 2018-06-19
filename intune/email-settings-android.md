---
title: Configurações de email do Microsoft Intune para dispositivos que executam o Android e Android for Work
titleSuffix: ''
description: Saiba mais sobre as configurações do Microsoft Intune que você pode usar para definir configurações de email em dispositivos que executam o Android e o Android for Work.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d492e107fffe730d36c662b9187fc9c6faced907
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31832743"
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-android-and-android-for-work"></a>Configurações de perfil de email no Microsoft Intune para dispositivos que executam o Android e Android for Work

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações de perfil de email que você pode definir para os dispositivos que executam Android.

Como administrador do Intune, você pode criar e atribuir configurações de email aos seguintes dispositivos Android:
- [Android Samsung Knox Standard](#android-samsung-knox-standard-email-settings)
- [Android for Work](#android-for-work-email-settings)

## <a name="android-samsung-knox-standard-email-settings"></a>Configurações de email do Android Samsung Knox Standard
- **Servidor de email** – O nome do host do seu servidor Exchange.
- **Nome da conta** – o nome de exibição da conta de email exibida aos usuários em seus dispositivos.
- **Atributo de nome de usuário do AAD** – esse nome é o atributo no AD (Active Directory) ou no Azure AD usado para gerar o nome de usuário para esse perfil de email. Selecione o **Endereço SMTP Primário**, como o user1@contoso.com ou **Nome UPN**, como user1 ou user1@contoso.com.
- **Atributo de endereço de email do AAD** – Como o endereço de email do usuário em cada dispositivo cliente será gerado. Selecione **Endereço SMTP Primário** para usar o endereço SMTP primário para fazer logon no Exchange ou use o **nome UPN** para usar o nome da entidade completo como o endereço de email.
- **Método de autenticação** – Selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.
    - Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS do cliente criado anteriormente para autenticar a conexão do Exchange.

### <a name="security-settings"></a>Configurações de segurança

- **SSL** – Use a comunicação por protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.
- **S/MIME** – Envia emails de saída usando a criptografia S/MIME.
    - Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS do cliente criado anteriormente para autenticar a conexão do Exchange.

### <a name="synchronization-settings"></a>Configurações de sincronização

- **Quantidade de emails a ser sincronizada** – Escolha o número de dias de emails que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todas as mensagens disponíveis.
- **Sincronizar agendamento** – selecione o agendamento conforme o qual os dispositivos sincronizam os dados do servidor Exchange. Você também pode selecionar **Conforme as mensagens chegam**, que sincroniza os dados quando eles chegam ou **Manual**, em que o usuário do dispositivo deve iniciar a sincronização.

### <a name="content-sync-settings"></a>Configurações de sincronização de conteúdo

- **Tipo de conteúdo a ser sincronizado** – Selecione os tipos de conteúdo que você deseja sincronizar dos dispositivos:
    - **Contatos**
    - **Calendário**
    - **Tarefas**

## <a name="android-for-work-email-settings"></a>Configurações de email do Android for Work

- **Aplicativo de email** – selecione **Gmail** ou **Nine Work**
- **Servidor de email** – O nome do host do seu servidor Exchange.
- **Atributo de nome de usuário do AAD** – esse nome é o atributo no AD (Active Directory) ou no Azure AD que é usado para gerar o nome de usuário para esse perfil de email. Selecione o **Endereço SMTP Primário**, como o user1@contoso.com ou **Nome UPN**, como user1 ou user1@contoso.com.
- **Atributo de endereço de email do AAD** – Como o endereço de email do usuário em cada dispositivo cliente será gerado. Selecione **nome UPN** para usar o nome da entidade completo como o endereço de email ou **Nome de usuário**.
- **Método de autenticação** – Selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.
    - Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS do cliente criado anteriormente para autenticar a conexão do Exchange.
- **SSL** – Use a comunicação por protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.
- **Quantidade de emails a ser sincronizada** – Escolha o número de dias de emails que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todas as mensagens disponíveis.
- **Tipo de conteúdo a ser sincronizado** (somente Nine Work) – selecione os tipos de conteúdo que você deseja sincronizar com os dispositivos de:
    - **Contatos**
    - **Calendário**
    - **Tarefas**
