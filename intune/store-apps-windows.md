---
title: Adicionar aplicativos da Microsoft Store ao Microsoft Intune
titleSuffix: ''
description: Aprenda a adicionar aplicativos da Microsoft Store (Windows Store) ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d8784d560d37068fd4559a2e67ecf35044ee498e
ms.sourcegitcommit: 63b74a60aafa8d2d6af0594448ae0471fbd79194
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2018
ms.locfileid: "46494040"
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Adicionar aplicativos da Microsoft Store ao Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Antes que possa atribuir, monitorar, configurar ou proteger aplicativos, você precisa adicioná-los ao Intune. 

## <a name="add-an-app-to-intune"></a>Adicionar um aplicativo ao Intune
Você pode adicionar um aplicativo da Microsoft Store ao Intune, fazendo o seguinte:

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**.  
    O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Aplicativos clientes**.
4. No painel da carga de trabalho **Aplicativos clientes**, em **Gerenciar**, selecione **Aplicativos**.
5. No painel **Aplicativos**, selecione **Adicionar**.
6. No painel **Adicionar aplicativo**, selecione um **Tipo de aplicativo** do **Windows** e selecione **Informações do aplicativo**.
7. No painel **Informações do aplicativo**, adicione as informações do aplicativo. Dependendo do aplicativo escolhido, alguns dos valores neste painel podem ter sido preenchidos automaticamente:
    - **Nome**: insira o nome do aplicativo como ele será exibido no portal da empresa. Verifique se todos os nomes de aplicativo usados são exclusivos. Se um nome de aplicativo estiver duplicado, apenas um nome será exibido aos usuários no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. Essa descrição é exibida para usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **URL da loja de aplicativos**: digite a URL da loja de aplicativos do aplicativo que você deseja criar.
    - **Categoria**: como opção, selecione uma ou mais das categorias de aplicativo internas ou uma categoria criada por você. Isso facilita a localização do aplicativo pelos usuários quando navegam pelo portal da empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: selecione esta opção para exibir o pacote de aplicativos de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações**: opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de Privacidade**: opcionalmente, insira a URL de um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, *Departamento de RH*.
    - **Observações**: como opção, insira as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: opcionalmente, carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
8. Selecione **OK**.
9. Selecione **Adicionar**.

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que selecionar. 

## <a name="next-steps"></a>Próximas etapas
- [Atribuir aplicativos a grupos](apps-deploy.md)
