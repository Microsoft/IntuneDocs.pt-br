---
title: 'Tutorial: Proteger o email do Exchange Online em dispositivos não gerenciados'
titleSuffix: Microsoft Intune
description: Saiba como proteger o Office 365 Exchange Online com as políticas de proteção de aplicativo do Intune e Acesso Condicional do Azure AD.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 810a898a3b2d1981babc231f32ed386bde37a856
ms.sourcegitcommit: ce518a5dfe62c546a77f32ef372f36efbaad473f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2019
ms.locfileid: "74465794"
---
# <a name="tutorial-protect-exchange-online-email-on-unmanaged-devices"></a>Tutorial: Proteger o email do Exchange Online em dispositivos não gerenciados

Saiba como usar as políticas de proteção de aplicativo com o Acesso Condicional para proteção do Exchange Online, mesmo quando os dispositivos não estiverem registrados em uma solução de gerenciamento de dispositivo, como o Intune. Neste tutorial, você aprenderá a:

> [!div class="checklist"]
> * Criar uma política de proteção de aplicativo do Intune para o aplicativo Outlook. Você limitará o que o usuário pode fazer com os dados de aplicativo, impedindo a opção "Salvar como" e restringindo ações de recortar, copiar e colar.
> * Crie políticas de Acesso Condicional do Azure AD (Azure Active Directory) que permitem somente ao aplicativo Outlook acessar o email da empresa no Exchange Online. Você também exigirá a autenticação multifator (MFA) para clientes de autenticação moderna, como o Outlook para iOS e o Android.

## <a name="prerequisites"></a>Pré-requisitos

Você precisará de um locatário de teste com as seguintes assinaturas para este tutorial:

- Azure Active Directory Premium ([avaliação gratuita](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
- Assinatura do Intune ([avaliação gratuita](../fundamentals/free-trial-sign-up.md))
- Assinatura do Office 365 Business que inclui o Exchange ([avaliação gratuita](https://go.microsoft.com/fwlink/p/?LinkID=510938))

## <a name="sign-in-to-intune"></a>Entrar no Intune

Para este tutorial, ao entrar no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), entre como [Administrador global](../fundamentals/users-add.md#types-of-administrators) ou [Administrador de serviços](../fundamentals/users-add.md#types-of-administrators) do Intune. Se você criar uma assinatura de avaliação do Intune, a conta com a qual criou a assinatura será a de Administrador global.

## <a name="create-the-app-protection-policy"></a>Criar a política de proteção do aplicativo

Neste tutorial, configuraremos uma política de proteção de aplicativo do Intune para iOS no aplicativo Outlook, a fim de aplicar proteções no nível do aplicativo. Exigiremos um PIN para abrir um aplicativo em um contexto de trabalho. Também limitaremos o compartilhamento de dados entre aplicativos e impediremos a gravação de dados da empresa em um local pessoal.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Aplicativos** > **Políticas de proteção de aplicativo** > **Criar política** e selecione **iOS/iPadOS** para a plataforma.

3. Na página **Noções básicas**, defina as seguintes configurações:

   - **Nome**: Insira **Teste de política de aplicativo do Outlook**.
   - **Descrição**: Insira **Teste de política de aplicativo do Outlook**.

   O valor **Plataforma** é definido como sua opção anterior.

   Clique em **Próximo** para continuar.

4. A página **Aplicativos** permite que você escolha como deseja aplicar essa política a aplicativos em diferentes dispositivos. Configure as seguintes opções:

   - Em **Destino para todos os tipos de aplicativo**: Selecione **Não** e, para **Tipos de aplicativo**, marque a caixa de seleção de **Aplicativos em dispositivos não gerenciados**.
   - Clique em **Selecionar aplicativos públicos**. Na lista Aplicativos, selecione **Outlook** e escolha **Selecionar**.  O Outlook agora aparece em *Aplicativos públicos*.

   Clique em **Próximo** para continuar.

5. A página **Proteção de dados** fornece configurações que determinam como os usuários interagem com os dados nos aplicativos aos quais se aplica essa política de proteção de aplicativo. Configure as seguintes opções:

   Abaixo de *Transferência de Dados*, defina as seguintes configurações, deixando todas as outras com seus valores padrão:

   - Para **Enviar dados da organização para outros aplicativos**, selecione **Nenhum**.  
   - Para **Receber dados de outros aplicativos**, selecione **Nenhum**.  
   - Para **Salvar cópias de dados da organização**, selecione **Bloquear**.  
   - Para **Restringir recortar, copiar e colar entre outros aplicativos**, selecione **Bloqueado**. 

   ![Selecione as configurações de realocação de dados da política de proteção de aplicativo do Outlook](./media/tutorial-protect-email-on-unmanaged-devices/data-protection-settings.png)

   Selecione **Avançar** para continuar.

6. A página **Requisitos de acesso** fornece definições para permitir que você configure os requisitos de PIN e de credenciais aos quais os usuários devem atender para acessar aplicativos em um contexto de trabalho. Defina as seguintes configurações, deixando todas as outras configurações com seus valores padrão:

   - Para **PIN para acesso**, selecione **Exigir**.
   - Para **Credenciais de conta corporativa ou de estudante para acesso**, selecione **Exigir**.

   ![Selecionar as ações de acesso da política de proteção de aplicativo do Outlook](./media/tutorial-protect-email-on-unmanaged-devices/access-requirements-settings.png)

   Selecione **Avançar** para continuar.

7. Esta página **Inicialização condicional** fornece configurações para definir os requisitos de segurança de entrada de sua política de proteção de aplicativo. Para este tutorial, você não precisa definir essas configurações.

   Clique em **Próximo** para continuar.

8. Use a página **Atribuições** para atribuir a política de proteção de aplicativos a grupos de usuários. Neste tutorial, você não atribuirá essa política a um grupo.  
 Não é necessário definir essas configurações.

   Clique em **Próximo** para continuar.

9. Na página **Próximo: Examinar + criar**, examine os valores e as configurações inseridos para esta política de proteção de aplicativo. Clique em **Criar** para criar a política de proteção de aplicativo no Intune.

A política de proteção de aplicativo para Outlook foi criada. Em seguida, você configurará o Acesso Condicional para exigir que os dispositivos usem o aplicativo Outlook.

## <a name="create-conditional-access-policies"></a>Criar políticas de Acesso Condicional

Agora, vamos criar duas políticas de Acesso Condicional para cobrir todas as plataformas de dispositivo.  

- A primeira política exigirá que os clientes de Autenticação Moderna usem o aplicativo Outlook aprovado e a MFA (Autenticação Multifator). Os clientes de Autenticação Moderna incluem o Outlook para iOS e o Outlook para Android.  

- A segunda política exigirá que os clientes do Exchange ActiveSync usem o aplicativo Outlook aprovado. Atualmente, Exchange Active Sync não dá suporte a condições além da plataforma de dispositivo. Configure as políticas de Acesso Condicional ​​no portal do Azure AD ou no portal do Intune. Como já estamos no portal do Intune, vamos criar a política aqui.  

### <a name="create-an-mfa-policy-for-modern-authentication-clients"></a>Criar uma política de MFA para os clientes de autenticação moderna  

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Segurança de ponto de extremidade** >  **Acesso condicional** > **Nova política**.  

3. Para **Nome**, insira **Testar política para clientes de autenticação moderna**.  

4. Em **Atribuições**, selecione **Usuários e Grupos**. Na guia **Incluir**, selecione **Todos os usuários** e, em seguida, **Concluído**.

5. Em **Atribuições**, selecione **Aplicativos de nuvem ou ações**. Como queremos proteger o email do Office 365 Exchange Online, vamos selecioná-lo seguindo estas etapas:

   1. Na guia **Incluir**, escolha **Selecionar aplicativos**.
   2. Escolha **Selecionar**.
   3. Na lista Aplicativos, selecione **Office 365 Exchange Online** e, em seguida, escolha **Selecionar**.
   4. Selecione **Concluído** para retornar ao painel Nova política.

   ![Selecionar o aplicativo do Office 365 Exchange Online](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-cloud-apps.png)

6. Em **Atribuições**, selecione **Condições** > **Plataformas de dispositivos**.

   1. Em **Configurar**, selecione **Sim**.
   2. Na guia **Incluir**, selecione **Qualquer dispositivo**.
   3. Selecione **Concluído**.

7. No painel **Condições**, selecione **Aplicativos clientes**.

   1. Em **Configurar**, selecione **Sim**.
   2. Selecione **Aplicativos móveis e clientes da área de trabalho** e **Clientes de autenticação moderna**.
   3. Desmarque as outras caixas de seleção.
   4. Selecione **Concluído** > **Concluído** para retornar ao painel Nova política.

   ![Selecionar Aplicativos móveis e clientes](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-client-apps.png)

8. Em **Controles de acesso**, selecione **Conceder**.

   1. No painel **Conceder**, selecione **Conceder acesso**.
   2. Selecione **Exigir autenticação multifator**.
   3. Selecione **Exigir aplicativo cliente aprovado**.
   4. Em **Para vários controles**, selecione **Exigir todos os controles selecionados**. Essa configuração garante que os dois requisitos selecionados sejam aplicados quando um dispositivo tentar acessar o email.
   5. Escolha **Selecionar**.

   ![Selecionar controles de acesso](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-mfa.png)

9. Em **Habilitar política**, selecione **Ativa** e selecione **Criar**.

   ![Criar política](./media/tutorial-protect-email-on-unmanaged-devices/enable-policy.png)  

A política de Acesso Condicional para clientes de autenticação moderna foi criada. Agora, você pode criar uma política para clientes do Exchange Active Sync.

### <a name="create-a-policy-for-exchange-active-sync-clients"></a>Criar uma política para clientes do Exchange Active Sync

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Segurança de ponto de extremidade** > **Acesso condicional** > **Nova política**.

3. Para **Nome**, insira **Política de teste para clientes de EAS**.

4. Em **Atribuições**, selecione **Usuários e Grupos**. Na guia *Incluir*, selecione **Todos os usuários** e, em seguida, **Concluído**.

5. Em **Atribuições**, selecione **Aplicativos de nuvem ou ações**. Selecione o email do Office 365 Exchange Online com estas etapas:

   1. Na guia *Incluir*, escolha **Selecionar aplicativos**.
   2. Escolha **Selecionar**.
   3. Na lista de *Aplicativos*, selecione **Office 365 Exchange Online**, escolha **Selecionar** e, então, **Concluído**.
  
6. Em **Atribuições**, selecione **Condições** > **Plataformas de dispositivos**.

   1. Em **Configurar**, selecione **Sim**.
   2. Na guia **Incluir**, selecione **Todos os dispositivos** e, em seguida, **Concluído**.

7. No painel **Condições**, selecione **Aplicativos clientes**.

   1. Em **Configurar**, selecione **Sim**.
   2. Selecione **Aplicativos móveis e clientes de área de trabalho**.
   3. Selecione **Clientes do Exchange ActiveSync** e **Aplicar política somente para plataformas com suporte**.  
   4. Desmarque todas as outras caixas de seleção.  
   5. Selecione **Concluído** e, em seguida, **Concluído** novamente.  

   ![Aplicar a plataformas com suporte](./media/tutorial-protect-email-on-unmanaged-devices/eas-client-apps.png)  

8. Em **Controles de acesso**, selecione **Conceder**.

   1. No painel **Conceder**, selecione **Conceder acesso**.
   2. Selecione **Exigir aplicativo cliente aprovado**. Desmarque todas as outras caixas de seleção.
   3. Escolha **Selecionar**.

   ![Exigir o aplicativo cliente aprovado](./media/tutorial-protect-email-on-unmanaged-devices/eas-grant-access.png)

9. Em **Habilitar política**, selecione **Ativa** e selecione **Criar**.

Suas políticas de proteção de aplicativo e o Acesso Condicional estão em vigor e prontos para teste.

## <a name="try-it-out"></a>Experimente

Com as políticas que você criou, será necessário inscrever os dispositivos no Intune e usar o aplicativo móvel do Outlook para acessar o email do Office 365. Para testar esse cenário em um dispositivo iOS, tente entrar no Exchange Online usando credenciais para um usuário em seu locatário de teste.

1. Para testar em um iPhone, acesse **Ajustes** > **Senhas e Contas** > **Adicionar Conta** > **Exchange**.

2. Digite o endereço de email de um usuário em seu locatário de teste e, em seguida, pressione **Avançar**.  
3. Pressione **Entrar**.

4. Insira a senha do usuário de teste e pressione **Entrar**.

5. A mensagem **Precisa de mais informações** é exibida, ou seja, você está recebendo a solicitação para configurar a MFA. Vá em frente e configure um método de verificação adicional.

6. Em seguida, você verá uma mensagem informando que você está tentando abrir este recurso com um aplicativo que não foi aprovado pelo departamento de TI. A mensagem significa que você está sendo impedido de usar o aplicativo de email nativo. Cancele a entrada.

7. Abra o aplicativo Outlook e selecione **Configurações** > **Adicionar Conta** > **Adicionar Conta de Email**.

8. Digite o endereço de email de um usuário em seu locatário de teste e, em seguida, pressione **Avançar**.

9. Pressione **Entrar com o Office 365**. Você receberá uma solicitação para outro registro e autenticação. Depois de entrar, você poderá testar ações como recortar, copiar, colar e "Salvar como".

## <a name="clean-up-resources"></a>Limpar os recursos

Quando as políticas de teste não forem mais necessárias, é possível removê-las.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivos** **Políticas de conformidade**.

3. Na lista **Nome da política**, selecione o menu de contexto ( **...** ) para sua política de teste e, em seguida, selecione **Excluir**. Selecione **OK** para confirmar.

4. Selecione **Segurança de ponto de extremidade** > **Acesso condicional**.

5. Na lista **Nome da política**, selecione o menu de contexto ( **...** ) para cada uma de suas políticas de teste e, em seguida, selecione **Excluir**. Selecione **Sim** para confirmar.

## <a name="next-steps"></a>Próximas etapas
Neste tutorial, você criou políticas de proteção de aplicativo para limitar as ações do usuário no aplicativo Outlook, e criou as políticas de Acesso Condicional para exigir o aplicativo Outlook e exigir MFA para clientes de autenticação moderna. Para aprender a usar o Intune com Acesso Condicional para proteger outros aplicativos e serviços, confira [Configurar Acesso Condicional](conditional-access.md).
