---
title: 'Início Rápido: criar um perfil de dispositivo de email para dispositivos iOS/iPadOS'
titleSuffix: Microsoft Intune
description: Saiba como usar o Microsoft Intune para criar um perfil de dispositivo de email para que dispositivos iOS/iPadOS possam se conectar ao email da empresa com segurança.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/18/2020
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: af2576c44e0486dbd859a56896db3b7d0ffc6cff
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511061"
---
# <a name="quickstart-create-an-email-device-profile-for-iosipados"></a>Início Rápido: Criar um perfil de dispositivo de email para o iOS/iPadOS

Neste início rápido, você verá como criar um perfil de dispositivo de email para dispositivos iOS/iPadOS. Esse perfil especifica as configurações que são necessárias para que o aplicativo de email interno no dispositivo iOS/iPadOS se conecte ao email da empresa. Os perfis de dispositivo de email ajudam a padronizar as configurações entre os dispositivos e permitem que os usuários finais tenham acesso ao email da empresa em seus dispositivos pessoais sem que precisem fazer qualquer configuração. Para proteger ainda mais seu email, você poderá usar um perfil de email para determinar se os dispositivos estão em conformidade e, em seguida, definir o Acesso Condicional para permitir que somente dispositivos em conformidade acessem o email. Para ver mais detalhes sobre perfis de email, consulte [Como definir as configurações de email no Microsoft Intune](email-settings-configure.md)

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) como Administrador global ou Administrador de serviços do Intune. Se você tiver criado uma assinatura de avaliação do Intune, a conta com a qual você criou a assinatura será a de administrador Global.

## <a name="create-an-iosipados-email-profile"></a>Criar um perfil de email iOS/iPadOS

1. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.

   ![Criar um perfil de email para iOS/iPadOS no Intune](./media/quickstart-email-profile/ios-create-profile.png)

2. Em **Nome**, insira um nome descritivo para o novo perfil. Neste exemplo, digite **iOS exige o email de trabalho**.
3. Digite as seguintes informações do perfil:
    - Em **Descrição**, digite **Exigir que dispositivos iOS/iPadOS usem o email de trabalho**.
    - Em **Plataforma**, selecione **iOS/iPadOS**.
    - Em **Tipo de perfil**, selecione **Email**.

        ![Criar um perfil de email para usar com dispositivos iOS/iPadOS no Intune](./media/quickstart-email-profile/ios-email-profile-name.png)

4. Selecione **Configurações** e insira as seguintes configurações (mantenha os padrões para as demais configurações):
   - **Servidor de email**: Para este início rápido, insira **outlook.office365.com**. Essa configuração especifica o local do Exchange (URL) do servidor de email que o aplicativo de email do iOS/iPadOS usará para se conectar ao email.
   - **Nome da conta**: Insira **Email da Empresa**.
   - **Atributo de nome de usuário do AAD**: Esse nome é o atributo que o Intune obtém do Azure AD (Azure Active Directory). O Intune gera dinamicamente o nome de usuário para este perfil usando esse nome. Para este início rápido, vamos supor que queremos que o **Nome UPN** seja usado como o nome de usuário do perfil (por exemplo, user1@contoso.com).
   - **Atributo de endereço de email do AAD**: Essa configuração é o endereço de email do Azure AD que será usado para entrar no Exchange. Para este início rápido, selecione **Nome UPN**.
   - **Método de autenticação**: Para este início rápido, selecione **Nome de usuário e senha**. (Você também pode escolher **Certificado** caso já tenha configurado um certificado para o Intune.)

        ![Criar um perfil de email para uso do iOS/iPadOS](./media/quickstart-email-profile/ios-email-profile.png)

5. Selecione **OK** > **Criar**. O novo perfil aparece na lista de perfis com o painel exibido para que você possa monitorar como o perfil foi atribuído a dispositivos e usuários iOS/iPadOS.
6. Selecione **Atribuições**.
7. Selecione a guia **Incluir** e escolha **Todos os usuários e todos os dispositivos**. 
8. Selecione **Salvar**.

## <a name="clean-up-resources"></a>Limpar os recursos

Se você não pretende usar o perfil criado para tutoriais adicionais ou de teste, pode excluí-lo agora.

1. No Intune, selecione **Configuração do dispositivo** e selecione **Perfis**.
2. Selecione o perfil de teste que você criou, **iOS/iPadOS exige o email de trabalho**.
3. Selecione as reticências ( **...** ) ao lado do perfil e escolha **Excluir**.

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você criou um perfil de email para dispositivos iOS/iPadOS. Agora você poderá usar esse perfil para determinar se um dispositivo iOS/iPadOS está em conformidade criando uma política de conformidade que marca como não compatível todos os dispositivos iOS/iPadOS que não corresponderem ao perfil. Para aumentar ainda mais a proteção, é possível criar uma política de Acesso Condicional que impede dispositivos iOS/iPadOS não compatíveis de acessar o email. Para obter mais informações sobre as políticas de conformidade do dispositivo, confira [Introdução às políticas de conformidade do dispositivo no Intune](../protect/device-compliance-get-started.md).

> [!div class="nextstepaction"]
> [Tutorial: Proteger o email do Exchange Online em dispositivos gerenciados](../tutorial-protect-email-on-enrolled-devices.md)
