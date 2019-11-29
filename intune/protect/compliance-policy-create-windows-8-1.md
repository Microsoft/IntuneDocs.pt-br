---
title: Configurações de conformidade do Windows 8.1 no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações que você pode usar ao definir a conformidade para seus dispositivos Windows 8.1 e Windows Phone 8.1 no Microsoft Intune. Verifique a conformidade no sistema de operacional mínimo e máximo, defina restrições de senha e comprimento, habilite a criptografia no armazenamento de dados e muito mais.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e074d922078a9772ca67a6ebd99948bc3e64601
ms.sourcegitcommit: 25acfc88b366d2da71c37d354a0238e4f1168325
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72813222"
---
# <a name="windows-81-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configurações do Windows 8.1 para marcar dispositivos como em conformidade ou não em conformidade usando o Intune

Este artigo lista e descreve as diferentes configurações de conformidade que você pode definir em dispositivos Windows 8.1 no Intune. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use estas configurações para bloquear senhas simples, definir a versão mínima e a máxima do SO e muito mais.

Esse recurso aplica-se a:

- Windows Phone 8.1
- Windows 8.1 e posterior

Como um administrador do Intune, use essas configurações de conformidade para ajudar a proteger os recursos da sua organização. Para saber mais sobre as políticas de conformidade e o que elas fazem, veja a [introdução à conformidade do dispositivo](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Antes de começar

[Criar uma política de conformidade](create-compliance-policy.md#create-the-policy). Para **Plataforma**, selecione **Windows Phone 8.1** ou **Windows 8.1 e posterior**.

## <a name="device-properties"></a>Propriedades do Dispositivo

### <a name="operating-system-version"></a>Versão do Sistema Operacional

**Windows Phone 8.1 e posterior**
- **Versão mínima do so para dispositivos móveis**:  
  Insira a versão mínima permitida. Quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não estando em conformidade. É exibido um link com informações sobre como atualizar. O usuário do dispositivo pode optar por atualizá-lo e, depois disso, poderá ter acesso aos recursos da empresa.

- **Versão máxima do sistema operacional para dispositivos móveis**:  
  Insira a versão máxima permitida. Quando um dispositivo estiver usando uma versão de SO posterior à versão inserida na regra, o acesso aos recursos da organização será bloqueado. É solicitado que o usuário do dispositivo entre em contato com o administrador de TI. O dispositivo não pode acessar os recursos da organização até que uma regra seja alterada para permitir a versão do SO.

**Windows 8.1 e posterior**
- **Versão mínima do SO**:  
  Insira a versão mínima permitida. Quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não estando em conformidade. É exibido um link com informações sobre como atualizar. O usuário do dispositivo pode optar por atualizá-lo e, depois disso, poderá ter acesso aos recursos da empresa.

- **Versão máxima do SO**:  
  Insira a versão máxima permitida. Quando um dispositivo estiver usando uma versão de SO posterior à versão inserida na regra, o acesso aos recursos da organização será bloqueado. É solicitado que o usuário do dispositivo entre em contato com o administrador de TI. O dispositivo não pode acessar os recursos da organização até que uma regra seja alterada para permitir a versão do SO.

Computadores com Windows 8.1 retornam a versão **3**. Se a regra de versão do sistema operacional for definida como Windows 8.1 para Windows, então o dispositivo será relatado como não estando em conformidade mesmo que o dispositivo tenha o Windows 8.1.

## <a name="system-security"></a>Segurança do Sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear os dispositivos móveis**:  
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Exigir** – Os usuários precisam inserir uma senha para acessar o dispositivo.

- **Senhas simples**:  
  - **Não configurado** (*padrão*)-os usuários podem criar senhas simples, como **1234** ou **1111**.
  - **Bloquear** — Os usuários não podem criar senhas simples, como **1234** ou **1111**.  

- **Comprimento mínimo da senha**:  
  Insira o número mínimo de dígitos ou caracteres que a senha deve ter.

  Para dispositivos que executam o Windows e são acessados com um conta Microsoft, a política de conformidade não é avaliada corretamente se alguma das condições a seguir for atendida:  
  - Comprimento mínimo da senha é maior que oito caracteres
  - Número mínimo de conjuntos de caracteres é maior que dois

- **Tipo de senha**:  
  Escolha se uma senha deve ter apenas caracteres **numéricos** ou se deve haver uma combinação de números e outros caracteres (**alfanuméricos**).

  Quando definido como *alfanumérico*, a configuração a seguir está disponível.  

  - **Número de caracteres não alfanuméricos na senha**:  
    Quando o *tipo de senha* for definido como **alfanumérico**, especifique o número mínimo de conjuntos de caracteres que a senha deve conter. As opções incluem de **0** a **4** conjuntos, com um padrão de **1**.
    
    Os quatro conjuntos de caracteres são:
    - Letras minúsculas
    - Letras maiúsculas
    - Símbolos
    - Números

    Definir um número mais alto exige que o usuário crie uma senha mais complexa. Para dispositivos que são acessados com um conta Microsoft, a política de conformidade não é avaliada corretamente se alguma das seguintes condições for atendida:

    - Comprimento mínimo da senha é maior que oito caracteres
    - Número mínimo de conjuntos de caracteres é maior que dois

- **Máximo de minutos de inatividade antes de a senha ser necessária**:  
  Insira o tempo ocioso antes que o usuário precise inserir novamente sua senha.

- **Expiração da senha (dias)** :  
  Selecione o número de dias antes que a senha expire e os usuários precisem criar uma nova.

- **Número de senhas anteriores para evitar a reutilização**:  
  Insira o número de senhas usadas anteriormente e que não podem ser usadas.

### <a name="encryption"></a>Criptografia

- **Criptografia de armazenamento de dados no dispositivo**:  
  - **Não configurado** (*padrão*)
  - **Exigir** – Use *Exigir* para criptografar o armazenamento de dados em seus dispositivos.


<!-- not on phone   
- **Require encryption on mobile device**: **Require** the device to be encrypted to connect to data storage resources.
--> 

## <a name="next-steps"></a>Próximas etapas

- [Adicione ações para dispositivos que não estão em conformidade](actions-for-noncompliance.md) e [use marcas de escopo para políticas de filtro](../fundamentals/scope-tags.md).
- [Monitore suas políticas de conformidade](compliance-policy-monitor.md).
- Consulte as [configurações de política de conformidade para dispositivos Windows 10 e posteriores](compliance-policy-create-windows.md).