---
title: Adicionar proteção de ponto de extremidade no Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Em dispositivos Windows 10, use ou defina as configurações de proteção de ponto de extremidade para habilitar inclusões do recurso Windows Defender, Application Guard, Firewall, SmartScreen, criptografia e bitLocker, Exploit Guard, Controle de Aplicativos, Central de Segurança e segurança em dispositivos locais no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cc378a4f484852d84943b4d1094b71df5b7a530d
ms.sourcegitcommit: 006fa8dd4d605e2873fba6e3a965ef794d6f3764
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36945470"
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-intune"></a>Configurações do Endpoint Protection para o Windows 10 (e posteriores) no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O perfil do Endpoint Protection permite controlar os recursos de segurança em dispositivos Windows 10, como o BitLocker e o Windows Defender.

Use as informações neste artigo para criar perfis de Endpoint Protection. Para configurar o Windows Defender Antivírus, confira [Restrições de dispositivo no Windows 10](device-restrictions-windows-10.md#windows-defender-antivirus). 

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Compatível com as seguintes edições do Windows 10:

- Enterprise 
- Professional

Ao usar o Microsoft Edge, o Windows Defender Application Guard protege seu ambiente contra sites que não são confiáveis para sua organização. Quando os usuários visitam sites que não estão listados no limite de rede isolada, os sites são abertos em uma sessão de navegação virtual do Hyper-V. Sites confiáveis são definidos por um limite de rede, que pode ser configurado na Configuração do Dispositivo.

O Application Guard só está disponível para dispositivos Windows 10 (64 bits). Usar esse perfil instala um componente do Win32 para ativar o Application Guard.

- **Application Guard**: selecione **Habilitar** para ativar esse recurso, que abre sites não aprovados em um contêiner de navegação virtualizado do Hyper-V. **Não configurado** (padrão) significa que qualquer site (aprovado e não aprovado) é aberto no dispositivo.
- **Comportamento da área de transferência**: escolha quais ações de copiar/colar são permitidas entre o computador local e o navegador virtual do Application Guard.
- **Conteúdo externo em sites empresariais**: selecione **Bloquear** o carregamento de conteúdo de sites não aprovados. **Não configurado** (padrão) significa que sites não empresariais podem ser abertos no dispositivo.
- **Imprimir por meio do navegador virtual**: selecione **Permitir** para permitir que impressoras de PDF, XPS, locais e/ou de rede imprimam o conteúdo por meio do navegador virtual. **Não configurado** (padrão) desabilita todos os recursos de impressão.
- **Coletar logs**: selecione **Permitir** para coletar logs de eventos que ocorrem em uma sessão de navegação do Application Guard. **Não configurado** (padrão) não coleta logs na sessão de navegação.
- **Manter dados do navegador gerados pelo usuário**: selecione **Permitir** para permitir que os dados de usuário (como senhas, favoritos e cookies) criados durante uma sessão de navegação virtual do Application Guard sejam salvos. **Não configurado** (padrão) descarta os dados e os arquivos baixados pelo usuário quando o dispositivo é reiniciado, ou quando um usuário sai do serviço.
- **Aceleração de elementos gráficos**: selecione **Habilitar** para carregar mais rapidamente sites e vídeos com uso intenso de elementos gráficos obtendo acesso a uma unidade de processamento de elementos gráficos virtuais. **Não configurado** (padrão) usa a CPU do dispositivo para os elementos gráficos; ele não usa a unidade de processamento de elementos gráficos virtuais.
- **Baixar arquivos no sistema de arquivos de host**: selecione **Habilitar** para permitir que os usuários baixem arquivos do navegador virtualizado no sistema operacional do host. **Não configurado** (padrão) mantém os arquivos localmente no dispositivo e não baixa arquivos no sistema de arquivos de host.

## <a name="windows-defender-firewall"></a>Windows Defender Firewall

Compatível com as seguintes edições do Windows 10:
- Início
- Professional
- Negócios
- Enterprise
- Educação
- Celular
- Mobile Enterprise

### <a name="global-settings"></a>Configurações globais

Essas configurações são aplicáveis a todos os tipos de rede.

- **Protocolo FTP**: selecione **Bloquear** para desabilitar o FTP com estado. Quando essa opção é **Não configurado** (padrão), o firewall realiza a filtragem do FTP com estado para permitir conexões secundárias.
- **Tempo ocioso da associação de segurança antes da exclusão**: as associações de segurança são excluídas quando não for detectado nenhum tráfego de rede por *n* segundos. Insira um tempo ocioso em segundos.
- **Codificação de chave pré-compartilhada**: selecione **Habilitar** para usar a codificação de chave pré-compartilhada usando UTF-8. **Não configurado** (padrão) usa o valor do repositório local.
- **Isenções do IPsec**: configure um tráfego específico para ser isento do IPsec, incluindo:
  - **Códigos de tipo ICMP do IPv6 de descoberta de vizinho**
  - **ICMP**
  - **Códigos de tipo ICMP do IPv6 de descoberta de roteador**
  - **Tráfego de rede DHCP do IPv4 e IPv6**
- **Verificação da lista de certificados revogados**: determine como a verificação da lista de certificados revogados é imposta, incluindo **Desabilitar a verificação de CRL**, **Falhar verificação de CRL somente para certificado revogado** e **Falhar verificação de CRL para qualquer erro encontrado**.
- **Combinar de modo oportuno o conjunto de autenticação por módulo para chave**: selecione **Habilitar** para que os módulos para chave ignorem apenas os pacotes de autenticação para os quais eles não dão suporte. Quando essa opção é **Não configurado**, os módulos para chave DEVEM ignorar o conjunto completo de autenticação caso eles não deem suporte a todos os pacotes de autenticação especificados no conjunto.
- **Enfileiramento de pacotes**: informe como o dimensionamento do software no lado do recebimento será habilitada para o recebimento criptografado e o encaminhamento de texto não criptografado para o cenário de gateway de túnel IPsec. Essa configuração garante que a ordem de pacotes seja preservada.

### <a name="network-settings"></a>Configurações da rede

Essas configurações aplicam-se a tipos de rede específicos, incluindo **Rede de domínio (local de trabalho)**, **Rede privada (detectável)** e **Rede pública (não detectável)**.

#### <a name="general-settings"></a>Configurações gerais

- **Windows Defender Firewall**: selecione **Habilitar** para ativar o firewall e a segurança avançada. **Não configurado** (padrão) permite todo o tráfego de rede, independentemente de outras configurações de política.
- **Modo furtivo**: selecione **Bloquear** a operação do firewall em modo furtivo. O bloqueio do modo furtivo permite bloquear também a **Isenção de pacote protegido por IPsec**. **Não configurado** (padrão) opera o firewall no modo furtivo, o que ajuda a prevenir respostas a solicitações de investigação.
- **Blindado**: a opção **Bloquear** desliga esse recurso. **Não configurado** (padrão) habilita essa configuração. Quando essa configuração e o Windows Defender Firewall estão ativados, todo o tráfego de entrada é bloqueado, independentemente de outras configurações de política.
- **Respostas unicast para difusões multicast**: quando essa opção está definida como **Bloquear**, ela desabilita as respostas unicast para difusões multicast. Normalmente, você não deseja receber respostas unicast para mensagens de difusão ou multicast. Essas respostas podem indicar um ataque de DOS (negação de serviço) ou um invasor tentando sondar um computador ativo conhecido. **Não configurado** (padrão) habilita essa configuração.
- **Notificações de entrada**: quando essa opção está definida como **Bloquear**, ela oculta as notificações para os usuários quando um aplicativo é impedido de escutar em uma porta. **Não configurado** (padrão) habilita essa configuração e pode mostrar uma notificação para os usuários quando um aplicativo é impedido de escutar em uma porta.
- **Ação padrão para conexões de entrada**: quando essa opção está definida como **Bloquear**, a ação de firewall padrão não é executada em conexões de entrada. Quando essa opção está definida como **Não configurado** (padrão), a ação de firewall padrão é executada em conexões de entrada.

#### <a name="rule-merging"></a>Mesclagem de regra

- **Regras do Windows Defender Firewall de aplicativo autorizado do repositório local**: selecione **Habilitar** para aplicar as regras de firewall no repositório local a serem reconhecidas e impostas. Quando essa opção está definida como **Não configurado** (padrão), as regras de firewall de aplicativo autorizado no repositório local são ignoradas e não são impostas.
- **Regras do Windows Defender Firewall de porta global do repositório local**: selecione **Habilitar** para aplicar as regras de firewall de porta global no repositório local a serem reconhecidas e impostas. Quando essa opção está definida como **Não configurado** (padrão), as regras de firewall de porta global no repositório local são ignoradas e não são impostas.
- **Regras do Windows Defender Firewall do repositório local**: selecione **Habilitar** para aplicar as regras de firewall no repositório local a serem reconhecidas e impostas. Quando essa opção está definida como **Não configurado** (padrão), as regras de firewall no repositório local são ignoradas e não são impostas.
- **Regras do IPsec do repositório local**: selecione **Habilitar** para aplicar as regras de segurança de conexão no repositório local, independentemente das versões de regra de segurança da conexão ou do esquema. Quando essa opção está definida como **Não configurado** (padrão), as regras de segurança da conexão no armazenamento local são ignoradas e não são impostas, independentemente das versões de regra de segurança da conexão ou do esquema.

## <a name="windows-defender-smartscreen-settings"></a>Configurações do Windows Defender SmartScreen

Compatível com as seguintes edições do Windows 10 com o Edge instalado:
- Início
- Professional
- Negócios
- Enterprise
- Educação
- Celular
- Mobile Enterprise

**Configurações**:

- **SmartScreen para aplicativos e arquivos**: **habilite** o Windows SmartScreen para execução de arquivos e os aplicativos em execução. O SmartScreen é um componente baseado em nuvem para anti-phishing e antimalware. A opção **Não configurado** (padrão) desabilita o SmartScreen.
- **Execução de arquivos não verificados**: **impeça** que os usuários finais executem arquivos que não foram verificados pelo Windows SmartScreen. A opção **Não configurado** (padrão) desabilita esse recurso e permite aos usuários finais executar arquivos que ainda não foram verificados.

## <a name="windows-encryption"></a>Criptografia do Windows

### <a name="windows-settings"></a>Configurações do Windows

Compatível com as seguintes edições do Windows 10:

- Professional
- Negócios
- Enterprise
- Educação
- Celular
- Mobile Enterprise

**Configurações**:

- **Criptografar dispositivos**: **exija** a exibição de um prompt para os usuários para habilitar a criptografia de dispositivo. Dependendo da edição do Windows e a configuração do sistema, os usuários podem ser solicitados a:  
  - Confirmar que a criptografia de outro provedor não está habilitada
  - Desligar a Criptografia de Unidade de Disco BitLocker e, em seguida, ativar o BitLocker novamente
    
    Se a criptografia do Windows for ativada enquanto outro método de criptografia está ativo, o dispositivo pode se tornar instável. 
- **Criptografar cartão de memória (somente dispositivos móveis)**: selecione **Exigir** para criptografar os cartões de memória removíveis usados pelo dispositivo. A opção **Não configurado** (padrão) não exige a criptografia do cartão de memória e não solicita ao usuário para ativá-la. Essa configuração só se aplica a dispositivos Windows 10 Mobile.

### <a name="bitlocker-base-settings"></a>Configurações base do BitLocker

Compatível com as seguintes edições do Windows 10:

- Enterprise
- Educação
- Celular
- Mobile Enterprise

As configurações básicas são as configurações universais do BitLocker para todos os tipos de unidades de dados. Essas configurações gerenciam quais tarefas de criptografia de unidade ou opções de configuração o usuário final pode modificar em todos os tipos de unidades de dados.

- **Aviso para outras criptografias de disco**: selecione **Bloquear** para desabilitar o prompt de aviso se outro serviço de criptografia de disco estiver no dispositivo. A opção **Não configurado** (padrão) permite que o aviso seja mostrado.
- **Configurar métodos de criptografia**: **habilite** essa configuração para definir os algoritmos de criptografia para o sistema operacional, os dados e as unidades removíveis. Quando essa opção está definida como **Não configurado** (padrão), o BitLocker usa o XTS-AES de 128 bits como o método de criptografia padrão ou usa o método de criptografia especificado por qualquer script de instalação.
  - **Criptografia para unidades do sistema operacional**: escolha o método de criptografia para unidades do sistema operacional. Recomendamos que você use o algoritmo XTS-AES.
  - **Criptografia para unidades de dados fixas**: escolha o método de criptografia para unidades de dados fixas (internas). Recomendamos que você use o algoritmo XTS-AES.
  - **Criptografia para unidades de dados removíveis**: escolha o método de criptografia para unidades de dados removíveis. Se a unidade removível é usada com dispositivos que não executam o Windows 10, recomendamos o uso do algoritmo AES-CBC.

### <a name="bitlocker-os-drive-settings"></a>Configurações de unidade do sistema operacional do BitLocker
Compatível com as seguintes edições do Windows 10:

- Enterprise
- Educação
- Celular
- Mobile Enterprise

Essas configurações aplicam-se especificamente às unidades de dados do sistema operacional.

- **Autenticação adicional na inicialização**: selecione **Exigir** para configurar os requisitos de autenticação de inicialização do computador, incluindo o uso do TPM (Trusted Platform Module). Selecione **Não configurado** (padrão) para configurar somente as opções básicas em dispositivos com um TPM.
  - **BitLocker com chip TPM não compatível**: selecione **Bloquear** (desabilitar) usando o BitLocker quando um dispositivo não tiver um chip TPM compatível. Quando essa opção está definida como **Não configurado**, os usuários podem usar o BitLocker sem um chip TPM compatível. O BitLocker pode exigir uma senha ou uma chave de inicialização.
  - **Inicialização de TPM compatível**: escolha permitir, não permitir ou exigir o chip do TPM.
  - **Inicialização de TPM compatível PIN**: escolha permitir, não permitir ou exigir o uso de um PIN de inicialização com o chip do TPM. A habilitação de um PIN de inicialização exige a interação do usuário final. 
  - **Chave de inicialização de TPM compatível**: escolha permitir, não permitir ou exigir o uso de uma chave de inicialização com o chip do TPM. A habilitação de uma chave de inicialização exige a interação do usuário final. 
  - **PIN e chave de inicialização de TPM compatível**: escolha permitir, não permitir ou exigir o uso de um PIN e uma chave de inicialização com o chip do TPM. A habilitação de uma chave de inicialização e um PIN exige a interação do usuário final.
- **Tamanho Mínimo do PIN**: **habilite** essa configuração para definir um tamanho mínimo para o PIN de inicialização do TPM. Quando essa opção está definida como **Não configurado** (padrão), os usuários podem configurar um PIN de inicialização de qualquer tamanho entre 6 e 20 dígitos.
  - **Número mínimo de caracteres**: insira o número de caracteres necessário para o PIN de inicialização variando de **4**-**20**.
- **Recuperação de unidade do sistema operacional**: **habilite** essa configuração para controlar como as unidades do sistema operacional protegidas pelo BitLocker são recuperadas quando as informações de inicialização necessárias não estão disponíveis. Quando essa opção está definida como **Não configurado** (padrão), as opções de recuperação padrão são compatíveis com a recuperação do BitLocker. Por padrão, um DRA é permitido, as opções de recuperação são especificadas pelo usuário, incluindo a senha e a chave de recuperação, e as informações de recuperação não são copiadas em backup no AD DS.
  - **Agente de recuperação de dados baseado em certificado**: quando essa opção está definida como **Bloquear**, você não pode usar o agente de recuperação de dados com as unidades do sistema operacional protegidas pelo BitLocker. Defina essa opção como **Não configurado** (padrão) para habilitar essa configuração, o que permite o uso dos agentes de recuperação de dados com as unidades do sistema operacional protegidas pelo BitLocker.
  - **Criação de senha de recuperação pelo usuário**: escolha se é permitido, obrigatório ou não permitido que os usuários gerem uma senha de recuperação de 48 dígitos.
  - **Criação de chave de recuperação pelo usuário**: escolha se é permitido, obrigatório ou não permitido que os usuários gerem uma chave de recuperação de 256 bits.
  - **Opções de recuperação no assistente de instalação do BitLocker**: definido como **Bloquear** para que os usuários não possam ver e alterar as opções de recuperação. Quando essa opção está definida como **Não configurado** (padrão), os usuários podem ver e alterar as opções de recuperação ao ativarem o BitLocker.
  - **Salvar informações de recuperação do BitLocker no AD DS**: selecione **Habilitar** para armazenar de informações de recuperação do BitLocker no AAD (Azure Active Directory). Quando a opção é definida como **Não configurado** (padrão), as informações de recuperação não são armazenadas no AAD.
  - **Informações de recuperação do BitLocker armazenadas no AD DS**: configure quais partes das informações de recuperação do BitLocker são armazenadas no Azure AD. Escolha:
    - **Fazer backup de pacotes de chaves e senhas de recuperação**
    - **Fazer backup somente de senhas de recuperação**
  - **Armazenar informações de recuperação no AD DS antes de habilitar o BitLocker**: selecione **Exigir** essa configuração para impedir que os usuários ativem o BitLocker, a menos que as informações de recuperação do BitLocker tenham sido armazenadas com êxito no Azure Active Directory. **Não configurado** (padrão) permite que os usuários ativem o BitLocker, mesmo se as informações de recuperação não tenham sido armazenadas com êxito no Azure Active Directory.
- **Mensagem e URL de recuperação pré-inicialização**: **habilite** essa configuração para definir a mensagem e a URL exibidas na tela de recuperação de chave pré-inicialização. **Não configurado** (padrão) desabilita esse recurso.
  - **Mensagem de recuperação pré-inicialização**: configure como a mensagem de recuperação pré-inicialização é exibida para os usuários. Escolha:
    - **Usar mensagem e URL de recuperação padrão**
    - **Usar mensagem e URL de recuperação vazia**
    - **Usar mensagem de recuperação personalizada**
    - **Usar URL de recuperação personalizada**

### <a name="bitlocker-fixed-data-drive-settings"></a>Configurações de unidades de dados fixas do BitLocker

Compatível com as seguintes edições do Windows 10:

- Enterprise
- Educação
- Celular
- Mobile Enterprise

**Configurações**:

- **Acesso de gravação à unidade de dados fixa não protegida pelo BitLocker**: defina essa opção como **Bloquear** para conceder acesso somente leitura às unidades de dados que não são protegidas pelo BitLocker. Quando essa opção está definida como **Não configurado** (padrão), há o acesso de leitura e gravação nas unidades de dados que não são protegidas pelo BitLocker.
- **Recuperação de unidade fixa**: **habilite** essa configuração para controlar como as unidades fixas protegidas pelo BitLocker são recuperadas quando as informações de inicialização necessárias não estão disponíveis. **Não configurado** (padrão) desabilita esse recurso.
  - **Agente de recuperação de dados**: **bloqueie** o uso do agente de recuperação de dados com o Editor de Política das unidades fixas protegidas pelo BitLocker. A opção **Não configurado** (padrão) habilita o uso de agentes de recuperação de dados com unidades fixas protegidas pelo BitLocker.
  - **Criação de senha de recuperação pelo usuário**: configure se é permitido, obrigatório ou não permitido que os usuários gerem uma senha de recuperação de 48 dígitos.  
  - **Criação de chave de recuperação pelo usuário**: configure se é permitido, necessário ou não permitido que os usuários gerem uma chave de recuperação de 256 bits.
  - **Opções de recuperação no assistente de instalação do BitLocker**: definido como **Bloquear** para que os usuários não possam ver e alterar as opções de recuperação. Quando essa opção está definida como **Não configurado** (padrão), os usuários podem ver e alterar as opções de recuperação ao ativarem o BitLocker.
  - **Salvar informações de recuperação do BitLocker no AD DS**: selecione **Habilitar** para armazenar de informações de recuperação do BitLocker no AAD (Azure Active Directory). Quando a opção é definida como **Não configurado** (padrão), as informações de recuperação não são armazenadas no AAD.
  - **Informações de recuperação do BitLocker no AD DS**: configure quais partes das informações de recuperação do BitLocker são armazenadas no Azure Active Directory. Escolha:
    - **Fazer backup de pacotes de chaves e senhas de recuperação**
    - **Fazer backup somente de senhas de recuperação**
  - **Armazenar informações de recuperação no AD DS antes de habilitar o BitLocker**: selecione **Exigir** essa configuração para impedir que os usuários ativem o BitLocker, a menos que as informações de recuperação do BitLocker tenham sido armazenadas com êxito no Azure Active Directory. **Não configurado** (padrão) permite que os usuários ativem o BitLocker, mesmo se as informações de recuperação não tenham sido armazenadas com êxito no Azure Active Directory.

### <a name="bitlocker-removable-data-drive-settings"></a>Configurações de unidade de dados removíveis do BitLocker

Compatível com as seguintes edições do Windows 10:

- Enterprise
- Educação
- Celular
- Mobile Enterprise

**Configurações**:

- **Acesso de gravação à unidade de dados removível não protegida pelo BitLocker**: defina essa opção como **Bloquear** para conceder acesso somente leitura às unidades de dados que não são protegidas pelo BitLocker. Quando essa opção está definida como **Não configurado** (padrão), há o acesso de leitura e gravação nas unidades de dados que não são protegidas pelo BitLocker.
  - **Acesso de gravação a dispositivos configurados em outra organização**: a opção **Bloquear** permite o acesso de gravação a dispositivos configurados em outra organização. A opção **Não configurado** (padrão) nega o acesso de gravação.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Compatível com as seguintes edições do Windows 10:

- Início
- Professional
- Negócios
- Enterprise
- Educação
- Celular
- Mobile Enterprise

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

#### <a name="rules-to-protect-against-ransomware"></a>Regras para se proteger contra ransomware
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

Para habilitar o Exploit Protection, crie um arquivo XML que inclua as configurações desejadas de mitigação do sistema e do aplicativo. Há dois métodos:

 1. PowerShell: use um ou mais dos cmdlets Get-ProcessMitigation, Set-ProcessMitigation e ConvertTo-ProcessMitigationPolicy PowerShell. Os cmdlets definem configurações de mitigação e exportam uma representação XML deles.

 2. Interface do usuário da Central de Segurança do Windows Defender: na Central de Segurança do Windows Defender, clique no controle de aplicativo e navegador e, em seguida, role até a parte inferior da tela resultante para localizar o Exploit Protection. Primeiro, use as guias Configurações do sistema e Configurações do programa para definir as configurações de mitigação. Em seguida, localize o link Exportar configurações na parte inferior da tela para exportar uma representação XML delas.

Bloqueie a **Edição pelo usuário da interface de proteção contra exploração** carregando um arquivo XML que permite configurar a memória, o fluxo de controle e as restrições de política. As configurações no arquivo XML podem ser usadas para bloquear um aplicativo contra explorações. **Não configurado** (padrão) não envia por push uma configuração personalizada. 

## <a name="windows-defender-application-control"></a>Controle de Aplicativos do Windows Defender

Compatível com as seguintes edições do Windows 10:

**MDM (Gerenciamento de Dispositivo Móvel)**: 
- Professional
- Negócios
- Enterprise
- Educação
- Celular
- Mobile Enterprise

**Gerenciamento de Política de Grupo**: 
- Enterprise

Use as **Políticas de integridade de código do controle de aplicativos** para escolher os aplicativos adicionais que são auditados ou que são confiáveis para serem executados pelo Controle de Aplicativos do Windows Defender. Os componentes do Windows e todos os aplicativos da Windows Store são automaticamente confiáveis para execução.

Os aplicativos não são bloqueados quando executados no modo **somente auditoria**. O modo **Somente auditoria** registra todos os eventos em logs do cliente local.

Uma vez habilitado, o Controle do Aplicativo poderá ser desabilitado somente alterando o modo de **Impor** para **Somente auditoria**. Alterar o modo de **Impor** para **Não Configurado** resultará no Controle do Aplicativo continuar a ser imposto nos dispositivos atribuídos.

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard

Compatível com as seguintes edições do Windows 10:

- Enterprise

O Windows Defender Credential Guard protege contra ataques de roubo de credenciais. Ele isola segredos de modo que apenas o software do sistema privilegiado possa acessá-los.

As configurações do **Credential Guard** incluem:

- **Desabilitar**: desativará o Credential Guard remotamente se ele tiver sido ativado anteriormente com a opção **Habilitado sem bloqueio de UEFI**.

- **Habilitar com bloqueio de UEFI**: o Credential Guard não pode ser desabilitado remotamente usando uma chave do Registro ou uma Política de Grupo.

    > [!NOTE]
    > Se você usar essa configuração e depois quiser desabilitar o Credential Guard, deverá definir a Política de Grupo como **Desabilitada**. Além disso, limpe fisicamente as informações de configuração de UEFI de cada computador. Enquanto a configuração da UEFI for mantida, o Credential Guard estará habilitado.

- **Habilitar sem bloqueio de UEFI**: permite que o Credential Guard seja desabilitado remotamente usando uma Política de Grupo. Os dispositivos que usam essa configuração devem estar executando, Windows 10 versão 1511 e mais recentes.

Quando você habilita o Credential Guard, os seguintes recursos obrigatórios também são habilitados:

- VBS (**Segurança baseada em Virtualização**): será ativada durante a próxima reinicialização. A segurança baseada em virtualização usa o Hipervisor do Windows para dar suporte aos serviços de segurança.
- **Inicialização Segura com Acesso Direto à Memória**: ativa a VBS com Inicialização Segura e AMD (acesso direto à memória). Proteções de AMD exigem suporte de hardware e são habilitadas somente em dispositivos configurados corretamente.

## <a name="windows-defender-security-center"></a>Central de Segurança do Windows Defender

Compatível com as seguintes edições do Windows 10:

- Início
- Professional
- Negócios
- Enterprise
- Educação
- Celular
- Mobile Enterprise

A Central de Segurança do Windows Defender funciona como um aplicativo ou um processo separado de cada um dos recursos individuais. Ele exibe notificações por meio da Central de Ações. Ele atua como um coletor ou um único lugar para ver o status e executar algumas etapas de configuração para cada um dos recursos. Encontre mais informações nos documentos do [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Aplicativo Central de Segurança do Windows Defender e notificações

Bloqueie o acesso de usuário final às várias áreas do aplicativo da Central de Segurança do Windows Defender. Ocultar uma seção também bloqueia as notificações relacionadas.

- **Proteção contra vírus e ameaças**
- **Integridade e desempenho do dispositivo**
- **Proteção de firewall e rede**
- **Controle de aplicativo e navegador**
- **Opções da família**
- **Notificações das áreas exibidas do aplicativo**: escolha quais notificações serão exibidas aos usuários finais. As notificações não críticas incluem resumos de atividades do Windows Defender Antivírus, incluindo notificações após a conclusão das verificações. Todas as outras notificações são consideradas críticas.

#### <a name="it-contact-information"></a>Informações de contato de TI

Forneça as informações de contato de TI que aparecem no aplicativo da Central de Segurança do Windows Defender e as notificações do aplicativo. Você pode escolher **Exibir no aplicativo e em notificações**, **Exibir somente no aplicativo**, **Exibir somente em notificações** ou **Não exibir**. Insira o **nome da organização de TI** e, pelo menos, uma das seguintes opções de contato:

- **Número de telefone ou ID do Skype do departamento de TI**
- **Endereço de email do departamento de TI**
- **URL do site de suporte de TI**

## <a name="local-device-security-options"></a>Opções de segurança de dispositivo local

Compatível com as seguintes edições do Windows 10:
 
- Início
- Professional
- Negócios
- Enterprise
- Educação

Use estas opções para definir as configurações de segurança locais em dispositivos Windows 10.

### <a name="accounts"></a>Contas

- **Adicionar novas contas da Microsoft**: defina essa opção como **Bloquear** para impedir que os usuários adicionem novas contas da Microsoft ao dispositivo. Quando definido como **Não configurado** (padrão), os usuários podem usar contas da Microsoft no dispositivo.
- **Fazer logon remoto sem senha**: a opção **Habilitar** permite a conexão de contas locais com senhas em branco usando o teclado do dispositivo. **Não configurado** (padrão) permite a conexão de contas locais com senhas em branco de locais que não sejam o dispositivo físico.

#### <a name="admin"></a>Administrador

- **Conta de administrador local**: defina essa opção como **Habilitado** para permitir a conta de administrador local. Defina essa opção como **Não configurado** (padrão) para desabilitar a conta de administrador local.
- **Renomear a conta do administrador**: defina um nome de conta diferente a ser associado ao SID (identificador de segurança) para a conta de Administrador.

#### <a name="guest"></a>Convidado

- **Conta Convidado**: defina essa opção como **Habilitado** para permitir a conta Convidado local. Defina essa opção como **Não configurado** (padrão) para desabilitar a conta Convidado local.
- **Renomear a conta de convidado**: defina um nome de conta diferente a ser associado ao SID (identificador de segurança) para a conta de Convidado.

### <a name="devices"></a>Dispositivos

- **Desencaixar dispositivo sem logon**: defina essa opção como **Bloquear** para que os usuários possam pressionar um botão Ejetar físico do dispositivo portátil encaixado para desencaixar o dispositivo com segurança. **Não configurado** (padrão) exige que o usuário entre no dispositivo e receba permissão para desencaixar o dispositivo.
- **Instalar drivers de impressora para impressoras compartilhadas**: quando **Habilitado**, qualquer usuário pode instalar um driver de impressora como parte da conexão a uma impressora compartilhada. Quando essa opção é **Não configurado** (padrão), somente os Administradores podem instalar um driver de impressora como parte da conexão a uma impressora compartilhada.
- **Restringir o acesso de CD-ROM para o usuário ativo local**: quando **Habilitado**, somente o usuário interativamente conectado pode usar a mídia de CD-ROM. Se essa política está habilitada e ninguém está conectado interativamente, o CD-ROM é acessado pela rede. Quando essa opção é **Não configurado** (padrão), qualquer pessoa tem acesso ao CD-ROM.
- **Formatar e ejetar a mídia removível**: defina quem tem permissão para formatar e ejetar mídia NTFS removível:
  - **Não configurado**
  - **Administradores**
  - **Administradores e Usuários Avançados**
  - **Administradores e Usuários Interativos**

### <a name="interactive-logon"></a>Logon interativo

- **Minutos de inatividade da tela de bloqueio até a proteção de tela ser ativada**: insira o máximo de minutos de inatividade na tela de logon da área de trabalho interativa até que a proteção de tela seja executada.
- **Exigir CTRL+ALT+DEL para fazer logon**: defina essa opção como **Habilitar** para que não seja necessário pressionar CTRL+ALT+DEL para os usuários se conectarem. Defina essa opção como **Não configurado** (padrão) para exigir que os usuários pressionem CTRL+ALT+DEL antes de fazer logon no Windows.
- **Comportamento de remoção de cartão inteligente**: determina o que acontece quando o cartão inteligente para um usuário conectado é removido do leitor de cartão inteligente. Suas opções:

  - **Bloquear Estação de Trabalho**: a estação de trabalho é bloqueada quando o cartão inteligente é removido. Essa opção permite que os usuários deixem a área, levem o cartão inteligente com eles e ainda mantenham uma sessão protegida.
  - **Forçar o Logoff**: é feito o logoff do usuário automaticamente quando o cartão inteligente é removido.
  - **Desconectar em caso de uma sessão de Serviços de Área de Trabalho Remota**: a remoção do cartão inteligente desconecta a sessão sem fazer logoff do usuário. Essa opção permite que o usuário insira o cartão inteligente e retome a sessão mais tarde, ou em outro computador equipado com o leitor de cartão inteligente, sem precisar entrar novamente. Se a sessão for local, essa política funcionará de modo idêntico a Bloquear a Estação de Trabalho.

    [Opções de LocalPoliciesSecurity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior) fornecem mais detalhes.

#### <a name="display"></a>Vídeo

- **Informações do usuário na tela de bloqueio**: configure as informações do usuário exibidas quando a sessão está bloqueada. Se não configurado, o nome de exibição do usuário, o domínio e o nome de usuário serão mostrados.
  - **Não configurado**
  - **Nome de exibição do usuário, domínio e nome de usuário**
  - **Somente nome de exibição do usuário**
  - **Não exibir informações do usuário**
- **Ocultar o último usuário conectado**: a opção **Habilitar** oculta o nome de usuário. **Não configurado** (padrão) mostra o nome de usuário.
- **Ocultar o nome de usuário após a entrada**: a opção **Habilitar** oculta o nome de usuário. **Não configurado** (padrão) mostra o nome de usuário.
- **Título da mensagem de logon**: defina o título da mensagem para os usuários que estão se conectando.
- **Texto da mensagem de logon**: defina o texto da mensagem para os usuários que estão se conectando.

### <a name="network-access-and-security"></a>Acesso e segurança de rede

- **Acesso anônimo a Compartilhamentos e Pipes Nomeados**: **Não configurado** (padrão) restringe o acesso anônimo a configurações de compartilhamento e Pipe Nomeado. Aplica-se às configurações que podem ser acessadas anonimamente.
- **Enumeração anônima de contas SAM**: **Permitir** a usuários anônimos enumerar as contas SAM. O Windows permite que usuários anônimos enumerem os nomes de contas de domínio e compartilhamentos de rede.
- **Enumeração anônima de contas e compartilhamentos SAM**: **Não configurado** (padrão) significa que os usuários anônimos podem enumerar os nomes de contas de domínio e compartilhamentos de rede. Para impedir a enumeração anônima de contas e compartilhamentos SAM, defina como **Bloquear**.
- **Valor de hash do LAN Manager armazenado na alteração de senha**: na próxima alteração de senha, escolha **Permitir** ao LM (LAN Manager) armazenar o valor de hash para a nova senha. Quando essa opção está definida como **Não configurado** (padrão), o valor de hash não é armazenado.
- **Solicitações de autenticação PKU2U**: **Bloquear** solicitações de autenticação PKU2U para este dispositivo para usar identidades online. **Não configurado** (padrão) permite essas solicitações.
- **Restringir conexões RPC remotas ao SAM**: **Permitir** a cadeia de caracteres da Linguagem de Definição do Descritor de Segurança padrão para proibir que usuários e grupos façam chamadas remotas para o SAM. **Não configurado** (padrão) a cadeia de caracteres de Linguagem de Definição do Descritor de Segurança padrão para permitir que os usuários e grupos façam chamadas remotas para o SAM.
  - **Descritor de segurança**

### <a name="recovery-console-and-shutdown"></a>Console de recuperação e desligamento

- **Limpar arquivo de paginação de memória virtual ao desligar**: defina essa opção como **Habilitar** para limpar o arquivo de paginação de memória virtual quando o dispositivo for desligado. A opção **Não configurado** não limpa a memória virtual.
- **Desligar sem fazer logon**: a opção **Bloquear** oculta a opção de desligamento na tela de logon do Windows. Os usuários precisam entrar no dispositivo e, em seguida, desligá-lo. A opção **Não configurado** (padrão) permite que os usuários desliguem o dispositivo na tela de logon do Windows.

### <a name="user-account-control"></a>Controle de conta de usuário

- **Integridade de UIA sem local seguro**: quando essa opção está definida como **Habilitar**, os aplicativos em um local seguro no sistema de arquivos são executados somente com a integridade de UIAccess. A opção **Não configurado** (padrão) permite que os aplicativos sejam executados com a integridade de UIAccess, mesmo se eles não estiverem em um local seguro no sistema de arquivos.
- **Virtualizar falhas de gravação de arquivo e do Registro em locais por usuário**: quando essa opção está definida como **Bloquear**, as falhas de gravação do aplicativo são redirecionadas em tempo de execução para os locais definidos pelo usuário do sistema de arquivos e do Registro. Quando essa opção está definida como **Não configurado** (padrão), ocorre uma falha dos aplicativos que gravam dados em locais protegidos.
- **Somente elevar arquivos executáveis assinados e validados**: defina essa opção como **Habilitado** para impor a validação de caminho de certificação de PKI a determinado arquivo executável antes de permitir sua execução. Defina essa opção como **Não configurado** (padrão) para não impor a validação de caminho de certificação de PKI antes da execução de um arquivo executável.

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
- **Encaminhar solicitações de elevação para a área de trabalho interativa do usuário**: selecione **Habilitar** para que todas as solicitações de elevação sejam encaminhadas para a área de trabalho do usuário interativo, não para a área de trabalho protegida. As configurações de política de comportamento de solicitação para administradores e usuários padrão são usadas. A opção **Não configurado** (padrão) força todas as solicitações de elevação a serem encaminhadas para a área de trabalho protegida, independentemente das configurações de política de comportamento de prompts para administradores e usuários padrão.
- **Prompt com privilégios elevados para instalações de aplicativo**: quando essa opção está definida como **Bloquear**, os pacotes de instalação de aplicativo não são detectados nem solicitados para elevação. Quando essa opção está definida como **Não configurado** (padrão), o usuário é solicitado a fornecer um nome de usuário administrativo e uma senha quando um pacote de instalação de aplicativo exige privilégios elevados.
- **Solicitação de elevação de UIA sem área de trabalho protegida**: selecione **Habilitar** para permitir que aplicativos de UIAccess solicitem a elevação sem o uso da área de trabalho protegida. Quando essa opção está definida como **Não configurado** (padrão), as solicitações de elevação usam uma área de trabalho protegida.

#### <a name="admin-approval-mode-settings"></a>Configurações do Modo de Aprovação de Administrador

- **Modo de Aprovação de Administrador para Administrador Interno**: a opção **Habilitado** permite que a conta de administrador interno use o Modo de Aprovação de Administrador. Qualquer operação que exija a elevação de privilégio solicita que o usuário aprove a operação. A opção **Não configurado** (padrão) executa todos os aplicativos com privilégios completos de administrador.
- **Executar todos os administradores no Modo de Aprovação de Administrador**: defina essa opção como **Bloquear** para desabilitar o Modo de Aprovação de Administrador e todas as configurações de política UAC relacionadas. A opção **Não configurado** (padrão) habilita o Modo de Aprovação de Administrador.

### <a name="microsoft-network-client"></a>Cliente da Rede Microsoft

- **Assinar a comunicação digitalmente (se o servidor concordar)**: determina se o cliente SMB negocia a assinatura do pacote SMB. Quando essa opção está definida como **Não configurado** ou habilitado (padrão), o cliente de rede da Microsoft solicita que o servidor execute a assinatura do pacote SMB após a configuração da sessão. Se a assinatura de pacote estiver habilitada no servidor, a assinatura de pacote será negociada. Se essa opção está definida como **Desabilitar**, o cliente SMB nunca negocia a assinatura do pacote SMB.
- **Enviar senha não criptografada para servidores SMB de terceiros**: quando essa opção está definida como **Habilitar**, o redirecionador do protocolo SMB pode enviar senhas em texto não criptografado para servidores SMB não Microsoft que não dão suporte à criptografia de senha durante a autenticação. Quando essa opção está definida como **Não configurado** (padrão), as senhas são criptografadas.

### <a name="microsoft-network-server"></a>Microsoft Network Server

- **Assinar comunicações digitalmente (se o cliente concordar)**: determina se o servidor SMB negocia a assinatura de pacote SMB com clientes que a solicitam. Quando essa opção está definida como **Habilitar**, o servidor de rede da Microsoft negocia a assinatura do pacote SMB, conforme solicitado pelo cliente. Ou seja, se a assinatura de pacote estiver habilitada no cliente, a assinatura de pacote será negociada. Quando **Não configurada** ou desabilitada (padrão), o cliente SMB nunca negocia a assinatura de pacote SMB.
- **Assinar comunicações digitalmente (sempre)**: determina se a assinatura de pacote é exigida pelo componente do servidor SMB. Quando essa opção está definida como **Habilitar**, o servidor de rede da Microsoft não se comunica com um cliente de rede da Microsoft, a menos que o cliente concorde em executar a assinatura do pacote SMB. Quando essa opção está definida como **Não configurado** ou desabilitado (padrão), a assinatura do pacote SMB é negociada entre o cliente e o servidor.

## <a name="next-steps"></a>Próximas etapas

Para atribuir esse perfil a grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
