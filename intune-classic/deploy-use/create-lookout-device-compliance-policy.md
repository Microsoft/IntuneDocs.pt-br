---
title: "Habilitar a regra de proteção de dispositivo"
description: "Habilite a regra de proteção contra ameaças móveis na política de conformidade do dispositivo."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5ee11809349999a795aca0a373724ce18eedbe65
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="create-lookout-device-compliance-policy-in-intune"></a>Criar política de conformidade de dispositivo do Lookout no Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Intune com a Defesa contra Ameaças Móveis do Lookout permite detectar ameaças em dispositivos móveis e avaliar o risco nesses dispositivos. Você pode criar uma regra de política de conformidade que avalia o risco para determinar se o dispositivo está em conformidade. Em seguida, é possível usar a política de acesso condicional para bloquear o acesso a serviços de acordo com a conformidade do dispositivo.

Pré-requisitos para a política de conformidade com a Defesa contra Ameaças Móveis do Lookout:

- [Configurar a assinatura da Defesa contra Ameaças Móveis do Lookout](setup-your-lookout-mtd-subscription.md)
- [Habilitar a conexão do Lookout MTP no console do administrador do Intune](enable-lookout-mtd-connection.md)
- [Configurar e implantar o aplicativo Lookout for work](configure-deploy-lookout-for-work-app.md)

Como parte da configuração da Defesa contra Ameaças Móveis do Lookout, no [console do Lookout](https://aad.lookout.com), você criou uma política que classifica diversas ameaças nos níveis alto, médio e baixo. Na política de conformidade do Intune, defina o nível máximo de ameaças permitido.

1. No [console do administrador do Intune](https://manage.microsoft.com), acesse a página **Políticas de Conformidade**. É possível usar uma política de conformidade existente ou criar uma nova. Acesse **Integridade do Dispositivo** e habilite **Proteção contra Ameaças ao Dispositivo**.
  ![captura de tela que mostra a definição da regra de proteção contra ameaças ao dispositivo no ](../media/mtp/mtp-compliance-policy-rule.png)

2. Selecione o **Nível máximo de ameaça permitido**:
  * **Nenhum (Seguro)**: este é o mais seguro.  O dispositivo não pode ter nenhuma ameaça presente e ainda acessar os recursos da empresa.  Se nenhuma ameaça for encontrada, o dispositivo será avaliado como fora de conformidade.  
  * **Baixo**: o dispositivo estará em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  * **Médio**: o dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio. Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.
  * **Alto**: esta é a opção menos segura. Isso permite todos os níveis de ameaça e usa o Lookout Mobile Threat Protection apenas para fins de relatório.

![captura de tela mostrando a opção de nível de ameaça para a configuração de regra de proteção contra ameaças do dispositivo](../media/mtp/mtp-compliance-policy-setting.png)

Se você criar políticas de acesso condicional para o Office 365 ou outros serviços, essa avaliação de conformidade será avaliada e os dispositivos que não estiverem em conformidade serão impedidos de acessar esses serviços até que a ameaça seja resolvida.

## <a name="monitor-device-threats"></a>Monitorar ameaças ao dispositivo
Para ver o estado de conformidade de um dispositivo, acesse o [console do administrador do Intune](https://manage.microsoft.com) e exiba **Todos os Dispositivos**.

![captura de tela da página de dispositivos no console do administrador do Intune mostrando o status de conformidade de um dispositivo](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>Próximas etapas
* Criar política de acesso condicional
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange Local](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
