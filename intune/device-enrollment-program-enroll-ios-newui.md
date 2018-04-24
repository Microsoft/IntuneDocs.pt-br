---
title: Registrar dispositivos iOS – Programa de registro de dispositivos
titleSuffix: Microsoft Intune
description: Saiba como registrar dispositivos iOS de propriedade corporativa usando o Programa de registro de dispositivos (nova interface de usuário).
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5532e00f90702b820ec5bed6bf2fdb3d5e9d37df
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Registrar automaticamente dispositivos iOS com o Programa de registro de dispositivos da Apple

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> ### <a name="temporary-user-interface-differences"></a>Diferenças de interface de usuário temporárias
> As interfaces de usuário para os recursos descritos nesta página estão em processo de atualização. Essas atualizações estão sendo implementadas em todas as contas de usuário até o final de abril.
>
> Se a sua página de **Registro de dispositivo** for semelhante à imagem abaixo, as suas interfaces de usuário estão atualizadas e você pode usar esta página de ajuda.
>
> ![Nova interface do usuário](./media/appleenroll-newui.png)
>
> Caso contrário, se a sua página de **Registro de dispositivo** for semelhante à imagem abaixo, sua conta ainda não foi atualizada para a nova interface do usuário. Vá para [esta página de ajuda](device-enrollment-program-enroll-ios.md).
>
> ![Antiga interface do usuário](./media/appleenroll-oldui.png)

Este tópico ajuda você a habilitar o registro de dispositivos iOS comprados por meio do [DEP (Programa de registro de dispositivos)](https://deploy.apple.com) da Apple. Você pode habilitar o registro de DEP para um grande número de dispositivos sem nunca tocá-los. Você pode enviar dispositivos como iPhones e iPads diretamente aos usuários. Quando o usuário liga o dispositivo, o Assistente de Configuração é executado com as configurações predefinidas e o dispositivo é registrado no gerenciamento.

Para habilitar o registro de DEP, você pode usar ambos os portais do Intune e do Apple DEP. É necessária uma lista de números de série ou um número de ordem de compra para que você possa atribuir os dispositivos ao Intune para gerenciamento. Você cria perfis de registro de DEP que contém configurações aplicadas aos dispositivos durante o registro.

A propósito, o registro de DEP não funciona com o [gerenciador de registros de dispositivos](device-enrollment-manager-enroll.md).

## <a name="what-is-supervised-mode"></a>O que é o modo supervisionado?
A Apple apresentou o modo supervisionado no iOS 5. Um dispositivo iOS no modo supervisionado pode ser gerenciado com mais controles. Assim, é especialmente útil para dispositivos corporativos. O Intune dá suporte ao configurar dispositivos para o modo supervisionado como parte do Programa de registro de dispositivos (DEP) da Apple. 

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
> Caso exclua o token do Portal Clássico do Intune antes de migrar para o Azure, o Intune poderá restaurar um token de DEP da Apple. Você pode excluir o token de DEP novamente no portal do Azure. Você pode excluir o token de DEP novamente no portal do Azure.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Etapa 1. Baixe o certificado de chave pública do Intune necessário para criar um token.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Token do Programa de Registro** > **Adicionar**.

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
Na caixa **Token da Apple**, navegue até o arquivo de certificado (.pem), escolha **Abrir** e, em seguida, escolha **Criar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados. O Intune sincroniza automaticamente com a Apple para ver a sua conta de programa de registro.

## <a name="create-an-apple-enrollment-profile"></a>Criar um perfil de registro da Apple

Agora que você instalou o token, pode criar um perfil de registro para dispositivos do DEP. Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro**.
2. Selecione um token, escolha **Perfis** e, em seguida, escolha **Criar perfil**.
    ![Crie uma captura de tela de perfil.](./media/device-enrollment-program-enroll-ios/image04.png)
3. Em **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil para fins administrativos. Os usuários não veem esses detalhes. Você pode usar esse campo **Nome** para criar um grupo dinâmico no Azure Active Directory. Use o nome do perfil para definir o parâmetro enrollmentProfileName para atribuir dispositivos com este perfil de registro. Saiba mais sobre os [grupos dinâmicos do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).
    ![Nome e descrição do perfil.](./media/device-enrollment-program-enroll-ios/image05.png)

4. Em **Afinidade de Usuário**, escolha se os dispositivos com esse perfil devem ser registrados com ou sem um usuário atribuído.
    - **Registrar com afinidade do usuário** – escolha esta opção para dispositivos que pertencem a usuários e que desejam usar o portal da empresa para serviços como a instalação de aplicativos. Esta opção também permite que os usuários façam a autenticação de seus dispositivos usando o portal da empresa. A afinidade de usuário requer [ponto de extremidade nome do usuário/misto WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints). [Saiba mais](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Registrar sem afinidade do usuário** – escolha esta opção para dispositivos não afiliados com um único usuário. Use-a para dispositivos que executam tarefas sem acessar os dados de usuário local. Aplicativos como o aplicativo de Portal da Empresa não funcionam.

5. Se você tiver escolhido **Registrar com Afinidade do Usuário**, terá a opção de permitir que os usuários façam a autenticação com o Portal da Empresa em vez do Assistente de Configuração da Apple.

    ![Faça a autenticação com o Portal da Empresa.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > A MFA (autenticação multifator) não funcionará durante o registro de DEP se você tiver propriedades de perfil definidas como **Registrar com afinidade do usuário** e não estiver usando um Portal da Empresa. Após o registro, a MFA funciona conforme o esperado nos dispositivos. Os dispositivos não podem exibir uma solicitação aos usuários que precisam alterar sua senha quando entrarem pela primeira vez. Além disso, os usuários com senhas expiradas não receberão uma solicitação para redefinir a senha durante o registro. Os usuários devem usar um dispositivo diferente para redefinir a senha.

6. Escolha **Configurações de Gerenciamento de Dispositivo** e selecione se deseja ou não que os dispositivos que utilizam esse perfil sejam supervisionados.
    Os dispositivos **supervisionados** permitem mais opções de gerenciamento e desabilitam o Bloqueio de Ativação por padrão. A Microsoft recomenda usar o DEP como o mecanismo para habilitar o modo supervisionado, especialmente para as empresas que implantam grandes números de dispositivos iOS.

    Os usuários são notificados de que seus dispositivos são supervisionados de duas maneiras:

   - A tela de bloqueio diz: "Este iPhone é gerenciado pela Contoso".
   - A tela **Configurações** > **Geral** > **Sobre** diz: "Este iPhone é supervisionado. A Contoso pode monitorar o tráfego de Internet e localizar este dispositivo."

     > [!NOTE]
     > Um dispositivo registrado sem supervisão só pode ser redefinido para supervisionado usando o Apple Configurator. A redefinição do dispositivo dessa maneira requer conectar um dispositivo iOS a um Mac com um cabo USB. Saiba mais sobre isso nos [documentos do Apple Configurator](http://help.apple.com/configurator/mac/2.3).

7. Escolha se deseja ou não registro bloqueado para dispositivos que usam esse perfil. O **registro bloqueado** desabilita as configurações de iOS que permitem que o perfil de gerenciamento seja removido do menu **Configurações**. Depois de registrar o dispositivo, não é possível alterar esta configuração sem restaurar as configurações de fábrica. Esses dispositivos devem ter o Modo de Gerenciamento **Supervisionado** configurado como *Sim*. 

8. Escolha se deseja ou não que os dispositivos usando este perfil possam **Sincronizar com computadores**. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em **Certificados do Apple Configurator**.

9. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em Certificados do Apple Configurator para importar.

10. Selecione **OK**.

11. Escolha as **Configurações do Assistente de Configuração** para definir as seguintes configurações de perfil: ![Personalização do Assistente de Configuração.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    |                 Setting                  |                                                                                               Descrição                                                                                               |
    |------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |     <strong>Nome do Departamento</strong>     |                                                             Aparece quando os usuários tocam em <strong>Sobre a Configuração</strong> durante a ativação.                                                              |
    |    <strong>Telefone do Departamento</strong>     |                                                          Aparece quando o usuário clica no botão <strong>Precisa de Ajuda</strong> durante a ativação.                                                          |
    | <strong>Opções do Assistente de Instalação</strong> |                                                     As configurações opcionais a seguir podem ser configuradas posteriormente no menu <strong>Configurações</strong> do iOS.                                                      |
    |        <strong>Senha</strong>         | Solicitar senha durante a ativação. Sempre exija uma senha, a menos que o dispositivo esteja protegido ou tenha o acesso controlado de alguma outra maneira (ou seja, o modo de quiosque que restringe o dispositivo a um aplicativo). |
    |    <strong>Serviços de Localização</strong>    |                                                                 Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação.                                                                  |
    |         <strong>Restaurar</strong>         |                                                                Se habilitado, o Assistente de Instalação solicitará o backup do iCloud durante a ativação.                                                                 |
    |   <strong>iCloud e ID da Apple</strong>   |                         Se habilitado, o Assistente de Configuração solicita ao usuário que insira uma ID da Apple e a tela Aplicativos e Dados permitirá que o dispositivo seja restaurado a partir do backup do iCloud.                         |
    |  <strong>Termos e Condições</strong>   |                                                   Se habilitado, o Assistente de Instalação solicitará que os usuários aceitem os termos e as condições da Apple durante a ativação.                                                   |
    |        <strong>ID de Toque</strong>         |                                                                 Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação.                                                                 |
    |        <strong>Apple Pay</strong>        |                                                                 Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação.                                                                 |
    |          <strong>Zoom</strong>           |                                                                 Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação.                                                                 |
    |          <strong>Siri</strong>           |                                                                 Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação.                                                                 |
    |     <strong>Dados de diagnóstico</strong>     |                                                                 Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação.                                                                 |


12. Selecione **OK**.

13. Para salvar o perfil, escolha **Criar**.

## <a name="sync-managed-devices"></a>Sincronizar dispositivos gerenciados
Agora que o Intune tem permissão para gerenciar seus dispositivos, você pode sincronizar o Intune com a Apple para ver os dispositivos gerenciados no Intune no Portal do Azure.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha um token na lista > **Dispositivos** > **Sincronizar**. ![Captura de tela do nó Dispositivos de Programa de Registro selecionado com o link de Sincronização escolhido.](./media/device-enrollment-program-enroll-ios/image06.png)

   Para estar em conformidade com os termos da Apple em relação ao tráfego aceitável do programa de registro, o Intune impõe as seguintes restrições:
   - Uma sincronização completa pode ser executada, no máximo, uma vez a cada sete dias. Durante uma sincronização completa, o Microsoft Intune atualiza todos os números de série da Apple atribuídos à nossa plataforma. Se você tentar uma sincronização completa dentro de sete dias após a sincronização completa anterior, o Intune atualizará somente os números de série ainda não listados no Intune.
   - Qualquer solicitação de sincronização tem 15 minutos para ser concluída. Durante esse tempo ou até a solicitação ser bem-sucedida, o botão de **Sincronizar** fica desabilitado.
   - O Intune sincroniza dispositivos novos e removidos com a Apple a cada 24 horas.

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
Você habilitou o gerenciamento e a sincronização entre o Apple e o Intune e atribuiu um perfil para permitir o registro dos dispositivos de DEP. Agora você pode distribuir dispositivos para os usuários. Os dispositivos com afinidade de usuário requerem que cada usuário receba uma licença do Intune. Os dispositivos sem afinidade de usuário requerem uma licença de dispositivo. Um dispositivo ativado só pode ser aplicado a um perfil de registro após restaurar as respectivas configurações de fábrica.

Consulte [Registre seu dispositivo iOS no Intune com o Programa de registro de dispositivos](/intune-user-help/enroll-your-device-dep-ios).


