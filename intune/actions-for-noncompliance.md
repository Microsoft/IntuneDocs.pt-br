---
title: Mensagem e ações de não conformidade com o Microsoft Intune – Azure | Microsoft Docs
description: Crie um email de notificação que será enviado para dispositivos sem conformidade. Adicione ações depois que um dispositivo é marcado como sem conformidade, como adicionar um período de carência para ficar em conformidade ou criar um agendamento para bloquear o acesso até que o dispositivo esteja em conformidade. Faça isso usando o Microsoft Intune no Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/01/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 751d89ef023bea07d3c8bdb69904605d88c9e0b6
ms.sourcegitcommit: dde4b8788e96563edeab63f612347fa222d8ced0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135215"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices-in-intune"></a>Automatizar email e adicionar ações para dispositivos sem conformidade no Intune

Para dispositivos que não atendem às suas políticas ou regras de conformidade, é possível adicionar **Ações de não conformidade**. Este recurso configura uma sequência ordenada por tempo de ações, como enviar email para o usuário final e mais.

## <a name="overview"></a>Visão geral

Por padrão, quando o Intune detecta um dispositivo que não está em conformidade, ele marca imediatamente o dispositivo como não compatível. Em seguida, o [acesso condicional](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) do AD (Azure Active Directory) bloqueia o dispositivo. Quando um dispositivo não está em conformidade, a **ação de não conformidade** também oferece mais flexibilidade para decidir o que fazer. Por exemplo, não bloquear o dispositivo imediatamente e conceder ao usuário um período de carência para ter conformidade.

Há muitos tipos de ações:

- **Enviar email para o usuário final**: personalize uma notificação por email antes de enviá-la ao usuário final. É possível personalizar os destinatários, o assunto e o corpo da mensagem, incluindo o logotipo da empresa e as informações de contato.

    Além disso, o Intune inclui detalhes sobre o dispositivo não compatível na notificação por email.

- **Bloquear remotamente um dispositivo fora de conformidade**: para dispositivos que não estão em conformidade, é possível emitir um bloqueio remoto. O usuário deve inserir um PIN ou uma senha desbloquear o dispositivo. Saiba mais sobre o recurso [Bloqueio remoto](device-remote-lock.md). 

- **Marcar dispositivo fora de conformidade**: crie um agendamento (em número de dias) depois que o dispositivo for marcado como fora de conformidade. Você pode configurar a ação para entrar em vigor imediatamente ou conceder ao usuário um período de cortesia para que ele fique em conformidade.

Este artigo mostra como:

- Criar um modelo de notificação de mensagem
- Criar uma ação de não conformidade, como enviar um email ou bloquear remotamente um dispositivo


## <a name="before-you-begin"></a>Antes de começar

- Para configurar ações de não conformidade, você precisa ter, pelo menos, uma política de conformidade do dispositivo. Para criar uma política de conformidade do dispositivo, consulte as seguintes plataformas:

  - [Android](compliance-policy-create-android.md)
  - [Perfis de trabalho Android](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- O acesso condicional do Microsoft Azure AD precisa ser configurado ao usar políticas de conformidade do dispositivo para impedir que dispositivos usem recursos corporativos. Confira [Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) ou [Maneiras comuns de usar o acesso condicional com o Intune](conditional-access-intune-common-ways-use.md) para obter orientação.

## <a name="create-a-notification-message-template"></a>Criar um modelo da mensagem de notificação

Para enviar email aos seus usuários, crie um modelo de mensagem de notificação. Quando um dispositivo estiver fora de conformidade, os detalhes inseridos no modelo serão mostrados no email enviado aos seus usuários.

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Conformidade do dispositivo** > **Notificações**.
3. Selecione **Criar notificação**. Insira as seguintes informações:

   - **Nome**
   - **Assunto**
   - **Message**
   - **Cabeçalho do email – Incluir o logotipo da empresa**
   - **Rodapé do email – Incluir o nome da empresa**
   - **Rodapé do email – Incluir informações de contato**

   ![Exemplo de uma mensagem de notificação de conformidade no Intune](./media/actionsfornoncompliance-1.PNG)

4. Quando terminar de adicionar as informações, escolha **Criar**. O Modelo da mensagem de notificação está disponível para ser usado. O logotipo que você carregar como parte da identidade visual do Portal da Empresa será usado por modelos de email. Para obter mais informações sobre identidade visual do Portal da Empresa, confira [Personalização de marcas de identidade da empresa](company-portal-app.md#company-identity-branding-customization).

> [!NOTE]
> Também é possível alterar ou atualizar um modelo de notificação existente criado anteriormente.

## <a name="add-actions-for-noncompliance"></a>Adicionar ações de não conformidade

Quando você cria uma política de conformidade de dispositivo, o Intune cria automaticamente uma ação de não conformidade. Se um dispositivo não atender à sua política de conformidade, esta ação o marcará como fora de conformidade. É possível personalizar por quanto tempo o dispositivo fica marcado como sem conformidade. Esta ação não pode ser removida.

É possível adicionar outra ação quando você cria uma política de conformidade ou atualizar uma política existente. 

1. No [Portal do Azure](https://portal.azure.com), abra **Microsoft Intune** > **Conformidade do dispositivo**.
2. Selecione **Políticas**, escolha uma das suas políticas e, em seguida, **Propriedades**. 

    Você ainda não tem uma política? Criar uma política para [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md) ou outra plataforma.
  
    > [!NOTE]
    > No momento, dispositivos JAMF e dispositivos direcionados com grupos de dispositivos não podem receber ações de conformidade.

3. Selecione **Ações para não conformidade** > **Adicionar**.
4. Selecione sua **Ação**: 

    - **Enviar email para usuários finais**: quando o dispositivo não estiver em conformidade, opte por enviar um email ao usuário. Também: 
    
         - Escolha o **Modelo de mensagem** criado anteriormente
         - Insira quaisquer **Destinatários adicionais** selecionando grupos
    
    - **Bloquear remotamente um dispositivo fora de conformidade**: quando o dispositivo não estiver em conformidade, bloqueie o dispositivo. Essa ação força o usuário a inserir um PIN ou uma senha para desbloquear o dispositivo. 
    
5. Configurar um **Agendamento**: insira o número de dias (0 a 365) após a não conformidade disparar a ação nos dispositivos dos usuários. Após esse período de carência, será possível impor uma política de acesso condicional. Se você inserir **0** (zero) número de dias, o acesso condicional entrará em vigor **imediatamente**. Por exemplo, será possível bloquear o acesso a recursos corporativos imediatamente se um dispositivo não for compatível.

6. Após terminar, selecione **Adicionar** > **OK** para salvar suas alterações.

## <a name="next-steps"></a>Próximas etapas

[Monitorar suas políticas](compliance-policy-monitor.md).
