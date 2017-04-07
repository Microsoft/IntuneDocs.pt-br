---
title: "Ações de não conformidade"
titleSuffix: Intune Azure preview
description: "Visualização do Intune Azure: saiba como criar ações para os dispositivos incompatíveis"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: 16da087e741e335144266c838c0a91050bd7d520
ms.lasthandoff: 03/15/2017


---

# <a name="create-actions-for-non-compliance"></a>Criar Ações de não conformidade

As **Ações de não conformidade** permitem configurar uma sequência ordenada pelo tempo das ações que são aplicadas nos dispositivos que estão sem conformidade. Por exemplo, você pode notificar os usuários dos dispositivos não compatíveis por email ou impedir que esses dispositivos acessem os recursos corporativos por meio do acesso condicional.

## <a name="use-case-scenario"></a>Cenário do caso de uso

Por padrão, assim que um dispositivo é relatado como incompatível por uma política de conformidade do dispositivo do Intune, o acesso condicional bloqueia imediatamente esse dispositivo e o usuário recebe um email com instruções para ser compatível. As **Ações de não conformidade** proporcionam mais flexibilidade para decidir o que fazer quando um dispositivo for incompatível. Por exemplo, você pode decidir não bloquear o dispositivo imediatamente e fornecer ao usuário um período de cortesia para ser compatível.

Existem dois tipos de ações:

-   notificar o usuário por email

-   bloquear o acesso ao recurso corporativo por meio do acesso condicional

## <a name="notify-the-user-via-email"></a>Notificar o usuário por email

Você pode escolher um dos modelos de email padrão criados previamente ou criar uma notificação de email totalmente personalizada. Fornecemos a personalização do assunto, corpo da mensagem, incluindo o logotipo da empresa, informações de contato e destinatários adicionais.

## <a name="block-corporate-resource-access-through-conditional-access"></a>Bloquear o acesso ao recurso corporativo por meio do acesso condicional

Você pode determinar uma agenda em número de dias em que o dispositivo deve ser impedido de acessar os recursos corporativos. Isso pode ser imediatamente, mas você também pode dar ao usuário um período de cortesia para ficar compatível com as políticas de conformidade do dispositivo.

## <a name="before-you-begin"></a>Antes de começar

Você precisa ter, pelo menos, uma política de conformidade do dispositivo criada para configurar as ações de não conformidade.

-   Saiba como criar uma política de conformidade do dispositivo para:

    -   [Android](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android)

    -   [Android for Work](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android-for-work)

    -   [iOS](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-ios)

    -   [Windows](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-windows)

Você precisa ter o acesso condicional do EMS configurado e pronto ao planejar usar políticas de conformidade do dispositivo para impedir que os dispositivos usem os recursos corporativos.

- Saiba [como configurar o acesso condicional do EMS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Além disso, você precisa ter um modelo da mensagem de notificação criado. O modelo da mensagem de notificação é usado posteriormente no processo de criação de ações de não conformidade para enviar emails aos usuários.

### <a name="to-add-a-notification-message-template"></a>Para adicionar um modelo da mensagem de notificação

Na folha **Políticas de conformidade do dispositivo**:

1.  Em **Gerenciar**, escolha **Notificações** e a folha de Modelos da mensagem de notificação é aberta.

    ![Como adicionar um modelo de notificação](../media/afnc-1.png)

2.  Escolha **Adicionar**, em seguida, você precisará definir o seguinte:

    a.  Descrição

    b.  De

    c.  Assunto

    d.  Mensagem

    e.  Cabeçalho do email – incluir o logotipo da empresa

    f.  Rodapé do email – incluir o nome da empresa

    g.  Rodapé do email – incluir informações de contato

     ![Modelo da mensagem de notificação](../media/afnc-2.png)

Depois de terminar a adição das informações, você pode clicar em **Criar**. O Modelo da mensagem de notificação está disponível para o uso.

> [!NOTE] 
> Você também pode editar um Modelo de notificação criado anteriormente.

## <a name="to-create-actions-for-non-compliance"></a>Para criar ações de não conformidade

Você poderá adicionar uma ação no momento em que estiver criando uma nova política de conformidade do dispositivo ou editando uma política de conformidade do dispositivo existente.

1.  Na folha **Políticas de conformidade do dispositivo**, em **Gerenciar**, escolha **Políticas**.

2.  Escolha uma política de conformidade do dispositivo clicando nela.

    ![Políticas de conformidade](../media/afnc-3.png)

3.  A folha **Propriedades da política de conformidade do dispositivo** abre; escolha **Ações de não conformidade**.

4.  A folha Ações de não conformidade lâmina é aberta; escolha **Adicionar** para especificar os parâmetros de ação.

    ![Folha Ações de não conformidade](../media/afnc-4.png)

As Ações de não conformidade são:

-   **impor a política de acesso condicional**

-   **enviar um email para o usuário final**

### <a name="enforce-conditional-access-policy"></a>Impor a política de acesso condicional

Para adicionar esta ação de não conformidade:

1.  Na folha **Ações de não conformidade**, escolha **Adicionar**.

2.  Na **folha Parâmetros de ação**, selecione **Impor a política de acesso condicional** na lista suspensa Ação.

3.  Em **Agenda**, você pode especificar o número de dias (de 0 a 255) para impor a política de acesso condicional. Se você especificar **0** número de dias, isso significará que o acesso condicional deverá **imediatamente** bloquear o acesso aos recursos corporativos assim que os dispositivos ficam incompatíveis com as políticas de conformidade do dispositivo.

    ![Agendar Ações de não conformidade](../media/afnc-5.png)

4.  Escolha **Adicionar**, em seguida, escolha **OK** na folha **Ações**.

5.  Na folha **Propriedades da política de conformidade do dispositivo**, escolha **Salvar**.

### <a name="send-e-mail-to-end-user"></a>Enviar email para o usuário final

Você pode usar um modelo de email para enviar para os usuários incompatíveis. Esses emails ajudam a orientar a conformidade do dispositivo em toda a organização.

Para adicionar esta ação de não conformidade:

1.  Na folha **Ações de não conformidade**, escolha **Adicionar**.

2.  Na **folha Parâmetros de ação**, selecione **Enviar email para o usuário final** na lista suspensa Ação.

3.  Escolha um modelo de mensagem criado anteriormente clicando no **Modelo de mensagem**. Você pode exibir o conteúdo do Modelo de mensagem e escolher **Selecionar**.

    ![Modelo de mensagem](../media/afnc-6.png)

> [!NOTE] 
> Você pode exibir o modelo de mensagem, mas não pode editá-lo. Se você quiser editar o Modelo de mensagem, precisará voltar para a folha **Notificações**.

1.  Em **Agendar**, insira o número de dias, após a não conformidade, que o email deve ser enviado para os usuários. Se você especificar **0** número de dias, isso significará que o email será **imediatamente** enviado.

2.  Escolha **Adicionar**, em seguida, escolha **OK** na folha **Ações**.

3.  Na folha **Propriedades da política de conformidade do dispositivo**, escolha **Salvar**.

