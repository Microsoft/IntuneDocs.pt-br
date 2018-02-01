---
title: Como adicionar aplicativos da loja do iOS ao Intune | Microsoft Docs
titlesuffix: Azure portal
description: Saiba como adicionar aplicativos da loja do iOS ao Intune.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e013b5c995274365978ee0c2ba2f45bfeef54baa
ms.sourcegitcommit: b982f9d50da4f958fb0c48c56ba46c8ef71500c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Como adicionar aplicativos da iOS Store ao Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Use as informações neste tópico para ajudá-lo a adicionar aplicativos da iOS store ao Intune.

>[!NOTE]
>Embora os usuários de dispositivos iOS possam remover alguns dos aplicativos iOS internos, por exemplo, Ações e Mapas, você não pode usar o Intune para reimplantar esses aplicativos. Se os usuários finais excluírem esses aplicativos, eles deverão ir para a loja de aplicativos e reinstalá-los manualmente.

## <a name="before-you-start"></a>Antes de começar

Você só poderá atribuir aplicativos usando este método se eles forem gratuitos na App Store. Se você quiser atribuir aplicativos pagos usando o Intune, considere o uso do [programa de compra por volume do iOS](vpp-apps-ios.md).

>[!NOTE]
>O Chrome e o Edge são os navegadores recomendados para trabalhar com o Microsoft Intune.

## <a name="step-1---search-for-the-app-in-the-store"></a>Etapa 1 – Pesquise o aplicativo na loja

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Gerenciar aplicativos**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > Aplicativos.
5. Acima da lista de aplicativos, escolha **Adicionar**.
6. Na folha **Adicionar Aplicativo**, escolha **Pesquisar na Loja de Aplicativos**.
7. Na folha **Apple App Store**, selecione a localidade do país da loja de aplicativos.
8. Na caixa de pesquisa, digite o nome (ou parte do nome). O Intune pesquisará na loja e retornará uma lista de resultados relevantes.
9. Na lista, escolha o aplicativo que desejar e clique em **OK**.

## <a name="step-2---configure-app-information"></a>Etapa 2 – Configurar informações de aplicativo

1. Na folha **Adicionar Aplicativo**, escolha **Informações do Aplicativo**.
2. Na folha **Editar Aplicativo**, configure as informações do aplicativo. Ao terminar, clique em **Adicionar**. Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:
- **Nome** – digite o nome do aplicativo que será exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para os usuários no portal da empresa.
- **Descrição** – digite uma descrição para o aplicativo que será exibida aos usuários no portal da empresa.
- **Editor** – digite o nome do editor do aplicativo.
- **URL da loja de aplicativos** – digite a URL da loja de aplicativos do aplicativo que você deseja criar.
- **País/região da loja** – selecione a localidade do país da loja de aplicativos.
- **Sistema operacional mínimo** – na lista, escolha a versão mínima do sistema operacional em que o aplicativo pode ser instalado. O aplicativo não será instalado em um dispositivo com um sistema operacional anterior.
- **Tipo de dispositivo aplicável** – na lista, escolha os dispositivos que são usados pelo aplicativo.
- **Categoria** (opcional). Selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você. As categorias facilitam para os usuários a localização do aplicativo ao navegar no portal da empresa.
- **Exibir como um aplicativo em destaque no Portal da Empresa** – exiba o aplicativo em destaque na página principal do portal da empresa quando os usuários procurarem por aplicativos.
- **URL de informações** – opcionalmente, digite a URL de um site que contenha informações sobre este aplicativo. A URL é exibida para os usuários no portal da empresa.
- **URL de Privacidade** – opcionalmente, digite a URL de um site que contenha as informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
- **Desenvolvedor** – opcionalmente, digite o nome do desenvolvedor do aplicativo. Esse campo só é visível para administradores, e não para usuários finais.
- **Proprietário** – Opcionalmente, digite um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.  Esse campo só é visível para administradores, e não para usuários finais.
- **Observações** – digite as observações que você deseja associar a este aplicativo. Esse campo só é visível para administradores, e não para usuários finais.
- **Logotipo** – carregue um ícone que será associado ao aplicativo. Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.
3. Quando você terminar, na folha **Adicionar Aplicativo**, escolha **OK**.

O aplicativo que você criou aparece na lista de aplicativos, de onde ele poderá ser atribuído aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).
