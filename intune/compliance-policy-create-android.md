---
title: Criar política de conformidade para dispositivo Android no Microsoft Intune – Azure | Microsoft Docs
description: Criar ou configurar uma política de conformidade do dispositivo do Microsoft Intune para dispositivos Android. Escolha para desbloquear dispositivos, defina o nível de ameaça aceitável, verifique o Google Play, insira a versão mínima e máxima de versão do sistema operacional, escolha seus requisitos de senha e permita sideload dos aplicativos.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 85f11e3a9bfd43affde35806d9aeaf40dcbfe03d
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37906185"
---
# <a name="add-a-device-compliance-policy-for-android-devices-in-intune"></a>Adicionar uma política de conformidade do dispositivo para dispositivos Android no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uma política de conformidade de dispositivos do Intune para Android especifica as regras e configurações que dispositivos do Android precisam cumprir para serem considerados em conformidade. Você pode usar essas políticas com acesso condicional para permitir ou bloquear o acesso aos recursos da empresa. Você também pode obter relatórios de dispositivo e realizar ações de não conformidade. As políticas de conformidade de dispositivo são criadas para cada plataforma no Portal do Azure no Intune. Para saber mais sobre as políticas de conformidade e qualquer pré-requisito, veja a [Introdução às políticas de conformidade do dispositivo](device-compliance-get-started.md).

A tabela a seguir descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional.

--------------------

|**Configuração de política**| **Android 4.0 e posterior, Samsung Knox Standard 4.0 e posterior** |
| --- | ----|
| **Configuração de senha ou PIN** |  Em Quarentena |
| **Criptografia de dispositivo** | Em Quarentena |
| **Dispositivo desbloqueado ou com raiz** | Em Quarentena (não é uma configuração) |
| **perfil de email** | Não Aplicável |
| **Versão mínima do SO** | Em Quarentena |
| **Versão máxima do SO** |   Em Quarentena |
| **Atestado de integridade do Windows** | Não Aplicável |

--------------------------

**Remediado** = o sistema operacional do dispositivo impõe a conformidade. (Por exemplo, o usuário é forçado a definir um PIN.)

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. (Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo.) Quando o dispositivo não é compatível, ocorrem as seguintes ações:

- O dispositivo será bloqueado se uma política de acesso condicional se aplicar ao usuário.
- O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

## <a name="create-a-device-compliance-policy"></a>Criar uma política de conformidade do dispositivo

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. Para **Plataforma**, selecione **Android**. Escolha **Definição de Configurações** para inserir as configurações de **Integridade do Dispositivo**, **Propriedades do Dispositivo** e **Segurança do Sistema**. Quando terminar, selecione **OK**, e **Criar**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.--->

<!---##  Compliance policy settings--->

## <a name="device-health"></a>Device health

- **Dispositivos desbloqueados por rooting**: se você habilitar essa configuração, os dispositivos desbloqueados com rooting serão avaliados como fora de conformidade.
- **Exigir que o dispositivo esteja no ou sob o nível de ameaça de dispositivo**: use esta configuração para utilizar a avaliação de sua solução de Lookout MTP como condição para a conformidade. Selecione o nível máximo de ameaça permitido:
  - **Protegido**: essa opção é a mais segura, porque o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, ele será avaliado como não compatível.
  - **Baixo**: o dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como em conformidade se as ameaças existentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele é não compatível.
  - **Alta**: esta opção é a menos segura e permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.
- **Google Play Services está configurado**: exige que o aplicativo de serviços do Google Play esteja instalado e habilitado. Os serviços do Google Play permitem atualizações de segurança e são uma dependência em nível de base para muitos recursos de segurança em dispositivos certificados do Google.
- **Atualizar provedor de segurança**: Exige que um provedor de segurança atualizado possa proteger um dispositivo contra vulnerabilidades conhecidas.
- **Verificação de ameaça em aplicativos**: exige que o recurso **Verificar Aplicativos** do Android esteja ativado.

  > [!NOTE]
  > Na plataforma Android herdada, esse recurso é uma configuração de conformidade. O Intune só pode verificar se essa configuração está habilitada no nível do dispositivo. Em dispositivos com perfis de trabalho Android, essa configuração pode ser encontrada como uma definição de política de configuração. Isso permite que os administradores habilitem a configuração para um dispositivo.

  Se sua empresa usa perfis de trabalho do Android, você pode habilitar a **Verificação de ameaças em aplicativos** para seus dispositivos registrados. Estabeleça um perfil de dispositivo e exija a configuração de segurança do sistema. Para obter mais informações, confira [Configurações de restrição de dispositivo de perfil de trabalho Android no Intune](device-restrictions-android-for-work.md).

- **Atestado de dispositivo SafetyNet**: insira o nível de [atestado de SafetyNet](https://developer.android.com/training/safetynet/attestation.html) que deve ser atendido. Suas opções:
  - **Não configurado**
  - **Verificação básica de integridade**
  - **Verifique a integridade básica e os dispositivos certificados**

## <a name="device-property-settings"></a>Configurações de propriedade do dispositivo

- **Sistema operacional mínimo**: quando um dispositivo não atender ao requisito mínimo da versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seu dispositivo e, depois disso, poderá ter acesso aos recursos da empresa.
- **Versão do sistema operacional máxima**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado. O usuário deverá contatar seu administrador de TI. Até que haja uma alteração de regra para permitir a versão do sistema operacional, este dispositivo não poderá acessar os recursos da empresa.

## <a name="system-security-settings"></a>Configurações de segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo.
- **Tamanho mínimo da senha**: insira o número mínimo de dígitos ou de caracteres que a senha do usuário deve ter.
- **Tipo de senha necessária**: selecione se uma senha deve ter apenas caracteres numéricos ou uma combinação de números e outros caracteres. Escolha:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Pelo menos, numérico**
  - **Numérico complexo**: números repetidos ou consecutivos, (como "1111" ou "1234") não são permitidos.
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**
- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias)**: selecione o número de dias antes que a senha expire e o usuário precise criar uma nova.
- **Número de senhas anteriores para evitar a reutilização**: insira o número de senhas recentes que não podem ser utilizadas. Use essa configuração para impedir que o usuário crie senhas usadas anteriormente.

### <a name="encryption"></a>Criptografia

- **Criptografia de armazenamento de dados em um dispositivo** (Android 4.0 e acima ou KNOX 4.0 e acima): escolha **Exigir** para criptografar o armazenamento de dados em seus dispositivos. Os dispositivos serão criptografados quando você escolher a configuração **Exigir uma senha para desbloquear dispositivos móveis**.

### <a name="device-security"></a>Segurança de dispositivo

- **Impedir aplicativos de fontes desconhecidas**: escolha bloquear os dispositivos com fontes habilitadas "Segurança > Fontes Desconhecidas" (Android 4.0 – 7. x Android. Não suportado pelo Android 8.0 e posterior). Para o sideload de aplicativos, as fontes desconhecidas devem ser permitidas. Se não estiver fazendo sideload de aplicativos Android, aplique esta política de conformidade.

  > [!IMPORTANT]
  > O sideload de aplicativos exigem que a configuração **Bloquear aplicativos de fontes desconhecidas** esteja habilitada. Aplique esta política de conformidade somente se você não estiver fazendo o sideload de aplicativos Android nos dispositivos.

- **Integridade de tempo de execução do aplicativo do portal da empresa**: verifica se o aplicativo de Portal da empresa tem o ambiente de tempo de execução padrão instalado, está assinado corretamente, não está no modo de depuração e é instalado de uma origem conhecida.
- **Bloquear a depuração de USB no dispositivo** (Android 4.2 ou posterior): escolha impedir que os dispositivos usem o recurso de depuração de USB.
- **Nível mínimo de patch de segurança** (Android 6.0 ou posterior): selecione o nível de patch de segurança mais antigo que um dispositivo pode ter. Dispositivos com níveis de patch mais antigos são incompatíveis. A data deve ser inserida no formato `YYYY-MM-DD`.

## <a name="locations"></a>Locais

Em sua política, escolha entre locais existentes. Ainda não tem um local? [Usar locais (limite de rede) no Intune](use-network-locations.md) fornece alguma orientação.

1. Escolha **Selecionar locais**.
2. Na lista, verifique seu local e escolha **Selecionar**.
3. **Salve** a política.
4. Selecione **Ações para não conformidade**. A ação padrão marca o dispositivo como em não conformidade imediatamente. Essa ação se aplica quando você seleciona pelo menos um local e se o dispositivo não está conectado aos locais selecionados.

  Você pode alterar essa ação para atualizar a agenda quando o dispositivo está marcado como não em conformidade, como após um dia. Você também pode configurar uma segunda ação que envia um email ao usuário quando o dispositivo não está mais em conformidade com os seus locais.

## <a name="assign-user-groups"></a>Atribuir grupos de usuários

1. Escolha uma política que você configurou. As políticas existentes estão em **Conformidade do dispositivo** > **Políticas**.
2. Escolha a política e as **Atribuições**. Você pode incluir ou excluir grupos de segurança do Azure Active Directory (AD).
3. Escolha **Grupos selecionados** para ver os grupos de segurança do Azure AD. Selecione os grupos de usuários aos quais deseja que essa política seja aplicada e escolher **Salvar** para implantar a política para os usuários.

Você aplicou a política para os usuários. Os dispositivos usados pelos usuários que são direcionados pela política são avaliados quanto à conformidade.

## <a name="next-steps"></a>Próximas etapas
[Automatizar email e adicionar ações para dispositivos não compatíveis](actions-for-noncompliance.md)  
[Monitorar as políticas de conformidade do dispositivo do Intune](compliance-policy-monitor.md)