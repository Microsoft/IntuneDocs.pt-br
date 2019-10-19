---
title: Configurações de conformidade do Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações que você pode usar ao definir a conformidade para seus dispositivos Windows 10, Windows Holographic e Surface Hub no Microsoft Intune. Verifique a conformidade no sistema de operacional mínimo e máximo, defina restrições de senha e comprimento, verifique soluções de AV (antivírus) de parceiros, habilite a criptografia no armazenamento de dados e muito mais.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/10/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2e427fe0889dcfb51ba5be322ed4db566cc29e9d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502473"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Configurações do Windows 10 e posteriores para marcar dispositivos como em conformidade ou não em conformidade usando o Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Este artigo lista e descreve as diferentes configurações de conformidade que você pode definir em dispositivos Windows 10 e posteriores no Intune. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para exigir o BitLocker, definir um sistema operacional mínimo e máximo, definir um nível de risco usando a ATP (Proteção Avançada contra Ameaças) do Microsoft Defender e muito mais.

Esse recurso aplica-se a:

- Windows 10 e posterior
- Windows Holographic for Business
- Surface Hub

Como um administrador do Intune, use essas configurações de conformidade para ajudar a proteger os recursos da sua organização. Para saber mais sobre as políticas de conformidade e o que elas fazem, veja a [introdução à conformidade do dispositivo](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Antes de começar

[Criar uma política de conformidade](create-compliance-policy.md#create-the-policy). Em **Plataforma**, selecione **Windows 10 e posteriores**.

## <a name="device-health"></a>Device health

- **Exigir BitLocker**: quando definido como **Exigir**, o dispositivo pode proteger os dados armazenados na unidade contra acesso não autorizado quando o sistema está desligado ou em hibernação. A Criptografia de Unidade de Disco Windows BitLocker criptografa todos os dados armazenados no volume do sistema operacional Windows. O BitLocker usa o TPM para ajudar a proteger o sistema operacional Windows e os dados do usuário. Ele ajuda a confirmar que um computador não será adulterado, mesmo se ficar sem supervisão, for perdido ou roubado. Se o computador estiver equipado com um TPM compatível, o BitLocker usará o TPM para bloquear as chaves de criptografia que protegem os dados. Como resultado, as chaves não poderão ser acessadas até que o TPM confirme o estado do computador.

  Quando definido como **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

- **Exigir que a Inicialização Segura seja habilitada no dispositivo:** quando definido como **Exigir**, o sistema é forçado a inicializar para um estado confiável de fábrica. Quando habilitada, os principais componentes usados para inicializar o computador devem ter assinaturas criptográficas corretas que são confiáveis para a organização que fabricou o dispositivo. O firmware UEFI confirma essa assinatura antes de permitir que o computador seja iniciado. Se algum arquivo for violado, interrompendo sua assinatura, o sistema não inicializará.

  Quando definido como **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

  > [!NOTE]
  > A configuração **Requer que Inicialização Segura esteja habilitada no dispositivo** é compatível com alguns dispositivos TPM 1.2 e 2.0. Para dispositivos que não dão suporte a TPM 2.0 ou posterior, o status da política do Intune aparece como **Não em Conformidade**. Para obter mais informações sobre versões com suporte, veja [Atestado de Integridade do Dispositivo](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Exigir integridade de código:** a integridade de código é um recurso que valida a integridade de um driver ou arquivo do sistema cada vez que ele é carregado na memória. Quando definido como **Exigir**, a integridade de código detecta quando um arquivo de sistema ou driver não assinado está sendo carregado no kernel. Também detecta se um arquivo de sistema é modificado por um software mal-intencionado executado por uma conta de usuário com privilégios de administrador.

  Quando definido como **Não configurado** (padrão), essa configuração não é avaliada de conformidade ou não conformidade.

Mais recursos:

- O [CSP do Atestado de Integridade](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp) tem detalhes de como funciona o serviço HAS.
- [Dica de suporte: como usar configurações de atestado de integridade do dispositivo como parte de sua política de conformidade do Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643)

## <a name="device-properties"></a>Propriedades do dispositivo

- **Versão mínima do SO**: insira a versão mínima permitida no formato **número major.minor.build.CU**. Para obter o valor correto, abra um prompt de comando e digite `ver`. O comando `ver` retorna a versão no seguinte formato:

  `Microsoft Windows [Version 10.0.17134.1]`

  Quando um dispositivo tiver uma versão mais antiga que a versão do sistema operacional que você inseriu, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar o dispositivo. Após a atualização, ele poderá acessar recursos da empresa.

- **Versão máxima do SO**: insira a versão máxima permitida no formato de **número major.minor.build.revision**. Para obter o valor correto, abra um prompt de comando e digite `ver`. O comando `ver` retorna a versão no seguinte formato:

  `Microsoft Windows [Version 10.0.17134.1]`

  Quando um dispositivo estiver usando uma versão de SO posterior à versão inserida, o acesso aos recursos da organização será bloqueado. O usuário final é solicitado a contatar seu administrador de TI. O dispositivo não pode acessar os recursos da organização até a regra ser alterada para permitir a versão do SO.

- **Sistema operacional mínimo necessário para dispositivos móveis**: insira a versão mínima permitida, no formato de número major.minor.build.

  Quando um dispositivo tiver uma versão mais antiga que a versão do sistema operacional que você inseriu, ele será relatado como não compatível. É exibido um link com informações sobre como atualizar. O usuário final pode optar por atualizar o dispositivo. Após a atualização, ele poderá acessar recursos da empresa.

- **Sistema operacional máximo necessário para dispositivos móveis**: insira a versão máxima permitida, no número major.minor.build.

  Quando um dispositivo estiver usando uma versão de SO posterior à versão inserida, o acesso aos recursos da organização será bloqueado. O usuário final é solicitado a contatar seu administrador de TI. O dispositivo não pode acessar os recursos da organização até a regra ser alterada para permitir a versão do SO.

- **Versões de sistema operacional válidas**: insira um intervalo para as versões de sistemas de operacionais aceitáveis, incluindo uma mínima e uma máxima. Também é possível **Exportar** uma lista de arquivos CSV (valores separados por vírgula) desses números de build de SO aceitáveis.

## <a name="configuration-manager-compliance"></a>Conformidade do Configuration Manager

Aplica-se apenas a dispositivos que executam o Windows 10 e posteriores. Os dispositivos que usam apenas o Intune retornam um status não disponível.

- **Exigir conformidade do dispositivo do System Center Configuration Manager**: escolha **Exigir** para forçar todas as configurações (itens de configuração) no System Center Configuration Manager a estarem em conformidade. 

  Por exemplo, você pode exigir que todas as atualizações de software sejam instaladas nos dispositivos. No Configuration Manager, esse requisito tem o estado "Instalado". Se algum programa no dispositivo estiver em um estado desconhecido, o dispositivo estará como não compatível no Intune.
  
  Se o estado for **Não configurado**, o Intune não verificará a conformidade das configurações do Configuration Manager.

## <a name="system-security"></a>Segurança do sistema

### <a name="password"></a>Senha

- **Exigir uma senha para desbloquear dispositivos móveis**: **exija** que os usuários insiram uma senha antes de acessar o dispositivo. Quando **não configurado**, o Intune não avalia o dispositivo para as configurações de senha para fins de conformidade.
- **Senhas simples**: defina como **Bloquear** para que os usuários não possam criar uma senha simples como **1234** ou **1111**. Definido como **Não configurado** para permitir que os usuários criem senhas como **1234** ou **1111**.
- **Tipo de senha**: escolha o tipo de senha ou PIN necessário. Suas opções:

  - **Padrão do dispositivo**: requer uma senha, PIN numérico ou PIN alfanumérico
  - **Numeric**: exigir uma senha ou PIN numérico
  - **Alfanumérico**: exigir uma senha ou PIN alfanumérico. Escolha também a **complexidade da senha**: 
    
    - **Exigir dígitos e letras minúsculas**
    - **Exigir dígitos, letras minúsculas e letras maiúsculas**
    - **Exigir dígitos, letras minúsculas, letras maiúsculas e caracteres especiais**

    > [!TIP]
    > As políticas de senha alfanuméricas podem ser complexas. Incentivamos os administradores a ler os CSPs para obter mais informações:
    >
    > - [CSP DeviceLock/AlphanumericDevicePasswordRequired](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)
    > - [CSP DeviceLock/MinDevicePasswordComplexCharacters](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-mindevicepasswordcomplexcharacters)

- **Tamanho mínimo da senha**: insira o número mínimo de dígitos ou de caracteres que a senha deve ter.
- **Máximo de minutos de inatividade antes que a senha seja exigida**: insira o tempo ocioso antes que o usuário precise digitar novamente a senha.
- **Expiração da senha (dias)** : insira o número de dias antes que a senha expire e seja preciso criar uma nova, de 1 a 730.
- **Número de senhas anteriores para evitar a reutilização**: insira o número de senhas usadas anteriormente que não podem ser utilizadas.
- **Exigir senha quando o dispositivo retornar do estado ocioso (Mobile e Holographic)** : forçar os usuários a inserirem a senha sempre que o dispositivo retornar do estado ocioso.

  > [!IMPORTANT]
  > Quando o requisito de senha é alterado em uma área de trabalho do Windows, os usuários são afetados na próxima vez que fizerem logon, como quando o dispositivo passa de ocioso para ativo. Os usuários com senhas que atendam ao requisito ainda serão solicitados a alterar suas senhas.

### <a name="encryption"></a>Criptografia

- **Criptografia de armazenamento de dados em um dispositivo**: escolha **Exigir** para criptografar o armazenamento de dados em seus dispositivos.

  > [!NOTE]
  > A configuração **Criptografia de armazenamento de dados em um dispositivo** verifica genericamente a presença de criptografia no dispositivo. Para uma configuração de criptografia mais robusta, considere usar **Requer BitLocker**, que aproveita o Atestado de Integridade de Dispositivo do Windows para validar o status do BitLocker no nível do TPM.

### <a name="device-security"></a>Segurança de dispositivo

- **Firewall**: Defina como **exigir** para ativar o Microsoft defender firewall e impedir que os usuários o desativem. **Não configurado** (padrão) não controla o Microsoft defender firewall nem altera as configurações existentes.

  [CSP do firewall](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp)

  > [!NOTE]
  > Se o dispositivo for sincronizado imediatamente após uma reinicialização ou sincronizar imediatamente a ativação do estado de suspensão, essa configuração poderá ser relatada como um **erro**. Esse cenário pode não afetar o status geral de conformidade do dispositivo. Para reavaliar o status de conformidade, [sincronize manualmente o dispositivo](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).

- **Trusted Platform Module (TPM)** : quando definido como **exigir**, o Intune verifica a compatibilidade da versão. O dispositivo será compatível se a versão do chip do TPM for maior que 0 (zero). O dispositivo não será compatível se não houver uma versão do TPM no dispositivo. Quando **não estiver configurado**, o Intune não verificará o dispositivo em busca de uma versão de chip do TPM.

  [DeviceStatus CSP-DeviceStatus/TPM/nó SpecificationVersion](https://docs.microsoft.com/windows/client-management/mdm/devicestatus-csp)
  
- **Antivírus**: quando definido como **Obrigatório**, você pode verificar a conformidade usando soluções antivírus registradas na [Central de Segurança do Windows](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), como Symantec e Microsoft Defender. Quando **Não configurado**, o Intune não verifica se há soluções antivírus instaladas no dispositivo.
- **Software antispyware**: quando definido como **Obrigatório**, você pode verificar a conformidade usando soluções de software antispyware registradas na [Central de Segurança do Windows](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/), como Symantec e Microsoft Defender. Quando **Não configurado**, o Intune não verifica se há alguma solução de software antispyware instalada no dispositivo.

### <a name="defender"></a>Defender

- **Microsoft Defender Antimalware**: Defina como **exigir** para ativar o serviço antimalware do Microsoft defender e impedir que os usuários o desativem. **Não configurado** (padrão) não controla o serviço nem altera as configurações existentes.
- **Versão mínima do Microsoft Defender Antimalware**: Insira a versão mínima permitida do serviço antimalware do Microsoft defender. Por exemplo, insira `4.11.0.0`. Quando deixado em branco, qualquer versão do serviço antimalware do Microsoft defender pode ser usada.
- **Inteligência de segurança antimalware do Microsoft defender atualizada**: controla as atualizações de proteção contra ameaças e vírus de segurança do Windows nos dispositivos. **Exigir** força a inteligência de segurança do Microsoft defender a ser atualizada. **Não configurado** (padrão) não impõe nenhum requisito.

  [As atualizações de inteligência de segurança para o Microsoft defender antivírus e outros antimalware da Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates) têm mais informações sobre a inteligência de segurança.

- **Proteção em tempo real**: **requer** a habilitação da proteção em tempo real, que verifica o malware, spyware e outros softwares indesejados. **Não configurado** (padrão) não controla esse recurso, nem altera as configurações existentes.

  [CSP do defender/AllowRealtimeMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring)

## <a name="microsoft-defender-atp"></a>ATP do Microsoft Defender

- **Exigir que o dispositivo esteja na pontuação de risco do computador ou abaixo**: use essa configuração para utilizar a avaliação de risco dos seus serviços de ameaça de defesa como uma condição para a conformidade. Selecione o nível máximo de ameaça permitido:

  - **Limpar**: essa opção é a mais segura, porque o dispositivo não pode ter nenhuma ameaças. Se for detectado que o dispositivo tem qualquer nível de ameaça, ele será avaliado como não estando em conformidade.
  - **Baixo**: o dispositivo será avaliado como em conformidade se apenas ameaças de nível baixo estiverem presentes. Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.
  - **Médio**: o dispositivo será avaliado como em conformidade se as ameaças existentes nele forem de nível baixo ou médio. Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele não está em conformidade.
  - **Alta**: esta opção é a menos segura e permite todos os níveis de ameaça. Talvez seja útil se você estiver usando esta solução apenas para fins de relatório.
  
  Para configurar a Microsoft Defender ATP (Proteção Avançada contra Ameaças) como seu serviço de defesa contra ameaças, confira [Habilitar a Microsoft Defender ATP com Acesso Condicional](advanced-threat-protection.md).

Selecione **OK** > **Criar** para salvar suas alterações.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

O Windows Holographic for Business usa a plataforma **Windows 10 e posterior**. O Windows Holographic for Business é compatível com a seguinte configuração:

- **Segurança do Sistema** > **Criptografia** > **Criptografia de armazenamento de dados no dispositivo**.

Para verificar a criptografia do dispositivo no Microsoft HoloLens, consulte [Verificar criptografia do dispositivo](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## <a name="surface-hub"></a>Surface Hub

O Surface Hub usa a plataforma **Windows 10 e posterior**. Os Surface Hubs têm suporte para conformidade e Acesso Condicional. Para habilitar esses recursos em Surface Hubs, recomendamos que você [habilite o registro automático do Windows 10](../enrollment/windows-enroll.md) no Intune (exige o Azure AD [Azure Active Directory]) e marque os dispositivos do Surface Hub como grupos de dispositivos. Os Surface Hubs precisam ser adicionados ao Azure AD para fins de conformidade e Acesso Condicional ao trabalho.

Veja [configurar o registro para dispositivos Windows](../enrollment/windows-enroll.md) para obter diretrizes.

## <a name="next-steps"></a>Próximas etapas

- [Adicione ações para dispositivos que não estão em conformidade](actions-for-noncompliance.md) e [use marcas de escopo para políticas de filtro](../fundamentals/scope-tags.md).
- [Monitore suas políticas de conformidade](compliance-policy-monitor.md).
- Veja as [configurações da política de conformidade para dispositivos Windows 8.1](compliance-policy-create-windows-8-1.md).
