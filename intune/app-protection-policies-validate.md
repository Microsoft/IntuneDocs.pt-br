---
title: "Validar políticas de proteção do aplicativo"
titleSuffix: Azure portal
description: "Este tópico descreve como você pode testar e validar se a política de proteção de aplicativo está configurada corretamente e funcionando conforme esperado."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angerobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0c97fbbffa416dce6b9aa8f56ecda7c265f377db
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>Como validar sua configuração de política de proteção de aplicativo

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Este tópico fornece informações sobre a verificação de problemas depois que você configura a política de proteção de aplicativo. Estas diretrizes se aplicam às políticas de proteção de aplicativo no portal do Azure.

### <a name="checking-for-symptoms"></a>Verificar sintomas
Não é provável que os usuários relatem problemas, pois a proteção de aplicativo é uma ferramenta de proteção de dados. Se houver um problema com a configuração de proteção de aplicativo, o usuário terá acesso irrestrito, como teria sem a proteção de aplicativo, e não estará ciente de que há um problema. Por esse motivo, é recomendável que você valide sua configuração de proteção de aplicativo realizando um piloto de suas políticas de proteção de aplicativo com um pequeno grupo de usuários que podem testar deliberadamente as restrições de proteção de aplicativo.


### <a name="what-to-check"></a>O que verificar

Se o teste mostra que o comportamento da política de proteção de aplicativo não é esperado, é recomendável que você verifique o seguinte:

- Os usuários estão licenciados para a proteção de aplicativo?
- Os usuários estão licenciados para o O365?
- O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**.

#### <a name="user-app-protection-status"></a>Status de proteção de aplicativo do usuário
1. No Portal do Azure, escolha **Gerenciar aplicativos** > **Monitorar** >  **Status de usuário de proteção do aplicativo** > **Usuários**.

2. Escolha um usuário na lista ou procure e escolha um usuário e escolha **Selecionar usuário**. Na parte superior da coluna **Relatórios de aplicativo**, você verá se o usuário está licenciado para proteção de aplicativo. Abaixo disso, você verá se o usuário está licenciado para o O365 e o status do aplicativo para todos os dispositivos do usuário.



### <a name="what-to-do"></a>O que fazer
Aqui estão as ações necessárias com base no status do usuário:

- Se o usuário não está licenciado para proteção de aplicativo, atribua uma licença do Intune ao usuário.
- Se o usuário não está licenciado para o O365, obtenha uma licença para o usuário.
- Se o aplicativo do usuário é listado como **Não submetido a check-in**, verifique se você configurou corretamente uma política de proteção de aplicativo para o aplicativo.
- Verifique se essas condições são aplicadas a todos os usuários aos quais você deseja que as políticas de proteção de aplicativo sejam aplicadas.

### <a name="see-also"></a>Consulte também

[O que é a política de proteção de aplicativo do Intune?](app-protection-policies.md)
