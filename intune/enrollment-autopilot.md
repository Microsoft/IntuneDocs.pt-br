---
title: Registrar dispositivos usando o Windows Autopilot
titleSuffix: Microsoft Intune
description: Saiba como registrar dispositivos Windows 10 usando o Windows Autopilot.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: b3c374e4ce6baeab8cc6fde3f6c45c63c48e34dd
ms.sourcegitcommit: d99def6e4ceb44f3e7ca10fe7cdd7f222cf814c8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42903068"
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot"></a>Registrar dispositivos Windows usando o Windows Autopilot
O Windows Autopilot simplifica o provisionamento de dispositivos. Compilar e manter imagens de sistema operacional personalizadas é um processo que consome muito tempo. Além disso, geralmente se gasta muito tempo para aplicar essas imagens personalizadas de sistema operacional aos novos dispositivos para prepará-los para o uso antes de fornecê-los aos usuários finais. Com o Microsoft Intune e o AutoPilot, você pode dar novos dispositivos seus usuários finais sem precisar criar, manter e aplicar imagens personalizadas do sistema operacional para os dispositivos. Quando usa o Intune para gerenciar dispositivos do Autopilot, você pode gerenciar políticas, perfis, aplicativos e muito mais, depois de registrá-los. Para obter uma visão geral dos benefícios, cenários e pré-requisitos, consulte [Overview of Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot) (Visão geral do Windows AutoPilot).

## <a name="prerequisites"></a>Pré-requisitos
- [Registro automático no Windows habilitado](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Assinatura do Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)<!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="add-devices"></a>Adicionar Dispositivos

Você pode adicionar dispositivos Windows AutoPilot importando um arquivo CSV com as respectivas informações.

1. Vá até o [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **Dispositivos** > **Importar**.

    ![Captura de tela de dispositivos Windows AutoPilot](media/enrollment-autopilot/autopilot-import-device.png)

2. Em **Adicionar dispositivos do Windows Autopilot**, navegue até um arquivo CSV que inclui a listagem de dispositivos que você pretende adicionar. O arquivo deve incluir os números de série, as IDs de produtos do Windows, os hashes de hardware e as IDs de pedidos opcionais dos dispositivos.

    ![Captura de tela de adição de dispositivos Windows AutoPilot](media/enrollment-autopilot/autopilot-import-device2.png)

3. Escolha **Importar** para iniciar a importação de informações do dispositivo. A importação pode demorar vários minutos.

4. Após concluir a importação, escolha **Registro de dispositivo** > **Registro do Windows** > **Windows Autopilot** > **Dispositivos** > **Sincronizar**. É exibida uma mensagem informando que a sincronização está em andamento. O processo poderá levar alguns minutos para ser concluído, dependendo de quantos dispositivos estiverem sendo sincronizados.

5. Atualize a exibição para ver os novos dispositivos.

## <a name="create-an-autopilot-device-group"></a>Criar um grupo de dispositivos do Autopilot

1. Vá até o [Intune no portal do Azure](https://aka.ms/intuneportal) e escolha **Grupos**.
2. Na folha **Grupo**:
    1. Em **Tipo de grupo**, escolha **Segurança**.
    2. Digite o **Nome do grupo** e a **Descrição do grupo**.
    3. Em **Tipo de associação**, escolha **Atribuído** ou **Dispositivo Dinâmico**.
3. Se escolheu **Atribuído** como **Tipo de associação** na etapa anterior, na folha **Grupo**, escolha **Membros** e adicione dispositivos do Autopilot ao grupo.
    Os dispositivos do Autopilot ainda não registrados são dispositivos cujos nomes são iguais aos respectivos números de série.
4. Se escolheu **Dispositivo Dinâmico** como **Tipo de associação** anteriormente, na folha **Grupo**, escolha **Membros de dispositivo dinâmico** e digite qualquer um dos códigos a seguir na caixa **Regra avançada**.
    - Se pretende criar um grupo que inclui todos os dispositivos do Autopilot, digite `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Se pretende criar um grupo que inclui todos os dispositivos do Autopilot com uma ID do pedido específica, digite: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - Se pretende criar um grupo que inclui todos os dispositivos do Autopilot com uma Identificação da Ordem de Compra específica, digite: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Depois de adicionar o código de **Regra avançada**, escolha **Salvar**.
5. Escolha **Criar**.



## <a name="create-an-autopilot-deployment-profile"></a>Criar um perfil de implantação do AutoPilot
Os perfis de implantação do AutoPilot são usados para configurar os dispositivos do AutoPilot.
1. Vá até o [Intune no portal do Azure](https://aka.ms/intuneportal) e escolha **Registro de dispositivo** > **Registro do Windows** > **Perfis de Implantação** > **Criar Perfil**.
2. Forneça um **Nome** e uma **Descrição** opcional.
3. No caso do **Modo de implantação**, escolha entre duas opções:
    - **Controlado pelo usuário**: dispositivos com este perfil são associados ao usuário que faz o registro do dispositivo. As credenciais do usuário são necessárias para provisionar o dispositivo.
    - **Implantação automática (versão prévia)**: (Windows 10 Pro Insider Preview, build 17672 ou posterior) dispositivos com este perfil não são associados ao usuário que faz o registro do dispositivo. As credenciais do usuário não são necessárias para provisionar o dispositivo.
4. Na caixa **Ingressar no Azure AD como**, escolha **Ingressado no Azure AD**.
5. Escolha **OOBE (configuração inicial pelo usuário)**, configure as opções a seguir e escolha **Salvar**:
    - **Idioma (Região)**\*: escolha o idioma que pretende usar no dispositivo. Esta opção está disponível apenas quando você escolhe **Implantação automática** como **Modo de implantação**.
    - **Configurar o teclado automaticamente**\*: se houver um **Idioma (Região)** selecionado, avance para a página de seleção do teclado. Esta opção está disponível apenas quando você escolhe **Implantação automática** como **Modo de implantação**.
    - **EULA (Contrato de Licença de Usuário Final)**: (Windows 10, versão 1709 ou posterior) escolha se deseja mostrar ou não o EULA aos usuários.
    - **Configurações de privacidade**: escolha se deseja mostrar ou não as configurações de privacidade aos usuários.
    - **Tipo de conta de usuário**: escolha se o tipo de conta do usuário deve ser **Administrador** ou **Padrão**. 

6. Escolha **Criar** para criar o perfil. O perfil de implantação do AutoPilot agora está disponível para ser atribuído aos dispositivos.

*As opções **Idioma (Região)** e **Configurar o teclado automaticamente** estão disponíveis apenas quando você escolhe **Implantação automática (versão prévia)** como **Modo de implantação** (Windows 10 Pro Insider Preview, build 17672 ou posterior).


## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>Atribuir um perfil de implantação do Autopilot a um grupo de dispositivos

1. Vá até o [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **Perfis de implantação** e escolha um perfil.
2. Na folha do perfil específico, escolha **Atribuições**. 
3. Escolha **Selecionar grupos**, em seguida, na folha **Selecionar grupos**, escolha os grupos aos quais deseja atribuir um perfil e escolha **Selecionar**.

## <a name="edit-an-autopilot-deployment-profile"></a>Editar um perfil de implantação do AutoPilot
Depois de criar um perfil de implantação do AutoPilot, você poderá editar determinadas partes do perfil de implantação.   

1. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo**.
2. Em **Registro do Windows**, vá até a seção **Windows Autopilot** e escolha **Perfis de Implantação**.
3. Selecione o perfil que deseja editar.
4. Clique em **Propriedades** à esquerda para alterar o nome ou a descrição do perfil de implantação. Clique em **Salvar** depois de fazer as alterações.
5. Clique em **Configurações** para alterar as configurações de OOBE. Clique em **Salvar** depois de fazer as alterações.

> [!NOTE]
> As alterações feitas no perfil se aplicam aos dispositivos atribuídos a ele. No entanto, o perfil atualizado somente será aplicado a um dispositivo que já foi registrado no Intune depois que o dispositivo for redefinido e registrado novamente.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Alertas para dispositivos não atribuídos do Windows AutoPilot <!-- 163236 -->
Você pode exibir um alerta para ver quantos dispositivos do Autopilot não receberam atribuição de perfis de implantação desse programa. Use as informações no alerta para criar perfis e atribuí-los aos dispositivos não atribuídos. Quando você clica no alerta, vê uma lista completa de dispositivos Windows AutoPilot e informações detalhadas sobre eles.

Para receber alertas sobre dispositivos não atribuídos, vá até o [Intune no portal do Azure](https://aka.ms/intuneportal) e escolha **Registro de dispositivo** > **Visão geral** > **Dispositivos não atribuídos**.  

## <a name="delete-autopilot-devices"></a>Excluir dispositivos AutoPilot

É possível excluir os dispositivos não registrados do Windows Autopilot.

1. Se os dispositivos estiverem registrados no Intune, primeiro [exclua-os do portal do Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **Dispositivos**.

3. Em **Dispositivos do Windows AutoPilot**, escolha os dispositivos que você deseja excluir e, em seguida, escolha **Excluir**.

4. Confirmar a exclusão escolhendo **Sim**. A exclusão pode levar alguns minutos.

## <a name="using-autopilot-in-other-portals"></a>Usando o AutoPilot em outros portais
Caso não tenha interesse em gerenciamento de dispositivo móvel, você pode usar o Autopilot na Microsoft Store para Empresas. Embora haja a opção de usar outros portais, é recomendável usar somente o Intune para gerenciar suas implantações do AutoPilot. Se você usar o Intune e outro portal, o Intune não será capaz de:
- Exibir as alterações dos perfis criados no Intune, mas editados em outro portal
- Sincronizar os perfis criados em outro portal
- Exibir alterações em atribuições de perfil feitas em outro portal
- Sincronizar as atribuições de perfil feitas em outro portal
- Exibir as alterações na lista de dispositivos que foram feitas em outro portal

## <a name="next-steps"></a>Próximas etapas
Depois de configurar o Windows AutoPilot para dispositivos Windows 10 registrados, saiba como gerenciar esses dispositivos. Para saber mais, confira [O que é gerenciamento de dispositivos do Microsoft Intune?](https://docs.microsoft.com/intune/device-management)
