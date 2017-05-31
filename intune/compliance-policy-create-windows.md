---
title: "Como criar uma política de conformidade para o Windows"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: aprenda a criar uma política de conformidade para dispositivos Windows."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 13fc7783-d4de-47d0-b1b8-4c8710a9e6ab
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 4de81c3dc6f1499c2364d8bf9c3b49b219248684
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-create-a-device-compliance-policy-for-windows-devices-in-intune-azure-preview"></a>Como criar uma política de conformidade do dispositivo para dispositivos Windows na versão prévia do Intune Azure


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

As políticas de conformidade são criadas para cada plataforma.  Você pode criar uma política de conformidade no Portal do Azure. Para saber mais sobre o que é a política de conformidade, consulte o tópico [O que é conformidade do dispositivo](device-compliance.md). Para saber mais sobre os pré-requisitos que você precisa cumprir antes de criar uma política de conformidade, consulte o tópico [Introdução à conformidade do dispositivo](device-compliance-get-started.md).

A tabela abaixo descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional.

---------------------------

| **Configuração de política** | **Windows 8.1 e posterior** | **Windows Phone 8.1 e posterior** |
|----| ----| --- |
| **Configuração de senha ou PIN** | Corrigida | Corrigida |   
| **Criptografia de dispositivo** | Não aplicável | Corrigida |   
| **Dispositivo desbloqueado ou com raiz** | Não aplicável | Não aplicável |  
| **Perfil de email** | Não aplicável | Não aplicável |   
| **Versão mínima do SO** | Em Quarentena | Em Quarentena |   
| **Versão máxima do SO** | Em Quarentena | Em Quarentena |   
| **Atestado de integridade do Windows** | Em quarentena: Windows 10 e Windows 10 Mobile|Não aplicável: Windows 8.1 |

-------------------------------

**Remediado** = o sistema operacional do dispositivo impõe a conformidade. (Por exemplo, o usuário é forçado a definir um PIN.)+

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. (Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo.) Quando os dispositivos não são compatíveis, ocorrem as seguintes ações:+

- O dispositivo será bloqueado se uma política de acesso condicional se aplicar ao usuário.
- O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Criar uma política de conformidade no Portal do Azure

1. Na folha **Intune**, escolha **Definir conformidade do dispositivo**. Em **Gerenciar**, escolha **Todas as políticas de conformidade de dispositivo** e selecione **Criar**.
2. Digite um nome, descrição e escolha a plataforma à qual você deseja que essa política se aplique.
3. Escolha **Requisitos de conformidade** para abrir a folha de requisitos de conformidade.  Você pode especificar as configurações de **Segurança**, **Integridade do dispositivo** e **Propriedade do dispositivo** aqui. Quando terminar, escolha **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
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

- **Exigir uma senha para desbloquear dispositivos móveis:** defina esta opção como **Sim** para exigir que os usuários insiram uma senha antes que eles possam acessar o dispositivo.
- **Permitir senhas simples:** defina como **Sim** para permitir que os usuários criem senhas simples, como &#39; “**1234**” ou “**1111**”.
- **Tamanho mínimo da senha:** especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve conter.
- **Tipo de senha exigido:** especifique se os usuários devem criar uma senha **Alfanumérica** ou **Numérica**.

Para dispositivos que executam o Windows e são acessados com uma Conta da Microsoft, a política de conformidade não será avaliada corretamente se o comprimento mínimo da senha tiver mais de oito caracteres ou se o número mínimo de conjuntos de caracteres for maior que dois.

- **Número mínimo de conjuntos de caracteres:** se o **Tipo de senha necessário** for definido como **Alfanumérico**, essa configuração especificará o número mínimo de conjuntos de caracteres que a senha deve conter. Os quatro conjuntos de caracteres são:
  - Letras minúsculas
  - Letras maiúsculas
  - Símbolos
  - Números

Definir um número mais alto para essa configuração exigirá que os usuários criem senhas mais complexas. Para dispositivos que executam o Windows e são acessados com uma Conta da Microsoft, a política de conformidade não será avaliada corretamente se o comprimento mínimo da senha tiver mais de oito caracteres ou se o número mínimo de conjuntos de caracteres for maior que dois.

- **Minutos de inatividade antes da senha ser necessária:** especifica o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias):** selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.
- **Lembrar o histórico da senha:** use essa configuração em conjunto com **Evitar a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.
- **Evitar a reutilização de senhas anteriores:** se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.
- **Exigir uma senha quando o dispositivo retorna do estado ocioso:** essa configuração deve ser usada junto com **Minutos de inatividade antes da senha ser necessária**. Os usuários finais serão solicitados a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.

**Essa configuração só se aplica a dispositivos Windows 10 Mobile.**

### <a name="encryption"></a>Criptografia

- **Exigir criptografia no dispositivo móvel:** defina esta opção como **Sim** para exigir que o dispositivo seja criptografado para conectar-se aos recursos.



## <a name="device-health-settings"></a>Configurações de integridade do dispositivo

- **Exigir que os dispositivos sejam relatados como íntegros:** você pode definir uma regra para exigir que os dispositivos **Windows 10 Mobile** sejam relatados como íntegros nas Políticas de Conformidade novas ou existentes. Se essa configuração estiver habilitada, dispositivos Windows 10 serão avaliados por meio do HAS (Serviço de Atestado de Integridade) para os seguintes pontos de dados:
  - **BitLocker habilitado**: quando o Bitlocker está ativado, o dispositivo é capaz de proteger os dados armazenados na unidade do acesso não autorizado quando o sistema é desligado ou entra no modo de hibernação. A Criptografia de Unidade de Disco Windows BitLocker criptografa todos os dados armazenados no volume do sistema operacional Windows. O BitLocker usa o TPM para ajudar a proteger o sistema operacional Windows e os dados de usuário e ajuda a garantir que um computador não foi violado, mesmo se tiver sido deixado sem supervisão, tiver sido perdido ou roubado. Se o computador estiver equipado com um TPM compatível, o BitLocker usará o TPM para bloquear as chaves de criptografia que protegem os dados. Consequentemente, as chaves não poderão ser acessadas até que o TPM verifique o estado do computador
  - **Integridade de código habilitada:** a integridade de código é um recurso que valida a integridade de um driver ou arquivo do sistema cada vez que ele é carregado na memória. A integridade do código detecta se um arquivo de sistema ou de driver não assinado está sendo carregado no kernel, ou se um arquivo do sistema foi modificado por software mal-intencionado que está sendo executado por uma conta de usuário com privilégios de administrador.
  - **Inicialização Segura habilitada:** quando a Inicialização Segura está habilitada, o sistema é forçado a inicializar para um estado confiável de fábrica. Além disso, quando a Inicialização Segura é habilitada, os principais componentes usados para inicializar o computador devem ter assinaturas criptográficas corretas que são confiáveis para a organização que fabricou o dispositivo. O firmware UEFI confirma isso antes de permitir que o computador seja iniciado. Se todos os arquivos foram violados, interrompendo sua assinatura, o sistema não inicializará.

Para obter informações sobre como funciona o serviço HAS, consulte [CSP do Estado de Integridade](https://msdn.microsoft.com/library/dn934876.aspx).

## <a name="device-property-settings"></a>Configurações de propriedade do dispositivo

- **Sistema operacional mínimo exigido:** quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seus dispositivos, quando então será possível acessar os recursos da empresa.
- **Versão do sistema operacional máxima permitida:** quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.

<!---## Compliance policy settings for Windows PCs--->

## <a name="system-security-settings"></a>Configurações de segurança do sistema

### <a name="password"></a>Senha

- **Comprimento mínimo da senha:** - Com suporte no Windows 8.1.

Especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve conter.

Para dispositivos acessados com uma Conta da Microsoft, a política de conformidade não será avaliada corretamente se o **Comprimento mínimo da senha** tiver mais de oito caracteres ou se o **Número mínimo de conjuntos de caracteres** for maior do que dois.

- **Tipo de senha necessária** – Com suporte no Windows RT, Windows RT 8.1 e Windows 8.1

Especifique se os usuários devem criar uma senha **Alfanumérica** ou **Numérica**.

- **Número mínimo de conjuntos de caracteres** – Com suporte no Windows RT, Windows RT 8.1 e Windows 8.1. Se **Tipo de senha necessário** for definido como **Alfanumérico**, essa configuração especificará o número mínimo de conjuntos de caracteres que a senha deve conter. Os quatro conjuntos de caracteres são:
  - Letras minúsculas
  - Letras maiúsculas
  - Símbolos
  - Números: definir um número mais alto para essa configuração exigirá que os usuários criem senhas mais complexas.

Para dispositivos acessados com uma Conta da Microsoft, a política de conformidade não é avaliada corretamente se o **Comprimento mínimo da senha** tiver mais de oito caracteres ou se o **Número mínimo de conjuntos de caracteres** for maior do que dois.

- **Minutos de inatividade antes da senha ser necessária:** - Com suporte no Windows RT, Windows RT 8.1 e Windows 8.1

Especifique o tempo ocioso antes que o usuário precise inserir novamente sua senha.

- **Expiração de senha (dias)** – Com suporte no Windows RT, Windows RT 8.1 e Windows 8.1.

Selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.

- **Lembrar histórico de senha:** - Com suporte no Windows RT, Windows RT e Windows 8.1.

Use essa configuração em conjunto com **Evitar a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.

- **Evitar a reutilização de senhas anteriores:** - Com suporte no Windows RT, Windows RT 8.1 e Windows 8.1

Se a opção **Lembrar Histórico de Senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.


## <a name="device-health-settings"></a>Configurações de integridade do dispositivo

- **Exigir que os dispositivos sejam relatados como íntegros:** - Com suporte em dispositivos Windows 10. Você pode definir uma regra para exigir que os dispositivos Windows 10 sejam relatados como íntegros nas Políticas de Conformidade novas ou existentes. Se essa configuração estiver habilitada, dispositivos Windows 10 serão avaliados por meio do HAS (Serviço de Atestado de Integridade) para os seguintes pontos de dados:
  - **BitLocker habilitado**: quando o Bitlocker está ativado, o dispositivo é capaz de proteger os dados armazenados na unidade do acesso não autorizado quando o sistema é desligado ou entra no modo de hibernação. A Criptografia de Unidade de Disco Windows BitLocker criptografa todos os dados armazenados no volume do sistema operacional Windows. O BitLocker usa o TPM para ajudar a proteger o sistema operacional Windows e os dados de usuário e ajuda a garantir que um computador não foi violado, mesmo se tiver sido deixado sem supervisão, tiver sido perdido ou roubado. Se o computador estiver equipado com um TPM compatível, o BitLocker usará o TPM para bloquear as chaves de criptografia que protegem os dados. Consequentemente, as chaves não poderão ser acessadas até que o TPM verifique o estado do computador
  - **Integridade de código habilitada:** a integridade de código é um recurso que valida a integridade de um driver ou arquivo do sistema cada vez que ele é carregado na memória. A integridade do código detecta se um arquivo de sistema ou de driver não assinado está sendo carregado no kernel, ou se um arquivo do sistema foi modificado por software mal-intencionado que está sendo executado por uma conta de usuário com privilégios de administrador.
  - **Inicialização Segura habilitada:** quando a Inicialização Segura está habilitada, o sistema é forçado a inicializar para um estado confiável de fábrica. Além disso, quando a Inicialização Segura é habilitada, os principais componentes usados para inicializar o computador devem ter assinaturas criptográficas corretas que são confiáveis para a organização que fabricou o dispositivo. O firmware UEFI confirma isso antes de permitir que o computador seja iniciado. Se todos os arquivos foram violados, interrompendo sua assinatura, o sistema não inicializará.
  - **Antimalware de Início Antecipado habilitado:** o ELAM (Antimalware de Início Antecipado) fornece proteção para os computadores na sua rede quando eles são iniciados e antes de inicializar drivers de terceiros.

Para obter informações sobre como funciona o serviço HAS, consulte [CSP do Estado de Integridade](https://msdn.microsoft.com/library/dn934876.aspx).

## <a name="device-property-settings"></a>Configurações de propriedade do dispositivo

- **Sistema operacional mínimo necessário:** - Com suporte no Windows 8.1 e no Windows 10.

Especifique o número de major.minor.build aqui. O número de versão deve corresponder à versão retornada pelo comando ```winver```.

Quando um dispositivo tiver uma versão mais antiga que a versão de sistema operacional especificada, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seus dispositivos, quando então será possível acessar os recursos da empresa.

- **Sistema operacional máximo permitido:** - Com suporte no Windows 8.1 e no Windows 10.

Quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.

Para localizar a versão do sistema operacional que deve ser usada para as configurações **Sistema operacional mínimo necessário** e **Versão máxima do sistema operacional permitida**, execute o comando **winver** no prompt de comando. O comando winver retorna a versão relatada do sistema operacional.+

- Computadores com Windows 8.1 retornam a versão **3**. Se a regra de versão do sistema operacional for definida como Windows 8.1 para Windows, então o dispositivo será relatado como não compatível mesmo que o dispositivo tenha o Windows 8.1.
- Em computadores que executam o Windows 10, a versão deve ser definida como &quot;10.0&quot;+ o número de build do sistema operacional retornado pelo comando winver.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->

