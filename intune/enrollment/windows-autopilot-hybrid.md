---
title: Registro de dispositivos ingressados no Azure AD híbrido – Windows Autopilot
titleSuffix: ''
description: Use o Windows Autopilot para registrar dispositivos ingressados no Azure AD híbrido no Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/01/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d87a4b5d46a5f0d40cebe3dbcaff211ff508d667
ms.sourcegitcommit: 822a70c61f5d644216ccc401b8e8949bc39e8d4a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76125303"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-by-using-intune-and-windows-autopilot"></a>Implante dispositivos ingressados no Azure AD híbrido usando o Intune e o Windows Autopilot
Você pode usar o Intune e o Windows Autopilot para configurar dispositivos ingressados no Azure Active Directory (Azure AD) híbrido. Para isso, siga as etapas neste artigo.

## <a name="prerequisites"></a>Pré-requisitos

Configurar com êxito seus [dispositivos ingressados no Azure AD híbrido](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan). Certifique-se de [verificar o registro do seu dispositivo](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration) usando o cmdlet Get-MsolDevice.

Os dispositivos a serem registrados também devem:
- Estar executando o Windows 10 v1809 ou posterior.
- Ter acesso à Internet [seguindo os requisitos de rede documentados do Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements).
- Ter acesso a um controlador de domínio do Active Directory, que precisa estar conectado à rede da organização (na qual é possível resolver os registros DNS para o domínio do AD e o controlador de domínio do AD e se comunicar com o controlador de domínio para autenticar o usuário. A conexão VPN não tem suporte no momento).
- Ser capazes de executar ping do controlador do domínio que você está tentando ingressar.
- Se estiver usando um proxy, a opção de configurações de proxy WPAD precisa ser habilitada e definida.
- Percorra a OOBE (experiência de configuração inicial pelo usuário).

## <a name="set-up-windows-10-automatic-enrollment"></a>Configurar o registro automático do Windows 10

1. Entre no Azure e, no painel esquerdo, selecione **Azure Active Directory**.

   ![O portal do Azure](./media/windows-autopilot-hybrid/auto-enroll-azure-main.png)

1. Selecione **Mobilidade (MDM e MAM)** .

   ![O painel do Azure Active Directory](./media/windows-autopilot-hybrid/auto-enroll-mdm.png)

1. Selecione **Microsoft Intune**.

   ![O painel Mobilidade (MDM e MAM)](./media/windows-autopilot-hybrid/auto-enroll-intune.png)

1. Verifique se os usuários que implantam dispositivos ingressados no Azure AD usando o Intune e o Windows são membros de um grupo incluído no seu **escopo do usuário MDM**.

   ![O painel Configurar Mobilidade (MDM e MAM)](./media/windows-autopilot-hybrid/auto-enroll-scope.png)

1. Use os valores padrão para as caixas **Termos de uso do MDM**, **Descoberta do MDM** e **URL da Conformidade do MDM** e, em seguida, selecione **salvar**.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>Aumentar o limite de conta de computador na Unidade Organizacional

O conector do Intune para o Active Directory cria computadores do Autopilot registrados no domínio do Active Directory Local. O computador que hospeda o Conector do Intune deve ter os direitos de criar os objetos de computador dentro do domínio. 

Em alguns domínios, computadores não recebem os direitos para criar computadores. Além disso, os domínios têm um limite integrado (padrão de 10) que se aplica a todos os usuários e computadores que não têm direitos delegados para criar objeto de computador. Portanto, os direitos precisam ser delegados a computadores que hospedam o conector do Intune na unidade organizacional em que os dispositivos ingressados no Azure AD híbrido foram criados.

A unidade organizacional que recebeu o direito de criar computadores deve corresponder:
- À unidade organizacional inserida no perfil do Ingresso no Domínio.
- Ou, se nenhum perfil for selecionado, ao nome de domínio do computador para seu domínio.

1. Abra **Usuários e Computadores do Active Directory** (DSA.msc).

1. Clique com o botão direito do mouse na unidade organizacional que você usará para criar computadores ingressados no Azure AD híbrido e, em seguida, selecione **Delegar Controle**.

    ![O Comando de Delegar Controle](./media/windows-autopilot-hybrid/delegate-control.png)

1. No assistente **Delegação de Controle**, escolha **Avançar** > **Adicionar** > **Tipos de Objeto**.

1. No painel **Tipos de Objeto**, selecione a caixa de seleção **Computadores** e, em seguida, clique em **OK**.

    ![Painel Tipos de objeto](./media/windows-autopilot-hybrid/object-types-computers.png)

1. No painel **Selecionar Usuários, Computadores ou Grupos**, na caixa **Inserir nomes de objeto para selecionar**, insira o nome do computador em que o conector está instalado.

    ![O painel Selecionar usuários, computadores ou grupos](./media/windows-autopilot-hybrid/enter-object-names.png)

1. Selecione **Verificar Nomes** para validar sua entrada, selecione **OK**e, em seguida, selecione **Avançar**.

1. Selecione **Criar uma tarefa personalizada para delegar** > **Avançar**.

1. Selecione a caixa de seleção **Somente os seguintes objetos na pasta** e, em seguida, selecione as caixas de seleção **Objetos de computador**, **Criar objetos selecionados nesta pasta** e **Excluir objetos selecionados nesta pasta**.

    ![O painel Tipo de Objeto do Active Directory](./media/windows-autopilot-hybrid/only-following-objects.png)
    
1. Selecione **Avançar**.

1. Sob **Permissões**, selecione a caixa de seleção **Controle total**.  
    Essa ação selecionará todas as outras opções.

    ![O painel Permissões](./media/windows-autopilot-hybrid/full-control.png)

1. Selecione **Avançar** e, em seguida, selecione **Concluir**.

## <a name="install-the-intune-connector"></a>Instalar o Conector do Intune

O conector do Intune para o Active Directory deve ser instalado em um computador que está executando o Windows Server 2016 ou posterior. O computador também deve ter acesso à internet e ao seu Active Directory. Para aumentar a disponibilidade e a escala ou para dar suporte a vários domínios do Active Directory, você pode instalar vários conectores em seu ambiente. É recomendável instalar o conector em um servidor que não está executando nenhum outro conector do Intune.

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **Windows** > **Registro do Windows** > **Conector do Intune para Active Directory** > **Adicionar**. 
2. Siga as instruções para baixar o Conector.
3. Abra o arquivo de configuração do Conector baixado, *ODJConnectorBootstrapper.exe*, para instalar o Conector.
4. No final da instalação, selecione **Configurar**.
5. Selecione **Entrar.**
6. Insira as credenciais de função de Administrador do Intune ou Administrador Global do usuário.  
   A conta de usuário deve ter uma licença válida do Intune.
7. Vá para **Dispositivos** > **Windows** > **Registro do Windows** > **Conector do Intune para Active Directory** e confirme se o status da conexão é **Ativo**.

> [!NOTE]
> Depois que você entrar no Conector, pode levar alguns minutos para que ele apareça no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431). O Conector somente será exibido se puder se comunicar com êxito com o serviço Intune.

### <a name="turn-off-ie-enhanced-security-configuration"></a>Desativar a Configuração de Segurança Reforçada do IE
Por padrão, o Windows Server tem a Configuração de Segurança Reforçada do Internet Explorer ativada. Se não for possível fazer login no conector do Intune para o Active Directory, desative a Configuração de Segurança Reforçada do IE para o administrador. [Como desabilitar a Configuração de Segurança Reforçada do Internet Explorer](https://blogs.technet.microsoft.com/chenley/2011/03/10/how-to-turn-off-internet-explorer-enhanced-security-configuration)

### <a name="configure-web-proxy-settings"></a>Definir configurações de proxy Web

Se você tiver um proxy da Web em seu ambiente de rede, verifique se o conector do Intune para o Active Directory funciona corretamente consultando [Trabalhar com existentes locais servidores proxy](autopilot-hybrid-connector-proxy.md).


## <a name="create-a-device-group"></a>Criar um grupo de dispositivos
1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Grupos** > **Novo grupo**.

1. No painel **Grupos** pane, faça o seguinte:

    a. Para **Tipo de grupo**, selecione **Segurança**.

    b. Insira o **Nome do grupo** e a **Descrição do grupo**.

    c. Selecione um **Tipo de associação**.

1. Se você selecionou **Dispositivos Dinâmicos** como tipo de associação, no painel **Grupo** selecione **Membros do dispositivo dinâmico** e, em seguida, na caixa **Regra avançada**, faça um dos seguintes:
    - Para criar um grupo que inclua todos os dispositivos do Autopilot, insira `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`.
    - O campo de Marcação de Grupo do Intune é mapeado para o atributo OrderID em dispositivos do Azure AD. Se você pretende criar um grupo que inclua todos os dispositivos do Autopilot com uma Marca de Grupo (OrderID) específica, digite: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
    - Para criar um grupo que inclua todos os dispositivos do Autopilot com uma ID do pedido de compra específica, insira `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`.
    
1. Selecione **Salvar**.

1. Selecione **Criar**.  

## <a name="register-your-autopilot-devices"></a>Registrar seus dispositivos do Autopilot

Escolha uma das maneiras a seguir para registrar seus dispositivos do Autopilot.

### <a name="register-autopilot-devices-that-are-already-enrolled"></a>Registrar dispositivos do Autopilot já registrados

1. Criar um perfil de implantação do Autopilot com **Converter todos os dispositivos de destino para o Autopilot** definido como **Sim**. 
2. Atribua o perfil a um grupo que contém os membros que você deseja registrar automaticamente com o Autopilot.

Para obter mais informações, confira [Criar um perfil de implantação do Autopilot](enrollment-autopilot.md#create-an-autopilot-deployment-profile).

### <a name="register-autopilot-devices-that-arent-enrolled"></a>Registrar dispositivos Autopilot não registrados

Se os dispositivos ainda não estiverem registrados, você poderá registrá-los por conta própria. Para obter mais informações, confira [Adicionar dispositivos](enrollment-autopilot.md#add-devices).

### <a name="register-devices-from-an-oem"></a>Registrar dispositivos de um OEM

Se você estiver comprando novos dispositivos, alguns OEMs poderão registrar dispositivos para você. Para obter mais informações, confira a [página do Windows Autopilot](https://aka.ms/WindowsAutopilot).

Quando seus dispositivos Autopilot são *registrados*, antes de serem registrados no Intune, você pode vê-los em três locais (com nomes definidos para os números seriais):
- O painel **Dispositivos Autopilot** do Intune no portal do Azure. Selecione **Registro de dispositivo** > **Registro do Windows** > **Dispositivos**.
- O painel **Dispositivos do Azure AD** do Intune no portal do Azure. Selecione **Dispositivos** > **Dispositivos do Azure AD**.
- O painel **Todos os dispositivos do Azure AD** do Azure Active Directory no portal do Azure selecionando **Dispositivos** > **Todos os dispositivos**.

Depois que os dispositivos do Autopilot são *registrados*, eles são exibidos em quatro lugares:
- O painel **Dispositivos Autopilot** do Intune no portal do Azure. Selecione **Registro de dispositivo** > **Registro do Windows** > **Dispositivos**.
- O painel **Dispositivos do Azure AD** do Intune no portal do Azure. Selecione **Dispositivos** > **Dispositivos do Azure AD**.
- O painel **Todos os dispositivos do Azure AD** do Azure Active Directory no portal do Azure. Selecione **Dispositivos** > **Todos os dispositivos**.
- O painel **Todos os Dispositivos** do Intune no portal do Azure. Selecione **Dispositivos** > **Todos os dispositivos**.

Depois que os dispositivos do Autopilot são registrados, seus nomes de dispositivo mudam para o nome do host do dispositivo. Por padrão, o nome do host começa com *DESKTOP -* .


## <a name="create-and-assign-an-autopilot-deployment-profile"></a>Criar e atribuir um perfil de implantação do Autopilot
Os perfis de implantação do Autopilot são usados para configurar os dispositivos do Autopilot.

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **Windows** > **Registro do Windows** > **Perfis de Implantação** > **Criar Perfil**.
2. Na página **Básico**, digite um **Nome** e uma **Descrição** opcional.
3. Se quiser que todos os dispositivos nos grupos atribuídos sejam convertidos automaticamente no Autopilot, defina **Converter todos os dispositivos direcionados em Autopilot** como **Sim**. Todos os dispositivos de propriedade corporativa que não sejam Autopilot em grupos atribuídos serão registrados com o serviço de implantação do Autopilot. Os dispositivos de propriedade pessoal não serão convertidos para o Autopilot. Aguarde 48 horas para que o registro seja processado. Quando o registro do dispositivo é cancelado e redefinido, o Autopilot o registra. Após um dispositivo ser registrado dessa maneira, desabilitar essa opção ou remover a atribuição de perfis não removerá o dispositivo do serviço de implantação do Autopilot. Em vez disso, é necessário [remover o dispositivo diretamente](enrollment-autopilot.md#delete-autopilot-devices).
4. Selecione **Avançar**.
5. Na página **OOBE (Experiência de configuração inicial pelo usuário)** , para o **Modo de implantação**, selecione **Orientado pelo usuário**.
6. Na caixa **Ingressar no Azure AD como**, escolha **Ingressado no Azure AD híbrido**.
7. Configure as opções restantes da página **OOBE (Experiência de configuração inicial pelo usuário)** como necessário.
8. Selecione **Avançar**.
9. Na página **Marcas de escopo**, selecione as [marcas de escopo](../fundamentals/scope-tags.md) desse perfil.
10. Selecione **Avançar**.
11. Na página **Atribuições**, escolha **Selecionar grupos para incluir** > pesquise e selecione o grupo de dispositivos > **Selecionar**.
12. Selecione **Avançar** > **Criar**.

Levará cerca de 15 minutos para que o status do perfil de dispositivo mude de *Não atribuídos* para *Atribuindo* e, por fim, para *Atribuído*.

## <a name="optional-turn-on-the-enrollment-status-page"></a>(Opcional) Ative a página de status de registro

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **Windows** > **Registro do Windows** > **Página de Status de Registro**.
1. No painel **Página de Status de Registro**, selecione **Padrão** > **Configurações**.
1. Na caixa **Mostrar o progresso da instalação do aplicativo e do perfil**, selecione **Sim**.
1. Configure as outras opções conforme necessário.
1. Selecione **Salvar**.

## <a name="create-and-assign-a-domain-join-profile"></a>Criar e atribuir um perfil de Ingresso no Domínio

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **Perfis de configuração** > **Criar Perfil**.
2. Insira as seguintes propriedades:
   - **Nome**: insira um nome descritivo para o novo perfil.
   - **Descrição**: Insira uma descrição para o perfil.
   - **Plataforma**: Selecione **Windows 10 e posterior**.
   - **Tipo de perfil**: Selecione **Ingresso no Domínio (Versão Prévia)** .
3. Escolha **Configurações** e forneça um **Prefixo de nome do computador**, **Nome de domínio**.
4. (Opcional) Forneça uma UO **Unidade organizacional** no [formato](https://docs.microsoft.com/windows/desktop/ad/object-names-and-identities#distinguished-name). As opções são:
   - Forneça uma UO na qual você tenha delegado o controle para seu dispositivo Windows 2016 que executa o Intune Connector.
   - Forneça uma UO na qual você tenha delegado o controle para os computadores raiz no Active Directory local.
   - Se deixar em branco, o objeto do computador será criado no contêiner padrão do Active Directory (CN=Computers se você nunca [o alterou](https://support.microsoft.com/en-us/help/324949/redirecting-the-users-and-computers-containers-in-active-directory-dom)).
   
   Estes são alguns exemplos válidos:
   - OU=Level 1,OU=Level2,DC=contoso,DC=com
   - OU=Mine,DC=contoso,DC=com
   
   Estes são alguns exemplos não válidos:
   - CN=Computers,DC=contoso,DC=com  (não é possível especificar um contêiner; em vez disso, deixe o valor em branco para usar o padrão do domínio)
   - OU=Mine (especifique o domínio por meio dos atributos DC=)
     
   > [!NOTE]
   > Não use aspas em volta do valor na **Unidade organizacional**.
5. Selecione **OK** > **Criar**.  
    O perfil é criado e exibido na lista.
6. Para atribuir o perfil, siga as etapas descritas em [Atribuir um perfil de dispositivo](../configuration/device-profile-assign.md#assign-a-device-profile) e atribua o perfil para o mesmo grupo usado na etapa [Criar um grupo de dispositivos](windows-autopilot-hybrid.md#create-a-device-group)
   - Implantar vários perfis de ingresso no domínio
   
     a. Crie um grupo dinâmico que inclua todos os seus dispositivos do Autopilot com um perfil específico de implantação do Autopilot, digite (device.enrollmentProfileName -eq "Nome do perfil do Autopilot"). 
     
     b. Substitua 'Nome do perfil do Autopilot' pelo nome de exibição do perfil criado em [Criar e atribuir um perfil de implantação do Autopilot](windows-autopilot-hybrid.md#create-and-assign-an-autopilot-deployment-profile). 
     
     c. Crie vários perfis de implantação do Autopilot e atribua esse dispositivo ao perfil especificado neste grupo dinâmico.

> [!NOTE]
> As funcionalidades de nomenclatura para o Windows Autopilot para Ingresso no Azure AD Híbrido não dão suporte a variáveis como %SERIAL% e só dão suporte a prefixos para o nome do computador.

## <a name="next-steps"></a>Próximas etapas

Depois de configurar o Windows Autopilot, saiba como gerenciar esses dispositivos. Para obter mais informações, confira [O que é gerenciamento de dispositivos do Microsoft Intune?](../remote-actions/device-management.md).
