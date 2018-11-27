---
title: Registrar dispositivos iOS – Programa de registro de dispositivos
titleSuffix: Microsoft Intune
description: Saiba como registrar dispositivos iOS de propriedade corporativa usando o Programa de registro de dispositivos.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 650a358281f89c511bbd56f3807f2ef4a6ba582c
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52190346"
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Registrar automaticamente dispositivos iOS com o Programa de registro de dispositivos da Apple

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo ajuda você a habilitar o registro de dispositivos iOS comprados por meio do [DEP (Programa de Registro de Dispositivos)](https://deploy.apple.com) da Apple. Você pode habilitar o registro de DEP para um grande número de dispositivos sem nunca tocá-los. Você pode enviar dispositivos como iPhones e iPads diretamente aos usuários. Quando o usuário liga o dispositivo, o Assistente de Configuração é executado com as configurações predefinidas e o dispositivo é registrado no gerenciamento.

Para habilitar o registro de DEP, você pode usar ambos os portais do Intune e do Apple DEP. É necessária uma lista de números de série ou um número de ordem de compra para que você possa atribuir os dispositivos ao Intune para gerenciamento. Você cria perfis de registro de DEP que contém configurações aplicadas aos dispositivos durante o registro.

A propósito, o registro de DEP não funciona com o [gerenciador de registros de dispositivos](device-enrollment-manager-enroll.md).

## <a name="what-is-supervised-mode"></a>O que é o modo supervisionado?
A Apple apresentou o modo supervisionado no iOS 5. Um dispositivo iOS no modo supervisionado pode ser gerenciado com mais controles. Assim, é especialmente útil para dispositivos corporativos. O Intune dá suporte ao configurar dispositivos para o modo supervisionado como parte do Programa de registro de dispositivos (DEP) da Apple. 

A compatibilidade com dispositivos DEP não supervisionados foi preterida no iOS 11. No iOS 11 e posterior, os dispositivos configurados com o DEP devem sempre ser supervisionados. O sinalizador is_supervised do DEP será ignorado em um lançamento futuro do iOS.

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
- [Autoridade MDM](mdm-authority-set.md)
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Obtenha um token DEP da Apple

Antes que possa registrar dispositivos iOS o DEP, você precisa de um arquivo de token (.p7m) do DEP da Apple. Esse token permite que o Intune sincronize informações sobre os dispositivos do DEP de sua empresa. Ele também permite que o Intune carregue perfis de registro para a Apple e atribua novos dispositivos a esses perfis.

Você pode usar o portal de DEP da Apple para criar um token de DEP. Você também pode usar o portal de DEP para atribuir dispositivos ao Intune para gerenciamento.

> [!NOTE]
> Caso exclua o token do Portal Clássico do Intune antes de migrar para o Azure, o Intune poderá restaurar um token de DEP da Apple. Você pode excluir o token de DEP novamente no portal do Azure.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Etapa 1. Baixe o certificado de chave pública do Intune necessário para criar um token.

1. No [Intune no Portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens do Programa de Registro** > **Adicionar**.

    ![Obtenha um token do programa de registro.](./media/device-enrollment-program-enroll-ios/image01.png)

2. Conceder permissão à Microsoft para enviar informações de usuário e dispositivo para a Apple selecionando **Eu concordo**.

   ![Captura de tela do painel do Token de Programa de Registro no workspace de Certificados da Apple para baixar a chave pública.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

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
Na caixa **Token da Apple**, navegue até o arquivo de certificado (.pem), escolha **Abrir** e, em seguida, escolha **Criar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados. O Intune sincroniza automaticamente com a Apple para ver a sua conta de programa de registro.

## <a name="create-an-apple-enrollment-profile"></a>Criar um perfil de registro da Apple

Agora que você instalou o token, pode criar um perfil de registro para dispositivos do DEP. Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro**.
2. Selecione um token, escolha **Perfis** e, em seguida, escolha **Criar perfil**.

    ![Criar uma captura de tela de perfil.](./media/device-enrollment-program-enroll-ios/image04.png)

3. Em **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil para fins administrativos. Os usuários não veem esses detalhes. Você pode usar esse campo **Nome** para criar um grupo dinâmico no Azure Active Directory. Use o nome do perfil para definir o parâmetro enrollmentProfileName para atribuir dispositivos com este perfil de registro. Saiba mais sobre os [grupos dinâmicos do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

    ![Nome e descrição do perfil.](./media/device-enrollment-program-enroll-ios/image05.png)

4. Em **Afinidade de Usuário**, escolha se os dispositivos com esse perfil devem ser registrados com ou sem um usuário atribuído.
    - **Registrar com dispositivo de afinidade do usuário** – Escolha esta opção para dispositivos que pertencem a usuários e que desejam usar o Portal da Empresa para serviços como a instalação de aplicativos. Se estiver usando o ADFS e o perfil de registro tiver a opção **Autenticar com o Portal da Empresa em vez de usar o Assistente de Configuração** definida como **Não**, será obrigatório [Nome de usuário/Ponto de extremidade misto do WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints) [Saiba mais](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Registrar sem afinidade do usuário** – escolha esta opção para dispositivos não afiliados com um único usuário. Use esta opção para os dispositivos que executam tarefas sem acessar os dados de usuário local. Aplicativos como o aplicativo de Portal da Empresa não funcionam.

5. Se você tiver escolhido **Registrar com Afinidade do Usuário**, terá a opção de permitir que os usuários façam a autenticação com o Portal da Empresa em vez do Assistente de Configuração da Apple.

    ![Faça a autenticação com o Portal da Empresa.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Quando quiser fazer algum dos seguintes procedimentos, defina **Autenticar com o Portal da Empresa em vez de usar o Assistente de Configuração** como **Sim**.
    >    - Usar autenticação multifator
    >    - Solicitar aos usuários que precisam alterar a senha quando entram pela primeira vez
    >    - solicitar que os usuários redefinam suas senhas expiradas durante o registro
    >
    > Essas opções não têm suporte na autenticação com o Assistente de Configuração da Apple.

6. Se escolher **Sim** para **Autenticar-se com o Portal da Empresa em vez do Assistente de Configuração do Apple**, você terá a opção de usar um token do VPP (Volume Purchase Program) para instalar automaticamente o Portal da Empresa no dispositivo sem que o usuário forneça uma ID da Apple. Para instalar o Portal da Empresa com um token de VPP, escolha um token em **Instalar o Portal da Empresa com o VPP**. Verifique se o token não expira e se você tem licenças do dispositivo suficientes para o aplicativo de Portal da Empresa. Se o token expirar ou for executado sem licenças, o Intune instalará em seu lugar o Portal da Empresa da App Store e ID da Apple será solicitada.

    ![Captura de tela da instalação do Portal da Empresa com o VPP.](./media/device-enrollment-program-enroll-ios/install-cp-with-vpp.png)

7. Se você escolheu um token para **Instalar o Portal da Empresa com o VPP**, há uma opção para bloquear o dispositivo no Modo de Aplicativo Único (especificamente, o aplicativo Portal da Empresa) imediatamente após a conclusão do Assistente de Configuração. Escolha **Sim** para **Executar Portal da Empresa no Modo de Aplicativo Único até a autenticação** para definir essa opção. Para usar o dispositivo, o usuário precisa primeiro se autenticar usando o Portal da Empresa.
    Esse recurso é executado melhor com o iOS 11.3.1 e posterior. Usar versões mais antigas pode levar muito tempo para instalar.

8. Escolha **Configurações de Gerenciamento de Dispositivo** e selecione se deseja ou não que os dispositivos que utilizam esse perfil sejam supervisionados.

    ![Captura de tela Configurações de Gerenciamento de Dispositivos.](./media/device-enrollment-program-enroll-ios/devicemanagementsettingsblade.png)

    Os dispositivos **supervisionados** permitem mais opções de gerenciamento e desabilitam o Bloqueio de Ativação por padrão. A Microsoft recomenda usar o DEP como o mecanismo para habilitar o modo supervisionado, especialmente para as empresas que implantam grandes números de dispositivos iOS.

    Os usuários são notificados de que seus dispositivos são supervisionados de duas maneiras:

   - A tela de bloqueio diz: "Este iPhone é gerenciado pela Contoso".
   - A tela **Configurações** > **Geral** > **Sobre** diz: "Este iPhone é supervisionado. A Contoso pode monitorar o tráfego de Internet e localizar este dispositivo."

     > [!NOTE]
     > Um dispositivo registrado sem supervisão só pode ser redefinido para supervisionado usando o Apple Configurator. A redefinição do dispositivo dessa maneira requer conectar um dispositivo iOS a um Mac com um cabo USB. Saiba mais sobre isso nos [documentos do Apple Configurator](http://help.apple.com/configurator/mac/2.3).

9. Escolha se deseja ou não registro bloqueado para dispositivos que usam esse perfil. O **registro bloqueado** desabilita as configurações de iOS que permitem que o perfil de gerenciamento seja removido do menu **Configurações**. Depois que o dispositivo é registrado, não é possível alterar essa configuração sem apagar o dispositivo. Esses dispositivos devem ter o Modo de Gerenciamento **Supervisionado** configurado como *Sim*. 

10. Escolha se deseja ou não que os dispositivos usando este perfil possam **Sincronizar com computadores**. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em **Certificados do Apple Configurator**.

11. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em Certificados do Apple Configurator para importar.

12. Selecione **OK**.

13. Escolha as **Personalização do Assistente de Configuração** para definir as seguintes configurações de perfil: ![Personalização do Assistente de Configuração.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    | Configurações de departamento | Descrição |
    |---|---|
    | <strong>Nome do Departamento</strong> | Aparece quando os usuários tocam em <strong>Sobre a Configuração</strong> durante a ativação. |
    |    <strong>Telefone do Departamento</strong>     | Aparece quando o usuário clica no botão <strong>Precisa de Ajuda</strong> durante a ativação. |

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


14. Selecione **OK**.

15. Para salvar o perfil, escolha **Criar**.

## <a name="sync-managed-devices"></a>Sincronizar dispositivos gerenciados
Agora que o Intune tem permissão para gerenciar seus dispositivos, você pode sincronizar o Intune com a Apple para ver os dispositivos gerenciados no Intune no Portal do Azure.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha um token na lista > **Dispositivos** > **Sincronizar**. ![Captura de tela do nó Dispositivos de Programa de Registro selecionado com o link de Sincronização escolhido.](./media/device-enrollment-program-enroll-ios/image06.png)

   Para estar em conformidade com os termos da Apple em relação ao tráfego aceitável do programa de registro, o Intune impõe as seguintes restrições:
   - Uma sincronização completa pode ser executada, no máximo, uma vez a cada sete dias. Durante uma sincronização completa, o Intune busca a lista atualizada completa de números de série atribuído ao servidor Apple MDM conectado ao Intune. Quando um dispositivo do Programa de Registro é excluído do portal do Intune sem ter sido desvinculado do servidor MDM da Apple no portal do DEP, ele não é importado novamente para o Intune até que a sincronização completa seja executada.   
   - A sincronização é executada automaticamente a cada 24 horas. Você também pode sincronizar clicando no botão **Sincronizar** (não mais do que uma vez a cada 15 minutos). Todas as solicitações de sincronização têm 15 minutos para conclusão. O botão **Sincronizar** fica desativado até que a sincronização seja concluída. Essa sincronização atualizará o status do dispositivo existente e importará novos dispositivos atribuídos ao servidor MDM da Apple.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Atribuir um perfil de registro aos dispositivos
Atribua um perfil do Programa de Registro aos dispositivos antes de registrá-los.

>[!NOTE]
>Você também pode atribuir números de série aos perfis na folha **Números de Série da Apple**.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha um token na lista.
2. Escolha **Dispositivos**> escolha dispositivos na lista > **Atribuir perfil**.
3. Em **Atribuir perfil**, escolha um perfil para os dispositivos e, em seguida, escolha **Atribuir**.

### <a name="assign-a-default-profile"></a>Atribuir um perfil padrão

Você pode escolher um perfil padrão a ser aplicado a todos os dispositivos que se registrem com um token específico.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha um token na lista.
2. Escolha **Definir como Perfil Padrão**, selecione um perfil na lista suspensa e escolha **Salvar**. Este perfil será aplicado a todos os dispositivos registrados com o token.

## <a name="distribute-devices"></a>Distribuir dispositivos
Você habilitou o gerenciamento e a sincronização entre o Apple e o Intune e atribuiu um perfil para permitir o registro dos dispositivos de DEP. Agora você pode distribuir dispositivos para os usuários. Os dispositivos com afinidade de usuário requerem que cada usuário receba uma licença do Intune. Os dispositivos sem afinidade de usuário requerem uma licença de dispositivo. Um dispositivo ativado só poderá receber um perfil de registro depois que for apagado.

Consulte [Registre seu dispositivo iOS no Intune com o Programa de registro de dispositivos](/intune-user-help/enroll-your-device-dep-ios).

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
