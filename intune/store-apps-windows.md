---
title: Como adicionar aplicativos da Microsoft Store para o Microsoft Intune
titleSuffix: ''
description: Aprenda a adicionar aplicativos da Microsoft Store (Windows Store) ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 511cf2e01a2f5db93f0e0db9dbe2a32326c17723
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Adicionar aplicativos da Microsoft Store ao Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Antes que possa atribuir, monitorar, configurar ou proteger aplicativos, você precisa adicioná-los ao Intune. As etapas a seguir permitem que você adicione um aplicativo da Microsoft Store ao Microsoft Intune.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.
5. Acima da lista de aplicativos, escolha **Adicionar**.
6. No painel **Adicionar aplicativo**, escolha um **Tipo de aplicativo** do **Windows** e selecione **Informações do aplicativo**.
7. No painel **Informações do aplicativo**, configure as seguintes informações. Quando terminar, clique em **OK**. Dependendo do aplicativo escolhido, alguns dos valores neste painel podem ter sido preenchidos automaticamente:
    - **Nome**: insira o nome do aplicativo como ele será exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição** -insira uma descrição para o aplicativo que será exibida aos usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **URL da loja de aplicativos** – insira a URL da loja de aplicativos do aplicativo que você deseja criar.
    - **Categoria (opcional)** – selecione uma ou mais categorias de aplicativo internas ou uma categoria que você criou, para facilitar a localização do aplicativo para os usuários que procuram no portal da empresa.
    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL será exibida para os usuários no portal da empresa.
    - **URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL será exibida para os usuários no portal da empresa.
    - **Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.
    - **Observações** – Digite as observações que você deseja associar a este aplicativo.
    - **Logotipo** – carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários procuram no portal da empresa.
8. Após terminar, no painel **Adicionar aplicativo**, escolha **Adicionar**.

O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher. 

## <a name="next-steps"></a>Próximas etapas
- [Como atribuir aplicativos aos grupos](apps-deploy.md)