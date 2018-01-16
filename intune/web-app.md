---
title: Como adicionar aplicativos Web ao Intune
titleSuffix: Azure portal
description: Saiba como adicionar aplicativos Web ao Intune.
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6da1441b16a43b5e22bedd9e87970f3388b11b9e
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/30/2017
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Como adicionar aplicativos Web ao Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Antes de gerenciar e atribuir um aplicativo para seus usuários, adicione-o ao Intune. O Intune dá suporte a vários tipos de aplicativo, incluindo aplicativos Web.

> [!Note]
> Não há suporte para aplicativos Web em dispositivos com Android for Work.

Conclua as etapas a seguir para adicionar um aplicativo ao Intune como atalho para um aplicativo na Web:

1. Entre no portal do Azure.
2. Usando **Mais recursos**, procure e selecione **Intune**.
3. Na folha **Microsoft Intune**, selecione **Aplicativos móveis**.
4. Na folha **Aplicativos móveis**, selecione **Aplicativos**.
5. Acima da lista de aplicativos, selecione **Adicionar**. A folha **Adicionar aplicativo** é exibida.
6. Na folha **Adicionar aplicativo**, selecione o tipo **Aplicativo Web** na lista suspensa **Tipo de aplicativo**.
7. Selecione a opção **Configurar** para exibir a folha **Informações do aplicativo**.
8. Na folha **Informações do aplicativo**, adicione as seguintes informações:
    - **Nome** – insira o nome do aplicativo como ele será exibido no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. Isso será exibido para os usuários finais no portal da empresa.
    - **Editor** – insira o nome do editor do aplicativo.
    - **URL do aplicativo** – insira a URL do site da web que hospeda o aplicativo que você deseja atribuir.
    - **Categoria (opcional)** – Selecione uma das categorias de aplicativo internas ou uma categoria criada por você. Essa seleção pode facilitar a localização do aplicativo quando os usuários navegarem pelo portal da empresa.
    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **Requer um navegador gerenciado para abrir esse link** – quando você atribui um link para um site ou aplicativo Web aos usuários, eles podem abri-lo no navegador gerenciado do Intune. Este navegador deve estar instalado em seu dispositivo.
    - **Logotipo** – carregue um logotipo que será associado ao aplicativo. Esse é o logotipo exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.
9. Quando você terminar, na folha **Adicionar informações**, selecione **Ok**.
10. Depois, na folha **Adicionar aplicativo**, selecione **Adicionar**.

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).