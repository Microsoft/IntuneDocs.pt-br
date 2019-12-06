---
title: Início Rápido – Enviar notificações para dispositivos não compatíveis
titleSuffix: Microsoft Intune
description: Neste início rápido, você usará o Microsoft Intune para enviar notificações por email a dispositivos não compatíveis.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1b89f2d-7937-46bb-926b-b05f6fa9c749
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d89cfcafd5452b990509e0fa6fd431a614ee5c1
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410228"
---
# <a name="quickstart-send-notifications-to-noncompliant-devices"></a>Início Rápido: Enviar notificações para dispositivos não compatíveis

Neste início rápido, você usará o Microsoft Intune para enviar uma notificação por email aos membros da sua força de trabalho que possuem dispositivos não compatíveis.

Por padrão, quando o Intune detecta um dispositivo que não está em conformidade, ele marca imediatamente o dispositivo como não compatível. [Acesso Condicional](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) do Azure Active Directory (Azure AD) e, em seguida, bloqueia o dispositivo. Quando um dispositivo não é compatível, o Intune permite adicionar ações para não conformidade, o que oferece flexibilidade para decidir o que fazer. Por exemplo, você pode conceder aos usuários um período de cortesia para estar em conformidade antes de bloquear dispositivos não compatíveis.

Uma ação a ser tomada quando um dispositivo não atende à conformidade é enviar um email ao usuário do dispositivo. Você também pode personalizar uma notificação por email antes de enviá-la. Especificamente, é possível personalizar os destinatários, o assunto e o corpo da mensagem, incluindo o logotipo da empresa e as informações de contato. O Intune também inclui detalhes sobre o dispositivo não compatível na notificação por email.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos

O Acesso Condicional do Microsoft Azure AD precisa ser configurado ao usar políticas de conformidade do dispositivo para impedir que dispositivos usem recursos corporativos. Se você concluiu o início rápido [Criar uma política de conformidade do dispositivo](quickstart-set-password-length-android.md), está usando o Azure Active Directory. Para saber mais sobre o Azure AD, confira [Acesso Condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) e [formas comuns de usar o Acesso Condicional com o Intune](../protect/conditional-access-intune-common-ways-use.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) como [Administrador global](../fundamentals/users-add.md#types-of-administrators) ou [Administrador de serviços](../fundamentals/users-add.md#types-of-administrators) do Intune. Se você criar uma assinatura de avaliação do Intune, a conta com a qual criou a assinatura será a de Administrador global.

## <a name="create-a-notification-message-template"></a>Criar um modelo da mensagem de notificação

Para enviar email aos seus usuários, crie um modelo de mensagem de notificação. Quando um dispositivo estiver fora de conformidade, os detalhes inseridos no modelo serão mostrados no email enviado aos seus usuários.

1. No Intune, selecione **Dispositivos** > **Políticas de conformidade** > **Notificações** > **Criar notificação**.
2. Insira as seguintes informações:

   - **Nome**: *Administrador da Contoso*
   - **Assunto**: *Conformidade do dispositivo*
   - **Mensagem**: *No momento, seu dispositivo não atende aos nossos requisitos de conformidade de organizações.*
   - **Cabeçalho do email – Incluir o logotipo da empresa**: Defina como **Habilitado** para mostrar o logotipo da sua organização.
   - **Rodapé do email – Incluir o nome da empresa**: Defina como **Habilitado** para mostrar o nome da sua organização.
   - **Rodapé do email – Incluir informações de contato**: Defina como **Habilitado** para mostrar as informações de contato da sua organização.

   ![Exemplo de uma mensagem de notificação de conformidade no Intune](./media/quickstart-send-notification/quickstart-send-notification-01.png)

3. Selecione **Avançar** e revise sua notificação. Selecione **Criar**, e o modelo de mensagem de notificação estará pronto para uso.

   > [!NOTE]
   > Você também pode editar um Modelo de notificação criado anteriormente.

Para obter detalhes sobre como definir o nome da empresa, as informações de contato e o logotipo da empresa, confira os seguintes artigos:

- [Dados da empresa e declaração de privacidade](../apps/company-portal-app.md#company-information-and-privacy-statement)
- [Informações de suporte](../apps/company-portal-app.md#support-information)
- [Personalização da identidade visual da empresa](../apps/company-portal-app.md#company-identity-branding-customization).

## <a name="add-a-noncompliance-policy"></a>Adicionar uma política de não conformidade

Quando você cria uma política de conformidade de dispositivo, o Intune cria automaticamente uma ação de não conformidade. O Intune marca os dispositivos como não compatíveis quando eles não atendem à sua política de conformidade. É possível personalizar por quanto tempo o dispositivo fica marcado como não compatível. É possível adicionar outra ação quando você cria uma política de conformidade ou atualizar uma política de conformidade existente.

As etapas a seguir criarão uma política de conformidade para dispositivos Windows 10.

1. No Intune, selecione **Dispositivos** > **Políticas de Conformidade** > **Criar Política**.

2. Insira as seguintes informações:

   - **Nome**: *Conformidade do Windows 10*
   - **Descrição**: *política de conformidade do Windows 10*
   - **Plataforma**: Windows 10 e posterior

3. Selecione **Configurações** > **Segurança do Sistema** para exibir as configurações relacionadas à segurança do dispositivo.

4. Configure as seguintes opções:

   - Defina **Exigir uma senha para desbloquear os dispositivos móveis** como **Exigir**. Essa configuração especifica se os usuários terão que inserir uma senha antes do acesso ser concedido às informações em seus dispositivos móveis.

   - Defina **Comprimento mínimo da senha** como **6**. Essa configuração especifica o número mínimo de dígitos ou caracteres na senha.

   ![Configurações de segurança do sistema para uma nova política de conformidade](./media/quickstart-send-notification/system-security-settings-01.png)

5. Selecione **Ok** > **Ok** > **Criar** para criar a política de conformidade.

6. Selecione **Propriedades** > **Ação de não conformidade** > **Adicionar**.

7. Na caixa suspensa **Ação**, confirme se a opção **Enviar um email para os usuários finais** está selecionada.

8. Selecione **Modelo de mensagem**, o modelo que você criou anteriormente neste artigo e, em seguida, **Selecionar** para selecionar o modelo de mensagem.

9. Selecione **ADICIONAR** > **Ok** > **Salvar** para salvar suas alterações.

## <a name="assign-the-policy"></a>Atribuir a política

Você pode atribuir a política de conformidade a um grupo de usuários específico ou para todos os usuários. Quando o Intune reconhece que um dispositivo não é compatível, o usuário é notificado de que deve atualizá-lo para atender à política de conformidade. Use as etapas a seguir para atribuir a política.

1. No Intune, acesse **Dispositivos** > **Políticas de Conformidade** e selecione a política de **conformidade do Windows 10** que você criou anteriormente.

2. Selecione **Atribuições**.

3. Na caixa suspensa **Atribuir a**, selecione **Todos os Usuários**. Isso selecionará todos os usuários. Qualquer usuário que tenha um dispositivo **Windows 10 e posterior** será notificado de que não atende a essa política de conformidade do dispositivo.

    > [!NOTE]
    > Você pode incluir e excluir grupos quando atribuir políticas de conformidade.

4. Clique em **Salvar**.

Quando você criar e salvar a política, ela aparecerá na lista de **Políticas de conformidade - Políticas**. Observe na lista que **Atribuído** está configurado como **Sim**.

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você usou o Intune para criar e atribuir uma política de conformidade para os dispositivos Windows 10 da sua força de trabalho para exigir uma senha com pelo menos seis caracteres de comprimento. Para obter mais informações sobre como criar políticas de conformidade para dispositivos Windows, confira [Adicionar uma política de conformidade de dispositivo para dispositivos Windows no Intune](compliance-policy-create-windows.md).

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início rápido: Adicionar e atribuir um aplicativo cliente](../apps/quickstart-add-assign-app.md)
