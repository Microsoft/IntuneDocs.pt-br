---
title: Configurar o registro do Programa do Apple School Manager em dispositivos iOS
titleSuffix: Intune on Azure
description: Saiba como configurar o registro do programa do Apple School Manager em dispositivos iOS de propriedade corporativa com o Intune
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 91fd4719a4305f5e422163f9049684ebd9e9e656
ms.sourcegitcommit: bb1a1e4e0bc26543a9c8fb52cb208e298c6b8e3f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Habilitar o registro de dispositivo iOS com o Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este tópico o ajuda a habilitar o registro de dispositivo iOS em dispositivos comprados por meio do programa [Apple School Manager](https://school.apple.com/). Ao usar o Intune com o Apple School Manager, é possível registrar grandes quantidades de dispositivos iOS sem a necessidade de tocá-los. Quando um estudante ou professor liga o dispositivo, o Assistente de Configuração é executado com as configurações predefinidas e o dispositivo é registrado no gerenciamento.

Para habilitar o registro do Apple School Manager, é necessário usar os portais do Intune e do Apple School Manager. É necessária uma lista de números de série ou um número de ordem de compra para que você possa atribuir os dispositivos ao Intune para gerenciamento. Você cria perfis de registro de DEP que contém configurações aplicadas aos dispositivos durante o registro.

Além do mais, o registro do Apple School Manager não pode ser usado com o [Programa de registro de dispositivos da Apple](device-enrollment-program-enroll-ios.md) ou o [gerenciador de registros de dispositivo](device-enrollment-manager-enroll.md).

**Pré-requisitos**
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- [Autoridade MDM](mdm-authority-set.md)
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- A afinidade de usuário requer [ponto de extremidade nome do usuário/misto WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints). [Saiba mais](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Dispositivos comprados no programa [Apple School Management](http://school.apple.com)

**Etapas de registro do Apple School Manager**
1. [Obter um token Apple School Manager e atribuir dispositivos](#get-the-apple-token-and-assign-devices)
2. [Criar um perfil de registro](#create-an-apple-enrollment-profile)
3. [Conectar o School Data Sync](#connect-school-data-sync) (opcional)
4. [Sincronizar dispositivos gerenciados pelo Apple School Manager](#sync-managed-devices)
5. [Atribuir perfil do Apple School Manager a dispositivos](#assign-a-profile-to-devices)
6. [Distribuir dispositivos para usuários](#distribute-devices-to-users)

>[!NOTE]
>A MFA (autenticação multifator) não funciona durante o registro em dispositivos Apple School Manager com a afinidade de usuário. Após o registro, a MFA funciona conforme o esperado nesses dispositivos. Após o registro, a MFA funciona conforme o esperado nos dispositivos. Os dispositivos não podem exibir uma solicitação aos usuários que precisam alterar sua senha quando entrarem pela primeira vez. Além disso, os usuários com senhas expiradas não receberão uma solicitação para redefinir a senha durante o registro. Os usuários devem usar um dispositivo diferente para redefinir a senha.


## <a name="get-the-apple-token-and-assign-devices"></a>Obter o token Apple e atribuir dispositivos

Antes de poder registrar dispositivos iOS de propriedade corporativa com o Apple School Manager, você precisa de um arquivo de token (.p7m) da Apple. Esse token permite que o Intune sincronize informações sobre os dispositivos que participam do Apple School Manager. Ele também permite que o Intune realize carregamentos de perfis de registro para a Apple e atribua dispositivos a esses perfis. No portal da Apple, você também pode atribuir números de série do dispositivo a serem gerenciados.

**Etapa 1. Baixe o certificado de chave pública do Intune necessário para criar um token Apple.**<br>
1. No [Intune no Portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** e, em seguida, escolha **Token do programa de registro**.

  ![Captura de tela do painel do Token de Programa de Registro no espaço de trabalho de Certificados da Apple para baixar a chave pública.](./media/enrollment-program-token-download.png)

2. Na folha **Token do programa de registro**, escolha **Baixar a chave pública** para baixar e salvar o arquivo de chave de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Apple School Manager.

**Etapa 2. Baixar um token e atribuir dispositivos.**<br>
1. Escolha **Criar um token por meio do Apple School Manager** e entre com sua ID corporativa da Apple. Use essa ID da Apple para renovar o token Apple School Manager.
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

**Etapa 3. Inserir a ID da Apple usada para criar o token Apple School Manager.**<br>Essa ID deve ser usada para renovar o token Apple School Manager e é armazenada para referência futura.

![Captura de tela mostrando a especificação do ID Apple usado para criar o Token do Programa de Registro e a navegação para este recurso.](./media/enrollment-program-token-apple-id.png)

**Etapa 4. Localizar e carregar o token.**<br>
Acesse o arquivo de certificado (.p7m), escolha **Abrir** e, depois, **Carregar**. O Intune sincroniza automaticamente os dispositivos Apple School Manager da Apple.

## <a name="create-an-apple-enrollment-profile"></a>Criar um perfil de registro da Apple
Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** e, em seguida, escolha **Registro da Apple**.
2. Em **Programa de Registro**, escolha **Perfis do Programa de Registro**.
3. Na folha **Perfis do Programa de Registro**, escolha **Criar**.
4. Na folha **Criar Perfil de Registro**, insira um **Nome** e uma **Descrição** para o perfil exibido no Intune.
5. Em **Afinidade de Usuário**, escolha se os dispositivos com esse perfil são registrados com ou sem a afinidade de usuário.

 - **Registrar com afinidade do usuário** – afilia o dispositivo a um usuário durante a instalação.

  O modo iPad Compartilhado do Apple School Manager exige o registro do usuário sem a afinidade de usuário.

 - **Registrar sem afinidade do usuário** – escolha para dispositivos não afiliados com um único usuário, como dispositivos compartilhados. Use para dispositivos que executam tarefas sem acessar os dados de usuário local. Aplicativos como o aplicativo de Portal da Empresa não funcionam.

6. Escolha **Configurações de Gerenciamento de Dispositivos**. Esses itens são definidos durante a ativação e exigem uma redefinição para as configurações de fábrica para serem alterados. Defina as seguintes configurações de perfil e, em seguida, escolha **Salvar**:

  ![Captura de tela mostrando a escolha do Modo de Gerenciamento. O dispositivo apresenta as seguintes configurações: Supervisionado, Registro Bloqueado e Permitir Emparelhamento definido como Negar todos. O recurso Certificados do Apple Configurator está desabilitado para um novo perfil do Programa de Registro.](./media/enrollment-program-profile-mode.png)

    - **Supervisionado** – Um modo de gerenciamento que habilita mais opções de gerenciamento e desabilitou o Bloqueio de Ativação por padrão. Se você deixar a caixa de seleção, terá recursos de gerenciamento limitados.

     - **Registro bloqueado** – (Requer o Modo de Gerenciamento = Supervisionado) Desabilita as configurações de iOS que podem permitir a remoção do perfil de gerenciamento. Se você deixar a caixa de seleção em branco, permitirá que o perfil de gerenciamento seja removido do menu Configurações.
   - **iPad Compartilhado** – (exige os modos **Registro sem Afinidade de Usuário** e **Supervisionado**.) Permite que vários usuários façam logon em iPads registrados usando uma ID da Apple gerenciada. As IDs da Apple gerenciadas são criadas no portal do Apple School Manager. Saiba mais sobre [iPad compartilhado](education-settings-configure-ios-shared.md).
   >[!NOTE]
   >Se **Afinidade do Usuário** estiver definida como **Com afinidade do usuário** ou o modo **Supervisionado** estiver definido como **Desativado**, o modo iPad compartilhado será desabilitada para o perfil de registro.

        - **Maximum Cached Users** - (Requires **Shared iPad** = **Yes**) Creates a partition on the device for each user. The recommended value is the number of students likely to use the device over a period of time. For example, if six students use the device regularly during the week, set this number to six.  

    - **Permitir Emparelhamento** – Especifica se os dispositivos iOS podem sincronizar com computadores. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em **Certificados do Apple Configurator**.

      - **Certificados do Apple Configurator** – Se que você escolheu **Permitir Apple Configurator por certificado** em **Permitir Emparelhamento**, escolha um Certificado do Apple Configurator para ser importado.

7. Escolha as **Configurações de Assistente de Instalação**, defina as seguintes configurações de perfil e, em seguida, escolha **Salvar**:

    - **Nome do Departamento** – Aparece quando os usuários tocam em **Sobre a Configuração** durante a ativação.

    - **Telefone do Departamento** – Aparece quando o usuário clica no botão Precisa de Ajuda durante a ativação.
    - **Opções do Assistente de Configuração** – se forem excluídas das opções do Assistente de Configuração, essas configurações poderão ser definidas posteriormente no menu **Configurações** do iOS.
        - **Senha** - Solicitar senha durante a ativação. Sempre exija uma senha, a menos que o dispositivo esteja protegido ou tenha o acesso controlado de alguma outra maneira (ou seja, o modo de quiosque que restringe o dispositivo a um aplicativo).
        - **Serviços de Localização** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação
        - **Restaurar** - Se habilitado, o Assistente de Instalação solicitará o backup do iCloud durante a ativação
        - **ID da Apple** – se estiver habilitado, o iOS solicitará aos usuários uma ID da Apple quando o Intune tentar instalar um aplicativo sem uma ID. Uma ID da Apple é necessária para baixar aplicativos da iOS App Store, incluindo aplicativos instalados pelo Intune.
        - **Termos e Condições** - Se habilitado, o Assistente de Instalação solicitará que os usuários aceitem os termos e as condições da Apple durante a ativação
        - **ID de Toque** – Se habilitada, o Assistente de Configuração solicitará o serviço durante a ativação
        - **Apple Pay** – Se habilitado, o Assistente de Configuração solicitará o serviço durante a ativação
        - **Zoom** – Se habilitado, o Assistente de Configuração solicitará o serviço durante a ativação
        - **Siri** - Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação
        - **Dados de Diagnóstico** – Se habilitado, o Assistente de Instalação solicitará o serviço durante a ativação

8. Para salvar as configurações de perfil, escolha **Criar** na folha **Criar Perfil de Registro**.

## <a name="connect-school-data-sync"></a>Conectar o School Data Sync
(Opcional) O Apple School Manager dá suporte à sincronização de dados da lista de classes com o Azure AD (Active Directory) usando o Microsoft SDS (School Data Sync). Conclua as etapas a seguir para usar o SDS para sincronizar dados de estudante.

1. Na folha **Token do Programa de Registro**, escolha a faixa de informações azul ou **Conectar SDS**.
2. Escolha **Permitir que o Microsoft School Data Sync use este token**, definindo como **Permitir**. Essa configuração permite que o Intune se conecte com o SDS no Office 365.
3. Para habilitar uma conexão entre o Apple School Manager e o Azure AD, escolha **Configurar o Microsoft School Data Sync**. Saiba mais sobre [como configurar o School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Clique em **OK** para salvar e continuar.

## <a name="sync-managed-devices"></a>Sincronizar dispositivos gerenciados
Agora que o Intune recebeu permissão para gerenciar seus dispositivos Apple School Manager, é possível sincronizar o Intune com o serviço da Apple para ver os dispositivos gerenciados no Intune.

1. No Intune no Portal do Azure, escolha **Registro de dispositivo** e, em seguida, escolha **Registro da Apple**.
2. Em **Dispositivos do Programa de Registro**, escolha **Sincronizar**. A barra de progresso mostra a quantidade de tempo que você deve aguardar antes de solicitar a Sincronização novamente.
3. Na folha **Sincronizar**, escolha **Solicitar Sincronização**. A barra de progresso mostra a quantidade de tempo que você deve aguardar antes de solicitar a Sincronização novamente.

  ![Captura de tela mostrando a folha Sincronização com o link Solicitar sincronização escolhido.](./media/enrollment-program-device-request-sync.png)

  Para estar em conformidade com os termos da Apple em relação ao tráfego aceitável, o Intune impõe as seguintes restrições:
   -    Uma sincronização completa pode ser executada, no máximo, uma vez a cada sete dias. Durante uma sincronização completa, o Intune atualiza cada número de série que a Apple atribuiu ao Intune, tenha o número de série sido sincronizado anteriormente ou não. Se você tentar uma sincronização completa dentro de sete dias após a sincronização completa anterior, o Intune atualizará somente os números de série ainda não listados no Intune.
   -    Qualquer solicitação de sincronização tem 15 minutos para ser concluída. Durante esse tempo ou até a solicitação ser bem-sucedida, o botão de **Sincronizar** fica desabilitado.

>[!NOTE]
>Atribua também números de série do Apple School Manager a perfis na folha **Dispositivos do Programa de Registro**.

## <a name="assign-a-profile-to-devices"></a>Atribuir um perfil a dispositivos
Os dispositivos Apple School Manager gerenciados pelo Intune devem receber um perfil de registro antes de serem registrados.

1. No Intune no portal do Azure, escolha **Registro de dispositivo** > **Registro da Apple** e, em seguida, escolha **Perfis do Programa de Registro**.
2. Na lista de **Perfis do Programa de Registro**, escolha o perfil que será atribuído aos dispositivos e, em seguida, escolha **Atribuir dispositivos**

 ![Captura de tela de Atribuições de Dispositivo com Atribuir sendo selecionado.](./media/enrollment-program-device-assign.png)

3. Escolha **Atribuir** e, em seguida, selecione os dispositivos Apple School Manager que serão atribuídos a esse perfil. Filtre para exibir os dispositivos disponíveis:
  - **não atribuído**
  - **qualquer**
  - **&lt;nome do perfil&gt;**
4. Escolha os dispositivos que deseja atribuir. A caixa de seleção acima da coluna seleciona até 1.000 dispositivos listados. Clique em **Atribuir**. Para registrar mais de 1000 dispositivos, repita as etapas de atribuição até que todos os dispositivos sejam atribuídos a um perfil de registro.

  ![Captura de tela do botão Atribuir para atribuir o perfil do programa de registro no Intune](media/dep-profile-assignment.png)

## <a name="distribute-devices-to-users"></a>Distribuir dispositivos para usuários

Agora você pode distribuir dispositivos da empresa para os usuários. Quando um dispositivo Apple School Manager do iOS é ativado, ele é registrado no gerenciamento pelo Intune. Se o dispositivo tiver sido ativado e estiver em uso, o perfil não poderá ser aplicado até que o dispositivo volte à redefinição de fábrica.
