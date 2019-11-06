---
title: Adicionar aplicativos Web ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar aplicativos Web (aplicativos de cliente-servidor) ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6600c75ce3e6120143b17fb863670b2eb423a09f
ms.sourcegitcommit: ae6f2e7812e7fd36f2393b8f4b6cd8de63777b2c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73592049"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Adicionar aplicativos Web ao Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Intune é compatível com vários tipos de aplicativos, incluindo aplicativos Web. Um aplicativo Web é um aplicativo cliente-servidor. O servidor fornece o aplicativo Web, que inclui a interface do usuário, o conteúdo e a funcionalidade. Além disso, plataformas modernas de hospedagem na Web geralmente oferecem segurança, balanceamento de carga e outros benefícios. Um aplicativo Web é mantido separadamente na Web. Use o Microsoft Intune para apontar para esse tipo de aplicativo. Você também atribui quais grupos de usuários podem acessar esse aplicativo. 

Antes de gerenciar e atribuir um aplicativo para seus usuários, adicione-o ao Intune. 

O Intune cria um atalho para o aplicativo Web no dispositivo do usuário. Em dispositivos iOS, um atalho para o aplicativo Web é adicionado à tela inicial. Em dispositivos Android, um atalho para o aplicativo Web é adicionado ao widget do portal da empresa do Intune, e o widget precisa ser fixado manualmente pelo usuário. Em dispositivos Windows, um atalho para o aplicativo Web é adicionado ao Menu Iniciar.

> [!Note]
> O dispositivo do usuário deve ter um navegador instalado para inicialização de aplicativos Web.

## <a name="add-a-web-app-to-intune"></a>Adicionar um aplicativo Web ao Intune
Para adicionar um aplicativo ao Intune como atalho para um aplicativo na Web, faça o seguinte:

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel **Intune**, selecione **Aplicativos clientes**.
4. No painel da carga de trabalho **Aplicativos clientes**, em **Gerenciar**, selecione **Aplicativos**.
5. No painel **Aplicativos**, selecione **Adicionar**.
6. No painel **Adicionar aplicativo**, selecione o tipo **Link da Web** na lista suspensa **Tipo de aplicativo**.
7. Selecione **Configurar**.
8. No painel **Informações do aplicativo**, adicione as seguintes informações:
    - **Nome**:  Insira o nome do aplicativo como ele será exibido no Portal da Empresa. 

        > [!NOTE]
        > Se você alterar o nome do aplicativo por meio do portal do Azure do Intune depois de ter implantado e instalado o aplicativo, o aplicativo não poderá mais ser direcionado usando comandos.

    - **Descrição**: Insira uma descrição para o aplicativo. Essa descrição é exibida para usuários no portal da empresa.
    - **Editor**: Insira o nome do editor desse aplicativo.
    - **URL do Aplicativo**: Insira a URL do site da web que hospeda o aplicativo que você deseja atribuir.
    - **Categoria**: Como opção, selecione uma ou mais categorias de aplicativo internas ou uma categoria criada por você. Isso facilita a localização do aplicativo pelos usuários quando navegam pelo portal da empresa.
    - **Exibir isso como um aplicativo em destaque no Portal da Empresa**: Selecione essa opção para destacar o pacote de aplicativos na página principal do Portal da Empresa quando os usuários procurarem por aplicativos.
    - **É necessário usar um managed browser para abrir este link**: Selecione essa opção para atribuir a seus usuários um link para um site ou aplicativo Web que eles possam abrir no navegador gerenciado do Intune. Este navegador deve estar instalado em seu dispositivo.
    - **Logotipo**: Carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
9. Selecione **OK**.
10. No painel **Adicionar aplicativo**, selecione **Adicionar**.

> [!Note]
> Os usuários devem adicionar o widget do Intune à tela inicial para exibir os aplicativos Web que foram atribuídos aos dispositivos Android.
>
> Atualmente, a implantação de aplicativos Web do Intune para dispositivos iOS está associada ao perfil de gerenciamento e não pode ser removida manualmente. Você pode alterar o tipo de implantação para **Desinstalar** no portal do Intune para que o aplicativo Web possa ser removido automaticamente. No entanto, se você remover a implantação antes de alterar a intenção de atribuição de aplicativo para **Desinstalar**, o aplicativo Web ficará permanentemente em vigor no dispositivo até que o registro do dispositivo seja cancelado no Intune.

## <a name="next-steps"></a>Próximas etapas

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que selecionar. Para obter ajuda, veja [Atribuir aplicativos aos grupos](apps-deploy.md). 
