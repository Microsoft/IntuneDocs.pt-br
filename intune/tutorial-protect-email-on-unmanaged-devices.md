---
title: 'Tutorial: Proteger o email do Exchange Online em dispositivos não gerenciados'
titlesuffix: Microsoft Intune
description: Saiba como proteger o Office 365 Exchange Online com as políticas de proteção de aplicativo do Intune e acesso condicional do Azure AD.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/11/2018
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4692e19d657e19efe18a91273ce585eb59c6cb65
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57528268"
---
# <a name="tutorial-protect-exchange-online-email-on-unmanaged-devices"></a>Tutorial: Proteger o email do Exchange Online em dispositivos não gerenciados

Saiba como usar as políticas de proteção de aplicativo com o acesso condicional para proteção do Exchange Online, mesmo quando os dispositivos não estiverem registrados em uma solução de gerenciamento de dispositivo, como o Intune. Neste tutorial, você aprenderá a: 

> [!div class="checklist"]
> * Criar uma política de proteção de aplicativo do Intune para o aplicativo Outlook. Você limitará o que o usuário pode fazer com os dados de aplicativo, impedindo a opção "Salvar como" e restringindo ações de recortar, copiar e colar. 
> * Crie políticas de acesso condicional do Azure AD (Azure Active Directory) que permitem somente ao aplicativo Outlook acessar o email da empresa no Exchange Online. Você também exigirá a autenticação multifator (MFA) para clientes de autenticação moderna, como o Outlook para iOS e o Android.

## <a name="prerequisites"></a>Pré-requisitos
  - Você precisará de um locatário de teste com as seguintes assinaturas para este tutorial:
    - Azure Active Directory Premium ([avaliação gratuita](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
    - Assinatura do Intune ([avaliação gratuita](free-trial-sign-up.md))
    - Assinatura do Office 365 Business que inclui o Exchange ([avaliação gratuita](https://go.microsoft.com/fwlink/p/?LinkID=510938))

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune. O Intune encontra-se no portal do Azure, escolha **Todos os serviços** > **Intune**.

## <a name="create-the-app-protection-policy"></a>Criar a política de proteção do aplicativo
Para este tutorial, configuraremos uma política de proteção de aplicativo do Intune para o aplicativo Outlook, a fim de aplicar proteções no nível do aplicativo. Exigiremos um PIN para abrir um aplicativo em um contexto de trabalho. Também limitaremos o compartilhamento de dados entre aplicativos e impediremos a gravação de dados da empresa em um local pessoal.

1.  No Intune, selecione **Aplicativos clientes** > **Políticas de proteção de aplicativos** > **Adicionar uma política**.
2.  Em **Nome**, insira **Teste de política de aplicativo do Outlook**.
3.  Em **Descrição**, insira **Teste de política de aplicativo do Outlook**.
4.  Selecione **Aplicativos**. Na lista de aplicativos, selecione **Outlook** e escolha **Selecionar**.
5.  Selecione **Configurações**. 
6.  Em **Realocação de dados**, para este tutorial, selecione estas configurações:

    - Para **Permitir que o aplicativo transfira dados para outros aplicativos**, selecione **Nenhum**.
    - Para **Permitir que o aplicativo receba dados de outros aplicativos**, selecione **Nenhum**.
    - Para **Impedir "Salvar como"**, selecione **Sim**.
    - Para **Restringir recortar, copiar e colar com outros aplicativos**, selecione **Bloqueado**.
   
     ![Selecione as configurações de realocação de dados da política de proteção de aplicativo do Outlook](media/tutorial-protect-email-on-unmanaged-devices/outlook-app-data-relocation.png)
    
7.  Em **Ações de Acesso**, para este tutorial, selecione estas configurações:

    - Para **Exigir PIN para acesso**, selecione **Sim**.
    - Para **Exigir credenciais corporativas para acesso**, selecione **Sim**.
    - Deixe todas as outras configurações com seus valores padrão.
 
     ![Selecionar as ações de acesso da política de proteção de aplicativo do Outlook](media/tutorial-protect-email-on-unmanaged-devices/outlook-app-access-actions.png)

9.  Selecione **OK**.
10. Selecione **Criar**.

A política de proteção de aplicativo para Outlook foi criada. Agora, você pode configurar o acesso condicional para exigir que os dispositivos usem o aplicativo Outlook.

## <a name="create-conditional-access-policies"></a>Criar políticas de acesso condicional
Agora, vamos criar duas políticas de acesso condicional para cobrir todas as plataformas de dispositivo. A primeira política exigirá clientes de autenticação moderna, como o Outlook para iOS e o Outlook para Android, para usar o aplicativo Outlook aprovado e MFA. A segunda política exigirá que os clientes do Exchange ActiveSync usem o aplicativo Outlook aprovado. Atualmente, Exchange Active Sync não dá suporte a condições além da plataforma de dispositivo. Configure as políticas de acesso condicional ​​no portal do Azure AD ou no portal do Intune. Como já estamos no portal do Intune, vamos criar a política aqui.
### <a name="create-an-mfa-policy-for-modern-authentication-clients"></a>Criar uma política de MFA para os clientes de autenticação moderna
1.  No Intune, selecione **Acesso condicional** > **Políticas** > **Nova Política**.
1.  Em **Nome**, insira **Testar política para clientes de autenticação moderna**. 
3.  Em **Atribuições**, selecione **Usuários e Grupos**. Na guia **Incluir**, selecione **Todos os usuários** e, em seguida, **Concluído**.

4.  Em **Atribuições**, selecione **Aplicativos de nuvem**. Como queremos proteger o email do Office 365 Exchange Online, vamos selecioná-lo seguindo estas etapas:
     
    1. Na guia **Incluir**, escolha **Selecionar aplicativos**.
    2. Escolha **Selecionar**. 
    3. Na lista de aplicativos, selecione **Office 365 Exchange Online** e, em seguida, escolha **Selecionar**. 
    4. Selecione **Concluído**.
  
    ![Selecionar o aplicativo do Office 365 Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-cloud-apps.png)

5.  Em **Atribuições**, selecione **Condições** > **Plataformas de dispositivos**.
     
    1. Em **Configurar**, selecione **Sim**.
    2. Na guia **Incluir**, selecione **Todas as plataformas (incluindo sem suporte)**. 
    3. Selecione **Concluído**.
   
6.  No painel **Condições**, selecione **Aplicativos clientes**.
     
    1. Em **Configurar**, selecione **Sim**.
    2. Selecione **Aplicativos móveis e clientes da área de trabalho** e **Clientes de autenticação moderna**.
    3. Desmarque as outras caixas de seleção.
    4. Selecione **Concluído** e, em seguida, **Concluído** novamente.
    
    ![Selecionar o aplicativo do Office 365 Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-client-apps.png)

7.  Em **Controles de acesso**, selecione **Conceder**. 
     
    1. No painel **Conceder**, selecione **Conceder acesso**.
    2. Selecione **Exigir autenticação multifator**.
    4. Selecione **Exigir aplicativo cliente aprovado**.
    5. Em **Para vários controles**, selecione **Exigir todos os controles selecionados**. Essa configuração garante que os dois requisitos selecionados sejam aplicados quando um dispositivo tentar acessar o email.
    6. Escolha **Selecionar**.
     
    ![Selecionar o aplicativo do Office 365 Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-mfa.png)

8.  Em **Habilitar política**, selecione **Ativado**.
     
    ![Selecionar o aplicativo do Office 365 Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/enable-policy.png)

9.  Selecione **Criar**.

A política de acesso condicional para clientes de autenticação moderna foi criada. Agora, você pode criar uma política para clientes do Exchange Active Sync.

### <a name="create-a-policy-for-exchange-active-sync-clients"></a>Criar uma política para clientes do Exchange Active Sync
1.  No Intune, selecione **Acesso condicional** > **Políticas** > **Nova Política**.
2.  Em **Nome**, insira **Política de teste para clientes de EAS**. 
3.  Em **Atribuições**, selecione **Usuários e Grupos**. Na guia **Incluir**, selecione **Todos os usuários** e, em seguida, **Concluído**.

4.  Em **Atribuições**, selecione **Aplicativos de nuvem**. Selecione o email do Office 365 Exchange Online com estas etapas:
     
    1. Na guia **Incluir**, escolha **Selecionar aplicativos**.
    2. Escolha **Selecionar**. 
    3. Na lista de aplicativos, selecione **Office 365 Exchange Online** e, em seguida, escolha **Selecionar**. 
    4. Selecione **Concluído**.

5.  Em **Atribuições**, selecione **Condições** > **Plataformas de dispositivos**.
     
    1. Em **Configurar**, selecione **Sim**.
    2. Na guia **Incluir**, selecione **Todas as plataformas (incluindo sem suporte)** e, em seguida, selecione **Concluído**. 
    3. Selecione **Concluído** novamente.

6.  No painel **Condições**, selecione **Aplicativos clientes**.
     
    1. Em **Configurar**, selecione **Sim**.
    2. Selecione **Aplicativos móveis e clientes de área de trabalho**.
    3. Selecione **Clientes do Exchange ActiveSync** e **Aplicar política somente para plataformas com suporte**. 
    4. Desmarque todas as outras caixas de seleção.
    5. Selecione **Concluído** e, em seguida, **Concluído** novamente.
    
    ![Selecionar o aplicativo do Office 365 Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/eas-client-apps.png)

7.  Em **Controles de acesso**, selecione **Conceder**. 
     
    1. No painel **Conceder**, selecione **Conceder acesso**.
    4. Selecione **Exigir aplicativo cliente aprovado**. Desmarque todas as outras caixas de seleção.
    6. Escolha **Selecionar**.
     
    ![Selecionar o aplicativo do Office 365 Exchange Online](media/tutorial-protect-email-on-unmanaged-devices/eas-grant-access.png)

8.  Em **Habilitar política**, selecione **Ativado**.

9.  Selecione **Criar**.

Suas políticas de proteção de aplicativo e o acesso condicional estão em vigor e prontos para teste. 

## <a name="try-it-out"></a>Experimente
Com as políticas que você criou, será necessário inscrever os dispositivos no Intune e usar o aplicativo móvel do Outlook para acessar o email do Office 365. Para testar esse cenário em um dispositivo iOS, tente entrar no Exchange Online usando credenciais para um usuário em seu locatário de teste.
1. Para testar em um iPhone, acesse **Ajustes** > **Senhas e Contas** > **Adicionar Conta** > **Exchange**.
2. Digite o endereço de email de um usuário em seu locatário de teste e, em seguida, pressione **Avançar**.
3. Pressione **Entrar**.
4. Insira a senha do usuário de teste e pressione **Entrar**.
5. A mensagem **Precisa de mais informações** é exibida, ou seja, você está recebendo a solicitação para configurar a MFA. Vá em frente e configure um método de verificação adicional.
6. Em seguida, você verá uma mensagem informando que você está tentando abrir este recurso com um aplicativo que não foi aprovado pelo departamento de TI. Isso significa que você está sendo impedido de usar o aplicativo de email nativo. Cancele a entrada.
7.  Abra o aplicativo Outlook e selecione **Configurações** > **Adicionar Conta** > **Adicionar Conta de Email**.
8. Digite o endereço de email de um usuário em seu locatário de teste e, em seguida, pressione **Avançar**.
9. Pressione **Entrar com o Office 365**. Você receberá uma solicitação para outro registro e autenticação. Depois de entrar, você poderá testar ações como recortar, copiar, colar e "Salvar como".

## <a name="clean-up-resources"></a>Limpar os recursos
Quando as políticas de teste não forem mais necessárias, é possível removê-las.
1. Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune.
2. Selecione **Conformidade do dispositivo** > **Políticas**.
3. Na lista **Nome da política**, selecione o menu de contexto (**...**) para sua política de teste e, em seguida, selecione **Excluir**. Selecione **OK** para confirmar.
4. Selecione **Acesso condicional** > **Políticas**.
5. Na lista **Nome da política**, selecione o menu de contexto (**...**) para cada uma de suas políticas de teste e, em seguida, selecione **Excluir**. Selecione **Sim** para confirmar.

 ## <a name="next-steps"></a>Próximas etapas 
Neste tutorial, você criou políticas de proteção de aplicativo para limitar as ações do usuário no aplicativo Outlook, e criou as políticas de acesso condicional para exigir o aplicativo Outlook e exigir MFA para clientes de autenticação moderna. Para aprender a usar o Intune com acesso condicional para proteger outros aplicativos e serviços, confira [Configurar acesso condicional](conditional-access.md).
