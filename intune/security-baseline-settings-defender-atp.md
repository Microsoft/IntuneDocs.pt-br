---
title: Configurações de linhas de base de segurança do Intune para a Proteção Avançada contra Ameaças do Microsoft Defender
titleSuffix: Microsoft Intune
description: Configurações de linha de base de segurança com suporte do Intune para gerenciar a Proteção Avançada contra Ameaças do Microsoft Defender
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: karthib
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: eee3d4187dd513cd3945e86aff478fe96b341660
ms.sourcegitcommit: 1d4aec7b79c70d35ec3fc29df6ff9c6a1403412e
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68491925"
---
# <a name="microsoft-defender-advanced-threat-protection-baseline-settings-for-intune"></a>Configurações para Intune da Linha de base da Proteção Avançada contra Ameaças do Microsoft Defender

Exiba as configurações de linha de base da Proteção Avançada contra Ameaças do Microsoft Defender (anteriormente conhecido como Proteção Avançada contra Ameaças do Windows Defender) têm suporte pelo Microsoft Intune. Os padrões de linha de base da ATP (Proteção Avançada contra Ameaças) representam a configuração recomendada para ATP e podem não corresponder aos padrões de linha de base para outras linhas de base de segurança.  

A linha de base da Proteção Avançada contra Ameaças do Microsoft Defender está disponível quando o seu ambiente atende aos pré-requisitos para usar a [Proteção Avançada contra Ameaças do Microsoft Defender](advanced-threat-protection.md#prerequisites). 

Essa linha de base é otimizada para dispositivos físicos e não é recomendada no momento para uso em VMs (máquinas virtuais) ou pontos de extremidade de VDI. Algumas configurações de linha de base podem afetar as sessões interativas remotas em ambientes virtualizados. Para obter mais informações, confira [Aumentar a conformidade com a linha de base de segurança do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline) na documentação do Windows.


> [!NOTE]  
> As configurações de linha de base de ATP estão em **Versão prévia**. Enquanto estiver em versão prévia, a lista de configurações disponíveis e a ordem em que este conteúdo apresenta essas configurações podem não corresponder ao que estiver disponível no portal.  
>
> Quando as configurações de linha de base saírem da versão prévia, esse conteúdo será atualizado para refletir uma lista atualizada da versão prévia das configurações de linha de base de segurança compatíveis com o Intune.

## <a name="application-guard"></a>Application Guard  
Para saber mais, veja [CSP do WindowsDefenderApplicationGuard](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp) na documentação do Windows.  

Ao usar o Microsoft Edge, o Microsoft Defender Application Guard protege seu ambiente contra sites que não são confiáveis para sua organização. Quando os usuários visitam sites que não estão listados no limite de rede isolada, os sites são abertos em uma sessão de navegação virtual do Hyper-V. Os sites confiáveis são definidos por um limite de rede.  

- **Application Guard** - *Settings/AllowWindowsDefenderApplicationGuard*  
  Selecione *Sim* para ativar esse recurso, que abre sites não confiáveis em um contêiner de navegação virtualizado do Hyper-V. Quando estiver definido como *Não configurado*, qualquer site (confiável e não confiável) é aberto no dispositivo e não em um contêiner virtualizado.  

  **Padrão**: Sim
 
  - **Conteúdo externo em sites corporativos** - *Settings/BlockNonEnterpriseContent*  
    Selecione *Sim* para impedir o carregamento do conteúdo de sites não aprovados. Quando estiver definido como *Não configurado*, os sites não empresariais poderão ser abertos no dispositivo. 
 
    **Padrão**: Sim

  - **Comportamento da área de transferência** - *Settings/ClipboardSettings*  
    Escolha quais ações de copiar e colar são permitidas entre o computador local e o navegador virtual do Application Guard.  As opções incluem:
    - *Não Configurado*  
    - *Bloquear ambos* - não é possível transferir dados entre o computador e o navegador virtual.  
    - *Bloquear host para o contêiner* - não é possível transferir dados do PC para o navegador virtual.
    - *Bloquear contêiner para o host* - não é possível transferir dados do navegador virtual para o PC host.
    - *Não bloquear* – não há bloqueio para conteúdo.  

    **Padrão**: Bloquear ambos  

- **Política de isolamento de rede do Windows – nomes de domínio de rede corporativa**  
  Para saber mais, veja [CSP de política – NetworkIsolation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-networkisolation) na documentação do Windows.
  
  Especifique uma lista de recursos corporativos como domínios, intervalos de endereços IP e limites de rede que são hospedados na nuvem, que o Application Guard trata como sites corporativos.  

  **Padrão**: securitycenter.windows.com

## <a name="application-reputation"></a>Reputação de aplicativo  

Para obter mais informações, veja [CSP de política – SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) na documentação do Windows.

- **Bloquear a execução de arquivos não verificados**  
    Impedir que o usuário execute arquivos não verificados. Quando estiver definido como *Não Configurado*, os funcionários podem ignorar os avisos do SmartScreen e executar arquivos mal-intencionados. Defina como *Sim* para que os funcionários não possam ignorar os avisos do SmartScreen nem executar arquivos mal-intencionados.  
  
    **Padrão**: Sim

- **Exigir SmartScreen para aplicativos e arquivos**  
  Definido como *Sim* para habilitar o SmartScreen para Windows.  

  **Padrão**: Sim

## <a name="attack-surface-reduction"></a>Redução da superfície de ataque  

- **Tipo de processo filho de iniciar aplicativos do Office**  
  [Regra de redução da superfície de ataque](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – quando definido como *Bloquear*, os aplicativos do Office não terão permissão para criar processos filho. Os aplicativos do Office incluem Word, Excel, PowerPoint, OneNote e Access. A criação de um processo filho é um comportamento típico de malware, especialmente para ataques baseados em macro que tentam usar aplicativos do Office para iniciar ou baixar executáveis mal-intencionados.  

  **Padrão**: Bloquear

- **Gerar script de tipo de execução de payload baixada**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection) – especificar um nível de detecção de aplicativos potencialmente indesejados que baixam ou tentam instalar.  

  **Padrão**: Bloquear 

- **Impedir que o tipo de roubo de credencial**  
  Defina como *Habilitar* para [Proteger as credenciais de domínio derivadas com o Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard). O Windows Defender Credential Guard usa segurança baseada em virtualização para isolar segredos para que apenas o software de sistema privilegiado possa acessá-los. O acesso não autorizado a esses segredos pode levar a ataques de roubo de credenciais, como Pass-the-Hash ou Pass-The-Ticket. O Windows Defender Credential Guard evita esses ataques protegendo os hashes de senha NTLM, Kerberos Ticket Granting Tickets e credenciais armazenadas por aplicativos como credenciais de domínio.  

  **Padrão**: Habilitar

- **Tipo de execução de conteúdo de email**  
  [Regra de redução da superfície de ataque](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – quando definido como *Bloquear*, esta regra bloqueia a execução ou a inicialização dos seguintes tipos de arquivo de um email visto no Microsoft Outlook ou webmail (por exemplo, Gmail.com ou Outlook.com):  

  - Arquivos executáveis (como .exe, .dll, ou .scr)  
  - Arquivos de script (como .ps do PowerShell, .vbs do Visual Basic ou arquivo .js do JavaScript)  
  - Criar script de arquivos mortos  

  **Padrão**: Bloquear

- **Inicialização do Adobe Reader em um processo filho**  
  [Regra de redução da superfície de ataque](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – *habilite* essa regra para impedir que o Adobe Reader crie um processo filho. Por meio de engenharia social ou explorações, o malware pode baixar e iniciar cargas adicionais e sair do Adobe Reader.  

  **Padrão**: Habilitar

- **Tipo de código de macro ocultado de script**  
  [Regra de redução da superfície de ataque](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – Malware e outras ameaças podem tentar ocultar seu código mal-intencionado em arquivos de script. Essa regra impede a execução de scripts que parecem estar ocultos.  
    
  **Padrão**: Bloquear

- **Tipo de processo de USB não confiável**  
  [Regra de redução da superfície de ataque](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – quando definido como *Bloquear*, os arquivos executáveis não assinados ou não confiáveis de unidades removíveis USB e cartões SD não podem ser executados.

  Os arquivos executáveis incluem:
  - Arquivos executáveis (como .exe, .dll, ou .scr)
  - Arquivos de script (como .ps do PowerShell, .vbs do Visual Basic ou arquivo .js do JavaScript)  

  **Padrão**: Bloquear

- **Tipo de injeção de outros processos de aplicativos do Office**  
  [Regra de redução da superfície de ataque](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) -quando definido como *Bloquear*, os aplicativos do Office, incluindo Word, Excel, PowerPoint e OneNote não podem injetar código em outros processos. A injeção de código normalmente é usado por malware para executar código mal-intencionado em uma tentativa de ocultar a atividade de mecanismos de verificação de antivírus.  

  **Padrão**: Bloquear

- **Tipo de código de macro do Office que permite importações do Win32**  
  [Regra de redução da superfície de ataque](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) - quando definido como *Bloquear*, essa regra tenta bloquear os arquivos do Office que contêm código de macro que pode importar as DLLs do Win32. Os arquivos do Office incluem o Word, o Excel, o PowerPoint e o OneNote. O malware pode usar o código de macro em arquivos do Office para importar e carregar DLLs do Win32, que são usados para fazer chamadas à API para permitir a infecção em todo o sistema.  

  **Padrão**: Bloquear

- **Inicialização de aplicativos de comunicação do Office em um processo filho**  
  [Regra de redução da superfície de ataque](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – quando definido como *Habilitar*, essa regra impede que o Outlook crie processos filho. Ao bloquear a criação de um processo filho, essa regra protege contra ataques de engenharia social e impede que o código de exploração abuse de uma vulnerabilidade no Outlook.  

  **Padrão**: Habilitar

- **Tipo de lançamento ou criação de conteúdo executável de aplicativos do Office**  
  [Regra de redução da superfície de ataque](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules) – quando definido como *Bloquear*, os aplicativos do Office não podem criar conteúdo executável. Os aplicativos do Office incluem Word, Excel, PowerPoint, OneNote e Access.  

  Essa regra tem como alvo os comportamentos típicos usados por complementos e scripts (extensões) suspeitos e mal-intencionados que criam ou inicializam arquivos executáveis. Essa é uma técnica de malware típica. As extensões são impedidas de serem usadas pelos aplicativos do Office. Normalmente essas extensões usam o Windows Script Host (arquivos .wsh) para executar scripts que automatizam determinadas tarefas ou fornecem recursos de complemento criados pelo usuário.

  **Padrão**: Bloquear

## <a name="bitlocker"></a>BitLocker  

Para saber mais, veja [Configurações de Política de Grupo do Bitlocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) na documentação do Windows.  

- **Criptografar dispositivos**  
  Selecione *Sim* para habilitar a criptografia de dispositivo do BitLocker. Dependendo do hardware do dispositivo e da versão do Windows, os usuários de dispositivos podem ser solicitados a confirmar que não há nenhuma criptografia de terceiros no dispositivo. Se você ativar a criptografia do Windows enquanto a criptografia de terceiros estiver ativa, o dispositivo será renderizado como instável.  

   **Padrão**: Sim

- **Política de unidade removível do BitLocker**  
  Os valores para essa política determinam o nível da criptografia que o BitLocker usa para criptografia de unidades removíveis. As empresas controlam o nível de criptografia para aumentar a segurança (AES-256 é mais forte do que AES-128). Se você selecionar *Sim* para habilitar essa configuração, poderá configurar um algoritmo de criptografia e a intensidade da chave de criptografia para unidades de dados fixas, unidades do sistema operacional e unidades de dados removíveis individualmente. Para unidades de sistemas operacionais e fixas, recomendamos usar o algoritmo XTS-AES. Para unidades removíveis, você deve usar AES-CBC de 128 bits ou AES-CBC de 256 bits caso a unidade seja usada em outros dispositivos que não estejam executando o Windows 10, versão 1511 ou posterior. Alterar o método de criptografia não terá efeito se a unidade já estiver criptografada ou se a criptografia estiver em andamento. Nesses casos, essa configuração de política será ignorada. 

  Para a política da unidade removível do BitLocker, defina as seguintes configurações:

  - **Exigir criptografia para acesso de gravação**  
    **Padrão**: Sim

  - **Método de criptografia**  
    **Padrão**: CBC AES de 128 bits

- **Política de unidade fixa do BitLocker**  
  Os valores para essa política determinam o nível da criptografia que o BitLocker usa para criptografia de unidades fixas. As empresas podem controlar o nível de criptografia para aumentar a segurança (AES-256 é mais forte do que AES-128). Se você habilitar essa configuração, poderá configurar um algoritmo de criptografia e a intensidade da chave de criptografia para unidades de dados fixas, unidades do sistema operacional e unidades de dados removíveis individualmente. Para unidades de sistemas operacionais e fixas, recomendamos usar o algoritmo XTS-AES. Para unidades removíveis, você deve usar AES-CBC de 128 bits ou AES-CBC de 256 bits caso a unidade seja usada em outros dispositivos que não estejam executando o Windows 10, versão 1511 ou posterior. Alterar o método de criptografia não terá efeito se a unidade já estiver criptografada ou se a criptografia estiver em andamento. Nesses casos, essa configuração de política será ignorada.

  Para a política da unidade fixa do BitLocker, defina as seguintes configurações:

  - **Exigir criptografia para acesso de gravação**  
    **Padrão**: Sim

  - **Método de criptografia**  
    **Padrão**: XTS AES de 128 bits

- **Política de unidade do sistema do BitLocker**  
  Os valores para essa política determinam o nível da criptografia que o BitLocker usa para criptografia da unidade do sistema. As empresas talvez queiram controlar o nível de criptografia para aumentar a segurança (AES-256 é mais forte do que AES-128). Se você habilitar essa configuração, poderá configurar um algoritmo de criptografia e a intensidade da chave de criptografia para unidades de dados fixas, unidades do sistema operacional e unidades de dados removíveis individualmente. Para unidades de sistemas operacionais e fixas, recomendamos usar o algoritmo XTS-AES. Para unidades removíveis, você deve usar AES-CBC de 128 bits ou AES-CBC de 256 bits caso a unidade seja usada em outros dispositivos que não estejam executando o Windows 10, versão 1511 ou posterior. Alterar o método de criptografia não terá efeito se a unidade já estiver criptografada ou se a criptografia estiver em andamento. Nesses casos, essa configuração de política será ignorada.  

  Para a política da unidade de sistema do BitLocker, defina as seguintes configurações:  

  - **Método de criptografia**  
    **Padrão**: XTS AES de 128 bits

## <a name="device-control"></a>Controle de dispositivo  

- **Examinar unidades removíveis durante um exame completo**  
  [Defender/AllowFullScanRemovableDriveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning) – quando definido como *Sim*, o Defender examina softwares mal-intencionados e indesejados em unidades removíveis, como unidades flash, durante uma verificação completa. O Defender Antivírus examina todos os arquivos nos dispositivos USB antes de os arquivos no dispositivo USB serem executados.

  Configuração relacionada nesta lista: *Defender/AllowFullScanOnMappedNetworkDrives*  

  **Padrão**: Sim

- **Enumeração de dispositivos externos incompatíveis com a proteção de DMA do Kernel**  
   Confira *DmaGuard/DeviceEnumerationPolicy* na [Política CSP - DmaGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  Essa política fornece segurança adicional em relação a dispositivos externos com capacidade de DMA. Ele permite mais controle sobre a enumeração de dispositivos externos com capacidade de DMA que são incompatíveis com áreas de segurança e isolamento de memória de dispositivo DMA.

  Essa política tem efeito somente quando a Proteção DMA de Kernel tem suporte e está habilitada pelo firmware do sistema. A Proteção DMA de Kernel é um recurso de plataforma que não pode ser controlado por política ou pelo usuário de um dispositivo. Ele precisa ser suportado pelo sistema no momento da produção. 

  Para verificar se o sistema dá suporte à proteção de DMA do Kernel, execute o MSINFO32.exe no sistema e examine o campo *Proteção DMA de Kernel* na página de resumo.  

  As opções incluem: 
  - *Padrão do dispositivo* – após acessar ou desbloquear a tela, os dispositivos com drivers compatíveis com remapeamento de DMA têm permissão para serem enumerados a qualquer momento. Os dispositivos com drivers incompatíveis com remapeamento de DMA somente serão enumerados somente depois que o usuário desbloquear a tela
  - *Permitir tudo* -todos os dispositivos PCIe externos habilitados para DMA serão enumerados a qualquer momento
  - *Bloquear tudo* -os dispositivos com drivers compatíveis com remapeamento de DMA têm permissão para serem enumerados a qualquer momento. Os dispositivos com drivers incompatíveis com o remapeamento de DMA nunca poderão iniciar e executar o DMA a qualquer momento.

  **Padrão**: Padrão do dispositivo

- **Instalação de dispositivo de hardware por identificadores de dispositivo**  
  [DeviceInstallation/PreventInstallationOfMatchingDeviceIDs](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-preventinstallationofmatchingdeviceids) - com essa política, você especifica uma lista de IDs de hardware Plug and Play e IDs compatíveis com dispositivos que o Windows é impedido de instalar. Essa configuração de política tem precedência sobre qualquer outra configuração de política que permita ao Windows instalar um dispositivo. Se você habilitar essa configuração de política (definida para *Bloquear a instalação de dispositivo de hardware*), o Windows será impedido de instalar um dispositivo cuja ID de hardware ou ID compatível seja exibida na lista que você cria. Se você habilitar essa configuração de política em um servidor de área de trabalho remota, a política afetará o redirecionamento de dispositivos especificados de um cliente da área de trabalho remota para o servidor de área de trabalho remota. Se você desabilitar ou não configurar essa política (definida como *Permitir a instalação de dispositivo de hardware*), os dispositivos poderão instalar e atualizar conforme permitido ou impedido por outras configurações de política.  

  **Padrão**: bloquear a instalação de dispositivo de hardware  

  Quando *Bloquear a instalação de dispositivo de hardware* estiver selecionada, as configurações a seguir estarão disponíveis.
  - **Remover dispositivos de hardware correspondentes**  
    Essa configuração está disponível apenas quando *Instalação de dispositivo de hardware por identificadores de dispositivo* é definida como *Bloquear instalação de dispositivo de hardware*.  

    **Padrão**: *nenhuma configuração padrão*

  - **Identificadores de dispositivo de hardware que estão bloqueados**  
    Essa configuração está disponível apenas quando *Instalação de dispositivo de hardware por identificadores de dispositivo* é definida como *Bloquear instalação de dispositivo de hardware*. Para definir essa configuração, expanda a opção, selecione **+ Adicionar** e, em seguida, especifique o identificador de dispositivo de hardware que você deseja bloquear.  

    **Padrão**: *Nenhum dispositivo está bloqueado*  

- **Bloquear acesso direto à memória**  
  [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess) - use essa configuração de política para bloquear o DMA (acesso direto à memória) para todas as portas downstream PCI em um dispositivo com hot-plug até um usuário fazer logon no Windows. Depois que um usuário fizer logon, o Windows vai enumerar os dispositivos PCI conectados às portas host plug PCI. Sempre que o usuário bloqueia o computador, o DMA é bloqueado em portas PCI com hot-plug sem dispositivos filhos até que o usuário faça logon novamente. Os dispositivos que já foram enumerados quando o computador foi desbloqueado continuarão a funcionar até que sejam desconectados. 

  Essa configuração de política é imposta somente quando a criptografia BitLocker ou de dispositivo está habilitada.  

  **Padrão**: Sim


- **Instalação de dispositivo de hardware por classes de instalação**  
  [DeviceInstallation/AllowInstallationOfMatchingDeviceSetupClasses](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation#deviceinstallation-allowinstallationofmatchingdevicesetupclasses) - essa política permite que você especifique uma lista de GUIDs (identificadores globalmente exclusivos) de classe de configuração de dispositivo para drivers de dispositivo que o Windows seja impedido de instalar. Essa configuração de política tem precedência sobre qualquer outra configuração de política que permita ao Windows instalar um dispositivo. Se você habilitar essa configuração de política (definido como *Bloquear instalação do dispositivo de hardware*), o Windows será impedido de instalar ou atualizar drivers de dispositivo cujos GUIDs de classe de instalação do dispositivo apareçam na lista de você cria. Se você habilitar essa configuração de política em um servidor de área de trabalho remota, a configuração de política afetará o redirecionamento de dispositivos especificados de um cliente da área de trabalho remota para o servidor de área de trabalho remota. Se você desabilitar ou não configurar essa política (definida como *Permitir a instalação de dispositivo de hardware*), o Windows poderá instalar e atualizar dispositivos conforme permitido ou impedido por outras configurações de política.  

  **Padrão**: bloquear a instalação de dispositivo de hardware

  Quando *Bloquear a instalação de dispositivo de hardware* estiver selecionada, as configurações a seguir estarão disponíveis.  

  - **Remover dispositivos de hardware correspondentes**  
    Essa configuração está disponível apenas quando *Instalação de dispositivo de hardware por classes de instalação* é definida como *Bloquear instalação de dispositivo de hardware*.  
 
    **Padrão**: *nenhuma configuração padrão*  

  - **Identificadores de dispositivo de hardware que estão bloqueados**  
    Essa configuração está disponível apenas quando Instalação de dispositivo de hardware por classes de instalação é definida como Bloquear instalação de dispositivo de hardware. Para definir essa configuração, expanda a opção, selecione **+ Adicionar** e, em seguida, especifique o identificador de dispositivo de hardware que você deseja bloquear.  
 
    **Padrão**: *Nenhum dispositivo está bloqueado*

## <a name="endpoint-detection-and-response"></a>Ponto de extremidade de detecção e resposta  
Para saber mais, consulte [CSP WindowsAdvancedThreatProtection](https://docs.microsoft.com/windows/client-management/mdm/windowsadvancedthreatprotection-csp) na documentação do Windows.  

- **Agilize a frequência do relatório de telemetria** - *Configuration/TelemetryReportingFrequency*  

  Agilize a frequência do relatório de telemetria da Proteção Avançada contra Ameaças do Microsoft Defender.  

  **Padrão**: Sim

- **Exemplo de compartilhamento para todos os arquivos** - *Configuration/SampleSharing*  

  Retorna ou define o parâmetro de configuração do Compartilhamento de Amostra da Proteção Avançada contra Ameaças do Microsoft Defender.  

  **Padrão**: Sim

## <a name="exploit-protection"></a>Proteção contra explorações  

- **XML de Exploit Protection**  
  Para saber mais, confira [Importar, exportar e implantar configurações de proteção de exploração ](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/import-export-exploit-protection-emet-xml) na documentação do Windows.  

  Permite que o administrador de TI efetue o push de uma configuração que representa as opções de migração de aplicativo e sistema desejadas para todos os dispositivos na organização. A configuração é representada por um XML. 

  O Exploit Protection aplicado ajuda a proteger os dispositivos contra malware que usa explorações para se espalhar e infectar. Use o aplicativo de Segurança do Windows ou o PowerShell para criar um conjunto de mitigações (conhecido como uma configuração). Você pode então exportar essa configuração como um arquivo XML e compartilha-lo com vários computadores na sua rede para que todos tenham o mesmo conjunto de configurações de mitigação.
 
  Você também pode converter e importar um arquivo XML de configuração EMET existente em um XML de Exploit Protection.

- **Substituição de proteção de exploração de bloqueio**  
  [WindowsDefenderSecurityCenter/DisallowExploitProtectionOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsdefendersecuritycenter#windowsdefendersecuritycenter-disallowexploitprotectionoverride) – definido como *Sim* para impedir que os usuários alterem a área de configurações da proteção de exploração na Central de Segurança do Windows Defender. Se você desabilitar ou não definir essa configuração, os usuários locais poderão fazer alterações na área de configurações de proteção de exploração.  
  **Padrão**: Sim  

- **Acesso controlado a pastas**  
  Consulte [Defender/ControlledFolderAccessAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessallowedapplications) e [Defender/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) 
  
   Proteger arquivos e pastas contra alterações não autorizadas por aplicativos não amigáveis.

  **Padrão**: Modo de auditoria

## <a name="web--network-protection"></a>Proteção de rede e da Web  

- **Tipo de proteção de rede**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) - essa política permite que você ative ou desative a proteção de rede no Windows Defender Exploit Guard. A proteção de rede é um recurso do Windows Defender Exploit Guard que protege os funcionários usando qualquer aplicativo do acesso a golpes de phishing, sites que hospedam explorações e conteúdo mal-intencionado na Internet. Isso inclui impedir que navegadores de terceiros se conectem a sites perigosos.  

  Quando estiver definido como *Habilitar* ou *Modo de auditoria*, os usuários não poderão desativar a proteção de rede e você poderá usar a Central de Segurança do Windows Defender para exibir informações sobre as tentativas de conexão.  
 
  - *Habilitar* impedirá os usuários e os aplicativos de se conectarem a domínios perigosos.  
  - *Modo de auditoria* não impedirá os usuários e os aplicativos de se conectarem a domínios perigosos.  

  Quando definido como *Definido pelo usuário*, os usuários e os aplicativos não são impedidos de se conectarem a domínios perigosos e as informações sobre conexões não estão disponíveis na Central de Segurança do Windows Defender.  

  **Padrão**: Modo de auditoria

- **Exigir SmartScreen para Microsoft Edge**  
  [Browser/AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) - o Microsoft Edge usa o Windows Defender SmartScreen (ligado) para proteger os usuários contra possíveis golpes de phishing e software mal-intencionado por padrão. Por padrão, essa política está habilitada (definida como *Sim*) e, quando habilitada, impede que os usuários desativem o Windows Defender SmartScreen.  Quando a política efetiva para um dispositivo é igual a não configurado, os usuários podem desativar o Windows Defender SmartScreen, que deixa o dispositivo desprotegido.  

  **Padrão**: Sim
  
- **Bloquear acesso a sites mal-intencionados**  
  [Browser/PreventSmartScreenPromptOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride) - por padrão, o Microsoft Edge permite que os usuários contornem (ignorem) os avisos do Windows Defender SmartScreen sobre sites potencialmente mal-intencionados, permitindo que os usuários prossigam para o site. Com essa política habilitada (definida como *Sim*), o Microsoft Edge impede que os usuários ignorem os avisos e os impede de prosseguir para o site.  

  **Padrão**: Sim

- **Bloquear download de arquivo não verificado**  
  [Browser/PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles) - por padrão, o Microsoft Edge permite que os usuários contornem (ignorem) os avisos do Windows Defender SmartScreen sobre sites potencialmente mal-intencionados, permitindo que os usuários continuem baixando arquivos não verificado. Com essa política habilitada (definida como *Sim*), os usuários são impedidos de ignorar os avisos e não podem baixar os arquivos não verificados.  

  **Padrão**: Sim

## <a name="windows-defender-anti-virus----settings-review-pending-for-this-section"></a>Antivírus do Windows Defender [revisão das configurações pendentes para esta seção]

Para obter mais informações, veja [CSP de política – Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) na documentação do Windows.

- **Examinar scripts carregados em navegadores da Web da Microsoft**  
  [Defender/AllowScriptScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning) – definido como *Sim* para permitir a funcionalidade de verificação de Script do Windows Defender.  

  **Padrão**: Sim

- **Examinar mensagens de email recebidas**  
  [Defender/AllowEmailScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning) – definido como *Sim* para permitir que o Windows Defender verifique email.  

  **Padrão**: Sim

- **Tipo de consentimento de envio de amostra do Defender**  
  [Defender/SubmitSamplesConsent](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) - verifica o nível de consentimento do usuário no Windows Defender para enviar dados. Se o consentimento necessário já tiver sido concedido, o Windows Defender os enviará. Caso contrário (e se o usuário tiver especificou nunca perguntar), a interface do usuário será iniciada para pedir consentimento do usuário (quando o *Cloud-delivered protection* estiver definido como *Sim*) antes de enviar dados.  

  **Padrão**: enviar amostras seguras automaticamente

- **NIS (Sistema de Inspeção de Rede)**  
  [Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) - bloqueie tráfego mal-intencionado detectado por assinaturas no Sistema de Inspeção da Rede (NIS).  
 
  **Padrão**: Sim

- **Intervalo de atualização de assinaturas (em horas)**  
  [Defender/SignatureUpdateInterval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval) – especifique em horas, a frequência com que o dispositivo verifica novas atualizações de assinatura do Defender.  
 
  **Padrão**: 4

- **Configurar prioridade baixa da CPU para verificações agendadas**  
  [Defender/EnableLowCPUPriority](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablelowcpupriority) – quando definido como *Sim*, a prioridade da CPU para verificações é definida como baixa. Quando *Não Configurado*, nenhuma alteração é feita na prioridade da CPU para verificações agendadas.  

    **Padrão**: Sim

- **O Defender bloqueia na proteção de acesso**  
  [Defender/AllowOnAccessProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowonaccessprotection) – quando definido como *Sim*, a proteção ao acessar do Windows Defender é habilitada.  

  **Padrão**: Sim

- **Tipo de exame do sistema a ser realizado**  
  [Defender/ScanParameter](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter) - tipo de verificação do Defender.  

  **Padrão**: Verificação rápida

- **Verificar todos os downloads**  
  [Defender/AllowIOAVProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection) - quando definido como *Sim*, o Defender examina todos os arquivos e anexos baixados.  

  **Padrão**: Sim

- **Dias antes da exclusão de malware em quarentena**  
  [Defender/DaysToRetainCleanedMalware](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware) -especifique o número de dias para manter os itens em quarentena no sistema antes que eles sejam excluídos automaticamente. Quando definido como zero, os itens em quarentena nunca são excluídos automaticamente.  

  **Padrão**: 0

- **Hora de início de verificação agendada**  
  [Defender/ScheduleScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime) – agendar um horário do dia para o Defender verificar dispositivos. 
  
  Opção relacionada nesta lista: *Defender/ScheduleScanDay*   

  **Padrão**: 2h00

- **Proteção entregue na nuvem**  
  [Defender/AllowCloudProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection) – quando definido como *Sim*, o Windows Defender envia informações à Microsoft sobre os problemas encontrados. A Microsoft analisará essas informações, saberá mais sobre os problemas que afetam você e outros clientes e oferecerá soluções aprimoradas.

  Quando essa política é definida como *Sim*, você pode usar *Tipo de consentimento de envio de amostra do Defender* para dar aos usuários controle sobre o envio de informações do seu dispositivo.  

  **Padrão**: Sim

- **Ação de aplicativo potencialmente indesejado do Defender**  
  [Defender/PUAProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection) – o antivírus do Windows Defender pode identificar e bloquear *aplicativos potencialmente indesejados* (PUAs) de serem baixados e instalados em pontos de extremidade na sua rede. 
 
  - Quando definido como *Bloquear*, o Windows Defender bloqueia os PUAs e lista-os no histórico juntamente com outras ameaças.
  - Quando definido como *Auditoria*, o Windows Defender detecta os PUAs, mas não os bloqueia. As informações sobre os aplicativos sobre os quais o Windows Defender teria que agir podem ser encontradas pesquisando os eventos que foram criados pelo Windows Defender no Visualizador de Eventos.  
  - Quando definido como *Padrão do dispositivo*, a proteção de PUA está desativada.  
 
  **Padrão**: Bloquear

- **Tempo limite estendido de nuvem do Defender**  
  [Defender/CloudExtendedTimeout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudextendedtimeout) - especifique o máximo de tempo adicional para o Windows Defender Antivírus bloquear um arquivo enquanto aguarda um resultado da nuvem. O valor base do tempo de espera do Windows Defender é 10 segundos. Qualquer tempo adicional especificado aqui (até 50 segundos) é adicionado a esses 10 segundos. Na maioria dos casos, a verificação leva menos tempo do que o máximo. Estender o tempo permite que a nuvem investigue completamente os arquivos suspeitos.  

  Por padrão, o valor de tempo expandido é 0 (desabilitado). O Intune recomenda que você habilite essa configuração e especifique pelo menos 20 segundos adicionais.  
 
  **Padrão**: 0

- **Verificar arquivos mortos**  
  [Defender/AllowArchiveScanning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning) – definido como *Sim* para que o Windows Defender verifique arquivos mortos.  

  **Padrão**: Sim

- **O agendamento de verificação do sistema do Defender**  
  [Defender/ScheduleScanDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday) -agenda em que dia o Defender verifica os dispositivos. 
 
  Opção relacionada nesta lista: *Defender/ScheduleScanTime*

  **Padrão**: definido pelo usuário

- **Monitoramento de comportamento**  
  [Defender/AllowBehaviorMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring) – definido como *Sim* para ativar a funcionalidade de monitoramento do comportamento do Windows Defender. Inseridos no Windows 10, os sensores de Monitoramento de Comportamento do Windows Defender coletam e processam sinais comportamentais do sistema operacional e enviam esses dados do sensor à sua instância de nuvem privada e isolada do Microsoft Defender ATP.  

  **Padrão**: Sim

- **Examinar arquivos abertos em pastas de rede**  
  [Defender/AllowScanningNetworkFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles) – definido como *Sim* para que o Windows Defender verifique arquivos na rede. O usuário não poderá remover nenhum malware detectado de arquivos somente leitura.  

  **Padrão**: Sim

- **Nível de bloco de nuvem do Defender**  
  [Defender/CloudBlockLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-cloudblocklevel) – use essa política para determinar o nível de agressividade do antivírus do Windows Defender em bloquear e verificar os arquivos suspeitos. As opções incluem:

  - Alta – bloqueia agressivamente os arquivos desconhecidos, otimizando o desempenho do cliente (maior chance de falsos positivos)
  - Mais alta – bloqueia agressivamente os arquivos desconhecidos e aplica medidas de proteção adicionais (pode afetar o desempenho do cliente)
  - Tolerância zero - bloqueia todos os arquivos executáveis desconhecidos

  **Padrão**: Não configurado

- **Monitoramento em tempo real**  
  [Defender/AllowRealtimeMonitoring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring) – definido como *Sim* para permitir o monitoramento do Windows Defender em tempo real.  

  **Padrão**: Sim

- **Limite de uso da CPU durante um exame**  
  [Defender/AvgCPULoadFactor](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-avgcpuloadfactor) – especifique a média máxima de % de uso da CPU que o Windows Defender pode usar durante uma verificação.  

  **Padrão**: 50

- **Examinar unidades de rede mapeadas durante um exame completo**  
  [Defender/AllowFullScanOnMappedNetworkDrives](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanonmappednetworkdrives) – definido como *Sim* para que o Windows Defender verifique arquivos na rede. O usuário não poderá remover nenhum malware detectado de arquivos somente leitura,

  Configurações relacionadas nesta lista: *Defender/AllowScanningNetworkFiles*

  **Padrão**: Sim

- **Bloquear acesso do usuário final ao Defender**  
  [Defender/AllowUserUIAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowuseruiaccess) – definido como *Sim* para bloquear o acesso de usuários finais na interface do usuário do Windows Defender em seu dispositivo.  

  **Padrão**: Sim

- **Hora de início da verificação rápida**  
  [Defender/ScheduleQuickScanTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime) – agende um horário do dia para o Defender realizar uma verificação rápida.  

  **Padrão**: 2h00

## <a name="windows-defender-firewall"></a>Windows Defender Firewall
Para saber mais, veja [CSP de Firewall](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp) na documentação do Windows.

- **Tempo ocioso da associação de segurança antes da exclusão** - *MdmStore/Global/SaIdleTime*   
  As associações de segurança são excluídas depois que o tráfego de rede não é percebido por esse número de segundos.  
  **Padrão**: 300

- **Protocolo de transferência de arquivos** - *MdmStore/Global/DisableStatefulFtp*   
  Bloqueia Protocolo FTP com estado.  
  **Padrão**: Sim

- **Enfileiramento de pacotes** - *MdmStore/Global/EnablePacketQueue*    
  Especifique como o dimensionamento de software no lado do recebimento será habilitado para o recebimento criptografado e o encaminhamento de texto não criptografado para o cenário de gateway de túnel do IPsec. Isso garante que a ordem de pacotes seja preservada.  
  **Padrão**: Padrão do dispositivo

- **Domínio do perfil do firewall** - *FirewallRules/FirewallRuleName/Profiles*  
  Especifica os perfis aos quais a regra pertence: domínio, privado, público. Esse valor representa o perfil para redes que estão conectadas aos domínios.  

  Configurações disponíveis:  
  - **Respostas unicast para difusões multicast necessárias**  
    **Padrão**: Sim

  - **Regras de aplicativo autorizado da diretiva de grupo mesclada**  
    **Padrão**: Sim

  - **Notificações de entrada bloqueadas**  
    **Padrão**: Sim

  - **Regras de porta global da política de grupo mesclada**  
    **Padrão**: Sim

  - **Modo furtivo bloqueado**  
    **Padrão**: Sim

  - **Firewall habilitado**  
    **Padrão**: Permitido

  - **Regras de segurança de conexão da política de grupo não mesclada**  
    **Padrão**: Sim

  - **Regras de política da política de grupo não mesclada**  
    **Padrão**: Sim

- **Perfil público do firewall** - *FirewallRules/FirewallRuleName/Profiles*  
  Especifica os perfis aos quais a regra pertence: domínio, privado, público. Esse valor representa o perfil para redes públicas. Essas redes são classificadas como públicas pelos administradores no host do servidor. A classificação ocorre na primeira vez em que o host se conecta à rede. Normalmente, essas redes estão em aeroportos, cafeterias e outros locais públicos, onde os pontos na rede ou o administrador de rede não são confiáveis.  

  Configurações disponíveis:

  - **Conexões de entrada bloqueadas**  
    **Padrão**: Sim 

  - **Respostas unicast para difusões multicast necessárias**  
    **Padrão**: Sim  

  - **Modo furtivo necessário**  
    **Padrão**: Sim 
 
  - **Conexões de saída necessárias**  
    **Padrão**: Sim  

  - **Regras de aplicativo autorizado da diretiva de grupo mesclada**  
    **Padrão**: Sim  

  - **Notificações de entrada bloqueadas**  
    **Padrão**: Sim  

  - **Regras de porta global da política de grupo mesclada**  
    **Padrão**: Sim

  - **Modo furtivo bloqueado**  
    **Padrão**: Sim

  - **Firewall habilitado**  
    **Padrão**: Permitido  

  - **Regras de segurança de conexão da política de grupo não mesclada**  
    **Padrão**: Sim  

  - **Tráfego de entrada necessário**  
    **Padrão**: Sim

  - **Regras de política da política de grupo não mesclada**  
    **Padrão**: Sim  

- **Perfil privado do firewall** - *FirewallRules/FirewallRuleName/Profiles*  
  Especifica os perfis aos quais a regra pertence: Domínio, Privado, Público. Esse valor representa o perfil para redes privadas.  

  Configurações disponíveis: 

  - **Conexões de entrada bloqueadas**  
    **Padrão**: Sim

  - **Respostas unicast para difusões multicast necessárias**  
    **Padrão**: Sim

  - **Modo furtivo necessário**  
    **Padrão**: Sim

  - **Conexões de saída necessárias**  
    **Padrão**: Sim

  - **Notificações de entrada bloqueadas**  
    **Padrão**: Sim

  - **Regras de porta global da política de grupo mesclada**  
    **Padrão**: Sim

  - **Modo furtivo bloqueado**  
    **Padrão**: Sim  

  - **Firewall habilitado**  
    **Padrão**: Permitido

  - **Regras de aplicativo autorizado da diretiva de grupo não mescladas**  
    **Padrão**: Sim

  - **Regras de segurança de conexão da política de grupo não mesclada**  
    **Padrão**: Sim

  - **Tráfego de entrada necessário**  
    **Padrão**: Sim

  - **Regras de política da política de grupo não mesclada**  
    **Padrão**: Sim  

- **Método de codificação de chave pré-compartilhado de firewall**  
  **Padrão**: UTF8

- **Verificação da lista de certificados revogados**  
  **Padrão**: Padrão do dispositivo

## <a name="windows-hello-for-business"></a>Windows Hello para Empresas  

Para saber mais, veja [PassportForWork CSP](https://docs.microsoft.com/windows/client-management/mdm/passportforwork-csp) na documentação do Windows.

- **Configurar o Windows Hello para empresas** - *TenantId/Policies/UsePassportForWork*    
  O Windows Hello para Empresas é um método alternativo para entrar no Windows que substitui senhas, cartões inteligentes e cartões inteligentes virtuais.  

  - Quando definido como *Sim*, você habilita essa política e o dispositivo provisiona o Windows Hello para empresas.  
  - Quando definido como *não configurado*, a linha de base não afeta a configuração de política do dispositivo. Isso significa que, se o Windows Hello para empresas estiver desabilitado em um dispositivo, ele permanecerá desabilitado. Se estiver habilitado, ele permanecerá habilitado. 

  Não é possível desabilitar o Windows Hello para empresas por meio desta linha de base. Você pode desabilitar o Windows Hello para empresas ao configurar o [registro do Windows](windows-hello.md)ou como parte de um perfil de configuração do dispositivo para a proteção de [identidade](identity-protection-configure.md).  

O Windows Hello para Empresas é um método alternativo para entrar no Windows que substitui senhas, cartões inteligentes e cartões inteligentes virtuais.  

  Se você habilitar ou não definir essa configuração de política, o dispositivo provisionará o Windows Hello para Empresas. Se você desabilitar essa configuração de política, o dispositivo não provisionará o Windows Hello para Empresas para qualquer usuário.

  O Intune não dá suporte à desabilitação do Windows Hello. Em vez disso, você pode configurar a política para habilitar o Windows Hello para Empresas (Sim) ou não configurar o Windows Hello diretamente (não configurado). Quando não estiver configurado, um dispositivo pode receber a configuração por meio de outra política, o que pode ativar ou desativar esse recurso.  

  **Padrão**: Sim  

- **Exigir letras minúsculas no PIN** - *TenantId/Policies/PINComplexity/LowercaseLetters*  
  **Padrão**: Permitido  

- **Exigir caracteres especiais no PIN** - *TenantId/Policies/PINComplexity/SpecialCharacters*  
  **Padrão**: Permitido  

- **Exigir letras maiúsculas no PIN** - *TenantId/Policies/PINComplexity/UppercaseLetters*   
  **Padrão**: Permitido  

