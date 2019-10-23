---
title: Validar sua configuração de política de proteção de aplicativo
titleSuffix: Microsoft Intune
description: Saiba como testar se a política de proteção do aplicativo está configurada e funcionando corretamente no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 455f717e0e8ca4337cfef8693d5b71a0902b103f
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72499227"
---
# <a name="how-to-validate-your-app-protection-policy-setup-in-microsoft-intune"></a>Como validar sua configuração da política de proteção do aplicativo no Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Verifique se a política de proteção de aplicativo está funcionando e configurada corretamente. Estas diretrizes se aplicam às políticas de proteção de aplicativo no portal do Azure.

## <a name="checking-for-symptoms"></a>Verificar sintomas
Não é provável que os usuários relatem problemas, pois a proteção de aplicativo é uma ferramenta de proteção de dados. Se houver algum problema com a configuração da proteção de aplicativo, o usuário terá acesso irrestrito, como teria sem a proteção de aplicativo, e não saberá que há um problema. Por esse motivo, é recomendável que você valide a configuração de proteção de aplicativo, realizando um piloto das políticas de proteção de aplicativo com um pequeno grupo de usuários que podem testar deliberadamente as restrições de proteção de aplicativo.

## <a name="what-to-check"></a>O que verificar

Se o teste mostrar que o comportamento da política de proteção do aplicativo não funciona como esperado, verifique estes itens:

- Os usuários estão licenciados para a proteção de aplicativo?
- Os usuários estão licenciados para o O365?
- O status de cada um dos aplicativos de proteção de aplicativo dos usuários está como esperado? Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**.

### <a name="user-app-protection-status"></a>Status de proteção de aplicativo do usuário
1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Escolha **Aplicativos do cliente** >  **Status de proteção do aplicativo** e escolha o bloco **Usuários atribuídos**. 
4. Na página **Relatório do aplicativo**, escolha **Selecionar usuário** para exibir uma lista de usuários e grupos. 
5. Pesquise e selecione um usuário na lista e depois escolha **Selecionar usuário**. Na parte superior do painel **Relatórios de aplicativo**, é possível ver se o usuário tem a licença da proteção de aplicativo. Você também pode ver se o usuário tem a licença do O365 e o status dos aplicativos de todos os dispositivos do usuário.

## <a name="what-to-do"></a>O que fazer
Aqui estão as ações necessárias com base no status do usuário:

- Se o usuário não tem a licença da proteção de aplicativo, atribua uma [licença do Intune](../fundamentals/licenses.md) a ele.
- Se o usuário não tem a licença do O365, obtenha uma [licença](../fundamentals/licenses.md) para ele.
- Se um aplicativo do usuário está listado como **Não verificado**, veja se você configurou corretamente uma [política de proteção do aplicativo](app-protection-policies-validate.md) para esse aplicativo.
- Verifique se essas condições se aplicam a todos os usuários para os quais você deseja que as [políticas de proteção do aplicativo](app-protection-policies-monitor.md) sejam válidas.

## <a name="see-also"></a>Consulte também

- [O que é a política de proteção de aplicativo do Intune?](app-protection-policies.md)
- [Licenças que incluem o Intune](../fundamentals/licenses.md)
- [Atribuir licenças aos usuários para que possam registrar dispositivos no Intune](../fundamentals/licenses-assign.md)
- [Como validar sua configuração de política de proteção do aplicativo](app-protection-policies-validate.md)
- [Como monitorar as políticas de proteção do aplicativo](app-protection-policies-monitor.md)

