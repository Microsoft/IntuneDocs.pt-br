---
title: "Validar suas políticas de proteção de aplicativo | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Azure Intune: este tópico descreve como você pode testar e validar se a política de proteção de aplicativo está configurada corretamente e funcionando conforme o esperado."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angerobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: e0d5b4b0c3557c1d8158f9e0ea6e33c426dba925


---

# <a name="how-to-validate-your-app-protection-policy-setup"></a>Como validar sua configuração de política de proteção de aplicativo

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Este tópico fornece informações sobre a verificação de problemas depois que você configura a política de proteção de aplicativo. Estas diretrizes se aplicam às políticas de proteção de aplicativo na **versão prévia** do Portal do Azure.

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



<!--HONumber=Feb17_HO1-->


