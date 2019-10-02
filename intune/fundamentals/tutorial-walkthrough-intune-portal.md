---
title: Tutorial – passo a passo do Intune no portal do Azure
titleSuffix: Microsoft Intune
description: Neste tutorial, você conhecerá o Microsoft Intune para entender melhor como realizar tarefas.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/24/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e892d8a3-7f74-498c-98d5-e968a8fbb049
Customer intent: As an Intune admin, I want to learn where to find the different features in Intune.
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b3caa2d8d8ac0a9b3ad1590d610618094c1fadcc
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726265"
---
# <a name="tutorial-walkthrough-of-microsoft-intune-in-the-azure-portal"></a>Tutorial: Instruções passo a passo do Microsoft Intune no portal do Azure

O [Azure](https://docs.microsoft.com/learn/modules/welcome-to-azure) contém mais de 100 serviços para ajudá-lo com uma variedade de possibilidades e cenários de computação em nuvem. O Microsoft Intune é um dos vários serviços disponíveis no Azure. O Intune ajuda você a garantir que dispositivos, aplicativos e dados da sua empresa atendam aos requisitos de segurança da sua empresa. Você tem o controle para definir quais requisitos precisam ser verificados e o que acontece quando esses requisitos não são cumpridos. O [Portal do Azure](https://portal.azure.com) é onde você pode encontrar o serviço Microsoft Intune. Conhecer os recursos disponíveis no Intune ajudará você a realizar diversas tarefas de MDM (gerenciamento de dispositivo móvel) e MAM (gerenciamento de aplicativo móvel).

Neste tutorial, você vai:
> [!div class="checklist"]
> * Fazer um tour do Microsoft Intune
> * Configurar o portal do Azure

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos
Antes de configurar o Microsoft Intune, examine os requisitos a seguir:

- [Navegadores e sistemas operacionais compatíveis](../supported-devices-browsers.md) 
- [Largura de banda e requisitos de configuração de rede](../network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Inscrever-se para uma avaliação gratuita do Microsoft Intune

Experimentar o Intune gratuitamente por 30 dias. Se você já tem uma conta corporativa ou de estudante, **entre** com essa conta e adicione o Intune à sua assinatura. Caso contrário, você pode [inscrever-se para uma conta de avaliação gratuita](free-trial-sign-up.md) para usar o Intune para sua organização.

> [!IMPORTANT]
> Você não pode combinar uma conta corporativa ou de estudante depois de se inscrever para uma nova conta.

## <a name="tour-microsoft-intune"></a>Tour do Microsoft Intune

Siga as etapas abaixo para entender melhor o Intune no portal do Azure. Depois de concluir o tour, você terá uma compreensão melhor sobre algumas das principais áreas do Intune.

1. Abra um navegador e entre no [portal do Intune](https://aka.ms/intuneportal). Se você estiver familiarizado com o Intune, use sua assinatura de avaliação gratuita.

    ![Captura de tela do portal do Microsoft Intune](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-01.png)

    Sempre que você abrir o Intune ou qualquer outro serviço no Azure, o serviço será exibido em um painel. Algumas das primeiras cargas de trabalho você pode usar no Intune incluem **Dispositivos**, **Aplicativos cliente**, **Usuários** e **Grupos**. Uma carga de trabalho é simplesmente uma subárea de um serviço. Quando você selecionar a carga de trabalho, ela abrirá esse painel em uma página inteira. Outros painéis deslizarão do lado direito do painel ao serem abertos e fecharão para revelar o painel anterior. Um painel também é chamado de folha. 

    Por padrão, quando abrir o Intune, você verá o painel **Visão geral**. Este painel fornece um instantâneo visual geral do status de atribuição e de conformidade do dispositivo, bem como do status de instalação do aplicativo.

2. No [Intune](https://aka.ms/intuneportal), selecione **Registro do dispositivo** para exibir detalhes sobre os dispositivos registrados no seu locatário do Intune. Se estiver começando com um novo locatário do Intune, você ainda não terá nenhum dispositivo registrado. 

    ![Captura de tela do painel de registro do dispositivo](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-02.png)
    
    O Intune permite gerenciar os dispositivos e os aplicativos da sua força de trabalho, incluindo o modo como ela acessa os dados da empresa. Para usar esse MDM (gerenciamento de dispositivo móvel), os dispositivos devem primeiro ser registrados no serviço do Intune. Quando um dispositivo é registrado, ele recebe um certificado de MDM. Esse certificado é usado para se comunicar com o serviço do Intune. 

    Há vários métodos de registrar os dispositivos da sua força de trabalho no Intune. Cada método depende da propriedade do dispositivo (pessoal ou corporativo), tipo de dispositivo (iOS, Windows, Android) e requisitos de gerenciamento (redefinições, afinidade, bloqueio). No entanto, antes de habilitar o registro de dispositivo, você precisa configurar sua infraestrutura do Intune. Em especial, o registro de dispositivo exige que você [defina a autoridade MDM](mdm-authority-set.md). Para obter mais informações sobre como preparar seu ambiente do Intune (locatário), veja [Configurar o Intune](setup-steps.md). Depois que seu locatário do Intune estiver pronto, você poderá registrar dispositivos. Para obter mais informações sobre o registro de dispositivo, confira [O que é o registro de dispositivo?](../enrollment/device-enrollment.md)

3. De [Intune](https://aka.ms/intuneportal), selecione **Conformidade do dispositivo** para exibir detalhes sobre a conformidade para dispositivos gerenciados pelo Intune. Você verá detalhes semelhantes aos da imagem a seguir.

    ![Captura de tela do painel de conformidade do dispositivo](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-03.png)
    
    Os requisitos de conformidade são essencialmente regras, como exigir um PIN do dispositivo ou exigir criptografia do dispositivo. Políticas de conformidade do dispositivo definem essas regras e configurações que um dispositivo deve seguir para ser considerado em conformidade. Para usar a conformidade do dispositivo, você precisa ter:
    - Uma assinatura do Intune e outra do Azure AD (Azure Active Directory) Premium
    - Dispositivos executando uma plataforma compatível
    - Os dispositivos precisam estar registrados no Intune
    - Dispositivos que estejam registrados para um usuário ou que não estejam registrados para nenhum usuário primário.
    
    Para mais informações, veja [Introdução às políticas de conformidade do dispositivo no Intune](../protect/device-compliance-get-started.md).

4. De [Intune](https://aka.ms/intuneportal), selecione **Configuração do dispositivo** para exibir detalhes sobre perfis de dispositivo no Intune.

    ![Captura de tela do painel de configuração do dispositivo](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-04.png)
    
    O Intune inclui configurações e recursos que você pode habilitar ou desabilitar em diferentes dispositivos na sua organização. Essas configurações e recursos são adicionados a "perfis de configuração". Você pode criar perfis para diferentes dispositivos e plataformas, incluindo iOS, Android e Windows. Em seguida, você pode usar o Intune para aplicar o perfil aos dispositivos em sua organização.   

    Para obter mais informações sobre a configuração de dispositivo, veja [Aplicar configurações de recursos aos seus dispositivos usando perfis de dispositivo no Microsoft Intune](../configuration/device-profiles.md).

5. No [Intune](https://aka.ms/intuneportal), selecione **Dispositivos** para exibir detalhes sobre os dispositivos registrados no seu locatário do Intune. Se estiver começando com uma nova inscrição no Intune, você ainda não terá nenhum dispositivo registrado.

    ![Captura de tela do painel de registro do dispositivo](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-05.png)

    O painel **Dispositivos** fornece detalhes sobre os dispositivos registrados do seu locatário. Você pode clicar em **Todos os dispositivos** para exibir uma lista de dispositivos para seu locatário do Intune.

6. Em [Intune](https://aka.ms/intuneportal), selecione **Aplicativos cliente** para exibir o status de instalação do aplicativo.

    ![Captura de tela do painel de aplicativos cliente](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-06.png)

    Como administrador de TI, você pode usar o Microsoft Intune para gerenciar os aplicativos cliente que os colaboradores da sua empresa usam. Essa funcionalidade está além do gerenciamento de dispositivos e proteção de dados. Uma das prioridades do administrador é garantir que os usuários finais tenham acesso aos aplicativos necessários para realizar seu trabalho. Além disso, pode ser útil atribuir e gerenciar aplicativos em dispositivos que não estão registrados com o Intune. O Intune oferece uma variedade de recursos para ajudar a obter os aplicativos que você precisa, nos dispositivos que você deseja. Para obter mais informações sobre como adicionar e atribuir aplicativos, confira [Adicionar aplicativos ao Microsoft Intune](../apps/apps-add.md) e [Atribuir aplicativos a grupos com o Microsoft Intune](../apps/apps-deploy.md).

7. Em [Intune](https://aka.ms/intuneportal), selecione **Acesso Condicional** para exibir detalhes sobre as políticas de acesso.

    ![Captura de tela do painel de Acesso Condicional](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-07.png)

    Acesso Condicional significa às formas de controlar os dispositivos e aplicativos que têm permissão para se conectar ao email e aos recursos da empresa. Para saber mais sobre Acesso Condicional baseado em dispositivo e em aplicativo e ver cenários comuns para uso do acesso condicional com o Intune, confira [O que é acesso condicional?](../protect/conditional-access.md)

8. Do [Intune](https://aka.ms/intuneportal), selecione **Usuários** para exibir detalhes sobre os usuários que você incluiu no Intune. Esses usuários são a força de trabalho de sua empresa.

    ![Captura de tela do painel Usuários](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-08.png)

    Você pode adicionar usuários diretamente ao Intune ou sincronizar os usuários do seu Active Directory local. Depois de adicionados, os usuários podem registrar dispositivos e acessar os recursos da empresa. Você também pode conceder permissões adicionais aos usuários para que acessem o Intune. Para obter mais informações, confira [Adicionar usuários e conceder permissão administrativa ao Intune](users-add.md).

9. Em [Intune](https://aka.ms/intuneportal), selecione **Grupos** para exibir detalhes sobre os grupos do Azure AD (Azure Active Directory) incluídos no Intune. Como um administrador do Intune, use os grupos para gerenciar usuários e dispositivos.

    ![Captura de tela do painel Grupos](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-09.png)

    Você pode configurar grupos para atender às suas necessidades organizacionais. Crie grupos para organizar usuários ou dispositivos por localização geográfica, departamento ou características de hardware. Use grupos para gerenciar tarefas em grande escala. Por exemplo, você pode definir políticas para vários usuários ou implantar aplicativos em um conjunto de dispositivos. Para obter mais informações sobre grupos, confira [Adicionar grupos para organizar usuários e dispositivos](../groups-add.md).

10. Em [Intune](https://aka.ms/intuneportal), selecione **Ajuda e suporte** para solicitar ajuda. Como administrador de TI, você poderá usar a opção **Ajuda e Suporte** para pesquisar e exibir soluções, bem como abrir um tíquete de suporte online para o Intune. 

    ![Captura de tela do painel de Ajuda e suporte](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-10.png)

    Para criar um tíquete de suporte, é preciso atribuir uma função de administrador à sua conta no Azure Active Directory. As funções de administrador incluem **Administrador do Intune**, **Administrador global** e **Administrador de serviços**. Para obter mais informações, confira [Como obter suporte para o Microsoft Intune](../get-support.md).

11. No [Intune](https://aka.ms/intuneportal), selecione **Status do locatário** para exibir detalhes sobre o seu locatário do Intune.

    ![Captura de tela do painel de Status do Locatário](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-11.png)

    Detalhes do status de locatário incluem o status do conector, a integridade do serviço do Intune e novidades do Intune. Se há problemas com seu locatário ou o Intune em si, você pode encontrar detalhes no painel **Status do Locatário**. Para obter mais informações, veja [Status do Locatário do Intune](../tenant-status.md).

12. Em [Intune](https://aka.ms/intuneportal), selecione **Solucionar problemas** para alcançar um atalho para dicas de solução de problemas, solicitar suporte ou verificar o status do Intune. Essas informações são específicas do usuário do Intune que você seleciona.

    ![Captura de tela do painel de Solução de problemas](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-12.png)

Para obter mais informações sobre a solução de problemas no Intune, confira [Usar o portal de solução de problemas para ajudar os usuários na empresa](../help-desk-operators.md).

## <a name="configure-the-azure-portal"></a>Configurar o portal do Azure

O Azure permite que você personalize e configure a exibição do portal.

### <a name="change-the-sidebar"></a>Alterar a barra lateral

A **barra lateral** no lado esquerdo do portal do Azure mostra uma lista de todos os serviços do Azure disponíveis. A exibição padrão dessa lista abrangente pode ser modificada permitindo manter uma exibição persistente dos serviços que são mais importantes para você. As informações abaixo usam o Intune como exemplo de um serviço a ser adicionado no topo da lista.

![Um usuário pesquisando Microsoft Intune na lista "Mais serviços".](./media/tutorial-walkthrough-intune-portal/azure-add-intune1.png)

1. Selecione **Todos os serviços** da barra lateral no lado esquerdo da página.
2. Pesquise **Intune** na caixa de filtro.
3. Selecione a **estrela** para adicionar o Intune no final da lista de serviços favoritos.
4. Passe o mouse sobre o serviço Intune. Selecione e arraste o Intune usando os **três pontos verticais** à direita do nome do serviço.

### <a name="change-the-dashboard"></a>Alterar o painel

Sua página de aterrissagem é o **painel**. É nessa página que você pode personalizar seus blocos para mostrar as informações mais relevantes.

![Uma imagem do novo painel genérico. Ele mostra a barra lateral com todos os serviços à esquerda e o painel principal no centro. Os botões de modificação do painel estão na parte superior, com blocos que oferecem acesso a todos os recursos, a tutoriais de início rápido, a integridade de serviço e ao Azure Marketplace.](./media/tutorial-walkthrough-intune-portal/azure-default-dashboard.png)

Para modificar o painel atual, selecione o botão **Editar painel**. Caso não deseje alterar o painel padrão, você também poderá criar um **Novo painel**. A opção de criar um novo painel oferece um painel privado vazio com a **Galeria de Blocos**, permitindo que você adicione ou reorganize os blocos. Você pode encontrar os blocos pela categoria **Geral**, por **Tipo** por **Pesquisa** e por um **Grupo de recursos** ou uma **Marca**.

Você também pode adicionar blocos diretamente ao painel por meio de qualquer botão **reticências** e selecionando **Fixar no painel**.

![Uma imagem aproximada do local Usuários e Grupos > Todos no Intune, tem a opção "Fixar no painel" visível na extrema direita de um grupo.](./media/tutorial-walkthrough-intune-portal/azure-pin-to-dashboard.png)

Essa funcionalidade será mais relevante depois que você adicionar mais conteúdo, como grupos e usuários, no Intune.

## <a name="next-steps"></a>Próximas etapas

Para começar rapidamente a usar o Microsoft Intune, siga os Inícios Rápidos do Intune, configurando primeiro uma conta gratuita do Intune.

> [!div class="nextstepaction"]
> [Início rápido: Experimente o Microsoft Intune gratuitamente](free-trial-sign-up.md)
