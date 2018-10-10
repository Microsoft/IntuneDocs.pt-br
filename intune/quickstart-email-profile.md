---
title: Início Rápido – Criar um perfil de dispositivo de email para iOS
titlesuffix: Microsoft Intune
description: Saiba como usar o Microsoft Intune para criar um perfil de dispositivo de email para que dispositivos iOS possam se conectar ao email da empresa com segurança.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b797951c878dd90cbb7bb716b5108f94f48921c5
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48231943"
---
# <a name="quickstart-create-an-email-device-profile-for-ios"></a>Início Rápido: criar um perfil de dispositivo de email para iOS

Neste início rápido, você verá como criar um perfil de dispositivo de email para dispositivos iOS. Esse perfil especifica as configurações que são necessárias para que o aplicativo de email interno no dispositivo iOS se conecte ao email da empresa. Os perfis de dispositivo de email ajudam a padronizar as configurações entre os dispositivos e permitem que os usuários finais tenham acesso ao email da empresa em seus dispositivos pessoais sem que precisem fazer qualquer configuração. Para proteger ainda mais seu email, você poderá usar um perfil de email para determinar se os dispositivos estão em conformidade e, em seguida, definir o acesso condicional para permitir que somente dispositivos em conformidade acessem o email. Para ver mais detalhes sobre perfis de email, consulte [Como definir as configurações de email no Microsoft Intune](email-settings-configure.md)

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune. O Intune encontra-se no portal do Azure, escolha **Todos os serviços** > **Intune**.

## <a name="create-an-ios-email-profile"></a>Criar um perfil de email iOS
1. No Intune, selecione **Configuração do dispositivo** e selecione **Perfis**.
2. Selecione **Criar Perfil**.
   
   ![Criar um perfil de email para iOS](media/quickstart-email-profile/ios-create-profile.png)

3. Em **Nome**, insira um nome descritivo para o novo perfil. Neste exemplo, digite **iOS exige o email de trabalho**.
4. Digite as seguintes informações do perfil:
   - Em **Descrição**, digite **Exigir que dispositivos iOS usem o email de trabalho**.
   - Selecione **Plataforma** para **iOS**.
   - Em **Tipo de perfil**, selecione **Email**.
    
     ![Criar um perfil de email para iOS](media/quickstart-email-profile/ios-email-profile-name.png)

5. Selecione **Configurações** e insira as seguintes configurações (mantenha os padrões para as demais configurações):
   - **Servidor de email**: para este início rápido, insira **outlook.office365.com**. Essa configuração especifica o local do Exchange (URL) do servidor de email que o aplicativo de email do iOS usará para se conectar ao email.
   - **Nome da conta**: insira **Email da empresa**.
   - **Atributo de nome de usuário do AAD**: esse nome é o atributo que o Intune obtém do Microsoft Azure AD (Azure Active Directory). O Intune gera dinamicamente o nome de usuário para este perfil usando esse nome. Para este início rápido, vamos supor que queremos que o **Nome UPN** seja usado como o nome de usuário do perfil (por exemplo, user1@contoso.com).
   - **Atributo de endereço de email do AAD**: essa configuração é o endereço de email do Microsoft Azure AD que será usado para entrar no Exchange. Para este início rápido, selecione **Nome UPN**.
   - **Método de autenticação**: para este início rápido, selecione **Nome de usuário e senha**. (Você também pode escolher **Certificado** caso já tenha configurado um certificado para o Intune.)
    
     ![Criar um perfil de email para iOS](media/quickstart-email-profile/ios-email-profile.png)

6. Selecione **OK**.
7. Selecione **Criar**. O novo perfil aparece na lista de perfis com o painel exibido para que você possa monitorar como o perfil foi atribuído a dispositivos e usuários iOS.
8. Selecione **Atribuições**.
9. Selecione a guia **Incluir** e escolha **Todos os usuários e todos os dispositivos**. 
10. Selecione **Salvar**.

## <a name="clean-up-resources"></a>Limpar os recursos
Se você não pretende usar o perfil criado para tutoriais adicionais ou de teste, pode excluí-lo agora.
1. No Intune, selecione **Configuração do dispositivo** e selecione **Perfis**.
2. Selecione o perfil de teste que você criou, **iOS exige o email de trabalho**.
3. Selecione as reticências (**...**) ao lado do perfil e escolha **Excluir**.

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você criou um perfil de email para dispositivos iOS. Agora você poderá usar esse perfil para determinar se um dispositivo iOS está em conformidade criando uma política de conformidade que marca como não compatível todos os dispositivos iOS que não corresponderem ao perfil. Para aumentar ainda mais a proteção, é possível criar uma política de acesso condicional que impede dispositivos iOS não compatíveis de acessar o email.

> [!div class="nextstepaction"]
> [Introdução às políticas de conformidade do dispositivo no Intune](device-compliance-get-started.md)
