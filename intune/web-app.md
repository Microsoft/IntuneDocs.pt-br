---
title: Como adicionar aplicativos Web ao Intune
titleSuffix: Intune on Azure
description: Saiba como adicionar aplicativos Web ao Intune.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f64d60b659d0316cab542cb6005026a353ab0589
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Como adicionar aplicativos Web ao Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Gerenciar aplicativos**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.
5. Acima da lista de aplicativos, escolha **Adicionar**.
6. Na folha **Adicionar Aplicativo**, escolha **Informações do Aplicativo**.
7. Na folha **Editar Aplicativo**, configure as seguintes informações. Ao terminar, clique em **Adicionar**:
    - **URL do aplicativo** – insira a URL do site da web que hospeda o aplicativo que você deseja atribuir.
    - **Nome do Aplicativo** – Insira o nome do aplicativo como ele será exibido no portal da empresa.
    - **Descrição do Aplicativo** – Insira uma descrição para o aplicativo. Isso será exibido para os usuários finais no portal da empresa.
    - **Editor** – insira o nome do editor do aplicativo.
    - **Categoria (opcional)** – Selecione uma das categorias de aplicativo internas ou uma categoria criada por você. Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.

    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **Requer um navegador gerenciado para abrir esse link** – quando você atribui um link para um site ou aplicativo Web aos usuários, eles só poderão abri-lo no navegador gerenciado do Intune. Este navegador deve estar instalado em seu dispositivo.
    - **Carregar Ícone** – Carregue um ícone que será associado ao aplicativo. Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.
8. Após terminar, escolha **Salvar** na folha **Adicionar Aplicativo**.

O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).