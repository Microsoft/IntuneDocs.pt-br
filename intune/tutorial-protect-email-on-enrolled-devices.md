---
title: 'Tutorial: proteger o email do Exchange Online em dispositivos gerenciados pelo Intune'
titleSuffix: Microsoft Intune
description: Saiba como proteger o Exchange Online com políticas de conformidade do Intune para iOS e acesso condicional do Azure AD para exigir dispositivos gerenciados e o aplicativo do Outlook.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/26/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 80f9d3d2799732f2d019189913c5c47cc6973809
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66044585"
---
# <a name="tutorial-protect-exchange-online-email-on-managed-devices"></a>Tutorial: Proteger o email do Exchange Online em dispositivos gerenciados
Saiba como usar políticas de conformidade de dispositivo com acesso condicional para garantir que os dispositivos iOS acessem emails do Exchange Online somente se forem gerenciados pelo Intune e usarem um aplicativo de email aprovado. 

Neste tutorial, você aprenderá a: 
> [!div class="checklist"]
> * Criar uma política de conformidade do Intune para dispositivos iOS a fim de definir as condições que um dispositivo deve atender para ser considerado compatível.
> * Criar uma política de acesso condicional do Azure Active Directory (Azure AD) que exija que os dispositivos iOS se inscrevam no Intune, cumpram as políticas do Intune e usem o aplicativo móvel Outlook aprovado para acessar o email do Exchange Online.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos
  - Você precisará de um locatário de teste com as seguintes assinaturas para este tutorial:
    - Azure Active Directory Premium ([avaliação gratuita](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
    - Assinatura do Office 365 Business que inclui o Exchange ([avaliação gratuita](https://go.microsoft.com/fwlink/p/?LinkID=510938))
  - Antes de começar, crie um perfil de dispositivo de teste para dispositivos iOS seguindo as etapas no [Início Rápido: Criar um perfil de dispositivo de email para iOS](quickstart-email-profile.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune. Se você tiver criado uma assinatura de avaliação do Intune, a conta com a qual você criou a assinatura será a de administrador Global.

## <a name="create-the-ios-device-compliance-policy"></a>Criar a política de conformidade para o dispositivo iOS
Definir uma política de conformidade do Intune para dispositivos a fim de definir as condições que um dispositivo deve atender para ser considerado compatível. Para este tutorial, criaremos uma política de conformidade do dispositivo para dispositivos iOS. As políticas de conformidade são específicas da plataforma, portanto, você precisa de uma política de conformidade separada para cada plataforma de dispositivo que deseja avaliar.

1.  No Intune, selecione **Conformidade do dispositivo** > **Políticas** > **Criar política**.
2.  Em **Nome**, insira **Teste de Política de Conformidade do iOS**. 
3.  Em **Descrição**, insira **Teste de política de conformidade do iOS**.
4.  Em **Plataforma**, selecione **iOS**. 
5.  Selecione **Configurações** > **Email**. 
     
    1.  Próximo a **Exigir que os dispositivos móveis tenham um perfil de email gerenciado**, selecione **Exigir**.
    2. Selecione **OK**.

    ![Definir a política de conformidade de email para exigir um perfil de email gerenciado](media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-email.png)
    
6.  Selecione **Integridade do Dispositivo**. Próximo a **Dispositivos com jailbreak**, selecione **Bloquear** e, em seguida, selecione **OK**.
7.  Selecione **Segurança do Sistema** e insira as configurações de **Senha**. Para este tutorial, selecione as seguintes configurações recomendadas:
     
    - Em **Exigir uma senha para desbloquear os dispositivos móveis**, selecione **Exigir**.
    - Em **Senhas simples**, selecione **Bloquear**.
    - Em **Tamanho mínimo da senha**, insira **4**.
    - Em **Tipo de senha obrigatório**, escolha **Alfanumérica**.
    - Em **Máximo de minutos após o bloqueio de tela antes que a senha seja necessária**, escolha **Imediatamente**.
    - Em **Expiração de senha (dias)**, insira **41**.
    - Em **Número de senhas anteriores para evitar a reutilização**, insira **5**.
 
    ![Definir configurações de senha para a política de conformidade de email](media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-system-security.png)

8.  Selecione **OK** e, em seguida, **OK** novamente.
9.  Selecione **Criar**.

## <a name="create-the-conditional-access-policy"></a>Criar a política de acesso condicional
Agora, criaremos uma política de acesso condicional que exige que todas as plataformas de dispositivos se inscrevam no Intune e cumpram nossa política de conformidade do Intune para que possam acessar o Exchange Online. Também exigiremos o aplicativo do Outlook para acessar o email. Políticas de acesso condicional são configuráveis ​​no portal do Azure AD ou no portal do Intune. Como já estamos no portal do Intune, vamos criar a política aqui.
1.  No Intune, selecione **Acesso condicional** > **Políticas** > **Nova Política**.
1.  Em **Nome**, insira **Política de teste para email do Office 365**. 
3.  Em **Atribuições**, selecione **Usuários e Grupos**. Na guia **Incluir**, selecione **Todos os usuários** e, em seguida, **Concluído**.

4.  Em **Atribuições**, selecione **Aplicativos de nuvem**. Como queremos proteger o email do Office 365 Exchange Online, vamos selecioná-lo seguindo estas etapas:
     
    1. Na guia **Incluir**, escolha **Selecionar aplicativos**.
    2. Escolha **Selecionar**. 
    3. Na lista de aplicativos, selecione **Office 365 Exchange Online** e, em seguida, escolha **Selecionar**. 
    4. Selecione **Concluído**.
  
    ![Selecionar o aplicativo do Office 365 Exchange Online](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-apps.png)

5.  Em **Atribuições**, selecione **Condições** > **Plataformas de dispositivos**.
     
    1. Em **Configurar**, selecione **Sim**.
    2. Na guia **Incluir**, selecione **Todos os dispositivos** e, em seguida, **Concluído**. 
    3. Selecione **Concluído** novamente.
   
    ![Selecionar o aplicativo do Office 365 Exchange Online](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-device-platforms.png)

6.  Em **Atribuições**, selecione **Condições** > **Aplicativos cliente**.
     
    1. Em **Configurar**, selecione **Sim**.
    2. Para este tutorial, selecione **Aplicativos móveis e clientes de área de trabalho** e **Clientes de autenticação modernos** (que se referem a aplicativos como o Outlook para iOS e o Outlook para Android). Desmarque todas as outras caixas de seleção.
    3. Selecione **Concluído** e, em seguida, **Concluído** novamente.
    
    ![Selecionar o aplicativo do Office 365 Exchange Online](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-client-apps.png)

7.  Em **Controles de acesso**, selecione **Conceder**. 
     
    1. No painel **Conceder**, selecione **Conceder acesso**.
    2. Selecione **Exigir que o dispositivo seja marcado como em conformidade**. 
    3. Selecione **Exigir aplicativo cliente aprovado**.
    4. Em **Para vários controles**, selecione **Exigir todos os controles selecionados**. Essa configuração garante que os dois requisitos selecionados sejam aplicados quando um dispositivo tentar acessar o email.
    5. Escolha **Selecionar**.
     
    ![Selecionar o aplicativo do Office 365 Exchange Online](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-grant-access.png)

8.  Em **Habilitar política**, selecione **Ativado**.
     
    ![Selecionar o aplicativo do Office 365 Exchange Online](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-enable-policy.png)

9.  Selecione **Criar**.

## <a name="try-it-out"></a>Experimente
Com as políticas que você criou, qualquer dispositivo iOS que tente entrar no email do Office 365 precisará se inscrever no Intune e usar o aplicativo móvel do Outlook para iOS. Para testar esse cenário em um dispositivo iOS, tente entrar no Exchange Online usando credenciais para um usuário em seu locatário de teste. Você será solicitado a inscrever o dispositivo e instalar o aplicativo móvel do Outlook.
1. Para testar em um iPhone, acesse **Ajustes** > **Senhas e Contas** > **Adicionar Conta** > **Exchange**.
2. Digite o endereço de email de um usuário em seu locatário de teste e, em seguida, pressione **Avançar**.
3. Pressione **Entrar**.
4. Insira a senha do usuário de teste e pressione **Entrar**.
5. É exibida uma mensagem informando que seu dispositivo deve ser gerenciado para acessar o recurso, com uma opção para se inscrever. 

## <a name="clean-up-resources"></a>Limpar os recursos
Quando as políticas de teste não forem mais necessárias, é possível removê-las.
1. Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune.
2. Selecione **Conformidade do dispositivo** > **Políticas**.
3. Na lista **Nome da política**, selecione o menu de contexto (**...**) para sua política de teste e, em seguida, selecione **Excluir**. Selecione **OK** para confirmar.
4. Selecione **Acesso condicional** > **Políticas**.
5. Na lista **Nome da política**, selecione o menu de contexto (**...**) para sua política de teste e, em seguida, selecione **Excluir**. Selecione **Sim** para confirmar.

 ## <a name="next-steps"></a>Próximas etapas 
Neste tutorial, você criou políticas que exigem que os dispositivos iOS se inscrevam no Intune e usem o aplicativo do Outlook para acessar o email do Exchange Online. Para aprender a usar o Intune com acesso condicional para proteger outros aplicativos e serviços, incluindo clientes do Exchange ActiveSync para o Office 365 Exchange Online, confira [Configurar acesso condicional](conditional-access.md).
