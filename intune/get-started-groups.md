---
title: "Introdução aos grupos"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 04843a918a3c661ab69dfa711f4d22a8feedf5f3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# Introdução aos grupos
<a id="get-started-with-groups" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[](./media/generic-users-groups.png)

O Microsoft Intune usa o Azure AD (Azure Active Directory) para [gerenciar o acesso aos recursos da empresa](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups). Esse acesso é controlado usando as funções no diretório. O Intune gerencia então esse acesso para dispositivos móveis, que permite que os membros desse grupo acessem os recursos.

__Como eu crio um grupo?__

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Usando **Pesquisar recursos**, pesquise **Usuários e grupos**.
3. Depois de abrir a folha **Usuários e grupos**, selecione **Todos os grupos**.
4. Na folha **Usuários e grupos – Todos os Grupos**, selecione o comando **Novo grupo**.
5. Na folha **Grupo**, adicione um **Nome** e uma **Descrição** para o grupo.
6. Defina o **Tipo de associação** como **Atribuído**. Não **Habilite os recursos do Office** para o grupo de teste.
7. Clique em **Criar**.

Se um grupo foi criado com êxito, ele deverá aparecer na lista de **Todos os grupos**. Se ele não aparecer, tente criar um outro grupo.
