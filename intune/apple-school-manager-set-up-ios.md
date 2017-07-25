---
title: Configurar o registro do Programa do Apple School Manager em dispositivos iOS
titleSuffix: Intune on Azure
description: Saiba como configurar o registro do programa do Apple School Manager em dispositivos iOS de propriedade corporativa com o Intune
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73556209c88759ffe0747d9927cbcbb49600e0c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Habilitar o registro de dispositivo iOS com o Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este tópico ajuda os administradores de TI a habilitar o registro de dispositivo iOS em dispositivos comprados por meio do programa [ASM](https://school.apple.com/) (Apple School Manager). O Microsoft Intune pode implantar um perfil de registro “sem fio” que registra os dispositivos ASM no gerenciamento. O administrador nunca precisa tocar em nenhum dispositivo gerenciado. Um perfil do ASM contém as configurações de gerenciamento que são aplicadas aos dispositivos durante o registro, incluindo opções do Assistente de Configuração.

**Etapas do Registro do ASM**
1. [Obter um token ASM e atribuir dispositivos](#get-the-asm-token-and-assign-devices)
2. [Criar um perfil de registro](#create-an-apple-enrollment-profile)
3. [Conectar o School Data Sync](#connect-school-data-sync) (opcional)
4. [Sincronizar dispositivos gerenciados pelo ASM](#sync-asm-managed-devices)
5. [Atribuir um perfil do ASM a dispositivos](#assign-an-asm-profile-to-devices)
6. [Distribuir dispositivos para usuários](#distribute-devices-to-users)

>[!NOTE]
>O registro do ASM não pode ser usado com o [DEP (Programa de registro de dispositivos)](device-enrollment-program-enroll-ios.md) da Apple nem com uma conta do [gerenciador de registros de dispositivo](device-enrollment-manager-enroll.md) do Intune.

## <a name="get-the-apple-asm-token-and-assign-devices"></a>Obter o token Apple ASM e atribuir dispositivos

Antes de poder registrar dispositivos iOS de propriedade corporativa com o ASM (Apple School Manager), você precisa de um arquivo de token (.p7m) ASM da Apple. Esse token permite que o Intune sincronize informações sobre os dispositivos que participam do ASM. Ele também permite que o Intune realize carregamentos de perfis de registro para a Apple e atribua dispositivos a esses perfis. No portal da Apple, você também pode atribuir números de série do dispositivo a serem gerenciados.

**Pré-requisitos**
- [Apple MDM Push Certificate](apple-mdm-push-certificate-get.md)
- Inscrição no [Apple School Management](http://school.apple.com)

**Etapa 1. Baixar o certificado de chave pública do Intune necessário para criar um token Apple ASM.**<br>
1. No [portal do Intune](https://aka.ms/intuneportal) no Azure, escolha **Registro de dispositivo** e, em seguida, selecione **Token do programa de registro**.
2. Na folha **Token do programa de registro**, selecione **Baixar a chave pública** para baixar e salvar o arquivo de chave de criptografia (.pem) localmente. O arquivo .pem é usado para solicitar um certificado de relação de confiança do portal do Apple School Manager.

**Etapa 2. Baixar um token ASM e atribuir dispositivos.**<br>
Selecione **Criar um token por meio do Apple School Manager** e entre com sua ID corporativa da Apple. Use essa ID da Apple para renovar o token ASM.

   1.  No [portal do Apple School Manager](https://school.apple.com), acesse **Servidores MDM** e, em seguida, selecione **Adicionar Servidor MDM** (canto superior direito).
   2.  Insira o **Nome do Servidor MDM**. O nome do servidor é para sua referência para identificar o servidor MDM (gerenciamento de dispositivo móvel). Não é o nome ou URL do servidor Microsoft Intune.
   3.  Selecione **Carregar Arquivo...**  no portal da Apple, procure o arquivo .pem e selecione **Salvar Servidor MDM** (canto inferior direito).
   4.  Selecione **Obter Token** e, em seguida, baixe o arquivo de token (.p7m) do servidor no computador.
   5. Acesse **Atribuições de Dispositivo** e **Escolher Dispositivo** com a entrada manual dos **Números de Série**, do **Número do Pedido** ou **Carregar Arquivo CSV**.
   6.   Escolha a ação **Atribuir ao Servidor** e selecione o **Servidor MDM** criado.
   7. Especifique como você vai **Escolher Dispositivos**, forneça informações do dispositivo e especifique os detalhes por **Número de Série**, **Número do Pedido** ou **Carregar o Arquivo CSV**.
   8. Escolha **Atribuir ao Servidor**, escolha o &lt;ServerName&gt; especificado para o Microsoft Intune e escolha **OK**.

**Etapa 3. Inserir a ID da Apple usada para criar o token ASM.**<br>Essa ID deve ser usada para renovar o token Apple ASM e é armazenada para referência futura.

**Etapa 4. Localizar e carregar o token.**<br>
Acesse o arquivo de certificado (.p7m), escolha **Abrir** e, depois, **Carregar**. O Intune sincroniza automaticamente os dispositivos ASM da Apple.

## <a name="create-an-apple-enrollment-profile"></a>Criar um perfil de registro da Apple
Um perfil de registro de dispositivo define as configurações aplicadas a um grupo de dispositivos durante o registro.

1. No portal do Intune, escolha **Registro de dispositivo** e, depois, **Registro da Apple**.
2. Em **Programa de Registro**, selecione **Perfis do Programa de Registro**.
3. Na folha **Perfis do Programa de Registro**, selecione **Criar**.
4. Na folha **Criar Perfil de Registro**, insira um **Nome** e uma **Descrição** para o perfil que é exibido no portal do Intune.
5. Em **Afinidade de Usuário**, escolha se os dispositivos com esse perfil são registrados com ou sem a afinidade de usuário.

 - **Inscrever com afinidade do utilizador** – O dispositivo deve ser afiliado a um usuário durante a configuração inicial e, depois, pode receber permissão para acessar dados e email da empresa. Escolha afinidade de usuário para os dispositivos gerenciados pelo ASM nos quais os usuários fazem logon com suas IDs da Apple gerenciadas.

 >[!NOTE]
 >O MFA (autenticação multifator) não funciona durante o registro em dispositivos ASM com a afinidade de usuário. Após o registro, a MFA funciona conforme o esperado nesses dispositivos.

  O modo iPad Compartilhado do Apple School Manager exige o registro do usuário com a afinidade de usuário.

 >[!NOTE]
    >O ASM com a afinidade de usuário exige que o [ponto de extremidade Nome do usuário/Misto WS-Trust 1.3](https://technet.microsoft.com/library/adfs2-help-endpoints) seja habilitado para solicitar um token de usuário. [Saiba mais sobre o WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Inscrever sem afinidade do utilizador** – O dispositivo não está afiliado a um usuário. Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local. Aplicativos que exigem a afinidade de usuário (incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios) não funcionarão.

6. Selecione **Configurações de Gerenciamento de Dispositivos**. Esses itens são definidos durante a ativação e exigem uma redefinição para as configurações de fábrica para serem alterados. defina as seguintes configurações de perfil e, em seguida, selecione **Salvar**:

    - **Supervisionado** – Um modo de gerenciamento que habilita mais opções de gerenciamento e desabilitou o Bloqueio de Ativação por padrão. Se você deixar a caixa de seleção, terá recursos de gerenciamento limitados.

    - **Registro bloqueado** – (Requer o Modo de Gerenciamento = Supervisionado) Desabilita as configurações de iOS que podem permitir a remoção do perfil de gerenciamento. Se você deixar a caixa de seleção em branco, permitirá que o perfil de gerenciamento seja removido do menu Configurações.

  - **iPad Compartilhado** – (exige os modos **Registro com Afinidade de Usuário** e **Supervisionado**.) Permite que vários usuários façam logon em iPads registrados usando uma ID da Apple gerenciada. As IDs da Apple gerenciadas são criadas no portal do Apple School Manager.

  >[!NOTE]
  >Se o modo **iPad Compartilhado** estiver habilitado em um perfil e um modo **Afinidade de Usuário** ou **Supervisionado** for então definido como **Desativado**, o modo iPad Compartilhado será desabilitado no perfil de registro.

  - **Máximo de Usuários Armazenados em Cache** – (exige **iPad Compartilhado** = **Sim**) cria uma partição no dispositivo para cada usuário. O valor recomendado é o número de alunos que provavelmente usarão o dispositivo durante um período. Por exemplo, se seis alunos usarem o dispositivo regularmente durante a semana, defina esse número como seis.  

    - **Permitir Emparelhamento** – Especifica se os dispositivos iOS podem sincronizar com computadores. Se você escolher **Permitir Apple Configurator por certificado**, deverá escolher um certificado em **Certificados do Apple Configurator**.

    - **Certificados do Apple Configurator** – Se que você escolheu **Permitir Apple Configurator por certificado** em **Permitir Emparelhamento**, selecione um Certificado do Apple Configurator para ser importado.

7. Selecione as **Configurações de Assistente de Instalação**, defina as seguintes configurações de perfil e, em seguida, selecione **Salvar**:

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

8. Para salvar as configurações de perfil, selecione **Criar** na folha **Criar Perfil de Registro**.

## <a name="connect-school-data-sync"></a>Conectar o School Data Sync
(Opcional) O ASM dá suporte à sincronização de dados da lista de classes com o Azure AD (Active Directory) usando o Microsoft SDS (School Data Sync). Conclua as etapas a seguir para usar o SDS para sincronizar dados de estudante.

1. Na folha **Token do Programa de Registro**, selecione a faixa de informações azul ou **Conectar SDS**.
2. Selecione **Permitir que o Microsoft School Data Sync use este token**, definindo como **Permitir**. Essa configuração permite que o Intune se conecte com o SDS no Office 365.
3. Para habilitar uma conexão entre o ASM e o Azure AD, selecione **Configurar o Microsoft School Data Sync**. Saiba mais sobre [como configurar o School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Clique em **OK** para salvar e continuar.

## <a name="sync-asm-managed-devices"></a>Sincronizar dispositivos gerenciados pelo ASM
Agora que o Intune recebeu permissão para gerenciar seus dispositivos ASM, você pode sincronizar o Intune com o serviço ASM para ver os dispositivos gerenciados no portal do Intune.

1. No portal do Intune, escolha **Registro de dispositivo** e, depois, **Registro da Apple**.
2. Em **Dispositivos do Programa de Registro**, selecione **Sincronização**. A barra de progresso mostra a quantidade de tempo que você deve aguardar antes de solicitar a Sincronização novamente.

    Para estar em conformidade com os termos da Apple em relação ao tráfego do ASM aceitável, o Intune impõe as seguintes restrições:
     -  Uma sincronização completa do ASM pode ser executada, no máximo, uma vez a cada sete dias. Durante uma sincronização completa, o Intune atualiza cada número de série que a Apple atribuiu ao Intune, tenha o número de série sido sincronizado anteriormente ou não. Se você tentar uma sincronização completa dentro de sete dias após a sincronização completa anterior, o Intune atualizará somente os números de série ainda não listados no Intune.
     -  Qualquer solicitação de sincronização tem 15 minutos para ser concluída. Durante esse tempo ou até a solicitação ser bem-sucedida, o botão de **Sincronizar** fica desabilitado.

>[!NOTE]
>Atribua também números de série do ASM a perfis na folha **Dispositivos do Programa de Registro**.

## <a name="assign-an-asm-profile-to-devices"></a>Atribuir um perfil do ASM a dispositivos
Os dispositivos ASM gerenciados pelo Intune devem receber um perfil do ASM antes de serem registrados.

1. No portal do Intune, escolha **Registro de dispositivo** > **Registro da Apple** e, em seguida, selecione **Perfis do Programa de Registro**.
2. Na lista de **Perfis do Programa de Registro**, selecione o perfil que você deseja atribuir a dispositivos e, em seguida, selecione **Atribuições de Dispositivo**
3. Selecione **Atribuir** e, em seguida, selecione os dispositivos ASM que você deseja atribuir a esse perfil. Filtre para exibir os dispositivos ASM disponíveis:
  - **não atribuído**
  - **qualquer**
  - **&lt;Nome do perfil do ASM&gt;**
4. Selecionar os dispositivos que deseja atribuir. A caixa de seleção acima da coluna seleciona até 1.000 dispositivos listados. Clique em **Atribuir**. Para registrar mais de 1.000 dispositivos, repita as etapas de atribuição até que todos os dispositivos sejam atribuídos a um perfil do ASM.

## <a name="distribute-devices-to-users"></a>Distribuir dispositivos para usuários

Agora você pode distribuir dispositivos da empresa para os usuários. Quando um dispositivo ASM do iOS é ativado, ele é registrado no gerenciamento pelo Intune. Se o dispositivo tiver sido ativado e estiver em uso, o perfil não poderá ser aplicado até que o dispositivo volte à redefinição de fábrica.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Como os usuários instalam e usam o Portal da Empresa em seus dispositivos

Os dispositivos configurados com a afinidade de usuário podem instalar e executar o aplicativo Portal da Empresa para baixar aplicativos e gerenciar dispositivos. Depois que os usuários recebem seus dispositivos, eles devem executar o Assistente de Configuração e instalar o aplicativo do Portal da Empresa.
