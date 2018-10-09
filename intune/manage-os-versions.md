---
title: Gerenciar versões do sistema operacional com o Microsoft Intune
description: Saiba como gerenciar versões do sistema operacional em diferentes plataformas com o Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/19/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 361ef17b-1ee0-4879-b7b1-d678b0787f5a
ms.openlocfilehash: 763cc61aae50de893461d1ed137025fa1e6b00b9
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48231639"
---
# <a name="manage-operating-system-versions-with-intune"></a>Gerenciar versões do sistema operacional com o Intune
Em plataformas móveis e de área de trabalho modernas, atualizações, patches e novas versões principais são liberadas em um ritmo acelerado. Você tem controles para gerenciar totalmente as atualizações e patches no Windows, mas outras plataformas como iOS e Android exigem que os usuários finais participem do processo.  O Microsoft Intune tem os recursos para ajudá-lo a estruturar o gerenciamento de versão do sistema operacional em diferentes plataformas.

O Intune pode ajudá-lo a solucionar estes cenários comuns: 
- Determinar quais versões do sistema operacional estão instaladas em seus dispositivos de usuário final
- Controlar o acesso aos dados organizacionais nos dispositivos enquanto você valida uma nova versão do sistema operacional
- Incentivar/exigir que os usuários finais atualizem para a versão mais recente do sistema operacional aprovada pela sua organização
- Gerenciar a distribuição de uma nova versão do sistema operacional que abranja toda a organização
  
## <a name="operating-system-version-control-using-intune-mobile-device-management-mdm-enrollment-restrictions"></a>Controle de versão do sistema operacional usando as restrições de registro do MDM (gerenciamento de dispositivo móvel) do Intune
As restrições de registro do MDM do Intune permitem que você defina os requisitos do dispositivo cliente antes de permitir o registro do dispositivo. A meta é exigir que os usuários finais registrem somente dispositivos que estejam em conformidade antes de obterem acesso aos recursos organizacionais. Os requisitos do dispositivo incluem as versões mínima e máxima do sistema de operacional permitidas para as plataformas com suporte.
 
![Folha de restrições de configuração de plataforma](./media/os-version-platform-configurations.png) 
 
### <a name="in-practice"></a>Na prática
As organizações estão usando restrições de tipo de dispositivo para controlar o acesso aos recursos organizacionais usando as seguintes configurações: 
1. Use a versão mínima do sistema operacional para manter os usuários finais em plataformas com suporte e atuais em sua organização. 
2. Deixe o sistema operacional máximo não especificado (sem limite) ou defina-o como a última versão validada em sua organização para que haja tempo para os testes internos das novas versões do sistema operacional.

Para obter detalhes, consulte [Definir restrições de registro no Intune](https://docs.microsoft.com/intune/enrollment-restrictions-set#set-device-type-restrictions).
 
## <a name="operating-system-version-reporting-and-compliance-with-intune-mdm-device-compliance-policies"></a>Relatório de versão do sistema operacional e conformidade com as políticas de conformidade de dispositivo do MDM do Intune
As políticas de conformidade de dispositivo do MDM do Intune fornecem as seguintes ferramentas: 
- Especificar regras de conformidade
- Exibir o status de conformidade por meio de relatórios
- Executar ações quando há não conformidade por meio de quarentena de dispositivo e acesso condicional

Como as restrições de registro, as políticas de conformidade do dispositivo incluem as versões mínima e máxima do sistema operacional. As políticas também têm um prazo para conformidade que oferece aos usuários um período de cortesia para obter a conformidade. As políticas de conformidade do dispositivo mantém seus dispositivos de usuário final registrados em conformidade com a política organizacional.

![Conformidade do dispositivo – ações para dispositivos fora de conformidade](./media/os-version-actions-noncompliance.png) 

### <a name="in-practice"></a>Na prática
As organizações estão usando políticas de conformidade de dispositivo para os mesmos cenários que as restrições de registro. Essas políticas mantêm os usuários nas versões do sistema operacional atuais e validadas em sua organização. Quando os dispositivos de usuários finais ficam fora de conformidade, o acesso aos recursos organizacionais pode ser bloqueado por meio de acesso condicional até que os usuários finais fiquem dentro do intervalo de sistema operacional com suporte para a sua organização. Os usuários finais são notificados que estão fora de conformidade e recebem as etapas para recuperar o acesso.   

Para obter detalhes, consulte [Introdução às políticas de conformidade do dispositivo no Intune](https://docs.microsoft.com/intune/device-compliance-get-started).
 
## <a name="operating-system-version-controls-using-intune-app-protection-policies"></a>Controles de versão do sistema operacional usando políticas de proteção de aplicativo do Intune    
As configurações de acesso a políticas de proteção de aplicativo do Intune e do MAM (gerenciamento de aplicativos móveis) permitem que você especifique a versão mínima do sistema operacional na camada do aplicativo. Isso permite informar e incentivar ou exigir que os usuários finais atualizem o sistema operacional para uma versão mínima especificada.
 
Você tem duas opções diferentes: 

|Aviso  |Bloquear  |
|---------|---------|
|Avisar informará ao usuário final que ele deve atualizar se ele abrir um aplicativo com uma configuração de política de proteção do aplicativo ou de acesso de MAM em um dispositivo com uma versão de sistema operacional abaixo da versão especificada. O acesso será permitido para o aplicativo e para dados organizacionais.|Bloquear informará ao usuário final que ele deve atualizar quando ele abrir um aplicativo com uma configuração de política de proteção do aplicativo ou de acesso de MAM em um dispositivo com uma versão de sistema operacional abaixo da versão especificada. O acesso não será permitido para o aplicativo e para dados organizacionais.|
|![Caixa de diálogo de aviso de atualização do Android](./media/os-version-update-warning.png)    |![Caixa de diálogo de bloqueio de acesso do aplicativo](./media/os-version-access-blocked.png)          |

 
### <a name="in-practice"></a>Na prática
Atualmente, as organizações estão usando configurações de política de proteção do aplicativo quando os aplicativos são abertos ou retomados como uma maneira de instruir os usuários finais sobre a necessidade de manter seus aplicativos atualizados. Um exemplo de configuração é que os usuários finais são avisados quando estão uma versão abaixo da atual e bloqueados quando estão duas versões abaixo da atual.
 
Para obter detalhes, consulte [Como criar e implantar políticas de proteção do aplicativo](https://docs.microsoft.com/intune/app-protection-policies).

## <a name="managing-a-new-operating-system-version-rollout"></a>Gerenciando a distribuição de uma nova versão do sistema operacional
Você pode usar os recursos do Intune descritos neste artigo para ajudar a passar a sua organização para uma nova versão de sistema operacional dentro do prazo que você definir. As seguintes etapas fornecem um exemplo de modelo de implantação para passar os usuários do sistema operacional v1 para o sistema operacional v2 em sete dias.
- **Etapa 1**: Usar restrições de registro para exigir o sistema operacional v2 como a versão mínima para registrar o dispositivo. Isso garante que novos dispositivos de usuários finais estejam em conformidade no momento do registro.
- **Etapa 2a**: Usar as políticas de proteção de aplicativo do Intune para avisar os usuários que é necessário ter o sistema operacional v2 quando o aplicativo for aberto ou retomado.
- **Etapa 2b**. Usar políticas de conformidade de dispositivo para exigir o sistema operacional v2 como a versão mínima para que um dispositivo esteja em conformidade. Use **Ações** em caso de não conformidade para conceder um período de cortesia de sete dias e enviar aos usuários finais uma notificação por email com o prazo e os requisitos.
  -  Essas políticas informarão aos usuários finais que os dispositivos existentes precisam ser atualizados por email, pelo Portal da Empresa do Intune e quando o aplicativo for aberto para aplicativos habilitados com uma política de proteção do aplicativo.
  - Você pode executar um relatório de conformidade para identificar os usuários que estão fora de conformidade. 
- **Etapa 3a**: Usar as políticas de proteção de aplicativo do Intune para bloquear os usuários quando um aplicativo for aberto ou retomado se o dispositivo não estiver executando o sistema operacional v2.
- **Etapa 3b**: Usar as políticas de conformidade do dispositivo para exigir o sistema operacional v2 como a versão mínima para que um dispositivo esteja em conformidade.
  - Essas políticas exigem que os dispositivos sejam atualizados para que possam continuar a acessar os dados organizacionais. Os serviços protegidos são bloqueados quando usados com acesso condicional do dispositivo. Os aplicativos habilitados com uma política de proteção do aplicativo são bloqueados quando são abertos ou quando acessam dados organizacionais.

## <a name="next-steps"></a>Próximas etapas
Use os seguintes recursos para gerenciar versões de sistema operacional em sua organização: 

- [Definir restrições de tipo de dispositivo](https://docs.microsoft.com/intune/enrollment-restrictions-set#set-device-type-restrictions)
- [Introdução à conformidade do dispositivo](https://docs.microsoft.com/intune/device-compliance-get-started)
- [Como criar e atribuir as políticas de proteção de aplicativo](https://docs.microsoft.com/intune/app-protection-policies)
