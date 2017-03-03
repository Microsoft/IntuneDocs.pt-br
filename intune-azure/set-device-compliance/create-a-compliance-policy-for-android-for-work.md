---
title: "Criar uma política de conformidade para o Android para Trabalho"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: aprenda a criar uma política de conformidade para dispositivos Android para Trabalho."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 48eaa3cbe1ff4e3fb18bfa762a341dbe74a7adce
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-create-a-device-compliance-policy-for-android-for-work-devices-in-intune-azure-preview"></a>Como criar uma política de conformidade do dispositivo para dispositivos Android para Trabalho na versão prévia do Intune Azure


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

As políticas de conformidade são criadas para cada plataforma.  Você pode criar uma política de conformidade no Portal do Azure. Para saber mais sobre o que é a política de conformidade, consulte o tópico [O que é conformidade do dispositivo](what-is-device-compliance.md). Para saber mais sobre os pré-requisitos que você precisa cumprir antes de criar uma política de conformidade, consulte o tópico [Introdução à conformidade do dispositivo](get-started-with-device-compliance.md).

A tabela abaixo descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional.

--------------------------

|**configuração de política**| **Android for Work** |
| --- | --- |
| **Configuração de senha ou PIN** |  Em Quarentena |
| **Criptografia de dispositivo** |  Em Quarentena |
| **Dispositivo desbloqueado ou com raiz** | Em Quarentena (não é uma configuração) |
| **perfil de email** | Não aplicável |
| **Versão mínima do SO** | Em Quarentena |
| **Versão máxima do SO** | Em Quarentena |
| **Atestado de integridade do Windows** |Não aplicável |

**Remediado** = o sistema operacional do dispositivo impõe a conformidade. (Por exemplo, o usuário é forçado a definir um PIN.)+

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. (Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo.) Quando os dispositivos não são compatíveis, ocorrem as seguintes ações:

- O dispositivo será bloqueado se uma política de acesso condicional se aplicar ao usuário.
- O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Criar uma política de conformidade no Portal do Azure

1. Na folha **Intune**, escolha **Definir conformidade do dispositivo**. Em **Gerenciar**, escolha **Todas as políticas de conformidade de dispositivo** e selecione **Criar**.
2. Digite um nome, descrição e escolha a plataforma à qual você deseja que essa política se aplique.
3. Escolha **Requisitos de conformidade** para especificar as configurações de **Segurança**, **Integridade do dispositivo** e **Propriedade do dispositivo** aqui. Quando terminar, escolha **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Atribuir grupos de usuários

Para atribuir uma política de conformidade aos usuários, escolha uma política que você configurou. As políticas existentes podem ser encontradas na folha **Conformidade – Política**.

1. Escolha a política que você deseja atribuir aos usuários e escolha **Atribuições**. Isso abrirá a folha na qual é possível selecionar **Grupos de segurança do Azure Active Directory** e atribuí-los à política.
2. Escolha **Selecionar grupos** para abrir a folha que exibe os grupos de segurança do Azure AD.  Escolher **Selecionar** implanta a política para os usuários.

Você aplicou a política para os usuários.  A conformidade dos dispositivos usados pelos usuários de destino da política será avaliada.

<!--- ##  Compliance policy settings--->

## <a name="system-security-settings"></a>Configurações de segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis:** defina esta opção como **Sim** para exigir que os usuários insiram uma senha antes que eles possam acessar o dispositivo.
- **Tamanho mínimo da senha:** especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve conter.
- **Qualidade da senha:** essa configuração detecta se os requisitos de senha especificados por você estão configurados no dispositivo. Habilite essa configuração para exigir que os usuários configurem certos requisitos de senha para dispositivos Android. Escolha:
  - **Biométrico de segurança baixa**
  - **Necessária**
  - **Pelo menos, numérico**
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Alfanumérico com símbolos**
- **Minutos de inatividade antes da senha ser necessária:** especifica o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias):** selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.
- **Lembrar o histórico da senha:** use essa configuração em conjunto com **Evitar a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.
- **Evitar a reutilização de senhas anteriores:** se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.
- **Exigir uma senha quando o dispositivo retorna do estado ocioso:** essa configuração deve ser usada junto com a configuração **Minutos de inatividade antes da senha ser necessária**. Os usuários finais serão solicitados a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.


### <a name="encryption"></a>Criptografia

- **Exigir criptografia no dispositivo móvel:** não é necessário definir essa configuração, pois os dispositivos Android for Work impõem a criptografia.


## <a name="device-health-and-security-settings"></a>Configurações de segurança e integridade do dispositivo

- **O dispositivo não pode estar com jailbreak ou com raiz:** se você habilitar essa configuração, os dispositivos com jailbreak serão avaliados como não compatíveis.
- **Exigir que dispositivos impeçam a instalação de aplicativos de fontes desconhecidas:** não é necessário definir essa configuração, pois dispositivos Android for Work sempre restringem a instalação de fontes desconhecidas. .
- **Exigir que a depuração de USB esteja desabilitada**: não é necessário definir essas configurações, pois a depuração USB já está desabilitada em dispositivos Android para Trabalho.
- **Nível mínimo do patch de segurança do Android**: use essa configuração para especificar o nível mínimo do patch do Android. Dispositivos com níveis de patch mais antigos são incompatíveis. A data deve ser especificada no formato: AAAA-MM-DD.
- **Exigir proteção contra ameaças ao dispositivo a ser habilitado**: use esta configuração para fazer a avaliação de risco da solução Lookout MTP como uma condição para conformidade. Selecione o nível máximo de ameaça permitido, que é um dos seguintes:
  - **Nenhum (Seguro)**: este é o mais seguro. Isso significa que o dispositivo não pode ter nenhuma ameaça. Se for detectado que o dispositivo tem qualquer nível de ameaça, ele será avaliado como não compatível.
  - **Baixo**: o dispositivo será avaliado como compatível se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como compatível se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele é não compatível.
  - **Alto**: esta é a opção menos segura. Basicamente, ela permite todos os níveis de ameaça e talvez só seja útil se você usa esta solução apenas para fins de relatório.

Para obter mais detalhes, consulte [Habilitar regra de proteção contra ameaças de dispositivo na política de conformidade](https://docs.microsoft.com/en-us/intune/deploy-use/enable-device-threat-protection-rule-in-compliance-policy).

## <a name="device-property-settings"></a>Configurações de propriedade do dispositivo

- **Sistema operacional mínimo exigido:** quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seus dispositivos após o que será possível acessar os recursos da empresa.
- **Versão do sistema operacional máxima permitida:** quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.

<!--- ## Next steps

[How to monitor device compliance](monitor-device-compliance.md)--->

