---
title: "Criar uma política de conformidade do Android for Work"
titleSuffix: Microsoft Intune
description: "Crie uma política de conformidade de dispositivo do Intune para dispositivos Android for Work, para que você possa especificar os requisitos que um dispositivo precisa cumprir para estar em conformidade."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ca31d4c83ccc6b786933080b96f66953cf1a108
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-for-work-devices-in-intune"></a>Como criar uma política de conformidade do dispositivo para dispositivos Android for Work no Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Uma política de conformidade de dispositivos do Intune para Android for Work especifica as regras e configurações que dispositivos do Android for Work precisam cumprir para estar serem considerados em conformidade. Você pode usar essas políticas com acesso condicional para permitir ou bloquear o acesso aos recursos da empresa, bem como obter relatórios de dispositivos e executar ações em caso de não conformidade. As políticas de conformidade de dispositivo são criadas para cada plataforma no Portal do Azure no Intune. Para saber mais sobre as políticas de conformidade e os pré-requisitos que você precisa cumprir antes de criá-las, consulte [Introdução à conformidade do dispositivo](device-compliance-get-started.md).

A tabela a seguir descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional.

--------------------------

|**configuração de política**| **Android for Work** |
| --- | --- |
| **Configuração de senha ou PIN** |  Em Quarentena |
| **Criptografia de dispositivo** |  Em Quarentena |
| **Dispositivo desbloqueado ou com raiz** | Em Quarentena (não é uma configuração) |
| **perfil de email** | Não Aplicável |
| **Versão mínima do SO** | Em Quarentena |
| **Versão máxima do SO** | Em Quarentena |
| **Atestado de integridade do Windows** |Não Aplicável |

**Remediado** = o sistema operacional do dispositivo impõe a conformidade. (Por exemplo, o usuário é forçado a definir um PIN.)+

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. (Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo.) Quando o dispositivo não é compatível, ocorrem as seguintes ações:

- Se uma política de acesso condicional se aplicar ao usuário, o dispositivo será bloqueado.
- O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Criar uma política de conformidade no Portal do Azure

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
1. No painel **Intune**, escolha **Conformidade do dispositivo**. Em **Gerenciar**, escolha **Políticas** e **Criar política**.
2. Digite um nome, descrição e escolha a plataforma à qual você deseja que essa política se aplique.
3. Escolha **Definir configurações** para especificar as configurações de **Segurança do Sistema**, **Integridade do Dispositivo** e **Propriedades do Dispositivo** aqui. Quando terminar, escolha **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Atribuir grupos de usuários

Para atribuir uma política de conformidade aos usuários, escolha uma política que você configurou. As políticas existentes podem ser encontradas no painel **Conformidade do dispositivo – Políticas**.

1. Escolha a política que você deseja atribuir aos usuários e escolha **Atribuições**. Isso abrirá o painel no qual é possível selecionar os **Grupos de segurança do Azure Active Directory** e atribuí-los à política.
2. Escolha **Grupos selecionados** para abrir o painel que exibe os grupos de segurança do Microsoft Azure AD.  Escolher **Salvar** implanta a política para os usuários.

Você aplicou a política para os usuários.  A conformidade dos dispositivos usados pelos usuários de destino da política será avaliada.

<!--- ##  Compliance policy settings--->

## <a name="system-security-settings"></a>Configurações de segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: defina esta opção como **Sim** para exigir que os usuários insiram uma senha antes que possam acessar o dispositivo.
- **Tamanho mínimo da senha**: especifique o número mínimo de dígitos ou caracteres que a senha deve conter.
- **Qualidade da senha**: essa configuração detecta se os requisitos de senha especificados por você estão configurados no dispositivo. Habilite essa configuração para exigir que os usuários configurem certos requisitos de senha para dispositivos Android. Escolha:
  - **Biométrico de segurança baixa**
  - **Necessária**
  - **Pelo menos, numérico**
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Alfanumérico com símbolos**
- **Minutos de inatividade antes que a senha seja solicitada**: especifica o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias):** selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.
- **Lembrar histórico de senha:** use essa configuração em conjunto com **Evitar reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.
- **Evitar a reutilização de senhas anteriores:** se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.
- **Exigir uma senha quando o dispositivo volta do estado ocioso**: essa configuração deve ser usada com **Minutos de inatividade antes que a senha seja solicitada**. Os usuários finais serão solicitados a inserir uma senha para acessar um dispositivo que esteve inativo durante o tempo especificado na configuração **Minutos de inatividade antes que a senha seja solicitada**.


### <a name="encryption"></a>Criptografia

- **Exigir criptografia no dispositivo móvel**: não é necessário definir essa configuração, pois os dispositivos Android for Work impõem a criptografia.


## <a name="device-health-and-security-settings"></a>Configurações de segurança e integridade do dispositivo

- **O dispositivo não pode ter sofrido jailbreak ou root**: se você habilitar essa configuração, os dispositivos com jailbreak serão avaliados como não compatíveis.
- **Exigir que dispositivos impeçam a instalação de aplicativos de fontes desconhecidas**: não é necessário definir essa configuração, pois dispositivos Android for Work sempre restringem a instalação de fontes desconhecidas.
- **Exigir que a depuração de USB esteja desabilitada**: não é necessário definir essa configuração, pois a depuração USB já está desabilitada em dispositivos Android for Work.
- **Nível mínimo do patch de segurança do Android**: use essa configuração para especificar o nível mínimo do patch do Android. Dispositivos com níveis de patch mais antigos são incompatíveis. A data deve ser especificada no formato: AAAA-MM-DD.
- **Requer proteção contra ameaças de dispositivo a ser habilitado**: use esta configuração para fazer a avaliação de risco da solução Consulta MTP como uma condição para conformidade. Selecione o nível máximo de ameaça permitido, que é um dos seguintes:
  - **Nenhum (Seguro)**: este é o mais seguro. Isso significa que o dispositivo não pode ter nenhuma ameaça. Se for detectado que o dispositivo tem qualquer nível de ameaça, ele será avaliado como não compatível.
  - **Baixo**: o dispositivo será avaliado como compatível se houver apenas ameaças de nível baixo. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo é avaliado como em conformidade se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, ele será determinado como não compatível.
  - **Alto**: esta é a opção menos segura. Essencialmente, essa opção permite todos os níveis de risco, e talvez seja útil somente se você estiver usando esta solução para fins de relatório.

## <a name="device-property-settings"></a>Configurações de propriedade do dispositivo

- **SO mínimo exigido**: quando um dispositivo não atender ao requisito mínimo de versão do SO, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seus dispositivos, quando então será possível acessar os recursos da empresa.
- **Versão do sistema operacional máxima permitida**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
