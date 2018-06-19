---
title: Criar um grupo no Microsoft Intune
titleSuffix: ''
description: Organize usuários em grupos para facilitar o gerenciamento das políticas e dos aplicativos que eles possam acessar.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d039cfe5509990ff15fe8a1cb476ad44037d60df
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31021006"
---
# <a name="create-a-group-to-manage-your-users-and-data-access"></a>Criar um grupo para gerenciar usuários e acesso a dados

Os grupos são usados para gerenciar os usuários e controlar o acesso dos funcionários aos recursos da empresa. Esses recursos podem fazer parte de seu diretório ou podem ser recursos externos, como aplicativos SaaS ou sites do SharePoint.

O Microsoft Intune usa o Azure AD (Azure Active Directory) para gerenciar o acesso aos recursos da empresa. Esse acesso é controlado usando as funções no diretório. O Intune gerencia então esse acesso para dispositivos móveis, que permite que os membros desse grupo acessem os recursos.

## <a name="how-do-i-create-a-group"></a>Como fazer para criar um grupo?

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Depois de abrir o painel **Microsoft Intune**, selecione **Grupos**.
4. No painel **Usuários e grupos – Todos os grupos**, selecione o comando **Novo grupo**.
5. No painel **Grupo**, escolha um **Tipo de grupo**.
5. Adicione um **Nome** e uma **Descrição** para o grupo.
6. Defina o **Tipo de associação** como **Atribuído**. Não **Habilite os recursos do Office** para o grupo de teste.
7. Selecione **Membros** para o grupo.
7. Clique em **Criar**.

Se um grupo foi criado com êxito, ele deverá aparecer na lista de **Todos os grupos**. Se ele não aparecer, tente criar um outro grupo.

## <a name="next-steps"></a>Próximas etapas

[Introdução às políticas](get-started-policies.md) – crie políticas para impedir que os usuários executem ações não autorizadas com seus dispositivos.

## <a name="learn-more"></a>Saiba mais

* [Definir restrições de registro usando grupos no Intune](groups-add.md)
* [Gerenciar o acesso aos recursos da empresa usando grupos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
