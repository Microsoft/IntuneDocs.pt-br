---
title: Registrar dispositivos macOS – Programa de registro de dispositivos
titleSuffix: Microsoft Intune
description: Saiba como registrar dispositivos macOS de propriedade corporativa usando o Programa de registro de dispositivos.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 18b4ab35627e1ccb694104f3f5800e5fb07dd1c7
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313419"
---
# <a name="automatically-enroll-macos-devices-with-apples-device-enrollment-program"></a>Registrar automaticamente dispositivos macOS com o Programa de registro de dispositivos da Apple

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo vai ajudá-lo a configurar o registro de dispositivos macOS comprados por meio do [DEP (Programa de registro de dispositivos)](https://deploy.apple.com) da Apple. Você pode configurar o registro DEP para um grande número de dispositivos sem nunca precisar tocá-los. É possível enviar dispositivos macOS diretamente aos usuários. Quando o usuário liga o dispositivo, o Assistente de Configuração é executado com as configurações predefinidas e o dispositivo é registrado no gerenciamento do Intune.

Para configurar o registro DEP, você pode usar os portais do Intune e do Apple DEP. Você cria perfis de registro de DEP que contém configurações aplicadas aos dispositivos durante o registro.

A propósito, o registro de DEP não funciona com o [gerenciador de registros de dispositivos](device-enrollment-manager-enroll.md).

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Pré-requisitos
- Dispositivos comprados no [Programa de registro de dispositivos da Apple](http://deploy.apple.com)
- Uma lista de números de série ou um número de ordem de compra. 
- [Autoridade MDM](mdm-authority-set.md)
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Obtenha um token DEP da Apple

Para registrar dispositivos macOS com o DEP, é necessário um arquivo de token (.p7m) do DEP da Apple. Esse token permite que o Intune sincronize informações sobre os dispositivos do DEP de sua empresa. Ele permite também ao Intune carregar perfis de registro na Apple e atribuir dispositivos a esses perfis.

Você pode usar o portal de DEP da Apple para criar um token de DEP. Você também pode usar o portal de DEP para atribuir dispositivos ao Intune para gerenciamento.

> [!NOTE]
> Caso exclua o token do Portal Clássico do Intune antes de migrar para o Azure, o Intune poderá restaurar um token de DEP da Apple. Você pode excluir o token de DEP novamente no portal do Azure.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Etapa 1. Baixe o certificado de chave pública do Intune necessário para criar um token.

1. No [Intune no Portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens do Programa de Registro** > **Adicionar**.

    ![Obtenha um token do programa de registro.](./media/device-enrollment-program-enroll-ios/image01.png)

2. Conceder permissão à Microsoft para enviar informações de usuário e dispositivo para a Apple selecionando **Eu concordo**.

   ![Captura de tela do painel do Token de Programa de Registro no espaço de trabalho de Certificados da Apple para baixar a chave pública.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Escolha **Baixar sua chave pública** para baixar e salvar o arquivo da chave de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Programa de registro de dispositivo da Apple.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Etapa 2. Use a chave para baixar um token da Apple.

1. Escolha **Criar um token para o Programa de registro de dispositivos da Apple** para abrir o Portal do Programa de Implantação da Apple e entrar com sua ID da Apple da empresa. Você pode usar essa ID da Apple para renovar seu token de DEP.
2.  No [Portal de Programas de Implantação](https://deploy.apple.com) da Apple, escolha **Começar** para **Programa de registro de dispositivos**.

3. Na página **Gerenciar Servidores**, escolha **Adicionar servidor MDM**.
4. Insira o **Nome do servidor MDM** e escolha **Avançar**. O nome do servidor é para sua referência para identificar o servidor MDM (gerenciamento de dispositivo móvel). Não é o nome ou URL do servidor Microsoft Intune.

5. A caixa de diálogo **Adicionar &lt;ServerName&gt;** é aberta, indicando abre a caixa de diálogo, indicando **Carregar sua chave pública**. Escolha **Escolher Arquivo…** para carregar o arquivo .pem e clique em **Avançar**.

6. Acesse **Programas de Implantação** &gt; **Programa de Registro de Dispositivos** &gt; **Gerenciar Dispositivos**.
7. Em **Escolher dispositivos por**, especifique como os dispositivos são identificados:
    - **Número de série**
    - **Número do pedido**
    - **Carregar o arquivo CSV**.

   ![Captura de tela que especifica de especificação para escolher dispositivos pelo número de série, definindo a ação de escolha como Atribuir ao servidor e selecionando o nome do servidor.](./media/enrollment-program-token-specify-serial.png)

8. Para **Escolher Ação**, escolha **Atribuir ao Servidor**, escolha o &lt;ServerName&gt; especificado para o Microsoft Intune e escolha **OK**. O Portal da Apple atribui os dispositivos especificados para o servidor do Intune para gerenciamento e exibe **Atribuição Concluída**.

   No Portal da Apple, acesse **Programas de Implantação** &gt; **Programa de registro de dispositivos** &gt; **Exibir o Histórico de Atribuição** para ver uma lista de dispositivos e sua atribuição de servidor MDM.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Etapa 3. Salve a ID da Apple usada para criar esse token.

No Intune no Portal do Azure, forneça a ID da Apple para referência futura.

![Captura de tela mostrando a especificação do ID Apple usado para criar o Token do Programa de Registro e a navegação para este recurso.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Etapa 4. Carregue o seu token.
Na caixa **Token da Apple**, navegue até o arquivo de certificado (.pem), escolha **Abrir** e, em seguida, escolha **Criar**. Com o Push Certificate, o Intune pode registrar e gerenciar dispositivos macOS enviando políticas por push aos dispositivos registrados. O Intune sincroniza automaticamente com a Apple para ver a sua conta de programa de registro.

## <a name="create-an-apple-enrollment-profile"></a>Criar um perfil de registro da Apple

Agora que você instalou o token, pode criar um perfil de registro para dispositivos do DEP. Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro**.
2. Selecione um token, escolha **Perfis** e, em seguida, escolha **Criar perfil**.

    ![Criar uma captura de tela de perfil.](./media/device-enrollment-program-enroll-ios/image04.png)

3. Em **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil para fins administrativos. Os usuários não veem esses detalhes. Você pode usar esse campo **Nome** para criar um grupo dinâmico no Azure Active Directory. Use o nome do perfil para definir o parâmetro enrollmentProfileName para atribuir dispositivos com este perfil de registro. Saiba mais sobre os [grupos dinâmicos do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

    ![Nome e descrição do perfil.](./media/device-enrollment-program-enroll-macos/createprofile.png)

4. Para **Plataforma**, escolha **macOS**.

5. Em **Afinidade de Usuário**, escolha se os dispositivos com esse perfil devem ser registrados com ou sem um usuário atribuído.
    - **Registrar com dispositivo de afinidade do usuário** – Escolha esta opção para dispositivos que pertencem a usuários e que desejam usar o aplicativo Portal da Empresa para serviços como a instalação de aplicativos. Se estiver usando o ADFS, a afinidade de dispositivo de usuário exigirá o [ponto de extremidade Nome do Usuário/Misto do WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints). [Saiba mais](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint). A autenticação multifator não tem suporte para dispositivos DEP macOS com afinidade de usuário.

    - **Registrar sem afinidade do usuário** – escolha esta opção para dispositivos não afiliados com um único usuário. Use-a para dispositivos que executam tarefas sem acessar os dados de usuário local. Aplicativos como o aplicativo de Portal da Empresa não funcionam.

6. Escolha **Configurações de Gerenciamento de Dispositivo** e selecione se deseja ou não o Registro Bloqueado para dispositivos que usam esse perfil. O **Registro Bloqueado** desabilita as configurações do macOS que permitem que o perfil de gerenciamento seja removido do menu **Preferências do Sistema** ou do **Terminal**. Depois que o dispositivo é registrado, não é possível alterar essa configuração sem apagar o dispositivo.

    ![Captura de tela Configurações de Gerenciamento de Dispositivos.](./media/device-enrollment-program-enroll-macos/devicemanagementsettingsblade-macos.png)
 
7. Selecione **OK**.

8. Escolha as **Configurações do Assistente de Configuração** para definir as seguintes configurações de perfil: ![Personalização do Assistente de Configuração.](./media/device-enrollment-program-enroll-macos/setupassistantcustom-macos.png)

    | Configurações de departamento | Descrição |
    |---|---|
    | <strong>Nome do Departamento</strong> | Aparece quando os usuários tocam em <strong>Sobre a Configuração</strong> durante a ativação. |
    | <strong>Telefone do Departamento</strong> | Aparece quando o usuário clica no botão <strong>Precisa de Ajuda</strong> durante a ativação. |

  Você pode optar por mostrar ou ocultar uma variedade de telas do Assistente de Instalação no dispositivo quando o usuário o configura.
  - Se você escolher **Ocultar**, a tela não será exibida durante a instalação. Depois de configurar o dispositivo, o usuário pode ainda entrar no menu **Configurações** para configurar o recurso.
  - Se você escolher **Mostrar**, a tela será exibida durante a instalação. O usuário pode, às vezes, ignorar a tela sem executar uma ação. No entanto, é possível ir mais tarde para o menu **Configurações** do dispositivo para configurar o recurso. 


    | Configurações de tela do Assistente de Instalação | Se você escolher **Mostrar**, durante a instalação, o dispositivo... |
    |------------------------------------------|------------------------------------------|
    | <strong>Senha</strong> | Solicitará ao usuário uma senha. Sempre exija uma senha, a menos que o dispositivo esteja protegido ou tenha o acesso controlado de alguma outra maneira (ou seja, o modo de quiosque que restringe o dispositivo a um aplicativo). |
    | <strong>Serviços de Localização</strong> | Solicitará ao usuário sua localização. |
    | <strong>Restaurar</strong> | Exibirá a tela **Aplicativos e Dados**. Esta tela fornece aos usuários a opção de restaurar ou transferir dados do Backup do iCloud quando eles configuram o dispositivo. |
    | <strong>iCloud e ID da Apple</strong> | Dará ao usuário as opções de entrar com sua **ID da Apple** e usar o **iCloud**.                         |
    | <strong>Termos e Condições</strong> | Exigirá que o usuário aceite os termos e condições da Apple. |
    | <strong>ID de Toque</strong> | Dará ao usuário a opção de configurar a identificação por impressão digital para o dispositivo. |
    | <strong>Apple Pay</strong> | Dará ao usuário a opção de configurar o Apple Pay no dispositivo. |
    | <strong>Zoom</strong> | Dará ao usuário a opção para aplicar zoom na exibição quando ele configurar o dispositivo. |
    | <strong>Siri</strong> | Dará ao usuário a opção de configurar o Siri. |
    | <strong>Dados de diagnóstico</strong> | Exibir a tela **Diagnóstico** para o usuário. Esta tela fornece ao usuário a opção de enviar dados de diagnóstico para a Apple. |
    | <strong>FileVault</strong> | Dará ao usuário a opção de configurar a criptografia do FileVault. |
    | <strong>Diagnóstico do iCloud</strong> | Dará ao usuário a opção de enviar dados de diagnóstico do iCloud para a Apple. |
    | <strong>Registro</strong>| Exigirá que o usuário registre o dispositivo. |

   

10. Selecione **OK**.

11. Para salvar o perfil, escolha **Criar**.

## <a name="sync-managed-devices"></a>Sincronizar dispositivos gerenciados
Agora que o Intune tem permissão para gerenciar seus dispositivos, você pode sincronizar o Intune com a Apple para ver os dispositivos gerenciados no Intune no Portal do Azure.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha um token na lista > **Dispositivos** > **Sincronizar**. ![Captura de tela do nó Dispositivos de Programa de Registro selecionado com o link de Sincronização escolhido.](./media/device-enrollment-program-enroll-ios/image06.png)

   Para estar em conformidade com os termos da Apple em relação ao tráfego aceitável do programa de registro, o Intune impõe as seguintes restrições:
   - Uma sincronização completa pode ser executada, no máximo, uma vez a cada sete dias. Durante uma sincronização completa, o Intune busca a lista atualizada completa de números de série atribuído ao servidor Apple MDM conectado ao Intune. Quando um dispositivo do Programa de Registro é excluído do portal do Intune sem ter sido desvinculado do servidor MDM da Apple no portal do DEP, ele não é importado novamente para o Intune até que a sincronização completa seja executada.   
   - A sincronização é executada automaticamente a cada 24 horas. Você também pode sincronizar clicando no botão **Sincronizar** (não mais do que uma vez a cada 15 minutos). Todas as solicitações de sincronização têm 15 minutos para conclusão. O botão **Sincronizar** fica desativado até que a sincronização seja concluída. Essa sincronização atualizará o status do dispositivo existente e importará novos dispositivos atribuídos ao servidor MDM da Apple.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Atribuir um perfil de registro aos dispositivos
Atribua um perfil do Programa de Registro aos dispositivos antes de registrá-los.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha um token na lista.
2. Escolha **Dispositivos**> escolha dispositivos na lista > **Atribuir perfil**.
3. Em **Atribuir perfil**, escolha um perfil para os dispositivos e, em seguida, escolha **Atribuir**.

### <a name="assign-a-default-profile"></a>Atribuir um perfil padrão

Você pode escolher um perfil padrão do macOS e do iOS a ser aplicado a todos os dispositivos que se registrem com um token específico. 

1. No Intune, no portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha um token na lista.
2. Escolha **Definir como Perfil Padrão**, selecione um perfil na lista suspensa e escolha **Salvar**. Este perfil será aplicado a todos os dispositivos registrados com o token.

## <a name="distribute-devices"></a>Distribuir dispositivos
Você habilitou o gerenciamento e a sincronização entre o Apple e o Intune e atribuiu um perfil para permitir o registro dos dispositivos de DEP. Agora você pode distribuir dispositivos para os usuários. Os dispositivos com afinidade de usuário requerem que cada usuário receba uma licença do Intune. Os dispositivos sem afinidade de usuário requerem uma licença de dispositivo. Um dispositivo ativado só poderá receber um perfil de registro depois que for apagado.

## <a name="renew-a-dep-token"></a>Renovar um token DEP  
1. Acesse deploy.apple.com.  
2. Em **Gerenciar Servidores**, escolha o servidor MDM associado ao arquivo de token que você deseja renovar.
3. Escolha **Gerar Novo Token**.

    ![Captura de tela de geração de novo token.](./media/device-enrollment-program-enroll-ios/generatenewtoken.png)

4. Escolha **Token do Seu Servidor**.  
5. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivos** > **Registro da Apple** > **Tokens do programa de registro** > escolha o token.
    ![Captura de tela de tokens do programa de registro.](./media/device-enrollment-program-enroll-ios/enrollmentprogramtokens.png)

6. Escolha **Renovar token** e insira a ID da Apple usada para criar o token original.  
    ![Captura de tela de geração de novo token.](./media/device-enrollment-program-enroll-ios/renewtoken.png)

8. Carregue o token recém-baixado.  
9. Escolha **Renovar token**. Você verá a confirmação de renovação do token.   
    ![Captura de tela de confirmação.](./media/device-enrollment-program-enroll-ios/confirmation.png)

## <a name="next-steps"></a>Próximas etapas

Depois de registrar dispositivos macOS, você poderá começar a [gerenciá-los](device-management.md).