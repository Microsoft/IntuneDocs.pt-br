---
title: Como adicionar aplicativos da Android Store ao Intune
titleSuffix: Azure portal
description: Saiba como adicionar aplicativos da loja do Android ao Intune.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/13/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cdf00d8adc5a854f90b59c6066d6f0ab7c6ae94a
ms.sourcegitcommit: 754fcc31155b28d6910bba45419c6be745f8793e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2018
---
# <a name="how-to-add-android-store-apps-to-microsoft-intune"></a>Como adicionar aplicativos Android Store ao Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Antes de atribuir um aplicativo em um dispositivo ou um grupo de usuários, você deve primeiro adicionar o aplicativo ao Microsoft Intune. As etapas a seguir permitem que você adicione um aplicativo da Android Store ao Intune do Portal do Azure.

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Microsoft Intune**, escolha **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Aplicativos** na seção **Gerenciar**.
5. Acima da lista de aplicativos, escolha **Adicionar**.
6. Na folha **Adicionar Aplicativo**, selecione **Android** nos tipos de **Aplicativo da loja** disponíveis.
7. Selecione **Configurar** para configurar as seguintes informações do aplicativo: dependendo do aplicativo escolhido, alguns dos valores nesta folha podem ter sido preenchidos automaticamente:
    - **Nome**: insira o nome do aplicativo como ele será exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. Essa descrição será exibida para os usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **URL da loja de aplicativos** – insira a URL da loja de aplicativos do aplicativo que você deseja criar.
    - **Sistema operacional mínimo** – na lista, escolha a versão mínima do sistema operacional em que o aplicativo pode ser instalado. Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.
    - **Categoria** (opcional) – Selecione uma das categorias de aplicativo internas ou uma categoria criada por você. Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.

    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações** (opcional) – insira a URL de um site que contém informações sobre esse aplicativo. A URL será exibida para os usuários no portal da empresa.
    - **URL privada** (opcional) – insira a URL para um site que contém informações de privacidade desse aplicativo. A URL será exibida para os usuários no portal da empresa.
    - **Desenvolvedor** (opcional) – insira o nome do desenvolvedor do aplicativo.
    - **Proprietário** (opcional) – insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.
    - **Observações** (opcional) – insira as observações que você deseja associar a este aplicativo.
    - **Logotipo** (opcional) – carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
8. Clique em **OK** quando concluir a configuração de informações do aplicativo.
9. Clique em **Adicionar** para adicionar o aplicativo.

O aplicativo que você criou é exibido na lista de aplicativos, na qual poderá atribuí-lo aos grupos que escolher. 

##<a name="next-steps"></a>Próximas etapas

- [Como atribuir aplicativos aos grupos](apps-deploy.md)