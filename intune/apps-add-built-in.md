---
title: "Adicionar aplicativos nativos a dispositivos móveis usando o Intune"
titlesuffix: Azure portal
description: "Saiba como usar o Intune para facilitar a instalação de aplicativos nativos em dispositivos móveis."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/13/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d622f2cb8c6b3e8c9aace4e805108ccfa71eb4d2
ms.sourcegitcommit: 754fcc31155b28d6910bba45419c6be745f8793e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2018
---
# <a name="how-to-add-built-in-apps-to-microsoft-intune"></a>Como adicionar aplicativos nativos ao Microsoft Intune

O tipo de aplicativo **nativo** facilita a atribuição de aplicativos gerenciados organizados, como aplicativos do Office 365, para dispositivos iOS e Android. Você pode atribuir aplicativos específicos para esse tipo de aplicativo, como Excel, OneDrive, Outlook, Skype e outros. Depois de adicionar um aplicativo, você verá o tipo de aplicativo como **Aplicativo iOS interno** ou **Aplicativo Android interno**. Ao usar o tipo de aplicativo nativo, você pode escolher qual desses aplicativos específicos publicar para os usuários do dispositivo.

 As edições anteriores do console do Intune forneciam vários aplicativos padrão gerenciados do Office 365, como Outlook e OneDrive. O tipo de aplicativo desses aplicativos gerenciados era marcado como "Aplicativo da iOS Store Gerenciado" ou "Aplicativo Android Gerenciado". Recomendamos que você use o tipo de aplicativo interno, em vez de "iOS Store Gerenciado" ou "Aplicativo Android Gerenciado". O tipo de aplicativo interno fornece flexibilidade adicional para editar e excluir aplicativos do Office 365.

>[!NOTE]
>Os aplicativos padrão do Office 365 marcados como "iOS Store Gerenciado" e "Aplicativo Android Gerenciado" são removidos da lista de aplicativos quando todas as atribuições são excluídas.

## <a name="add-built-in-app"></a>Adicionar aplicativo nativo

As etapas a seguir ajudam você a adicionar um aplicativo nativo a seus aplicativos disponíveis no Microsoft Intune.
1.  Entre no portal do Azure.
2.  Exiba a folha do Microsoft Intune, escolhendo **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3.  Na folha **Intune**, escolha **Aplicativos móveis**.
4.  Na folha **Aplicativos móveis**, escolha **Aplicativos** no grupo **Gerenciar**.
5.  Escolha **Adicionar** para adicionar um novo aplicativo.
6.  Na folha **Adicionar** aplicativo, escolha **Aplicativo nativo** na lista **Tipo de aplicativo**.
7.  Clique em **Selecionar aplicativo** para escolher os aplicativos nativos a serem incluídos.
8.  Na folha aplicativo nativo, selecione os aplicativos a serem incluídos.
9.  Na folha **Adicionar aplicativo**, clique em **Adicionar** para incluir os aplicativos.


## <a name="configure-app-information"></a>Configurar informações do aplicativo

Você pode modificar as informações sobre o aplicativo nativo. Essas informações ajudam a identificar o aplicativo no Intune, além de ajudar os usuários a encontrá-lo no aplicativo Portal da Empresa.
1.  Na folha **Aplicativos móveis – Aplicativos**, escolha o aplicativo nativo que você deseja modificar. Será exibida uma folha para o aplicativo nativo.
2.  Selecione a opção **Propriedades** no grupo **Gerenciar**.
3.  Selecione a opção **Configurar** para modificar as informações do aplicativo nativo.
4.  Na folha **Informações do aplicativo**, você pode modificar as seguintes informações:
    -   **Nome** – Insira o nome do aplicativo nativo como ele é exibido no portal da empresa. Certifique-se de que todos os nomes usados sejam exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    -   **Descrição**: insira uma descrição para o aplicativo. 
    -   **Editor**: insira o nome do editor do aplicativo.
    -   **Categoria** – De forma opcional, selecione uma ou mais das categorias de aplicativo nativo. A configuração dessa opção facilita a localização do aplicativo pelos usuários quando procurarem no portal da empresa.
    -   **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    -   **URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    -   **URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    -   **Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.
    -   **Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, Departamento de RH.
    -   **Observações** – Digite as observações que você deseja associar a este aplicativo.
    -   **Carregar Ícone** – carregue um ícone que será exibido com o aplicativo quando os usuários navegarem pelo Portal da Empresa.
3.  Ao terminar, clique em **OK** na folha **Informações do aplicativo**.
4.  Clique em **Salvar** na folha **Propriedades**.

## <a name="next-steps"></a>Próximas etapas

Agora você pode atribuir os aplicativos aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).
