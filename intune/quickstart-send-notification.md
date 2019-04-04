---
title: Início Rápido – Enviar notificações para dispositivos não compatíveis
titleSuffix: Microsoft Intune
description: Neste início rápido você usará o Microsoft Intune para enviar notificações por email para dispositivos não compatíveis.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1b89f2d-7937-46bb-926b-b05f6fa9c749
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba835eb76dae19a13985a6175b4eceee0bae7f12
ms.sourcegitcommit: 79baf89e4a7a7b1cecb8ccf5cb976736ae6a7286
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58871426"
---
# <a name="quickstart-send-notifications-to-noncompliant-devices"></a>Início Rápido: Enviar notificações para dispositivos não compatíveis

Neste início rápido, você usará o Microsoft Intune para enviar uma notificação por email para os membros de sua força de trabalho que têm dispositivos não compatíveis.

Por padrão, quando o Intune detecta um dispositivo que não está em conformidade, ele marca imediatamente o dispositivo como não compatível. Em seguida, o [acesso condicional](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) do AAD (Azure Active Directory) bloqueia o dispositivo. Quando um dispositivo não está em conformidade, o Intune permite que você adicione ações de não conformidade, que oferecem mais flexibilidade para decidir o que fazer. Por exemplo, você pode conceder aos usuários um período de cortesia para estar em conformidade antes de bloquear dispositivos não compatíveis.

Uma das ações que você pode realizar quando dispositivos não atendem à conformidade é enviar um email aos usuários finais. Você também pode personalizar uma notificação por email antes de enviá-la para os usuários finais. Especificamente, é possível personalizar os destinatários, o assunto e o corpo da mensagem, incluindo o logotipo da empresa e as informações de contato. O Intune também incluirá detalhes sobre o dispositivo não compatível na notificação por email.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos
- O acesso condicional do AAD precisa ser configurado ao usar políticas de conformidade do dispositivo para impedir que dispositivos usem recursos corporativos. Se você tiver concluído o início rápido [Criar uma política de conformidade do dispositivo](quickstart-set-password-length-android.md), você estará usando o Azure Active Directory. Para obter mais informações sobre o AAD, confira [Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) e [Maneiras comuns de usar o acesso condicional com o Intune](conditional-access-intune-common-ways-use.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no portal do [Intune](https://aka.ms/intuneportal) como um [administrador global](users-add.md#types-of-administrators) ou um [administrador de serviços](users-add.md#types-of-administrators) do Intune. Se você tiver criado uma assinatura de avaliação do Intune, a conta com a qual você criou a assinatura será a de administrador Global.

## <a name="create-a-notification-message-template"></a>Criar um modelo da mensagem de notificação

Para enviar email aos seus usuários, crie um modelo de mensagem de notificação. Quando um dispositivo estiver fora de conformidade, os detalhes inseridos no modelo serão mostrados no email enviado aos seus usuários.

1. No Intune, selecione **Conformidade do dispositivo** > **Notificações** > **Criar notificação**. 
2. Insira as seguintes informações:

   - **Nome**: *Administrador da Contoso*
   - **Assunto**: *Conformidade do dispositivo*
   - **Mensagem**: *No momento, seu dispositivo não atende aos nossos requisitos de conformidade de organizações.*
   - **Cabeçalho do email – Incluir o logotipo da empresa**: Defina como **Habilitado** para mostrar o logotipo da sua organização.
   - **Rodapé do email – Incluir o nome da empresa**: Defina como **Habilitado** para mostrar o nome da sua organização.
   - **Rodapé do email – Incluir informações de contato**: Defina como **Habilitado** para mostrar as informações de contato da sua organização.

   ![Exemplo de uma mensagem de notificação de conformidade no Intune](./media/quickstart-send-notification-01.png)

3. Quando terminar de adicionar as informações, escolha **Criar**. O Modelo da mensagem de notificação está disponível para ser usado.

    > [!NOTE]
    > Você também pode editar um Modelo de notificação criado anteriormente.

Para obter detalhes sobre como configurar o nome, as informações de contato e o logotipo da empresa, confira [Política de privacidade e informações da empresa](company-portal-app.md#company-information-and-privacy-statement), [Informações de suporte](company-portal-app.md#support-information) e [Personalização de marca de identidade da empresa](company-portal-app.md#company-identity-branding-customization). 

## <a name="add-a-noncompliance-policy"></a>Adicionar uma política de não conformidade

Quando você cria uma política de conformidade de dispositivo, o Intune cria automaticamente uma ação de não conformidade. Quando um dispositivo não cumpre sua política de conformidade, o Intune marca o dispositivo automaticamente como não compatível. É possível personalizar por quanto tempo o dispositivo fica marcado como não compatível. É possível adicionar outra ação quando você cria uma política de conformidade ou atualizar uma política de conformidade existente. 

As etapas a seguir criarão uma política de conformidade para dispositivos Windows 10.

1. No Intune, selecione **Conformidade do dispositivo**.
2. Selecione **Políticas** > **Criar Política**.
3. Insira as seguintes informações:

   - **Nome**: *Conformidade do Windows 10*
   - **Descrição**: *política de conformidade do Windows 10*
   - **Plataforma**: Windows 10 e posterior

4. Selecione **Configurações** > **Segurança do Sistema** para exibir as configurações relacionadas à segurança do dispositivo.
5. Defina **Exigir uma senha para desbloquear os dispositivos móveis** como **Exigir**. Essa configuração especifica se os usuários terão que inserir uma senha antes do acesso ser concedido às informações em seus dispositivos móveis. 
6. Defina **Comprimento mínimo da senha** como **6**. Essa configuração especifica o número mínimo de dígitos ou caracteres na senha.

    <img alt="System Security settings for a new compliance policy" src="./media/quickstart-send-notification-02.png" width="600">

7. Clique em **Ok**, **Ok** e **criar** para criar a política de conformidade.
8. Selecione **Propriedades** > **Ação de não conformidade** > **Adicionar**.
9. Na caixa suspensa **Ação**, confirme se a opção **Enviar um email para os usuários finais** está selecionada.
10. Selecione **Modelo de mensagem** > **Administrador da Contoso** > **Selecionar** para selecionar o modelo de mensagem que você criou anteriormente neste tópico.
11. Selecione **ADICIONAR** > **Ok** > **Salvar** para salvar suas alterações.

## <a name="assign-the-policy"></a>Atribuir a política

Você pode atribuir a política de conformidade a um grupo de usuários específico ou para todos os usuários. Quando o Intune reconhecer que um dispositivo não é compatível, o usuário será notificado de que precisa atualizar seu dispositivo para atender à política de conformidade. As etapas a seguir permitem que você atribua a política.

1. Selecione a política **Conformidade do Windows 10** que você criou anteriormente.
2. Selecione **Atribuições**.
3. Na caixa suspensa **Atribuir a**, selecione **Todos os Usuários**. Isso selecionará todos os usuários. Qualquer usuário que tenha um dispositivo **Windows 10 e posterior** será notificado de que não atende a essa política de conformidade do dispositivo.

    > [!NOTE]
    > Você pode incluir e excluir grupos quando atribuir políticas de conformidade.

4. Clique em **Salvar**.

Após criar e salvar a política com êxito, ela aparecerá na lista **Conformidade do dispositivo — Políticas**. Observe na lista que **Atribuído** está configurado como **Sim**.

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você usou o Intune para criar e atribuir uma política de conformidade para os dispositivos Windows 10 da sua força de trabalho para exigir uma senha com pelo menos seis caracteres de comprimento. Para obter mais informações sobre como criar políticas de conformidade para dispositivos Windows, confira [Adicionar uma política de conformidade de dispositivo para dispositivos Windows no Intune](compliance-policy-create-windows.md).

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início rápido: Adicionar e atribuir um aplicativo cliente](quickstart-add-assign-app.md)
