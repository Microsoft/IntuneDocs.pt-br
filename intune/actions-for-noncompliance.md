---
title: "Mensagem e ações de não conformidade com o Microsoft Intune – Azure | Microsoft Docs"
description: "Crie um email de notificação que será enviado para dispositivos sem conformidade. Adicione ações depois que um dispositivo é marcado como sem conformidade, como adicionar um período de carência para ficar em conformidade ou criar um agendamento para bloquear o acesso até que o dispositivo esteja em conformidade. Faça isso usando o Microsoft Intune no Azure."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 37a8deca147bbad1e706b814f366a2c3f1247869
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2018
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices---intune"></a>Automatizar email e adicionar ações para dispositivos não compatíveis – Intune

Há um recurso **Ações de não conformidade** que configura uma sequência ordenada de ações. Essas ações se aplicam a dispositivos que não atendam à política de conformidade. 

## <a name="overview"></a>Visão geral
Por padrão, quando o Intune detecta um dispositivo que não está em conformidade, ele marca imediatamente o dispositivo como não compatível. Em seguida, o [acesso condicional](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) do AD (Azure Active Directory) bloqueia o dispositivo. Quando um dispositivo não está em conformidade, as **ações de não conformidade** também oferecem mais flexibilidade para decidir o que fazer. Por exemplo, não bloquear o dispositivo imediatamente e conceder ao usuário um período de carência para ter conformidade.

Existem dois tipos de ações:

- **Notificar usuários finais por email**: personalize uma notificação por email antes de enviá-la para o usuário final. É possível personalizar os destinatários, o assunto e o corpo da mensagem, incluindo o logotipo da empresa e as informações de contato.

    Além disso, o Intune inclui detalhes sobre o dispositivo não compatível na notificação por email.

- **Marcar dispositivos como fora de conformidade**: crie um agendamento (em número de dias) depois dos quais o dispositivo será marcado como fora de conformidade. Você pode configurar a ação para entrar em vigor imediatamente ou conceder ao usuário um período de cortesia para que ele fique em conformidade.

## <a name="before-you-begin"></a>Antes de começar

- Para configurar ações de não conformidade, você precisa ter, pelo menos, uma política de conformidade do dispositivo. Para criar uma política de conformidade do dispositivo, consulte as seguintes plataformas:

  - [Android](compliance-policy-create-android.md)
  - [Android for Work](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- O acesso condicional do Microsoft Azure AD precisa ser configurado ao usar políticas de conformidade do dispositivo para impedir que dispositivos usem recursos corporativos. Consulte [Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) para ver as diretrizes.

- É necessário criar um modelo de mensagem de notificação. Para enviar email para os usuários, esse modelo é usado para criar ações de não conformidade.

## <a name="create-a-notification-message-template"></a>Criar um modelo da mensagem de notificação

1. Entre no [Portal do Azure](https://portal.azure.com) com suas credenciais do Intune. 
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Conformidade do dispositivo** e **Notificações**. 
4. Selecione **Criar notificação** e insira as seguintes informações:

  - Nome
  - Assunto
  - Mensagem
  - Cabeçalho do email – Incluir o logotipo da empresa
  - Rodapé do email – Incluir o nome da empresa
  - Rodapé do email – Incluir informações de contato

  ![Exemplo de uma mensagem de notificação de conformidade no Intune](./media/actionsfornoncompliance-1.PNG)

Quando terminar de adicionar as informações, escolha **Criar**. O Modelo da mensagem de notificação está disponível para ser usado.

> [!NOTE]
> Você também pode editar um Modelo de notificação criado anteriormente.

## <a name="add-actions-for-noncompliance"></a>Adicionar ações de não conformidade

Por padrão, o Intune cria automaticamente uma ação para não conformidade. Quando um dispositivo não cumpre sua política de conformidade, esta ação marca o dispositivo como incompatível. É possível personalizar por quanto tempo o dispositivo fica marcado como sem conformidade. Esta ação não pode ser removida.

É possível adicionar uma ação ao criar uma nova política de conformidade ou ao atualizar uma política de conformidade existente. 

1. No [Portal do Azure](https://portal.azure.com), abra **Microsoft Intune** e selecione **Conformidade do dispositivo**.
2. Selecione **Políticas**, escolha uma das suas políticas e, em seguida, **Propriedades**. 

  Você ainda não tem uma política? Criar uma política para [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md) ou outra plataforma.

3. Selecione **Ações de não conformidade** e **Adicionar** para inserir os parâmetros da ação. Você pode escolher o modelo de mensagem criado anteriormente, adicionar outros destinatários e atualizar o agendamento do período de cortesia. É possível inserir o número de dias (de 0 a 365) no agendamento e, em seguida, impor as políticas de acesso condicional. Se você inserir **0** número de dias, o acesso condicional bloqueia **imediatamente** o acesso aos recursos corporativos.

4. Após terminar, selecione **Adicionar** > **OK** para salvar suas alterações.

## <a name="next-steps"></a>Próximas etapas
Monitorar a atividade de conformidade de dispositivo executando os relatórios. [Como monitorar a conformidade do dispositivo com o Intune](device-compliance-monitor.md) fornece algumas diretrizes.
