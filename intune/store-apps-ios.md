---
title: Como adicionar aplicativos da iOS Store ao Microsoft Intune
titlesuffix: 
description: Saiba como adicionar aplicativos da iOS Store ao Microsoft Intune.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b5315d683abfc38a7f42d2f322cc77c625270e3c
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Como adicionar aplicativos da iOS Store ao Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Use as informações deste artigo para ajudá-lo a adicionar aplicativos da iOS Store ao Microsoft Intune. Aplicativos da iOS Store são aplicativos que o Intune instala no dispositivo de um usuário. O usuário é colaborador da sua empresa. Os aplicativos da iOS Store são atualizados automaticamente. 

>[!NOTE]
>Embora os usuários de dispositivos iOS possam remover alguns dos aplicativos iOS internos, por exemplo, Ações e Mapas, você não pode usar o Intune para reimplantar esses aplicativos. Se os usuários finais excluírem esses aplicativos, eles deverão acessar a loja de aplicativos e reinstalá-los manualmente.

## <a name="before-you-start"></a>Antes de começar

Você só poderá atribuir aplicativos usando este método se eles forem gratuitos na App Store. Se você quiser atribuir aplicativos pagos usando o Intune, considere o uso do [programa de compra por volume do iOS](vpp-apps-ios.md).

>[!NOTE]
>O Chrome e o Edge são os navegadores recomendados para trabalhar com o Microsoft Intune.

## <a name="step-1---search-for-the-app-in-the-store"></a>Etapa 1 – Pesquise o aplicativo na loja

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Aplicativos** na seção **Gerenciar**.
5. Escolha **Adicionar** no lado direito do painel **Aplicativos**.
6. Na lista **Tipo de aplicativo**, selecione **iOS** nos tipos disponíveis de **aplicativos da Loja**.
6. Escolha **Pesquisar na Loja de Aplicativos**.
7. Na folha **Pesquisar na Loja de Aplicativos**, selecione a localidade do país da loja de aplicativos.
8. Na caixa de pesquisa, digite o nome (ou parte do nome). O Intune pesquisará na loja e retornará uma lista de resultados relevantes.
9. Na lista, escolha o aplicativo e clique em **Selecionar**.

## <a name="step-2---configure-app-information"></a>Etapa 2 – Configurar informações de aplicativo

1. Na folha **Adicionar aplicativo**, escolha **Informações do Aplicativo** para configurar o aplicativo.
2. Na folha **Informações do aplicativo**, adicione as informações do aplicativo. Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:
- **Nome** – digite o nome do aplicativo que será exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para os usuários no portal da empresa.
- **Descrição** – digite uma descrição para o aplicativo que será exibida aos usuários no portal da empresa.
- **Editor** – digite o nome do editor do aplicativo.
- **URL da loja de aplicativos** – digite a URL da loja de aplicativos do aplicativo que você deseja criar.
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
3. Ao terminar, clique em **OK** na folha **Adicionar informações**.
4. Clique em **Adicionar**, na folha **Adicionar aplicativo**. 

O aplicativo que você criou aparece na lista de aplicativos, de onde ele poderá ser atribuído aos grupos que você escolher. 

## <a name="next-steps"></a>Próximas etapas

- [Como atribuir aplicativos aos grupos](apps-deploy.md)
