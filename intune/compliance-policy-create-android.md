---
title: Criar política de conformidade para dispositivo Android no Microsoft Intune – Azure | Microsoft Docs
description: Criar ou configurar uma política de conformidade do dispositivo do Microsoft Intune para dispositivos Android. Escolha para desbloquear dispositivos, defina o nível de ameaça aceitável, verifique o Google Play, insira a versão mínima e máxima de versão do sistema operacional, escolha seus requisitos de senha e permita sideload dos aplicativos.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: cb5fc7256e68b8ea10ba1b3ddd7cfe6ed44bd544
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180605"
---
# <a name="add-a-device-compliance-policy-for-android-devices-in-intune"></a>Adicionar uma política de conformidade do dispositivo para dispositivos Android no Intune

Uma política de conformidade de dispositivos do Intune para Android especifica as regras e configurações que dispositivos do Android precisam cumprir para serem considerados em conformidade. Você pode usar essas políticas com [acesso condicional](conditional-access.md) para permitir ou bloquear o acesso aos recursos da organização. Você também pode obter relatórios de dispositivo e realizar ações de não conformidade. 

Para saber mais sobre as políticas de conformidade e qualquer pré-requisito, veja a [Introdução às políticas de conformidade do dispositivo](device-compliance-get-started.md).

Este tópico lista as configurações que você pode usar dentro de uma política de conformidade para dispositivos Android.

## <a name="non-compliance-and-conditional-access"></a>Não conformidade e acesso condicional

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

**Remediado** = o sistema operacional do dispositivo impõe a conformidade. Por exemplo, o usuário é forçado a definir um PIN.

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo. Quando o dispositivo não é compatível, ocorrem as seguintes ações:

  - O dispositivo será bloqueado se uma política de acesso condicional se aplicar ao usuário.
  - O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

## <a name="create-a-device-compliance-policy"></a>Criar uma política de conformidade do dispositivo

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. Para **Plataforma**, selecione **Android**. 
5. Escolha **Definir Configurações**. Insira as configurações de **Integridade do Dispositivo**, **Propriedades do Dispositivo** e **Segurança do Sistema**, conforme descrito neste artigo.

## <a name="device-health"></a>Device health

- **Dispositivos desbloqueados por rooting**: escolha **Bloquear** para marcar dispositivos desbloqueados por rooting (com jailbreak) como não estando em conformidade. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Exigir que o dispositivo esteja no ou sob o nível de ameaça de dispositivo**: use esta configuração para utilizar a avaliação de sua solução de Lookout MTP como condição para a conformidade. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade. Para usar essa configuração, escolha o nível de ameaça permitido:
  - **Protegido**: essa opção é a mais segura, porque o dispositivo não pode ter ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, será avaliado que ele não está em conformidade.
  - **Baixo**: o dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como em conformidade se as ameaças existentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele não está em conformidade.
  - **Alta**: esta opção é a menos segura e permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.
- **Google Play Services está configurado**: **exige** que o aplicativo de Google Play Services esteja instalado e habilitado. Os serviços do Google Play permitem atualizações de segurança e são uma dependência em nível de base para muitos recursos de segurança em dispositivos certificados do Google. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Atualizar provedor de segurança**: **exige** que um provedor de segurança atualizado possa proteger um dispositivo contra vulnerabilidades conhecidas. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Verificação de ameaça em aplicativos**: **exige** que o recurso **Verificar Aplicativos** do Android esteja habilitado. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  > [!NOTE]
  > Na plataforma Android herdada, esse recurso é uma configuração de conformidade. O Intune só pode verificar se essa configuração está habilitada no nível do dispositivo.

- **Atestado de dispositivo SafetyNet**: insira o nível de [atestado de SafetyNet](https://developer.android.com/training/safetynet/attestation.html) que deve ser atendido. Suas opções:
  - **Não configurado** (padrão): a configuração não é avaliada em relação a estar ou não em conformidade.
  - **Verificação básica de integridade**
  - **Verifique a integridade básica e os dispositivos certificados**

## <a name="device-property-settings"></a>Configurações de propriedade do dispositivo

- **Sistema operacional mínimo**: quando um dispositivo não atender ao requisito mínimo da versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seu dispositivo e, depois disso, poderá ter acesso aos recursos da empresa.
- **Versão do sistema operacional máxima**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado. O usuário deverá contatar seu administrador de TI. Até uma regra ser alterada para permitir a versão do sistema operacional, este dispositivo não poderá acessar os recursos da empresa.

## <a name="system-security-settings"></a>Configurações de segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Tamanho mínimo da senha**: insira o número mínimo de dígitos ou de caracteres que a senha do usuário deve ter.
- **Tipo de senha necessária**: escolha se uma senha deve incluir apenas caracteres numéricos ou uma combinação de números e outros caracteres. Suas opções:
  - **Padrão do dispositivo**
  - **Biométrico de segurança baixa**
  - **Pelo menos numérico** (padrão)
  - **Numérico complexo**: números repetidos ou consecutivos, como `1111` ou `1234`, não são permitidos.
  - **Pelo menos, alfabético** 
  - **Pelo menos, alfanumérico**
  - **Pelo menos alfanumérico com símbolos**

- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha. Quando você escolhe **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.
- **Expiração da senha (dias)**: selecione o número de dias antes que a senha expire e o usuário precise criar uma nova.
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

Quando terminar, selecione **OK** > **OK** para salvar suas alterações.

## <a name="locations"></a>Locais

Em sua política, escolha entre locais existentes. Ainda não tem um local? [Usar locais (limite de rede) no Intune](use-network-locations.md) fornece alguma orientação.

1. Escolha **Locais**.
2. Na lista, verifique seu local e escolha **Selecionar**.
3. **Salve** a política.

## <a name="actions-for-noncompliance"></a>Ações de não conformidade

Selecione **Ações para não conformidade**. A ação padrão marca o dispositivo como em não conformidade imediatamente.

Você pode alterar a agenda quando o dispositivo está marcado como não em conformidade, como após um dia. Você também pode configurar uma segunda ação que envia um email para o usuário quando o dispositivo não está em conformidade.

[Adicionar ações a dispositivos que não estão em conformidade](actions-for-noncompliance.md) apresenta mais informações, incluindo como criar um email de notificação para seus usuários.

Por exemplo, você está usando o recurso Locais e adiciona uma localização em uma política de conformidade. A ação padrão para não conformidade se aplica quando você seleciona pelo menos uma localização. Se o dispositivo não estiver conectado a locais selecionados, imediatamente será considerado que ele não está em conformidade. Você pode dar aos usuários um período de cortesia, como um dia.

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
[Configurações da política de conformidade para Android Enterprise](compliance-policy-create-android-for-work.md)
