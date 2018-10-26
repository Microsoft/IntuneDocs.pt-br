---
title: Configurações do Outlook para dispositivos iOS e Android no Microsoft Intune
description: Crie uma política de configuração para definir as configurações do Microsoft Outlook em execução em dispositivos iOS e Android.
keywords: ''
author: Erikre
ms.author: erikre
ms.reviewer: smithre4
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 24ed1a895dd3e4cad6111b40913b43fa9c6a3cec
ms.sourcegitcommit: 11bd3dbbc9dd762df7c6d20143f2171799712547
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2018
ms.locfileid: "48903515"
---
# <a name="microsoft-outlook-configuration-settings"></a>Definições de configuração do Microsoft Outlook 

Use uma política de configuração para definir as configurações do Microsoft Outlook em execução em dispositivos iOS e Android. 

Para criar uma política de configuração de aplicativo para dispositivos iOS gerenciados, confira [Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados](app-configuration-policies-use-ios.md). Para criar uma política de configuração de aplicativo para dispositivos Android gerenciados, confira [Adicionar políticas de configuração de aplicativos para dispositivos Android gerenciados](app-configuration-policies-use-android.md). 

## <a name="configuration-settings"></a>Definições de configuração

Ao adicionar uma política de configuração no Intune, é possível definir configurações específicas para configurar o Microsoft Outlook. No painel **Definições de configuração**, é possível definir a configuração da conta de email.

### <a name="basic-authentication-email-account-settings"></a>Configurações de conta de email de autenticação Básica
O Outlook para iOS e Android oferece aos administradores do Exchange a capacidade de "enviar por push" configurações de conta para seus usuários locais que usam autenticação Básica com o protocolo ActiveSync. Para obter mais informações, veja [Configuração de conta no Outlook para iOS e Android usando a autenticação Básica](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/account-setup). Para habilitar a configuração de conta, você pode configurar o seguinte:

- **Servidor de email**: insira o nome do host do seu servidor Exchange local (por exemplo, mail.contoso.com).
- **Nome da conta de email**: insira o nome de exibição da conta de email. Esse nome é exibido aos usuários em seus dispositivos.
- **Atributo de nome de usuário do AAD**: esse nome é o atributo que o Intune obtém do Microsoft Azure AD (Azure Active Directory). O Intune gera dinamicamente o nome de usuário que é usado por esse perfil. As opções são:
  - **Nome UPN**: obtém o nome, como `user1` ou `user1@contoso.com`
  - **Endereço SMTP primário**: obtém o nome no formato de endereço de email, como `user1@contoso.com`
- **Atributo de endereço de email do AAD**: escolha como o endereço de email para o usuário é gerado. Selecione **nome UPN** (`user1@contoso.com` ou `user1`) para usar o nome da entidade completo como o endereço de email, ou **Endereço SMTP primário** (`user1@contoso.com`) para usar o endereço SMTP primário para entrar no Exchange. A recomendação é selecionar **Endereço SMTP primário**.
- **Domínio da conta**: (opcional) o domínio da conta.

## <a name="next-steps"></a>Próximas etapas
[Definir as configurações de email no Intune](email-settings-configure.md)

