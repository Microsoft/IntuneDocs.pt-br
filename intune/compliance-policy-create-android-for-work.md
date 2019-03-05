---
title: Criar política de conformidade para Android Enterprise no Microsoft Intune – Azure | Microsoft Docs
description: Criar ou configurar uma política de conformidade de dispositivo do Microsoft Intune para dispositivos de perfil de trabalho ou Android Enterprise. Escolha para desbloquear dispositivos, defina o nível de ameaça aceitável, verifique o Google Play, insira a versão mínima e máxima de versão do sistema operacional, escolha seus requisitos de senha e permita sideload dos aplicativos.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b1c89257a05ad1aa68ee328253c2e954cb77da47
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57229778"
---
# <a name="add-a-device-compliance-policy-for-android-enterprise-devices-in-intune"></a>Adicionar uma política de conformidade do dispositivo para dispositivos Android Enterprise no Intune

As políticas de conformidade do dispositivo são um recurso importante ao usar o Intune para proteger recursos da sua organização. No Intune, você pode criar regras e configurações que dispositivos precisam cumprir para serem considerados em conformidade, como um comprimento de senha. Se o dispositivo não estiver em conformidade, você poderá bloquear o acesso aos dados e recursos usando [acesso condicional](conditional-access.md). 

Você também pode obter relatórios de dispositivo e executar ações para casos de não conformidade, como enviar um email de notificação ao usuário. Para saber mais sobre as políticas de conformidade e qualquer pré-requisito, veja a [Introdução às políticas de conformidade do dispositivo](device-compliance-get-started.md).

Este artigo lista as configurações que você pode usar dentro de uma política de conformidade para dispositivos que executem o Android Enterprise.

## <a name="non-compliance-and-conditional-access"></a>Não conformidade e acesso condicional

A tabela a seguir descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional.

--------------------------

|**configuração de política**| **Perfil do Android Enterprise** |
| --- | --- |
| **Configuração de senha ou PIN** |  Em Quarentena |
| **Criptografia de dispositivo** |  Em Quarentena |
| **Dispositivo desbloqueado ou com raiz** | Em Quarentena (não é uma configuração) |
| **perfil de email** | Não Aplicável |
| **Versão mínima do SO** | Em Quarentena |
| **Versão máxima do SO** | Em Quarentena |
| **Atestado de integridade do Windows** |Não Aplicável |

**Remediado** = o sistema operacional do dispositivo impõe a conformidade. Por exemplo, o usuário é forçado a definir um PIN.

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo. Quando o dispositivo não está em conformidade, ocorrem as seguintes ações:

  - Se uma política de acesso condicional se aplicar ao usuário, o dispositivo será bloqueado.
  - O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

## <a name="create-a-device-compliance-policy"></a>Criar uma política de conformidade do dispositivo

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. Para **Plataforma**, selecione **Android Enterprise**. 
5. Escolha **Definir Configurações**. Insira as configurações de **Integridade do Dispositivo**, **Propriedades do Dispositivo** e **Segurança do Sistema**, conforme descrito neste artigo.

## <a name="device-health"></a>Device health

- **Dispositivos desbloqueados por rooting**: Escolha **Bloquear** para marcar dispositivos desbloqueados por rooting (com jailbreak) como não estando em conformidade. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Requer que o dispositivo esteja em nível igual ou inferior ao Nível de Ameaças do Dispositivo**: Use essa configuração para fazer a avaliação de risco da solução Lookout MTP como uma condição para conformidade. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade. Para usar essa configuração, escolha o nível de ameaça permitido:
  - **Protegido**: Essa opção é a mais segura e significa que o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, será avaliado que ele não está em conformidade.
  - **Baixo**: O dispositivo será avaliado como compatível se houver apenas ameaças de nível baixo. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: O dispositivo será avaliado como compatível se as ameaças presentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele não está em conformidade.
  - **Alto**: Essa opção é a menos segura, porque permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.
- **O Google Play Services está configurado**: **Exige** que o aplicativo de serviços do Google Play esteja instalado e habilitado. Os serviços do Google Play permitem atualizações de segurança e são uma dependência em nível de base para muitos recursos de segurança em dispositivos certificados do Google. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Provedor de segurança atualizado**: **Exige** que um provedor de segurança atualizado possa proteger um dispositivo contra vulnerabilidades conhecidas. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Atestado de dispositivo SafetyNet**: Insira o nível de [atestado de SafetyNet](https://developer.android.com/training/safetynet/attestation.html) que deve ser atendido. Suas opções:
  - **Não configurado** (padrão): A configuração não é avaliada em relação a estar ou não em conformidade.
  - **Verificação básica de integridade**
  - **Verifique a integridade básica e os dispositivos certificados**

#### <a name="threat-scan-on-apps"></a>Verificação de ameaças em aplicativos

Em dispositivos Android Enterprise, a configuração **Verificação de ameaças em aplicativos** é uma política de configuração. Veja [Configurações de restrição de dispositivo Android Enterprise](device-restrictions-android-for-work.md).

## <a name="device-properties-settings"></a>Configurações de propriedades do dispositivo

- **Versão mínima do SO**: Quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seu dispositivo e, depois disso, poderá acessar os recursos da empresa.
- **Versão máxima do SO**: Quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela na regra, o acesso aos recursos da empresa será bloqueado. E o usuário deverá contatar seu administrador de TI. Até uma regra ser alterada para permitir a versão do sistema operacional, este dispositivo não poderá acessar os recursos da empresa.

## <a name="system-security-settings"></a>Configurações de segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear os dispositivos móveis**: **Exige** que os usuários insiram uma senha antes que possam acessar seu dispositivo. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade. Essa configuração é aplicada no nível do dispositivo. Se você precisar exigir senha apenas no nível do perfil de trabalho, use uma política de configuração. Confira [Definições de configuração de dispositivo do Android Enterprise](device-restrictions-android-for-work.md).
- **Comprimento mínimo da senha**: Insira o número mínimo de dígitos ou caracteres que a senha do usuário deve ter.
- **Tipo de senha necessária**: Escolha se uma senha deve incluir apenas caracteres numéricos ou uma combinação de números e outros caracteres. Suas opções:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Pelo menos numérico** (padrão)
  - **Complexo numérico**
  - **Pelo menos, alfabético**
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**

- **Máximo de minutos de inatividade antes de a senha ser necessária**: Insira o tempo ocioso antes que o usuário precise inserir novamente sua senha. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Expiração da senha (dias)**: Selecione o número de dias antes que a senha expire e seja preciso criar uma nova.
- **Número de senhas anteriores para evitar a reutilização**: Insira o número de senhas recentes que não podem ser reutilizadas. Use essa configuração para impedir que o usuário crie senhas usadas anteriormente.

### <a name="encryption"></a>Criptografia

- **Criptografia de armazenamento de dados no dispositivo**: Escolha **Exigir** para criptografar o armazenamento de dados em seus dispositivos. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade. 

  Você não precisa definir essa configuração porque os dispositivos de perfil de trabalho do Android impõem a criptografia.

### <a name="device-security"></a>Segurança de dispositivo

- **Bloquear aplicativos de fontes desconhecidas**: Escolha **bloquear** dispositivos com fontes de "Segurança > Fontes Desconhecidas" habilitadas (com suporte em Android 4.0 – Android 7.x; sem suporte em Android 8.0 e posteriores). Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  Para o sideload de aplicativos, as fontes desconhecidas devem ser permitidas. Se você não tiver aplicativos Android com sideload, defina esse recurso como **Bloquear** para habilitar essa política de conformidade. 

  > [!IMPORTANT]
  > O sideload de aplicativos exigem que a configuração **Bloquear aplicativos de fontes desconhecidas** esteja habilitada. Aplique esta política de conformidade somente se você não estiver fazendo o sideload de aplicativos Android nos dispositivos.

  Você não precisa definir essa configuração, pois os dispositivos com perfil de trabalho do Android sempre restringem a instalação de fontes desconhecidas.

- **Integridade de tempo de execução do aplicativo Portal da Empresa**: Escolha **Exigir** para confirmar que o aplicativo Portal da Empresa cumpre todos os requisitos a seguir:

  - Tem o ambiente de tempo de execução padrão instalado
  - Está assinado corretamente
  - Não está no modo de depuração
  - É instalado de uma origem conhecida

  Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

- **Bloquear a depuração de USB no dispositivo**: Escolha **Bloquear** para impedir que os dispositivos usem o recurso de depuração de USB. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  Você não precisa definir essa configuração porque a depuração de USB já está desabilitada em dispositivos de perfil de trabalho Android.

- **Nível mínimo do patch de segurança**: Selecione o nível de patch de segurança mais antigo que um dispositivo pode ter. Dispositivos que não estão pelo menos nesse nível de patch não estão em conformidade. A data deve ser inserida no formato *AAAA-MM-DD*.

Quando terminar, selecione **OK** > **OK** para salvar suas alterações.

## <a name="actions-for-noncompliance"></a>Ações de não conformidade

Selecione **Ações para não conformidade**. A ação padrão marca o dispositivo como em não conformidade imediatamente.

Você pode alterar a agenda quando o dispositivo está marcado como não em conformidade, como após um dia. Você também pode configurar uma segunda ação que envia um email para o usuário quando o dispositivo não está em conformidade.

[Adicionar ações a dispositivos que não estão em conformidade](actions-for-noncompliance.md) apresenta mais informações, incluindo como criar um email de notificação para seus usuários.

## <a name="scope-tags"></a>Marcas de escopo

Marcas de escopo são uma ótima maneira de atribuir políticas a grupos específicos, como Vendas, Engenharia, RH e assim por diante. Você pode adicionar marcas de um escopo a políticas de conformidade. Veja [Usar marcas de escopo para filtrar políticas](scope-tags.md). 

## <a name="assign-user-groups"></a>Atribuir grupos de usuários

Depois de criar uma política, ela não fará nada até que você atribua a política. Para atribuir a política: 

1. Escolha uma política que você configurou. As políticas existentes estão em **Conformidade do dispositivo** > **Políticas**.
2. Escolha a política e as **Atribuições**. Você pode incluir ou excluir grupos de segurança do Azure Active Directory (AD).
3. Escolha **Grupos selecionados** para ver os grupos de segurança do Azure AD. Selecione os grupos de usuários aos quais deseja que essa política seja aplicada e escolher **Salvar** para implantar a política para os usuários.

Você aplicou a política aos usuários. Os dispositivos usados pelos usuários afetados pela política são avaliados quanto à conformidade.

## <a name="next-steps"></a>Próximas etapas
[Automatizar email e adicionar ações para dispositivos não compatíveis](actions-for-noncompliance.md)  
[Monitorar as políticas de conformidade do dispositivo do Intune](compliance-policy-monitor.md)  
[Configurações da política de conformidade para o Android](compliance-policy-create-android.md)
