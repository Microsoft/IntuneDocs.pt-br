---
title: "Como criar uma política de conformidade para o Android"
titleSuffix: Azure portal
description: "Saiba como criar uma política de conformidade para dispositivos Android."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7995b79422a142f3eb8d5e81d81dbc525fbbb696
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-devices-in-intune"></a>Como criar uma política de conformidade do dispositivo para dispositivos Android no Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Políticas de conformidade do dispositivo são criadas para cada formulário de plataforma no portal do Intune no Azure. 

- Para saber mais sobre o que é a política de conformidade, consulte o tópico [O que é conformidade do dispositivo](device-compliance.md).
- Para saber mais sobre os pré-requisitos que você precisa cumprir antes de criar uma política de conformidade, consulte o tópico [Introdução à conformidade do dispositivo](device-compliance-get-started.md).

## <a name="to-create-a-device-compliance-policy"></a>Para criar uma política de conformidade do dispositivo

1. Na folha **Intune**, escolha **Definir conformidade do dispositivo**. Em **Gerenciar**, escolha **Todas as políticas de conformidade de dispositivo** e selecione **Criar**.
2. Digite um nome, descrição e escolha a plataforma à qual você deseja que essa política se aplique.
3. Escolha **Requisitos de conformidade** para especificar as configurações de **Segurança**, **Integridade do dispositivo** e **Propriedade do dispositivo**. Quando terminar, escolha **OK**.

<!-- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.-->

## <a name="to-assign-user-groups"></a>Para atribuir grupos de usuários

Para atribuir uma política de conformidade aos usuários, escolha uma política que você configurou. As políticas existentes podem ser encontradas na folha **Conformidade – Políticas**.

1. Escolha a política e as **Atribuições**. Isso abrirá a folha na qual é possível selecionar **Grupos de segurança do Azure Active Directory** e atribuí-los à política.
2. Escolha **Selecionar grupos** para abrir a folha que exibe os grupos de segurança do Azure AD. Aqui você pode encontrar os grupos de segurança no seu Azure Active Directory.  Você pode selecionar os grupos de usuários aos quais deseja que essa política seja aplicada e escolher **Selecionar**. Escolher **Selecionar** implanta a política para os usuários.

Você aplicou a política para os usuários.  A conformidade dos dispositivos usados pelos usuários de destino da política será avaliada.

<!---##  Compliance policy settings--->

## <a name="device-health-and-security-settings"></a>Configurações de segurança e integridade do dispositivo

- **O dispositivo não pode estar com jailbreak ou com raiz:** se você habilitar essa configuração, os dispositivos com jailbreak serão avaliados como não compatíveis.
- **Exigir que dispositivos impeçam a instalação de aplicativos de fontes desconhecidas (Android 4.0 ou posterior)**: para bloquear dispositivos que têm a opção **Segurança** > **Fontes desconhecidas** habilitado no dispositivo, habilite essa configuração e defina-a como **Sim**.

### <a name="important"></a>Importante

Aplicativos de sideload requerem que a configuração **Fontes desconhecidas** esteja habilitada. Aplique esta política de conformidade somente se você não estiver fazendo o sideload de aplicativos Android nos dispositivos.

- **Exigir que a depuração de USB esteja desabilitada (Android 4.2 ou posterior)**: essa configuração especifica se a opção de detecção de depuração de USB no dispositivo de está habilitada.
- **Exigir que os dispositivos tenham habilitado “Examinar dispositivo contra ameaças à segurança” (Android 4.4 4.2)**: essa configuração especifica se o recurso **Verificar aplicativos** está habilitado no dispositivo.
- **Nível mínimo do patch de segurança do Android (Android 6.0 ou posterior)**: use essa configuração para especificar o nível mínimo de patch de Android. Dispositivos com níveis de patch mais antigos são incompatíveis. A data deve ser especificada no formato: AAAA-MM-DD.
- **Exigir proteção contra ameaças ao dispositivo a ser habilitado**: use esta configuração para fazer a avaliação de risco da solução Lookout MTP como uma condição para conformidade. Escolha o nível máximo de ameaça permitido, que é um dos seguintes:
  - **Nenhum (Seguro)**: este é o mais seguro. Isso significa que o dispositivo não pode ter nenhuma ameaça. Se for detectado que o dispositivo tem qualquer nível de ameaça, ele será avaliado como não compatível.
  - **Baixo**: o dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como em conformidade se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele é não compatível.
  - **Alto**: esta é a opção menos segura. Essencialmente, isso permite todos os níveis de ameaça. Poderá ser útil se você estiver usando esta solução apenas para fins de relatório.

Para obter mais detalhes, consulte [Habilitar regra de proteção contra ameaças de dispositivo na política de conformidade](https://docs.microsoft.com/intune-classic/deploy-use/enable-device-threat-protection-rule-in-compliance-policy).

## <a name="system-security-settings"></a>Configurações de segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: defina esta opção como **Sim** para exigir que os usuários insiram uma senha antes que possam acessar o dispositivo.
- **Tamanho mínimo da senha**: especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve ter.
- **Qualidade da senha**: essa configuração detecta se os requisitos de senha especificados por você estão configurados no dispositivo. Habilite essa configuração para exigir que os usuários atendam certos requisitos de senha para dispositivos Android. Escolha:
  - **Biométrico de segurança baixa**
  - **Necessária**
  - **Pelo menos, numérico**
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Alfanumérico com símbolos**
- **Minutos de inatividade antes que a senha seja exigida**: especifique o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias)**: selecione o número de dias antes que a senha expire e seja preciso criar uma nova.
- **Lembrar o histórico da senha**: use essa configuração em conjunto com **Impedir a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.
- **Impedir a reutilização de senhas anteriores**: se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.
- **Exigir uma senha quando o dispositivo retorna do estado ocioso:** use essa configuração junto com **Minutos de inatividade antes da senha ser necessária**. O usuário é solicitado a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.

### <a name="encryption"></a>Criptografia

- **Exigir criptografia no dispositivo móvel**: defina esta opção como **Sim** para exigir que os dispositivos sejam criptografados para conectar aos recursos. Os dispositivos serão criptografados quando você escolher a configuração **Exigir uma senha para desbloquear dispositivos móveis**.

## <a name="device-property-settings"></a>Configurações de propriedade do dispositivo

- **Sistema operacional mínimo exigido**: quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário pode optar por atualizar seus dispositivos após o que será possível acessar os recursos da empresa.
- **Versão do sistema operacional máxima permitida**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e será solicitado que o usuário entre em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.

## <a name="how-noncompliant-settings-work-with-conditional-access-policies"></a>Como as configurações não compatíveis funcionam com políticas de acesso condicional?

A tabela abaixo descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional.

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

**Remediado** = o sistema operacional do dispositivo impõe a conformidade. (Por exemplo, o usuário é forçado a definir um PIN.)+

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. (Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo.) Quando os dispositivos não são compatíveis, ocorrem as seguintes ações:+

- O dispositivo será bloqueado se uma política de acesso condicional se aplicar ao usuário.
- O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
