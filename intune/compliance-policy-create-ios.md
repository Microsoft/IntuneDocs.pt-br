---
title: "Como criar uma política de conformidade para o iOS"
titleSuffix: Azure portal
description: "Saiba como criar uma política de conformidade para dispositivos iOS."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b0fdb06b072c325d30b3e5ee72f1982c5f61849
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-create-a-device-compliance-policy-for-ios-devices-in-intune"></a>Como criar uma política de conformidade do dispositivo para dispositivos iOS no Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

As políticas de conformidade são criadas para cada plataforma.  Você pode criar uma política de conformidade no Portal do Azure. Para saber mais sobre o que é a política de conformidade, consulte o tópico [O que é conformidade do dispositivo](device-compliance.md). Para saber mais sobre os pré-requisitos que você precisa cumprir antes de criar uma política de conformidade, consulte o tópico [Introdução à conformidade do dispositivo](device-compliance-get-started.md).

A tabela abaixo descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional.

-------------------------------


| **Configuração de política** | **iOS 8.0 e posterior** |
| --- | --- |
| **Configuração de senha ou PIN** | Corrigida |   
| **Criptografia de dispositivo** | Corrigida (pela definição do PIN) |
| **Dispositivo desbloqueado ou com raiz** | Em Quarentena (não é uma configuração)
| **Perfil de email** | Em Quarentena |
|**Versão mínima do SO** | Em Quarentena |
| **Versão máxima do SO** | Em Quarentena |  
| **Atestado de integridade do Windows** | Não aplicável |  
----------------------------


**Remediado** = o sistema operacional do dispositivo impõe a conformidade. (Por exemplo, o usuário é forçado a definir um PIN.)

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. (Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo.) Quando os dispositivos não são compatíveis, ocorrem as seguintes ações:

- O dispositivo será bloqueado se uma política de acesso condicional se aplicar ao usuário.
- O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Criar uma política de conformidade no Portal do Azure

1. Na folha **Intune**, escolha **Definir conformidade do dispositivo**. Em **Gerenciar**, escolha **Todas as políticas de conformidade de dispositivo** e selecione **Criar**.
2. Digite um nome, descrição e escolha a plataforma à qual você deseja que essa política se aplique.
3. Escolha **Requisitos de conformidade** para especificar as configurações de **Segurança**, **Integridade do dispositivo** e **Propriedade do dispositivo** aqui. Quando terminar, escolha **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Atribuir grupos de usuários

Para atribuir uma política de conformidade aos usuários, escolha uma política que você configurou. As políticas existentes podem ser encontradas na folha **Conformidade – Políticas**.

1. Escolha a política que você deseja atribuir aos usuários e escolha **Atribuições**. Isso abrirá a folha na qual é possível selecionar **Grupos de segurança do Azure Active Directory** e atribuí-los à política.
2. Escolha **Selecionar grupos** para abrir a folha que exibe os grupos de segurança do Azure AD.  Escolher **Selecionar** implanta a política para os usuários.

Você aplicou a política para os usuários.  A conformidade dos dispositivos usados pelos usuários de destino da política será avaliada.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>Configurações de segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: defina essa opção como **Sim** para exigir que o usuário insira uma senha antes de acessar o dispositivo. Dispositivos iOS que usam uma senha são criptografados.
- **Permitir senhas simples**: defina como **Sim** para permitir que o usuário crie uma senha simples, como **1234** ou **1111**.
- **Tamanho mínimo da senha:** especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve ter.
- **Tipo de senha necessária**: especifique se o usuário deve criar uma senha **Alfanumérica** ou **Numérica**.
- **Número mínimo de conjuntos de caracteres:** se você definir **Tipo de senha necessária** como **Alfanumérica**, use essa configuração para especificar o número mínimo de conjuntos de caracteres que a senha deve conter. Os quatro conjuntos de caracteres são:
  - Letras minúsculas
  - Letras maiúsculas
  - Símbolos
  - Números

Definir um número mais alto exige que o usuário crie uma senha mais complexa.

Para dispositivos iOS, essa configuração se refere ao número de caracteres especiais (por exemplo, **!** , **#**, **&amp;**) que devem ser incluídos na senha.

- **Minutos de inatividade antes que a senha seja exigida**: especifique o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias)**: selecione o número de dias antes que a senha expire e seja preciso criar uma nova.
- **Lembrar o histórico da senha**: use essa configuração em conjunto com **Impedir a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.
- **Impedir a reutilização de senhas anteriores**: se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.
- **Exigir uma senha quando o dispositivo volta do estado ocioso**: use essa configuração em conjunto com **Minutos de inatividade antes que a senha seja exigida**. O usuário é solicitado a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.

### <a name="email-profile"></a>Perfil de email

- **A conta de email deve ser gerenciada pelo Intune**: quando essa opção é definida como **Sim**, o dispositivo deve usar o perfil de email implantado no dispositivo. O dispositivo é considerado incompatível nas seguintes situações:
  - O perfil de email é implantado em um grupo de usuários diferente do grupo de usuários que é destino da política de conformidade.
  - O usuário já configurou uma conta de email no dispositivo que corresponde ao perfil de email do Intune implantado no dispositivo. Intune não pode substituir o perfil de usuário provisionado e, portanto, não é capaz de gerenciá-lo. Para garantir a conformidade, o usuário deve remover as configurações de email existentes. Depois, o Intune pode instalar o perfil de email gerenciado.
- **Selecione o perfil de email que deve ser gerenciado pelo Intune**: se a configuração **A conta de email deve ser gerenciada pelo Intune** for selecionada, escolha **Selecionar** para especificar o perfil de email do Intune. O perfil de email deve estar presente no dispositivo.

Para obter detalhes sobre o perfil de email, consulte [Configurar o acesso ao email corporativo usando perfis de email com o Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).

## <a name="device-health-settings"></a>Configurações de integridade do dispositivo

- **O dispositivo não pode estar com jailbreak ou com raiz**: se você habilitar essa configuração, os dispositivos com jailbreak não serão compatíveis.

## <a name="device-properties"></a>Propriedades do dispositivo

- **Sistema operacional mínimo exigido**: quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário pode optar por atualizar o dispositivo. Depois disso, ele pode acessar recursos da empresa.
- **Versão do sistema operacional máxima permitida**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e será solicitado que o usuário entre em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
