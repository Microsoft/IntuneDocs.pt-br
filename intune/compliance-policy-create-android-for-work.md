---
title: Configurações de dispositivo do Android Enterprise no Microsoft Intune – Azure | Microsoft Docs
description: Ver uma lista de todas as configurações que você pode usar ao definir a conformidade para os dispositivos da empresa Android no Microsoft Intune. Definir regras de senha, escolha uma versão de sistema operacional mínimo ou máximo, restringir aplicativos específicos, evitar a reutilização senha e muito mais.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 16db0acab84a1095c40e9a92648c75c2581187cd
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423553"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configurações do Android Enterprise para marcar dispositivos como em conformidade ou não conformidade usando o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo lista e descreve as configurações de conformidade diferentes que você pode definir em dispositivos do Android Enterprise no Intune. Como parte de sua solução MDM (gerenciamento) do dispositivo móvel, use essas configurações para marcar dispositivos com raiz (desbloqueado) como não compatíveis, definir um nível de ameaça permitido, habilitar o Google Play Protect e muito mais.

Esse recurso aplica-se a:

- Android Enterprise

Como um administrador do Intune, use essas configurações de conformidade para ajudar a proteger seus recursos organizacionais. Para saber mais sobre as políticas de conformidade e qualquer pré-requisito, veja a [Introdução às políticas de conformidade do dispositivo](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Antes de começar

[Criar uma política de conformidade](create-compliance-policy.md#create-the-policy). Para **Plataforma**, selecione **Android Enterprise**.

## <a name="device-health"></a>Device health

- **Dispositivos desbloqueados por rooting**: escolha **Bloquear** para marcar dispositivos desbloqueados por rooting (com jailbreak) como não estando em conformidade. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Exigir que o dispositivo esteja no ou sob o nível de ameaça de dispositivo**: use esta configuração para utilizar a avaliação de sua solução de Lookout MTP como condição para a conformidade. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade. Para usar essa configuração, escolha o nível de ameaça permitido:
  - **Protegido**: essa opção é a mais segura e significa que o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, será avaliado que ele não está em conformidade.
  - **Baixo**: o dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como em conformidade se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele não está em conformidade.
  - **Alta**: esta opção é a menos segura, porque permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.

### <a name="google-play-protect"></a>Proteger o Google Play

- **Google Play Services está configurado**: **exige** que o aplicativo de Google Play Services esteja instalado e habilitado. Os serviços do Google Play permitem atualizações de segurança e são uma dependência em nível de base para muitos recursos de segurança em dispositivos certificados do Google. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Atualizar provedor de segurança**: **exige** que um provedor de segurança atualizado possa proteger um dispositivo contra vulnerabilidades conhecidas. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Atestado de dispositivo SafetyNet**: insira o nível de [atestado de SafetyNet](https://developer.android.com/training/safetynet/attestation.html) que deve ser atendido. Suas opções:
  - **Não configurado** (padrão): a configuração não é avaliada em relação a estar ou não em conformidade.
  - **Verificação básica de integridade**
  - **Verifique a integridade básica e os dispositivos certificados**

> [!NOTE]
> Em dispositivos Android Enterprise, **verificação de ameaças em aplicativos** é uma política de configuração do dispositivo. Usando uma política de configuração, os administradores podem habilitar a configuração em um dispositivo. Veja [Configurações de restrição de dispositivo Android Enterprise](device-restrictions-android-for-work.md).

## <a name="device-properties-settings"></a>Configurações de propriedades do dispositivo

- **Sistema operacional mínimo**: quando um dispositivo não atender ao requisito mínimo da versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seu dispositivo e, depois disso, poderá acessar os recursos da empresa.
- **Versão do sistema operacional máxima**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela na regra, o acesso aos recursos da empresa será bloqueado. E o usuário deverá contatar seu administrador de TI. Até uma regra ser alterada para permitir a versão do sistema operacional, este dispositivo não poderá acessar os recursos da empresa.

## <a name="system-security-settings"></a>Configurações de segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade. Essa configuração é aplicada no nível do dispositivo. Se você precisar exigir senha apenas no nível do perfil de trabalho, use uma política de configuração. Confira [Definições de configuração de dispositivo do Android Enterprise](device-restrictions-android-for-work.md).
- **Tamanho mínimo da senha**: insira o número mínimo de dígitos ou de caracteres que a senha do usuário deve ter.
- **Tipo de senha necessária**: escolha se uma senha deve incluir apenas caracteres numéricos ou uma combinação de números e outros caracteres. Suas opções:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Pelo menos numérico** (padrão)
  - **Complexo numérico**
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**

- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Expiração da senha (dias)**: selecione o número de dias antes que a senha expire e seja preciso criar uma nova.
- **Número de senhas anteriores para evitar a reutilização**: insira o número de senhas recentes que não podem ser utilizadas. Use essa configuração para impedir que o usuário crie senhas usadas anteriormente.

### <a name="encryption"></a>Criptografia

- **Criptografia de armazenamento de dados em dispositivo**: escolha **Exigir** para criptografar o armazenamento de dados em seus dispositivos. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade. 

  Você não precisa definir essa configuração porque os dispositivos de perfil de trabalho do Android impõem a criptografia.

### <a name="device-security"></a>Segurança de dispositivo

- **Bloquear aplicativos de fontes desconhecidas**: escolha **bloquear** dispositivos com fontes de "Segurança > Fontes Desconhecidas" habilitadas (com suporte em Android 4.0 – Android 7.x; sem suporte em Android 8.0 e posteriores). Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  Para o sideload de aplicativos, as fontes desconhecidas devem ser permitidas. Se você não tiver aplicativos Android com sideload, defina esse recurso como **Bloquear** para habilitar essa política de conformidade. 

  > [!IMPORTANT]
  > O sideload de aplicativos exigem que a configuração **Bloquear aplicativos de fontes desconhecidas** esteja habilitada. Aplique esta política de conformidade somente se você não estiver fazendo o sideload de aplicativos Android nos dispositivos.

  Você não precisa definir essa configuração, pois os dispositivos com perfil de trabalho do Android sempre restringem a instalação de fontes desconhecidas.

- **Integridade de tempo de execução do aplicativo do portal da empresa**: escolha **exigir** para confirmar que o aplicativo do Portal da Empresa cumpre todos os requisitos a seguir:

  - Tem o ambiente de tempo de execução padrão instalado
  - Está assinado corretamente
  - Não está no modo de depuração
  - É instalado de uma origem conhecida

  Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

- **Bloquear a depuração de USB no dispositivo**: escolha **Bloquear** para impedir que os dispositivos usem o recurso de depuração de USB. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  Você não precisa definir essa configuração porque a depuração de USB já está desabilitada em dispositivos de perfil de trabalho Android.

- **Nível mínimo de patch de segurança**: selecione o nível de patch de segurança mais antigo que um dispositivo pode ter. Dispositivos que não estão pelo menos nesse nível de patch não estão em conformidade. A data deve ser inserida no formato *AAAA-MM-DD*.

Selecione **OK** > **Criar** para salvar suas alterações.

## <a name="next-steps"></a>Próximas etapas

- [Adicionar ações para dispositivos não compatíveis](actions-for-noncompliance.md) e [usar marcas de escopo para políticas de filtro](scope-tags.md).
- [Monitorar suas políticas de conformidade](compliance-policy-monitor.md).
- [Configurações da política de conformidade para dispositivos Android](compliance-policy-create-android.md)
