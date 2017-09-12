---
title: Como adicionar aplicativos da loja do iOS ao Intune
titlesuffix: Azure portal
description: Saiba como adicionar aplicativos da loja do iOS ao Intune.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 53ff149b28a2f75a3b30c59fa5f30edcf4879fae
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Como adicionar aplicativos da iOS Store ao Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Use as informações neste tópico para ajudá-lo a adicionar aplicativos da iOS store ao Intune.

>[!NOTE]
>Embora os usuários de dispositivos iOS possam remover alguns dos aplicativos iOS internos, por exemplo, Ações e Mapas, você não pode usar o Intune para reimplantar esses aplicativos. Se os usuários finais excluírem esses aplicativos, eles deverão ir para a loja de aplicativos e reinstalá-los manualmente.

## <a name="before-you-start"></a>Antes de começar

Você só poderá atribuir aplicativos usando este método se eles forem gratuitos na App Store. Se você quiser atribuir aplicativos pagos usando o Intune, considere o uso do [programa de compra por volume do iOS](vpp-apps-ios.md).


## <a name="step-1---search-for-the-app-in-the-store"></a>Etapa 1 – Pesquise o aplicativo na loja

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Gerenciar aplicativos**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > Aplicativos.
5. Acima da lista de aplicativos, escolha **Adicionar**.
6. Na folha **Adicionar Aplicativo**, escolha **Pesquisar na Loja de Aplicativos**.
7. Na folha **Apple App Store**, digite o nome (ou parte do nome) na caixa de pesquisa. O Intune pesquisará na loja e retornará uma lista de resultados relevantes.
8. Na lista, escolha o aplicativo que desejar e clique em **OK**.

## <a name="step-2---configure-app-information"></a>Etapa 2 – Configurar informações de aplicativo

1. Na folha **Adicionar Aplicativo**, escolha **Informações do Aplicativo**.
2. Na folha **Editar Aplicativo**, configure as seguintes informações. Ao terminar, clique em **Adicionar**. Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:
- **Nome do Aplicativo** – Insira o nome do aplicativo como ele será exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição do Aplicativo** – Insira uma descrição para o aplicativo. Isso será exibido para os usuários no portal da empresa.
- **Editor**: insira o nome do editor do aplicativo.
- **URL da loja de aplicativos** – Insira a URL da loja de aplicativos do aplicativo que você deseja criar.
- **Sistema Operacional Mínimo** – Na lista, escolha a versão mínima do sistema operacional no qual o aplicativo pode ser instalado. Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.
- **Categoria** (opcional). Selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você. Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.

- **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
- **URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL será exibida para os usuários no portal da empresa.
- **URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL será exibida para os usuários no portal da empresa.
- **Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.
- **Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.
- **Observações** – Digite as observações que você deseja associar a este aplicativo.
- **Carregar Ícone** – Carregue um ícone que será associado ao aplicativo. Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.
3. Após terminar, escolha **Salvar** na folha **Adicionar Aplicativo**.

O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).
