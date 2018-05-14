---
title: Adicionar aplicativos da Android Store ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar aplicativos da Android Store ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 685ddf806bff865930de70b2d1925fb9b463b173
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="add-android-store-apps-to-microsoft-intune"></a>Adicionar aplicativos da Android Store ao Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Antes de atribuir um aplicativo em um dispositivo ou um grupo de usuários, você deve primeiro adicionar o aplicativo ao Microsoft Intune. É possível adicionar um aplicativo da Android Store ao Intune do Portal do Azure ao fazer o seguinte:

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**.  
    O Intune está localizado na seção **Monitoramento + Gerenciamento**.
1. No painel **Intune**, selecione **Aplicativos móveis**.
2. No painel de carga de trabalho **Aplicativos móveis**, em **Gerenciar**, selecione **Aplicativos**.
3. Selecione **Adicionar**.
4. No painel **Adicionar Aplicativo**, selecione **Android** nos tipos de **Aplicativos da loja** disponíveis.
5. Para configurar as informações do aplicativo, selecione **Configurar** e, em seguida, forneça as informações a seguir.  
    Dependendo do aplicativo escolhido, alguns dos valores podem ter sido preenchidos automaticamente.
    - **Nome**: insira o nome do aplicativo como ele será exibido no portal da empresa. Verifique se todos os nomes de aplicativo usados são exclusivos. Se um nome de aplicativo estiver duplicado, apenas um nome será exibido aos usuários no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. Essa descrição é exibida para usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **URL da loja de aplicativos**: insira a URL da loja de aplicativos do aplicativo que você deseja criar.
    - **Sistema operacional mínimo**: na lista, escolha a versão mais recente do sistema operacional em que o aplicativo pode ser instalado. Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.
    - **Categoria**: como opção, selecione uma ou mais das categorias de aplicativo internas ou uma categoria criada por você. Isso facilita a localização do aplicativo pelos usuários quando navegam pelo portal da empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: selecione esta opção para exibir o pacote de aplicativos de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações**: opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de Privacidade**: opcionalmente, insira a URL de um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, *Departamento de RH*.
    - **Observações**: como opção, insira as observações que você deseja associar a esse aplicativo.
    - **Logotipo**: opcionalmente, carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
1. Selecione **OK**.
2. Selecione **Adicionar**.

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que selecionar. 

## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos](apps-deploy.md)