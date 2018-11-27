---
title: Adicionar aplicativos Web ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar aplicativos Web ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: ace65aab5ded1449b1e1fd092936e9e2a019f6c1
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187626"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Adicionar aplicativos Web ao Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Intune é compatível com vários tipos de aplicativos, incluindo aplicativos Web. Um aplicativo Web é um aplicativo cliente-servidor. O servidor fornece o aplicativo Web, que inclui a interface do usuário, o conteúdo e a funcionalidade. Além disso, plataformas modernas de hospedagem na Web geralmente oferecem segurança, balanceamento de carga e outros benefícios. Um aplicativo Web é mantido separadamente na Web. Use o Microsoft Intune para apontar para esse tipo de aplicativo. Você também atribui quais grupos de usuários podem acessar esse aplicativo. 

Antes de gerenciar e atribuir um aplicativo para seus usuários, adicione-o ao Intune. O Intune cria um atalho para o aplicativo Web na tela inicial do dispositivo do usuário.

> [!Note]
> Não há suporte para aplicativos Web nos dispositivos de perfil de trabalho Android e no macOS.

## <a name="add-a-web-app-to-intune"></a>Adicionar um aplicativo Web ao Intune
Para adicionar um aplicativo ao Intune como atalho para um aplicativo na Web, faça o seguinte:

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**.  
    O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Aplicativos clientes**.
4. No painel da carga de trabalho **Aplicativos clientes**, em **Gerenciar**, selecione **Aplicativos**.
5. No painel **Aplicativos**, selecione **Adicionar**.
6. No painel **Adicionar aplicativo**, selecione o tipo **Link da Web** na lista suspensa **Tipo de aplicativo**.
7. Selecione **Configurar**.
8. No painel **Informações do aplicativo**, adicione as seguintes informações:
    - **Nome**: insira o nome do aplicativo como ele será exibido no portal da empresa. 
    
        > [!NOTE]
        > Se você alterar o nome do aplicativo por meio do portal do Azure do Intune depois de ter implantado e instalado o aplicativo, o aplicativo não poderá mais ser direcionado usando comandos.
    
    - **Descrição**: insira uma descrição para o aplicativo. Essa descrição é exibida para usuários no portal da empresa.
    - **Editor**: insira o nome do editor desse aplicativo.
    - **URL do aplicativo**: insira a URL do site da web que hospeda o aplicativo que você deseja atribuir.
    - **Categoria**: como opção, selecione uma ou mais das categorias de aplicativo internas ou uma categoria criada por você. Isso facilita a localização do aplicativo pelos usuários quando navegam pelo portal da empresa.
    - **Exibir como um aplicativo em destaque no Portal da Empresa**: selecione esta opção para exibir o pacote de aplicativos de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **Requer um navegador gerenciado para abrir esse link**: selecione essa opção para atribuir a seus usuários um link para um site ou aplicativo Web que eles possam abrir no navegador gerenciado do Intune. Este navegador deve estar instalado em seu dispositivo.
    - **Logotipo**: carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
9. Selecione **OK**.
10. No painel **Adicionar aplicativo**, selecione **Adicionar**.

> [!Note]
> Os usuários devem adicionar o widget do Intune à tela inicial para exibir os aplicativos Web que foram atribuídos aos dispositivos Android.
>
> Atualmente, a implantação de aplicativos Web do Intune para dispositivos iOS está associada ao perfil de gerenciamento e não pode ser removida manualmente. Você pode alterar o tipo de implantação para **Desinstalar** no portal do Intune para que o aplicativo Web possa ser removido automaticamente. No entanto, se você remover a implantação antes de alterar a intenção de atribuição de aplicativo para **Desinstalar**, o aplicativo Web ficará permanentemente em vigor no dispositivo até que o registro do dispositivo seja cancelado no Intune.

## <a name="next-steps"></a>Próximas etapas

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que selecionar. Para obter ajuda, veja [Atribuir aplicativos aos grupos](apps-deploy.md). 
