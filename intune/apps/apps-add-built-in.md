---
title: Adicionar aplicativos nativos a dispositivos móveis usando o Microsoft Intune
titleSuffix: ''
description: Saiba como usar o Intune para facilitar a instalação de aplicativos nativos em dispositivos móveis.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2a94542311bc5ff4a25b2f9c6229898b1d891c6c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725303"
---
# <a name="add-built-in-apps-to-microsoft-intune"></a>Adicionar aplicativos nativos ao Microsoft Intune

O tipo de aplicativo *nativo* facilita a atribuição de aplicativos gerenciados organizados, como aplicativos do Office 365, para dispositivos iOS e Android. Você pode atribuir aplicativos específicos para esse tipo de aplicativo, como Excel, OneDrive, Outlook, Skype e outros. Depois de adicionar um aplicativo e o tipo de aplicativo for exibido como *Aplicativo iOS interno* ou *Aplicativo Android interno*. Ao usar o tipo de aplicativo nativo, você pode escolher qual desses aplicativos publicar para os usuários do dispositivo.

As versões anteriores do console do Intune forneciam vários aplicativos padrão gerenciados do Office 365, como Outlook e OneDrive. Os tipos de aplicativo desses aplicativos gerenciados era marcado como *Aplicativo da iOS Store Gerenciado* ou *Aplicativo Android Gerenciado*. Em vez de usar esses tipos de aplicativo, recomendamos usar o tipo de aplicativo interno. Ao usar tipo de aplicativo interno, você terá a flexibilidade adicional para editar e excluir aplicativos do Office 365.

>[!NOTE]
>Os aplicativos padrão do Office 365 marcados como *iOS Store Gerenciado* e *Aplicativo Android Gerenciado* são removidos da lista de aplicativos quando todas as atribuições são excluídas.

## <a name="add-a-built-in-app"></a>Adicionar um aplicativo nativo

Para adicionar um aplicativo nativo a seus aplicativos disponíveis no Microsoft Intune, faça o seguinte:
1. Entre no Portal do Azure.
2. Para exibir o painel do Microsoft Intune, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. No painel **Intune**, selecione **Aplicativos clientes**.
4. No painel **Aplicativos clientes**, em **Gerenciar**, selecione **Aplicativos**.
5. Selecione **Adicionar**.
6. No painel do aplicativo **Adicionar**, na lista **Tipo de aplicativo**, selecione **Aplicativo interno**.
7. Escolha **Selecionar aplicativo**.
8. No painel **Aplicativo interno**, selecione os aplicativos que você deseja incluir.
9. No painel **Adicionar aplicativo**, selecione **Adicionar**.


## <a name="configure-app-information"></a>Configurar informações do aplicativo

Você pode modificar as informações sobre o aplicativo nativo. Essas informações ajudam a identificar o aplicativo no Intune e ajudar os usuários a encontrá-lo no aplicativo Portal da Empresa.
1. No painel **Aplicativos Cliente – Aplicativos**, selecione o aplicativo nativo que você deseja modificar.  
    Será exibido um painel para o aplicativo nativo.
2. Em **Gerenciar**, selecione a opção **Propriedades**.
3. Para modificar as informações do aplicativo nativo, selecione a opção **Configurar**.
4. No painel **Informações do aplicativo**, você pode modificar as seguintes informações:
    - **Nome**: insira o nome do aplicativo interno como ele é exibido no portal da empresa. Certifique-se de que todos os nomes usados sejam exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição**: Insira uma descrição para o aplicativo. 
    - **Editor**: Insira o nome do editor do aplicativo.
    - **Categoria**: ou selecione uma ou mais categorias do aplicativo interno. A configuração dessa opção facilita a localização do aplicativo pelos usuários quando procurarem no portal da empresa.
    - **Exibir isso como um aplicativo em destaque no portal da empresa**: Exiba o aplicativo de maneira proeminente em na página principal do portal da empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: Opcionalmente, insira uma URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de privacidade**: Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: Opcionalmente, Insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: ou insira um nome para o proprietário desse aplicativo (por exemplo, *Departamento de RH*).
    - **Observações**: Insira as observações que você deseja associar a esse aplicativo.
    - **Ícone Carregar**: carregue um ícone que será exibido com o aplicativo quando os usuários procurarem no portal da empresa.
4. Selecione **OK**.
5. No painel **Propriedades**, selecione **Salvar**.

## <a name="next-steps"></a>Próximas etapas

- Agora você pode atribuir os aplicativos aos grupos que você escolher. Para saber mais, confira [Atribuir aplicativos a grupos](apps-deploy.md).
