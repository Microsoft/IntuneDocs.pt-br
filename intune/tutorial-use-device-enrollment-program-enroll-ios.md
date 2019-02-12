---
title: Tutorial – usar a conta Programa de registro de dispositivos para registrar dispositivos iOS no Intune
titleSuffix: Microsoft Intune
description: Neste tutorial, você configurará o DEP da Apple para registrar dispositivos iOS no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/30/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Device Enrollment Program so that users can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: 17258ce2bd671dba091fa7206e599858e5ec7a93
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841531"
---
# <a name="tutorial-use-the-device-enrollment-program-to-enroll-ios-devices-in-intune"></a>Tutorial: Usar a conta Programa de Registro de Dispositivos para registrar dispositivos iOS no Intune
O DEP (Programa de registro de dispositivos) da Apple simplifica o registro de dispositivos. Com o Microsoft Intune e o DEP, os dispositivos são registrados automaticamente na primeira vez em que o usuário liga o dispositivo. Assim, você pode enviar dispositivos para vários usuários sem a necessidade de configurar cada dispositivo individualmente. 

Neste tutorial, você aprenderá a:
> [!div class="checklist"]
> * Obtenha um token DEP da Apple
> * Criar um grupo de dispositivos do Autopilot
> * Criar um perfil de implantação do Autopilot
> * Atribuir um perfil de implantação do Autopilot a um grupo de dispositivos
> * Distribuir dispositivos Windows a usuários

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos
- Dispositivos comprados no [Programa de registro de dispositivos da Apple](http://deploy.apple.com)
- Defina a [autoridade de gerenciamento de dispositivo móvel](mdm-authority-set.md)
- Obtenha um [certificado push de MDM da Apple](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Obtenha um token DEP da Apple
Antes de registrar dispositivos iOS com o DEP, você precisará de um arquivo de token do DEP da Apple (.pem). Esse token permite que o Intune sincronize informações sobre os dispositivos do DEP de sua empresa. Ele também permite que o Intune carregue perfis de registro para a Apple e atribua novos dispositivos a esses perfis.

Você pode usar o portal de DEP da Apple para criar um token de DEP. Você também pode usar o portal de DEP para atribuir dispositivos ao Intune para gerenciamento.

1. No [Intune no Portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens do Programa de Registro** > **Adicionar**.

2. Conceder permissão à Microsoft para enviar informações de usuário e dispositivo para a Apple selecionando **Eu concordo**.

   ![Captura de tela do painel do Token de Programa de Registro no workspace de Certificados da Apple para baixar a chave pública.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Escolha **Baixar sua chave pública** para baixar e salvar o arquivo da chave de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Programa de registro de dispositivo da Apple.

4. Escolha **Criar um token para o Programa de registro de dispositivos da Apple** para abrir o Portal do Programa de Implantação da Apple e entrar com sua ID da Apple da empresa. Você pode usar essa ID da Apple para renovar seu token de DEP.

5.  No [Portal de Programas de Implantação](https://deploy.apple.com) da Apple, escolha **Começar** para **Programa de registro de dispositivos**.

4. Na página **Gerenciar Servidores**, escolha **Adicionar servidor MDM**.

5. Para **Nome do Servidor MDM**, insira *TestMDMServer* e, em seguida, escolha **Avançar**. O nome do servidor é para sua referência para identificar o servidor MDM (gerenciamento de dispositivo móvel). Não é o nome ou URL do servidor Microsoft Intune.

6. A caixa de diálogo **Adicionar &lt;ServerName&gt;** é aberta, indicando abre a caixa de diálogo, indicando **Carregar sua chave pública**. Escolha **Escolher Arquivo…** para carregar o arquivo .pem e clique em **Avançar**.

6. Vá para **Programas de Implantação** > **Programa de Registro de Dispositivos** > **Gerenciar Dispositivos**.
7. Em **Escolher Dispositivos Por**, escolha **Número de Série**. <!--ask Tiffany about this-->

8. Para **Escolher Ação**, escolha **Atribuir ao Servidor**, escolha o &lt;ServerName&gt; especificado para o Microsoft Intune e escolha **OK**. O Portal da Apple atribui os dispositivos especificados para o servidor do Intune para gerenciamento e exibe **Atribuição Concluída**.

   No Portal da Apple, acesse **Programas de Implantação** &gt; **Programa de registro de dispositivos** &gt; **Exibir o Histórico de Atribuição** para ver uma lista de dispositivos e sua atribuição de servidor MDM.

9. Para referência futura, no Intune, no portal do Azure, forneça a ID Apple usada para criar esse token.

    ![Captura de tela mostrando a especificação do ID Apple usado para criar o Token do Programa de Registro e a navegação para este recurso.](./media/device-enrollment-program-enroll-ios/image03.png)

10. Na caixa **Token da Apple**, navegue até o arquivo de certificado (.pem), escolha **Abrir** e, em seguida, escolha **Criar**. 

## <a name="create-an-apple-enrollment-profile"></a>Criar um perfil de registro da Apple
Agora que você instalou o token, pode criar um perfil de registro para dispositivos do DEP. Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro**.

2. Selecione o token que você acabou de instalar, escolha **Perfis** > **Criar perfil**.

3. Em **Criar perfil**, insira *TestDEPProfile* para **Nome** e *Teste DEP para dispositivos iOS* para **Descrição**. Os usuários não veem esses detalhes.

4. Para **Afinidade de Usuário**, escolha **Registrar com Afinidade de Usuário**. Essa opção é para dispositivos que pertencem a usuários que desejam usar o Portal da Empresa para serviços como a instalação de aplicativos.

5. Escolha **Não** em **Autenticar com o Portal da Empresa em vez do Assistente de Configuração da Apple**.

6. Escolha **Configurações de Gerenciamento de Dispositivo** e escolha **Nenhum** em **Supervisionado**. Dispositivos supervisionados oferecem mais opções de gerenciamento, mas você não usá-lo para os fins deste tutorial.

7. Selecione **OK**.

8. Escolha **Personalização do Assistente de Instalação** e insira *Departamento de tutorial* para **Nome do Departamento**. Essa cadeia de caracteres é o que os usuários veem quando tocam em **Sobre a configuração** durante a ativação do dispositivo.

9. Em **Telefone do Departamento**, insira um número de telefone. Esse número é exibido quando os usuários tocam no botão **Precisa de ajuda** durante a ativação.

10. Você pode **Mostram** ou **Ocultar** uma série de telas durante a ativação do dispositivo. Para os fins deste tutorial, defina **Senha** para **Mostrar** e todas as outras opções para **Ocultar**.

11. Escolha **OK** > **Criar**.

## <a name="sync-managed-devices"></a>Sincronizar dispositivos gerenciados

Agora você pode ver quais dispositivos são atribuídos a esse token.

1. No Intune, no portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha um token na lista > **Dispositivos** > **Sincronizar**.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>Atribuir um perfil de registro aos dispositivos iOS

Atribua um perfil do Programa de Registro aos dispositivos antes de registrá-los.

1. No Intune, no portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha seu token na lista.
2. Escolha **Dispositivos**> escolha dispositivos na lista > **Atribuir perfil**.
3. Em **Atribuir perfil**, escolha um perfil para os dispositivos e, em seguida, escolha **Atribuir**.

## <a name="distribute-devices-to-users"></a>Distribuir dispositivos para usuários

Você configurou o gerenciamento e a sincronização entre o Apple e o Intune e atribuiu um perfil para permitir o registro dos dispositivos de DEP. Agora você pode distribuir dispositivos para os usuários. Os dispositivos com afinidade de usuário requerem que cada usuário receba uma licença do Intune.

## <a name="clean-up-resources"></a>Limpar os recursos

Se você não quiser mais usar os dispositivos do Autopilot, poderá excluí-los.

- Se os dispositivos estiverem registrados no Intune, primeiro [exclua-os do portal do Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

<!--ask tiffany how to do this-->

## <a name="next-steps"></a>Próximas etapas

Você pode encontrar mais informações sobre outras opções disponíveis para registrar dispositivos iOS.

> [!div class="nextstepaction"]
> [Artigo detalhado sobre o registro no DEP do iOS](device-enrollment-program-enroll-ios.md)
