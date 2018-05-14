---
title: Adicionar proteção de ponto de extremidade no Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Em dispositivos Windows 10, use ou defina as configurações de proteção de ponto de extremidade para habilitar inclusões do recurso Windows Defender, Application Guard, Firewall, SmartScreen, criptografia e bitLocker, Exploit Guard, Controle de Aplicativos, Central de Segurança e segurança em dispositivos locais no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 069f71d75c0a9c7cec083a929f89a2b39bb4aac5
ms.sourcegitcommit: 4c06fa8e9932575e546ef2e880d96e96a0618673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-intune"></a>Configurações do Endpoint Protection para o Windows 10 (e posteriores) no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O perfil do Endpoint Protection permite controlar os recursos de segurança em dispositivos Windows 10, como o BitLocker e o Windows Defender.

Use as informações neste artigo para criar perfis de Endpoint Protection. Para configurar o Windows Defender Antivírus, confira [Restrições de dispositivo no Windows 10](device-restrictions-windows-10.md#windows-defender-antivirus). 

> [!NOTE]
> Essas configurações não têm suporte nas edições Professional e Home do Windows 10.

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Ao usar o Microsoft Edge, o Windows Defender Application Guard protege seu ambiente contra sites que ainda não foram definidos como confiáveis pela sua organização. Quando os usuários visitam sites que não estão listados no limite de rede isolada, os sites serão abertos em uma sessão de navegação virtual no Hyper-V. Sites confiáveis são definidos por um limite de rede, que pode ser configurado na Configuração do Dispositivo. 

O Application Guard só está disponível para dispositivos Windows 10 (64 bits). Usar esse perfil instala um componente do Win32 para ativar o Application Guard.

- **Application Guard**: abra sites não aprovados em um contêiner de navegação virtualizado do Hyper-V.
- **Comportamento da área de transferência**: escolha quais ações de copiar/colar são permitidas entre o computador local e o navegador virtual do Application Guard.
- **Conteúdo externo em sites corporativos**: bloqueie o carregamento do conteúdo de sites não aprovados.
- **Impressão do navegador virtual**: permita que impressoras de PDF, XPS e/ou de rede local imprimam o conteúdo do navegador virtual.
- **Coletar logs**: colete logs de eventos que ocorrem dentro de uma sessão de navegação do Application Guard.
- **Manter dados de navegador gerados pelo usuário**: salve dados do usuário (como senhas, favoritos e cookies) criados durante uma sessão de navegação virtual do Application Guard.
- **Aceleração gráfica**: carregue mais rapidamente sites que fazem uso intenso de elementos gráficos ao trabalhar na sessão de navegação virtual do Application Guard. Os sites são carregados mais rapidamente habilitando acesso a uma unidade de processamento de gráficos virtuais.
- **Baixar arquivos para o sistema de arquivos de host**: permite que os usuários baixem os arquivos do navegador virtualizado no sistema operacional do host.

## <a name="windows-defender-firewall"></a>Windows Defender Firewall

### <a name="global-settings"></a>Configurações globais

Essas configurações são aplicáveis a todos os tipos de rede.

- **Protocolo FTP**: bloqueie FTP com estado.
- **Tempo ocioso da associação de segurança antes da exclusão**: as associações de segurança são excluídas quando não for detectado nenhum tráfego de rede por *n* segundos.
- **Codificação de chave pré-compartilhada**: codifique chaves pré-compartilhadas usando UTF-8.
- **Isenções de IPsec**: configure um tráfego específico como isento do IPsec, incluindo **Códigos de tipo ICMP de IPv6 de descoberta de vizinho**, **ICMP**, **Códigos de tipo ICMP de IPv6 de descoberta de roteador** e **Tráfegos de rede DHCP de IPv4 e IPv6**.
- **Verificação da lista de certificados revogados**: defina um valor para indicar como a verificação da lista de certificados revogados será imposta, incluindo **Desabilitar a verificação de CRL**, **Falhar verificação de CRL somente para certificado revogado** e **Falhar verificação de CRL para qualquer erro encontrado**.
- **Combinar de modo oportuno o conjunto de autenticação por módulo de chave**: defina os módulos de chave para ignorar todo o conjunto de autenticação caso eles não tenham suporte para todos os pacotes de autenticação no conjunto.
- **Enfileiramento de pacotes**: informe como o dimensionamento do software no lado do recebimento será habilitada para o recebimento criptografado e o encaminhamento de texto não criptografado para o cenário de gateway de túnel IPsec. Essa configuração garante que a ordem de pacotes seja preservada.

### <a name="network-settings"></a>Configurações da rede

Essas configurações aplicam-se a tipos de rede específicos, incluindo **Rede de domínio (local de trabalho)**, **Rede privada (detectável)** e **Rede pública (não detectável)**.

#### <a name="general-settings"></a>Configurações gerais

- **Windows Defender Firewall**: habilite essa configuração para bloquear o tráfego de rede.
- **Modo oculto**: bloqueie a operação do firewall em modo oculto. O bloqueio do modo furtivo permite bloquear também a **Isenção de pacote protegido por IPsec**.
- **Blindado**: habilitar essa configuração e a configuração de firewall bloqueará todo o tráfego de entrada.
- **Respostas unicast para transmissões multicast**: bloqueie respostas unicast para transmissões multicast. Normalmente, você não deseja receber respostas unicast para mensagens de difusão ou multicast. Essas respostas podem indicar um ataque de DOS (negação de serviço) ou um invasor tentando sondar um computador ativo conhecido.
- **Notificações de entrada**: bloqueie a exibição de notificações para os usuários quando a escuta de um aplicativo estiver bloqueada em uma porta.
- **Ação padrão para conexões de entrada**: bloqueie a ação padrão que o firewall executa nas conexões de entrada.

#### <a name="rule-merging"></a>Mesclagem de regra

- **Regras do Windows Defender Firewall de aplicativo autorizados do repositório local**: aplique regras de firewall autorizadas no repositório local para serem reconhecidas e impostas.
- **Regras do Windows Defender Firewall de porta global do repositório local**: aplique regras de firewall de porta globais no repositório local para serem reconhecidas e impostas.
- **Regras do Windows Defender Firewall do repositório local**: aplique regras de firewall globais no repositório local a serem reconhecidas e impostas.
- **Regras de IPsec do repositório local**: aplique regras de segurança de conexão do repositório local, independentemente das versões de regra de segurança do esquema ou da conexão.

## <a name="windows-defender-smartscreen-settings"></a>Configurações do Windows Defender SmartScreen

- **SmartScreen para aplicativos e arquivos**: habilite o Windows SmartScreen para execução de arquivos e aplicativos em execução.
- **Execução de arquivos não verificados**: impeça que o usuário final execute arquivos que não foram verificados pelo Windows SmartScreen.

## <a name="windows-encryption"></a>Criptografia do Windows

### <a name="windows-settings"></a>Configurações do Windows

As duas configurações a seguir se aplicam a todas as versões do Windows 10:

- **Criptografar dispositivos**: se habilitado, os usuários são solicitados a habilitar a criptografia do dispositivo. Além disso, é solicitado que eles confirmem que a criptografia de outro provedor não foi habilitada. Se a criptografia do Windows for ativada enquanto outro método de criptografia está ativo, o dispositivo pode se tornar instável.
- **Criptografar cartão de memória**: habilite essa configuração para criptografar os cartões de memória removíveis usados pelo dispositivo.


### <a name="bitlocker-base-settings"></a>Configurações base do BitLocker

As configurações básicas são as configurações universais do BitLocker para todos os tipos de unidades de dados. As configurações de política de grupo do BitLocker gerenciam quais tarefas de criptografia de unidade ou opções de configuração o usuário final pode modificar em todos os tipos de unidades de dados.

- **Aviso para outra criptografia de disco**: desabilite a mensagem de aviso para outra criptografia de disco nos computadores dos usuários finais.
- **Configurar métodos de criptografia**: habilite essa configuração para definir os algoritmos de criptografia para o sistema operacional, dados e unidades removíveis.
  - **Criptografia para unidades do sistema operacional**: escolha o método de criptografia para unidades do sistema operacional. Recomendamos que você use o algoritmo XTS-AES.
  - **Criptografia para unidades de dados fixas**: escolha o método de criptografia para unidades de dados fixas (internas). Recomendamos que você use o algoritmo XTS-AES.
  - **Criptografia para unidades de dados removíveis**: escolha o método de criptografia para unidades de dados removíveis. Se a unidade removível for usada com dispositivos que não executam o Windows 10, é recomendável usar o algoritmo AES-CBC.

### <a name="bitlocker-os-drive-settings"></a>Configurações de unidade do sistema operacional do BitLocker

Essas configurações aplicam-se especificamente às unidades de dados do sistema operacional.

- **Autenticação adicional na inicialização**: configure os requisitos da autenticação de inicialização do computador, incluindo o uso do TPM (Trusted Platform Module).
  - **BitLocker com chip do TPM não compatível**
  - **Inicialização de TPM compatível**: escolha permitir, não permitir ou exigir o chip do TPM.
  - **Inicialização de TPM compatível PIN**: escolha permitir, não permitir ou exigir o uso de um PIN de inicialização com o chip do TPM.
  - **Chave de inicialização de TPM compatível**: escolha permitir, não permitir ou exigir o uso de uma chave de inicialização com o chip do TPM.
  - **PIN e chave de inicialização de TPM compatível**: escolha permitir, não permitir ou exigir o uso de um PIN e uma chave de inicialização com o chip do TPM.
- **Tamanho mínimo do PIN**: habilite essa configuração para definir um tamanho mínimo para o PIN de inicialização de TPM.
  - **Número mínimo de caracteres**: insira o número de caracteres necessário para o PIN de inicialização variando de **4**-**20**.
- **Recuperação de unidade do sistema operacional**: habilite essa configuração para controlar como as unidades do sistema operacional protegidas pelo BitLocker são recuperadas quando as informações de inicialização necessárias não estão disponíveis.
  - **Agente de recuperação de dados baseada em certificado**: habilite essa configuração se quiser que os agentes de recuperação de dados possam ser usados com as unidades do sistema operacional protegidas pelo BitLocker.
  - **Criação de senha de recuperação pelo usuário**: escolha se é permitido, obrigatório ou não permitido que os usuários gerem uma senha de recuperação de 48 dígitos.
  - **Criação de chave de recuperação pelo usuário**: escolha se é permitido, obrigatório ou não permitido que os usuários gerem uma chave de recuperação de 256 bits.
  - **Opções de recuperação no assistente de instalação do BitLocker**: habilite essa configuração para impedir que os usuários vejam ou alterem as opções de recuperação ao ativarem o BitLocker.
  - **Salvar informações de recuperação do BitLocker no AD DS**: habilita o armazenamento de informações de recuperação do BitLocker no Active Directory.
  - **Informações de recuperação do BitLocker armazenadas no AD DS**: configure quais partes das informações de recuperação do BitLocker são armazenadas no Active Directory. Escolha:
    - **Fazer backup de pacotes de chaves e senhas de recuperação**
    - **Fazer backup somente de senhas de recuperação**
  - **Armazenar informações de recuperação no AD DS antes de habilitar o BitLocker**: habilite essa configuração para impedir que os usuários ativem o BitLocker, a menos que o dispositivo esteja ingressado no domínio e que as informações de recuperação do BitLocker tenham sido armazenadas com êxito no Active Directory.
- **Mensagem e URL de recuperação pré-inicialização**: habilite essa configuração para definir a mensagem e a URL que serão exibidas na tela de recuperação de chave pré-inicialização.
  - **Mensagem de recuperação pré-inicialização**: configure como a mensagem de recuperação pré-inicialização é exibida para os usuários. Escolha:
    - **Usar mensagem e URL de recuperação padrão**
    - **Usar mensagem e URL de recuperação vazia**
    - **Usar mensagem de recuperação personalizada**
    - **Usar URL de recuperação personalizada**

### <a name="bitlocker-fixed-data-drive-settings"></a>Configurações de unidades de dados fixas do BitLocker

- **Acesso de gravação para unidades de dados fixas não protegidas pelo BitLocker**: se habilitado, a proteção do BitLocker deverá ser habilitada em todas as unidades de dados fixas ou internas para que seja possível gravar nelas.
- **Recuperação de unidade fixa**: habilite essa configuração para controlar como as unidades fixas protegidas pelo BitLocker serão recuperadas quando as informações de inicialização necessárias não estiverem disponíveis.
  - **Agente de recuperação de dados**: habilite essa configuração se quiser que os agentes de recuperação de dados possam ser usados com as unidades fixas protegidas pelo BitLocker.
  - **Criação de senha de recuperação pelo usuário**: configure se é permitido, obrigatório ou não permitido que os usuários gerem uma senha de recuperação de 48 dígitos.  
  - **Criação de chave de recuperação pelo usuário**: configure se é permitido, necessário ou não permitido que os usuários gerem uma chave de recuperação de 256 bits.
  - **Opções de recuperação no assistente de instalação do BitLocker**: habilite essa configuração para impedir que os usuários vejam ou alterem as opções de recuperação ao ativarem o BitLocker.
  - **Salvar informações de recuperação do BitLocker no AD DS**: habilita o armazenamento de informações de recuperação do BitLocker no Active Directory.
  - **Informações de recuperação do BitLocker no AD DS**: configure quais partes das informações de recuperação do BitLocker são armazenadas no Active Directory. Escolha:
    - **Fazer backup de pacotes de chaves e senhas de recuperação**
    - **Fazer backup somente de senhas de recuperação**
  - **Armazenar informações de recuperação no AD DS antes de habilitar o BitLocker**: habilite essa configuração para impedir que os usuários ativem o BitLocker, a menos que o dispositivo esteja adicionado ao domínio e que as informações de recuperação do BitLocker tenham sido armazenadas com êxito no Active Directory.

### <a name="bitlocker-removable-data-drive-settings"></a>Configurações de unidade de dados removíveis do BitLocker

- **Acesso de gravação para unidades de dados removíveis não protegidas pelo BitLocker**: especifique se a criptografia do BitLocker é necessária para unidades de armazenamento removíveis.
  - **Acesso de gravação a dispositivos configurados em outra organização**: especifique se é possível gravar em unidades de dados removíveis que pertencem a outra organização.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Use o [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) para gerenciar e reduzir a superfície de ataque de aplicativos usados pelos seus funcionários.

### <a name="attack-surface-reduction"></a>Redução da superfície de ataque

- **Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows**

Ajude a [impedir que aplicativos e ações](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard), que normalmente são usados por malwares em busca de exploração, infectem computadores.

#### <a name="rules-to-prevent-office-macro-threats"></a>Regras para impedir ameaças a macros do Office

Impeça que os aplicativos do Office executem as seguintes ações:

- **Injeção de aplicativos do Office em outros processos (sem exceções)**
- **Criação de conteúdo executável por aplicativos/macros do Office**
- **Inicialização de processos filhos por aplicativos do Office**
- **Importações do Win32 de código de macro do Office**

#### <a name="rules-to-prevent-script-threats"></a>Regras para impedir ameaças de script

Bloqueie o seguinte para ajudar a prevenir ameaças de script:

- **Código de js/vbs/ps/macro ofuscado**
- **Execução de conteúdo baixado da Internet pelo js/vbs (sem exceções)**
- **Criação de processo usando comandos WMI e PSExec**
- **Processos não assinados e não confiáveis executados de um USB**
- **Executáveis que não atendem um critério de prevalência, idade ou lista confiável**

#### <a name="rules-to-prevent-email-threats"></a>Regras para impedir ameaças de email

Bloqueie o seguinte para ajudar a prevenir ameaças por email:

- **Execução de conteúdo executável (exe, dll, ps, js, vbs, etc.) proveniente do email (cliente de webmail/email) (sem exceções)**

#### <a name="rules-to-protect-against-ransomware"></a>Regras para proteger-se contra ransomware
- **Proteção avançada contra ransomware**

> [!TIP]
> [Reduzir superfícies de ataque com o Windows Defender Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) fornece mais detalhes sobre essas regras.

#### <a name="attack-surface-reduction-exceptions"></a>Exceções de redução da superfície de ataque

- **Arquivos e pastas a serem excluídos das regras de redução da superfície de ataque**: importe/adicione uma lista de locais a serem excluídos das regras configuradas.

### <a name="controlled-folder-access"></a>Acesso controlado à pasta

Ajude a proteger dados valiosos contra ameaças e aplicativos mal-intencionados, como ransomware.

- **Proteção de pasta**: proteja arquivos e pastas contra alterações indesejadas realizadas por aplicativos mal-intencionados. Você pode importar uma **Lista de aplicativos com acesso a pastas protegidas** ou adicioná-los manualmente. Você também pode adicionar uma **Lista de pastas adicionais que precisam ser protegidas** com um upload ou adicioná-las manualmente.

### <a name="network-filtering"></a>Filtragem de rede

Bloqueie conexões de saída de qualquer aplicativo para IPs/domínios de reputação ruim.

### <a name="exploit-protection"></a>Proteção contra explorações

Bloqueie a **Edição pelo usuário da interface de proteção contra exploração** carregando um arquivo XML que permite configurar a memória, o fluxo de controle e as restrições de política. As configurações no arquivo XML podem ser usadas para bloquear um aplicativo contra explorações.

Para habilitar o Exploit Protection, crie um arquivo XML que represente as configurações da sua escolha para mitigação do sistema e do aplicativo. Você pode fazer isso usando um destes dois métodos:

 1. PowerShell: use um ou mais dos cmdlets Get-ProcessMitigation, Set-ProcessMitigation e ConvertTo-ProcessMitigationPolicy PowerShell. Os cmdlets definem configurações de mitigação e exportam uma representação XML deles.

 2. Interface do usuário da Central de Segurança do Windows Defender: na Central de Segurança do Windows Defender, clique no controle de aplicativo e navegador e, em seguida, role até a parte inferior da tela resultante para localizar o Exploit Protection. Primeiro, use as guias Configurações do sistema e Configurações do programa para definir as configurações de mitigação. Em seguida, localize o link Exportar configurações na parte inferior da tela para exportar uma representação XML delas.

## <a name="windows-defender-application-control"></a>Controle de Aplicativos do Windows Defender

Use as **Políticas de integridade de código do controle de aplicativos** para escolher os aplicativos adicionais que precisam ser auditados ou que são confiáveis para serem executados pelo Controle de Aplicativos do Windows Defender. Os componentes do Windows e todos os aplicativos da Windows Store são automaticamente confiáveis para execução.

Os aplicativos não são bloqueados durante a execução no modo **somente auditoria**. O modo **Somente auditoria** registra todos os eventos em logs do cliente local.

Uma vez habilitado, o Controle do Aplicativo poderá ser desabilitado somente alterando o modo de **Impor** para **Somente auditoria**. Alterar o modo de **Impor** para **Não Configurado** resultará no Controle do Aplicativo continuar a ser imposto nos dispositivos atribuídos.

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard
O Windows Defender Credential Guard protege contra ataques de roubo de credenciais. Ele isola segredos de modo que apenas o software do sistema privilegiado possa acessá-los.

As configurações do **Credential Guard** incluem:

- **Desabilitada**: desativará o Credential Guard remotamente se ele tiver sido ativado anteriormente com a opção **Habilitada sem bloqueio de UEFI**.
- **Habilitada com o bloqueio de UEFI**: garante que o Credential Guard não possa ser desabilitado remotamente usando a chave do Registro ou a Política de Grupo.

    > [!NOTE]
    > Se você usar essa configuração e depois quiser desabilitar o Credential Guard, deverá definir a Política de Grupo como **Desabilitada**. Além disso, limpe fisicamente as informações de configuração de UEFI de cada computador. Enquanto a configuração da UEFI for mantida, o Credential Guard estará habilitado.

- **Habilitado sem bloqueio de UEFIE**: permite que o Credential Guard seja desabilitado remotamente usando a Política de Grupo. Os dispositivos que usam essa configuração devem estar executando, Windows 10 versão 1511 e mais recentes.

Quando você habilita o Credential Guard, os seguintes recursos obrigatórios também são habilitados:

- VBS (**Segurança baseada em Virtualização**): será ativada durante a próxima reinicialização. A segurança baseada em virtualização usa o Hipervisor do Windows para dar suporte aos serviços de segurança.
- **Inicialização Segura com Acesso Direto à Memória**: ativa a VBS com Inicialização Segura e AMD (acesso direto à memória). Proteções de AMD exigem suporte de hardware e são habilitadas somente em dispositivos configurados corretamente.

## <a name="windows-defender-security-center"></a>Central de Segurança do Windows Defender

O aplicativo da Central de Segurança do Windows Defender opera como um aplicativo ou processo separado de cada um dos recursos individuais. Ele exibe notificações por meio da Central de Ações. Ele atua como um coletor ou um único lugar para ver o status e executar algumas etapas de configuração para cada um dos recursos. Encontre mais informações nos documentos do [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Aplicativo Central de Segurança do Windows Defender e notificações

Bloqueie o acesso de usuário final às várias áreas do aplicativo da Central de Segurança do Windows Defender. Ocultar uma seção também bloqueará as notificações relacionadas.

- **Proteção contra vírus e ameaças**
- **Integridade e desempenho do dispositivo**
- **Proteção de firewall e rede**
- **Controle de aplicativo e navegador**
- **Opções da família**
- **Notificações das áreas exibidas do aplicativo**: escolha quais notificações serão exibidas aos usuários finais. As notificações não críticas incluem resumos de atividades do Windows Defender Antivírus, incluindo notificações após a conclusão das verificações. Todas as outras notificações são consideradas críticas.

#### <a name="it-contact-information"></a>Informações de contato de TI

Forneça as informações de contato de TI que aparecem no aplicativo da Central de Segurança do Windows Defender e as notificações do aplicativo. Você pode escolher **Exibir no aplicativo e em notificações**, **Exibir somente no aplicativo**, **Exibir somente em notificações** ou **Não exibir**. Você deve inserir o **nome da organização de TI** e pelo menos uma das seguintes opções de contato:

- **Número de telefone ou ID do Skype do departamento de TI**
- **Endereço de email do departamento de TI**
- **URL do site de suporte de TI**

## <a name="local-device-security-options"></a>Opções de segurança de dispositivo local

Use estas opções para definir as configurações de segurança locais em dispositivos Windows 10.

### <a name="accounts"></a>Contas

- **Adicionar novas contas da Microsoft**: impeça que usuários adicionem novas contas da Microsoft a este computador.
- **Logon remoto sem senha**: habilite contas locais que não são protegidas por senha a fazer logon de locais que não o dispositivo físico.

#### <a name="admin"></a>Administrador

- **Conta do administrador local**: determine se a conta de Administrador local está habilitada ou desabilitada.
- **Renomear a conta do administrador**: defina um nome de conta diferente a ser associado ao SID (identificador de segurança) para a conta de Administrador.

#### <a name="guest"></a>Convidado

- **Conta de convidado**: determine se a conta de Convidado está habilitada ou desabilitada.
- **Renomear a conta de convidado**: defina um nome de conta diferente a ser associado ao SID (identificador de segurança) para a conta de Convidado.

### <a name="devices"></a>Dispositivos

- **Desencaixar dispositivo sem logon**: impeça que um computador portátil seja desencaixado sem necessidade de logon.
- **Instalar drivers de impressora para impressoras compartilhadas**: restrinja a instalação de drivers de impressora como parte de conectar-se a uma impressora compartilhada somente a administradores.
- **Restrinja o acesso de CD-ROM para o usuário ativo local**: habilitar essa configuração permite apenas que o usuário conectado interativamente acesse a mídia de CD-ROM
- **Formatar e ejetar a mídia removível**: defina quem tem permissão para formatar e ejetar mídia NTFS removível:
  - **Não configurado**
  - **Administradores e Usuários Avançados**
  - **Administradores e Usuários Interativos**

### <a name="interactive-logon"></a>Logon interativo

- **Minutos de inatividade da tela de bloqueio até a proteção de tela ser ativada**: defina o máximo de minutos de inatividade na tela de logon da área de trabalho interativa até que a proteção de tela seja executada.
- **Exigir CTRL+ALT+DEL para fazer logon**: exija que CTRL+ALT+DEL seja pressionado antes que um usuário possa fazer logon.
- **Comportamento de remoção de cartão inteligente**: determina o que acontece quando o cartão inteligente para um usuário conectado é removido do leitor de cartão inteligente.
[Opções de LocalPoliciesSecurity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior) fornecem mais detalhes.

#### <a name="display"></a>Vídeo

- **Informações do usuário na tela de bloqueio**: configure as informações do usuário exibidas quando a sessão está bloqueada. Se não configurado, o nome de exibição do usuário, o domínio e o nome de usuário serão mostrados.
  - **Somente nome de exibição do usuário**
  - **Não exibir informações do usuário**
  - **Não configurado**: nome de exibição do usuário, domínio e nome de usuário
- **Ocultar o último usuário conectado**: não exibir o nome de usuário da última pessoa que entrar neste dispositivo.
- **Ocultar o nome de usuário na entrada**: não exiba o nome de usuário da pessoa que está entrando neste dispositivo depois que as credenciais forem inseridas e antes que a área de trabalho do dispositivo seja mostrada.
- **Título da mensagem de logon**: defina o título da mensagem para usuários que estejam tentando fazer logon.
- **Texto da mensagem de logon**: defina o texto da mensagem para usuários que estejam tentando fazer logon.

### <a name="network-access-and-security"></a>Acesso e segurança de rede

- **Acesso anônimo a Compartilhamentos e Pipes Nomeados**: restringe o acesso anônimo a configurações de Compartilhamento e Pipe Nomeado. Aplica-se às configurações que podem ser acessadas anonimamente.
- **Enumeração anônima de contas SAM**: permite que usuários anônimos enumerem as contas SAM. O Windows permite que usuários anônimos enumerem os nomes de contas de domínio e compartilhamentos de rede.
- **Enumeração anônima de compartilhamentos e contas SAM**: pode bloquear a enumeração anônima de compartilhamentos e contas SAM. O Windows permite que usuários anônimos enumerem os nomes de contas de domínio e compartilhamentos de rede.
- **Valor de hash do LAN Manager armazenado na alteração de senha**: na próxima alteração de senha, escolha se o valor de hash do LM (LAN Manager) para a nova senha é armazenado. Ele não é armazenado por padrão.
- **Solicitações de autenticação PKU2U**: bloqueie solicitações de autenticação PKU2U para este dispositivo usar identidades online.
- **Restringir conexões RPC remotas ao SAM**: edite a cadeia de caracteres da Linguagem de Definição do Descritor de Segurança padrão para permitir ou proibir que usuários e grupos façam chamadas remotas para o SAM.
- **Descritor de segurança**

### <a name="recovery-console-and-shutdown"></a>Console de recuperação e desligamento

- **Limpar arquivo de paginação de memória virtual ao desligar**: limpe o arquivo de paginação de memória virtual quando o dispositivo for desligado.
- **Desligamento sem logon**: bloqueie a opção de desligar o computador da tela de logon do Windows. Neste caso, os usuários devem poder fazer logon no computador com êxito e antes de poderem executar um desligamento do sistema.

### <a name="user-account-control"></a>Controle de conta de usuário

- **Integridade de UIA sem local seguro**: habilite aplicativos de locais não seguros no sistema de arquivos a serem executados com nível de integridade UIAccess.
- **Virtualizar falhas de gravação de arquivo e Registro para locais por usuário**: determine se as falhas de gravação do aplicativo são redirecionadas para locais de sistema de arquivos e registro definidos. Ou faça o aplicativo falhar.
- **Somente elevar arquivos executáveis assinados e validados**: imponha validação de caminho de certificação de PKI a um determinado arquivo executável antes de permitir a execução.

#### <a name="uia-elevation-prompt-behavior-settings"></a>Configurações de comportamento da solicitação de elevação de UIA

- **Solicitação de elevação para administradores**: defina o comportamento da solicitação de elevação para administradores no Modo de Aprovação de Administrador:
  - **Elevar sem solicitar**
  - **Solicitar credenciais na área de trabalho protegida**
  - **Solicitar consentimento na área de trabalho protegida**
  - **Solicitar credenciais**
  - **Solicitar consentimento**
  - **Não configurado**: solicitar consentimento para binários não Windows
- **Solicitação de elevação para usuários padrão**: defina o comportamento da solicitação de elevação para usuários padrão:
  - **Negar automaticamente solicitações de elevação**
  - **Solicitar credenciais na área de trabalho protegida**
  - **Não configurado**: prompt para credenciais
- **Rotear solicitações de elevação para área de trabalho interativa do usuário**: habilite todas as solicitações de elevação para irem para a área de trabalho do usuário interativo, em vez de irem para a área de trabalho protegida. São usadas configurações de política de comportamento de solicitação para administradores e usuários padrão.
- **Solicitação elevada para instalações de aplicativo**: instalações de aplicativos que requerem privilégios elevados solicitarão as credenciais de administrador.
- **Solicitação de elevação de UIA sem a área de trabalho protegida**: permita a aplicativos UIAccess solicitar elevação sem usarem a área de trabalho protegida.

#### <a name="admin-approval-mode-settings"></a>Configurações do Modo de Aprovação de Administrador

- **Modo de Aprovação de Administrador para Conta de Administrador Interno**: define se a conta de administrador interno usa o Modo de Aprovação de Administrador ou executa todos os aplicativos com privilégios de administrador completos.
- **Executar todos os administradores no Modo de Aprovação de Administrador**: defina se o Modo de Aprovação de Administrador e todas as configurações de política UAC estão habilitadas.

### <a name="microsoft-network-client"></a>Cliente da Rede Microsoft

- **Assinar comunicações digitalmente (se o servidor concordar)**: determina se o cliente SMB tenta negociar a assinatura do pacote SMB. Quando habilitado (padrão), o cliente de rede Microsoft solicita que o servidor execute assinatura de pacote SMB na configuração da sessão. Se a assinatura de pacote tiver sido habilitada no servidor, a assinatura de pacote será negociada. Se esta política estiver desabilitada, o cliente SMB nunca negociará a assinatura de pacote SMB.
- **Enviar senha não criptografada para servidores SMB de terceiros**: quando habilitado, o redirecionador de protocolo SMB (bloco de mensagens de servidor) tem permissão para enviar senhas de texto sem formatação para servidores SMB não Microsoft que não dão suporte a criptografia de senha durante a autenticação.

### <a name="microsoft-network-server"></a>Microsoft Network Server

- **Assinar comunicações digitalmente (se o cliente concordar)**: determina se o servidor SMB negocia a assinatura de pacote SMB com clientes que a solicitam. Quando habilitada, o servidor da rede Microsoft negocia a assinatura de pacote SMB conforme solicitado pelo cliente. Ou seja, se a assinatura de pacote estiver habilitada no cliente, a assinatura de pacote será negociada. Quando desabilitada (padrão), o cliente SMB nunca negocia a assinatura de pacote SMB.
- **Assinar comunicações digitalmente (sempre)**: determina se a assinatura de pacote é exigida pelo componente do servidor SMB. Quando habilitado, o servidor da rede Microsoft não se comunicará com um cliente de rede da Microsoft, a menos que o cliente concorde em executar a assinatura de pacote SMB. Quando desabilitada (padrão), a assinatura de pacote SMB é negociada entre o cliente e servidor.

## <a name="next-steps"></a>Próximas etapas

Para atribuir esse perfil a grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
