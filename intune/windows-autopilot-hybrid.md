---
title: Registro de dispositivos ingressados no Azure AD híbrido – Windows Autopilot
titleSuffix: ''
description: Use o Windows Autopilot para registrar dispositivos ingressados no Azure AD híbrido no Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 030467009e0fed8716a1aa622474188352c0e0b0
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66050347"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-by-using-intune-and-windows-autopilot"></a>Implante dispositivos ingressados no Azure AD híbrido usando o Intune e o Windows Autopilot
Você pode usar o Intune e o Windows Autopilot para configurar dispositivos ingressados no Azure Active Directory (Azure AD) híbrido. Para isso, siga as etapas neste artigo.

## <a name="prerequisites"></a>Pré-requisitos

Configurar com êxito seus [dispositivos ingressados no Azure AD híbrido](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan). Certifique-se de [verificar o registro do seu dispositivo]( https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration) usando o cmdlet Get-MsolDevice.

Os dispositivos a serem registrados também devem:
- Executar o Windows 10 com a [atualização de outubro de 2018](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/).
- Ter acesso à Internet.
- Ter acesso ao Active Directory (não há suporte para a conexão de VPN no momento).
- Percorra a OOBE (experiência de configuração inicial pelo usuário).
- Ser capazes de executar ping do controlador do domínio que você está tentando ingressar.

## <a name="set-up-windows-10-automatic-enrollment"></a>Configurar o registro automático do Windows 10

1. Entre no [Portal do Azure](https://portal.azure.com) e, no painel esquerdo, selecione **Azure Active Directory**.

   ![O portal do Azure](./media/auto-enroll-azure-main.png)

1. Selecione **Mobilidade (MDM e MAM)** .

   ![O painel do Azure Active Directory](./media/auto-enroll-mdm.png)

1. Selecione **Microsoft Intune**.

   ![O painel Mobilidade (MDM e MAM)](./media/auto-enroll-intune.png)

1. Verifique se os usuários que implantam dispositivos ingressados no Azure AD usando o Intune e o Windows são membros de um grupo incluído no seu **escopo do usuário MDM**.

   ![O painel Configurar Mobilidade (MDM e MAM)](./media/auto-enroll-scope.png)

1. Use os valores padrão para as caixas **Termos de uso do MDM**, **Descoberta do MDM** e **URL da Conformidade do MDM** e, em seguida, selecione **salvar**.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>Aumentar o limite de conta de computador na Unidade Organizacional

O conector do Intune para o Active Directory cria computadores do Autopilot registrados no domínio do Active Directory Local. O computador que hospeda o Conector do Intune deve ter os direitos de criar os objetos de computador dentro do domínio. 

Em alguns domínios, computadores não recebem os direitos para criar computadores. Além disso, os domínios têm um limite integrado (padrão de 10) que se aplica a todos os usuários e computadores que não têm direitos delegados para criar objeto de computador. Portanto, os direitos precisam ser delegados a computadores que hospedam o conector do Intune na unidade organizacional em que os dispositivos ingressados no Azure AD híbrido foram criados.

A unidade organizacional que recebeu o direito de criar computadores deve corresponder:
- À unidade organizacional inserida no perfil do Ingresso no Domínio.
- Ou, se nenhum perfil for selecionado, ao nome de domínio do computador para seu domínio.

1. Abra **Usuários e Computadores do Active Directory** (DSA.msc).

1. Clique com o botão direito do mouse na unidade organizacional que você usará para criar computadores ingressados no Azure AD híbrido e, em seguida, selecione **Delegar Controle**.

    ![O Comando de Delegar Controle](media/windows-autopilot-hybrid/delegate-control.png)

1. No assistente **Delegação de Controle**, escolha **Avançar** > **Adicionar** > **Tipos de Objeto**.

1. No painel **Tipos de Objeto**, selecione a caixa de seleção **Computadores** e, em seguida, clique em **OK**.

    ![Painel Tipos de objeto](media/windows-autopilot-hybrid/object-types-computers.png)

1. No painel **Selecionar Usuários, Computadores ou Grupos**, na caixa **Inserir nomes de objeto para selecionar**, insira o nome do computador em que o conector está instalado.

    ![O painel Selecionar usuários, computadores ou grupos](media/windows-autopilot-hybrid/enter-object-names.png)

1. Selecione **Verificar Nomes** para validar sua entrada, selecione **OK**e, em seguida, selecione **Avançar**.

1. Selecione **Criar uma tarefa personalizada para delegar** > **Avançar**.

1. Selecione a caixa de seleção **Somente os seguintes objetos na pasta** e, em seguida, selecione as caixas de seleção **Objetos de computador**, **Criar objetos selecionados nesta pasta** e **Excluir objetos selecionados nesta pasta**.

    ![O painel Tipo de Objeto do Active Directory](media/windows-autopilot-hybrid/only-following-objects.png)
    
1. Selecione **Avançar**.

1. Sob **Permissões**, selecione a caixa de seleção **Controle total**.  
    Essa ação selecionará todas as outras opções.

    ![O painel Permissões](media/windows-autopilot-hybrid/full-control.png)

1. Selecione **Avançar** e, em seguida, selecione **Concluir**.

## <a name="install-the-intune-connector"></a>Instalar o Conector do Intune

O conector do Intune para o Active Directory deve ser instalado em um computador que está executando o Windows Server 2016 ou posterior. O computador também deve ter acesso à internet e ao seu Active Directory. Para aumentar a disponibilidade e a escala ou para dar suporte a vários domínios do Active Directory, você pode instalar vários conectores em seu ambiente. É recomendável instalar o conector em um servidor que não está executando nenhum outro conector do Intune.

1. Certifique-se de ter um pacote de idiomas instalado e configurado como descrito em [Requisitos de idioma do Conector do Intune (versão prévia)](https://docs.microsoft.com/windows/deployment/windows-autopilot/intune-connector).
2. No [Intune](https://aka.ms/intuneportal), selecione **Registro de dispositivo** > **Registro do Windows** > **Conector do Intune para Active Directory (Versão Prévia)**  > **Adicionar conector**. 
3. Siga as instruções para baixar o Conector.
4. Abra o arquivo de configuração do Conector baixado, *ODJConnectorBootstrapper.exe*, para instalar o Conector.
5. No final da instalação, selecione **Configurar**.
6. Selecione **Entrar.**
7. Insira as credenciais de função de Administrador do Intune ou Administrador Global do usuário.  
   A conta de usuário deve ter uma licença válida do Intune.
8. Vá para **Registro de dispositivo** > **Registro do Windows** > **Conector do Intune para Active Directory (Versão Prévia)** e confirme se o status da conexão é **Ativo**.

> [!NOTE]
> Depois que você entrar no Conector, pode levar alguns minutos para que ele apareça no [Intune](https://aka.ms/intuneportal). O Conector somente será exibido se puder se comunicar com êxito com o serviço Intune.

### <a name="turn-off-ie-enhanced-security-configuration"></a>Desativar a Configuração de Segurança Reforçada do IE
Por padrão, o Windows Server tem a Configuração de Segurança Reforçada do Internet Explorer ativada. Se não for possível fazer login no conector do Intune para o Active Directory, desative a Configuração de Segurança Reforçada do IE para o administrador. [Como desabilitar a Configuração de Segurança Reforçada do Internet Explorer](https://blogs.technet.microsoft.com/chenley/2011/03/10/how-to-turn-off-internet-explorer-enhanced-security-configuration)

### <a name="configure-web-proxy-settings"></a>Definir configurações de proxy Web

Se você tiver um proxy da Web em seu ambiente de rede, verifique se o conector do Intune para o Active Directory funciona corretamente consultando [Trabalhar com existentes locais servidores proxy](autopilot-hybrid-connector-proxy.md).


## <a name="create-a-device-group"></a>Criar um grupo de dispositivos
1. Na [Intune](https://aka.ms/intuneportal), selecione **Grupos** > **Novo grupo**.

1. No painel **Grupos** pane, faça o seguinte:

    a. Para **Tipo de grupo**, selecione **Segurança**.

    b. Insira o **Nome do grupo** e a **Descrição do grupo**.

    c. Selecione um **Tipo de associação**.

1. Se você selecionou **Dispositivos Dinâmicos** como tipo de associação, no painel **Grupo** selecione **Membros do dispositivo dinâmico** e, em seguida, na caixa **Regra avançada**, faça um dos seguintes:
    - Para criar um grupo que inclua todos os dispositivos do Autopilot, insira `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`.
    - O campo de Marcação de Grupo do Intune é mapeado para o atributo OrderID em dispositivos do Azure AD. Se você pretende criar um grupo que inclua todos os dispositivos do Autopilot com uma Marcação de Grupo específica (OrderID), digite:  `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
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

Se você estiver comprando novos dispositivos, alguns OEMs poderão registrar dispositivos para você. Para obter mais informações, confira a [página do Windows Autopilot](http://aka.ms/WindowsAutopilot).

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

1. No [Intune](https://aka.ms/intuneportal), selecione **Registro de dispositivo** > **Registro do Windows** > **Perfis de Implantação** > **Criar Perfil**.
1. Digite um **Nome** e, opcionalmente, uma **descrição**.
1. Para **Modo de implantação**, selecione **Orientado pelo Usuário**.
1. Na caixa **Ingressar no Azure AD como**, escolha **Ingressado no Azure AD híbrido (Versão Prévia)** .
1. Selecione **OOBE (configuração inicial pelo usuário)** , configure as opções conforme necessário e, em seguida, selecione **Salvar**.
1. Selecione **Criar** para criar o perfil. 
1. No painel de perfil, selecione **Atribuições**.
1. Selecione **Selecionar grupos**.
1. No painel **Selecionar grupos**, selecione o grupo do dispositivo e, em seguida, clique em **Selecionar**.

Levará cerca de 15 minutos para que o status do perfil de dispositivo mude de *Não atribuídos* para *Atribuindo* e, por fim, para *Atribuído*.

## <a name="optional-turn-on-the-enrollment-status-page"></a>(Opcional) Ative a página de status de registro

1. No [Intune](https://aka.ms/intuneportal), selecione **Registro de Dispositivo** > **Registro do Windows** > **Página de Status de Registro**.
1. No painel **Página de Status de Registro**, selecione **Padrão** > **Configurações**.
1. Na caixa **Mostrar o progresso da instalação do aplicativo e do perfil**, selecione **Sim**.
1. Configure as outras opções conforme necessário.
1. Selecione **Salvar**.

## <a name="create-and-assign-a-domain-join-profile"></a>Criar e atribuir um perfil de Ingresso no Domínio

1. No [Intune](https://aka.ms/intuneportal), selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
1. Insira as seguintes propriedades:
   - **Nome**: insira um nome descritivo para o novo perfil.
   - **Descrição**: Insira uma descrição para o perfil.
   - **Plataforma**: Selecione **Windows 10 e posterior**.
   - **Tipo de perfil**: Selecione **Ingresso no Domínio (Versão Prévia)** .
1. Selecione **Configurações** e forneça um **Prefixo de nome do computador**, **Nome de domínio** e **Unidade organizacional** (opcional) no [formato DN](https://docs.microsoft.com/windows/desktop/ad/object-names-and-identities#distinguished-name). 
1. Selecione **OK** > **Criar**.  
    O perfil é criado e exibido na lista.
1. Para atribuir o perfil, siga as etapas descritas em [Atribuir um perfil de dispositivo](device-profile-assign.md#assign-a-device-profile) e atribua o perfil para o mesmo grupo usado na etapa [Criar um grupo de dispositivos](windows-autopilot-hybrid.md#create-a-device-group)
   - Implantar vários perfis de ingresso no domínio
   
     a. Crie um grupo dinâmico que inclua todos os seus dispositivos do Autopilot com um perfil específico de implantação do Autopilot, digite (device.enrollmentProfileName -eq "Nome do perfil do Autopilot"). 
     
     b. Substitua 'Nome do perfil do Autopilot' pelo nome de exibição do perfil criado em [Criar e atribuir um perfil de implantação do Autopilot](windows-autopilot-hybrid.md#create-and-assign-an-autopilot-deployment-profile). 
     
     c. Crie vários perfis de implantação do Autopilot e atribua esse dispositivo ao perfil especificado neste grupo dinâmico.

> [!NOTE]
> As funcionalidades de nomenclatura para o Windows Autopilot para Ingresso no Azure AD Híbrido não dão suporte a variáveis como %SERIAL% e só dão suporte a prefixos para o nome do computador.

## <a name="next-steps"></a>Próximas etapas

Depois de configurar o Windows Autopilot, saiba como gerenciar esses dispositivos. Para obter mais informações, confira [O que é gerenciamento de dispositivos do Microsoft Intune?](device-management.md).
