---
title: Adicionar um aplicativo de linha de negócios do Windows ao Microsoft Intune
titlesuffix: ''
description: Saiba como adicionar um aplicativo de linha de negócios do Windows ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ac5c06bc1656f932379d634e341ad9db9bc66419
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="add-a-windows-line-of-business-app-to-microsoft-intune"></a>Adicionar um aplicativo de linha de negócios do Windows ao Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Um aplicativo de LOB (linha de negócios) é um aplicativo que pode ser adicionado de um arquivo de instalação do aplicativo. Esse tipo de aplicativo normalmente é escrito internamente. As etapas a seguir fornecem diretrizes para ajudá-lo a adicionar um aplicativo de LOB do Windows ao Microsoft Intune.

## <a name="step-1-specify-the-software-setup-file"></a>Etapa 1: especificar o arquivo de instalação de software

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**. O Intune está na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, selecione **Gerenciar** > **Aplicativos**.
5. Acima da lista de aplicativos, selecione **Adicionar**.
6. No painel **Adicionar aplicativo**, selecione **Aplicativo de linha de negócios**.

## <a name="step-2-configure-the-app-package-file"></a>Etapa 2: configurar o arquivo de pacote do aplicativo

1. No painel **Adicionar aplicativo**, selecione o **Arquivo do pacote do aplicativo**.
2. No painel **Arquivo do pacote do aplicativo**, selecione o botão Procurar. Em seguida, selecione um arquivo de instalação do Windows com a extensão **.msi**, **.appx** ou **.appxbundle**.
3. Quando tiver terminado, selecione **OK**.


## <a name="step-3-configure-app-information"></a>Etapa 3: configurar informações do aplicativo

1. No painel **Adicionar aplicativo**, selecione **Informações do aplicativo**.
2. No painel **Informações do aplicativo**, configure as seguintes informações. Alguns dos valores neste painel podem ser sido preenchidos automaticamente.
    - **Nome**: insira o nome do aplicativo como ele é exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. A descrição será exibida no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **Ignorar versão do aplicativo**: defina como **Sim** se o aplicativo for atualizado automaticamente pelo desenvolvedor do aplicativo.
    - **Categoria**: selecione uma ou mais das categorias de aplicativo interno ou uma categoria criada por você. As categorias facilitam para os usuários a localização do aplicativo ao navegar no portal da empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: exiba o aplicativo em destaque na página principal do portal da empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: opcionalmente, insira a URL de um site que contém informações sobre o aplicativo. A URL será exibida no portal da empresa.
    - **URL de Privacidade**: opcionalmente, insira a URL de um site que contém informações de privacidade do aplicativo. A URL será exibida no portal da empresa.
    - **Argumentos de linha de comando**: opcionalmente, insira os argumentos de linha de comando que você deseja aplicar ao arquivo .msi quando ele for executado. Um exemplo é **/q**.
    - **Desenvolvedor**: opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: opcionalmente, insira um nome para o proprietário desse aplicativo. Um exemplo é **Departamento de RH**.
    - **Observações**: digite as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: carregue um ícone que será associado ao aplicativo. O ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
3. Quando tiver terminado, selecione **OK**.

## <a name="step-4-finish-up"></a>Etapa 4: concluir

1. No painel **Adicionar aplicativo**, verifique se você configurou as informações do aplicativo corretamente.
2. Selecione **Adicionar** para carregar o aplicativo no Intune.

## <a name="step-5-update-a-line-of-business-app"></a>Etapa 5: atualizar um aplicativo de linha de negócios

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## <a name="configure-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Configurar um aplicativo móvel de MSI com atualização automática para ignorar o processo de verificação de versão

Você pode configurar um aplicativo móvel do MSI com atualização automática conhecido para ignorar o processo de verificação de versão. 

Alguns aplicativos com base no instalador MSI são atualizados automaticamente pelo desenvolvedor do aplicativo. Para esses aplicativos do MSI atualizados automaticamente, você pode configurar a opção **Ignorar a versão do aplicativo** no painel **Informações do aplicativo**. Quando essa configuração é definida como **Sim**, o Microsoft Intune não impõe a versão do aplicativo instalada no cliente do Windows. 

Essa funcionalidade é útil para evitar entrar em uma condição de corrida. Por exemplo, uma condição de corrida pode ocorrer quando o aplicativo é atualizado automaticamente pelo desenvolvedor do aplicativo e é atualizado pelo Intune. As duas atualizações podem tentar impor uma versão do aplicativo em um cliente do Windows, o que cria um conflito.

## <a name="next-steps"></a>Próximas etapas

- O aplicativo que você criou aparece na lista de aplicativos. Agora você pode atribuí-lo aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

- Saiba mais sobre as maneiras como você pode monitorar as propriedades e a atribuição de seu aplicativo. Veja [Como monitorar informações e atribuições de aplicativo](apps-monitor.md).

- Saiba mais sobre o contexto do seu aplicativo no Intune. Veja [Visão geral dos ciclos de vida do dispositivo e do aplicativo](introduction-device-app-lifecycles.md).
