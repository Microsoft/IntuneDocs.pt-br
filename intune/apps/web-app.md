---
title: Adicionar aplicativos Web ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar aplicativos Web (aplicativos de cliente-servidor) ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
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
ms.openlocfilehash: e018fb9888db19995556a6671d93a1db5fa78c2a
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415439"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Adicionar aplicativos Web ao Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Intune é compatível com vários tipos de aplicativos, incluindo aplicativos Web. Um aplicativo Web é um aplicativo cliente-servidor. O servidor fornece o aplicativo Web, que inclui a interface do usuário, o conteúdo e a funcionalidade. Além disso, plataformas modernas de hospedagem na Web geralmente oferecem segurança, balanceamento de carga e outros benefícios. Um aplicativo Web é mantido separadamente na Web. Use o Microsoft Intune para apontar para esse tipo de aplicativo. Você também atribui quais grupos de usuários podem acessar esse aplicativo. 

Antes de gerenciar e atribuir um aplicativo para seus usuários, adicione-o ao Intune. 

O Intune cria um atalho para o aplicativo Web no dispositivo do usuário. Em dispositivos iOS/iPadOS, um atalho para o aplicativo Web é adicionado à tela inicial. Em dispositivos do administrador de dispositivos Android, um atalho para o aplicativo Web é adicionado ao widget do portal da empresa do Intune, e o widget precisa ser fixado manualmente pelo usuário. Em dispositivos Windows, um atalho para o aplicativo Web é adicionado ao Menu Iniciar.

> [!Note]
> O dispositivo do usuário deve ter um navegador instalado para inicialização de aplicativos Web. 

> [!Note]
> Em Atribuir dispositivos Android Enterprise, confira [Links do Google Play Gerenciado](apps-add-android-for-work.md#managed-google-play-web-links)

## <a name="add-a-web-app-to-intune"></a>Adicionar um aplicativo Web ao Intune
Para adicionar um aplicativo ao Intune como atalho para um aplicativo na Web, faça o seguinte:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. No painel **Selecionar tipo de aplicativo**, sob **Outros** tipos disponíveis, selecione **Link da Web**.
4. Clique em **Selecionar**. As etapas de **Adicionar aplicativo** são exibidas.
5. Na página **Informações do aplicativo**, adicione as seguintes informações:
    - **Nome**:  Insira o nome do aplicativo como ele será exibido no Portal da Empresa. 

        > [!NOTE]
        > Se você alterar o nome do aplicativo por meio do portal do Azure do Intune depois de ter implantado e instalado o aplicativo, o aplicativo não poderá mais ser direcionado usando comandos.

    - **Descrição**: Insira uma descrição para o aplicativo. Essa descrição é exibida para usuários no portal da empresa.
    - **Editor**: Insira o nome do editor desse aplicativo.
    - **URL do Aplicativo**: Insira a URL do site da web que hospeda o aplicativo que você deseja atribuir.
    - **Categoria**: Como opção, selecione uma ou mais categorias de aplicativo internas ou uma categoria criada por você. Isso facilita a localização do aplicativo pelos usuários quando navegam pelo portal da empresa.
    - **Mostrar como um aplicativo em destaque no Portal da Empresa**: Selecione essa opção para destacar o pacote de aplicativos na página principal do Portal da Empresa quando os usuários procurarem por aplicativos.
    - **É necessário usar um managed browser para abrir este link**: Selecione essa opção para atribuir a seus usuários um link para um site ou aplicativo Web que eles possam abrir no navegador gerenciado do Intune. Este navegador deve estar instalado em seu dispositivo.
    - **Logotipo**: Carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
6. Clique em **Avançar** para exibir a página **Marcas de escopo**.
7. Clique em **Selecionar marcas de escopo** para adicionar opcionalmente marcas de escopo no aplicativo. Confira mais informações em [Usar o RBAC (controle de acesso baseado em função) e marcas de escopo para TI distribuída](~/fundamentals/scope-tags.md).
8. Clique em **Avançar** para exibir a página **Atribuições**.
9. Selecione as atribuições de grupo para o aplicativo. Para saber mais, confira [Adicionar grupos para organizar usuários e dispositivos](~/fundamentals/groups-add.md). 
10. Clique em **Avançar** para exibir a página **Revisar + criar**. Examine os valores e as configurações que você inseriu para o aplicativo.
11. Ao terminar, clique em **Criar** para adicionar o aplicativo ao Intune.

    A folha **Visão geral** do aplicativo criado é exibida.

> [!Note]
> Atualmente, a implantação de aplicativos Web do Intune para dispositivos iOS/iPadOS está associada ao perfil de gerenciamento e não pode ser removida manualmente. Você pode alterar o tipo de implantação para **Desinstalar** no portal do Intune para que o aplicativo Web possa ser removido automaticamente. No entanto, se você remover a implantação antes de alterar a intenção de atribuição de aplicativo para **Desinstalar**, o aplicativo Web ficará permanentemente em vigor no dispositivo até que o registro do dispositivo seja cancelado no Intune.

Os usuários finais podem iniciar aplicativos Web diretamente do aplicativo do Portal da Empresa para Windows selecionando o aplicativo Web e escolhendo a opção **Abrir no navegador**. A URL da Web publicada é aberta diretamente no navegador da Web. 

## <a name="next-steps"></a>Próximas etapas

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que selecionar. Para obter ajuda, veja [Atribuir aplicativos aos grupos](apps-deploy.md). 
