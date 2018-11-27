---
title: Validar sua configuração de política de proteção de aplicativo
titleSuffix: Microsoft Intune
description: Saiba como testar se a política de proteção de aplicativo está configurada e funcionando corretamente.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2018
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9f6d5bc8c124e3ba26b7e3fc110510c7d5e0e6a3
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52183155"
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>Como validar sua configuração de política de proteção de aplicativo

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Verifique se a política de proteção de aplicativo está funcionando e configurada corretamente. Estas diretrizes se aplicam às políticas de proteção de aplicativo no portal do Azure.

### <a name="checking-for-symptoms"></a>Verificar sintomas
Não é provável que os usuários relatem problemas, pois a proteção de aplicativo é uma ferramenta de proteção de dados. Se houver algum problema com a configuração da proteção de aplicativo, o usuário terá acesso irrestrito, como teria sem a proteção de aplicativo, e não saberá que há um problema. Por esse motivo, é recomendável que você valide a configuração de proteção de aplicativo, realizando um piloto das políticas de proteção de aplicativo com um pequeno grupo de usuários que podem testar deliberadamente as restrições de proteção de aplicativo.


### <a name="what-to-check"></a>O que verificar

Se o teste mostrar que o comportamento da política de proteção de aplicativo não funciona como o esperado, verifique estes itens:

- Os usuários estão licenciados para a proteção de aplicativo?
- Os usuários estão licenciados para o O365?
- O status de cada um dos aplicativos de proteção de aplicativo dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**.

#### <a name="user-app-protection-status"></a>Status de proteção de aplicativo do usuário
1. Entre no [portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Selecione **Aplicativos cliente** > **Monitor** >  **Status de proteção do aplicativo** e escolha o bloco **Usuários atribuídos**. 
4. Na página **Relatório do aplicativo**, escolha **Selecionar usuário** para exibir uma lista de usuários e grupos. 
5. Pesquise e selecione um usuário na lista e depois escolha **Selecionar usuário**. Na parte superior do painel **Relatórios de aplicativo**, é possível ver se o usuário tem a licença da proteção de aplicativo. Você também pode ver se o usuário tem a licença do O365 e o status dos aplicativos de todos os dispositivos do usuário.



### <a name="what-to-do"></a>O que fazer
Aqui estão as ações necessárias com base no status do usuário:

- Se o usuário não tiver a licença da proteção de aplicativo, atribua uma licença do Intune ao usuário.
- Se o usuário não tiver a licença do O365, obtenha uma licença para o usuário.
- Se um aplicativo do usuário estiver listado como **Não submetido a check-in**, verifique se você configurou corretamente uma política de proteção de aplicativo para esse aplicativo.
- Verifique se essas condições se aplicam a todos os usuários para os quais você deseja que as políticas de proteção de aplicativo sejam aplicadas.

### <a name="see-also"></a>Consulte também

[O que é a política de proteção de aplicativo do Intune?](app-protection-policies.md)
