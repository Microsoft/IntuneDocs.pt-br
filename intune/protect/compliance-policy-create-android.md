---
title: Configurações de conformidade para dispositivo Android no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações que você pode usar ao definir a conformidade para seus dispositivos Android no Microsoft Intune. Definir regras de senha, escolha uma versão de sistema operacional mínima ou máxima, restrinja aplicativos específicos, evite a reutilização senha e muito mais.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 80ed21c0831eb92a8e18596e7ab5f09848362b3a
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71733056"
---
# <a name="android-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configurações do Android para marcar dispositivos como em conformidade ou não em conformidade usando o Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Este artigo lista e descreve as diferentes configurações de conformidade que você pode definir em dispositivos Android no Intune. Como parte de sua solução MDM (gerenciamento de dispositivo móvel), use estas configurações para marcar dispositivos com raiz (desbloqueados) como não estando em conformidade, definir um nível de ameaça permitido, habilitar o Google Play Protect e muito mais.

Esse recurso aplica-se a:

- Android

Como um administrador do Intune, use essas configurações de conformidade para ajudar a proteger os recursos da sua organização. Para saber mais sobre as políticas de conformidade e o que elas fazem, veja a [introdução à conformidade do dispositivo](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Antes de começar

[Criar uma política de conformidade](create-compliance-policy.md#create-the-policy). Para **Plataforma**, selecione **Android**.

## <a name="device-health"></a>Device health

- **Dispositivos desbloqueados por rooting**: escolha **Bloquear** para marcar dispositivos desbloqueados por rooting (com jailbreak) como não estando em conformidade. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Exigir que o dispositivo esteja no Nível de Ameaça do Dispositivo ou abaixo dele**: use esta configuração para adotar a avaliação de riscos da solução Lookout Mobile Endpoint Security como condição para a conformidade. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade. Para usar essa configuração, escolha o nível de ameaça permitido:
  - **Protegido**: essa opção é a mais segura, porque o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, será avaliado que ele não está em conformidade.
  - **Baixo**: o dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como em conformidade se as ameaças existentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele não está em conformidade.
  - **Alta**: esta opção é a menos segura e permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.

### <a name="google-play-protect"></a>Proteção do Google Play

- **Google Play Services está configurado**: **exige** que o aplicativo de Google Play Services esteja instalado e habilitado. Os serviços do Google Play permitem atualizações de segurança e são uma dependência em nível de base para muitos recursos de segurança em dispositivos certificados do Google. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Atualizar provedor de segurança**: **exige** que um provedor de segurança atualizado possa proteger um dispositivo contra vulnerabilidades conhecidas. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Verificação de ameaça em aplicativos**: **exige** que o recurso **Verificar Aplicativos** do Android esteja habilitado. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  > [!NOTE]
  > Na plataforma Android herdada, esse recurso é uma configuração de conformidade. O Intune só pode verificar se essa configuração está habilitada no nível do dispositivo.

- **Atestado de dispositivo SafetyNet**: insira o nível de [atestado de SafetyNet](https://developer.android.com/training/safetynet/attestation.html) que deve ser atendido. Suas opções:
  - **Não configurado** (padrão): a configuração não é avaliada em relação a estar ou não em conformidade.
  - **Verificação básica de integridade**
  - **Verifique a integridade básica e os dispositivos certificados**

> [!NOTE]
> Para definir as configurações do Google Play Protect usando políticas de proteção de aplicativo, veja [Configurações de política de Proteção de Aplicativo do Intune](../apps/app-protection-policy-settings-android.md#conditional-launch) no Android.

## <a name="device-property-settings"></a>Configurações de propriedade do dispositivo

- **Sistema operacional mínimo**: quando um dispositivo não atender ao requisito mínimo da versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seu dispositivo e, depois disso, poderá ter acesso aos recursos da empresa.
- **Versão do sistema operacional máxima**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado. O usuário deverá contatar seu administrador de TI. Até uma regra ser alterada para permitir a versão do sistema operacional, este dispositivo não poderá acessar os recursos da empresa.

## <a name="system-security-settings"></a>Configurações de segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Tamanho mínimo da senha**: insira o número mínimo de dígitos ou de caracteres que a senha do usuário deve ter.
- **Tipo de senha necessária**: escolha se uma senha deve incluir apenas caracteres numéricos ou uma combinação de números e outros caracteres. Suas opções:
  - **Padrão do dispositivo**: para avaliar a conformidade de senha, certifique-se de selecionar uma senha que não seja o **padrão do dispositivo**.
  - **Biométrico de segurança baixa**
  - **Pelo menos numérico** (padrão)
  - **Numérico complexo**: números repetidos ou consecutivos, como `1111` ou `1234`, não são permitidos.
  - **Pelo menos, alfabético** 
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**

- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Expiração da senha (dias)** : selecione o número de dias antes que a senha expire e o usuário precise criar uma nova.
- **Número de senhas anteriores para evitar a reutilização**: insira o número de senhas recentes que não podem ser utilizadas. Use essa configuração para impedir que o usuário crie senhas usadas anteriormente.

### <a name="encryption"></a>Criptografia

- **Criptografia de armazenamento de dados em um dispositivo** (Android 4.0 e acima ou KNOX 4.0 e acima): escolha **Exigir** para criptografar o armazenamento de dados em seus dispositivos. Os dispositivos serão criptografados quando você escolher a configuração **Exigir uma senha para desbloquear dispositivos móveis**. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

### <a name="device-security"></a>Segurança de dispositivo

- **Bloquear aplicativos de fontes desconhecidas**: escolha **bloquear** dispositivos com fontes de "Segurança > Fontes Desconhecidas" habilitadas (com suporte em Android 4.0 – Android 7.x; sem suporte em Android 8.0 e posteriores). Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  Para o sideload de aplicativos, as fontes desconhecidas devem ser permitidas. Se você não tiver aplicativos Android com sideload, defina esse recurso como **Bloquear** para habilitar essa política de conformidade. 

  > [!IMPORTANT]
  > O sideload de aplicativos exigem que a configuração **Bloquear aplicativos de fontes desconhecidas** esteja habilitada. Aplique esta política de conformidade somente se você não estiver fazendo o sideload de aplicativos Android nos dispositivos.

- **Integridade de tempo de execução do aplicativo do portal da empresa**: escolha **exigir** para confirmar que o aplicativo do Portal da Empresa cumpre todos os requisitos a seguir:

  - Tem o ambiente de tempo de execução padrão instalado
  - Está assinado corretamente
  - Não está no modo de depuração
  - É instalado de uma origem conhecida

  Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

- **Bloquear a depuração de USB no dispositivo** (Android 4.2 ou posterior): escolha **Bloquear** para impedir que os dispositivos usem o recurso de depuração de USB. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Nível mínimo de patch de segurança** (Android 6.0 ou posterior): selecione o nível de patch de segurança mais antigo que um dispositivo pode ter. Dispositivos que não estão pelo menos nesse nível de patch não estão em conformidade. A data deve ser inserida no formato `YYYY-MM-DD`.
- **Aplicativos restritos**: insira o **Nome do aplicativo** e a **ID do pacote de aplicativo** para aplicativos que devem ser restritos. Escolha **Adicionar**. Um dispositivo com pelo menos um aplicativo restrito instalado é marcado como não estando em conformidade.

Selecione **OK** > **Criar** para salvar suas alterações.

## <a name="locations"></a>Locais

Em sua política, você pode forçar conformidade pela localização do dispositivo. Escolha entre os locais existentes. Ainda não tem um local? [Usar locais (limite de rede)](use-network-locations.md) no Intune fornece alguma orientação.

1. Escolha **Locais** > **Selecionar locais**.
2. Na lista, verifique sua localização > **Selecionar**.
3. **Salve** a política.

## <a name="next-steps"></a>Próximas etapas

- [Adicione ações para dispositivos que não estão em conformidade](actions-for-noncompliance.md) e [use marcas de escopo para políticas de filtro](../fundamentals/scope-tags.md).
- [Monitore suas políticas de conformidade](compliance-policy-monitor.md).
- Veja as [configurações da política de conformidade para dispositivos Android Enterprise](compliance-policy-create-android-for-work.md).
