---
title: "Validar a configuração do MAM | Microsoft Docs"
description: "Este tópico descreve como você pode testar e validar se a política de MAM está configurada corretamente e funcionando conforme o esperado."
keywords: 
author: andredm7
ms.author: andredm
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d6ff74f0b46baf384dbdedf13ad75538dd33a089
ms.openlocfilehash: 080d8f4fd4b6e1b53df860f4319b1c199d504c06


---

# <a name="validating-your-mobile-application-management-setup"></a>Validar a configuração do gerenciamento de aplicativo móvel

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico fornece informações sobre a verificação de problemas depois que você configura o MAM (gerenciamento de aplicativos móveis). Esta orientação se aplica a políticas de MAM no Portal do Azure.

### <a name="checking-for-symptoms"></a>Verificar sintomas
Não é provável que os usuários relatem problemas, pois o MAM é uma ferramenta de proteção de dados. Se houver um problema com a configuração de MAM, o usuário terá acesso irrestrito, como teria sem o MAM, e não estará ciente de que há um problema. Por esse motivo, é recomendável que você valide sua configuração de MAM realizando um piloto de suas políticas de MAM com um pequeno grupo de usuários que podem testar deliberadamente as restrições de MAM.


### <a name="what-to-check"></a>O que verificar

Se o teste mostrar que o comportamento da política de MAM não é esperado, é recomendável que você verifique o seguinte:

- Os usuários estão licenciados para MAM?
- Os usuários estão licenciados para o O365?
- O status de cada um dos aplicativos MAM dos usuários. Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**.

#### <a name="user-mam-status"></a>Status MAM do usuário
1. No Portal do Azure, escolha **Gerenciamento de aplicativos móveis do Intune** > **Configurações** > **Gerenciamento de aplicativo** > **Todas as configurações** > **Relatórios de aplicativos pelo usuário** > **usuários**.

2. Escolha um usuário na lista ou procure e escolha um usuário e escolha **Selecionar usuário**. Na parte superior da coluna **Relatórios de aplicativo**, você verá se o usuário está licenciado para MAM. Abaixo disso, você verá se o usuário está licenciado para o O365 e o status do aplicativo para todos os dispositivos do usuário.

![Status de aplicativo para MAM](..\media\ts-mam-user-apps.png)

### <a name="what-to-do"></a>O que fazer
Aqui estão as ações necessárias com base no status do usuário:

- Se o usuário não está licenciado para MAM, atribua uma licença do Intune ao usuário, conforme descrito em [Gerenciar licenças do Intune](..\get-started\start-with-a-paid-subscription-to-microsoft-intune.md).
- Se o usuário não está licenciado para o O365, obtenha uma licença para o usuário.
- Se o aplicativo do usuário é listado como **Não submetido a check-in**, verifique se você configurou corretamente uma política de MAM para o aplicativo.
- Verifique se essas condições são aplicadas a todos os usuários aos quais você deseja que as políticas MAM sejam aplicadas.

### <a name="see-also"></a>Consulte também
[Preparar-se para configurar as políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[Proteger dados de aplicativo usando políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


