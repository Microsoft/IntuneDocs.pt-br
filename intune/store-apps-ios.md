---
title: Adicionar aplicativos da loja do iOS ao Microsoft Intune
titlesuffix: ''
description: Saiba como adicionar aplicativos da iOS Store ao Microsoft Intune.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ac96c66dd6f09a7bd7a1b1c8c37f2f0eda24828c
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34223502"
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>Adicionar aplicativos da loja do iOS ao Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use as informações deste artigo para ajudá-lo a adicionar aplicativos da iOS Store ao Microsoft Intune. Aplicativos da loja do iOS são aplicativos instalados pelo Intune no dispositivo de um usuário. Um usuário faz parte da força de trabalho da sua empresa. Os aplicativos da iOS Store são atualizados automaticamente.

>[!NOTE]
>Embora os usuários de dispositivos iOS possam remover alguns aplicativos iOS internos, por exemplo, Ações e Mapas, você não pode usar o Intune para reimplantar esses aplicativos. Se os usuários excluírem esses aplicativos, eles deverão acessar a App Store e reinstalá-los manualmente.

## <a name="before-you-start"></a>Antes de iniciar

Você poderá atribuir aplicativos usando esse método apenas se eles forem gratuitos na App Store. Se você quiser atribuir aplicativos pagos usando o Intune, considere o uso do [programa de compra por volume do iOS](vpp-apps-ios.md).

>[!NOTE]
>Ao trabalhar com o Microsoft Intune, recomendamos que você use o Microsoft Edge ou o Google Chrome.

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**.  
    O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Aplicativos móveis**.
4. No painel de carga de trabalho **Aplicativos móveis**, em **Gerenciar**, selecione **Aplicativos**.
5. No painel **Aplicativos**, selecione **Adicionar**.
6. Na lista **Tipo de aplicativo**, em **Loja de aplicativos**, selecione **iOS**.
7. Selecione **Pesquisar na App Store**.
8. Na folha **Pesquisar na App Store**, selecione a localidade do país da App Store.
9. Na caixa **Pesquisar**, digite o nome (ou parte do nome) do aplicativo.  
    O Intune pesquisará na loja e retornará uma lista com resultados relevantes.
10. Na lista de resultados, selecione o aplicativo desejado e, em seguida, selecione **Selecionar**.
11. Na folha **Adicionar aplicativo**, selecione **Informações do aplicativo** para configurar o aplicativo.
12. No painel **Informações do aplicativo**, adicione as informações do aplicativo. Dependendo do aplicativo escolhido, alguns dos valores neste painel podem ter sido preenchidos automaticamente:
    - **Nome**: insira o nome do aplicativo como ele será exibido no portal da empresa. Verifique se todos os nomes de aplicativo usados são exclusivos. Se um nome de aplicativo estiver duplicado, apenas um nome será exibido aos usuários no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. Essa descrição é exibida para usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **URL da loja de aplicativos**: digite a URL da loja de aplicativos do aplicativo que você deseja criar.
    - **Sistema operacional mínimo**: na lista, escolha a versão mais recente do sistema operacional em que o aplicativo pode ser instalado. Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.
    - **Tipo de dispositivo aplicável**: na lista, selecione os dispositivos que são usados pelo aplicativo.
    - **Categoria**: como opção, selecione uma ou mais das categorias de aplicativo internas ou uma categoria criada por você. Isso facilita a localização do aplicativo pelos usuários quando navegam pelo portal da empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: selecione esta opção para exibir o pacote de aplicativos de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações**: opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de Privacidade**: opcionalmente, insira a URL de um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: opcionalmente, insira o nome do desenvolvedor do aplicativo. Este campo estará visível somente para administradores, e não para os usuários.
    - **Proprietário**: opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, *Departamento de RH*. Este campo estará visível somente para administradores, e não para os usuários.
    - **Observações**: como opção, insira as observações que você deseja associar a esse aplicativo. Esse campo só é visível para administradores, e não para usuários finais.
    - **Logotipo**: opcionalmente, carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
13. Selecione **OK**.
14. Selecione **Adicionar**.

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que selecionar.

## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos](apps-deploy.md)
