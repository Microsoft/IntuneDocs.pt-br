---
title: Exibir e corrigir dados pessoais
titleSuffix: Microsoft Intune
description: Saiba como exibir e corrigir dados pessoais.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1ba77bc7-505e-4eca-a49e-dcdaa75d0043
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9b6ca291f55511be9e88b0ff898d9383691542bf
ms.sourcegitcommit: a2654f3642b43b29ab0e1cbb2dfa2b56aae18d0e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72310895"
---
# <a name="view-and-correct-personal-data"></a>Exibir e corrigir dados pessoais

Os administradores do Intune podem exibir alguns dados pessoais com base em suas permissões de acesso, mas somente os usuários finais podem alterar os dados pessoais de seus dispositivos.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-dsr-and-stp-note.md)]


## <a name="view-personal-data"></a>Exibir dados pessoais

Os administradores podem ver as informações pessoais do usuário final em várias folhas na interface do usuário do Intune. Os seguintes artigos explicam a quais informações os administradores têm e não têm acesso:
- [Conferir os detalhes do dispositivo](../remote-actions/device-inventory.md) no Intune explica como você pode examinar os detalhes sobre o dispositivo de um usuário final.
- [Monitorar as informações e atribuições do aplicativo](../apps/apps-monitor.md) explica como ver detalhes sobre os aplicativos instalados no dispositivo de um usuário final.
- O [artigo Quais informações minha empresa pode ver quando registro meu dispositivo?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) oferece aos usuários finais uma lista de dados que suas empresas podem e não podem ver. É melhor informar os usuários com clareza sobre qual tipo de dados você está coletando e por quê. Este artigo pode ser a primeira etapa em direção à essa transparência.

### <a name="who-can-view-the-data"></a>Quem pode exibir os dados?

A Microsoft usa os controles rígidos para controlar o acesso a dados do cliente, concedendo o menor nível de acesso necessário para concluir tarefas importantes e revogando o acesso quando não for mais necessário. 

Você pode proteger e controlar o acesso aos dados pessoais do usuário final usando o RBAC (controle de administração baseada em funções). Para obter mais informações, confira [RBAC com o Microsoft Intune](../fundamentals/role-based-access-control.md).

Saiba mais sobre as práticas de dados da Microsoft lendo os Termos do Online Services e a [Política de Privacidade do Microsoft Online Services](https://go.microsoft.com/fwlink/p/?linkid=131004&clcid=0x409). 

## <a name="correct-end-user-personal-data"></a>Corrigir os dados pessoais do usuário final

Os administradores não podem atualizar informações específicas a um dispositivo ou a um aplicativo. Se um usuário final desejar corrigir seus dados pessoais (como o nome do dispositivo), ele precisará fazer isso diretamente em seu dispositivo. Essas alterações serão sincronizadas na próxima vez que ele se conectar ao Intune.


## <a name="next-steps"></a>Próximas etapas

Descubra como [auditar, exportar ou excluir](privacy-data-audit-export-delete.md) dados pessoais no Intune.
