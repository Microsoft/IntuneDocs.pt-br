---
title: Configurações de conformidade com o Android Enterprise no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações que você pode usar ao definir a conformidade para seus dispositivos Android Enterprise no Microsoft Intune. Definir regras de senha, escolha uma versão de sistema operacional mínima ou máxima, restrinja aplicativos específicos, evite a reutilização senha e muito mais.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/16/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f7d38d5c71b06587b593eef46eca46f3d32f1349
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71733095"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configurações do Android Enterprise para marcar dispositivos como em conformidade ou não em conformidade usando o Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Este artigo lista e descreve as diferentes configurações de conformidade que você pode definir em dispositivos Android Enterprise no Intune. Como parte de sua solução MDM (gerenciamento de dispositivo móvel), use estas configurações para marcar dispositivos com raiz (desbloqueados) como não estando em conformidade, definir um nível de ameaça permitido, habilitar o Google Play Protect e muito mais.

Esse recurso aplica-se a:

- Android Enterprise

Como um administrador do Intune, use essas configurações de conformidade para ajudar a proteger os recursos da sua organização. Para saber mais sobre as políticas de conformidade e o que elas fazem, veja a [introdução à conformidade do dispositivo](device-compliance-get-started.md).

> [!IMPORTANT]
> As políticas de conformidade também aplicam dispositivos Android Enterprise dedicados. Se uma política de conformidade for atribuída a um dispositivo dedicado, o dispositivo poderá mostrar como **não compatível**. O acesso condicional e a imposição de conformidade não estão disponíveis em dispositivos dedicados. Lembre-se de concluir todas as tarefas ou ações para colocar os dispositivos dedicados em conformidade com as políticas atribuídas.

## <a name="before-you-begin"></a>Antes de começar

[Criar uma política de conformidade](create-compliance-policy.md#create-the-policy). Para **Plataforma**, selecione **Android Enterprise**.

## <a name="device-owner"></a>Proprietário do dispositivo

### <a name="device-health"></a>Integridade do Dispositivo

- **Exigir que o dispositivo esteja no nível de ameaça do dispositivo ou abaixo**dele: selecione o nível máximo permitido de ameaça do dispositivo avaliado pelo seu [serviço de defesa contra ameaças móveis](mobile-threat-defense.md). Os dispositivos que excedem esse nível de ameaça são marcados como não compatíveis. Para usar essa configuração, escolha o nível de ameaça permitido:

  - **Não configurado** (padrão): esta configuração não é avaliada em relação a estar ou não em conformidade.
  - **Protegido**: essa opção é a mais segura e significa que o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, será avaliado que ele não está em conformidade.
  - **Baixo**: o dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como em conformidade se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele não está em conformidade.
  - **Alta**: esta opção é a menos segura, porque permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.
  
> [!NOTE] 
> Os seguintes provedores de defesa contra ameaças móveis (MTD) dão suporte a implantações de proprietário de dispositivo Android Enterprise usando a configuração de aplicativo:
> - Better Mobile 
> - Pradeo
> - Sophos Mobile
> - Zimperium 
>  
>  Verifique com seu provedor MTD a configuração exata necessária para dar suporte a plataformas do proprietário do dispositivo Android Enterprise no Intune. Essa lista é atualizada, pois o MTD parters dá suporte a cenários de proprietário do dispositivo Android Enterprise. 

#### <a name="google-play-protect"></a>Google Play Protect

- **Atestado de dispositivo SafetyNet**: insira o nível de [atestado de SafetyNet](https://developer.android.com/training/safetynet/attestation.html) que deve ser atendido. Suas opções:
  - **Não configurado** (padrão): a configuração não é avaliada em relação a estar ou não em conformidade.
  - **Verificação básica de integridade**
  - **Verifique a integridade básica e os dispositivos certificados**

### <a name="device-properties"></a>Propriedades do dispositivo

- **Sistema operacional mínimo**: quando um dispositivo não atender ao requisito mínimo da versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode atualizar seu dispositivo e, em seguida, acessar os recursos da organização.
- **Versão do sistema operacional máxima**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela na regra, o acesso aos recursos da organização será bloqueado. O usuário é solicitado a contatar o administrador de TI. Até que uma regra seja alterada para permitir a versão do sistema operacional, esse dispositivo não poderá acessar os recursos da organização.

### <a name="system-security"></a>Segurança do sistema

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  Essa configuração é aplicada no nível do dispositivo. Se você precisar exigir senha apenas no nível do perfil de trabalho, use uma política de configuração. Confira [Definições de configuração de dispositivo do Android Enterprise](../configuration/device-restrictions-android-for-work.md).

  - **Tipo de senha necessária**: escolha se uma senha deve incluir apenas caracteres numéricos ou uma combinação de números e outros caracteres. Suas opções:
    - **Padrão do dispositivo**: para avaliar a conformidade de senha, certifique-se de selecionar uma senha que não seja o **padrão do dispositivo**.  
    - **Senha obrigatória, sem restrições**
    - **Biometria fraca**: [Biometria forte vs. fraca](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (abre o site do Android)
    - **Numérica** (padrão): a senha só deve conter números, como `123456789`. Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
    - **Complexo numérico**: números repetidos ou consecutivos, como "1111" ou "1234", não são permitidos. Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
    - **Alfabética**: as letras do alfabeto são obrigatórias. Números e símbolos não são obrigatórios. Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
    - **Alfanumérica**: inclui letras maiúsculas, letras minúsculas e caracteres numéricos. Insira o **comprimento mínimo da senha** que um usuário deve digitar, entre 4 e 16 caracteres.
    - **Alfanumérica com símbolos**: inclui letras maiúsculas, letras minúsculas, caracteres numéricos, sinais de pontuação e símbolos. Insira também:

      - **Comprimento máximo da senha**: insira o comprimento máximo que uma senha deve ter, entre 4 e 16 caracteres.
      - **Número de caracteres obrigatórios**: insira o número de caracteres que a senha deve ter, entre 0 e 16 caracteres.
      - **Número de caracteres minúsculos obrigatórios**: insira o número de caracteres minúsculos que a senha deve ter, entre 0 e 16 caracteres.
      - **Número de caracteres maiúsculos obrigatórios**: insira o número de caracteres maiúsculos que a senha deve ter, entre 0 e 16 caracteres.
      - **Número de caracteres diferentes de letras obrigatórios**: insira o número de caracteres diferentes de letras (qualquer coisa diferente de letras do alfabeto) que a senha deve ter, entre 0 e 16 caracteres.
      - **Número de caracteres numéricos obrigatórios**: insira o número de caracteres numéricos (`1`, `2`, `3` e assim por diante) que a senha deve ter, entre 0 e 16 caracteres.
      - **Número de caracteres de símbolo obrigatórios**: insira o número de caracteres de símbolo (`&`, `#`, `%` e assim por diante) que a senha deve ter, entre 0 e 16 caracteres.

- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Número de dias até que a senha expire**: insira o número de dias, entre 1 e 365, até que a senha do dispositivo precise ser alterada. Por exemplo, para alterar a senha após 60 dias, insira `60`. Quando a senha expirar, o usuário deverá criar uma.
- **Número de senhas obrigatórias antes que o usuário possa reutilizar uma senha**: insira o número de senhas recentes que não podem ser utilizadas, entre 1 e 24. Use essa configuração para impedir que o usuário crie senhas usadas anteriormente.

- **Criptografia de armazenamento de dados em dispositivo**: escolha **Exigir** para criptografar o armazenamento de dados em seus dispositivos. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  Você não precisa definir essa configuração porque os dispositivos Android Enterprise impõem a criptografia.

## <a name="work-profile"></a>Perfil de trabalho

### <a name="device-health"></a>Device health

- **Dispositivos desbloqueados por rooting**: escolha **Bloquear** para marcar dispositivos desbloqueados por rooting (com jailbreak) como não estando em conformidade. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Exigir que o dispositivo esteja no nível de ameaça do dispositivo ou abaixo**dele: selecione o nível máximo permitido de ameaça do dispositivo avaliado pelo seu [serviço de defesa contra ameaças móveis](mobile-threat-defense.md). Os dispositivos que excedem esse nível de ameaça são marcados como não compatíveis. Para usar essa configuração, escolha o nível de ameaça permitido:

  - **Não configurado** (padrão): esta configuração não é avaliada em relação a estar ou não em conformidade.
  - **Protegido**: essa opção é a mais segura e significa que o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, será avaliado que ele não está em conformidade.
  - **Baixo**: o dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como em conformidade se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele não está em conformidade.
  - **Alta**: esta opção é a menos segura, porque permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.

#### <a name="google-play-protect"></a>Google Play Protect

- **Google Play Services está configurado**: **exige** que o aplicativo de Google Play Services esteja instalado e habilitado. Os serviços do Google Play permitem atualizações de segurança e são uma dependência em nível de base para muitos recursos de segurança em dispositivos certificados do Google. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Atualizar provedor de segurança**: **exige** que um provedor de segurança atualizado possa proteger um dispositivo contra vulnerabilidades conhecidas. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Atestado de dispositivo SafetyNet**: insira o nível de [atestado de SafetyNet](https://developer.android.com/training/safetynet/attestation.html) que deve ser atendido. Suas opções:
  - **Não configurado** (padrão): a configuração não é avaliada em relação a estar ou não em conformidade.
  - **Verificação básica de integridade**
  - **Verifique a integridade básica e os dispositivos certificados**

> [!NOTE]
> Em dispositivos Android Enterprise, **Verificação de ameaças em aplicativos** é uma política de configuração de dispositivo. Usando uma política de configuração, os administradores podem habilitar a configuração em um dispositivo. Veja [Configurações de restrição de dispositivo Android Enterprise](../configuration/device-restrictions-android-for-work.md).

### <a name="device-properties"></a>Propriedades do dispositivo

- **Sistema operacional mínimo**: quando um dispositivo não atender ao requisito mínimo da versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode atualizar seu dispositivo e, em seguida, acessar os recursos da organização.
- **Versão do sistema operacional máxima**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela na regra, o acesso aos recursos da organização será bloqueado. O usuário é solicitado a contatar o administrador de TI. Até que uma regra seja alterada para permitir a versão do sistema operacional, esse dispositivo não poderá acessar os recursos da organização.

### <a name="system-security"></a>Segurança do sistema

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade. Essa configuração é aplicada no nível do dispositivo. Se você precisar exigir senha apenas no nível do perfil de trabalho, use uma política de configuração. Confira [Definições de configuração de dispositivo do Android Enterprise](../configuration/device-restrictions-android-for-work.md).
- **Tipo de senha necessária**: escolha se uma senha deve incluir apenas caracteres numéricos ou uma combinação de números e outros caracteres. Suas opções:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Pelo menos numérica** (padrão): insira o **comprimento mínimo da senha** que um usuário deve inserir, entre 4 e 16 caracteres.
  - **Complexo numérico**: insira o **comprimento mínimo da senha** que um usuário deve inserir, entre 4 e 16 caracteres.
  - **Pelo menos alfabética**: insira o **comprimento mínimo da senha** que um usuário deve inserir, entre 4 e 16 caracteres.
  - **Pelo menos alfanumérica**: insira o **comprimento mínimo da senha** que um usuário deve inserir, entre 4 e 16 caracteres.
  - **Pelo menos alfanumérica com símbolos**: insira o **comprimento mínimo da senha** que um usuário deve inserir, entre 4 e 16 caracteres.

- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Número de dias até que a senha expire**: selecione o número de dias antes que a senha expire e o usuário final precise criar uma nova.
- **Número de senhas anteriores para evitar a reutilização**: insira o número de senhas recentes que não podem ser utilizadas. Use essa configuração para impedir que o usuário crie senhas usadas anteriormente.

#### <a name="encryption"></a>Criptografia

- **Criptografia de armazenamento de dados em dispositivo**: escolha **Exigir** para criptografar o armazenamento de dados em seus dispositivos. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade. 

  Você não precisa definir essa configuração porque os dispositivos Android Enterprise impõem a criptografia.

#### <a name="device-security"></a>Segurança de dispositivo

- **Bloquear aplicativos de fontes desconhecidas**: escolha **bloquear** dispositivos com fontes de **Segurança** > **Fontes Desconhecidas** habilitadas (com suporte em Android 4.0 – Android 7.x; sem suporte em Android 8.0 e posteriores). Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  Para o sideload de aplicativos, as fontes desconhecidas devem ser permitidas. Se você não tiver aplicativos Android com sideload, defina esse recurso como **Bloquear** para habilitar essa política de conformidade.

  > [!IMPORTANT]
  > O sideload de aplicativos exigem que a configuração **Bloquear aplicativos de fontes desconhecidas** esteja habilitada. Aplique esta política de conformidade somente se você não estiver fazendo o sideload de aplicativos Android nos dispositivos.

  Você não precisa definir essa configuração, pois os dispositivos Android Enterprise sempre restringem a instalação de fontes desconhecidas.

- **Integridade de tempo de execução do aplicativo do portal da empresa**: escolha **exigir** para confirmar que o aplicativo do Portal da Empresa cumpre todos os requisitos a seguir:

  - Tem o ambiente de tempo de execução padrão instalado
  - Está assinado corretamente
  - Não está no modo de depuração
  - É instalado de uma origem conhecida

  Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

- **Bloquear a depuração de USB no dispositivo**: escolha **Bloquear** para impedir que os dispositivos usem o recurso de depuração de USB. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  Você não precisa definir essa configuração porque a depuração de USB já está desabilitada em dispositivos Android Enterprise.

- **Nível mínimo de patch de segurança**: selecione o nível de patch de segurança mais antigo que um dispositivo pode ter. Dispositivos que não estão pelo menos nesse nível de patch não estão em conformidade. A data deve ser inserida no formato *AAAA-MM-DD*.

## <a name="next-steps"></a>Próximas etapas

- [Adicione ações para dispositivos que não estão em conformidade](actions-for-noncompliance.md) e [use marcas de escopo para políticas de filtro](../fundamentals/scope-tags.md).
- [Monitore suas políticas de conformidade](compliance-policy-monitor.md).
- Veja as [configurações da política de conformidade para dispositivos Android](compliance-policy-create-android.md).
