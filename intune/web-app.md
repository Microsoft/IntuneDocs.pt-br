---
title: Como adicionar aplicativos Web ao Microsoft Intune
titleSuffix: 
description: Saiba como adicionar aplicativos Web ao Microsoft Intune.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ecb44f8b98501f6c82f91994cd8a06b8177208d7
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Como adicionar aplicativos Web ao Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Intune dá suporte a vários tipos de aplicativo, incluindo aplicativos Web. Um aplicativo Web é um aplicativo cliente-servidor. O servidor fornece o aplicativo Web, que inclui a interface do usuário, o conteúdo e a funcionalidade. Além disso, plataformas modernas de hospedagem na Web geralmente oferecem segurança, balanceamento de carga e outros benefícios. Este aplicativo Web é mantido separadamente na Web. Use o Microsoft Intune para apontar para esse tipo de aplicativo. Além disso, você atribui quais grupos de usuários podem acessar o aplicativo. 

Antes de gerenciar e atribuir um aplicativo para seus usuários, adicione-o ao Intune. O Intune cria um atalho para o aplicativo Web na tela inicial do dispositivo do usuário.

> [!Note]
> Não há suporte para aplicativos Web em dispositivos com Android for Work e macOS.

Conclua as etapas a seguir para adicionar um aplicativo ao Intune como atalho para um aplicativo na Web:

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Microsoft Intune**, selecione **Aplicativos móveis**.
4. No painel **Aplicativos móveis**, selecione **Aplicativos**.
5. Acima da lista de aplicativos, selecione **Adicionar**. O painel **Adicionar aplicativo** é exibido.
6. No painel **Adicionar aplicativo**, selecione o tipo **Link da Web** na lista suspensa **Tipo de aplicativo**.
7. Selecione a opção **Configurar** para exibir o painel **Informações do aplicativo**.
8. No painel **Informações do aplicativo**, adicione as seguintes informações:
    - **Nome** – insira o nome do aplicativo como ele será exibido no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. Isso será exibido para os usuários finais no portal da empresa.
    - **Editor** – insira o nome do editor do aplicativo.
    - **URL do aplicativo** – insira a URL do site da web que hospeda o aplicativo que você deseja atribuir.
    - **Categoria (opcional)** – Selecione uma das categorias de aplicativo internas ou uma categoria criada por você. Essa seleção pode facilitar a localização do aplicativo quando os usuários navegarem pelo portal da empresa.
    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **Requer um navegador gerenciado para abrir esse link** – quando você atribui um link para um site ou aplicativo Web aos usuários, eles podem abri-lo no navegador gerenciado do Intune. Este navegador deve estar instalado em seu dispositivo.
    - **Logotipo** – carregue um logotipo que será associado ao aplicativo. Esse é o logotipo exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.
9. Após terminar, no painel **Adicionar informações**, selecione **Ok**.
10. Em seguida, no painel **Adicionar aplicativo**, selecione **Adicionar**.

> [!Note]
> Os usuários precisam adicionar o widget do Intune à tela inicial para exibir os aplicativos Web que foram atribuídos aos dispositivos Android.

## <a name="next-steps"></a>Próximas etapas

- O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).