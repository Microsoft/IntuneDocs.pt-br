---
title: "Introdução aos grupos"
titleSuffix: Azure portal
description: "Organize usuários em grupos para facilitar o gerenciamento das políticas e dos aplicativos que eles possam acessar."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 705f57eca339f0f70cda9e7db60d33436d8198e7
ms.sourcegitcommit: fa6aaf12611c3e03e38e467806fc30b1d0255e88
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2017
---
# <a name="get-started-with-groups"></a>Introdução aos grupos

Os grupos são usados para gerenciar os usuários e controlar o acesso dos funcionários aos recursos da empresa. Esses recursos podem fazer parte de seu diretório ou podem ser recursos externos, como aplicativos SaaS ou sites do SharePoint.

O Microsoft Intune usa o Azure AD (Azure Active Directory) para gerenciar o acesso aos recursos da empresa. Esse acesso é controlado usando as funções no diretório. O Intune gerencia então esse acesso para dispositivos móveis, que permite que os membros desse grupo acessem os recursos.

## <a name="how-do-i-create-a-group"></a>Como fazer para criar um grupo?

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Usando **Pesquisar recursos**, pesquise **Intune**.
3. Depois de abrir a folha **Microsoft Intune**, selecione **Grupos**.
4. Na folha **Usuários e grupos – Todos os Grupos**, selecione o comando **Novo grupo**.
5. Na folha **Grupo**, adicione um **Nome** e uma **Descrição** para o grupo.
6. Defina o **Tipo de associação** como **Atribuído**. Não **Habilite os recursos do Office** para o grupo de teste.
7. Clique em **Criar**.

Se um grupo foi criado com êxito, ele deverá aparecer na lista de **Todos os grupos**. Se ele não aparecer, tente criar um outro grupo.

## <a name="next-steps"></a>Próximas etapas

[Introdução às políticas](get-started-policies.md) – crie políticas para impedir que os usuários executem ações não autorizadas com seus dispositivos.

## <a name="learn-more"></a>Saiba mais

* [Definir restrições de registro usando grupos no Intune](groups-add.md)
* [Gerenciar o acesso aos recursos da empresa usando grupos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
