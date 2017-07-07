---
title: "Configurações de email do Intune para dispositivos iOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para configurar as conexões de email em dispositivos iOS."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9f0fa6af-3669-439a-bd0d-75d8b1a0b135
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dcac410ae5c20b5942bf37f5eaa9a46205a4cc07
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="email-profile-settings-for-ios-devices-in-microsoft-intune"></a>Configurações de perfil de email para dispositivos iOS no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



- **Servidor de email** – O nome do host do seu servidor Exchange.
- **Nome da conta** – O nome de exibição para a conta de email que será exibida aos usuários em seus dispositivos.
- **Atributo de nome de usuário do AAD** – Esse é o atributo no AD (Active Directory) ou Azure AD, que será usado para gerar o nome de usuário para este perfil de email. Selecione o **Endereço SMTP Primário**, como o **user1@contoso.com** ou **Nome UPN**, como **user1** ou **user1@contoso.com**.
- **Atributo de endereço de email do AAD** – Como o endereço de email do usuário em cada dispositivo cliente será gerado. Selecione **Endereço SMTP Primário** para usar o endereço SMTP primário para fazer logon no Exchange ou use **Nome UPN** para usar o nome da entidade completo como o endereço de email.
- **Método de autenticação** – Selecione **Nome de Usuário e Senha** ou **Certificados** como o método de autenticação usado pelo perfil de email.
    - Se você selecionou **Certificado**, escolha um cliente SCEP ou perfil de certificado PKCS criado anteriormente para ser usado para autenticar a conexão do Exchange.
- **SSL** – Use a comunicação por protocolo SSL ao enviar e receber emails e ao se comunicar com o servidor Exchange.
- **S/MIME** - Enviar email de saída usando a assinatura de S/MIME.
    - Se você selecionou **Certificado**, escolha um cliente SCEP ou perfil de certificado PKCS criado anteriormente para ser usado para autenticar a conexão do Exchange.
- **Quantidade de emails a ser sincronizada** – Escolha o número de dias de emails que você deseja sincronizar ou selecione **Ilimitado** para sincronizar todas as mensagens disponíveis.
- **Permitir que as mensagens sejam movidas para outras contas de email** – Isso permite que os usuários movam mensagens de email entre contas diferentes que podem estar configuradas em seu dispositivo.
- **Permitir o envio de email de aplicativos de terceiros** – Permita que o usuário selecione este perfil como a conta padrão para enviar email e permitir que aplicativos de terceiros abram o email no aplicativo de email nativo, por exemplo, para anexar arquivos de email.
- **Sincronizar endereços de email usados recentemente** – Esse recurso permite que os usuários sincronizem a lista de endereços de email usados recentemente no dispositivo com o servidor.
