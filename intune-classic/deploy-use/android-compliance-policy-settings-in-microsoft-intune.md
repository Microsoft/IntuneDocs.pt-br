---
title: "Configurações da política de conformidade para o Android"
description: "Este tópico descreve as configurações de política de conformidade de dispositivo Android."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f781c5498a569a067f0f2aa6f780a6cc37c9985c
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="compliance-policy-settings-for-android-devices-in-microsoft-intune"></a>Configurações de política de conformidade para dispositivos Android no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As configurações de política descritas neste tópico se aplicam a dispositivos que executam o Android 4.0 e posterior ou o Samsung KNOX 4.0 e posterior.

Se você estiver procurando informações sobre outras plataformas, selecione uma das seguintes opções:
> [!div class="op_single_selector"]
- [Configurações da política de conformidade para dispositivos iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Configurações de política de conformidade para dispositivos Windows](windows-compliance-policy-settings-in-microsoft-intune.md)
- [Configurações da política de conformidade para dispositivos Android para Trabalho](afw-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Configurações de segurança do sistema
### <a name="password"></a>Senha
- **Exigir uma senha para desbloquear dispositivos móveis**: defina esta opção como **Sim** para exigir que os usuários insiram uma senha antes que possam acessar o dispositivo.

-  **Comprimento mínimo da senha**: especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve ter.

- **Qualidade da senha**: essa configuração detecta se os requisitos de senha especificados por você estão configurados no dispositivo. Habilite essa configuração para exigir que os usuários atendam certos requisitos de senha para dispositivos Android. Escolha:

  -   **Biométrico de segurança baixa**
  -   **Necessária**
  -   **Pelo menos, numérico**
  -   **Pelo menos, alfabético**
  -   **Pelo menos, alfanumérico**
  -   **Alfanumérico com símbolos**

- **Minutos de inatividade antes que a senha seja exigida:** especifica o tempo ocioso antes que o usuário precise digitar novamente sua senha.

- **Expiração da senha (dias)**: selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.

- **Lembrar o histórico da senha**: use essa configuração em conjunto com **Evitar a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.

- **Evitar a reutilização de senhas anteriores:** especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas (se **Lembrar o histórico de senha** estiver selecionado).

- **Exigir uma senha quando o dispositivo retorna do estado ocioso:** use em conjunto com a configuração **Minutos de inatividade antes da senha ser necessária**. Os usuários serão solicitados a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.

### <a name="encryption"></a>Criptografia
- **Exigir criptografia no dispositivo móvel**: defina esta opção como **Sim** para exigir que os dispositivos sejam criptografados para poderem conectarem-se aos recursos. Os dispositivos serão criptografados quando você definir a configuração **Exigir uma senha para desbloquear dispositivos móveis**.

## <a name="device-health-and-security-settings"></a>Configurações de segurança e integridade do dispositivo

- **O dispositivo não pode estar com jailbreak ou com raiz**: se você habilitar essa configuração, os dispositivos com jailbreak serão avaliados como não compatíveis.
- **Exigir que dispositivos impeçam a instalação de aplicativos de fontes desconhecidas (Android 4.0 ou posterior)**: para bloquear dispositivos que têm a opção **Segurança > Fontes desconhecidas** habilitado no dispositivo, habilite essa configuração e defina-a como **Sim**.  

>[!IMPORTANT]
>Aplicativos de sideload requerem que a configuração **Fontes desconhecidas** esteja habilitada. Aplique esta política de conformidade somente se você não estiver fazendo o sideload de aplicativos Android nos dispositivos.

- **Exigir que a depuração de USB esteja desabilitada (Android 4.2 ou posterior)**: especifique se a opção de detecção de depuração de USB no dispositivo está habilitada.
- **Exigir que os dispositivos tenham habilitado “Examinar dispositivo contra ameaças à segurança” (Android 4.4 4.2)**: especifique se o recurso **Verificar aplicativos** está habilitado no dispositivo.
- **Nível mínimo do patch de segurança do Android (Android 6.0 ou posterior)**: especifique o nível mínimo de patch de Android.  Dispositivos com níveis de patch mais antigos são incompatíveis. A data deve ser especificada neste formato: AAAA-MM-DD.
- **Requer proteção contra ameaças de dispositivo a ser habilitado**: use esta configuração para fazer a avaliação de risco da solução Consulta MTP como uma condição para conformidade. Selecione o nível máximo de ameaça permitido, que é um dos seguintes:

  - **Nenhum (Seguro)**: este é o mais seguro. Isso significa que o dispositivo não pode ter nenhuma ameaça. Se for detectado que o dispositivo tem qualquer ameaça, ele será avaliado como não compatível.
  - **Baixo**: o dispositivo será avaliado como compatível se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatibilidade.
  - **Médio**: o dispositivo será avaliado como compatível se as ameaças presentes nele forem de nível baixo ou médio. Se forem detectadas ameaças no dispositivo, será determinado que ele é não compatível.
  - **Alto**: esta é a opção menos segura. Basicamente, ela permite todos os níveis de ameaça, o que talvez só seja útil se você usar esta solução apenas para fins de relatório.

  Para obter mais detalhes, consulte [Criar política de conformidade de dispositivo do Lookout](create-lookout-device-compliance-policy.md).

## <a name="device-property-settings"></a>Configurações de propriedade do dispositivo

- **Sistema operacional mínimo exigido**: quando um dispositivo não atender ao requisito mínimo da versão do sistema operacional, ele será relatado como não compatível.
  É exibido um link com informações sobre como atualizar. O usuário pode optar por atualizar seus dispositivos após o que será possível acessar os recursos da empresa.

- **Versão do sistema operacional máxima permitida**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que a regra seja alterada para permitir a versão do SO, este dispositivo não poderá ser usado para acessar recursos da empresa.
