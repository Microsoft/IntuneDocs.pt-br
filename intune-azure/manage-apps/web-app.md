---
title: "Como adicionar aplicativos Web ao Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: aprenda a adicionar aplicativos Web ao Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4188957e263717d416853f308a50e3dbd7a9244a
ms.openlocfilehash: 4f8af0008300550d284957c1002be779e0e53f79

---

# <a name="how-to-add-web-apps-to-intune"></a>Como adicionar aplicativos Web ao Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Gerenciar aplicativos**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.
5. Acima da lista de aplicativos, escolha **Adicionar**.
6. Na folha **Adicionar Aplicativo**, escolha **Informações do Aplicativo**.
7. Na folha **Editar Aplicativo**, configure as seguintes informações. Ao terminar, clique em **Adicionar**:
    - **URL do aplicativo** – Insira a URL do site da web que hospeda o aplicativo que você deseja implantar.
    - **Nome do Aplicativo** – Insira o nome do aplicativo como ele será exibido no portal da empresa.
    - **Descrição do Aplicativo** – Insira uma descrição para o aplicativo. Isso será exibido para os usuários finais no portal da empresa.
    - **Editor** – insira o nome do editor do aplicativo.
    - **Categoria (opcional)** – Selecione uma das categorias de aplicativo internas ou uma categoria criada por você. Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.

    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **Requer um navegador gerenciado para abrir esse link** – Quando você implanta um link para um site ou aplicativo Web aos usuários, eles só poderão abri-lo no navegador gerenciado do Intune. Este navegador deve estar instalado em seu dispositivo.
    - **Carregar Ícone** – Carregue um ícone que será associado ao aplicativo. Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.
8. Após terminar, escolha **Salvar** na folha **Adicionar Aplicativo**.

O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](/intune-azure/manage-apps/deploy-apps).


<!--HONumber=Feb17_HO1-->


