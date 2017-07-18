---
title: "Como adicionar aplicativos de linha de negócios do Windows Phone ao Intune"
titleSuffix: Intune on Azure
description: "Saiba como adicionar aplicativos de linha de negócios do Windows Phone ao Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f27ad720556a866b5f2a9326df0a574cc37f2a5d
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2017
---
# <a name="how-to-add-windows-phone-line-of-business-lob-apps-to-microsoft-intune"></a>Como adicionar aplicativos de linha de negócios (LOB) do Windows Phone para o Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Etapa 1 – Especificar os arquivos de instalação de software

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Gerenciar aplicativos**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.
5. Acima da lista de aplicativos, escolha **Adicionar**.
6. Na folha **Adicionar Aplicativo**, escolha **Aplicativo de linha de negócios**.

## <a name="step-2---configure-the-app-package-file"></a>Etapa 2 - configurar o arquivo de pacote de aplicativos

1. Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.
2. Na folha do arquivo **Pacote do aplicativo**, escolha o botão Procurar e selecione um arquivo de instalação do Windows Phone com a extensão **.xap**.
3. Quando terminar, escolha **OK**.


## <a name="step-3---configure-app-information"></a>Etapa 3 - configurar informações do aplicativo

1. Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.
2. Na folha **informações do aplicativo**, configure as informações do aplicativo. Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:
    - **Nome** – insira o nome do aplicativo como ele é exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. A descrição é exibida para usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **Categoria** - selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você. O uso de categorias facilita a localização do aplicativo pelos usuários quando eles navegam pelo portal da empresa.
    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.
    - **Observações** – Digite as observações que você deseja associar a este aplicativo.
    - **Logotipo** – carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
3. Quando terminar, escolha **OK**.

## <a name="step-4---finish-up"></a>Etapa 4 - conclusão

1. Na folha **Adicionar aplicativo**, verifique se você configurou as informações corretamente.
2. Escolha **Adicionar** para carregar o aplicativo no Intune.

## <a name="next-steps"></a>Próximas etapas

O aplicativo que você criou será exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).
