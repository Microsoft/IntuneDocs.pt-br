---
title: "Habilitar a regra de proteção de dispositivo na política de conformidade | Microsoft Intune"
description: "Habilite a regra de proteção contra ameaças móveis na política de conformidade do dispositivo."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: 761372b2c8b81699bc2584ab1ef8d0f9d523abe9


---

# Habilitar a regra de proteção de dispositivo na política de conformidade
O Intune com a proteção contra ameaças móveis Lookout possibilita detectar ameaças móveis e fazer uma avaliação de riscos no dispositivo.  
A regra de política de conformidade permite que você use essa avaliação de riscos para determinar se o dispositivo é compatível com a política. Você pode, então, usar a política de acesso condicional para permitir ou bloquear o Exchange, o SharePoint e outros serviços com base na conformidade do dispositivo.

Para que a detecção de ameaças do Consulta MTP influencie a política de conformidade do dispositivo:

1.  A regra **Proteção contra Ameaças do Dispositivo** deve estar habilitada na política de conformidade.

2.  A página **Status do Lookout** no console de administrador do Intune deve mostrar **Ativo**. Consulte o tópico [Habilitar conexão da Consulta MTP no Intune](enable-lookout-mtp-connection-in-intune.md) para obter mais detalhes e instruções de como ativar a integração do Lookout.


## Configurar a regra de proteção contra ameaças do dispositivo

Antes de criar a regra de proteção contra ameaças do dispositivo na política de conformidade, recomendamos que você [configure sua assinatura com a Consulta MTP](set-up-your-subscription-with-lookout-mtp.md), [habilite a conexão do Lookout no Intune](enable-lookout-mtp-connection-in-intune.md) e [configure o aplicativo Lookout for Work](configure-and-deploy-lookout-for-work-apps.md). A regra de conformidade é imposta apenas depois que a instalação for concluída.

Para habilitar a regra de proteção contra ameaças do dispositivo, use uma política de conformidade existente ou crie uma nova política.

Como parte da instalação da Consulta MTP, no [console da Consulta MTP](https://aad.lookout.com), você criou uma política que classifica diversas ameaças nos níveis alto, médio e baixo. Na política de conformidade do Intune, você usará o nível de ameaça para definir o nível máximo de ameaça permitido.

No console do administrador do Intune, na página de política de conformidade, vá até **Integridade do Dispositivo** e habilite a regra **Proteção contra Ameaças do Dispositivo** usando a opção de alternância. Selecione o nível máximo de ameaça permitido, que é um dos seguintes:
* **Nenhum (Seguro)**: este é o mais seguro.  Isso significa que o dispositivo não pode ter nenhuma ameaça.  Se for detectado que o dispositivo tem qualquer nível de ameaça, ele será avaliado como não compatível.  
* **Baixo**: o dispositivo é avaliado como compatível se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
* **Médio**: o dispositivo é avaliado como compatível se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, é determinado que ele é não compatível.
* **Alto**: esta é a opção menos segura. Essencialmente, ela permite todos os níveis de ameaça e talvez só seja útil se você usar esta solução apenas para fins de relatório.

![captura de tela mostrando a definição da configuração de regra de proteção contra ameaças do dispositivo ](../media/mtp/mtp-compliance-policy-rule.png)

![captura de tela mostrando a opção de nível de ameaça para a configuração de regra de proteção contra ameaças do dispositivo](../media/mtp/mtp-compliance-policy-setting.png)

Se você criar políticas de acesso condicional para o O365 e outros serviços, a avaliação de conformidade acima será levada em consideração e dispositivos não compatíveis terão o acesso bloqueado até que a ameaça seja resolvida.

Você pode ver o estado de conformidade de um dispositivo na página de dispositivos do console do administrador do Intune.

![captura de tela da página de dispositivos no console do administrador do Intune mostrando o status de conformidade de um dispositivo](../media/mtp/mtp-device-status-intune-console.png)

## Próximas etapas
* Criar política de acesso condicional
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange local](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype for Business Online](restrict-access-to-skype-for-business-online-with-microsoft-intune,md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Sep16_HO2-->


