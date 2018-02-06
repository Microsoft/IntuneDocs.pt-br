---
title: Registrar dispositivos Windows usando o programa Windows AutoPilot Deployment
description: Saiba como registrar novos dispositivos Windows 10 usando o programa Windows AutoPilot Deployment.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: 56d585c52d3704e64c658cedb48cad7270ceeccf
ms.sourcegitcommit: 2c7794848777e73d6a9502b4e1000f0b07ac96bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2018
---
# <a name="enroll-windows-devices-using-windows-autopilot-deployment-program"></a>Registrar dispositivos Windows usando o programa Windows AutoPilot Deployment
O programa Windows AutoPilot Deployment simplifica o provisionamento de dispositivos. Compilar e manter imagens de sistema operacional personalizadas é um processo que consome muito tempo. Além disso, geralmente se gasta muito tempo para aplicar essas imagens personalizadas de sistema operacional aos novos dispositivos para prepará-los para o uso antes de fornecê-los aos usuários finais. Com o Microsoft Intune e o AutoPilot, você pode dar novos dispositivos seus usuários finais sem precisar criar, manter e aplicar imagens personalizadas do sistema operacional para os dispositivos. Ao usar o Intune para gerenciar dispositivos do AutoPilot, você pode gerenciar políticas, perfis, aplicativos e etc., nos dispositivos depois que eles são registrados. Para obter uma visão geral dos benefícios, cenários e pré-requisitos, consulte [Overview of Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot) (Visão geral do Windows AutoPilot).

## <a name="prerequisites"></a>Pré-requisitos
- [Os dispositivos devem ser registrados na sua organização](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot#device-registration-and-oobe-customization)
- [Registro automático no Windows habilitado](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Assinatura do Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)<!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="synchronize-devices"></a>Sincronizar dispositivos
Sincronize seus dispositivos registrados no Intune para que você possa configurá-los.

1. Entre no [Azure](https://portal.azure.com/).
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Em **Intune**, escolha **Registro de dispositivo**.
4. Em **Registro no Windows**, na seção **Programa Windows AutoPilot Deployment**, escolha **Dispositivos**.
5. Clique em **Sincronizar** para importar seus dispositivos registrados. É exibida uma mensagem informando que a sincronização está em andamento.
6. Atualize a exibição para ver os novos dispositivos. O processo poderá levar alguns minutos para ser concluído, dependendo de quantos dispositivos estiverem sendo sincronizados.  

## <a name="create-an-autopilot-deployment-profile"></a>Criar um perfil de implantação do AutoPilot
Os perfis de implantação do AutoPilot são usados para configurar os dispositivos do AutoPilot.
1. Entre no [Azure](https://portal.azure.com/). 
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Em **Intune**, escolha **Registro de dispositivo**.
4. Em **Registro no Windows**, na seção **Programa Windows AutoPilot Deployment**, escolha **Perfis de Implantação**.
5. Clique em **Criar Perfil** e escolha um nome e uma descrição opcional. 
6. Para **Tipo de ingresso**, selecione **Ingressado no Azure AD**.
7. Para **OOBE (configuração inicial pelo usuário)**, configure as seguintes opções e, em seguida, clique em **OK**: 
   - **Configurações de privacidade**: escolha se deseja mostrar as configurações de privacidade aos usuários. 
   - **Termos de licença**: escolha se deseja mostrar os termos de licença para os usuários.
   - **Tipo de conta do usuário**: escolha se o tipo de conta do usuário é de usuário **Administrador** ou **Padrão**.

     > [!Note]    
     > Esta configuração não se aplica às contas Administrador Global ou Administrador de Empresa. Não é possível atribuir essas contas a usuários padrão, pois elas têm acesso a todos os recursos administrativos do Microsoft Azure AD.
8. Clique em **Criar** para criar o perfil. O perfil de implantação do AutoPilot agora está disponível para ser atribuído aos dispositivos.
     
> [!Note]    
> As configurações a seguir são configuradas com todos os perfis de implantação do AutoPilot:
> - Ignorar as páginas de configuração de registro da Cortana, do OneDrive e de OEM
> - Configurar automaticamente para corporativo ou de estudante
> - Experiência de entrada com a marca da empresa ou da escola    

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Alertas para dispositivos não atribuídos do Windows AutoPilot <!-- 163236 -->
É possível exibir um alerta para dispositivos Windows AutoPilot não atribuídos para ver quantos dispositivos do programa AutoPilot não têm perfis de implantação AutoPilot atribuídos. Use as informações no alerta para criar perfis e atribuí-los aos dispositivos não atribuídos. Quando você clica no alerta, vê uma lista completa de dispositivos Windows AutoPilot e informações detalhadas sobre eles. 
1. Entre no [Azure](https://portal.azure.com/). 
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Em **Intune**, escolha **Registro de dispositivo**.
4. Para ver o alerta, escolha **Visão geral**. Clique no alerta para ver uma lista de dispositivos AutoPilot.  

## <a name="assign-an-autopilot-deployment-profile"></a>Atribuir um perfil de implantação do AutoPilot
Depois de criar perfis de implantação do AutoPilot, você poderá atribuí-los para dispositivos selecionados.

1. Entre no [Azure](https://portal.azure.com/). 
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Em **Intune**, escolha **Registro de dispositivo**.
4. Na folha **Registro no Windows**, na seção **Programa Windows AutoPilot Deployment**, escolha **Dispositivos**.
5. Selecione os dispositivos aos quais deseja atribuir o perfil de implantação. Você pode filtrar pela coluna **Status** para localizar facilmente os dispositivos que não têm um perfil atribuído. 
6. Clique em **Atribuir perfil**, selecione o perfil de implantação do AutoPilot e, em seguida, clique em **Atribuir**. É exibida uma mensagem informando que a atribuição está em andamento.
7. Atualize a exibição para ver o que o perfil foi atribuído aos dispositivos. O processo poderá levar alguns minutos para ser concluído, dependendo de quantos dispositivos tiverem sido selecionados. 

> [!Note]
> O novo perfil é atribuído ao dispositivo. Para dispositivos que já foram registrados no Intune, o perfil é aplicado depois que eles forem redefinidos e registrados novamente.

### <a name="assign-a-different-autopilot-deployment-profile"></a>Atribuir um perfil de implantação do AutoPilot diferente
Depois que você atribuir um perfil de implantação do AutoPilot a um dispositivo, se você decidir atribuir um perfil diferente, atribua o novo perfil ao dispositivo.  

## <a name="edit-an-autopilot-deployment-profile"></a>Editar um perfil de implantação do AutoPilot 
Depois de criar um perfil de implantação do AutoPilot, você poderá editar determinadas partes do perfil de implantação.   
1. Entre no [Azure](https://portal.azure.com/). 
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Em **Intune**, escolha **Registro de dispositivo**.
4. Em **Registro no Windows**, na seção **Programa Windows AutoPilot Deployment**, escolha **Perfis de Implantação**. 
5. Selecione o perfil que deseja editar. 
6. Clique em **Propriedades** à esquerda para alterar o nome ou a descrição do perfil de implantação. Clique em **Salvar** depois de fazer as alterações. 
7. Clique em **Configurações** para alterar as configurações de OOBE. Clique em **Salvar** depois de fazer as alterações. 

> [!NOTE]
> O perfil atualizado será atribuído aos dispositivos. No entanto, o perfil atualizado somente será aplicado a um dispositivo que já foi registrado no Intune depois que o dispositivo for redefinido e registrado novamente. 

## <a name="using-autopilot-in-other-portals"></a>Usando o AutoPilot em outros portais
Se você não tiver iteresse no gerenciamento de dispositivo móvel, poderá usar o AutoPilot na Microsoft Store para Empresas, por exemplo. Embora haja a opção de usar outros portais, é recomendável usar somente o Intune para gerenciar suas implantações do AutoPilot. Se você usar o Intune e outro portal, o Intune não será capaz de:
- Exibir as alterações dos perfis criados no Intune, mas editados em outro portal
- Sincronizar os perfis criados em outro portal
- Exibir alterações em atribuições de perfil feitas em outro portal
- Sincronizar as atribuições de perfil feitas em outro portal
- Exibir as alterações na lista de dispositivos que foram feitas em outro portal

## <a name="next-steps"></a>Próximas etapas
Depois de configurar o Windows AutoPilot para dispositivos Windows 10 registrados, saiba como gerenciar esses dispositivos. Para saber mais, confira [O que é gerenciamento de dispositivos do Microsoft Intune?](https://docs.microsoft.com/intune/device-management)