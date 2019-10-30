---
title: Adicionar um aplicativo de linha de negócios do Windows ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar aplicativos de linha de negócios (LOB) do Windows usando o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6df77d168bb8be3775c566f63833b46130515b36
ms.sourcegitcommit: 5807f4db4a45a093ce2fd6cb0c480bec384ec1ff
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72601574"
---
# <a name="add-a-windows-line-of-business-app-to-microsoft-intune"></a>Adicionar um aplicativo de linha de negócios do Windows ao Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Um aplicativo de LOB (linha de negócios) é um aplicativo que pode ser adicionado de um arquivo de instalação do aplicativo. Esse tipo de aplicativo normalmente é escrito internamente. As etapas a seguir fornecem diretrizes para ajudá-lo a adicionar um aplicativo de LOB do Windows ao Microsoft Intune.

> [!IMPORTANT]
> Ao implantar aplicativos Win32 usando um arquivo de instalação com a extensão *. msi*, considere usar a [Extensão de Gerenciamento do Intune](../apps/intune-management-extension.md). Se você misturar a instalação dos aplicativos Win32 e de linha de negócios durante o registro no AutoPilot, a instalação do aplicativo poderá falhar.  

## <a name="step-1-specify-the-software-setup-file"></a>Etapa 1: Especificar o arquivo de instalação do software

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel **Intune**, selecione **Aplicativos clientes**.
4. Na carga de trabalho **Aplicativos clientes**, selecione **Gerenciar** > **Aplicativos**.
5. Acima da lista de aplicativos, selecione **Adicionar**.
6. No painel **Adicionar aplicativo**, selecione **Aplicativo de linha de negócios**.

## <a name="step-2-configure-the-app-package-file"></a>Etapa 2: Configurar o arquivo de pacote do aplicativo

1. No painel **Adicionar aplicativo**, selecione o **Arquivo do pacote do aplicativo**.
2. No painel **Arquivo do pacote do aplicativo**, selecione o botão Procurar. Em seguida, selecione um arquivo de instalação do Windows com a extensão **.msi**, **.appx** ou **.appxbundle**.

    > [!NOTE]
    > As extensões do arquivo para aplicativos do Windows incluem **.msi**, **.appx**, **.appxbundle**, **.msix** e **.msixbundle**.  

1. Quando tiver terminado, selecione **OK**.


## <a name="step-3-configure-app-information"></a>Etapa 3: Configurar informações do aplicativo

1. No painel **Adicionar aplicativo**, selecione **Informações do aplicativo**.
2. No painel **Informações do aplicativo**, configure as seguintes informações. Alguns dos valores neste painel podem ser sido preenchidos automaticamente.
    - **Nome**: Insira o nome do aplicativo como ele é exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido no portal da empresa.
    - **Descrição**: Insira uma descrição para o aplicativo. A descrição será exibida no portal da empresa.
    - **Editor**: Insira o nome do editor do aplicativo.
    - **Ignorar versão do aplicativo**: Defina como **Sim** se o aplicativo for atualizado automaticamente pelo desenvolvedor do aplicativo. Essa opção se aplica somente a aplicativos .msi móveis.
    - **Categoria**: Selecione uma ou mais das categorias de aplicativo interno ou uma categoria criada por você. As categorias facilitam para os usuários a localização do aplicativo ao navegar no portal da empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: Exiba o aplicativo de maneira proeminente em na página principal do portal da empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: Opcionalmente, Insira a URL de um site que contém informações sobre esse aplicativo. A URL será exibida no portal da empresa.
    - **URL de Privacidade**: Opcionalmente, Insira a URL de um site que contém informações de privacidade desse aplicativo. A URL será exibida no portal da empresa.
    - **Argumentos de linha de comando**: Opcionalmente, Insira os argumentos de linha de comando que você deseja aplicar ao arquivo .msi quando ele for executado.  Um exemplo é **/q**. Não inclua o comando ou os argumentos msiexec, como **/i** ou **/x**, já que eles são usados automaticamente. Para mais informações, consulte as [Opções de linha de comando](https://docs.microsoft.com/windows/desktop/Msi/command-line-options). Se o arquivo .MSI precisar de opções de linha de comando adicionais, pense na possibilidade de usar o [gerenciamento do aplicativo Win32](app-management.md).
    - **Desenvolvedor**: Opcionalmente, Insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: Opcionalmente, Insira o nome do proprietário desse aplicativo. Um exemplo é **Departamento de RH**.
    - **Observações**: Insira as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: Carregue um ícone associado ao aplicativo. O ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
3. Quando tiver terminado, selecione **OK**.

## <a name="step-4-finish-up"></a>Etapa 4: Concluir

1. No painel **Adicionar aplicativo**, verifique se você configurou as informações do aplicativo corretamente.
2. Selecione **Adicionar** para carregar o aplicativo no Intune.

## <a name="step-5-update-a-line-of-business-app"></a>Etapa 5: Atualizar um aplicativo de linha de negócios

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

   > [!NOTE]
   > Para que o serviço do Intune implante com êxito um novo arquivo appx no dispositivo, incremente a cadeia de caracteres `Version` no arquivo AppxManifest.xml em seu pacote appx.

## <a name="configure-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Configurar um aplicativo móvel de MSI com atualização automática para ignorar o processo de verificação de versão

Você pode configurar um aplicativo móvel do MSI com atualização automática conhecido para ignorar o processo de verificação de versão.

Alguns aplicativos com base no instalador MSI são atualizados automaticamente pelo desenvolvedor do aplicativo ou por outro método de atualização. Para esses aplicativos do MSI atualizados automaticamente, você pode configurar a opção **Ignorar a versão do aplicativo** no painel **Informações do aplicativo**. Quando essa configuração é definida como **Sim**, o Microsoft Intune não impõe a versão do aplicativo instalada no cliente do Windows.

Essa funcionalidade é útil para evitar entrar em uma condição de corrida. Por exemplo, uma condição de corrida pode ocorrer quando o aplicativo é atualizado automaticamente pelo desenvolvedor do aplicativo e é atualizado pelo Intune. As duas atualizações podem tentar impor uma versão do aplicativo em um cliente do Windows, o que cria um conflito.

## <a name="next-steps"></a>Próximas etapas

- O aplicativo que você criou aparece na lista de aplicativos. Agora você pode atribuí-lo aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

- Saiba mais sobre as maneiras como você pode monitorar as propriedades e a atribuição de seu aplicativo. Veja [Como monitorar informações e atribuições de aplicativo](apps-monitor.md).

- Saiba mais sobre o contexto do seu aplicativo no Intune. Confira [Visão geral do ciclo de vida do aplicativo no Microsoft Intune](app-lifecycle.md).
