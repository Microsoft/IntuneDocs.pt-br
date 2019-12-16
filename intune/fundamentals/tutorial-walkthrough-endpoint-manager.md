---
title: Tutorial – Passo a passo do Intune no Gerenciador de Ponto de Extremidade da Microsoft
titleSuffix: Microsoft Intune
description: Neste tutorial, você fará um tour pelo Microsoft Intune no Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft para entender melhor como realizar tarefas.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to learn where to find the different features in Intune from the Microsoft Endpoint Manager admin center.
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 267f09c3dc16aab10fbe64f0e8662ee6f7c7ffa0
ms.sourcegitcommit: ec69e7ccc6e6183862a48c1b03ca6a3bf573f354
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2019
ms.locfileid: "74907986"
---
# <a name="tutorial-walkthrough-intune-in-microsoft-endpoint-manager"></a>Tutorial: Passo a passo do Intune no Gerenciador de Ponto de Extremidade da Microsoft

O [Azure](https://docs.microsoft.com/learn/modules/welcome-to-azure) contém mais de 100 serviços para ajudá-lo com uma variedade de possibilidades e cenários de computação em nuvem. O Microsoft Intune é um dos vários serviços disponíveis no Azure. O Intune ajuda você a garantir que dispositivos, aplicativos e dados da sua empresa atendam aos requisitos de segurança da sua empresa. Você tem o controle para definir quais requisitos precisam ser verificados e o que acontece quando esses requisitos não são cumpridos. O [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) é o local em que você pode encontrar o serviço Microsoft Intune, bem como outras configurações relacionadas ao gerenciamento de dispositivo. Conhecer os recursos disponíveis no Intune ajudará você a realizar diversas tarefas de MDM (gerenciamento de dispositivo móvel) e MAM (gerenciamento de aplicativo móvel).

> [!NOTE]
> O Gerenciador de Ponto de Extremidade da Microsoft é uma plataforma única e integrada de gerenciamento de pontos de extremidade para gerenciar todos os seus pontos de extremidade. Esse centro de administração do Gerenciador de Ponto de Extremidade da Microsoft integra o ConfigMgr e o Microsoft Intune.

Neste tutorial, você vai:
> [!div class="checklist"]
> * Fazer um tour pelo Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft
> * Personalizar sua exibição do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="prerequisites"></a>Pré-requisitos
Antes de configurar o Microsoft Intune, examine os requisitos a seguir:

- [Navegadores e sistemas operacionais compatíveis](../supported-devices-browsers.md) 
- [Largura de banda e requisitos de configuração de rede](../network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Inscrever-se para uma avaliação gratuita do Microsoft Intune

Experimentar o Intune gratuitamente por 30 dias. Se você já tem uma conta corporativa ou de estudante, **entre** com essa conta e adicione o Intune à sua assinatura. Caso contrário, você pode [inscrever-se para uma conta de avaliação gratuita](free-trial-sign-up.md) para usar o Intune para sua organização.

> [!IMPORTANT]
> Você não pode combinar uma conta corporativa ou de estudante depois de se inscrever para uma nova conta.

## <a name="tour-microsoft-intune-in-the-microsoft-endpoint-manager-admin-center"></a>Fazer um tour pelo Microsoft Intune no Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft

Siga as etapas abaixo para entender melhor o Intune no Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft. Depois de concluir o tour, você terá uma compreensão melhor sobre algumas das principais áreas do Intune.

1. Abra um navegador e entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431). Se você estiver familiarizado com o Intune, use sua assinatura de avaliação gratuita.

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Home page](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-01.png)

    Quando você abre o Gerenciador de Ponto de Extremidade da Microsoft ou qualquer outro serviço no Azure, o serviço é exibido em um painel. Algumas das primeiras cargas de trabalho que você pode usar no Intune incluem **Dispositivos**, **Aplicativos**, **Usuários** e **Grupos**. Uma carga de trabalho é simplesmente uma subárea de um serviço. Quando você selecionar a carga de trabalho, ela abrirá esse painel em uma página inteira. Outros painéis deslizarão do lado direito do painel ao serem abertos e fecharão para revelar o painel anterior. 

    Por padrão, ao abrir o Gerenciador de Ponto de Extremidade da Microsoft, você verá o painel **Home page**. Esse painel fornece um instantâneo visual geral do status do locatário e do status de conformidade, bem como outros links úteis relacionados.

2. No painel de navegação, selecione **Painel** para exibir detalhes gerais sobre os dispositivos e os aplicativos cliente em seu locatário do Intune. Se estiver começando com um novo locatário do Intune, você ainda não terá nenhum dispositivo registrado. 

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Painel](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-02.png)
    
    O Intune permite gerenciar os dispositivos e os aplicativos da sua força de trabalho, incluindo o modo como ela acessa os dados da empresa. Para usar esse MDM (gerenciamento de dispositivo móvel), os dispositivos devem primeiro ser registrados no serviço do Intune. Quando um dispositivo é registrado, ele recebe um certificado de MDM. Esse certificado é usado para se comunicar com o serviço do Intune. 

    Há vários métodos de registrar os dispositivos da sua força de trabalho no Intune. Cada método depende da propriedade do dispositivo (pessoal ou corporativo), tipo de dispositivo (iOS, Windows, Android) e requisitos de gerenciamento (redefinições, afinidade, bloqueio). No entanto, antes de habilitar o registro de dispositivo, você precisa configurar sua infraestrutura do Intune. Em especial, o registro de dispositivo exige que você [defina a autoridade MDM](mdm-authority-set.md). Para obter mais informações sobre como preparar seu ambiente do Intune (locatário), veja [Configurar o Intune](setup-steps.md). Depois que seu locatário do Intune estiver pronto, você poderá registrar dispositivos. Para obter mais informações sobre o registro de dispositivo, confira [O que é o registro de dispositivo?](../enrollment/device-enrollment.md)

3. No painel de navegação, selecione **Dispositivos** para exibir detalhes sobre os dispositivos registrados em seu locatário do Intune. 

    > [!TIP]
    > Se você já usou o Intune no portal do Azure, encontrou os detalhes acima no portal do Azure entrando no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecionando **Dispositivos**.

    O painel **Dispositivos – Visão Geral** tem várias guias que permitem exibir um resumo dos seguintes status e alertas:
    - **Status do registro** – examine os detalhes sobre os dispositivos registrados no Intune por plataforma e falhas de registro.
    - **Alertas de registro** – encontre mais detalhes sobre os dispositivos não atribuídos por plataforma. 
    - **Status de conformidade** – examine o status de conformidade com base em dispositivo, política, configuração, ameaças e proteção. Além disso, esse painel fornece uma lista de dispositivos sem uma política de conformidade.
    - **Status de configuração** – examine o status de configuração dos perfis de dispositivo, bem como a implantação de perfil e 
    - **Status de atualização de software** – veja um visual do status de implantação para todos os dispositivos e todos os usuários.

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Dispositivos](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-03.png)

4. No painel **Dispositivos – Visão Geral**, selecione **Políticas de conformidade** para exibir detalhes sobre a conformidade dos dispositivos gerenciados pelo Intune. Você verá detalhes semelhantes aos da imagem a seguir.

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Políticas de conformidade](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-04.png)
    
    > [!TIP]
    > Se você já usou o Intune no portal do Azure, encontrou os detalhes acima no portal do Azure entrando no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecionando **Conformidade do Dispositivo**.

    Os requisitos de conformidade são essencialmente regras, como exigir um PIN do dispositivo ou exigir criptografia do dispositivo. Políticas de conformidade do dispositivo definem essas regras e configurações que um dispositivo deve seguir para ser considerado em conformidade. Para usar a conformidade do dispositivo, você precisa ter:
    - Uma assinatura do Intune e outra do Azure AD (Azure Active Directory) Premium
    - Dispositivos executando uma plataforma compatível
    - Os dispositivos precisam estar registrados no Intune
    - Dispositivos que estejam registrados para um usuário ou que não estejam registrados para nenhum usuário primário.
    
    Para mais informações, veja [Introdução às políticas de conformidade do dispositivo no Intune](../protect/device-compliance-get-started.md).

5. No painel **Dispositivos – Visão Geral**, selecione **Acesso Condicional** para exibir detalhes sobre as políticas de acesso.

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Acesso condicional](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-05.png)

    > [!TIP]
    > Se você já usou o Intune no portal do Azure, encontrou os detalhes acima no portal do Azure entrando no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecionando **Acesso Condicional**.

    Acesso Condicional significa às formas de controlar os dispositivos e aplicativos que têm permissão para se conectar ao email e aos recursos da empresa. Para saber mais sobre Acesso Condicional baseado em dispositivo e em aplicativo e ver cenários comuns para uso do acesso condicional com o Intune, confira [O que é acesso condicional?](../protect/conditional-access.md)

6. No painel de navegação, selecione **Dispositivos** > **Perfis de configuração** para exibir detalhes sobre os perfis de dispositivo no Intune.

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Perfis de configuração](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-06.png)
    
    > [!TIP]
    > Se você já usou o Intune no portal do Azure, encontrou os detalhes acima no portal do Azure entrando no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecionando **Configuração do dispositivo**.

    O Intune inclui configurações e recursos que você pode habilitar ou desabilitar em diferentes dispositivos na sua organização. Essas configurações e recursos são adicionados a "perfis de configuração". Crie perfis para diferentes dispositivos e plataformas, incluindo iOS, Android, macOS e Windows. Em seguida, você pode usar o Intune para aplicar o perfil aos dispositivos em sua organização.   

    Para obter mais informações sobre a configuração de dispositivo, veja [Aplicar configurações de recursos aos seus dispositivos usando perfis de dispositivo no Microsoft Intune](../configuration/device-profiles.md).

7. No painel de navegação, selecione **Dispositivos** > **Todos os dispositivos** para exibir detalhes sobre os dispositivos registrados do seu locatário do Intune. Se estiver começando com uma nova inscrição no Intune, você ainda não terá nenhum dispositivo registrado.

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Todos os dispositivos](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-07.png)

    Esta lista de dispositivos mostra os principais detalhes sobre conformidade, versão do sistema operacional e data do último check-in.

    > [!TIP]
    > Se você já usou o Intune no portal do Azure, encontrou os detalhes acima no portal do Azure entrando no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecionando **Dispositivos** > **Todos os dispositivos**.
 
8. No painel de navegação, selecione **Aplicativos** para exibir uma visão geral do status do aplicativo. Esse painel fornece o status de instalação do aplicativo com base nas seguintes guias:

    > [!TIP]
    > Se você já usou o Intune no portal do Azure, encontrou os detalhes acima no portal do Azure entrando no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecionando **Aplicativos cliente**.

    O painel **Aplicativos – Visão Geral** tem duas guias que permitem ver um resumo dos seguintes status:
    - **Status da instalação** – veja as principais falhas de instalação por dispositivo, bem como os aplicativos com falhas de instalação.  
    - **Status da política de proteção do aplicativo** – encontre detalhes sobre os usuários atribuídos às políticas de proteção do aplicativo, bem como os usuários sinalizados.

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Aplicativos](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-08.png)

    Como administrador de TI, você pode usar o Microsoft Intune para gerenciar os aplicativos cliente que os colaboradores da sua empresa usam. Essa funcionalidade está além do gerenciamento de dispositivos e proteção de dados. Uma das prioridades do administrador é garantir que os usuários finais tenham acesso aos aplicativos necessários para realizar seu trabalho. Além disso, pode ser útil atribuir e gerenciar aplicativos em dispositivos que não estão registrados com o Intune. O Intune oferece uma variedade de recursos para ajudar a obter os aplicativos que você precisa, nos dispositivos que você deseja. 

    > [!NOTE]
    > O painel **Aplicativos – Visão Geral** também fornece detalhes do status do locatário e da conta.

    Para obter mais informações sobre como adicionar e atribuir aplicativos, confira [Adicionar aplicativos ao Microsoft Intune](../apps/apps-add.md) e [Atribuir aplicativos a grupos com o Microsoft Intune](../apps/apps-deploy.md).

9. No painel **Aplicativos – Visão Geral**, selecione **Todos os aplicativos** para ver uma lista dos aplicativos que foram adicionados ao Intune.

    > [!TIP]
    > Se você já usou o Intune no portal do Azure, encontrou os detalhes acima no portal do Azure entrando no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecionando **Aplicativos cliente** > **Aplicativos**.

    Você pode adicionar uma variedade de tipos de aplicativos diferentes baseados na plataforma ao Intune. Depois que um aplicativo for adicionado, você poderá atribuí-lo a grupos de usuários. 

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Todos os aplicativos](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-09.png)

    Para obter mais informações, confira [Adicionar aplicativos ao Microsoft Intune](~/apps/apps-add.md). 

10. No painel de navegação, selecione **Usuários** para exibir detalhes sobre os usuários que você incluiu no Intune. Esses usuários são a força de trabalho de sua empresa.

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Usuários](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-10.png)

    > [!TIP]
    > Se você já usou o Intune no portal do Azure, encontrou os detalhes acima no portal do Azure entrando no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecionando **Usuários**.

    Você pode adicionar usuários diretamente ao Intune ou sincronizar os usuários do seu Active Directory local. Depois de adicionados, os usuários podem registrar dispositivos e acessar os recursos da empresa. Você também pode conceder permissões adicionais aos usuários para que acessem o Intune. Para obter mais informações, confira [Adicionar usuários e conceder permissão administrativa ao Intune](users-add.md).

11. No painel de navegação, selecione **Grupos** para exibir detalhes sobre os grupos do Azure AD (Azure Active Directory) incluídos no Intune. Como um administrador do Intune, use os grupos para gerenciar usuários e dispositivos.

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Grupos](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-11.png)

    > [!TIP]
    > Se você já usou o Intune no portal do Azure, encontrou os detalhes acima no portal do Azure entrando no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecionando **Grupos**.

    Você pode configurar grupos para atender às suas necessidades organizacionais. Crie grupos para organizar usuários ou dispositivos por localização geográfica, departamento ou características de hardware. Use grupos para gerenciar tarefas em grande escala. Por exemplo, você pode definir políticas para vários usuários ou implantar aplicativos em um conjunto de dispositivos. Para obter mais informações sobre grupos, confira [Adicionar grupos para organizar usuários e dispositivos](../groups-add.md).

12. No painel de navegação, selecione **Administração de locatário** para exibir detalhes sobre o seu locatário do Intune.

    > [!TIP]
    > Se você já usou o Intune no portal do Azure, encontrou os detalhes acima no portal do Azure entrando no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecionando **Status do locatário**.

    O painel **Administrador de locatários – Status do locatário** fornece guias para **Detalhes do locatário**, **Status do conector** e **Painel de integridade do serviço**. Em caso de problemas com o seu locatário ou o próprio Intune, você encontrará detalhes disponíveis nesse painel. 

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Status do locatário](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-12.png)

    Para obter mais informações, veja [Status do Locatário do Intune](../tenant-status.md).

13. No painel de navegação, selecione **Solução de problemas + suporte** > **Solução de problemas** para verificar os detalhes do status de um usuário específico. 

    > [!TIP]
    > Se você já usou o Intune no portal do Azure, encontrou os detalhes acima no portal do Azure entrando no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecionando **Solução de problemas**.

    Na lista suspensa **Atribuições**, você pode optar por ver as atribuições de destino de aplicativos cliente, políticas, anéis de atualização e restrições de registro. Além disso, esse painel fornece detalhes do dispositivo, status de proteção do aplicativo e falhas de registro para um usuário específico.

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Solução de problemas](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-13.png)

    Para obter mais informações sobre a solução de problemas no Intune, confira [Usar o portal de solução de problemas para ajudar os usuários na empresa](../help-desk-operators.md).

14. No painel de navegação, selecione **Solução de problemas + suporte** > **Ajuda e suporte** para solicitar ajuda. 

    > [!TIP]
    > Se você já usou o Intune no portal do Azure, encontrou os detalhes acima no portal do Azure entrando no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecionando **Ajuda e suporte**.

    Como administrador de TI, você poderá usar a opção **Ajuda e Suporte** para pesquisar e exibir soluções, bem como abrir um tíquete de suporte online para o Intune. 

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Ajuda e suporte](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-14.png)

    Para criar um tíquete de suporte, é preciso atribuir uma função de administrador à sua conta no Azure Active Directory. As funções de administrador incluem **Administrador do Intune**, **Administrador global** e **Administrador de serviços**. 

    Para obter mais informações, confira [Como obter suporte para o Microsoft Intune](../get-support.md).

15. No painel de navegação, selecione **Solução de problemas + suporte** > **Cenários guiados** para exibir os cenários guiados do Intune disponíveis. 

    Um cenário guiado é uma série personalizada de etapas centradas em um caso de uso de ponta a ponta. Cenários comuns são baseados na função que um administrador, usuário ou dispositivo desempenha e sua organização. Essas funções normalmente exigem uma coleção de perfis, configurações, aplicativos e controles de segurança cuidadosamente orquestrados para fornecer as melhores experiência do usuário e segurança.

    Se você não estiver familiarizado com todas as etapas e recursos necessários para implementar um cenário específico do Intune, os cenários guiados poderão ser usados como seu ponto de partida. 

    ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Cenários guiados](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-15.png)

    Para obter mais informações sobre os cenários guiados, confira [Visão geral dos cenários guiados](~/fundamentals/guided-scenarios-overview.md).

## <a name="configure-the-microsoft-endpoint-manager-admin-center"></a>Configurar o Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft

O Azure permite que você personalize e configure a exibição do portal.

### <a name="change-the-dashboard"></a>Alterar o painel

O **Painel** para exibir detalhes gerais sobre os dispositivos e os aplicativos cliente em seu locatário do Intune. Os painéis fornecem uma maneira de criar uma exibição focalizada e organizada no Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft. Use os painéis como um workspace no qual você possa iniciar rapidamente tarefas para operações diárias e monitorar recursos. Crie painéis personalizados com base em projetos, tarefas ou funções de usuário, por exemplo. O Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft fornece um painel padrão como ponto de partida. Você pode editar o painel padrão, criar e personalizar painéis adicionais e publicar e compartilhar painéis a fim de disponibilizá-los para outros usuários. 

   ![Captura de tela do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft – Painel](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-16.png)

Para modificar o painel atual, selecione **Editar**. Caso não deseje alterar o painel padrão, você também poderá criar um **Novo painel**. A opção de criar um novo painel oferece um painel privado vazio com a **Galeria de Blocos**, permitindo que você adicione ou reorganize os blocos. Encontre blocos por categoria ou tipo de recurso. Pesquise também blocos específicos. Selecione **Meu Painel** para selecionar um dos painéis personalizados existentes.

### <a name="change-the-portal-settings"></a>Alterar as configurações do portal

Personalize o Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft escolhendo a exibição padrão, o tema, o período de tempo limite das credenciais, bem como as configurações de idioma e região.

   <img alt="Screenshot of the Microsoft Endpoint Manager admin center - Portal settings" src="./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-17.png" width="250">

## <a name="next-steps"></a>Próximas etapas

Para começar rapidamente a usar o Microsoft Intune, siga os Inícios Rápidos do Intune, configurando primeiro uma conta gratuita do Intune.

> [!div class="nextstepaction"]
> [Início rápido: Experimente o Microsoft Intune gratuitamente](free-trial-sign-up.md)
