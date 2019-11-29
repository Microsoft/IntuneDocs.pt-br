---
title: Configurações de conformidade para dispositivo Android no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações que você pode usar ao definir a conformidade para seus dispositivos Android no Microsoft Intune. Definir regras de senha, escolha uma versão de sistema operacional mínima ou máxima, restrinja aplicativos específicos, evite a reutilização senha e muito mais.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8efb9dcf9129375252b5d9a7d1e6255dce39625c
ms.sourcegitcommit: b5e719fb507b1bc4774674e76c856c435e69f68c
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2019
ms.locfileid: "73801401"
---
# <a name="android-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configurações do Android para marcar dispositivos como em conformidade ou não em conformidade usando o Intune

Este artigo lista e descreve as diferentes configurações de conformidade que você pode definir em dispositivos Android no Intune. Como parte de sua solução MDM (gerenciamento de dispositivo móvel), use estas configurações para marcar dispositivos com raiz (desbloqueados) como não estando em conformidade, definir um nível de ameaça permitido, habilitar o Google Play Protect e muito mais.

Esse recurso aplica-se a:

- Administrador do dispositivo Android

Como um administrador do Intune, use essas configurações de conformidade para ajudar a proteger os recursos da sua organização. Para saber mais sobre as políticas de conformidade e o que elas fazem, veja a [introdução à conformidade do dispositivo](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Antes de começar

[Criar uma política de conformidade](create-compliance-policy.md#create-the-policy). Para **plataforma**, selecione **administrador do dispositivo Android**.

## <a name="device-health"></a>Integridade do Dispositivo

- **Dispositivos desbloqueados por rooting**:

  - **Não configurado** (*padrão*) – Esta configuração não é avaliada em relação a estar ou não em conformidade.
  - **Bloquear** – Marque dispositivos desbloqueados por rooting (com jailbreak) como fora de conformidade.

- **Requer que o dispositivo esteja em nível igual ou inferior ao Nível de Ameaças do Dispositivo**:

  Use essa configuração para fazer a avaliação de risco de um serviço de defesa contra ameaças móveis conectado como uma condição para conformidade.
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade. 
  - **Protegido** – Esta opção é a mais segura, porque o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, será avaliado que ele não está em conformidade.
  - **Baixa** – O dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Média** – O dispositivo será avaliado como em conformidade se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele não está em conformidade.
  - **Alta** – Esta opção é a menos segura e permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.

### <a name="google-play-protect"></a>Google Play Protect

- **O Google Play Services está configurado**:

  Os serviços do Google Play permitem atualizações de segurança e são uma dependência em nível de base para muitos recursos de segurança em dispositivos certificados do Google.

  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.  
  - **Exigir** – Exige que o aplicativo de serviços do Google Play esteja instalado e habilitado.  

- **Provedor de segurança atualizado**:

  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Exigir** – Exige que um provedor de segurança atualizado possa proteger um dispositivo contra vulnerabilidades conhecidas.

- **Verificação de ameaças em aplicativos**:

  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Exigir** – exige que o recurso **Verificar Aplicativos** do Android esteja ativado.

  > [!NOTE]
  > Na plataforma Android herdada, esse recurso é uma configuração de conformidade. O Intune só pode verificar se essa configuração está habilitada no nível do dispositivo.

- **Atestado de dispositivo SafetyNet**:

  Insira o nível de [atestado de SafetyNet](https://developer.android.com/training/safetynet/attestation.html) que deve ser atendido. Suas opções:

  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Verificação básica de integridade**
  - **Verifique a integridade básica e os dispositivos certificados**

> [!NOTE]
> Para definir as configurações do Google Play Protect usando políticas de proteção de aplicativo, veja [Configurações de política de Proteção de Aplicativo do Intune](../apps/app-protection-policy-settings-android.md#conditional-launch) no Android.

## <a name="device-properties"></a>Propriedades do Dispositivo

### <a name="operating-system-version"></a>Versão do Sistema Operacional 

- **Versão mínima do SO**:

  Quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seu dispositivo e, depois disso, poderá ter acesso aos recursos da empresa.

  *Por padrão, nenhuma versão é configurada*.

- **Versão máxima do SO**:

  Quando um dispositivo estiver usando uma versão de sistema operacional posterior à especificada na regra, o acesso aos recursos da empresa será bloqueado. O usuário deverá contatar seu administrador de TI. Até uma regra ser alterada para permitir a versão do sistema operacional, este dispositivo não poderá acessar os recursos da empresa.

  *Por padrão, nenhuma versão é configurada*.

## <a name="system-security"></a>Segurança do Sistema

### <a name="password"></a>Senha

<!-- Removed
- **Minimum password length**: Enter the minimum number of digits or characters that the user's password must have.   


- **Maximum minutes of inactivity before password is required**: Enter the idle time before the user must reenter their password. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.

- **Password expiration (days)**: Select the number of days before the password expires and the user must create a new password.

- **Number of previous passwords to prevent reuse**: Enter the number of recent passwords that can't be reused. Use this setting to restrict the user from creating previously used passwords.

-->

- **Exigir uma senha para desbloquear os dispositivos móveis**:

  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Exigir** – Os usuários precisam inserir uma senha para acessar o dispositivo.

- **Tipo de senha necessária**:

  Escolha se uma senha deve incluir apenas caracteres numéricos ou uma combinação de números e outros caracteres. Suas opções:

  - **Dispositivo padrão** – para avaliar a conformidade de senha, selecione uma senha que não seja o **padrão do dispositivo**.
  - **Biométrico de segurança baixa**
  - **Pelo menos, numérico**
  - **Numérica complexa** – Números repetidos ou consecutivos, como `1111` ou `1234`, não são permitidos.
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**

### <a name="encryption"></a>Criptografia

- **Criptografia de armazenamento de dados em um dispositivo**:  
  *Com suporte no Android 4,0 e posterior, ou KNOX 4,0 e posterior.*

  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Exigir** -criptografar o armazenamento de dados em seus dispositivos. Os dispositivos serão criptografados quando você escolher a configuração **Exigir uma senha para desbloquear dispositivos móveis**.

### <a name="device-security"></a>Segurança de dispositivo

- **Bloquear aplicativos de fontes desconhecidas**:

  - **Não configurado** (*padrão*) – Esta configuração não é avaliada em relação a estar ou não em conformidade.
  - **Bloquear** -bloquear dispositivos com segurança > fontes habilitadas para **fontes desconhecidas** (*com suporte no Android 4,0 até o Android 7. x. Não suportado pelo Android 8.0 e posterior*).

  Para o sideload de aplicativos, as fontes desconhecidas devem ser permitidas. Se você não tiver aplicativos Android com sideload, defina esse recurso como **Bloquear** para habilitar essa política de conformidade.

  > [!IMPORTANT]
  > O sideload de aplicativos exigem que a configuração **Bloquear aplicativos de fontes desconhecidas** esteja habilitada. Aplique esta política de conformidade somente se você não estiver fazendo o sideload de aplicativos Android nos dispositivos.

- **Integridade de runtime do aplicativo Portal da Empresa**:

  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Exigir** – Escolha *Exigir* para confirmar que o aplicativo Portal da Empresa atende a todos os requisitos a seguir:

    - Tem o ambiente de runtime padrão instalado
    - Está assinado corretamente
    - Não está no modo de depuração
    - É instalado de uma origem conhecida

- **Bloquear a depuração de USB no dispositivo** *(Android 4,2 ou posterior)* :

  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Bloquear** – Impede que os dispositivos usem o recurso de depuração de USB.

- **Nível mínimo de patch de segurança** *(Android 6,0 ou posterior)* :

  Selecione o nível de patch de segurança mais antigo que um dispositivo pode ter. Dispositivos que não estão pelo menos nesse nível de patch não estão em conformidade. A data deve ser inserida no formato `YYYY-MM-DD`.

  *Por padrão, nenhuma data é configurada*.

- **Aplicativos restritos**:

  Insira o **Nome do aplicativo** e a **ID do pacote de aplicativo** para aplicativos que devem ser restritos, depois selecione **Adicionar**. Um dispositivo com pelo menos um aplicativo restrito instalado é marcado como não estando em conformidade.

## <a name="next-steps"></a>Próximas etapas

- [Adicione ações para dispositivos que não estão em conformidade](actions-for-noncompliance.md) e [use marcas de escopo para políticas de filtro](../fundamentals/scope-tags.md).
- [Monitore suas políticas de conformidade](compliance-policy-monitor.md).
- Veja as [configurações da política de conformidade para dispositivos Android Enterprise](compliance-policy-create-android-for-work.md).
