---
title: Criar e implantar a política de proteção do aplicativo da WIP (Proteção de Informações do Windows)
titlesuffix: Microsoft Intune
description: Criar e implantar a política de proteção de aplicativo da WIP (Proteção de Informações do Windows) com o Microsoft Intune
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f08dde25de5962eaaa11487a367b2895c6c047d4
ms.sourcegitcommit: 2b5d88c434bda7f1cdc32d1ccacc6b341a9a399b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2018
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Criar e implantar a política de proteção de aplicativo WIP (Proteção de Informações do Windows) com o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Você pode usar as políticas de proteção do aplicativo com aplicativos do Windows 10 para proteger aplicativos sem registro de dispositivo.

## <a name="before-you-begin"></a>Antes de começar

Você precisa compreender alguns conceitos ao adicionar uma política de WIP:

### <a name="list-of-allowed-and-exempt-apps"></a>Lista de aplicativos permitidos e isentos

-   **Aplicativos protegidos**: estes são os aplicativos que precisam atender a esta política.

-   **Aplicativos isentos**: estes aplicativos são isentos desta política e podem acessar dados corporativos sem restrições.

### <a name="types-of-apps"></a>Tipos de aplicativos

-   **Aplicativos recomendados:** uma lista pré-populada de aplicativos (principalmente do Microsoft Office) que pode ser importada facilmente para a política.
-   **Aplicativos da loja:** é possível adicionar qualquer aplicativo da Windows Store à política.
-   **Aplicativos da área de trabalho do Windows:** é possível adicionar qualquer aplicativo tradicional de área de trabalho do Windows à política (por exemplo, .exe, .dll etc.)

## <a name="prerequisites"></a>Pré-requisitos

Você precisa configurar o provedor MAM antes de criar uma política de proteção de aplicativo WIP. Saiba mais sobre [como configurar seu provedor MAM com o Intune](app-protection-policies-configure-windows-10.md).

Além disso, você precisa ter a licença e a atualização a seguir:

-   Licença do [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)
-   [Atualização do Windows para Criadores](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> O WIP não oferece suporte a várias identidades. Pode haver apenas uma identidade gerenciada de cada vez.

## <a name="to-add-a-wip-app-protection-policy"></a>Para adicionar uma política de proteção de aplicativo de WIP

Depois de configurar o Intune em sua organização, você poderá criar uma política específica de WIP.

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**.
3. Selecione **Aplicativos móveis** na folha **Microsoft Intune**.
4. Selecione **Políticas de proteção de aplicativo** na folha **Aplicativos móveis**.
5. Selecione **Adicionar uma política** para exibir a folha **Adicionar uma política**.
6. Adicione os seguintes valores:
    - **Nome:** digite um nome (obrigatório) para a nova política.
    - **Descrição:** (opcional) digite uma descrição.
    - **Plataforma:** escolha **Windows 10** como uma plataforma com suporte para a política de proteção do aplicativo.
    - **Estado do registro:** escolha **Sem registro** como o estado de registro para a política.
7.  Escolha **Criar**. A política é criada e aparece na tabela na folha **Políticas de proteção de aplicativo**.

## <a name="to-add-recommended-apps-to-your-protected-apps-list"></a>Como adicionar aplicativos recomendados à sua lista de aplicativos protegidos

1. Selecione **Aplicativos móveis** na folha **Microsoft Intune**.
2. Selecione **Políticas de proteção de aplicativo** na folha **Aplicativos móveis**.
3. Na folha **Políticas de proteção de aplicativo**, escolha a política que você deseja modificar. A folha **Proteção de Aplicativo do Intune** é exibida.
4. Escolha **Aplicativos protegidos** na folha **Proteção de Aplicativo do Intune**. A folha **Aplicativos protegidos** é aberta, mostrando todos os aplicativos que já estão incluídos na lista desta política de proteção de aplicativo.
5. Selecione **Adicionar aplicativos**. A informação **Adicionar aplicativos** mostra uma lista filtrada de aplicativos. A lista na parte superior da folha permite que você altere o filtro da lista.
6. Selecione cada aplicativo para o qual deseja permitir acesso aos dados corporativos.
7. Clique em **OK**. A folha **Aplicativos protegidos** é atualizada, mostrando todos os aplicativos selecionados.
8. Clique em **Salvar**.

## <a name="add-a-store-app-to-your-protected-apps-list"></a>Adicionar aplicativos da loja à sua lista de aplicativos protegidos

**Para adicionar um aplicativo da Store**
1. Selecione **Aplicativos móveis** na folha **Microsoft Intune**.
2. Selecione **Políticas de proteção de aplicativo** na folha **Aplicativos móveis**.
3. Na folha **Políticas de proteção de aplicativo**, escolha a política que você deseja modificar. A folha **Proteção de Aplicativo do Intune** é exibida.
4. Escolha **Aplicativos protegidos** na folha **Proteção de Aplicativo do Intune**. A folha **Aplicativos protegidos** é aberta, mostrando todos os aplicativos que já estão incluídos na lista desta política de proteção de aplicativo.
5. Selecione **Adicionar aplicativos**. A informação **Adicionar aplicativos** mostra uma lista filtrada de aplicativos. A lista na parte superior da folha permite que você altere o filtro da lista.
6. Na lista, selecione **Aplicativos da loja**.
7. Insira valores para **Nome**, **Editor**, **Nome do Produto** e **Ação**. Defina o valor de **Ação** como **Permitir**, para que o aplicativo tenha acesso aos dados corporativos.
9. Clique em **OK**. A folha **Aplicativos protegidos** é atualizada, mostrando todos os aplicativos selecionados.
10. Clique em **Salvar**.

## <a name="add-a-desktop-app-to-your-protected-apps-list"></a>Adicionar aplicativo da área de trabalho à sua lista de aplicativos protegidos

**Adicionar um aplicativo da área de trabalho**
1. Selecione **Aplicativos móveis** na folha **Microsoft Intune**.
2. Selecione **Políticas de proteção de aplicativo** na folha **Aplicativos móveis**.
3. Na folha **Políticas de proteção de aplicativo**, escolha a política que você deseja modificar. A folha **Proteção de Aplicativo do Intune** é exibida.
4. Escolha **Aplicativos protegidos** na folha **Proteção de Aplicativo do Intune**. A folha **Aplicativos protegidos** é aberta, mostrando todos os aplicativos que já estão incluídos na lista desta política de proteção de aplicativo.
5. Selecione **Adicionar aplicativos**. A informação **Adicionar aplicativos** mostra uma lista filtrada de aplicativos. A lista na parte superior da folha permite que você altere o filtro da lista.
6. Na lista, selecione **Aplicativos da área de trabalho**.
7. Insira valores para **Nome**, **Editor**, **Nome do Produto**, **Arquivo**, **Versão Mínima**, **Versão Máxima** e **Ação**. Defina o valor de **Ação** como **Permitir**, para que o aplicativo tenha acesso aos dados corporativos.
9. Clique em **OK**. A folha **Aplicativos protegidos** é atualizada, mostrando todos os aplicativos selecionados.
10. Clique em **Salvar**.

## <a name="wip-learning"></a>Aprendizado de WIP
Depois de adicionar os aplicativos que deseja proteger com WIP, você precisará aplicar um modo de proteção por meio de **Aprendizado de WIP**.

### <a name="before-you-begin"></a>Antes de começar

O Aprendizado da WIP é um relatório que permite monitorar aplicativos habilitados para WIP e desconhecidos da WIP. Os aplicativos desconhecidos são aqueles que não são implantados pelo departamento de TI da sua organização. É possível exportar esses aplicativos do relatório e adicioná-los às políticas de WIP para evitar a interrupção de produtividade antes que eles imponham o WIP no modo "Bloquear".

<!-- 1631908 -->
Além de exibir informações sobre aplicativos habilitados para WIP, você pode exibir um resumo dos dispositivos que compartilharam dados de trabalho com sites. Com essas informações, é possível determinar quais sites devem ser adicionados às políticas de WIP de grupo e de usuário. O resumo mostra quais URLs de site são acessadas pelos aplicativos habilitados pela WIP.

Ao trabalhar com aplicativos habilitados para a WIP e aplicativos desconhecidos da WIP, recomendamos que você inicie com **Silencioso** ou **Permitir Substituições** durante a verificação com um pequeno grupo que você tenha os aplicativos certos em sua lista de aplicativos protegidos. Depois de terminar, você poderá alterar sua política de imposição final, **Bloquear**.

### <a name="what-are-the-protection-modes"></a>Quais são os modos de proteção?

#### <a name="block"></a>Bloquear
O WIP procura práticas inadequadas de compartilhamento de dados e impede que o usuário conclua a ação. Isso pode incluir compartilhar informações entre aplicativos protegidos não corporativos e compartilhar dados corporativos entre outras pessoas e dispositivos fora da sua organização.

#### <a name="allow-overrides"></a>Permitir Substituições
O WIP procura compartilhamento inadequado de dados, avisando os usuários quando eles fizerem algo considerado potencialmente não seguro. No entanto, esse modo permite que o usuário substitua a política e compartilhe os dados, registrando a ação no log de auditoria.

#### <a name="silent"></a>Silencioso
O WIP é executado silenciosamente, registrando em log o compartilhamento inadequado de dados, sem bloquear nada que tenha solicitado a interação do funcionário enquanto estava no modo Permitir Substituições. As ações não permitidas, como aplicativos tentando acessar indevidamente um recurso de rede ou dados protegidos por WIP, ainda são interrompidas.

#### <a name="off-not-recommended"></a>Desligado (não recomendado)
O WIP é desativado e não ajuda a proteger ou auditar seus dados.

Depois de desativar o WIP, é feita uma tentativa de descriptografar arquivos marcados por WIP nas unidades conectadas localmente. Observe que as informações anteriores de política e a descriptografia não serão reaplicadas automaticamente se você ativar novamente a proteção da WIP.

### <a name="add-a-protection-mode"></a>Adicionar um modo de proteção

1.  Na folha **Política de aplicativo**, escolha o nome da política e, em seguida, escolha **Configurações necessárias**.

    ![Captura de tela do modo de aprendizado](./media/learning-mode-sc1.png)

1.  Selecione uma configuração e, em seguida, escolha **Salvar**.

### <a name="use-wip-learning"></a>Usar o aprendizado de WIP

1. Abra o [portal do Azure](https://portal.azure.com). Escolha **Todos os serviços**. Digite **Intune** no filtro de caixa de texto.

3. Escolha **Intune** > **Aplicativos móveis**.

4. Escolha **Status de proteção do aplicativo** > **Relatórios** > **aprendizado do Windows Information Protection**.  

    Quando os aplicativos estiverem aparecendo no relatório de log do Aprendizado de WIP, você poderá adicioná-los em suas políticas de proteção do aplicativo.

## <a name="allow-windows-search-indexer-to-search-encrypted-items"></a>Permitir que o indexador do Windows Search pesquise itens criptografados
Permite ou não a indexação de itens. Essa opção é para o indexador do Windows Search, que controla se os itens que são criptografados serão indexados, como os arquivos protegidos pela WIP (Proteção de Informações do Windows).

Essa opção de política de proteção de aplicativo está nas **Configurações avançadas** da política da Proteção de Informações do Windows. A política de proteção do aplicativo deve ser definida para a plataforma *Windows 10* e a política de aplicativo **Estado do registro** deve ser definida como **Com registro**.

Quando a política está habilitada, os itens protegido pela WIP são indexados e os metadados sobre eles são armazenados em um local não criptografado. Os metadados incluem coisas como o caminho do arquivo e a data de modificação.

Quando a política é desabilitada, os itens protegidos pela WIP não são indexados e não aparecem nos resultados na Cortana ou no Explorador de Arquivos. Também poderá haver um impacto no desempenho em fotos e em aplicativos do Groove se houver muitos arquivos de mídia protegidos pela WIP no dispositivo.

## <a name="add-encrypted-file-extensions"></a>Adicionar extensões de arquivo criptografado

Além da configuração da opção **Permitir que o indexador do Windows Search pesquise itens criptografados**, você pode especificar uma lista de extensões de arquivo. Os arquivos com essas extensões são criptografados durante a cópia de um compartilhamento de SMB (protocolo SMB) dentro do limite corporativo conforme definido na lista de locais de rede. Quando essa política não é especificada, o comportamento atual de criptografia automática é aplicado. Quando essa política está configurada, somente os arquivos com as extensões da lista são criptografados.

## <a name="deploy-your-wip-app-protection-policy"></a>Implantar uma política de proteção de aplicativo WIP

> [!IMPORTANT]
> Essa informação aplica-se à WIP sem registro de dispositivo.

<!---not sure why you need the Important note. Isn't this what the topic is about? app protection w/o enrollment?--->

Depois que você tiver criado a política de proteção de aplicativo WIP, precisará implantá-la em sua organização usando MAM.

1.  Na folha **Política de aplicativo**, escolha a política de proteção de aplicativo recém-criada e escolha **Grupos de usuários** > **Adicionar grupo de usuários**.

    Uma lista de grupos de usuários é aberta, composta por todos os grupos de segurança no Azure Active Directory, na folha **Adicionar grupo de usuários**.

2.  Escolha o grupo ao qual será aplicada a política e escolha **Selecionar** para implantá-la.

## <a name="next-steps"></a>Próximas etapas

Saiba mais sobre a Proteção de Informações do Windows, consulte [Proteger os dados corporativos usando a WIP (Proteção de Informações do Windows)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).
