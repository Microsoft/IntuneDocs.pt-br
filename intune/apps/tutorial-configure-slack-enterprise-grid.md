---
title: 'Tutorial: configurar o Slack para usar o Intune para EMM e configuração de aplicativos'
titleSuffix: Microsoft Intune
description: Neste tutorial, você configurará o Slack para usar o Intune para EMM e configuração de aplicativos.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 55db37c5-0da7-4d9c-8027-525afb1c6349
Customer intent: As an Intune admin, I want to learn how to configure Slack to use Intune for EMM and app configuration..
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f5045e78eaca19e5a78468c7c4b6698e4e1a5019
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511541"
---
# <a name="tutorial-configure-slack-to-use-intune-for-emm-and-app-configuration"></a>Tutorial: Configurar o Slack para usar o Intune para EMM e configuração de aplicativos

Slack é um aplicativo de colaboração que você pode usar com o Microsoft Intune.   

Neste tutorial, você vai:
> [!div class="checklist"]
> - Configurar o Intune como o provedor de Gerenciamento de Mobilidade Empresarial (EMM) no seu Slack Enterprise Grid. Você poderá limitar o acesso aos workspaces do plano da sua grade para dispositivos gerenciados pelo Intune.
> - Criar políticas de configuração do aplicativo para gerenciar o aplicativo Slack no iOS/iPadOS e o aplicativo Slack para dispositivos de perfil de trabalho do Android.
> - Criar uma política de conformidade de dispositivos do Intune a fim de definir as condições que os dispositivos Android e iOS/iPadOS devem atender para serem considerados compatíveis.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos
Você precisará de um locatário de teste com as seguintes assinaturas para este tutorial:
- Azure Active Directory Premium ([avaliação gratuita](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
- Assinatura do Intune ([avaliação gratuita](../fundamentals/free-trial-sign-up.md))

Você também precisará de um plano [Slack Enterprise Grid](https://get.slack.help/hc/articles/360004150931-What-is-Slack-Enterprise-Grid-).

## <a name="configure-your-slack-enterprise-grid-plan"></a>Configurar seu plano Slack Enterprise Grid
Ativar o EMM para seu plano Slack Enterprise Grid seguindo as [instruções do Slack](https://get.slack.help/hc/articles/115002579426-Enable-Enterprise-Mobility-Management-for-your-org#step-2:-turn-on-emm) e [conectando o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/saas-apps/slack-tutorial) como provedor de identidade (IDP) do plano da sua grade.

## <a name="sign-in-to-intune"></a>Entrar no Intune
Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) como Administrador global ou Administrador de Serviços do Intune. Se você tiver criado uma assinatura de avaliação do Intune, a conta com a qual você criou a assinatura será a de administrador Global.

## <a name="set-up-slack-for-emm-on-ios-devices"></a>Configurar o Slack para EMM em dispositivos iOS
Adicione o aplicativo Slack para EMM do iOS/iPadOS ao seu locatário do Intune e crie uma política de configuração do aplicativo para permitir que os usuários do iOS/iPadOS de sua organização acessem o Slack com o Intune como provedor de EMM.

### <a name="add-slack-for-emm-to-intune"></a>Adicionar o Slack para EMM ao Intune
Adicione o Slack para EMM como um aplicativo gerenciado para iOS/iPadOS no Intune e atribua os usuários do Slack. Os aplicativos são específicos da plataforma; portanto, você precisará adicionar um aplicativo do Intune separado para seus usuários Slack em dispositivos Android.
1. No Centro de administração, escolha **Aplicativos** > **Todos aplicativos** > **Adicionar**.
2. Em **Tipo de aplicativo**, escolha aplicativo da loja **iOS**.
3. Selecione **Pesquisar na App Store**. Insira o termo de pesquisa "Slack para EMM" e selecione o aplicativo. Clique em **Selecionar** no painel **Pesquisar na App Store**.
4. Selecione **Informações do aplicativo** e configure todas as alterações necessárias. Escolha **OK** para definir as informações do aplicativo.
5. Clique em **Adicionar**.
6. Selecione **Atribuições**.
7. Clique em **Adicionar grupo**. Dependendo do que você escolheu que seria afetado quando você ativasse o EMM para Slack, em **Tipo de atribuição**, selecione:
    - **Disponível para dispositivos registrados** se você tiver escolhido "Todos os membros (inclusive convidados)" OU
    - **Disponível com ou sem registro** se você tiver escolhido "Todos os membros (exceto os convidados)" ou "Opcional".
8. Marque **Grupos Incluídos** e, em **Tornar este aplicativo disponível para todos os usuários**, escolha **Sim**.
9. Clique em **OK** e em **OK** novamente para adicionar o grupo.
10. Clique em **Salvar**.

### <a name="add-an-app-configuration-policy-for-slack-for-emm"></a>Adicionar uma política de configuração do aplicativo para Slack para EMM
Adicione uma política de configuração do aplicativo para Slack para EMM para iOS/iPadOS. As políticas de configuração de aplicativo para dispositivos gerenciados são específicas da plataforma; portanto, você precisará adicionar uma política separada para seus usuários do Slack em dispositivos Android.
1. No centro de administração, escolha **Aplicativos** > **Políticas de configuração de aplicativo** > **Adicionar** > **Dispositivos gerenciados**.
2. Em Nome, digite “Teste de política de configuração do aplicativo Slack”.
3. Em Tipo de registro de dispositivos, confirme se **Dispositivos gerenciados** está definido.
4. Em Plataforma, selecione **iOS**.
5. Selecione **Aplicativo associado**.
6. Na barra de pesquisa, digite "Slack para EMM" e selecione o aplicativo.
7. Clique em **OK** e, em seguida, selecione **Parâmetros de configuração**. 
8. Selecione **OK** e **Adicionar**.
9. Na barra de pesquisa, digite "Teste de política de configuração do aplicativo Slack" e selecione a política que você acabou de adicionar.
10. Em Gerenciar, selecione **Atribuições**.
11. Em Atribuir a, selecione **Todos os usuários + Todos os dispositivos**.
12. Clique em **Salvar**.

### <a name="optional-create-an-ios-device-compliance-policy"></a>(Opcional) Criar uma política de conformidade para o dispositivo iOS
Definir uma política de conformidade do Intune para dispositivos a fim de definir as condições que um dispositivo deve atender para ser considerado compatível. Para este tutorial, criaremos uma política de conformidade do dispositivo para dispositivos iOS/iPadOS. As políticas de conformidade são específicas da plataforma; portanto, você precisará criar uma política separada para seus usuários do Slack em dispositivos Android.
1. No centro de administração, escolha **Conformidade do dispositivo** > **Políticas** > **Criar política**.
2. Em Nome, insira “Teste de política de conformidade do iOS”.
3. Em Descrição, insira “Teste de política de conformidade do iOS”.
4. Em Plataforma, selecione **iOS**.
5. Selecione **Integridade do Dispositivo**. Próximo a Dispositivos com jailbreak, selecione **Bloquear** e, em seguida, selecione **OK**.
6. Selecione **Segurança do Sistema** e insira as configurações de Senha. Para este tutorial, selecione as seguintes configurações recomendadas:
    - Em Exigir uma senha para desbloquear os dispositivos móveis, selecione **Exigir**.
    - Em Senhas simples, selecione **Bloquear**.
    - Em Tamanho mínimo da senha, insira 4.
    - Em Tipo de senha obrigatório, escolha **Alfanumérica**.
    - Em Máximo de minutos após o bloqueio de tela antes que a senha seja necessária, escolha **Imediatamente**.
    - Em Expiração de senha (dias), insira 41.
    - Em Número de senhas anteriores para evitar a reutilização, insira 5.
7. Clique em **OK** e em **OK** novamente.
8. Clique em **Criar**.

## <a name="set-up-slack-on-android-work-profile-devices"></a>Configurar os dispositivos de perfil de trabalho do Slack no Android
Adicione o aplicativo do Google Play gerenciado para Slack ao seu locatário do Intune e crie uma política de configuração de aplicativo para permitir que os usuários do Android de sua organização acessem o Slack com o Intune como provedor de EMM.

### <a name="add-slack-to-intune"></a>Adicionar Slack ao Intune
Adicione o aplicativo Slack como um aplicativo gerenciado do Google Play no Intune e atribua os usuários do Slack. Os aplicativos são específicos da plataforma; portanto, você precisará adicionar um aplicativo do Intune separado para seus usuários Slack em dispositivos iOS/iPadOS.
1. No Intune, selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
2. Em Tipo de aplicativo, selecione **Loja do aplicativo – Google Play gerenciado**.
3. Selecione **Google Play gerenciado - Aprovar**. Insira o termo de pesquisa "Slack para EMM" e selecione o aplicativo.
4. Selecione **Aprovar**.
5. Na barra de pesquisa, digite "Slack" e selecione o aplicativo que você acabou de adicionar.
6. Em Gerenciar, selecione **Atribuições**.
7. Selecione **Adicionar grupo**. Dependendo do que você escolheu que seria afetado quando você ativasse o EMM para Slack, em **Tipo de atribuição**, selecione:
    - **Disponível para dispositivos registrados** se você tiver escolhido "Todos os membros (inclusive convidados)" OU
    - **Disponível com ou sem registro** se você tiver escolhido "Todos os membros (exceto os convidados)" ou "Opcional".
8. Selecione Grupos Incluídos e em Tornar este aplicativo disponível para todos os usuários, selecione **Sim**.
9. Clique em **OK** e em **OK** novamente.
10. Clique em **Salvar**.

### <a name="add-an-app-configuration-policy-for-slack"></a>Adicionar uma política de configuração do aplicativo para Slack
Adicione uma política de configuração do aplicativo para Slack. As políticas de configuração do aplicativo para dispositivos gerenciados são específicas da plataforma; portanto, você precisará adicionar uma política separada para seus usuários do Slack em dispositivos iOS/iPadOS.
1. No Intune, escolha **Aplicativos** > **Políticas de configuração de aplicativo** > **Adicionar**.
2. Em Nome, digite teste de política de configuração do aplicativo Slack.
3. Em Tipo de registro de dispositivos, selecione **Dispositivos gerenciados**.
4. Em Plataforma, selecione **Android**.
5. Selecione **Aplicativo associado**.
6. Na barra de pesquisa, digite "Slack" e selecione o aplicativo.
7. Selecione **OK** e, em seguida, selecione **Parâmetros de configuração**.
    - Para saber mais sobre chaves de configuração e seus valores, confira a documentação na guia "Técnico" da [página da Web AppConfig do Slack](https://www.appconfig.org/company/slack/).
8. Clique em **OK** e em **Adicionar**.
9. Na barra de pesquisa, digite "Teste de política de configuração do aplicativo Slack" e selecione a política que você acabou de adicionar.
10. Em Gerenciar, selecione **Atribuições**.
11. Em Atribuir a, selecione **Todos os usuários + Todos os dispositivos**.
12. Clique em **Salvar**.

### <a name="optional-create-an-android-device-compliance-policy"></a>(Opcional) Criar uma política de conformidade para o dispositivo Android
Definir uma política de conformidade do Intune para dispositivos a fim de definir as condições que um dispositivo deve atender para ser considerado compatível. Para este tutorial, criaremos uma política de conformidade do dispositivo para dispositivos Android. As políticas de conformidade são específicas da plataforma, portanto, você precisará criar uma diretiva separada para seus usuários Slack em dispositivos iOS/iPadOS.
1. No Intune, selecione **Conformidade do dispositivo** > **Políticas** > **Criar política**.
2. Em Nome, insira “Teste de Política de Conformidade do Android”.
3. Em Descrição, insira “Teste de Política de Conformidade do Android”.
4. Para Plataforma, selecione **Android Enterprise**.
5. Em Tipo de perfil, selecione **Perfil de trabalho**.
6. Selecione **Integridade do Dispositivo**. Ao lado de Dispositivos desbloqueados, selecione **Bloquear** e, em seguida, selecione **OK**.
7. Selecione **Segurança do Sistema** e insira as configurações de **Senha**. Para este tutorial, selecione as seguintes configurações recomendadas:
    - Em Exigir uma senha para desbloquear os dispositivos móveis, selecione **Exigir**.
    - Em Tipo de senha obrigatório, selecione **Ao menos alfanumérico**.
    - Em Tamanho mínimo da senha, insira 4.
    - Em Máximo de minutos após o bloqueio de tela antes que a senha seja necessária, escolha **15 minutos**.
    - Em Expiração de senha (dias), insira 41.
    - Em Número de senhas anteriores para evitar a reutilização, insira 5.
8. Clique em **OK** e em **OK** novamente.
9. Clique em **Criar**.

## <a name="launch-slack"></a>Iniciar o Slack

Com as políticas que você acabou de criar, qualquer dispositivo de perfil de trabalho iOS/iPadOS ou Android que tentar entrar em um dos seus workspaces precisará ser registrado no Intune. Para testar este cenário, tente iniciar o Slack para EMM em um dispositivo do iOS/iPadOS registrado no Intune ou inicie o Slack em um dispositivo de perfil de trabalho do Android registrado no Intune. 

## <a name="next-steps"></a>Próximas etapas

Neste tutorial:
- você configurou o Intune como o provedor de gerenciamento de mobilidade empresarial (EMM) na sua grade de empresa do Slack. 
- Criou políticas de configuração do aplicativo para gerenciar o aplicativo Slack no iOS/iPadOS e o aplicativo Slack para dispositivos de perfil de trabalho do Android.
- Criou uma política de conformidade de dispositivos do Intune a fim de definir as condições que os dispositivos Android e iOS/iPadOS devem atender para serem considerados compatíveis.

Para saber mais sobre políticas de configuração de aplicativo, confira [Políticas de configuração de aplicativo para o Microsoft Intune](app-configuration-policies-overview.md). Para saber mais sobre políticas de conformidade com dispositivos, confira [Definir regras em dispositivos para permitir o acesso aos recursos em sua organização usando o Intune](../protect/device-compliance-get-started.md).
