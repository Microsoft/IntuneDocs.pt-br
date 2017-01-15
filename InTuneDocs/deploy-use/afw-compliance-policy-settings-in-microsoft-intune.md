---
title: "Configurações da política de conformidade para o Android para Trabalho | Microsoft Docs"
description: "Este tópico descreve as configurações de política de conformidade para dispositivos Android compatíveis com o Android for Work."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2b53e7a410d0ce268ce395c08161095af42857b7


---


# <a name="compliance-policy-settings-for-android-for-work-devices-in-microsoft-intune"></a>Configurações de política de conformidade para dispositivos Android for Work no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

As configurações de política descritas neste tópico se aplicam a dispositivos Android for Work.

Se você estiver procurando informações sobre outras plataformas, selecione uma das seguintes opções:
> [!div class="op_single_selector"]
- [Configurações de política de conformidade para Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Configurações de política de conformidade para dispositivos iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Configurações de política de conformidade para dispositivos Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Configurações de segurança do sistema
### <a name="password"></a>Senha
- **Exigir uma senha para desbloquear dispositivos móveis:** defina esta opção como **Sim** para exigir que os usuários insiram uma senha antes que eles possam acessar o dispositivo.

-  **Comprimento mínimo da senha:** especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve conter.

- **Qualidade da senha:** essa configuração detecta se os requisitos de senha especificados por você estão configurados no dispositivo. Habilite essa configuração para exigir que os usuários configurem certos requisitos de senha para dispositivos Android. Escolha:
  -   **Biométrico de segurança baixa**
  - **Necessária**
  -   **Pelo menos, numérico**
  -   **Pelo menos, alfabético**
  -   **Pelo menos, alfanumérico**
  -   **Alfanumérico com símbolos**

- **Minutos de inatividade antes da senha ser necessária:** especifica o tempo ocioso antes que o usuário precise digitar novamente a senha.

- **Expiração da senha (dias):** selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.

- **Lembrar o histórico da senha:** use essa configuração em conjunto com **Evitar a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.

- **Evitar a reutilização de senhas anteriores:** se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.

- **Exigir uma senha quando o dispositivo retorna do estado ocioso:** essa configuração deve ser usada junto com a configuração **Minutos de inatividade antes da senha ser necessária**. Os usuários finais serão solicitados a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.

### <a name="encryption"></a>Criptografia
- **Exigir criptografia no dispositivo móvel:** não é necessário definir essa configuração, pois os dispositivos Android for Work impõem a criptografia.

## <a name="device-health-and-security-settings"></a>Configurações de segurança e integridade do dispositivo

- **O dispositivo não pode estar com jailbreak ou com raiz:** se você habilitar essa configuração, os dispositivos com jailbreak serão avaliados como não compatíveis.
- **Exigir que dispositivos impeçam a instalação de aplicativos de fontes desconhecidas:** não é necessário definir essa configuração, pois dispositivos Android for Work sempre restringem a instalação de fontes desconhecidas. .  

- **Exigir que a depuração de USB esteja desabilitada**: não é necessário definir essas configurações, pois a depuração USB já está desabilitada em dispositivos Android for Work.

- **Nível mínimo do patch de segurança do Android**: use essa configuração para especificar o nível mínimo do patch do Android.  Dispositivos com níveis de patch mais antigos são incompatíveis. A data deve ser especificada no formato: AAAA-MM-DD.
- **Requer proteção contra ameaças de dispositivo a ser habilitado**: use esta configuração para fazer a avaliação de risco da solução Consulta MTP como uma condição para conformidade. Selecione o nível máximo de ameaça permitido, que é um dos seguintes:

  - **Nenhum (Seguro)**: este é o mais seguro. Isso significa que o dispositivo não pode ter nenhuma ameaça. Se for detectado que o dispositivo tem qualquer nível de ameaça, ele será avaliado como não compatível.
  - **Baixo**: o dispositivo será avaliado como compatível se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como compatível se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele é não compatível.
  - **Alto**: esta é a opção menos segura. Basicamente, ela permite todos os níveis de ameaça e talvez só seja útil se você usa esta solução apenas para fins de relatório.

  Para obter mais detalhes, consulte [Habilitar regra de proteção contra ameaças de dispositivo na política de conformidade](enable-device-threat-protection-rule-in-compliance-policy.md).

## <a name="device-property-settings"></a>Configurações de propriedade do dispositivo
- **Sistema operacional mínimo exigido:** quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não compatível.
  É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seus dispositivos após o que será possível acessar os recursos da empresa.

- **Versão do sistema operacional máxima permitida:** quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.



<!--HONumber=Dec16_HO2-->


