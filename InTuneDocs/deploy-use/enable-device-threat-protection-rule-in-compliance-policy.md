---
title: "Habilitar a regra de proteção do dispositivo na política de conformidade | Microsoft Docs"
description: "Habilite a regra de proteção contra ameaças móveis na política de conformidade do dispositivo."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 80e96003c584c67cb6b0289a7e2ed1ff3a833c2c
ms.openlocfilehash: 3dea6c35d5fc035a5aef6dda52543b64cd5ce177


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>Habilitar a regra de proteção de dispositivo na política de conformidade

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Intune com o Lookout Mobile Threat Protection permite detectar ameaças em dispositivos móveis e avaliar o risco nesses dispositivos. Você pode criar uma regra de política de conformidade que avalia o risco para determinar se o dispositivo está em conformidade. Em seguida, é possível usar a política de acesso condicional para bloquear o acesso a serviços de acordo com a conformidade do dispositivo.

Pré-requisitos para a política de conformidade com a proteção contra ameaças ao dispositivo do Lookout:

- [Configurar assinatura para a proteção contra ameaças ao dispositivo do Lookout](set-up-your-subscription-with-lookout-mtp.md)
- [Habilitar a conexão do Lookout MTP no console do administrador do Intune](enable-lookout-mtp-connection-in-intune.md)
- [Configurar e implantar aplicativos Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)

Como parte da configuração da proteção contra ameaças ao dispositivo do Lookout, no [console do Lookout](https://aad.lookout.com), você criou uma política que classifica diversas ameaças nos níveis alto, médio e baixo. Na política de conformidade do Intune, defina o nível máximo de ameaças permitido.

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



<!--HONumber=Dec16_HO4-->


