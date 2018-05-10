---
title: Configurações de email do Microsoft Intune para dispositivos iOS
titleSuffix: ''
description: Saiba quais são as configurações do Microsoft Intune que você pode usar para definir configurações de email em dispositivos que executam o iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0912ec4fdc77b51903b4febd54f9d16972b867a8
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-ios"></a>Configurações de perfil de email no Microsoft Intune para dispositivos que executam o iOS 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações de perfil de email que você pode definir para os dispositivos que executam o iOS.

## <a name="email-settings"></a>Configurações de email

- **Servidor de email** – O nome do host do seu servidor Exchange.
- **Nome da conta** – o nome de exibição da conta de email exibida aos usuários em seus dispositivos.
- **Atributo de nome de usuário do AAD** – Esse é o atributo no AD (Active Directory) ou Azure AD, que é usado para gerar o nome de usuário para este perfil de email. Selecione o **Endereço SMTP Primário**, como o **user1@contoso.com** ou **Nome UPN**, como **user1** ou **user1@contoso.com**.
- **Atributo de endereço de email do AAD** – Como o endereço de email do usuário em cada dispositivo cliente será gerado. Selecione **Endereço SMTP Primário** para usar o endereço SMTP primário para fazer logon no Exchange ou use **Nome UPN** para usar o nome da entidade completo como o endereço de email.
- **Método de autenticação** – selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email (**Observação**: a autenticação multifator do Azure não tem suporte).
    - Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS de cliente criado anteriormente para ser usado para autenticar a conexão do Exchange.
- **SSL** – Use a comunicação por protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.
- **S/MIME** - Enviar email de saída usando a assinatura de S/MIME.
    - Se você selecionou **Certificado**, escolha um perfil de certificado SCEP ou PKCS de cliente criado anteriormente para ser usado para autenticar a conexão do Exchange.
    - Se você escolher um certificado SCEP, verifique se um certificado de Troca de Informações Pessoais (PFX) está instalado no dispositivo.
- **Quantidade de emails a ser sincronizada** – Escolha o número de dias de emails que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todas as mensagens disponíveis.
- **Permitir que as mensagens sejam movidas para outras contas de email** – Isso permite que os usuários movam mensagens de email entre contas diferentes que podem estar configuradas em seu dispositivo.
- **Permitir o envio de email de aplicativos de terceiros** – Permita que o usuário selecione este perfil como a conta padrão para enviar email e permitir que aplicativos de terceiros abram o email no aplicativo de email nativo, por exemplo, para anexar arquivos ao email.
- **Sincronizar endereços de email usados recentemente** – Esse recurso permite que os usuários sincronizem a lista de endereços de email usados recentemente no dispositivo com o servidor.
