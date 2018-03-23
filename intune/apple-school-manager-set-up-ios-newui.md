---
title: Configurar o registro do Programa do Apple School Manager em dispositivos iOS
titleSuffix: Microsoft Intune
description: Saiba como configurar o registro do programa do Apple School Manager em dispositivos iOS de propriedade corporativa com o Intune (nova interface do usuário).
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4c35a23e-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4054eb3804c159e6256b07bf89b8ccd93f7b2e8e
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2018
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Habilitar o registro de dispositivo iOS com o Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> ### <a name="temporary-user-interface-differences"></a>Diferenças de interface de usuário temporárias
>
>As interfaces de usuário para os recursos descritos nesta página estão em processo de atualização. Essas atualizações estão sendo implementadas em todas as contas de usuário até o final de abril.
>
>Se a sua página de **Registro de dispositivo** for semelhante à imagem abaixo, as suas interfaces de usuário estão atualizadas e você pode usar esta página de ajuda.
>
>![Nova interface do usuário](./media/appleenroll-newui.png)
>
>Caso contrário, se a sua página de **Registro de dispositivo** for semelhante à imagem abaixo, sua conta ainda não foi atualizada para a nova interface do usuário. Vá para [esta página de ajuda](apple-school-manager-set-up-ios.md).
>
>![Antiga interface do usuário](./media/appleenroll-oldui.png)

Este tópico o ajuda a habilitar o registro de dispositivo iOS em dispositivos comprados por meio do programa [Apple School Manager](https://school.apple.com/). Ao usar o Intune com o Apple School Manager, é possível registrar grandes quantidades de dispositivos iOS sem a necessidade de tocá-los. Quando um estudante ou professor liga o dispositivo, o Assistente de Configuração é executado com as configurações predefinidas e o dispositivo é registrado no gerenciamento.

Para habilitar o registro do Apple School Manager, é necessário usar os portais do Intune e do Apple School Manager. É necessária uma lista de números de série ou um número de ordem de compra para que você possa atribuir os dispositivos ao Intune para gerenciamento. Você cria perfis de registro de DEP que contém configurações aplicadas aos dispositivos durante o registro.

O registro do Apple School Manager não pode ser usado com o [Programa de registro de dispositivos da Apple](device-enrollment-program-enroll-ios.md) ou o [gerenciador de registros de dispositivo](device-enrollment-manager-enroll.md).

**Pré-requisitos**
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- [Autoridade MDM](mdm-authority-set.md)
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- A afinidade de usuário requer [ponto de extremidade nome do usuário/misto WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints). [Saiba mais](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
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
    - **Registrar com afinidade do usuário** – escolha esta opção para dispositivos que pertencem a usuários e que desejam usar o portal da empresa para serviços como a instalação de aplicativos. Esta opção também permite que os usuários façam a autenticação de seus dispositivos usando o portal da empresa. A afinidade de usuário requer [ponto de extremidade nome do usuário/misto WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints). [Saiba mais](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).   O modo iPad Compartilhado do Apple School Manager exige o registro do usuário sem a afinidade de usuário.

    - **Registrar sem Afinidade do Usuário** – escolha esta opção para dispositivos não afiliados com um único usuário, como um dispositivo compartilhado. Use-a para dispositivos que executam tarefas sem acessar os dados de usuário local. Aplicativos como o aplicativo de Portal da Empresa não funcionam.

5. Se você tiver escolhido **Registrar com Afinidade do Usuário**, terá a opção de permitir que os usuários façam a autenticação com o Portal da Empresa em vez do Assistente de Configuração da Apple.

    ![Faça a autenticação com o Portal da Empresa.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    >[!NOTE]
    >A autenticação multifator (MFA) não funciona durante o registro nos dispositivos Apple School Manager se você tiver propriedades de perfil definidas para **Usar com Afinidade do Usuário** e não estiver usando um Portal da Empresa. Após o registro, a MFA funciona conforme o esperado nesses dispositivos. Os dispositivos não podem exibir uma solicitação aos usuários que precisam alterar sua senha quando entrarem pela primeira vez. Além disso, os usuários com senhas expiradas não receberão uma solicitação para redefinir a senha durante o registro. Os usuários devem usar um dispositivo diferente para redefinir a senha.

6. Escolha **Configurações de Gerenciamento de Dispositivo** e selecione se deseja ou não que os dispositivos que utilizam esse perfil sejam supervisionados.
    Os dispositivos **supervisionados** permitem mais opções de gerenciamento e desabilitam o Bloqueio de Ativação por padrão. A Microsoft recomenda usar o DEP como o mecanismo para habilitar o modo supervisionado, especialmente para as empresas que implantam grandes números de dispositivos iOS.

    Os usuários são notificados de que seus dispositivos são supervisionados de duas maneiras:

    - A tela de bloqueio diz: "Este iPhone é gerenciado pela Contoso".
    - A tela **Configurações** > **Geral** > **Sobre** diz: "Este iPhone é supervisionado. A Contoso pode monitorar o tráfego de Internet e localizar este dispositivo."

     > [!NOTE]
     > Um dispositivo registrado sem supervisão só pode ser redefinido para supervisionado usando o Apple Configurator. A redefinição do dispositivo dessa maneira requer conectar um dispositivo iOS a um Mac com um cabo USB. Saiba mais sobre isso nos [documentos do Apple Configurator](http://help.apple.com/configurator/mac/2.3).

7. Escolha se deseja ou não registro bloqueado para dispositivos que usam esse perfil. O **registro bloqueado** desabilita as configurações de iOS que permitem que o perfil de gerenciamento seja removido do menu **Configurações**. Depois de registrar o dispositivo, não é possível alterar esta configuração sem restaurar as configurações de fábrica. Esses dispositivos devem ter o Modo de Gerenciamento **Supervisionado** configurado como *Sim*. 

8. Se você quiser permitir que múltiplos usuários registrem iPads usando uma ID da Apple gerenciada, escolha **Sim** em **iPad Compartilhado**. Isso requer que o modo **Registrar sem Afinidade do Usuário** e **Supervisionado** sejam configurados como **Sim**. As IDs da Apple gerenciadas são criadas no portal do Apple School Manager. Saiba mais sobre [iPad compartilhado](education-settings-configure-ios-shared.md). Você também deve examinar os [requisitos de iPad compartilhado da Apple](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56).

9. Escolha se deseja ou não que os dispositivos usando este perfil possam **Sincronizar com computadores**. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em **Certificados do Apple Configurator**.

9. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em Certificados do Apple Configurator para importar.

10. Selecione **OK**.

11. Escolha as **Configurações do Assistente de Configuração** para definir as seguintes configurações de perfil: ![Personalização do Assistente de Configuração.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)

    | Setting | Descrição |
    | --- | --- |
    | **Nome do Departamento** | Aparece quando os usuários tocam em **Sobre a Configuração** durante a ativação. |
    | **Telefone do Departamento** | Aparece quando o usuário clica no botão **Precisa de Ajuda** durante a ativação. |
    | **Opções do Assistente de Instalação** | As configurações opcionais a seguir podem ser configuradas posteriormente no menu **Configurações** do iOS. |
    | **Senha** | Solicitar senha durante a ativação. Sempre exija uma senha, a menos que o dispositivo esteja protegido ou tenha o acesso controlado de alguma outra maneira (ou seja, o modo de quiosque que restringe o dispositivo a um aplicativo). |
    | **Serviços de Localização** | Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação. |
    | **Restaurar** | Se habilitado, o Assistente de Instalação solicitará o backup do iCloud durante a ativação. |
    | **iCloud e ID da Apple** | Se habilitado, o Assistente de Configuração solicita ao usuário que insira uma ID da Apple e a tela Aplicativos e Dados permitirá que o dispositivo seja restaurado a partir do backup do iCloud. |
    | **Termos e Condições** | Se habilitado, o Assistente de Instalação solicitará que os usuários aceitem os termos e as condições da Apple durante a ativação. |
    | **ID de Toque** | Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação. |
    | **Apple Pay** | Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação. |
    | **Zoom** | Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação. |
    | **Siri** | Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação. |
    | **Dados de diagnóstico** | Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação. |

12. Selecione **OK**.

13. Para salvar o perfil, escolha **Criar**.

## <a name="connect-school-data-sync"></a>Conectar o School Data Sync
(Opcional) O Apple School Manager dá suporte à sincronização de dados da lista de classes com o Azure AD (Active Directory) usando o Microsoft SDS (School Data Sync). Só é possível sincronizar um token com o SDS. Se você configurar outro token com o School Data Sync, o SDS será removido do token que o tinha anteriormente. Uma nova conexão substituirá o token atual. Conclua as etapas a seguir para usar o SDS para sincronizar dados de estudante.

1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro da Apple** > **Tokens de programa de registro**.
2. Selecione um token do Apple School Manager e, em seguida, escolha **School Data Sync**.
3. Em **School Data Sync**, escolha **Permitir**. Essa configuração permite que o Intune se conecte com o SDS no Office 365.
4. Para habilitar uma conexão entre o Apple School Manager e o Azure AD, escolha **Configurar o Microsoft School Data Sync**. Saiba mais sobre [como configurar o School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
5. Clique em **Salvar** > **OK**.

## <a name="sync-managed-devices"></a>Sincronizar dispositivos gerenciados

Agora que o Intune recebeu permissão para gerenciar seus dispositivos Apple School Manager, é possível sincronizar o Intune com o serviço da Apple para ver os dispositivos gerenciados no Intune.

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

Você habilitou o gerenciamento e a sincronização entre o Apple e o Intune e atribuiu um perfil para permitir o registro dos dispositivos Apple School. Agora você pode distribuir dispositivos para os usuários. Quando um dispositivo Apple School Manager do iOS é ativado, ele é registrado no gerenciamento pelo Intune. Se o dispositivo tiver sido ativado e estiver em uso, o perfil não poderá ser aplicado até que o dispositivo volte à redefinição de fábrica.
