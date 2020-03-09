---
title: Configurações de conformidade com o Android Enterprise no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações que você pode usar ao definir a conformidade para seus dispositivos Android Enterprise no Microsoft Intune. Definir regras de senha, escolha uma versão de sistema operacional mínima ou máxima, restrinja aplicativos específicos, evite a reutilização senha e muito mais.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/07/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 163f5dd246fb17e7d67a8baffbae9926f2f4bc79
ms.sourcegitcommit: a25f556aa9df4fcd9fdacccd12c9029bc6c5fe20
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2020
ms.locfileid: "78256434"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configurações do Android Enterprise para marcar dispositivos como em conformidade ou não em conformidade usando o Intune

Este artigo lista e descreve as diferentes configurações de conformidade que você pode definir em dispositivos Android Enterprise no Intune. Como parte de sua solução MDM (gerenciamento de dispositivo móvel), use estas configurações para marcar dispositivos com raiz (desbloqueados) como não estando em conformidade, definir um nível de ameaça permitido, habilitar o Google Play Protect e muito mais.

Esse recurso aplica-se a:

- Android Enterprise

Como um administrador do Intune, use essas configurações de conformidade para ajudar a proteger os recursos da sua organização. Para saber mais sobre as políticas de conformidade e o que elas fazem, veja a [introdução à conformidade do dispositivo](device-compliance-get-started.md).

> [!IMPORTANT]
> As políticas de conformidade também aplicam dispositivos Android Enterprise dedicados. Se uma política de conformidade for atribuída a um dispositivo dedicado, o dispositivo poderá aparecer como **Não compatível**. O acesso condicional e a imposição de conformidade não estão disponíveis em dispositivos dedicados. Lembre-se de concluir todas as tarefas ou ações para colocar os dispositivos dedicados em conformidade com as políticas atribuídas.

## <a name="before-you-begin"></a>Antes de começar

[Criar uma política de conformidade](create-compliance-policy.md#create-the-policy). Para **Plataforma**, selecione **Android Enterprise**.

## <a name="device-owner"></a>Proprietário do dispositivo

### <a name="device-health"></a>Integridade do dispositivo

- **Requer que o dispositivo esteja em nível igual ou inferior ao Nível de Ameaças do Dispositivo**: Selecione o nível máximo de ameaça de dispositivo permitido avaliado por seu [serviço de defesa contra ameaças móveis](mobile-threat-defense.md). Os dispositivos que excedem esse nível de ameaça são marcados como não compatíveis. Para usar essa configuração, escolha o nível de ameaça permitido:

  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Protegido** – Esta opção é a mais segura e significa que o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, será avaliado que ele não está em conformidade.
  - **Baixo** – O dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio** – O dispositivo será avaliado como em conformidade se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele não está em conformidade.
  - **Alto** – Esta opção é a menos segura, porque permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.
  
> [!NOTE] 
> Todos os provedores de MTD (Defesa Contra Ameaças Móveis) são compatíveis com implantações de proprietário do dispositivo Android Enterprise usando a configuração de aplicativos. Verifique com seu provedor MTD a configuração exata necessária para compatibilidade com plataformas do proprietário do dispositivo Android Enterprise no Intune.

#### <a name="google-play-protect"></a>Google Play Protect

- **Atestado de dispositivo SafetyNet**: Insira o nível de [atestado de SafetyNet](https://developer.android.com/training/safetynet/attestation.html) que deve ser atendido. Suas opções:
  - **Não configurado** (*padrão*) – A conformidade da configuração não é avaliada.
  - **Verificação básica de integridade**
  - **Verifique a integridade básica e os dispositivos certificados**

### <a name="device-properties"></a>Propriedades do Dispositivo

#### <a name="operating-system-version"></a>Versão do Sistema Operacional

- **Versão mínima do SO**: Quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não estando em conformidade. É exibido um link com informações sobre como atualizar. O usuário final pode atualizar seu dispositivo e, em seguida, acessar os recursos da organização.

  *Por padrão, nenhuma versão está configurada*.

- **Versão máxima do SO**: quando um dispositivo estiver usando uma versão de SO posterior à versão presente na regra, o acesso aos recursos da organização será bloqueado. O usuário é solicitado a contatar o administrador de TI. Até que uma regra seja alterada para permitir a versão do sistema operacional, esse dispositivo não poderá acessar os recursos da organização.

  *Por padrão, nenhuma versão está configurada*.

- **Nível mínimo do patch de segurança**:  Selecione o nível de patch de segurança mais antigo que um dispositivo pode ter. Dispositivos que não estão pelo menos nesse nível de patch não estão em conformidade. A data deve ser inserida no formato AAAA-MM-DD.

  *Por padrão, nenhuma data está configurada*.


### <a name="system-security"></a>Segurança do Sistema

- **Exigir uma senha para desbloquear os dispositivos móveis**: 
  - **Não configurado** (*padrão*) – A conformidade desta configuração não é avaliada.
  - **Exigir** – Os usuários precisam inserir uma senha para acessar o dispositivo.
  - **Tipo de senha necessária**: Escolha se uma senha deve incluir apenas caracteres numéricos ou uma combinação de números e outros caracteres. Suas opções:
    - **Padrão do dispositivo** – para avaliar a conformidade de senha, selecione uma força de senha diferente de **Padrão do dispositivo**.  
    - **Senha obrigatória, sem restrições**
    - **Biometria fraca** - [Biometria forte vs. fraca](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (abre o site do Android)
    - **Numérica** (*padrão*): a senha só deve conter números, como `123456789`. Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
    - **Numérica complexa** – Números repetidos ou consecutivos, como "1111" ou "1234", não são permitidos. Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
    - **Alfabética** – As letras do alfabeto são obrigatórias. Números e símbolos não são obrigatórios. Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
    - **Alfanumérica** – Inclui letras maiúsculas, letras minúsculas e caracteres numéricos. Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
    - **Alfanumérica com símbolos** – Inclui letras maiúsculas, letras minúsculas, caracteres numéricos, sinais de pontuação e símbolos. Insira também:
    
    Dependendo do *tipo de senha* selecionado, as seguintes configurações estarão disponíveis:  
    - **Comprimento mínimo da senha**: insira o comprimento máximo que uma senha deve ter, entre 4 e 16 caracteres.  

    - **Número de caracteres obrigatórios**: insira o número de caracteres que a senha deve ter, entre 0 e 16 caracteres.

    - **Número de caracteres em minúsculas obrigatórios**: insira o número de caracteres minúsculos que a senha deve ter, entre 0 e 16 caracteres.

    - **Número de caracteres maiúsculos obrigatórios**: insira o número de caracteres maiúsculos que a senha deve ter, entre 0 e 16 caracteres.

    - **Número de caracteres não alfabéticos obrigatórios**: insira o número de caracteres não alfabéticos (qualquer coisa diferente de letras do alfabeto) que a senha deve ter, entre 0 e 16 caracteres.

    - **Número de caracteres numéricos obrigatórios**: insira o número de caracteres numéricos (`1`, `2`, `3` e assim por diante) que a senha deve ter, entre 0 e 16 caracteres.
    
    - **Número de caracteres de símbolo obrigatórios**: insira o número de caracteres de símbolo (`&`, `#`, `%` e assim por diante) que a senha deve ter, entre 0 e 16 caracteres.
 
- **Máximo de minutos de inatividade antes de a senha ser necessária**: Insira o tempo ocioso antes que o usuário precise inserir novamente sua senha. As opções incluem o padrão de *Não configurado* e de *1 minuto* a *8 horas*.

- **Número de dias até que a senha expire**: insira o número de dias, entre 1 e 365, antes que a senha do dispositivo precise ser alterada. Por exemplo, para alterar a senha após 60 dias, insira `60`. Quando a senha expirar, o usuário deverá criar uma.

   *Por padrão, nenhum valor está configurado*.

- **Número de senhas necessárias antes que o usuário possa reutilizar uma senha**: insira o número de senhas recentes que não podem ser reutilizadas, entre 1 e 24. Use essa configuração para impedir que o usuário crie senhas usadas anteriormente.  

    *Por padrão, nenhuma versão está configurada*.

#### <a name="encryption"></a>Criptografia

- **Criptografia de armazenamento de dados no dispositivo**: 
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Exigir** – criptografar o armazenamento de dados em seus dispositivos.  

  Você não precisa definir essa configuração porque os dispositivos Android Enterprise impõem a criptografia.

## <a name="work-profile"></a>Perfil de trabalho

### <a name="device-health"></a>Integridade do dispositivo

- **Dispositivos desbloqueados por rooting**: 
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Bloquear** – Marque dispositivos desbloqueados por rooting (com jailbreak) como fora de conformidade.  

- **Requer que o dispositivo esteja em nível igual ou inferior ao Nível de Ameaças do Dispositivo**: Selecione o nível máximo de ameaça de dispositivo permitido avaliado por seu [serviço de defesa contra ameaças móveis](mobile-threat-defense.md). Os dispositivos que excedem esse nível de ameaça são marcados como não compatíveis. Para usar essa configuração, escolha o nível de ameaça permitido:

  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Protegido** – Esta opção é a mais segura e significa que o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, será avaliado que ele não está em conformidade.
  - **Baixa** – O dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio** – O dispositivo será avaliado como em conformidade se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele não está em conformidade.
  - **Alto** – Esta opção é a menos segura, porque permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.

#### <a name="google-play-protect"></a>Google Play Protect

- **O Google Play Services está configurado**: 
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Exigir** – Exige que o aplicativo de serviços do Google Play esteja instalado e habilitado. Os serviços do Google Play permitem atualizações de segurança e são uma dependência em nível de base para muitos recursos de segurança em dispositivos certificados do Google. 
  
- **Provedor de segurança atualizado**: 
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Exigir** – Exige que um provedor de segurança atualizado possa proteger um dispositivo contra vulnerabilidades conhecidas. 
  
- **Atestado de dispositivo SafetyNet**: Insira o nível de [atestado de SafetyNet](https://developer.android.com/training/safetynet/attestation.html) que deve ser atendido. Suas opções:
  - **Não configurado** (*padrão*) – A conformidade da configuração não é avaliada.
  - **Verificação básica de integridade**
  - **Verifique a integridade básica e os dispositivos certificados**

> [!NOTE]
> Em dispositivos Android Enterprise, **Verificação de ameaças em aplicativos** é uma política de configuração de dispositivo. Usando uma política de configuração, os administradores podem habilitar a configuração em um dispositivo. Veja [Configurações de restrição de dispositivo Android Enterprise](../configuration/device-restrictions-android-for-work.md).

### <a name="device-properties"></a>Propriedades do Dispositivo

#### <a name="operating-system-version"></a>Versão do Sistema Operacional

- **Versão mínima do SO**: Quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não estando em conformidade. É exibido um link com informações sobre como atualizar. O usuário final pode atualizar seu dispositivo e, em seguida, acessar os recursos da organização.

  *Por padrão, nenhuma versão está configurada*.

- **Versão máxima do SO**: quando um dispositivo estiver usando uma versão de SO posterior à versão presente na regra, o acesso aos recursos da organização será bloqueado. O usuário é solicitado a contatar o administrador de TI. Até que uma regra seja alterada para permitir a versão do sistema operacional, esse dispositivo não poderá acessar os recursos da organização.

  *Por padrão, nenhuma versão está configurada*.

### <a name="system-security"></a>Segurança do sistema

- **Exigir uma senha para desbloquear os dispositivos móveis**: 
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade. 
  - **Exigir** – Os usuários precisam inserir uma senha para acessar o dispositivo.  

  Essa configuração se aplica ao nível do dispositivo. Se você precisar exigir senha apenas no nível do perfil de trabalho, use uma política de configuração. Confira [Definições de configuração de dispositivo do Android Enterprise](../configuration/device-restrictions-android-for-work.md).

- **Tipo de senha necessária**: Escolha se uma senha deve incluir apenas caracteres numéricos ou uma combinação de números e outros caracteres. Suas opções:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Pelo menos numérica** (*padrão*): Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
  - **Complexo numérico**: Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
  - **Pelo menos, alfabética**: Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
  - **Pelo menos, alfanumérica**: Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
  - **Pelo menos alfanumérica com símbolos**: Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.

  Dependendo do *tipo de senha* selecionado, as seguintes configurações estarão disponíveis:  
  - **Máximo de minutos de inatividade antes de a senha ser necessária**: Insira o tempo ocioso antes que o usuário precise inserir novamente sua senha. As opções incluem o padrão de *Não configurado* e de *1 minuto* a *8 horas*.

  - **Número de dias até que a senha expire**: insira o número de dias, entre 1 e 365, antes que a senha do dispositivo precise ser alterada. Por exemplo, para alterar a senha após 60 dias, insira `60`. Quando a senha expirar, o usuário deverá criar uma.

  - **Comprimento mínimo da senha**: insira o comprimento máximo que uma senha deve ter, entre 4 e 16 caracteres. 
  
  - **Número de senhas anteriores para evitar a reutilização**: Insira o número de senhas recentes que não podem ser reutilizadas. Use essa configuração para impedir que o usuário crie senhas usadas anteriormente.

#### <a name="encryption"></a>Criptografia

- **Criptografia de armazenamento de dados no dispositivo**: 
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Exigir** – criptografar o armazenamento de dados em seus dispositivos.  

  Você não precisa definir essa configuração porque os dispositivos Android Enterprise impõem a criptografia.

#### <a name="device-security"></a>Segurança de dispositivo

- **Bloquear aplicativos de fontes desconhecidas**: 
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Bloquear** – bloquear dispositivos com fontes habilitadas para **Segurança** > **Fontes Desconhecidas** (*compatível com Android 4.0 a Android 7.x. Não compatível com Android 8.0 e posteriores*).  

  Para o sideload de aplicativos, as fontes desconhecidas devem ser permitidas. Se você não tiver aplicativos Android com sideload, defina esse recurso como **Bloquear** para habilitar essa política de conformidade.

  > [!IMPORTANT]
  > O sideload de aplicativos exigem que a configuração **Bloquear aplicativos de fontes desconhecidas** esteja habilitada. Aplique esta política de conformidade somente se você não estiver fazendo o sideload de aplicativos Android nos dispositivos.

  Você não precisa definir essa configuração, pois os dispositivos Android Enterprise sempre restringem a instalação de fontes desconhecidas.

- **Integridade de runtime do aplicativo Portal da Empresa**: 
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - *Exigir* – Escolha **Exigir** para confirmar que o aplicativo Portal da Empresa atende a todos os requisitos a seguir:
    - Tem o ambiente de runtime padrão instalado
    - Está assinado corretamente
    - Não está no modo de depuração
    - É instalado de uma origem conhecida

- **Bloquear a depuração de USB no dispositivo**: 
  - **Não configurado** (*padrão*) — Essa configuração não é avaliada em relação à conformidade.
  - **Bloquear** – Impede que os dispositivos usem o recurso de depuração de USB.  

  Você não precisa definir essa configuração porque a depuração de USB já está desabilitada em dispositivos Android Enterprise.

- **Nível mínimo do patch de segurança**:  Selecione o nível de patch de segurança mais antigo que um dispositivo pode ter. Dispositivos que não estão pelo menos nesse nível de patch não estão em conformidade. A data deve ser inserida no formato AAAA-MM-DD.

  *Por padrão, nenhuma data está configurada*.

## <a name="next-steps"></a>Próximas etapas

- [Adicione ações para dispositivos que não estão em conformidade](actions-for-noncompliance.md) e [use marcas de escopo para políticas de filtro](../fundamentals/scope-tags.md).
- [Monitore suas políticas de conformidade](compliance-policy-monitor.md).
- Veja as [configurações da política de conformidade para dispositivos Android](compliance-policy-create-android.md).
