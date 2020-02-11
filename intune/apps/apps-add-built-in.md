---
title: Adicionar aplicativos nativos a dispositivos móveis usando o Microsoft Intune
titleSuffix: ''
description: Saiba como usar o Intune para facilitar a instalação de aplicativos nativos em dispositivos móveis.
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
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e299601f69a7052ea52f9da2537306cb8556982b
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755367"
---
# <a name="add-built-in-apps-to-microsoft-intune"></a>Adicionar aplicativos nativos ao Microsoft Intune

O tipo de aplicativo *nativo* facilita a atribuição de aplicativos gerenciados organizados, como aplicativos do Office 365, para dispositivos iOS e Android. Você pode atribuir aplicativos específicos para esse tipo de aplicativo, como Excel, OneDrive, Outlook, Skype e outros. Depois de adicionar um aplicativo e o tipo de aplicativo for exibido como *Aplicativo iOS interno* ou *Aplicativo Android interno*. Ao usar o tipo de aplicativo nativo, você pode escolher qual desses aplicativos publicar para os usuários do dispositivo.

As versões anteriores do console do Intune forneciam vários aplicativos padrão gerenciados do Office 365, como Outlook e OneDrive. Os tipos de aplicativo desses aplicativos gerenciados era marcado como *Aplicativo da iOS Store Gerenciado* ou *Aplicativo Android Gerenciado*. Em vez de usar esses tipos de aplicativo, recomendamos usar o tipo de aplicativo interno. Ao usar tipo de aplicativo interno, você terá a flexibilidade adicional para editar e excluir aplicativos do Office 365.

>[!NOTE]
>Os aplicativos padrão do Office 365 marcados como *iOS Store Gerenciado* e *Aplicativo Android Gerenciado* são removidos da lista de aplicativos quando todas as atribuições são excluídas.

## <a name="add-a-built-in-app"></a>Adicionar um aplicativo nativo

Para adicionar um aplicativo nativo a seus aplicativos disponíveis no Microsoft Intune, faça o seguinte:
1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. No painel **Selecionar tipo de aplicativo**, nos tipos de **Aplicativos da loja** disponíveis, selecione **Aplicativo interno**.
4. Clique em **Selecionar**. As etapas de **Adicionar aplicativo** são exibidas.
5. Na página **Selecionar aplicativos internos**, clique em **Selecionar aplicativos** para selecionar os aplicativos que você deseja incluir.
6. Selecione os aplicativos internos que você deseja incluir. 
7. Depois de selecionar os aplicativos, clique em **Selecionar** no painel **Selecionar aplicativos internos**.
8. Clique em **Avançar** para exibir a página **Marcas de escopo**.
9. Clique em **Selecionar marcas de escopo** para adicionar opcionalmente marcas de escopo no aplicativo. Para saber mais, confira [Usar o RBAC (controle de acesso baseado em função) e marcas de escopo para TI distribuída](~/fundamentals/scope-tags.md).
10. Clique em **Avançar** para exibir a página **Atribuições**.
11. Selecione as atribuições de grupo para o aplicativo. Para saber mais, confira [Adicionar grupos para organizar usuários e dispositivos](~/fundamentals/groups-add.md). 
12. Clique em **Avançar** para exibir a página **Revisar + criar**. Examine os valores e as configurações que você inseriu para o aplicativo.
13. Quando terminar, clique em **Criar** para adicionar o aplicativo ao Intune.

    A folha **Visão geral** do aplicativo criado é exibida.

## <a name="configure-app-information"></a>Configurar informações do aplicativo

Você pode modificar as informações sobre o aplicativo nativo. Essas informações ajudam a identificar o aplicativo no Intune e ajudar os usuários a encontrá-lo no aplicativo Portal da Empresa.
1. Selecione **Aplicativos** > **Todos os aplicativos** e escolha o aplicativo nativo que você deseja modificar.  
   Será exibido um painel para o aplicativo nativo.
2. Selecione **Propriedades**.
3. Selecione **Editar** ao lado de **Informações do aplicativo**.
4. No painel **Informações do aplicativo**, você pode modificar as seguintes informações:
    - **Nome**: insira o nome do aplicativo interno como ele é exibido no portal da empresa. Certifique-se de que todos os nomes usados sejam exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição**: Insira uma descrição para o aplicativo. 
    - **Editor**: Insira o nome do editor do aplicativo.
    - **Categoria**: ou selecione uma ou mais categorias do aplicativo interno. A configuração dessa opção facilita a localização do aplicativo pelos usuários quando procurarem no portal da empresa.
    - **Mostrar como um aplicativo em destaque no portal da empresa**: Exiba o aplicativo de maneira proeminente em na página principal do portal da empresa quando os usuários procurarem por aplicativos.
    - **URL de Informações**: Opcionalmente, insira uma URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de privacidade**: Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor**: Opcionalmente, Insira o nome do desenvolvedor do aplicativo.
    - **Proprietário**: ou insira um nome para o proprietário desse aplicativo (por exemplo, *Departamento de RH*).
    - **Observações**: Insira as observações que você deseja associar a esse aplicativo.
    - **Ícone Carregar**: carregue um ícone que será exibido com o aplicativo quando os usuários procurarem no portal da empresa.
5. Clique em **Revisar + salvar** para exibir a página **Revisar + criar**. Examine os valores e as configurações que você inseriu para o aplicativo.
13. Quando terminar, clique em **Salvar** para atualizar o aplicativo no Intune.

    A folha **Visão geral** do aplicativo criado é exibida.

## <a name="next-steps"></a>Próximas etapas

- Agora você pode atribuir os aplicativos aos grupos que você escolher. Para saber mais, confira [Atribuir aplicativos a grupos](apps-deploy.md).
