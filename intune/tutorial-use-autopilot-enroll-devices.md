---
title: 'Tutorial: usar o Autopilot para registrar dispositivos no Intune'
titleSuffix: Microsoft Intune
description: Neste tutorial, você configurará o Windows Autopilot para registrar dispositivos no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/19/2018
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up Windows Autopilot so that users can enroll in Intune.
ms.openlocfilehash: a90f53bfc5841cc0f773751e7df917d8fc8b6cf8
ms.sourcegitcommit: cff65435df070940da390609d6376af6ccdf0140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2018
ms.locfileid: "49431905"
---
# <a name="tutorial-use-autopilot-to-enroll-windows-devices-in-intune"></a>Tutorial: usar o Autopilot para registrar dispositivos no Intune
O Windows Autopilot simplifica a inscrição de dispositivos. Com o Microsoft Intune e o Autopilot, você pode fornecer novos dispositivos aos usuários finais sem a necessidade de criar, manter e aplicar imagens personalizadas do sistema operacional. 

Neste tutorial, você aprenderá a:
> [!div class="checklist"]
> * Adicionar dispositivos ao Intune
> * Criar um grupo de dispositivos do Autopilot
> * Criar um perfil de implantação do Autopilot
> * Atribuir um perfil de implantação do Autopilot a um grupo de dispositivos
> * Distribuir dispositivos Windows a usuários

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

Para obter uma visão geral dos benefícios do Autopilot, conhecer os cenários e os pré-requisitos, confira [Visão geral do Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).


## <a name="prerequisites"></a>Pré-requisitos
- [Configurar o registro automático do Windows](quickstart-setup-auto-enrollment.md)
- [Assinatura do Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)<!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->


## <a name="add-devices"></a>Adicionar Dispositivos

A primeira etapa na configuração do Windows Autopilot é adicionar os dispositivos do Windows ao Intune. Tudo o que você precisa fazer é criar um arquivo CSV e importá-lo para o Intune.

1. Em qualquer editor de texto, crie uma lista de valores separados por vírgulas (CSV) que identifique os dispositivos do Windows. Use o seguinte formato:
    
    *número de série*, *id do produto windows*, *hash de hardware*, *ID de pedido opcional*
    
    Os três primeiros itens são necessários, mas a ID de pedido é opcional.

2. Salve o arquivo CSV.

3. Vá até o [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **Dispositivos** > **Importar**.

    ![Captura de tela de dispositivos Windows Autopilot](media/enrollment-autopilot/autopilot-import-device.png)

4. Em **Adicionar dispositivos do Windows Autopilot**, navegue até o arquivo CSV que você salvou.

    ![Captura de tela de adição de dispositivos Windows Autopilot](media/enrollment-autopilot/autopilot-import-device2.png)

5. Escolha **Importar** para iniciar a importação de informações do dispositivo. A importação pode demorar vários minutos.

4. Após concluir a importação, escolha **Registro de dispositivo** > **Registro do Windows** > **Windows Autopilot** > **Dispositivos** > **Sincronizar**. É exibida uma mensagem informando que a sincronização está em andamento. O processo poderá levar alguns minutos para ser concluído, dependendo de quantos dispositivos você estiver sincronizando.

5. Atualize a exibição para ver os novos dispositivos.

## <a name="create-an-autopilot-device-group"></a>Criar um grupo de dispositivos do Autopilot

Em seguida, crie um grupo de dispositivos e coloque nele os dispositivos Autopilot que você acabou de carregar.

1. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Grupos** > **Novo grupo**.
2. Na folha **Grupo**:
    1. Em **Tipo de grupo**, escolha **Segurança**.
    2. Em **Nome do grupo**, insira *Grupo Autopilot*. Em **Descrição do grupo**, insira *Grupo de teste para dispositivos do Autopilot*.
    3. Em **Tipo de associação**, escolha **Atribuído**.
3. Na folha **Grupo**, escolha **Membros** e adicione os dispositivos do Autopilot ao grupo. Os dispositivos do Autopilot ainda não registrados são dispositivos cujos nomes são iguais aos respectivos números de série.
4. Escolha **Criar**.  

## <a name="create-an-autopilot-deployment-profile"></a>Criar um perfil de implantação do Autopilot

Depois de criar um grupo de dispositivos, você deve criar um perfil de implantação para poder configurar os dispositivos do Autopilot.

1. Vá até o [Intune no portal do Azure](https://aka.ms/intuneportal) e escolha **Registro de dispositivo** > **Registro do Windows** > **Perfis de Implantação** > **Criar Perfil**.
2. Em **Nome**, insira *Perfil do Autopilot*. Em **Descrição**, insira *Perfil de teste para dispositivos do Autopilot*.
3. Defina **Converter todos os dispositivos de destino para Autopilot** como **Sim**. Essa configuração garante que todos os dispositivos na lista sejam registrados no serviço de implantação do Autopilot. Aguarde 48 horas para que o registro seja processado.
4. Em **Modo de implantação**, escolha **Orientado pelo Usuário**. Dispositivos com este perfil são associados ao usuário que faz o registro do dispositivo. As credenciais do usuário são necessárias para registrar o dispositivo.
5. Na caixa **Ingressar no Azure AD como**, escolha **Ingressado no Azure AD**.
6. Escolha **Experiência de configuração inicial do usuário (OOBE)**, defina as opções a seguir e deixe as outras configuradas como padrão, e escolha **Salvar**:
    - **Contrato de Licença de Usuário Final (EULA)**: **Ocultar**
    - **Configurações de privacidade**: **Exibir**
    - **Tipo de conta de usuário**: **Padrão**

6. Escolha **Criar** para criar o perfil. O perfil de implantação do Autopilot agora está disponível para ser atribuído aos dispositivos.

## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>Atribuir um perfil de implantação do Autopilot a um grupo de dispositivos

Agora que o perfil de implantação foi criado, você o atribuirá ao grupo de dispositivos.
1. Vá até o [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **Perfis de implantação** e escolha um perfil.
2. Na folha do perfil específico, escolha **Atribuições**. 
3. Escolha **Selecionar grupos**, depois, na folha **Selecionar grupos** , escolha **Grupo do Autopilot** e, em seguida, escolha **Selecionar**.

## <a name="distribute-devices-to-users"></a>Distribuir dispositivos para usuários

Agora você pode distribuir os dispositivos Windows para seus usuários. Quando entrarem pela primeira vez, o sistema Autopilot registrará e configurará automaticamente os dispositivos. 

## <a name="clean-up-resources"></a>Limpar os recursos

Se você não quiser mais usar os dispositivos do Autopilot, poderá excluí-los.

1. Se os dispositivos estiverem registrados no Intune, primeiro [exclua-os do portal do Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Registro de dispositivo** > **Registro do Windows** > **Dispositivos**.

3. Em **Dispositivos Windows Autopilot**, escolha os dispositivos que deseja excluir e, em seguida, escolha **Excluir**.

4. Confirmar a exclusão escolhendo **Sim**. A exclusão pode levar alguns minutos.

## <a name="next-steps"></a>Próximas etapas

Você pode encontrar mais informações sobre outras opções disponíveis para o Windows Autopilot.

> [!div class="nextstepaction"]
> [Artigo detalhado sobre o registro no Autopilot](enrollment-autopilot.md)

