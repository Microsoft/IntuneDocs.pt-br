---
title: "Criar e implantar a política de proteção de aplicativo WIP (Proteção de Informações do Windows) com o Intune"
titlesuffix: Azure portal
description: "Criar e implantar a política de proteção do aplicativo WIP com o Intune"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 97f9407c8ba93307059e44c8becf4f7a36c6861a
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Criar e implantar a política de proteção de aplicativo WIP (Proteção de Informações do Windows) com o Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A partir da versão 1704 do Intune, é possível usar políticas de proteção de aplicativo com o Windows 10 para proteger aplicativos sem a necessidade de registrar dispositivos.

## <a name="before-you-begin"></a>Antes de começar

Vamos falar sobre alguns conceitos ao adicionar uma política WIP.

### <a name="list-of-allowed-and-exempt-apps"></a>Lista de aplicativos permitidos e isentos

-   **Aplicativos permitidos**: estes são os aplicativos que precisam atender a esta política.

-   **Aplicativos isentos**: estes aplicativos são isentos desta política e podem acessar dados corporativos sem restrições.

### <a name="types-of-apps"></a>Tipos de aplicativos

-   **Aplicativos recomendados:** uma lista pré-populada de aplicativos (principalmente do Microsoft Office) que permite importar facilmente para a política. <!---I really don't know what you mean by "easily import into policy"--->

-   **Aplicativos da loja:** é possível adicionar qualquer aplicativo da Windows Store à política.

-   **Aplicativos da área de trabalho do Windows:** é possível adicionar qualquer aplicativo tradicional de área de trabalho do Windows à política (por exemplo, .exe, .dll etc.)

## <a name="pre-requisites"></a>Pré-requisitos

Você precisa configurar o provedor MAM antes de criar uma política de proteção de aplicativo WIP. Saiba mais sobre [como configurar seu provedor MAM com o Intune](https://docs.microsoft.com/app-protection-policies-configure-windows-10.md).

Além disso, você precisará ter o seguintes:

-   Licença do [AD Premium do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).
-   [Atualização do Windows para Criadores](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> O WIP não oferece suporte a várias identidades. Pode haver apenas uma identidade gerenciada de cada vez.
<!---Should you be linking to a topic that explains what multi-identity is?--->

## <a name="to-add-a-wip-policy"></a>Para adicionar uma política WIP

Depois de configurar o Intune em sua organização, você poderá criar uma política específica WIP por meio do [Portal do Azure](https://docs.microsoft.com/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies). <!---Is there an azure topic you can use instead of a classic? if not, should this topic be moved into the azure docset?--->

1.  Vá para o **painel de gerenciamento de aplicativos móveis do Intune**, escolha **Todas as configurações**, > **Política de aplicativo**.

2.  Na folha **Política de aplicativo**, escolha **Adicionar uma política**, em seguida, insira os seguintes valores:

    a.  **Nome:** digite um nome (obrigatório) para a nova política.

    b.  **Descrição:** digite uma descrição opcional.

    c.  **Plataforma:** escolha **Windows 10** como uma plataforma com suporte para a política de proteção do aplicativo.

    d.  **Estado do registro:** escolha **Sem registro** como o estado de registro para a política.

3.  Escolha **Criar**. A política é criada e aparece na tabela na folha **Política de Aplicativo**.

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a>Adicionar aplicativos recomendados à lista de aplicativos permitidos

1.  Na folha **Política de aplicativo**, escolha o nome da política e escolha **Aplicativos permitidos** na folha **Adicionar uma política**. A folha **Aplicativos permitidos** é aberta, mostrando todos os aplicativos que já estão incluídos na lista para esta política de proteção do aplicativo.

2.  Na folha **Aplicativos permitidos**, escolha **Adicionar aplicativos**. A folha **Adicionar aplicativos** é aberta, mostrando todos os aplicativos que fazem parte dessa lista.

3.  Selecione cada aplicativo que você deseja que acesse seus dados corporativos e escolha **OK**. A folha **Aplicativos permitidos** é atualizada, mostrando todos os aplicativos selecionados.

## <a name="add-a-store-app-to-your-allowed-apps-list"></a>Adicionar um aplicativo da Store à lista de aplicativos permitidos

**Para adicionar um aplicativo da Store**

1.  Na folha **Política de aplicativo**, escolha o nome da política e escolha **Aplicativos permitidos** no menu que aparece mostrando todos os aplicativos que já estão incluídos na lista para esta política de proteção do aplicativo.

2.  Na folha **Aplicativos permitidos**, escolha **Adicionar aplicativos**.

3.  Na folha **Adicionar aplicativos**, escolha **Aplicativos da Store** na lista suspensa. A folha é alterada para mostrar caixas para você adicionar um **editor** e um **nome** de aplicativo.

4.  Digite o nome do aplicativo e o nome do editor e, em seguida, escolha **OK**.

    > [!TIP]
    > Veja um exemplo de aplicativo, onde o **Editor** é *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US* e o **nome** do produto é *Microsoft.MicrosoftAppForWindows*.

5.  Depois de inserir as informações nos campos, escolha **OK** para adicionar o aplicativo a sua lista de **Aplicativos permitidos**.

> [!NOTE]
> Para adicionar vários aplicativos da Store ao mesmo tempo, clique no menu **(...)**  no final da linha de aplicativo, em seguida, continue a adicionar mais aplicativos. Quando terminar, selecione **OK**.

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a>Adicionar um aplicativo da área de trabalho à lista de aplicativos permitidos

**Adicionar um aplicativo da área de trabalho**

1.  Na folha **Política de aplicativo**, escolha o nome da política e escolha **Aplicativos permitidos.** A folha **Aplicativos permitidos** é aberta, mostrando todos os aplicativos que já estão incluídos na lista para esta política de proteção do aplicativo.

2.  Na folha **Aplicativos permitidos**, escolha **Adicionar aplicativos**.

3.  Na folha **Adicionar aplicativos**, escolha **Aplicativos da Área de Trabalho** na lista suspensa.

4.  Depois de inserir as informações nos campos, escolha **OK** para adicionar o aplicativo a sua lista de **Aplicativos permitidos**.

> [!NOTE]
> Para adicionar vários **aplicativos da área de trabalho** ao mesmo tempo, clique no menu **(…)** no final da linha de aplicativo e, em seguida, continue a adicionar mais aplicativos. Quando terminar, selecione **OK**.

## <a name="wip-learning"></a>Aprendizado de WIP
<!---You've already defined WIP earlier in the topic. You don't need to keep doing so. --->
Depois de adicionar os aplicativos que deseja proteger com WIP, você precisará aplicar um modo de proteção por meio de **Aprendizado de WIP**.

### <a name="before-you-begin"></a>Antes de começar

O Aprendizado de WIP é um relatório que permite monitorar aplicativos com WIP desconhecido. Os aplicativos desconhecidos são aqueles que não são implantados pelo departamento de TI da sua organização. É possível exportar esses aplicativos do relatório e adicioná-los às políticas de WIP para evitar a interrupção de produtividade antes que eles imponham o WIP no modo "Bloquear".

Recomendamos que você inicie com **Silencioso** ou **Permitir Substituições** durante a verificação com um pequeno grupo que você tenha os aplicativos certos em sua lista de aplicativos permitidos. Depois de terminar, você poderá alterar sua política de imposição final, **Bloquear**.

### <a name="what-are-the-protection-modes"></a>Quais são os modos de proteção?

#### <a name="block"></a>Bloquear
O WIP procura práticas inadequadas de compartilhamento de dados e impede que o usuário conclua a ação. Isso pode incluir compartilhar informações entre aplicativos protegidos não corporativos e compartilhar dados corporativos entre outras pessoas e dispositivos fora da sua organização.

#### <a name="allow-overrides"></a>Permitir Substituições
O WIP procura compartilhamento inadequado de dados, avisando os usuários se eles fizerem algo considerado potencialmente não seguro. No entanto, esse modo permite que o usuário substitua a política e compartilhe os dados, registrando a ação no log de auditoria.

#### <a name="silent"></a>Silencioso
O WIP é executado silenciosamente, registrando em log o compartilhamento inadequado de dados, sem bloquear nada que tenha solicitado a interação do funcionário enquanto estava no modo Permitir Substituições. As ações não permitidas, como aplicativos tentando acessar indevidamente um recurso de rede ou dados protegidos por WIP, ainda são interrompidas.

#### <a name="off-not-recommended"></a>Desligado (não recomendado)
O WIP é desativado e não ajuda a proteger ou auditar seus dados.

Depois de desativar o WIP, é feita uma tentativa de descriptografar arquivos marcados por WIP nas unidades conectadas localmente. Lembre-se de que as informações anteriores de política e a descriptografia não serão reaplicadas automaticamente se você ativar novamente a proteção de WIP.

### <a name="add-a-protection-mode"></a>Adicionar um modo de proteção

1.  Na folha **Política de aplicativo**, escolha o nome da política e, em seguida, escolha **Configurações necessárias**.

    ![Captura de tela do modo de aprendizado](./media/learning-mode-sc1.png)

1.  Selecione **Salvar**.

### <a name="use-wip-learning"></a>Usar o aprendizado de WIP

1. Abra o portal do Azure. Selecione **Mais serviços**. Digite **Intune** no filtro de caixa de texto.

3. Escolha **Intune** > **Aplicativos móveis**.

4. Escolha **Status de proteção do aplicativo** > **Relatórios** > **aprendizado do Windows Information Protection**.  
 
    Quando os aplicativos estiverem aparecendo no relatório de log do Aprendizado de WIP, você poderá adicioná-los em suas políticas de proteção do aplicativo.

## <a name="deploy-your-wip-app-protection-policy"></a>Implantar uma política de proteção de aplicativo WIP

> [!IMPORTANT]
> Aplica-se ao WIP sem registro de dispositivo.

<!---not sure why you need the Important note. Isn't this what the topic is about? app protection w/o enrollment?--->

Depois que você tiver criado a política de proteção de aplicativo WIP, precisará implantá-la em sua organização usando MAM.

1.  Na folha **Política de aplicativo**, escolha a política de proteção de aplicativo recém-criada e escolha **Grupos de usuários** > **Adicionar grupo de usuários**.

    Uma lista de grupos de usuários é aberta, composta por todos os grupos de segurança no Azure Active Directory, na folha **Adicionar grupo de usuários**.

1.  Escolha o grupo ao qual será aplicada a política e escolha **Selecionar** para implantá-la.
