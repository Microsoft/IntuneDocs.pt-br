---
title: Adicionar aplicativos da loja do iOS ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar aplicativos da iOS Store ao Microsoft Intune. Você poderá atribuir aplicativos usando este método se eles forem gratuitos na App Store.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c5616b27b97d5623958ec872390e2a6de79db3c5
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563444"
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>Adicionar aplicativos da loja do iOS ao Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Use as informações deste artigo para ajudá-lo a adicionar aplicativos da iOS Store ao Microsoft Intune. Aplicativos da loja do iOS são aplicativos instalados pelo Intune no dispositivo de um usuário. Um usuário faz parte da força de trabalho da sua empresa. Os aplicativos da iOS Store são atualizados automaticamente.

>[!NOTE]
>Embora os usuários de dispositivos iOS possam remover alguns aplicativos iOS internos, por exemplo, Ações e Mapas, você não pode usar o Intune para reimplantar esses aplicativos. Se os usuários excluírem esses aplicativos, eles deverão acessar a App Store e reinstalá-los manualmente.

## <a name="before-you-start"></a>Antes de começar

Você poderá atribuir aplicativos usando esse método apenas se eles forem gratuitos na App Store. Se você quiser atribuir aplicativos pagos usando o Intune, considere o uso do [programa de compra por volume do iOS](vpp-apps-ios.md).

>[!NOTE]
>Ao trabalhar com o Microsoft Intune, recomendamos que você use o Microsoft Edge ou o Google Chrome.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. Na lista **Tipo de aplicativo**, em **Loja de aplicativos**, selecione **iOS**.
4. Selecione **Pesquisar na App Store**.
5. No painel **Pesquisar na App Store**, escolha a localidade do país/região da App Store.
6. Na caixa **Pesquisar**, digite o nome (ou parte do nome) do aplicativo.  
    O Intune pesquisará na loja e retornará uma lista com resultados relevantes.
7. Na lista de resultados, selecione o aplicativo desejado e, em seguida, selecione **Selecionar**.
8. Na folha **Adicionar aplicativo**, selecione **Informações do aplicativo** para configurar o aplicativo.
9. No painel **Informações do aplicativo**, adicione as informações do aplicativo. Dependendo do aplicativo escolhido, alguns dos valores neste painel podem ter sido preenchidos automaticamente:
    - **Nome**: Insira o nome do aplicativo como ele será exibido no Portal da Empresa. Verifique se todos os nomes de aplicativo usados são exclusivos. Se um nome de aplicativo estiver duplicado, apenas um nome será exibido aos usuários no portal da empresa.
    - **Descrição**: Insira uma descrição para o aplicativo. Essa descrição é exibida para usuários no portal da empresa.
    - **Editor**: Insira o nome do editor do aplicativo.
    - **URL da loja de aplicativos**: Digite a URL da loja de aplicativos do aplicativo que você deseja criar.
    - **Sistema operacional mínimo**: Na lista, escolha a versão mais recente do sistema operacional em que o aplicativo pode ser instalado. Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.
    - **Tipo de dispositivo aplicável**: Na lista, selecione os dispositivos que são usados pelo aplicativo.
    - **Categoria**: Como opção, selecione uma ou mais categorias de aplicativo internas ou uma categoria criada por você. Isso facilita a localização do aplicativo pelos usuários quando navegam pelo portal da empresa.
    - **Exibir isso como um aplicativo em destaque no Portal da Empresa**: Selecione essa opção para destacar o pacote de aplicativos na página principal do Portal da Empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: Opcionalmente, insira uma URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de privacidade**: Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: Opcionalmente, insira o nome do desenvolvedor do aplicativo. Este campo estará visível somente para administradores, e não para os usuários.
    - **Proprietários**: Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, *Departamento de RH*. Este campo estará visível somente para administradores, e não para os usuários.
    - **Observações**: Opcionalmente, insira as observações que você deseja associar a esse aplicativo. Esse campo só é visível para administradores, e não para usuários finais.
    - **Logotipo**: Opcionalmente, carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
10. Selecione **OK**.
11. Selecione **Adicionar**.

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que selecionar.

## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos](apps-deploy.md)
