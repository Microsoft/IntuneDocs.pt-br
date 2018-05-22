---
title: Adicionar um aplicativo de linha de negócios do Windows Phone ao Microsoft Intune
titlesuffix: ''
description: Saiba como adicionar um aplicativo de linha de negócios do Windows Phone ao Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ccc1f25d137675ba8e5f984a16324f4b0771dc9c
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
---
# <a name="add-a-windows-phone-line-of-business-app-to-microsoft-intune"></a>Adicionar um aplicativo de linha de negócios do Windows Phone ao Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use as informações deste artigo para adicionar um aplicativo de linha de negócios (LOB) do Windows Phone ao Microsoft Intune. Um aplicativo de LOB é um aplicativo que pode ser adicionado ao Intune a partir de um arquivo de instalação de aplicativo. Esse tipo de aplicativo normalmente é escrito internamente. O Intune instala o aplicativo de LOB no dispositivo do usuário. 

## <a name="step-1-specify-the-software-setup-file"></a>Etapa 1: Especificar os arquivos de instalação de software

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**. O Intune está na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, selecione **Gerenciar** > **Aplicativos**.
5. Acima da lista de aplicativos, selecione **Adicionar**.
6. No painel **Adicionar aplicativo**, selecione **Aplicativo de linha de negócios**.

## <a name="step-2-configure-the-app-package-file"></a>Etapa 2: configurar o arquivo de pacote do aplicativo

1. No painel **Adicionar aplicativo**, selecione o **Arquivo do pacote do aplicativo**.
2. No painel **Arquivo do pacote do aplicativo**, selecione o botão Procurar. Em seguida, selecione um arquivo de instalação do Windows Phone com a extensão **.xap**.
3. Quando tiver terminado, selecione **OK**.


## <a name="step-3-configure-app-information"></a>Etapa 3: Configurar informações do aplicativo

1. No painel **Adicionar aplicativo**, selecione **Informações do aplicativo**.
2. No painel **Informações do aplicativo**, configure as informações do aplicativo. Dependendo do aplicativo escolhido, alguns dos valores neste painel podem ser preenchidos automaticamente.
    - **Nome**: insira o nome do aplicativo como ele é exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. A descrição será exibida no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **Ignorar versão do aplicativo**: defina como **Sim** se o aplicativo for atualizado automaticamente pelo desenvolvedor do aplicativo.
    - **Categoria**: selecione uma ou mais das categorias de aplicativo interno ou uma categoria criada por você. As categorias facilitam para os usuários a localização do aplicativo ao navegar no portal da empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: exiba o aplicativo em destaque na página principal do portal da empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL será exibida no portal da empresa.
    - **URL de Privacidade**: opcionalmente, insira a URL de um site que contém informações de privacidade desse aplicativo. A URL será exibida no portal da empresa.
    - **Desenvolvedor**: opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: opcionalmente, insira um nome para o proprietário desse aplicativo. Um exemplo é **Departamento de RH**.
    - **Observações**: digite as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
3. Quando tiver terminado, selecione **OK**.

## <a name="step-4-finish-up"></a>Etapa 4: concluir

1. No painel **Adicionar aplicativo**, verifique se você configurou as informações corretamente.
2. Selecione **Adicionar** para carregar o aplicativo no Intune.

## <a name="next-steps"></a>Próximas etapas

- O aplicativo que você criou aparece na lista de aplicativos. Agora você pode atribuí-lo aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

- Saiba mais sobre as maneiras como você pode monitorar as propriedades e a atribuição de seu aplicativo. Veja [Como monitorar informações e atribuições de aplicativo](apps-monitor.md).

- Saiba mais sobre o contexto do seu aplicativo no Intune. Veja [Visão geral dos ciclos de vida do dispositivo e do aplicativo](introduction-device-app-lifecycles.md).
