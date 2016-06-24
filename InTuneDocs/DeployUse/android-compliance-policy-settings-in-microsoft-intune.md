---
# required metadata

title: Configurações de política de conformidade para dispositivos Android | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Configurações de política de conformidade para dispositivos Android no Microsoft Intune

As configurações de política descritas neste tópico se aplicam a dispositivos que executam o Android 4.0 e posterior ou o Samsung KNOX 4.0 e posterior.

Se você estiver procurando informações sobre outras plataformas, selecione uma das seguintes opções:
> [!div class="op_single_selector"]
- [Configurações da política de conformidade para dispositivos iOS](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Configurações da política de conformidade para dispositivos Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## Configurações de segurança do sistema
### Senha
- **Exigir uma senha para desbloquear dispositivos móveis:** defina esta opção como **Sim** para exigir que os usuários insiram uma senha antes que eles possam acessar o dispositivo.

-  **Comprimento mínimo da senha:** especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve conter.

- **Qualidade da senha:** habilite essa configuração para configurar os requisitos de senha para dispositivos Android. Escolha:
  -   **Biométrico de baixa segurança**
  - **Necessária**
  -   **Ao menos numérico**
  -   **Ao menos alfabético**
  -   **Ao menos alfanumérico**
  -   **Alfanumérico com símbolos**

- **Minutos de inatividade antes da senha ser necessária:** especifica o tempo ocioso antes que o usuário precise digitar novamente a senha.

- **Expiração da senha (dias):** selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.

- **Lembrar o histórico da senha:** use essa configuração em conjunto com **Evitar a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.

- **Evitar a reutilização de senhas anteriores:** se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.

- **Exigir uma senha quando o dispositivo retorna do estado ocioso:** essa configuração deve ser usada junto com a configuração **Minutos de inatividade antes da senha ser necessária**. Os usuários finais serão solicitados a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.

### Criptografia
- **Exigir criptografia no dispositivo móvel:** defina esta opção como **Sim** para exigir que os dispositivos sejam criptografados para conectarem-se aos recursos. Os dispositivos serão criptografados quando você definir a configuração **Exigir uma senha para desbloquear dispositivos móveis**.

## Configurações de integridade do dispositivo

- **O dispositivo não pode estar com jailbreak ou com raiz:** se você habilitar essa configuração, os dispositivos com jailbreak serão avaliados como não compatíveis.

## Configurações de propriedade do dispositivo
- **Sistema operacional mínimo exigido:** quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não compatível.
  É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seus dispositivos após o que será possível acessar os recursos da empresa.

- **Versão do sistema operacional máxima permitida:** quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.


<!--HONumber=Jun16_HO2-->


