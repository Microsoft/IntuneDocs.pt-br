---
title: Como adicionar aplicativos da Store do Windows Phone 8.1 ao Microsoft Intune
titleSuffix: 
description: Saiba como adicionar aplicativos da Windows Phone 8.1 Store ao Microsoft Intune.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a95e575-2c63-4bfc-b9c4-f0a132eef618
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e4c3935c8dc263ceef9981a9fc9c47ace6f77d86
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-windows-phone-81-store-apps-to-microsoft-intune"></a>Como adicionar aplicativos da Store do Windows Phone 8.1 ao Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Antes de atribuir um aplicativo em um dispositivo ou um grupo de usuários, você deve primeiro adicionar o aplicativo ao Microsoft Intune. As etapas a seguir permitem que você adicione um aplicativo da Windows Phone 8.1 store ao Intune do Portal do Azure.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.
5. Acima da lista de aplicativos, escolha **Adicionar**.
6. No painel **Adicionar aplicativo**, escolha um **Tipo de aplicativo** do **Windows Phone 8.1** e selecione **Informações do aplicativo**.
7. No painel **Informações do aplicativo**, configure as seguintes informações. Quando terminar, clique em **OK**. Dependendo do aplicativo escolhido, alguns dos valores neste painel podem ter sido preenchidos automaticamente:
    - **Nome**: insira o nome do aplicativo como ele será exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. Isso será exibido para os usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **URL da loja de aplicativos** – insira a URL da loja de aplicativos do aplicativo que você deseja criar.
    - **Categoria (opcional)** – Selecione uma das categorias de aplicativo internas ou uma categoria criada por você. Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.

    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL será exibida para os usuários no portal da empresa.
    - **URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL será exibida para os usuários no portal da empresa.
    - **Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.
    - **Observações** – Digite as observações que você deseja associar a este aplicativo.
    - **Logotipo** - carregue um ícone que será associado ao aplicativo. Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.
8. Após terminar, no painel **Adicionar aplicativo**, escolha **Adicionar**.

O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).

## <a name="next-steps"></a>Próximas etapas

- [Como atribuir aplicativos aos grupos](apps-deploy.md)