---
title: Validar sua configuração de política de proteção de aplicativo
titleSuffix: Microsoft Intune
description: Saiba como testar se a política de proteção de aplicativo está configurada e funcionando corretamente.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 01/23/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6ea79a2e177b8a4e85454140c7efb9172defe5b6
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31834026"
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>Como validar sua configuração de política de proteção de aplicativo

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Verifique se a política de proteção de aplicativo está funcionando e configurada corretamente. Estas diretrizes se aplicam às políticas de proteção de aplicativo no portal do Azure.

### <a name="checking-for-symptoms"></a>Verificar sintomas
Não é provável que os usuários relatem problemas, pois a proteção de aplicativo é uma ferramenta de proteção de dados. Se houver um problema com a configuração da proteção de aplicativo, o usuário terá acesso irrestrito, como teria sem a proteção de aplicativo e não saberá que há um problema. Por esse motivo, é recomendável que você valide a configuração de proteção de aplicativo realizando um piloto das políticas de proteção de aplicativo com um pequeno grupo de usuários que podem testar deliberadamente as restrições de proteção de aplicativo.


### <a name="what-to-check"></a>O que verificar

Se o teste mostrar que o comportamento da política de proteção de aplicativo não funciona como o esperado, é recomendável que você verifique esses itens:

- Os usuários estão licenciados para a proteção de aplicativo?
- Os usuários estão licenciados para o O365?
- O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**.

#### <a name="user-app-protection-status"></a>Status de proteção de aplicativo do usuário
1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
1. Escolha **Gerenciar aplicativos** > **Monitorar** >  **Status da proteção do aplicativo** > **Usuários atribuídos**.

2. Escolha um usuário na lista, ou pesquise e selecione um usuário e, em seguida, escolha **Selecionar usuário**. Na parte superior da coluna **Relatórios de aplicativo**, é possível ver se o usuário está licenciado para a proteção de aplicativo. Você também pode ver se o usuário está licenciado para o O365 e o status do aplicativo para todos os dispositivos do usuário.



### <a name="what-to-do"></a>O que fazer
Aqui estão as ações necessárias com base no status do usuário:

- Se o usuário não está licenciado para proteção de aplicativo, atribua uma licença do Intune ao usuário.
- Se o usuário não está licenciado para o O365, obtenha uma licença para o usuário.
- Se um aplicativo do usuário estiver listado como **Não submetido a check-in**, verifique se você configurou corretamente uma política de proteção de aplicativo para esse aplicativo.
- Verifique se essas condições são aplicadas a todos os usuários aos quais você deseja que as políticas de proteção de aplicativo sejam aplicadas.

### <a name="see-also"></a>Consulte também

[O que é a política de proteção de aplicativo do Intune?](app-protection-policies.md)
