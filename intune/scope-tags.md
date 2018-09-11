---
title: Filtrar políticas com marcas de escopo no Microsoft Intune – Azure | Microsoft Docs
description: Use marcas de escopo para filtrar os perfis de configuração para funções específicas.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 000505df3c0898ed0939244dfe1b075c64097611
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329420"
---
# <a name="use-scope-tags-to-filter-policies"></a>Usar marcas de escopo para filtrar políticas

As marcas de escopo permitem filtrar as políticas com marcas personalizadas criadas por você.

Por exemplo, crie uma marca de escopo chamada "Departamento de engenharia" e atribua-a aos perfis de configuração relacionados ao departamento de engenharia. Atribua essa mesma marca a uma função de "Administradores de engenharia". Eles verão somente as políticas com a marca "Departamento de engenharia".

## <a name="to-create-a-scope-tag"></a>Para criar uma marca de escopo

Escolha **Funções** > **Escopo (marcas)** > **Criar**.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Para adicionar uma marca de escopo a um perfil de configuração

Escolha **Configuração do dispositivo** > **Perfis** > escolha um perfil > **Propriedades** > **Escopo (Marcas)**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Para atribuir uma marca de escopo a uma função

Escolha **Funções** > **Todas as funções** > **Gerenciador de Política e Perfil** > **Atribuições** > **Escopo (Marcas)**.

## <a name="next-steps"></a>Próximas etapas

Gerencie suas [funções](role-based-access-control.md) e seus [perfis](device-profile-assign.md).

