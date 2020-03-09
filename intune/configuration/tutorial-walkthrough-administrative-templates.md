---
title: Guia passo a passo – Criar um modelo administrativo no Microsoft Intune – Azure | Microsoft Docs
description: Este tutorial ou guia passo a passo usa o Microsoft Intune para configurar modelos ADMX do Office, do Windows e do Microsoft Edge no Windows 10 e em dispositivos mais recentes.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a96f291203e1513ab89196b26a7802856f90e048
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77688084"
---
# <a name="tutorial-use-the-cloud-to-configure-group-policy-on-windows-10-devices-with-admx-templates-and-microsoft-intune"></a>Tutorial: Usar a nuvem para configurar a política de grupo em dispositivos Windows 10 com modelos ADMX e o Microsoft Intune

> [!NOTE]
> Este tutorial foi criado como um workshop técnico para o Microsoft Ignite. Ele tem mais pré-requisitos do que os tutoriais típicos, pois compara o uso e a configuração de políticas do ADMX no Intune e locais.

Os modelos administrativos da política de grupo, também conhecidos como modelos ADMX, incluem configurações que podem ser definidas em dispositivos Windows 10, incluindo PCs. As configurações de modelo ADMX estão disponíveis em serviços diferentes. Essas configurações são usadas pelos provedores do MDM (Gerenciamento de Dispositivo Móvel), incluindo o Microsoft Intune. Por exemplo, você pode ativar Ideias de Design no PowerPoint, definir uma página inicial no Microsoft Edge, bloquear controles do ActiveX no Internet Explorer e muito mais.

Os modelos ADMX estão disponíveis para os seguintes serviços:

- **Microsoft Edge**: Download no [arquivo de política do Microsoft Edge](https://www.microsoftedgeinsider.com/en-us/enterprise).
- **Office**: Download no [Office 365 ProPlus, no Office 2019 e no Office 2016](https://www.microsoft.com/download/details.aspx?id=49030).
- **Windows**: Inserido no sistema operacional Windows 10.

Para obter mais informações sobre as políticas de ADMX, confira [Noções básicas de políticas apoiadas por ADMX](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies).

No Microsoft Intune, esses modelos são inseridos no serviço do Intune e estão disponíveis como perfis de **Modelos administrativos**. Nesse perfil, você define as configurações que deseja incluir e, em seguida, "atribui" esse perfil a seus dispositivos.

Neste tutorial, você vai:

> [!div class="checklist"]
> * Entre no [centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
> * Crie grupos de usuários e crie grupos de dispositivos.
> * Compare as configurações no Intune com as configurações do ADMX locais.
> * Crie modelos administrativos diferentes e defina as configurações direcionadas a grupos distintos.

Ao final deste laboratório, você terá as habilidades para começar a usar o Intune e Microsoft 365 para gerenciar seus usuários e implantar modelos administrativos.

Esse recurso aplica-se a:

- Windows 10 versão 1703 e mais recentes

## <a name="prerequisites"></a>Pré-requisitos

- Uma assinatura do Microsoft 365 E3 ou E5, que inclui o Intune e o Azure AD (Active Directory) Premium. Se você não tiver uma assinatura E3 ou E5, [teste gratuitamente](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365?view=o365-worldwide).

  Para obter mais informações sobre o que você obtém com as diferentes licenças de Microsoft 365, confira [Transforme sua empresa com o Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

- O Microsoft Intune está configurado como a **Autoridade de MDM do Intune**. Para obter mais informações, confira [Definir a autoridade de gerenciamento de dispositivo móvel](../fundamentals/mdm-authority-set.md).

  > [!div class="mx-imgBorder"]
  > ![Definir a autoridade de MDM para Microsoft Intune em seu status de locatário](./media/tutorial-walkthrough-administrative-templates/tenant-status.png)

- Em um DC (controlador de domínio) do Active Directory local:

  1. Copie os seguintes modelos do Office e do Microsoft Edge para o [Repositório Central (pasta SYSVOL)](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra):

      - [Modelos administrativos do Office](https://www.microsoft.com/download/details.aspx?id=49030)
      - [Modelos administrativos do Microsoft Edge > arquivo de Política](https://www.microsoftedgeinsider.com/en-us/enterprise)

  2. Crie uma política de grupo para enviar esses modelos por push a um computador de administrador do Windows 10 Enterprise no mesmo domínio que o controlador de domínio. Neste tutorial:

      - A política de grupo que criamos com esses modelos é chamada de **OfficeandEdge**. Você verá esse nome nas imagens.
      - O computador do administrador do Windows 10 Enterprise que usamos é chamado de **Computador do administrador**.

      Em algumas organizações, um administrador de domínio tem duas contas, uma conta de trabalho de domínio típica e uma conta de administrador de domínio diferente usada somente para tarefas de administrador de domínio, como a política de grupo.

      A finalidade desse **Computador do administrador** é que os administradores entrem com a conta de administrador de domínio e acessem as ferramentas criadas para gerenciar a política de grupo.

- Neste **Computador do administrador**:

  - Entre com uma conta de Administrador de Domínio.

  - Instalar as **Ferramentas de Administração de Servidor Remoto: Ferramentas de Gerenciamento de Política de Grupo**:

    1. Abra o aplicativo **Configurações** > **Aplicativos** > **Recursos opcionais** > **Adicionar recurso**.
    2. Selecione **Ferramentas de Administração de Servidor Remoto: Ferramentas de Gerenciamento de Política de Grupo** > **Instalar**.

        Aguarde enquanto o Windows instala o recurso. Quando concluído, ele eventualmente aparece no aplicativo **Ferramentas Administrativas do Windows**.

        > [!div class="mx-imgBorder"]
        > ![Aplicativos de Ferramentas Administrativas do Windows, incluindo aplicativo de Gerenciamento de Política de Grupo](./media/tutorial-walkthrough-administrative-templates/windows-administrative-tools-app.png)

  - Verifique se você tem direitos de acesso à Internet e de administrador para a assinatura do Microsoft 365, que inclui o centro de administração do Endpoint Manager.

## <a name="open-the-endpoint-manager-admin-center"></a>Abra o centro de administração do Endpoint Manager

1. Abra um navegador da Web Chromium, como o Microsoft Edge versão 77 e posteriores.
2. Acesse o [centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) (https://devicemanagement.microsoft.com). Entre com a seguinte conta:

    **Usuário**: Insira a conta de administrador de sua assinatura de locatário do Microsoft 365.  
    **Senha**: Insira sua senha.

Esse centro de administração concentra-se no gerenciamento de dispositivos e inclui serviços do Azure, como o Azure AD e o Intune. Talvez você não veja a identidade visual do **Azure Active Directory** e do **Intune**, mas você as está usando.

Você também pode abrir o centro de administração do Endpoint Manager no [centro de administração do Microsoft 365](https://admin.microsoft.com):

1. Vá para [https://admin.microsoft.com](https://admin.microsoft.com).
2. Entre com sua conta de administrador de sua assinatura de locatário do Microsoft 365.
3. Em **Centros de administração**, selecione **Todos os centros de administração** > **Gerenciamento de ponto de extremidade**. O centro de administração do Endpoint Manager é aberto.

    > [!div class="mx-imgBorder"]
    > ![Ver todos os centros de administração no centro de administração do Microsoft 365](./media/tutorial-walkthrough-administrative-templates/microsoft365-admin-centers.png)

## <a name="create-groups-and-add-users"></a>Criar grupos e adicionar usuários

As políticas locais são aplicadas na ordem LSDOU: local, site, domínio e UO (unidade organizacional). Nessa hierarquia, as políticas de UO substituem políticas locais, as políticas de domínio substituem políticas de site e assim por diante.

No Intune, as políticas são aplicadas aos usuários e grupos que você criar. Não há uma hierarquia. Se duas políticas atualizarem a mesma configuração, a configuração aparecerá como um conflito. Se duas políticas de conformidade estiverem em conflito, a mais restritiva se aplicará. Se dois perfis de configuração estiverem em conflito, a configuração não será aplicada. Para obter mais informações, confira [Perguntas, problemas e resoluções comuns com perfis e políticas de dispositivo](device-profile-troubleshoot.md#if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied).

Nestas próximas etapas, você criará grupos de segurança e adicionará usuários aos grupos. Você pode adicionar um usuário a vários grupos. Por exemplo, é normal que um usuário tenha vários dispositivos, como Surface Pro para trabalho e um dispositivo móvel Android para uso pessoal. E é normal que uma pessoa acesse os recursos organizacionais usando esses vários dispositivos.

1. No centro de administração do Microsoft Endpoint Manager, selecione **Grupos** > **Novo grupo**.

2. Insira as seguintes configurações:

    - **Tipo de grupo**: Selecione **Segurança**.
    - **Nome do grupo**: Insira **Todos os dispositivos do aluno com Windows 10**.
    - **Tipo de associação**: Selecione **Atribuído**.

3. Selecione **Membros** e adicione alguns dispositivos.

    Adicionar dispositivos é opcional. A meta é praticar a criação de grupos e saber como adicionar dispositivos. Se você estiver usando este tutorial em um ambiente de produção, lembre-se do que está fazendo.

4. **Selecione** > **Criar** para salvar suas alterações.

    Não vê seu grupo? Selecione **Atualizar**.

5. Selecione **Novo grupo** e insira as seguintes configurações:

    - **Tipo de grupo**: Selecione **Segurança**.
    - **Nome do grupo**: Insira **Todos os dispositivos Windows**.
    - **Tipo de associação**: Selecione **Dispositivo Dinâmico**.
    - **Membros do dispositivo dinâmico**: Configure sua consulta:

        - **Propriedade**: Selecione **deviceOSType**.
        - **Operador**: Selecione **Equals**.
        - **Valor**: Insira **Windows**.

        1. Selecione **Adicionar expressão**. Sua expressão é mostrada na **Sintaxe da regra**:

            > [!div class="mx-imgBorder"]
            > ![Criar uma consulta dinâmica e Adicionar a expressão no modelo administrativo Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/dynamic-group-query.png)

            Quando os usuários ou dispositivos cumprem os critérios inseridos, eles são automaticamente adicionados aos grupos dinâmicos. Neste exemplo, os dispositivos são adicionados automaticamente a esse grupo quando o sistema operacional é o Windows. Se você estiver usando este tutorial em um ambiente de produção, tenha cuidado. A meta é praticar a criação de grupos dinâmicos.

        2. **Salvar** > **Criar** para salvar suas alterações.

6. Crie o grupo **Todos os Professores** com as seguintes configurações:

    - **Tipo de grupo**: Selecione **Segurança**.
    - **Nome do grupo**: Insira **Todos os Professores**.
    - **Tipo de associação**: Selecione **Usuário Dinâmico**.
    - **Membros de usuário dinâmico**: Configure sua consulta:

      - **Propriedade**: Selecione **departamento**.
      - **Operador**: Selecione **Equals**.
      - **Valor**: Insira **Professores**.

        1. Selecione **Adicionar expressão**. Sua expressão é mostrada na **Sintaxe da regra**.

            Quando os usuários ou dispositivos cumprem os critérios inseridos, eles são automaticamente adicionados aos grupos dinâmicos. Neste exemplo, os usuários são adicionados automaticamente a esse grupo quando o departamento deles é Professores. Você pode inserir o departamento e outras propriedades quando os usuários são adicionados à sua organização. Se você estiver usando este tutorial em um ambiente de produção, tenha cuidado. A meta é praticar a criação de grupos dinâmicos.

        2. **Salvar** > **Criar** para salvar suas alterações.

### <a name="talking-points"></a>Pontos de discussão

- Grupos dinâmicos são um recurso no Azure AD Premium. Se você não tiver o Azure AD Premium, estará licenciado para criar apenas grupos atribuídos. Para obter mais informações sobre grupos dinâmicos, confira:

  - [Associação de grupo dinâmica no Azure Active Directory (Parte 1)](https://blogs.technet.microsoft.com/pauljones/2017/08/28/dynamic-group-membership-in-azure-active-directory-part-1/)
  - [Associação de grupo dinâmica no Azure Active Directory (Parte 2)](https://blogs.technet.microsoft.com/pauljones/2017/08/29/dynamic-group-membership-in-azure-active-directory-part-2/)

- O Azure AD Premium inclui outros serviços comumente usados ao gerenciar aplicativos e dispositivos, incluindo [MFA (autenticação multifator)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) e [acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

- Muitos administradores perguntam quando devem usar grupos de usuários e quando devem usar grupos de dispositivos. Para obter algumas diretrizes, confira [Grupos de usuários versus grupos de dispositivos](device-profile-assign.md#user-groups-vs-device-groups).

- Lembre-se de que um usuário pode pertencer a vários grupos. Considere alguns dos outros grupos de usuários e dispositivos dinâmicos que você pode criar, como:

  - Todos os alunos
  - Todos os dispositivos Android
  - Todos os dispositivos iOS/iPadOS
  - Marketing
  - Recursos Humanos
  - Todos os funcionários da Alice
  - Todos os funcionários da Redmond
  - Administradores de TI da costa oeste
  - Administradores de TI da costa leste

Os usuários e grupos criados também são vistos no [Centro de administração do Microsoft 365](https://admin.microsoft.com), no Azure AD no portal do Azure e no [Microsoft Intune no portal do Azure](https://go.microsoft.com/fwlink/?linkid=2090973). Você pode criar e gerenciar grupos em todas essas áreas para sua assinatura de locatário. **Se a meta for o gerenciamento de dispositivos, use o [centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)** .

### <a name="review-group-membership"></a>Examinar a associação de grupo

1. No centro de administração do Endpoint Manager, selecione **Usuários** > selecione o nome de qualquer usuário existente.

    > [!div class="mx-imgBorder"]
    > ![No centro de administração do Endpoint Manager, selecione Usuários](./media/tutorial-walkthrough-administrative-templates/select-users-endpoint-manager-admin-center.png)

2. Examine algumas das informações que você pode adicionar ou alterar. Por exemplo, examine as propriedades que você pode configurar, como Cargo, Departamento, Cidade, Localização do escritório e muito mais. Você pode usar essas propriedades em suas consultas dinâmicas ao criar grupos dinâmicos.
3. Selecione **Grupos** para ver a associação deste usuário. Você também pode remover o usuário de um grupo.
4. Selecione algumas das outras opções para ver mais informações e o que você pode fazer. Por exemplo, examine a licença atribuída, os dispositivos do usuário e muito mais.

### <a name="what-did-i-just-do"></a>O que eu acabei de fazer?

No centro de administração do Endpoint Manager, você criou grupos de segurança e adicionou usuários e dispositivos existentes a esses grupos. Usaremos esses grupos em etapas posteriores neste tutorial.

## <a name="create-a-template-in-intune"></a>Criar um modelo no Intune

Nesta seção, criamos um modelo administrativo no Intune, analisamos algumas configurações em **Política de Grupo Management**e comparamos a mesma configuração no Intune. A meta é mostrar uma configuração na política de grupo e mostrar a mesma configuração no Intune.

1. No centro de administração do Endpoint Manager, selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
2. Insira as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para o perfil. Nomeie seus perfis para que você possa identificá-los facilmente mais tarde. Por exemplo, insira **Modelo de administração – dispositivos de aluno do Windows 10**.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Selecione **Windows 10 e posterior**.
    - **Tipo de perfil**: Selecione **Modelos administrativos**.

3. Selecione **Criar**. Na lista suspensa **Selecionar uma categoria**, selecione **Todos os produtos**. Todas as configurações são mostradas. Nessas configurações, observe as seguintes propriedades:

    - O **Caminho** para a política é o mesmo que o Gerenciamento da Política de Grupo ou GPEdit.
    - A configuração se aplica a usuários ou dispositivos.

### <a name="open-group-policy-management"></a>Abrir o Gerenciamento de Política de Grupo

Nesta seção, mostramos uma política no Intune e sua política correspondente no Editor de Gerenciamento de Política de Grupo.

#### <a name="compare-a-device-policy"></a>Comparar uma política de dispositivo

1. No **Computador do administrador**, abra o aplicativo **Gerenciamento de Política de Grupo**.

    Esse aplicativo é instalado com **Ferramentas de Administração de Servidor Remoto: Ferramentas de Gerenciamento de Política de Grupo**, que é um recurso opcional que você instala no Windows. Os [Pré-requisitos](#prerequisites) (neste artigo) listam as etapas para instalá-lo.

2. Expanda **Domínios** > selecione seu domínio. Por exemplo, selecione **contoso.net**.
3. Clique com o botão direito do mouse na política **OfficeandEdge** > **Editar**. Isso abre o aplicativo Editor de Gerenciamento de Política de Grupo.

    > [!div class="mx-imgBorder"]
    > ![Clique com o botão direito do mouse na política de grupo ADMX do Office e do Edge e selecione Editar](./media/tutorial-walkthrough-administrative-templates/open-group-policy-management.png)

    **OfficeandEdge** é uma política de grupo que inclui os modelos ADMX do Office e do Microsoft Edge. Essa política é descrita nos [pré-requisitos](#prerequisites) (neste artigo).

4. Expanda **Configuração do computador** > **Políticas** > **Modelos Administrativos** > **Painel de Controle** > **Personalização**. Observe as configurações disponíveis.

    > [!div class="mx-imgBorder"]
    > ![Expanda Configuração do Computador no Editor de Gerenciamento de Política de Grupo e vá para Personalização](./media/tutorial-walkthrough-administrative-templates/open-group-policy-management-editor-admx-policy.png)

    Clique duas vezes em **Impedir a habilitação da câmera da tela de bloqueio** e veja as opções disponíveis:

    > [!div class="mx-imgBorder"]
    > ![Confira as Opções de configuração do computador na política de grupo](./media/tutorial-walkthrough-administrative-templates/prevent-enabling-lock-screen-camera-admx-policy.png)

5. No centro de administração do gerenciamento de dispositivos, acesse seu **Modelo de administrador – dispositivos de aluno do Windows 10**.
6. Selecione **Todos os produtos** na lista suspensa e pesquise **personalização**:

    > [!div class="mx-imgBorder"]
    > ![Pesquisar personalização no modelo administrativo no Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/search-personalization-administrative-template.png)

    Observe as configurações disponíveis.

    O tipo de configuração é **Dispositivo** e o caminho é **\Painel de Controle\Personalização**. Esse caminho é semelhante ao que você acabou de ver no Editor de Gerenciamento de Política de Grupo. Se você abrir a configuração, verá as mesmas opções **Não configurado**, **Habilitado** e **Desabilitado** que você vê no Editor de Gerenciamento de Política de Grupo.

#### <a name="compare-a-user-policy"></a>Comparar uma política de usuário

1. No modelo de administrador, pesquise **navegação inprivate**. Observe o caminho e que a configuração se aplica a usuários e dispositivos.

2. No **Editor de Gerenciamento de Política de Grupo**, localize as configurações de usuário e dispositivo correspondentes:

    - Dispositivo: expanda **Configuração do computador** > **Políticas** > **Modelos administrativos** > **Componentes do Windows** > **Internet Explorer** > **Privacidade** > **Desativar a Navegação InPrivate**.
    - Usuário: expanda **Configuração do usuário** > **Políticas** > **Modelos administrativos** > **Componentes do Windows** > **Internet Explorer** > **Privacidade** > **Desativar a Navegação InPrivate**.

    > [!div class="mx-imgBorder"]
    > ![Desligar a Navegação InPrivate no Internet Explorer usando o modelo ADMX](./media/tutorial-walkthrough-administrative-templates/group-policy-turn-off-inprivate-browsing.png)

> [!TIP]
> Para ver as políticas internas do Windows, você também pode usar o aplicativo GPEdit (**editar política de grupo**).

#### <a name="compare-an-edge-policy"></a>Comparar uma política do Edge

1. No centro de administração do gerenciamento de dispositivos, acesse seu **Modelo de administrador – dispositivos de aluno do Windows 10**.
2. Selecione **Edge versão 77 e posteriores** na lista suspensa.
3. Pesquise **inicialização**. Observe as configurações disponíveis.
4. Em Editor de Gerenciamento de Política de Grupo, encontre estas configurações:

    - Dispositivo: expanda **Configuração do computador** > **Políticas** > **Modelos Administrativos** > **Microsoft Edge** > **Inicialização, página inicial e página de nova guia**.
    - Usuário: expanda **Configuração do usuário** > **Políticas** > **Modelos Administrativos** > **Microsoft Edge** > **Inicialização, página inicial e página de nova guia**

### <a name="what-did-i-just-do"></a>O que eu acabei de fazer?

Você criou um modelo administrativo no Intune. Neste modelo, examinamos algumas configurações do ADMX e as mesmas configurações do ADMX no Gerenciamento de Política de Grupo.

## <a name="add-settings-to-the-students-admin-template"></a>Adicionar configurações ao modelo de administrador de Alunos

Neste modelo, definimos algumas configurações do Internet Explorer para bloquear dispositivos compartilhados por vários alunos.

1. Em seu **Modelo de administrador – dispositivos de aluno do Windows 10**, pesquise **Desligar Navegação InPrivate** e selecione a política de dispositivo:

    > [!div class="mx-imgBorder"]
    > ![Desligar política do dispositivo Desativar Navegação InPrivate no modelo administrativo no Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/turn-off-inprivate-browsing-administrative-template.png)

2. Nesta janela, observe a descrição e os valores que você pode definir. Essas opções são semelhantes às que você vê na política de grupo.
3. Selecione **Habilitado** > **OK** para salvar as alterações.
4. Além disso, defina as configurações do Internet Explorer a seguir. Selecione **OK** para salvar suas alterações.

    - **Permitir arrastar e soltar ou copiar e colar arquivos**
      - **Tipo**: Dispositivo
      - **Caminho**: \Componentes do Windows\Internet Explorer\Painel de Controle da Internet\Página de Segurança\Zona da Internet
      - **Valor**: Desativado

    - **Prevenir ignorar erros de certificado**
      - **Tipo**: Dispositivo
      - **Caminho**: \Componentes do Windows\Internet Explorer\Painel de Controle da Internet
      - **Valor**: Habilitada

    - **Desabilitar a alteração de configurações da página inicial**
      - **Tipo**: Usuário
      - **Caminho**: \Componentes do Windows\Internet Explorer
      - **Valor**: Habilitada
      - **Página Inicial**: insira uma URL, como `contoso.com`.

5. Limpe o filtro de pesquisa. Observe que as configurações que você definiu estão listadas na parte superior:

    > [!div class="mx-imgBorder"]
    > ![As configurações definidas são listadas na parte superior no Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/configured-settings-administrative-template.png)

### <a name="assign-your-template"></a>Atribuir seu modelo

1. Em seu modelo, selecione **Atribuições**. Talvez seja necessário fechar o modelo e, em seguida, selecioná-lo na lista **Dispositivos – perfis de configuração**:

    > [!div class="mx-imgBorder"]
    > ![Selecione o perfil de modelo administrativo na lista perfis de Configuração do Dispositivo no Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/filter-administrative-template-device-configuration-profiles-list.png)

2. Escolha **Selecionar grupos a incluir**. É mostrada uma lista de usuários e grupos existentes.
3. Selecione o grupo **Todos os dispositivos de aluno do Windows 10** criado anteriormente > **Selecionar**.

    Se você estiver usando este tutorial em um ambiente de produção, considere adicionar grupos vazios. A meta é praticar a atribuição do modelo.

4. **Salve** suas alterações.

Assim que o perfil é salvo, ele se aplica aos dispositivos quando eles fazem check-in no Intune. Se os dispositivos estiverem conectados à Internet, isso poderá acontecer imediatamente. Para obter mais informações sobre tempos de atualização de política, confira [Quanto tempo leva para que os dispositivos obtenham uma política, um perfil ou um aplicativo depois que eles são atribuídos](device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Ao atribuir políticas e perfis estritos ou restritivos, não se bloqueie. Considere criar um grupo que esteja excluído de suas políticas e perfis. A ideia é ter acesso para solucionar problemas. Monitore esse grupo para confirmar que ele está sendo usado conforme o pretendido.

### <a name="what-did-i-just-do"></a>O que eu acabei de fazer?

No centro de administração do Endpoint Manager, você criou um perfil de configuração de dispositivo de modelo administrativo e atribuiu esse perfil a um grupo que você criou.

## <a name="create-a-onedrive-template"></a>Criar um modelo do OneDrive

Nesta seção, você cria um modelo de administrador do OneDrive no Intune para controlar algumas configurações. Essas configurações específicas são escolhidas porque são comumente usadas pelas organizações.

1. Crie outro perfil (**Dispositivos** > **Perfis de configuração** > **Criar perfil**).

2. Insira as seguintes propriedades:

    - **Nome**: Insira **Modelo de administrador – políticas do OneDrive que se aplicam a todos os usuários do Windows 10**.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Selecione **Windows 10 e posterior**.
    - **Tipo de perfil**: Selecione **Modelos administrativos**.

3. Selecione **Criar**.
4. Selecione **Office** na lista suspensa.
5. **Habilite** as configurações a seguir. Selecione **OK** para salvar suas alterações.

    - **Conectar silenciosamente usuários ao cliente de sincronização do OneDrive com as respectivas credenciais do Windows**
    - **Usar arquivos do OneDrive sob demanda**
    - **Impedir que os usuários sincronizem contas pessoais do OneDrive**

Suas configurações serão semelhantes às seguintes:

> [!div class="mx-imgBorder"]
> ![Criar um modelo administrativo do OneDrive no Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/one-drive-administrative-template.png)

Para obter mais informações sobre as configurações do cliente do OneDrive, confira [Usar Política de Grupo para controlar as configurações do cliente de sincronização do OneDrive](https://docs.microsoft.com/onedrive/use-group-policy).

### <a name="assign-your-template"></a>Atribuir seu modelo

1. Em seu modelo, selecione **Atribuições**.
2. Escolha **Selecionar grupos a incluir**. É mostrada uma lista de usuários e grupos existentes.
3. Selecione o grupo **Todos os dispositivos do Windows** criado anteriormente > **Selecionar**.

    Se você estiver usando este tutorial em um ambiente de produção, considere adicionar grupos vazios. A meta é praticar a atribuição do modelo.

4. **Salve** suas alterações.

Neste ponto, você criou alguns modelos administrativos e os atribuiu a grupos que você criou. A próxima etapa é criar um modelo administrativo usando o Windows PowerShell e a API do Microsoft Graph para o Intune.

## <a name="optional-create-a-policy-using-powershell-and-graph-api"></a>Opcional: Criar uma política usando o PowerShell e a API do Graph

Esta seção usa os recursos a seguir. Instalaremos estes recursos nesta seção.

- [SDK do PowerShell do Intune](https://github.com/microsoft/Intune-PowerShell-SDK)
- [API do Microsoft Graph para Intune](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0)

1. No **computador do administrador**, abra o **Windows PowerShell** como administrador:

    1. Na barra de pesquisa, insira **poweshell**.
    2. Clique com o botão direito do mouse em **Windows PowerShell** > **Executar como administrador**.

    > [!div class="mx-imgBorder"]
    > ![Executar Windows PowerShell como administrador](./media/tutorial-walkthrough-administrative-templates/run-windows-powershell-administrator.png)

2. Obter e definir a política de execução.

    1. Insira: `get-ExecutionPolicy`

        Anote a definição, que pode ser **Restrito**. Ao concluir o tutorial, defina-o de volta para seu valor original.

    2. Insira: `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`

    3. Insira `Y` para alterá-lo.

    A política de execução do PowerShell ajuda a impedir a execução de scripts mal-intencionados. Para obter mais informações, confira [Sobre as Políticas de Execução](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies).

3. Insira: `Install-Module -Name Microsoft.Graph.Intune`

    Insira `Y` se:

    - Solicitado a instalar o provedor do NuGet
    - Solicitado a instalar os módulos de um repositório não confiável

    Ele pode demorar várias minutos para ser concluído. Quando terminar, um prompt semelhante ao seguinte será mostrado:

    > [!div class="mx-imgBorder"]
    > ![Prompt do Windows PowerShell após a instalação de um módulo](./media/tutorial-walkthrough-administrative-templates/powershell-prompt.png)

4. No navegador da Web, vá para [https://github.com/Microsoft/Intune-PowerShell-SDK/releases](https://github.com/Microsoft/Intune-PowerShell-SDK/releases) e selecione o arquivo **Intune-PowerShell-SDK_v6.1907.00921.0001.zip**.

    1. Selecione **Salvar como** e selecione uma pasta que você vá lembrar. `c:\psscripts` é uma boa opção.
    2. Abra a pasta, clique com o botão direito do mouse no arquivo .zip > **Extrair tudo** > **Extrair**. Sua estrutura de pastas é semelhante à seguinte pasta:

        > [!div class="mx-imgBorder"]
        > ![Estrutura de pastas do SDK do Intune PowerShell após ser extraída](./media/tutorial-walkthrough-administrative-templates/psscripts-directory.png)

5. Na guia **Exibir**, confira **Extensões de nome de arquivo**:

    > [!div class="mx-imgBorder"]
    > ![selecionar extensões de nome de arquivo na guia Exibir no explorador](./media/tutorial-walkthrough-administrative-templates/file-names-extension.png)

6. Em sua pasta e vá para `c:\psscripts\Intune-PowerShell-SDK_v6.1907.00921.0001\drop\outputs\build\Release\net471`. Clique com o botão direito do mouse em cada .dll > **Propriedades** > **Desbloquear**.

    > [!div class="mx-imgBorder"]
    > ![Desbloquear as DLLs](./media/tutorial-walkthrough-administrative-templates/unblock-dll.png)

7. No seu aplicativo **Windows PowerShell**, insira:

    ```powershell
    Import-Module c:\psscripts\Intune-PowerShell-SDK_v6.1907.00921.0001\drop\outputs\build\Release\net471\Microsoft.Graph.Intune.psd1
    ```

    Insira `R` se for solicitado a executar usando o editor não confiável.

8. Os modelos administrativos do Intune usam a versão beta do Graph:

    1. Insira: `Update-MSGraphEnvironment -SchemaVersion 'beta'`

    2. Insira: `Connect-MSGraph -AdminConsent`

    3. Quando solicitado, entre com a mesma conta de administrador do Microsoft 365. Esses cmdlets criam a política em sua organização de locatário.

        **Usuário**: Insira a conta de administrador de sua assinatura de locatário do Microsoft 365.  
        **Senha**: Insira sua senha.

    4. Selecione **Aceitar**.

9. Crie o perfil de configuração da **Configuração de Teste**. Insira:

    ```powershell
    $configuration = Invoke-MSGraphRequest -Url https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations -Content '{"displayName":"Test Configuration","description":"A test configuration created through PS"}' -HttpMethod POST
    ```

    Quando esses cmdlets forem bem-sucedidos, o perfil será criado. Para confirmar, acesse o centro de administração do Endpoint Manager > **Perfis de Configuração**. Seu perfil **Configuração de Teste** deve ser listado.

10. Obtenha todas as SettingDefinitions. Insira:

    ```powershell
    $settingDefinitions = Invoke-MSGraphRequest -Url https://graph.microsoft.com/beta/deviceManagement/groupPolicyDefinitions -HttpMethod GET
    ```

11. Localize a ID de definição usando o nome de exibição da configuração. Insira:

    ```powershell
    $desiredSettingDefinition = $settingDefinitions.value | ? {$_.DisplayName -Match "Silently sign in users to the OneDrive sync client with their Windows credentials"}
    ```

12. Defina uma configuração. Insira:

    ```powershell
    $configuredSetting = Invoke-MSGraphRequest -Url "https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations('$($configuration.id)')/definitionValues" -Content ("{""enabled"":""true"",""configurationType"":""policy"",""definition@odata.bind"":""https://graph.microsoft.com/beta/deviceManagement/groupPolicyDefinitions('$($desiredSettingDefinition.id)')""}") -HttpMethod POST
    ```

    ```powershell
    Invoke-MSGraphRequest -Url "https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations('$($configuration.id)')/definitionValues('$($configuredSetting.id)')" -Content ("{""enabled"":""false""}") -HttpMethod PATCH
    ```

    ```powershell
    $configuredSetting = Invoke-MSGraphRequest -Url "https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations('$($configuration.id)')/definitionValues('$($configuredSetting.id)')" -HttpMethod GET
    ```

### <a name="see-your-policy"></a>Veja sua política

1. No centro de administração do Endpoint Manager > **Perfis de Configuração** > **Atualizar**.
2. Selecione seu perfil de do **Configuração de Teste** > **Configurações**.
3. Na lista suspensa, selecione **Todos os Produtos**.

Você verá que a configuração **Conectar usuários silenciosamente ao cliente de sincronização do OneDrive com as credenciais do Windows** está definida.

## <a name="policy-best-practices"></a>Melhores práticas da política

Ao criar políticas e perfis no Intune, há algumas recomendações e melhores práticas a serem consideradas. Para obter mais informações, confira [Melhores práticas de política e perfil](device-profile-create.md#recommendations).

## <a name="clean-up-resources"></a>Limpar os recursos

Quando não for mais necessário, você poderá:

- Excluir os grupos que você criou:

  - **Todos os dispositivos do aluno com Windows 10**
  - **Todos os dispositivos Windows**
  - **Todos os professores**

- Exclua os modelos de administração que você criou:

  - **Modelo de administração – dispositivos de aluno do Windows 10**
  - **Modelo de administrador – políticas do OneDrive que se aplicam a todos os usuários do Windows 10**
  - **Configuração de Teste**

- Defina a política de execução do Windows PowerShell de volta para seu valor original. O seguinte exemplo define a política de execução como restrita:

  ```powershell
  Set-ExecutionPolicy -ExecutionPolicy Restricted
  ```

## <a name="next-steps"></a>Próximas etapas

Neste tutorial, você familiarizou-se com o [centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), usou o Construtor de Consultas para criar grupos dinâmicos e criou modelos administrativos no Intune para definir [configurações do ADMX](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies). Você também comparou o uso de modelos ADMX locais e na nuvem com o Intune. Como um bônus, você usou cmdlets do PowerShell para criar um modelo administrativo.

Para obter mais informações sobre modelos administrativos no Intune, confira:

> [!div class="nextstepaction"]
> [Usar modelos do Windows 10 para definir as configurações da política de grupo no Intune](administrative-templates-windows.md)
