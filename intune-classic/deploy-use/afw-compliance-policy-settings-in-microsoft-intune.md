---
title: Configurações de conformidade do Android for Work
description: Este tópico descreve as configurações de política de conformidade para dispositivos Android compatíveis com o Android for Work.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 02/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ab1e43d1cb66bdc6e0fc02324ffd1d8923e61174
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="compliance-policy-settings-for-android-for-work-devices-in-microsoft-intune"></a>Configurações de política de conformidade para dispositivos Android for Work no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As configurações de política descritas neste tópico se aplicam a dispositivos Android for Work.

Se você estiver procurando informações sobre outras plataformas, selecione uma das seguintes opções:
> [!div class="op_single_selector"]
- [Configurações de política de conformidade para Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Configurações da política de conformidade para dispositivos iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
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
- **Exigir que a proteção contra ameaças ao dispositivo esteja habilitada**: use essa configuração para executar a avaliação de risco da solução de proteção contra ameaças ao dispositivo como uma condição para a conformidade. Selecione o nível máximo de ameaça permitido, que é um dos seguintes:

  - **Nenhum (Seguro)**: este é o mais seguro. Isso significa que o dispositivo não pode ter nenhuma ameaça. Se for detectado que o dispositivo tem qualquer nível de ameaça, ele será avaliado como não compatível.
  - **Baixo**: o dispositivo será avaliado como compatível se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como compatível se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, ele será determinado como não compatível.
  - **Alto**: esta é a opção menos segura. Basicamente, ela permite todos os níveis de ameaça e talvez só seja útil se você usa esta solução apenas para fins de relatório.

  Para obter mais detalhes, consulte [Create device compliance policy](create-lookout-device-compliance-policy.md) (Criar política de conformidade do dispositivo).

## <a name="device-property-settings"></a>Configurações de propriedade do dispositivo
- **Sistema operacional mínimo exigido:** se um dispositivo não atender ao requisito mínimo de versão do SO (sistema operacional), ele será relatado como não compatível.
  É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seus dispositivos após o que será possível acessar os recursos da empresa.

- **Versão máxima permitida do sistema operacional:** quando um dispositivo estiver usando uma versão do SO (sistema operacional) posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário deverá entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do sistema operacional em questão, o dispositivo não poderá ser usado para acessar recursos da empresa.
