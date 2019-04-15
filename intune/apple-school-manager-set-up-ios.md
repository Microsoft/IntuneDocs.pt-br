---
title: Registro do Programa do Apple School Manager em dispositivos iOS
titleSuffix: Microsoft Intune
description: Saiba como configurar o registro do programa do Apple School Manager em dispositivos iOS de propriedade corporativa com o Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4c35a23e-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2d99712cfb972ae346c9254aac54feb5f4173a28
ms.sourcegitcommit: 25e17a1d002ee1faa49bb89648eb59373528539f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "59566653"
---
# <a name="set-up-ios-device-enrollment-with-apple-school-manager"></a>Configurar o registro de dispositivo iOS com o Apple School Manager

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Você pode configurar o Intune para registrar dispositivos iOS comprados por meio do programa [Apple School Manager](https://school.apple.com/). Ao usar o Intune com o Apple School Manager, é possível registrar grandes quantidades de dispositivos iOS sem a necessidade de tocá-los. Quando um estudante ou professor liga o dispositivo, o Assistente de Configuração é executado com as configurações predefinidas e o dispositivo é registrado no gerenciamento.

Para habilitar o registro do Apple School Manager, é necessário usar os portais do Intune e do Apple School Manager. É necessária uma lista de números de série ou um número de ordem de compra para que você possa atribuir os dispositivos ao Intune para gerenciamento. Você cria perfis de registro de DEP que contém configurações aplicadas aos dispositivos durante o registro.

O registro do Apple School Manager não pode ser usado com o [Programa de registro de dispositivos da Apple](device-enrollment-program-enroll-ios.md) ou o [gerenciador de registros de dispositivo](device-enrollment-manager-enroll.md).

**Pré-requisitos**
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- [Autoridade MDM](mdm-authority-set.md)
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- Se estiver usando o ADFS, a afinidade de dispositivo de usuário exigirá o [ponto de extremidade Nome do Usuário/Misto do WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints). [Saiba mais](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Dispositivos comprados no programa [Apple School Management](http://school.apple.com)

## <a name="get-an-apple-token-and-assign-devices"></a>Obter um token Apple e atribuir dispositivos

Antes de poder registrar dispositivos iOS de propriedade corporativa com o Apple School Manager, você precisa de um arquivo de token (.p7m) da Apple. Esse token permite que o Intune sincronize informações sobre os dispositivos que participam do Apple School Manager. Ele também permite que o Intune realize carregamentos de perfis de registro para a Apple e atribua dispositivos a esses perfis. No portal da Apple, você também pode atribuir números de série do dispositivo a serem gerenciados.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-an-apple-token"></a>Etapa 1. Baixar o certificado de chave pública do Intune necessário para criar um token da Apple

1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > **Adicionar**.

   ![Obtenha um token do programa de registro.](./media/device-enrollment-program-enroll-ios/image01.png)

2. Na folha **Token do programa de registro**, escolha **Baixar a chave pública** para baixar e salvar o arquivo de chave de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Apple School Manager.
     ![Folha Token do Programa de registro.](./media/device-enrollment-program-enroll-ios/image02.png)

### <a name="step-2-download-a-token-and-assign-devices"></a>Etapa 2. Baixar um token e atribuir dispositivos
1. Escolha **Criar um token usando o Apple School Manager** e entre no Apple School com sua ID corporativa da Apple. Use essa ID da Apple para renovar o token Apple School Manager.
2.  No [portal do Apple School Manager](https://school.apple.com), acesse **Servidores MDM** e, em seguida, escolha **Adicionar Servidor MDM** (canto superior direito).
3.  Insira o **Nome do Servidor MDM**. O nome do servidor é para sua referência para identificar o servidor MDM (gerenciamento de dispositivo móvel). Não é o nome ou URL do servidor Microsoft Intune.
   ![Captura de tela do portal do Apple School Manager com opção de Número de Série selecionada](./media/asm-server-assignment.png)

4.  Escolha **Carregar Arquivo...**  no portal da Apple, procure o arquivo .pem e escolha **Salvar Servidor MDM** (canto inferior direito).
5.  Escolha **Obter Token** e, em seguida, baixe o arquivo de token (.p7m) do servidor no computador.
6. Acesse **Atribuições de Dispositivo** e **Escolher Dispositivo** com a entrada manual dos **Números de Série**, do **Número do Pedido** ou **Carregar Arquivo CSV**.
     ![Captura de tela do portal do Apple School Manager com opção de Número de Série selecionada](./media/asm-device-assignment.png)
7.  Escolha a ação **Atribuir ao Servidor** e escolha o **Servidor MDM** criado.
8. Especifique como **Escolher Dispositivos** e forneça detalhes e informações do dispositivo.
9. Escolha **Atribuir ao Servidor**, escolha o &lt;ServerName&gt; especificado para o Microsoft Intune e escolha **OK**.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Etapa 3. Salvar a ID da Apple usada para criar esse token

No Intune no Portal do Azure, forneça a ID da Apple para referência futura.

![Captura de tela mostrando a especificação do ID Apple usado para criar o Token do Programa de Registro e a navegação para este recurso.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Etapa 4. Carregar o seu token
Na caixa **Token da Apple**, navegue até o arquivo de certificado (.pem), escolha **Abrir** e, em seguida, escolha **Criar**. Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados. O Intune sincroniza automaticamente os dispositivos Apple School Manager da Apple.

## <a name="create-an-apple-enrollment-profile"></a>Criar um perfil de registro da Apple
Agora que você instalou o token, pode criar um perfil de registro para dispositivos do Apple School. Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro.

1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro**.
2. Selecione um token, escolha **Perfis** e, em seguida, escolha **Criar perfil**.

3. Em **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil para fins administrativos. Os usuários não veem esses detalhes. Você pode usar esse campo **Nome** para criar um grupo dinâmico no Azure Active Directory. Use o nome do perfil para definir o parâmetro enrollmentProfileName para atribuir dispositivos com este perfil de registro. Saiba mais sobre os [grupos dinâmicos do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

    ![Nome e descrição do perfil.](./media/device-enrollment-program-enroll-ios/image05.png)

4. Em **Afinidade de Usuário**, escolha se os dispositivos com esse perfil devem ser registrados com ou sem um usuário atribuído.
    - **Registrar com afinidade do usuário** – escolha esta opção para dispositivos que pertencem a usuários e que desejam usar o portal da empresa para serviços como a instalação de aplicativos. Esta opção também permite que os usuários façam a autenticação de seus dispositivos usando o portal da empresa. Se estiver usando o ADFS, a afinidade de dispositivo de usuário exigirá o [ponto de extremidade Nome do Usuário/Misto do WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints). [Saiba mais](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).   O modo iPad Compartilhado do Apple School Manager exige o registro do usuário sem a afinidade de usuário.

    - **Registrar sem Afinidade do Usuário** – escolha esta opção para dispositivos não afiliados com um único usuário, como um dispositivo compartilhado. Use esta opção para os dispositivos que executam tarefas sem acessar os dados de usuário local. Aplicativos como o aplicativo de Portal da Empresa não funcionam.

5. Se você tiver escolhido **Registrar com Afinidade do Usuário**, terá a opção de permitir que os usuários façam a autenticação com o Portal da Empresa em vez do Assistente de Configuração da Apple.

    ![Faça a autenticação com o Portal da Empresa.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > Quando quiser fazer algum dos seguintes procedimentos, defina **Autenticar com o Portal da Empresa em vez de usar o Assistente de Configuração** como **Sim**.
    >    - Usar autenticação multifator
    >    - Solicitar aos usuários que precisam alterar a senha quando entram pela primeira vez
    >    - solicitar que os usuários redefinam suas senhas expiradas durante o registro
    >
    > Essas opções não têm suporte na autenticação com o Assistente de Configuração da Apple.

6. Escolha **Configurações de Gerenciamento de Dispositivo** e selecione se deseja ou não que os dispositivos que utilizam esse perfil sejam supervisionados.
    Os dispositivos **supervisionados** permitem mais opções de gerenciamento e desabilitam o Bloqueio de Ativação por padrão. A Microsoft recomenda usar o DEP como o mecanismo para habilitar o modo supervisionado, especialmente para as empresas que implantam grandes números de dispositivos iOS.

    Os usuários são notificados de que seus dispositivos são supervisionados de duas maneiras:

   - A tela de bloqueio diz: "Este iPhone é gerenciado pela Contoso."
   - A tela **Configurações** > **Geral** > **Sobre** diz: "Este iPhone é supervisionado. A Contoso pode monitorar o tráfego de Internet e localizar este dispositivo."

     > [!NOTE]
     > Um dispositivo registrado sem supervisão só pode ser redefinido para supervisionado usando o Apple Configurator. A redefinição do dispositivo dessa maneira requer conectar um dispositivo iOS a um Mac com um cabo USB. Saiba mais sobre isso nos [documentos do Apple Configurator](http://help.apple.com/configurator/mac/2.3).

7. Escolha se deseja ou não registro bloqueado para dispositivos que usam esse perfil. O **registro bloqueado** desabilita as configurações de iOS que permitem que o perfil de gerenciamento seja removido do menu **Configurações**. Depois que o dispositivo é registrado, não é possível alterar essa configuração sem apagar o dispositivo. Esses dispositivos devem ter o Modo de Gerenciamento **Supervisionado** configurado como *Sim*. 

8. Se deseja permitir que vários usuários façam logon em iPads inscritos usando um Apple Id gerenciado, escolha **Sim** em **iPad Compartilhado** (essa opção requer os modos **Registro sem Afinidade de Usuário** e **Supervisionado** definidos como **Sim**.) As IDs da Apple gerenciadas são criadas no portal do Apple School Manager. Saiba mais sobre [iPad compartilhado](education-settings-configure-ios-shared.md) e [os requisitos de iPad compartilhado da Apple](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56).

9. Escolha se deseja ou não que os dispositivos usando este perfil possam **Sincronizar com computadores**. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em **Certificados do Apple Configurator**.

10. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em Certificados do Apple Configurator para importar.

11. Selecione **OK**.

12. Escolha as **Configurações do Assistente de Configuração** para definir as seguintes configurações de perfil: ![Personalização do Assistente de Configuração.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


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


13. Selecione **OK**.

14. Para salvar o perfil, escolha **Criar**.

## <a name="connect-school-data-sync"></a>Conectar o School Data Sync
(Opcional) O Apple School Manager dá suporte à sincronização de dados da lista de classes com o Azure AD (Active Directory) usando o Microsoft SDS (School Data Sync). Só é possível sincronizar um token com o SDS. Se você configurar outro token com o School Data Sync, o SDS será removido do token que o tinha anteriormente. Uma nova conexão substituirá o token atual. Conclua as etapas a seguir para usar o SDS para sincronizar dados de estudante.

1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro**.
2. Selecione um token do Apple School Manager e, em seguida, escolha **School Data Sync**.
3. Em **School Data Sync**, escolha **Permitir**. Essa configuração permite que o Intune se conecte com o SDS no Office 365.
4. Para habilitar uma conexão entre o Apple School Manager e o Azure AD, escolha **Configurar o Microsoft School Data Sync**. Saiba mais sobre [como configurar o School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
5. Clique em **Salvar** > **OK**.

## <a name="sync-managed-devices"></a>Sincronizar dispositivos gerenciados

Depois que o Intune tiver recebido permissão para gerenciar seus dispositivos Apple School Manager, sincronize o Intune com o serviço da Apple para ver os dispositivos gerenciados no Intune.

No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha um token na lista > **Dispositivos** > **Sincronizar**. ![Captura de tela do nó Dispositivos de Programa de Registro selecionado com o link de Sincronização escolhido.](./media/device-enrollment-program-enroll-ios/image06.png)

  Para estar em conformidade com os termos da Apple em relação ao tráfego aceitável do programa de registro, o Intune impõe as seguintes restrições:
  - Uma sincronização completa pode ser executada, no máximo, uma vez a cada sete dias. Durante uma sincronização completa, o Microsoft Intune atualiza todos os números de série da Apple atribuídos à nossa plataforma. Se você tentar uma sincronização completa dentro de sete dias após a sincronização completa anterior, o Intune atualizará somente os números de série ainda não listados no Intune.
  - Qualquer solicitação de sincronização tem 15 minutos para ser concluída. Durante esse tempo ou até a solicitação ser bem-sucedida, o botão de **Sincronizar** fica desabilitado.
  - O Intune sincroniza dispositivos novos e removidos com a Apple a cada 24 horas.

>[!NOTE]
>Atribua também números de série do Apple School Manager a perfis na folha **Dispositivos do Programa de Registro**.

## <a name="assign-a-profile-to-devices"></a>Atribuir um perfil a dispositivos
Os dispositivos Apple School Manager gerenciados pelo Intune devem receber um perfil de registro antes de serem registrados.

1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro** > escolha um token na lista.
2. Escolha **Dispositivos**> escolha dispositivos na lista > **Atribuir perfil**.
3. Em **Atribuir perfil**, escolha um perfil para os dispositivos e, em seguida, escolha **Atribuir**.

## <a name="distribute-devices-to-users"></a>Distribuir dispositivos para usuários

Você habilitou o gerenciamento e a sincronização entre o Apple e o Intune e atribuiu um perfil para permitir o registro dos dispositivos Apple School. Agora você pode distribuir dispositivos para os usuários. Quando um dispositivo Apple School Manager do iOS é ativado, ele é registrado no gerenciamento pelo Intune. Se o dispositivo tiver sido ativado e estiver em uso, o perfil não poderá ser aplicado até que o dispositivo seja apagado.
