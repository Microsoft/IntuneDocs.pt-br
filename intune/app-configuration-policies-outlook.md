---
title: Configurações do Outlook para dispositivos iOS e Android no Microsoft Intune
description: Crie uma política de configuração para definir as configurações do Microsoft Outlook em execução em dispositivos iOS e Android.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7fc9f34bbd3d14ac4291582247b1e45169c2cccc
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2018
ms.locfileid: "48828652"
---
# <a name="microsoft-outlook-configuration-settings"></a>Definições de configuração do Microsoft Outlook 

Use uma política de configuração para definir as configurações do Microsoft Outlook em execução em dispositivos iOS e Android. 

Para criar uma política de configuração de aplicativo para dispositivos iOS gerenciados, confira [Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados](app-configuration-policies-use-ios.md). Para criar uma política de configuração de aplicativo para dispositivos Android gerenciados, confira [Adicionar políticas de configuração de aplicativos para dispositivos Android gerenciados](app-configuration-policies-use-android.md). 

## <a name="configuration-settings"></a>Definições de configuração

Ao adicionar uma política de configuração no Intune, é possível definir configurações específicas para configurar o Microsoft Outlook. No painel **Definições de configuração**, é possível definir a configuração da conta de email.

### <a name="email-account-settings"></a>Configurações da conta de email

As definições de configuração a seguir são específicas para o Microsoft Outlook.

- **Servidor de email**: insira o nome do host do servidor Exchange.
- **Nome da conta de email**: insira o nome de exibição da conta de email. Esse nome é exibido aos usuários em seus dispositivos.
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
- **Domínio da conta**: (opcional) o domínio da conta.

## <a name="next-steps"></a>Próximas etapas
[Definir as configurações de email no Intune](email-settings-configure.md)

