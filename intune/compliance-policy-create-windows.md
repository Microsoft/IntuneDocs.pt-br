---
title: Criar política de conformidade para dispositivo Windows no Microsoft Intune – Azure | Microsoft Docs
description: Criar ou configurar uma política de conformidade de dispositivo do Microsoft Intune para Windows Phone 8.1, Windows 8.1 e posterior e dispositivos com Windows 10 e posteriores. Verifique a conformidade com o sistema operacional mínimo e máximo, defina restrições e tamanho de senha, exija o BitLocker, verifique se há soluções antivírus de terceiros, defina o nível de ameaça aceitável e habilite a criptografia no armazenamento de dados, incluindo o Surface Hub e o Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 11ccace4ca8e43e09b8aebeb92530629cf50a472
ms.sourcegitcommit: bea4a81d262607c6e9dd1e26f5cd1a2faf7d051b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45602309"
---
# <a name="add-a-device-compliance-policy-for-windows-devices-in-intune"></a>Adicionar uma política de conformidade de dispositivo para dispositivos Windows no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uma política de conformidade de dispositivos do Intune para Windows especifica as regras e configurações que dispositivos Windows precisam cumprir para serem considerados em conformidade. Você pode usar essas políticas com acesso condicional para permitir ou bloquear o acesso aos recursos da empresa. Você também pode obter relatórios de dispositivo e realizar ações de não conformidade. As políticas de conformidade de dispositivo são criadas para cada plataforma no Portal do Azure no Intune. Para saber mais sobre as políticas de conformidade e qualquer pré-requisito, veja a [Introdução às políticas de conformidade do dispositivo](device-compliance-get-started.md).

A tabela a seguir descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional.

---------------------------

| **Configuração de política** | **Windows 8.1 e posterior** | **Windows Phone 8.1 e posterior** |
|----| ----| --- |
| **Configuração de senha ou PIN** | Corrigida | Corrigida |   
| **Criptografia de dispositivo** | Não aplicável | Corrigida |   
| **Dispositivo desbloqueado ou com raiz** | Não Aplicável | Não Aplicável |  
| **Perfil de email** | Não Aplicável | Não Aplicável |   
| **Versão mínima do SO** | Em Quarentena | Em Quarentena |   
| **Versão máxima do SO** | Em Quarentena | Em Quarentena |   
| **Atestado de integridade do Windows** | Em quarentena: Windows 10 e Windows 10 Mobile|Não aplicável: Windows 8.1 |

-------------------------------

**Remediado** = o sistema operacional do dispositivo impõe a conformidade. (Por exemplo, o usuário é forçado a definir um PIN.)

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. (Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo.) Quando o dispositivo não é compatível, ocorrem as seguintes ações:

- O dispositivo será bloqueado se uma política de acesso condicional se aplicar ao usuário.
- O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

## <a name="create-a-device-compliance-policy"></a>Criar uma política de conformidade do dispositivo

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. Para **Plataforma**, selecione **Windows Phone 8.1**, **Windows 8.1 e posterior** ou **Windows 10 e posterior**.
6. Escolha **Definição de Configurações** para inserir as configurações de **Integridade do Dispositivo**, **Propriedades do Dispositivo** e **Segurança do Sistema**. Quando terminar, selecione **OK** e **Criar**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="windows-81-devices-policy-settings"></a>Configurações de política de dispositivos com Windows 8.1

Essas configurações de política aplicam-se a dispositivos que executam as seguintes plataformas:

- Windows Phone 8.1
- Windows 8.1 e posterior

### <a name="device-properties"></a>Propriedades do dispositivo

- **Sistema operacional mínimo exigido**: quando um dispositivo não atender ao requisito mínimo da versão do sistema operacional, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seu dispositivo e, depois disso, poderá ter acesso aos recursos da empresa.
- **Versão do sistema operacional máxima permitida**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado. O usuário deverá contatar seu administrador de TI. Até que haja uma alteração de regra para permitir a versão do sistema operacional, este dispositivo não poderá acessar os recursos da empresa.

Computadores com Windows 8.1 retornam a versão **3**. Se a regra de versão do sistema operacional for definida como Windows 8.1 para Windows, então o dispositivo será relatado como não compatível mesmo que o dispositivo tenha o Windows 8.1.

### <a name="system-security"></a>Segurança do sistema

#### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo.
- **Senhas simples**: defina como **Bloquear** para que os usuários não possam criar uma senha simples como **1234** ou **1111**. Definido como **Não configurado** para permitir que os usuários criem senhas como **1234** ou **1111**.
- **Tamanho mínimo da senha**: insira o número mínimo de dígitos ou de caracteres que a senha deve ter.

  Para dispositivos que executam o Windows e são acessados com uma conta da Microsoft, a política de conformidade não consegue avaliar corretamente:
  - Se o comprimento mínimo da senha tiver mais de oito caracteres
  - Ou se o número mínimo de conjunto de caracteres for maior que dois

- **Tipo de senha**: escolha se uma senha deve ter apenas caracteres **numéricos** ou se deve haver uma combinação de números e outros caracteres (**alfanuméricos**).
  
  - **Número de caracteres não alfanuméricos na senha:** se o **Tipo de senha necessário** for definido como **Alfanumérico**, essa configuração especificará o número mínimo de conjuntos de caracteres que a senha deve conter. Os quatro conjuntos de caracteres são:
    - Letras minúsculas
    - Letras maiúsculas
    - Símbolos
    - Números

    Definir um número mais alto exige que o usuário crie uma senha mais complexa. Para dispositivos que executam o Windows e são acessados com uma conta da Microsoft, a política de conformidade não é avaliada corretamente quando o comprimento mínimo da senha tem mais de oito caracteres ou o número mínimo de conjuntos de caracteres é maior que dois.

- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias)**: selecione o número de dias antes que a senha expire e seja preciso criar uma nova.
- **Número de senhas anteriores para evitar a reutilização**: insira o número de senhas usadas anteriormente que não podem ser utilizadas.

#### <a name="encryption"></a>Criptografia

- **Exigir criptografia no dispositivo móvel**: **exigir** que o dispositivo seja criptografado para se conectar aos recursos de armazenamento de dados.

## <a name="windows-10-and-later-policy-settings"></a>Configurações de política do Windows 10 e posteriores

### <a name="device-health"></a>Device health

- **Exigir BitLocker**: quando o BitLocker está ativado, o dispositivo pode proteger os dados armazenados na unidade contra acesso não autorizado, quando o sistema é desligado ou entra no modo de hibernação. A Criptografia de Unidade de Disco Windows BitLocker criptografa todos os dados armazenados no volume do sistema operacional Windows. O BitLocker usa o TPM para ajudar a proteger o sistema operacional Windows e os dados do usuário. Ele também ajuda a garantir que um computador não seja violado, mesmo se ficar aberto, se for perdido ou roubado. Se o computador estiver equipado com um TPM compatível, o BitLocker usará o TPM para bloquear as chaves de criptografia que protegem os dados. Como resultado, as chaves não podem ser acessadas até que o TPM tenha verificado o estado do computador.
- **Exigir que a Inicialização Segura seja habilitada no dispositivo:** quando a Inicialização Segura está habilitada, o sistema é forçado a inicializar para um estado confiável de fábrica. Além disso, quando a Inicialização Segura é habilitada, os principais componentes usados para inicializar o computador devem ter assinaturas criptográficas corretas que são confiáveis para a organização que fabricou o dispositivo. O firmware UEFI confirma essa assinatura antes de permitir que o computador seja iniciado. Se todos os arquivos foram violados, interrompendo sua assinatura, o sistema não inicializará.

  > [!NOTE]
  > A configuração **Requer que Inicialização Segura esteja habilitada no dispositivo** é compatível com dispositivos TPM 1.2 e 2.0. Para dispositivos que não dão suporte a TPM 2.0 ou posterior, o status da política do Intune aparece como **Não em Conformidade**. Essa é uma limitação do serviço [Atestado de Integridade do Dispositivo](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation) no Windows 10.

- **Exigir integridade de código:** a integridade de código é um recurso que valida a integridade de um driver ou arquivo do sistema cada vez que ele é carregado na memória. A integridade de código detecta quando um arquivo de sistema ou driver não assinado está sendo carregado no kernel. Ou se um arquivo de sistema foi modificado por software mal-intencionado executado por uma conta de usuário com privilégios de administrador.

Confira [CSP do atestado de integridade](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp) para obter detalhes de como funciona o serviço HAS.

Para configurar o Windows Defender ATP (Proteção Avançada contra Ameaças) como seu serviço de defesa contra ameaças, veja [Habilitar o Windows Defender ATP com acesso condicional](advanced-threat-protection.md).

### <a name="device-properties"></a>Propriedades do dispositivo

- **Versão mínima do SO**: insira a versão mínima permitida no formato **número major.minor.build.CU**. Para obter o valor correto, abra um prompt de comando e digite `ver`. O comando `ver` retorna a versão no seguinte formato:

  `Microsoft Windows [Version 10.0.17134.1]`

  Quando um dispositivo tem uma versão mais antiga que a versão de sistema operacional especificada, ele é relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seus dispositivos, quando então será possível acessar os recursos da empresa.

- **Versão máxima do SO**: insira a versão máxima permitida no formato de **número major.minor.build.revision**. Para obter o valor correto, abra um prompt de comando e digite `ver`. O comando `ver` retorna a versão no seguinte formato:

  `Microsoft Windows [Version 10.0.17134.1]`

  Quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.

- **Sistema operacional mínimo necessário para dispositivos móveis**: insira a versão mínima permitida, no formato de número major.minor.build.

  Quando um dispositivo tem uma versão mais antiga que a versão de sistema operacional especificada, ele é relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar seus dispositivos, quando então será possível acessar os recursos da empresa.

- **Sistema operacional máximo necessário para dispositivos móveis**: insira a versão máxima permitida, no número major.minor.build.

  Quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI. Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.

- **Versões de sistema operacional válidas**: insira um intervalo para as versões de sistemas de operacionais aceitáveis, incluindo uma mínima e uma máxima. Também é possível **Exportar** uma lista de arquivos CSV (valores separados por vírgula) desses números de build de SO aceitáveis.

### <a name="system-security-settings"></a>Configurações de segurança do sistema

#### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo.
- **Senhas simples**: defina como **Bloquear** para que os usuários não possam criar uma senha simples como **1234** ou **1111**. Definido como **Não configurado** para permitir que os usuários criem senhas como **1234** ou **1111**.
- **Tipo de senha**: escolha se uma senha deve ter apenas caracteres **numéricos** ou se deve haver uma combinação de números e outros caracteres (**alfanuméricos**).

  - **Número de caracteres não alfanuméricos na senha:** se o **Tipo de senha necessário** for definido como **Alfanumérico**, essa configuração especificará o número mínimo de conjuntos de caracteres que a senha deve conter. Os quatro conjuntos de caracteres são:
    - Letras minúsculas
    - Letras maiúsculas
    - Símbolos
    - Números

    Definir um número mais alto exige que o usuário crie uma senha mais complexa.

- **Tamanho mínimo da senha**: insira o número mínimo de dígitos ou de caracteres que a senha deve ter.
- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias)**: selecione o número de dias antes que a senha expire e seja preciso criar uma nova.
- **Número de senhas anteriores para evitar a reutilização**: insira o número de senhas usadas anteriormente que não podem ser utilizadas.
- **Exigir senha quando o dispositivo retornar do estado ocioso (Mobile e Holographic)**: forçar os usuários a inserirem a senha sempre que o dispositivo retornar do estado ocioso.

#### <a name="encryption"></a>Criptografia

- **Criptografia de armazenamento de dados em um dispositivo**: escolha **Exigir** para criptografar o armazenamento de dados em seus dispositivos.

#### <a name="device-security"></a>Segurança de dispositivo

- **Antivírus**: quando definido como **Obrigatório**, você pode verificar a conformidade usando soluções antivírus registradas na Central de Segurança do Windows, como Symantec e Windows Defender. Quando **Não configurado**, o Intune não verifica se há soluções antivírus instaladas no dispositivo.
- **Software antispyware**: quando definido como **Obrigatório**, você pode verificar a conformidade usando soluções de software antispyware registradas na Central de Segurança do Windows, como Symantec e Windows Defender. Quando **Não configurado**, o Intune não verifica se há alguma solução de software antispyware instalada no dispositivo.

### <a name="windows-defender-atp"></a>Windows Defender ATP

- **Exigir que o dispositivo esteja na pontuação de risco do computador ou abaixo**: use essa configuração para utilizar a avaliação de risco dos seus serviços de ameaça de defesa como uma condição para a conformidade. Selecione o nível máximo de ameaça permitido:
  - **Limpar**: essa opção é a mais segura, porque o dispositivo não pode ter nenhuma ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, ele será avaliado como não compatível.
  - **Baixo**: o dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como em conformidade se as ameaças existentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele é não compatível.
  - **Alta**: esta opção é a menos segura e permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

O Windows Holographic for Business usa a plataforma **Windows 10 e posterior**. O Windows Holographic for Business é compatível com a seguinte configuração:

- **Segurança do Sistema** > **Criptografia** > **Criptografia de armazenamento de dados no dispositivo**.

Para verificar a criptografia do dispositivo no Microsoft HoloLens, consulte [Verificar criptografia do dispositivo](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## <a name="surface-hub"></a>Surface Hub
O Surface Hub usa a plataforma **Windows 10 e posterior**. Os Surface Hubs têm suporte para conformidade e acesso condicional. Para habilitar esses recursos em Surface Hubs, recomendamos que você [habilite o registro automático do Windows 10](windows-enroll.md) no Intune (também exige o Azure Active Directory (AAD)) e marque os dispositivos do Surface Hub como grupos de dispositivos. Os Surface Hubs deve ser unidos no Azure Active Directory para que funciona a conformidade e o acesso condicional.

Veja [configurar o registro para dispositivos Windows](windows-enroll.md) para obter diretrizes.

## <a name="assign-user-or-device-groups"></a>Atribuir grupos de usuários ou dispositivos

1. Escolha uma política que você configurou. As políticas existentes estão em **Conformidade do dispositivo** > **Políticas**.
2. Escolha a política e as **Atribuições**. Você pode incluir ou excluir grupos de segurança do Azure AD.
3. Escolha **Grupos selecionados** para ver os grupos de segurança do Azure AD. Selecione os grupos de usuários aos quais deseja que essa política seja aplicada e escolha **Salvar** para implantar a política.

Você aplicou a política. Os dispositivos usados pelos usuários que são direcionados pela política são avaliados quanto à conformidade.

## <a name="next-steps"></a>Próximas etapas
[Automatizar email e adicionar ações para dispositivos não compatíveis](actions-for-noncompliance.md)  
[Monitorar as políticas de conformidade do dispositivo do Intune](compliance-policy-monitor.md)
