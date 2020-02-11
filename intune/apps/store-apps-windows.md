---
title: Adicionar aplicativos da Microsoft Store ao Microsoft Intune
titleSuffix: ''
description: Aprenda a adicionar aplicativos da Microsoft Store (Windows Store) ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8743af2a05f6daebca5e1394ba5b7b8f13fcf7e3
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754891"
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Adicionar aplicativos da Microsoft Store ao Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Antes que possa atribuir, monitorar, configurar ou proteger aplicativos, você precisa adicioná-los ao Intune. 

## <a name="add-an-app-to-intune"></a>Adicionar um aplicativo ao Intune
Você pode adicionar um aplicativo da Microsoft Store ao Intune, fazendo o seguinte:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. No painel **Selecionar tipo de aplicativo**, nos tipos de **Aplicativos da loja** disponíveis, selecione **Aplicativo da Windows Store**.
4. Clique em **Selecionar**. As etapas de **Adicionar aplicativo** são exibidas.
5. Para configurar as **Informações do aplicativo** para aplicativos da Windows Store, navegue até a [Microsoft Store](https://www.microsoft.com/store/apps) e pesquise o aplicativo que você deseja implantar. Exiba a página do aplicativo e anote os detalhes sobre ele. 
6. No painel **Informações do aplicativo**, adicione os detalhes do aplicativo:
    - **Nome**: Insira o nome do aplicativo como ele será exibido no Portal da Empresa. Verifique se todos os nomes de aplicativo usados são exclusivos. Se um nome de aplicativo estiver duplicado, apenas um nome será exibido aos usuários no portal da empresa.
    - **Descrição**: Insira uma descrição para o aplicativo. Essa descrição é exibida para usuários no portal da empresa.
    - **Editor**: Insira o nome do editor do aplicativo.
    - **URL da loja de aplicativos**: Digite a URL da loja de aplicativos do aplicativo que você deseja criar. A URL pode ser encontrada, pesquisando-se na [Microsoft Store](https://www.microsoft.com/store/apps) em busca do aplicativo desejado. Use a URL da barra de endereços do navegador.
    - **Categoria**: Como opção, selecione uma ou mais categorias de aplicativo internas ou uma categoria criada por você. Isso facilita a localização do aplicativo pelos usuários quando navegam pelo portal da empresa.
    - **Mostrar como um aplicativo em destaque no Portal da Empresa**: Selecione essa opção para destacar o pacote de aplicativos na página principal do Portal da Empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: Opcionalmente, insira uma URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de privacidade**: Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: Opcionalmente, Insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, *Departamento de RH*.
    - **Observações**: Opcionalmente, insira as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: Opcionalmente, carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
7. Clique em **Avançar** para exibir a página **Marcas de escopo**.
8. Clique em **Selecionar marcas de escopo** para adicionar opcionalmente marcas de escopo no aplicativo. Para saber mais, confira [Usar o RBAC (controle de acesso baseado em função) e marcas de escopo para TI distribuída](~/fundamentals/scope-tags.md).
9. Clique em **Avançar** para exibir a página **Atribuições**.
10. Selecione as atribuições de grupo para o aplicativo. Para saber mais, confira [Adicionar grupos para organizar usuários e dispositivos](~/fundamentals/groups-add.md). 
11. Clique em **Avançar** para exibir a página **Revisar + criar**. Examine os valores e as configurações que você inseriu para o aplicativo.
12. Quando terminar, clique em **Criar** para adicionar o aplicativo ao Intune.

A folha **Visão geral** do aplicativo criado é exibida.

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que selecionar.

> [!IMPORTANT]
> Aplicativos da Microsoft Store só podem ser atribuídos a grupos com o tipo de atribuição **Disponível para dispositivos registrados** (usuários instalam o aplicativo no site ou aplicativo do Portal da Empresa).

## <a name="next-steps"></a>Próximas etapas
- [Atribuir aplicativos a grupos](apps-deploy.md)
