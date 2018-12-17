---
title: Inscrição de dispositivos ingressados no Active Directory híbrido – Windows Autopilot
titleSuffix: ''
description: Use o Windows Autopilot para registrar dispositivos ingressados no Active Directory híbrido no Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: ced67b2dcdd5720a9708868808ec885938b8ddcd
ms.sourcegitcommit: 5058dbfb0e224207dd4e7ca49712c6ad3434c83c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2018
ms.locfileid: "53112435"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-using-intune-and-windows-autopilot-preview"></a>Implantar dispositivos ingressados no Azure AD híbrido usando o Intune e o Windows Autopilot (Versão Prévia)
Você pode usar o Intune e o Windows Autopilot para configurar dispositivos ingressados no Azure Active Directory híbrido. Para isso, siga as etapas em abaixo.

> [!NOTE]
> Esse recurso será implantando em toda a base de usuários nos próximos dias. Portanto, você não poderá seguir estas etapas até que ela seja distribuída para a sua conta.

## <a name="prerequisites"></a>Pré-requisitos

- Configure com êxito [dispositivos ingressados no Azure Active Directory híbrido](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan).
    - Não deixe de [verificar o registro usando o cmdlet Get-MsolDevice]( https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration).

Os dispositivos a serem registrados também devem:
- Executar o Windows 10 com a [atualização de outubro de 2018](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/).
- Ter acesso à Internet.
- Ter acesso ao Active Directory (não há suporte para a conexão de VPN).
- Percorra a OOBE (experiência de configuração inicial pelo usuário).

## <a name="set-up-windows-10-automatic-enrollment"></a>Configurar o registro automático do Windows 10

1. Entre no [Portal do Azure](https://portal.azure.com) e selecione **Azure Active Directory**.

   ![Captura de tela do portal do Azure](./media/auto-enroll-azure-main.png)

2. Selecione **Mobilidade (MDM e MAM)**.

   ![Captura de tela do portal do Azure](./media/auto-enroll-mdm.png)

3. Selecione **Microsoft Intune**.

   ![Captura de tela do portal do Azure](./media/auto-enroll-intune.png)

4. Verifique se os usuários que estão implantando dispositivos ingressados no Azure Active Directory usando o Intune e o Windows são membros de um grupo incluído no seu **escopo do usuário MDM**.

   ![Captura de tela do portal do Azure](./media/auto-enroll-scope.png)

5. Use os valores padrão para as seguintes URLs:
    - **URL dos Termos de uso do MDM**
    - **URL de Descoberta do MDM**
    - **URL da Conformidade do MDM**
6. Selecione **Salvar**.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>Aumentar o limite de conta de computador na Unidade Organizacional

O conector do Intune para o Active Directory cria computadores do Autopilot registrados no domínio do Active Directory Local. O computador que hospeda o Conector do Intune deve ter os direitos de criar os objetos de computador dentro do domínio. 

Em alguns domínios, computadores não recebem os direitos para criar computadores. Além disso, os domínios têm um limite integrado (padrão de 10) que se aplica a todos os usuários e computadores que não têm direitos delegados para criar Objetos de Computador. Portanto, os direitos precisam ser delegados a computadores que hospedam o conector do Intune na unidade organizacional em que os dispositivos ingressados no Azure AD híbrido foram criados.

A unidade organizacional que recebeu o direito de criar computadores deve corresponder:
- à unidade organizacional inserida no perfil do Ingresso no Domínio
- ou, se nenhum perfil for selecionado, ao nome de domínio do computador para seu domínio.

1. Abra **Usuários e Computadores do Active Directory** (DSA.msc).

2. Clique com o botão direito do mouse na unidade organizacional que você usará para criar computadores ingressados no Azure AD híbrido > **Delegar Controle**.

    ![Captura de tela de delegar controle](media/windows-autopilot-hybrid/delegate-control.png)

3. No assistente **Delegação de Controle**, escolha **Avançar** > **Adicionar...** > **Tipos de Objeto**.

4. Na caixa de diálogo **Tipos de Objeto**, marque **Computadores** e, em seguida, escolha **OK**.

    ![Captura de tela de delegar controle](media/windows-autopilot-hybrid/object-types-computers.png)

5. Na caixa de diálogo **Selecionar Usuários, Computadores ou Grupos**, na caixa **Inserir nomes de objeto para selecionar**, insira o nome do computador em que o conector está instalado.

    ![Captura de tela de delegar controle](media/windows-autopilot-hybrid/enter-object-names.png)

6. Escolha **Verificar Nomes** para validar sua entrada, então escolha **OK** > **Avançar**.

7. Escolha **Criar uma tarefa personalizada para delegar** > **Avançar**.

8. Escolha **Somente os seguintes objetos na pasta** e, em seguida, marque as seguintes opções:
    - **Objetos do computador**
    - **Criar objetos selecionados nesta pasta**
    - **Excluir objetos selecionados nesta pasta**

    ![Captura de tela de delegar controle](media/windows-autopilot-hybrid/only-following-objects.png)
    
9. Escolha **Avançar**.

10. Em **Permissões**, marque **Controle Total** (isso marcará todas as outras opções) > **Avançar** > **Concluir**.

    ![Captura de tela de delegar controle](media/windows-autopilot-hybrid/full-control.png)

## <a name="install-the-intune-connector"></a>Instalar o Conector do Intune

O conector do Intune para o Active Directory precisa ser instalado em um computador que esteja executando o Windows Server 2016 com acesso à Internet e ao seu Active Directory. Para aumentar a disponibilidade e a escala ou para dar suporte a vários domínios do Active Directory, você pode instalar vários conectores em seu ambiente. É recomendável instalar o conector em um servidor que não esteja executando nenhum outro conector do Intune.

1. Certifique-se de ter um pacote de idiomas instalado e configurado como descrito em [Requisitos de idioma do Conector do Intune (versão prévia)](https://docs.microsoft.com/windows/deployment/windows-autopilot/intune-connector).
2. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **Conector do Intune para Active Directory (Versão Prévia)** > **Adicionar conector**. 
3. Siga as instruções para baixar o conector.
4. Abra o arquivo de configuração do conector baixado para instalar o conector (ODJConnectorBootstrapper.exe).
5. No final da configuração, escolha **Configurar**.
6. Escolha **Entrar**.
7. Insira as credenciais de função de Administrador do Intune ou Administrador Global do usuário.
8. Vá para **Registro de dispositivo** > **Registro do Windows** > **Conector do Intune para Active Directory (Versão Prévia)** e confirme se o status da conexão é **Ativo**.

### <a name="configure-web-proxy-settings"></a>Definir configurações de proxy Web

Se você tiver um proxy da Web em seu ambiente de rede, siga as instruções aqui para que o conector do Intune para Active Directory funcione corretamente: [Trabalhar com servidores proxy locais existentes](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers).


## <a name="create-a-device-group"></a>Criar um grupo de dispositivos
1. No [Intune](https://aka.ms/intuneportal), escolha **Grupos** > **Novo grupo**.
2. Na folha **Grupo**:
    1. Em **Tipo de grupo**, escolha **Segurança**.
    2. Digite o **Nome do grupo** e a **Descrição do grupo**.
    3. Escolha um **Tipo de associação**.
3. Se escolheu **Dispositivo Dinâmico** como **Tipo de associação** anteriormente, na folha **Grupo**, escolha **Membros de dispositivo dinâmico** e digite qualquer um dos códigos a seguir na caixa **Regra avançada**.
    - Se pretende criar um grupo que inclui todos os dispositivos do Autopilot, digite `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Se pretende criar um grupo que inclui todos os dispositivos do Autopilot com uma ID do pedido específica, digite: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - Se pretende criar um grupo que inclui todos os dispositivos do Autopilot com a ID da Ordem de Compra específica, digite: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Depois de adicionar o código de **Regra avançada**, escolha **Salvar**.
5. Escolha **Criar**.  

## <a name="register-your-autopilot-devices"></a>Registrar seus dispositivos do Autopilot

Escolha uma das maneiras a seguir para registrar seus dispositivos do Autopilot:

### <a name="register-autopilot-devices-that-are-already-enrolled"></a>Registrar dispositivos do Autopilot já registrados

1. Criar um perfil de implantação do Autopilot com **Converter todos os dispositivos de destino para o Autopilot** definido como **Sim**. 
2. Atribua o perfil a um grupo que contém os membros que você deseja registrar automaticamente com o Autopilot.

Para obter mais informações, confira [Criar um perfil de implantação do Autopilot](enrollment-autopilot.md#create-an-autopilot-deployment-profile).

### <a name="register-autopilot-devices-that-arent-enrolled"></a>Registrar dispositivos Autopilot não registrados

Se os dispositivos ainda não estiverem registrados, você poderá registrá-los por conta própria. Para obter mais informações, confira [Adicionar dispositivos](enrollment-autopilot.md#add-devices).

### <a name="register-devices-from-an-oem"></a>Registrar dispositivos de um OEM

Se você estiver comprando novos dispositivos, alguns OEMs poderão registrar dispositivos para você. Para obter mais informações, confira a [página do Windows Autopilot](http://aka.ms/WindowsAutopilot).

Quando dispositivos Autopilot são registrados (e antes de serem registrados no Intune), você pode vê-los em três locais (com nomes definidos para os números seriais):
- Folha Dispositivos do Autopilot no Intune no portal do Azure (**Registro de dispositivo** > **Registro do Windows** > **Dispositivos**).
- Folha de dispositivos do Azure AD no Intune no portal do Azure (**Dispositivos** > **Dispositivos do Azure AD**).
- Folha Todos os Dispositivos do AAD no Azure Active Directory no portal do Azure (**Dispositivos** > **Todos os Dispositivos**).

Depois que os dispositivos do Autopilot são registrados, você pode vê-los em quatro locais:
- Folha Dispositivos do Autopilot no Intune no portal do Azure (**Registro de dispositivo** > **Registro do Windows** > **Dispositivos**).
- Folha de dispositivos do Azure AD no Intune no portal do Azure (**Dispositivos** > **Dispositivos do Azure AD**).
- Folha Todos os Dispositivos do AAD no Azure Active Directory no portal do Azure (**Dispositivos** > **Todos os Dispositivos**).
- Folha Todos os Dispositivos no Intune no portal do Azure (**Dispositivos** > **Todos os Dispositivos**).

Depois que os dispositivos do Autopilot são registrados, seus nomes de dispositivo mudam para o nome do host do dispositivo. Por padrão, começa com "DESKTOP-".




## <a name="create-and-assign-an-autopilot-deployment-profile"></a>Criar e atribuir um perfil de implantação do Autopilot
Os perfis de implantação do Autopilot são usados para configurar os dispositivos do Autopilot.

1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **Perfis de Implantação** > **Criar Perfil**.
2. Forneça um **Nome** e uma **Descrição** opcional.
3. Em **Modo de implantação**, escolha **Orientado pelo Usuário**.
4. Na caixa **Ingressar no Azure AD como**, escolha **Ingressado no Azure AD híbrido (Versão Prévia)**.
5. Escolha **OOBE (configuração inicial pelo usuário)**, configure as opções conforme necessário e escolha **Salvar**.
6. Escolha **Criar** para criar o perfil. 
7. Na folha do perfil, escolha **Atribuições**.
8. Escolha **Selecionar grupos** > na folha **Selecionar grupos**, escolha o grupo de dispositivos > **Selecionar**.

Levará cerca de 15 minutos para que o status do perfil de dispositivo mude de **Não atribuídos** para **Atribuindo** e, por fim, para **Atribuído**.

## <a name="turn-on-the-enrollment-status-page-optional"></a>Ative a página de status de registro (opcional)

1. No [Intune](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **página de Status de Registro (Versão Prévia)**.
2. Na folha **Página de Status de Registro**, escolha **Padrão** > **Configurações**.
3. Para **Mostrar o progresso da instalação do aplicativo e do perfil**, escolha **Sim**.
4. Configure as outras opções conforme necessário.
5. Selecione **Salvar**.

## <a name="create-and-assign-a-domain-join-profile"></a>Criar e atribuir um perfil de Ingresso no Domínio

1. No [Intune](https://aka.ms/intuneportal), selecione **Configuração do dispositivo** > **Perfis** > **Criar Perfil**.
2. Digite as seguintes propriedades:
   - **Nome**: insira um nome descritivo para o novo perfil.
   - **Descrição**: Insira uma descrição para o perfil.
   - **Plataforma**: escolha **Windows 10 e posterior**.
   - **Tipo de perfil**: escolha **Ingresso no Domínio (Versão Prévia)**.
3. Escolha **Configurações** e informe um **Prefixo do nome do computador**, **Nome de domínio** e **Unidade organizacional** (opcional). 
4. Escolha **OK** > **Criar**. O perfil será criado e aparecerá na lista.
5. Para atribuir o perfil, siga as etapas descritas em [Atribuir um perfil de dispositivo](device-profile-assign.md#assign-a-device-profile). 

## <a name="next-steps"></a>Próximas etapas

Depois de configurar o Windows Autopilot, saiba como gerenciar esses dispositivos. Para saber mais, confira [O que é gerenciamento de dispositivos do Microsoft Intune?](device-management.md)
