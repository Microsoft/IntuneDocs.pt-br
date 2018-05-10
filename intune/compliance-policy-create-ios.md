---
title: Criar política de conformidade para dispositivo iOS no Microsoft Intune – Azure | Microsoft Docs
description: Crie ou configure uma política de conformidade de dispositivos do Microsoft Intune para os dispositivos iOS entrarem em uma conta de email, verificarem dispositivos com jailbreak, verificarem o sistema operacional mínimo e máximo e definirem restrições de senha, incluindo tamanho da senha e inatividade do dispositivo.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6f711a6bec9be0ac1fd94183931070f9988d49e3
ms.sourcegitcommit: 2773f388f50654366197a95a6838306f70fc18b8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="add-a-device-compliance-policy-for-ios-devices-in-intune"></a>Adicionar uma política de conformidade de dispositivos para dispositivos iOS no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uma política de conformidade de dispositivos iOS do Intune determina as regras e configurações que os dispositivos iOS precisam cumprir para estarem em conformidade. Quando você usa as políticas de conformidade de dispositivo, é possível permitir ou bloquear o acesso aos recursos da empresa. Você também pode obter relatórios de dispositivo e realizar ações de não conformidade. As políticas de conformidade de dispositivo de cada plataforma podem ser criadas no Portal do Azure no Intune. Para saber mais sobre as políticas de conformidade e qualquer pré-requisito, veja a [Introdução às políticas de conformidade do dispositivo](device-compliance-get-started.md).

A tabela a seguir descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional.

---------------------------

| **Configuração de política** | **iOS 8.0 e posterior** |
| --- | --- |
| **Configuração de senha ou PIN** | Corrigida |
| **Criptografia de dispositivo** | Corrigida (pela definição do PIN) |
| **Dispositivo desbloqueado ou com raiz** | Em Quarentena (não é uma configuração)
| **Perfil de email** | Em Quarentena |
|**Versão mínima do SO** | Em Quarentena |
| **Versão máxima do SO** | Em Quarentena |
| **Atestado de integridade do Windows** | Não Aplicável |

---------------------------

**Remediado** = o sistema operacional do dispositivo impõe a conformidade. (Por exemplo, o usuário é forçado a definir um PIN.)

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. (Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo.) Quando o dispositivo não é compatível, ocorrem as seguintes ações:

- O dispositivo será bloqueado se uma política de acesso condicional se aplicar ao usuário.
- O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

## <a name="create-a-device-compliance-policy"></a>Criar uma política de conformidade do dispositivo

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. Selecione **Plataforma** para **iOS**. Escolha **Definição de Configurações** e insira as configurações **Email**, **Integridade do Dispositivo**, **Propriedades do Dispositivo** e **Segurança do Sistema**. Quando terminar, selecione **OK** e **Criar**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="email"></a>Email

- **Exigir que os dispositivos móveis tenham um perfil de email gerenciado**: se você definir esta opção para exigir, os dispositivos que não têm um email de perfil gerenciado pelo Intune são considerados não compatíveis. Um dispositivo pode não ter um perfil de email gerenciado quando não é direcionado corretamente, ou se o usuário tiver configurado manualmente a conta de email no dispositivo.

  O dispositivo é considerado incompatível nas seguintes situações:
  - O perfil de email é implantado em um grupo de usuários diferente do grupo de usuários que é destino da política de conformidade.
  - O usuário já configurou uma conta de email no dispositivo que corresponde ao perfil de email do Intune implantado no dispositivo. Intune não pode substituir o perfil de usuário provisionado e, portanto, não é capaz de gerenciá-lo. Para garantir a conformidade, o usuário deve remover as configurações de email existentes. Depois, o Intune pode instalar o perfil de email gerenciado.

- **Selecione o perfil de email que deve ser gerenciado pelo Intune**: se a configuração **A conta de email deve ser gerenciada pelo Intune** for selecionada, escolha **Selecionar** para especificar o perfil de email do Intune. O perfil de email deve estar presente no dispositivo.

Para obter detalhes sobre o perfil de email, consulte [Configurar o acesso ao email corporativo usando perfis de email com o Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).

## <a name="device-health"></a>Device health

- **Dispositivos com jailbreak**: se você habilitar essa configuração, os dispositivos com jailbreak não estarão em conformidade.
- **Exigir que o dispositivo esteja no nível de ameaça do dispositivo ou abaixo dele** (iOS 8.0 e mais recente): escolha o nível máximo de ameaça para marcar dispositivos como não estando em conformidade. Os dispositivos que excedem esse nível de ameaça são marcados como não compatíveis:
  - **Protegido**: essa opção é a mais segura, porque o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, ele será avaliado como não compatível.
  - **Baixo**: o dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como em conformidade se as ameaças existentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele é não compatível.
  - **Alta**: esta opção é a menos segura e permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.

## <a name="device-properties"></a>Propriedades do dispositivo

- **SO mínimo exigido**: quando um dispositivo não atender ao requisito mínimo de versão do SO, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário pode optar por atualizar o dispositivo. Depois disso, ele pode acessar recursos da empresa.
- **Versão do sistema operacional máxima permitida**: quando um dispositivo usar uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado. O usuário, então, deverá contatar seu administrador de TI. Até que haja uma alteração na regra para permitir a versão do sistema operacional, este dispositivo não poderá acessar os recursos da empresa.

## <a name="system-security"></a>Segurança do sistema

### <a name="password"></a>Senha

> [!NOTE]
> Depois que uma política de conformidade ou de configuração for aplicada a um dispositivo iOS, os usuários deverão definir uma senha a cada 15 minutos. Os usuários serão notificados continuamente até que uma senha seja definida.

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo. Dispositivos iOS que usam uma senha são criptografados.
- **Senhas simples**: defina como **Bloquear** para que os usuários não possam criar uma senha simples como **1234** ou **1111**. Definido como **Não configurado** para permitir que os usuários criem senhas como **1234** ou **1111**.
- **Tamanho mínimo da senha**: insira o número mínimo de dígitos ou de caracteres que a senha deve ter.
- **Tipo de senha necessária**: escolha se uma senha deve ter apenas caracteres **numéricos** ou se deve haver uma combinação de números e outros caracteres (**alfanuméricos**).
- **Número de caracteres não alfanuméricos na senha**: Insira o número mínimo de caracteres especiais (&, #, %, ! e assim por diante) que devem ser incluídos na senha.

    Definir um número mais alto exige que o usuário crie uma senha mais complexa.

- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias)**: selecione o número de dias antes que a senha expire e seja preciso criar uma nova.
- **Número de senhas anteriores para evitar a reutilização**: insira o número de senhas usadas anteriormente que não podem ser utilizadas.

## <a name="assign-user-groups"></a>Atribuir grupos de usuários

1. Escolha uma política que você configurou. As políticas existentes estão em **Conformidade do dispositivo** > **Políticas**.
2. Escolha a política e as **Atribuições**. Você pode incluir ou excluir grupos de segurança do Azure Active Directory (AD).
3. Escolha **Grupos selecionados** para ver os grupos de segurança do Azure AD. Selecione os grupos de usuários aos quais deseja que essa política seja aplicada e escolher **Salvar** para implantar a política para os usuários.

Você aplicou a política para os usuários. Os dispositivos usados pelos usuários que são direcionados pela política são avaliados quanto à conformidade.

## <a name="next-steps"></a>Próximas etapas
[Automatizar email e adicionar ações para dispositivos não compatíveis](actions-for-noncompliance.md)  
[Monitorar as políticas de conformidade do dispositivo do Intune](compliance-policy-monitor.md)