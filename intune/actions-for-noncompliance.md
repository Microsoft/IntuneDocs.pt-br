---
title: "Ações para falta conformidade com o Intune"
titleSuffix: Intune on Azure
description: "Saiba como criar ações para a falta de conformidade com o Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3adc3c01d4657accfdb5cd70970ff191d06a9aef
ms.sourcegitcommit: a1c751959c9b3d5678bd9d67007e762df30eab59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2017
---
# <a name="automate-actions-for-noncompliance"></a>Automatizar ações para falta de conformidade

As **ações para falta de conformidade** permitem que você configure uma sequência ordenada por tempo de ações que são aplicadas a dispositivos que não atendem aos critérios da política de conformidade. Por padrão, quando é detectado que um dispositivo não atende aos critérios da política de conformidade, o Intune marca o dispositivo imediatamente como fora de conformidade e ele é bloqueado pelo acesso condicional do Azure AD. As **ações para falta de conformidade** oferecem mais flexibilidade para decidir o que fazer quando um dispositivo está fora de conformidade. Por exemplo, você pode decidir não bloquear o dispositivo imediatamente e fornecer ao usuário um período de cortesia para ser compatível.

Existem dois tipos de ações:

-   **Notificar usuários finais por email**: você pode personalizar a notificação por email antes de enviá-la ao usuário final. O Intune oferece a personalização do assunto, do corpo da mensagem, incluindo o logotipo da empresa, das informações de contato e de destinatários adicionais.

-   **Marcar dispositivos como fora de conformidade**: você pode determinar um agendamento do número de dias para que o dispositivo seja marcado como fora de conformidade. Pode ser imediatamente, mas você também pode fornecer ao usuário um período de cortesia para que ele fique em conformidade com as políticas de conformidade do dispositivo.

## <a name="before-you-begin"></a>Antes de começar

Você precisa ter, pelo menos, uma política de conformidade do dispositivo criada para configurar as ações de não conformidade.

-   Saiba como criar uma política de conformidade do dispositivo para:

    -   [Android](compliance-policy-create-android.md)

    -   [Android for Work](compliance-policy-create-android-for-work.md)

    -   [iOS](compliance-policy-create-ios.md)
    
    -   [macOS](compliance-policy-create-mac-os.md)

    -   [Windows](compliance-policy-create-windows.md)

A configuração de acesso condicional do Azure AD precisa estar pronta ao planejar usar políticas de conformidade do dispositivo para impedir que os dispositivos usem recursos corporativos.

- Saiba [como configurar o acesso condicional do EMS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Além disso, você precisa ter um modelo da mensagem de notificação criado. O modelo da mensagem de notificação é usado posteriormente no processo de criação de ações de não conformidade para enviar emails aos usuários.

### <a name="to-create-a-notification-message-template"></a>Para criar um modelo da mensagem de notificação

1. Acesse o [Intune no portal do Azure](https://portal.azure.com)e entre com suas credenciais do Intune.

2. Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3. Escolha **Intune**

4. Escolha **Conformidade do dispositivo** e, em seguida, escolha **Notificações** na seção **Gerenciar**.

5. Escolha **Criar notificação** e insira o seguinte:

    a.  Nome

    b.  Assunto

    c.  Mensagem

    d.  Cabeçalho do email – incluir o logotipo da empresa

    e.  Rodapé do email – incluir o nome da empresa

    f.  Rodapé do email – incluir informações de contato

![exemplo de modelo de mensagem de notificação](./media/actionsfornoncompliance-1.PNG)

Quando terminar de adicionar as informações, escolha **Criar**. O Modelo da mensagem de notificação está disponível para o uso.

> [!NOTE] 
> Você também pode editar um Modelo de notificação criado anteriormente.

## <a name="to-create-actions-for-non-compliance"></a>Para criar ações de não conformidade

> [!TIP]
> Por padrão, o Intune fornece uma ação predefinida na seção de ações para falta conformidade. Essa ação é para marcar o dispositivo como fora de conformidade quando for detectado que ele não atende aos critérios da política de conformidade do dispositivo. Você pode personalizar quanto tempo após a detecção o dispositivo será marcado como fora de conformidade. Esta ação não pode ser removida.

Você poderá adicionar uma ação no momento em que estiver criando uma nova política de conformidade do dispositivo ou editando uma política de conformidade do dispositivo existente.

1.  Na carga de trabalho do Intune, na folha **Políticas de conformidade do dispositivo**, escolha **Políticas** na seção **Gerenciar**.

2.  Escolha uma política de conformidade do dispositivo clicando nela e selecione **Propriedades** na seção **Gerenciar**.

3.  A folha **Propriedades da política de conformidade do dispositivo** abre; escolha **Ações de não conformidade**.

4.  A folha Ações de não conformidade lâmina é aberta; escolha **Adicionar** para especificar os parâmetros de ação. Você pode escolher o modelo de mensagem criado anteriormente, destinatários adicionais e o agendamento do período de cortesia. Você pode especificar o número de dias (de 0 a 365) no agendamento e, em seguida, impor as políticas de acesso condicional. Se você especificar **0** como o número de dias, isso significará que o acesso condicional deverá bloquear **imediatamente** o acesso aos recursos corporativos quando os dispositivos estiverem fora de conformidade com as políticas de conformidade do dispositivo.

5.  Quando terminar de adicionar suas informações, escolha **Adicionar** e, em seguida, **OK**.

## <a name="next-steps"></a>Próximas etapas

Você pode monitorar a atividade de conformidade do dispositivo executando os relatórios disponíveis na folha de conformidade do dispositivo. Saiba mais sobre [como monitorar a conformidade do dispositivo com o Intune](device-compliance-monitor.md)

