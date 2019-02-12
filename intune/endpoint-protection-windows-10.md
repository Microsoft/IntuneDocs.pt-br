---
title: Configurações de proteção para dispositivos Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Em dispositivos Windows 10, use ou defina as configurações de proteção de ponto de extremidade para habilitar inclusões do recurso Windows Defender, Application Guard, Firewall, SmartScreen, criptografia e bitLocker, Exploit Guard, Controle de Aplicativos, Central de Segurança e segurança em dispositivos locais no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/23/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5f87c2fa5fcb7e76fa8d398018e87ec0b15c05e9
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55843384"
---
# <a name="windows-10-and-later-settings-to-protect-devices-using-intune"></a>Configurações do Windows 10 (e posterior) para proteger dispositivos usando o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Microsoft Intune inclui muitas configurações para ajudar a proteger seus dispositivos. Este artigo descreve todas as configurações que você pode habilitar e definir em dispositivos Windows 10 e mais recente. Essas configurações são criadas em um perfil de configuração do Endpoint Protection no Intune para controle da segurança, incluindo o BitLocker e o Windows Defender.

Para configurar o Windows Defender Antivírus, confira [Restrições de dispositivo do Windows 10](device-restrictions-windows-10.md#windows-defender-antivirus).

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo do Endpoint Protection](endpoint-protection-configure.md).

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Compatível com as seguintes edições do Windows 10:

- Enterprise
- Professional

Ao usar o Microsoft Edge, o Windows Defender Application Guard protege seu ambiente contra sites que não são confiáveis para sua organização. Quando os usuários visitam sites que não estão listados no limite de rede isolada, os sites são abertos em uma sessão de navegação virtual do Hyper-V. Os sites confiáveis são definidos por um limite de rede, que são configurados em Configuração do Dispositivo.

O Application Guard só está disponível para dispositivos Windows 10 (64 bits). Usar esse perfil instala um componente do Win32 para ativar o Application Guard.

- **Application Guard**: Escolha **Habilitar** para ativar esse recurso, que abre sites não aprovados em um contêiner de navegação virtualizado do Hyper-V. **Não configurado** (padrão) significa que qualquer site (aprovado e não aprovado) é aberto no dispositivo.
- **Comportamento da área de transferência**: Escolha quais ações de copiar/colar são permitidas entre o computador local e o navegador virtual do Application Guard.
- **Conteúdo externo em sites empresariais**: Escolha **Bloquear** para impedir o carregamento do conteúdo de sites não aprovados. **Não configurado** (padrão) significa que sites não empresariais podem ser abertos no dispositivo.
- **Imprimir por meio do navegador virtual**: Escolha **Permitir** para que impressoras de rede, locais, PDF e XPS possam imprimir o conteúdo por meio do navegador virtual. **Não configurado** (padrão) desabilita todos os recursos de impressão.
- **Coletar logs**: Escolha **Permitir** para coletar logs de eventos que ocorrem em uma sessão de navegação do Application Guard. **Não configurado** (padrão) não coleta logs na sessão de navegação.
- **Manter os dados do navegador gerados pelo usuário**: A opção **Permitir** salva os dados do usuário (como senhas, favoritos e cookies) criados durante uma sessão de navegação virtual do Application Guard. **Não configurado** (padrão) descarta os dados e os arquivos baixados pelo usuário quando o dispositivo é reiniciado, ou quando um usuário sai do serviço.
- **Aceleração gráfica**: Escolha **Habilitar** para carregar mais rapidamente sites e vídeos com uso intenso de elementos gráficos obtendo acesso a uma unidade de processamento gráfico virtual. **Não configurado** (padrão) usa a CPU do dispositivo para os elementos gráficos; ele não usa a unidade de processamento de elementos gráficos virtuais.
- **Baixar arquivos no sistema de arquivos host**: Escolha **Habilitar** para permitir que os usuários baixem arquivos do navegador virtualizado no sistema operacional do host. **Não configurado** (padrão) mantém os arquivos localmente no dispositivo e não baixa arquivos no sistema de arquivos de host.

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

- **Protocolo FTP**: Escolha **Bloquear** para desabilitar o FTP com estado. Quando essa opção é **Não configurado** (padrão), o firewall realiza a filtragem do FTP com estado para permitir conexões secundárias.
- **Tempo ocioso da associação de segurança antes da exclusão**: As associações de segurança são excluídas quando não é detectado nenhum tráfego de rede por *n* segundos. Insira um tempo ocioso em segundos.
- **Codificação de chave pré-compartilhada**: Escolha **Habilitar** para usar a codificação de chave pré-compartilhada usando UTF-8. **Não configurado** (padrão) usa o valor do repositório local.
- **Isenções do IPsec**: Configure um tráfego específico a ser isento do IPsec, incluindo:
  - **Códigos de tipo ICMP do IPv6 de descoberta de vizinho**
  - **ICMP**
  - **Códigos de tipo ICMP do IPv6 de descoberta de roteador**
  - **Tráfego de rede DHCP do IPv4 e IPv6**
- **Verificação da lista de certificados revogados**: Escolha como o dispositivo verifica a lista de certificados revogados. As opções incluem **Desabilitar verificação da CRL**, **Falhar verificação da CRL somente em certificados revogados** e **Falhar verificação da CRL em qualquer erro encontrado**.
- **Encontrar uma correspondência oportuna de conjunto de autenticação por módulo de chave**: Escolha **Habilitar** para forçar os módulos de chave a ignorar somente os conjuntos de autenticação aos quais eles não dão suporte. Quando essa opção é **Não configurado**, os módulos para chave DEVEM ignorar o conjunto completo de autenticação caso eles não deem suporte a todos os pacotes de autenticação especificados no conjunto.
- **Enfileiramento de pacotes**: Informe como o dimensionamento de software no lado do recebimento é habilitado para o recebimento criptografado e o encaminhamento de texto não criptografado para o cenário de gateway de túnel IPsec. Essa configuração confirma que a ordem de pacote é preservada.

### <a name="network-settings"></a>Configurações de rede

Essas configurações aplicam-se a tipos de rede específicos, incluindo **Rede de domínio (local de trabalho)**, **Rede privada (detectável)** e **Rede pública (não detectável)**.

#### <a name="general-settings"></a>Configurações gerais

- **Windows Defender Firewall**: Escolha **Habilitar** para ativar o firewall e a segurança avançada. **Não configurado** (padrão) permite todo o tráfego de rede, independentemente de outras configurações de política.
- **Modo furtivo**: Escolha **Bloquear** para impedir a operação do firewall em modo furtivo. O bloqueio do modo furtivo permite bloquear também a **Isenção de pacote protegido por IPsec**. **Não configurado** (padrão) opera o firewall no modo furtivo, o que ajuda a prevenir respostas a solicitações de investigação.
- **Blindado**: A opção **Bloquear** desliga esse recurso. **Não configurado** (padrão) habilita essa configuração. Quando essa configuração e o Windows Defender Firewall estão ativados, todo o tráfego de entrada é bloqueado, independentemente de outras configurações de política.
- **Respostas unicast para difusões multicast**: Quando essa opção é definida como **Bloquear**, ela desabilita as respostas unicast para difusões multicast. Normalmente, você não deseja receber respostas unicast para mensagens de difusão ou multicast. Essas respostas podem indicar um ataque DoS (negação de serviço) ou um invasor tentando investigar um computador ativo conhecido. **Não configurado** (padrão) habilita essa configuração.
- **Notificações de entrada**: Quando essa opção é definida como **Bloquear**, ela oculta as notificações para os usuários quando um aplicativo é impedido de escutar em uma porta. **Não configurado** (padrão) habilita essa configuração e pode mostrar uma notificação para os usuários quando um aplicativo é impedido de escutar em uma porta.
- **Ação padrão para conexões de entrada**: Quando essa opção é definida como **Bloquear**, a ação de firewall padrão não é executada em conexões de entrada. Quando essa opção está definida como **Não configurado** (padrão), a ação de firewall padrão é executada em conexões de entrada.

#### <a name="rule-merging"></a>Mesclagem de regra

- **Regras do Windows Defender Firewall de aplicativo autorizado no repositório local**: Escolha **Habilitar** para aplicar regras de firewall no repositório local para que elas sejam reconhecidas e impostas. Quando essa opção está definida como **Não configurado** (padrão), as regras de firewall de aplicativo autorizado no repositório local são ignoradas e não são impostas.
- **Regras do Windows Defender Firewall de porta global no repositório local**: Escolha **Habilitar** para aplicar regras de firewall de porta global no repositório local para que elas sejam reconhecidas e impostas. Quando essa opção está definida como **Não configurado** (padrão), as regras de firewall de porta global no repositório local são ignoradas e não são impostas.
- **Regras do Windows Defender Firewall no repositório local**: Escolha **Habilitar** para aplicar regras de firewall no repositório local para que elas sejam reconhecidas e impostas. Quando essa opção está definida como **Não configurado** (padrão), as regras de firewall no repositório local são ignoradas e não são impostas.
- **Regras do IPsec no repositório local**: Escolha **Habilitar** para aplicar regras de segurança da conexão no repositório local, independentemente das versões do esquema ou da regra de segurança da conexão. Quando essa opção está definida como **Não configurado** (padrão), as regras de segurança da conexão no armazenamento local são ignoradas e não são impostas, independentemente das versões de regra de segurança da conexão ou do esquema.

## <a name="windows-defender-smartscreen-settings"></a>Configurações do Windows Defender SmartScreen

Compatível com as seguintes edições do Windows 10 com o Microsoft Edge instalado:
- Início
- Professional
- Negócios
- Enterprise
- Educação
- Celular
- Mobile Enterprise

**Configurações**:

- **SmartScreen para aplicativos e arquivos**: **Habilite** o Windows SmartScreen para execução de arquivos e aplicativos em execução. O SmartScreen é um componente baseado em nuvem para anti-phishing e antimalware. A opção **Não configurado** (padrão) desabilita o SmartScreen.
- **Execução de arquivos não verificados**: Escolha **Bloquear** para impedir que os usuários finais executem arquivos que não foram verificados pelo Windows SmartScreen. A opção **Não configurado** (padrão) desabilita esse recurso e permite aos usuários finais executar arquivos que ainda não foram verificados.

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

- **Criptografar dispositivos**: Escolha **Exigir** para solicitar aos usuários que habilitem a criptografia de dispositivo. Dependendo da edição do Windows e a configuração do sistema, os usuários podem ser solicitados a:  
  - Confirmar que a criptografia de outro provedor não está habilitada
  - Desligar a Criptografia de Unidade de Disco BitLocker e, em seguida, ativar o BitLocker novamente
    
    Se a criptografia do Windows for ativada enquanto outro método de criptografia está ativo, o dispositivo pode se tornar instável. 
- **Criptografar cartão de armazenamento (somente dispositivos móveis)**: Escolha **Exigir** para criptografar os cartões de armazenamento removíveis usados pelo dispositivo. A opção **Não configurado** (padrão) não exige a criptografia do cartão de memória e não solicita ao usuário para ativá-la. Essa configuração só se aplica a dispositivos Windows 10 Mobile.

### <a name="bitlocker-base-settings"></a>Configurações base do BitLocker

Compatível com as seguintes edições do Windows 10:

- Enterprise
- Educação
- Celular
- Mobile Enterprise
- Professional

As configurações básicas são as configurações universais do BitLocker para todos os tipos de unidades de dados. Essas configurações gerenciam quais tarefas de criptografia de unidade ou opções de configuração o usuário final pode modificar em todos os tipos de unidades de dados.

- **Aviso para outras criptografias de disco**: Selecione **Bloquear** para desabilitar o prompt de aviso se outro serviço de criptografia de disco estiver no dispositivo. A opção **Não configurado** (padrão) permite que o aviso seja mostrado.
    - **Permitir que usuários padrão habilitem a criptografia durante o ingresso no Azure AD**: Quando você escolhe **Permitir**, usuários padrão/não administradores podem habilitar a criptografia BitLocker após a entrada do usuário. Essa configuração só se aplica a dispositivos do Azure Active Directory Ingressados (Azure ADJ). **Não configurado** só permite que os Administradores habilitem a criptografia do BitLocker no dispositivo.
      
      Essa configuração só se aplica a dispositivos do Azure Active Directory Ingressados (Azure ADJ). Ela também exige que a configuração **Aviso para outra criptografia de disco** seja definida como **Bloquear**.
- **Configurar métodos de criptografia**: **Habilite** essa configuração para definir algoritmos de criptografia para o sistema operacional, os dados e as unidades removíveis. Quando essa opção está definida como **Não configurado** (padrão), o BitLocker usa o XTS-AES de 128 bits como o método de criptografia padrão ou usa o método de criptografia especificado por qualquer script de instalação.
  - **Criptografia para unidades do sistema operacional**: Escolha o método de criptografia para unidades do sistema operacional. Recomendamos que você use o algoritmo XTS-AES.
  - **Criptografia para unidades de dados fixas**: Escolha o método de criptografia para unidades de dados fixas (internas). Recomendamos que você use o algoritmo XTS-AES.
  - **Criptografia para unidades de dados removíveis**: Escolha o método de criptografia para unidades de dados removíveis. Se a unidade removível é usada com dispositivos que não executam o Windows 10, recomendamos o uso do algoritmo AES-CBC.

### <a name="bitlocker-os-drive-settings"></a>Configurações de unidade do sistema operacional do BitLocker
Compatível com as seguintes edições do Windows 10:

- Enterprise
- Educação
- Celular
- Mobile Enterprise
- Professional

Essas configurações aplicam-se especificamente às unidades de dados do sistema operacional.

- **Autenticação adicional na inicialização**: Selecione **Exigir** para configurar os requisitos de autenticação da inicialização do computador, incluindo o uso do TPM (Trusted Platform Module). Selecione **Não configurado** (padrão) para configurar somente as opções básicas em dispositivos com um TPM.
  - **BitLocker com chip do TPM não compatível**: **Bloqueie** (desabilite) o uso do BitLocker quando um dispositivo não tiver um chip do TPM compatível. Quando essa opção está definida como **Não configurado**, os usuários podem usar o BitLocker sem um chip TPM compatível. O BitLocker pode exigir uma senha ou uma chave de inicialização.
  - **Inicialização do TPM compatível**: Escolha permitir, não permitir ou exigir o chip do TPM.
  - **PIN de inicialização do TPM compatível**: Escolha permitir, não permitir ou exigir o uso de um PIN de inicialização com o chip do TPM. A habilitação de um PIN de inicialização exige a interação do usuário final. 
  - **Chave de inicialização do TPM compatível**: Escolha permitir, não permitir ou exigir o uso de uma chave de inicialização com o chip do TPM. A habilitação de uma chave de inicialização exige a interação do usuário final. 
  - **PIN e chave de inicialização do TPM compatível**: Escolha permitir, não permitir ou exigir o uso de um PIN e uma chave de inicialização com o chip do TPM. A habilitação de uma chave de inicialização e um PIN exige a interação do usuário final.
- **Tamanho Mínimo do PIN**: **Habilite** essa configuração para definir um tamanho mínimo para o PIN de inicialização do TPM. Quando essa opção está definida como **Não configurado** (padrão), os usuários podem configurar um PIN de inicialização de qualquer tamanho entre 6 e 20 dígitos.
  - **Número mínimo de caracteres**: Insira o número de caracteres necessário para o PIN de inicialização de **4**-**20**.
- **Recuperação de unidade do sistema operacional**: **Habilite** essa configuração para controlar como as unidades do sistema operacional protegidas pelo BitLocker são recuperadas quando as informações de inicialização necessárias não estão disponíveis. Quando essa opção está definida como **Não configurado** (padrão), as opções de recuperação padrão são compatíveis com a recuperação do BitLocker. Por padrão, um DRA é permitido, as opções de recuperação são escolhidas pelo usuário, incluindo a senha e a chave de recuperação, e as informações de recuperação não são copiadas em backup no AD DS.
  - **Agente de recuperação de dados baseado em certificado**: Quando essa opção é definida como **Bloquear**, você não pode usar o agente de recuperação de dados com as unidades do sistema operacional protegidas pelo BitLocker. Defina essa opção como **Não configurado** (padrão) para habilitar essa configuração, o que permite o uso dos agentes de recuperação de dados com as unidades do sistema operacional protegidas pelo BitLocker.
  - **Criação de senha de recuperação pelo usuário**: Escolha se é permitido, obrigatório ou não permitido que os usuários gerem uma senha de recuperação de 48 dígitos.
  - **Criação de chave de recuperação pelo usuário**: Escolha se é permitido, obrigatório ou não permitido que os usuários gerem uma chave de recuperação de 256 bits.
  - **Opções de recuperação no assistente de instalação do BitLocker**: Defina essa opção como **Bloquear** para que os usuários não possam ver nem alterar as opções de recuperação. Quando essa opção está definida como **Não configurado** (padrão), os usuários podem ver e alterar as opções de recuperação ao ativarem o BitLocker.
  - **Salvar as informações de recuperação do BitLocker no AD DS**: Escolha **Habilitar** para armazenar as informações de recuperação do BitLocker no AAD (Azure Active Directory). Quando a opção é definida como **Não configurado** (padrão), as informações de recuperação não são armazenadas no AAD.
  - **Informações de recuperação do BitLocker armazenadas no AD DS**: Configure quais partes das informações de recuperação do BitLocker são armazenadas no Azure AD. Escolha:
    - **Fazer backup de pacotes de chaves e senhas de recuperação**
    - **Fazer backup somente de senhas de recuperação**
  - **Armazenar as informações de recuperação no AD DS antes de habilitar o BitLocker**: Escolha **Exigir** essa configuração para impedir os usuários de ativar o BitLocker, a menos que as informações de recuperação do BitLocker sejam armazenadas com êxito no Azure AD (Active Directory). A opção **Não configurado** (padrão) permite que os usuários ativem o BitLocker, mesmo se as informações de recuperação não sejam armazenadas com êxito no Azure AD.
- **URL e mensagem de recuperação pré-inicialização**: **Habilite** essa configuração para definir a mensagem e a URL exibidas na tela de recuperação de chave pré-inicialização. **Não configurado** (padrão) desabilita esse recurso.
  - **Mensagem de recuperação pré-inicialização**: Configure como a mensagem de recuperação pré-inicialização é exibida para os usuários. Escolha:
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
- Professional

**Configurações**:

- **Acesso de gravação a unidades de dados fixas não protegidas pelo BitLocker**: Defina essa opção como **Bloquear** para fornecer acesso somente leitura às unidades de dados que não são protegidas pelo BitLocker. Quando essa opção é definida como **Não configurado** (padrão), há o acesso de leitura e gravação nas unidades de dados que não são protegidas pelo BitLocker.
- **Recuperação de unidade fixa**: **Habilite** essa configuração para controlar como as unidades fixas protegidas pelo BitLocker são recuperadas quando as informações de inicialização necessárias não estão disponíveis. **Não configurado** (padrão) desabilita esse recurso.
  - **Agente de recuperação de dados**: **Bloqueie** o uso do agente de recuperação de dados com o Editor de Política das unidades fixas protegidas pelo BitLocker. A opção **Não configurado** (padrão) habilita o uso de agentes de recuperação de dados com unidades fixas protegidas pelo BitLocker.
  - **Criação de senha de recuperação pelo usuário**: Configure se é permitido, obrigatório ou não permitido que os usuários gerem uma senha de recuperação de 48 dígitos.  
  - **Criação de chave de recuperação pelo usuário**: Configure se é permitido, obrigatório ou não permitido que os usuários gerem uma chave de recuperação de 256 bits.
  - **Opções de recuperação no assistente de instalação do BitLocker**: Defina essa opção como **Bloquear** para que os usuários não possam ver nem alterar as opções de recuperação. Quando essa opção está definida como **Não configurado** (padrão), os usuários podem ver e alterar as opções de recuperação ao ativarem o BitLocker.
  - **Salvar as informações de recuperação do BitLocker no AD DS**: Escolha **Habilitar** para armazenar as informações de recuperação do BitLocker no Azure AD (Active Directory). Quando essa opção é definida como **Não configurado** (padrão), as informações de recuperação não são armazenadas no Azure AD.
  - **Informações de recuperação do BitLocker no AD DS**: Configure quais partes das informações de recuperação do BitLocker são armazenadas no Azure AD. Suas opções:
    - **Fazer backup de pacotes de chaves e senhas de recuperação**
    - **Fazer backup somente de senhas de recuperação**
  - **Armazenar as informações de recuperação no AD DS antes de habilitar o BitLocker**: Escolha **Exigir** essa configuração para impedir os usuários de ativar o BitLocker, a menos que as informações de recuperação do BitLocker sejam armazenadas com êxito no Azure AD. A opção **Não configurado** (padrão) permite que os usuários ativem o BitLocker, mesmo se as informações de recuperação não sejam armazenadas com êxito no Azure AD.

### <a name="bitlocker-removable-data-drive-settings"></a>Configurações de unidade de dados removíveis do BitLocker

Compatível com as seguintes edições do Windows 10:

- Enterprise
- Educação
- Celular
- Mobile Enterprise
- Professional

**Configurações**:

- **Acesso de gravação a unidades de dados removíveis não protegidas pelo BitLocker**: Defina essa opção como **Bloquear** para fornecer acesso somente leitura às unidades de dados que não são protegidas pelo BitLocker. Quando essa opção é definida como **Não configurado** (padrão), há o acesso de leitura e gravação nas unidades de dados que não são protegidas pelo BitLocker.
  - **Acesso de gravação a dispositivos configurados em outra organização**: A opção **Bloquear** permite o acesso de gravação a dispositivos configurados em outra organização. A opção **Não configurado** (padrão) nega o acesso de gravação.

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

- **Arquivos e pastas a serem excluídos das regras de redução da superfície de ataque**: Importe/adicione uma lista de locais a serem excluídos das regras configuradas.

### <a name="controlled-folder-access"></a>Acesso controlado à pasta

Ajude a proteger dados valiosos contra ameaças e aplicativos mal-intencionados, como ransomware.

- **Proteção de pasta**: Proteja arquivos e pastas contra alterações indesejadas realizadas por aplicativos mal-intencionados. Você pode importar uma **Lista de aplicativos com acesso a pastas protegidas** ou adicioná-los manualmente. Você também pode adicionar uma **Lista de pastas adicionais que precisam ser protegidas** com um upload ou adicioná-las manualmente.

### <a name="network-filtering"></a>Filtragem de rede

Bloqueie conexões de saída de qualquer aplicativo para IPs/domínios de reputação ruim.

### <a name="exploit-protection"></a>Proteção contra explorações

Para usar o Exploit Protection, crie um arquivo XML que inclua as configurações desejadas de mitigação do sistema e do aplicativo. Há dois métodos:

 1. PowerShell: Use um ou mais dos cmdlets Get-ProcessMitigation, Set-ProcessMitigation e ConvertTo-ProcessMitigationPolicy do PowerShell. Os cmdlets definem configurações de mitigação e exportam uma representação XML deles.

 2. Interface do usuário da Central de Segurança do Windows Defender: Na Central de Segurança do Windows Defender, clique em Controle de aplicativos e navegadores e, em seguida, role a página até a parte inferior da tela resultante para localizar o Exploit Protection. Primeiro, use as guias Configurações do sistema e Configurações do programa para definir as configurações de mitigação. Em seguida, localize o link Exportar configurações na parte inferior da tela para exportar uma representação XML delas.

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

- **Desabilitar**: Desliga o Credential Guard remotamente se ele foi ativado anteriormente com a opção **Habilitado sem bloqueio UEFI**.

- **Habilitar com bloqueio UEFI**: O Credential Guard não pode ser desabilitado remotamente usando uma chave do Registro ou uma Política de Grupo.

    > [!NOTE]
    > Se você usar essa configuração e depois quiser desabilitar o Credential Guard, deverá definir a Política de Grupo como **Desabilitada**. Além disso, limpe fisicamente as informações de configuração de UEFI de cada computador. Enquanto a configuração da UEFI for mantida, o Credential Guard estará habilitado.

- **Habilitar sem bloqueio UEFI**: Permite que o Credential Guard seja desabilitado remotamente usando a Política de Grupo. Os dispositivos que usam essa configuração devem estar executando, Windows 10 versão 1511 e mais recentes.

Quando você habilita o Credential Guard, os seguintes recursos obrigatórios também são habilitados:

- **VBS** (Segurança baseada em virtualização): É ativada durante a próxima reinicialização. A segurança baseada em virtualização usa o Hipervisor do Windows para dar suporte aos serviços de segurança.
- **Inicialização Segura com acesso direto à memória**: Ativa a VBS com as proteções Inicialização Segura e DMA (acesso direto à memória). Proteções de AMD exigem suporte de hardware e são habilitadas somente em dispositivos configurados corretamente.

## <a name="windows-defender-security-center"></a>Central de Segurança do Windows Defender

Compatível com as seguintes edições do Windows 10:

- Início
- Professional
- Negócios
- Enterprise
- Educação
- Celular
- Mobile Enterprise

A Central de Segurança do Windows Defender funciona como um aplicativo ou um processo separado de cada um dos recursos individuais. Ele exibe notificações por meio da Central de Ações. Funciona como um coletor ou um único lugar para ver o status e executar algumas etapas de configuração para cada um dos recursos. Encontre mais informações nos documentos do [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Aplicativo Central de Segurança do Windows Defender e notificações

Bloqueie o acesso de usuário final às várias áreas do aplicativo da Central de Segurança do Windows Defender. Ocultar uma seção também bloqueia as notificações relacionadas.

- **Proteção contra vírus e ameaças**
- **Integridade e desempenho do dispositivo**
- **Proteção de firewall e rede**
- **Controle de aplicativo e navegador**
- **Opções da família**
- **Notificações das áreas exibidas do aplicativo**: Escolha quais notificações serão exibidas aos usuários finais. As notificações não críticas incluem resumos de atividades do Windows Defender Antivírus, incluindo notificações após a conclusão das verificações. Todas as outras notificações são consideradas críticas.

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

- **Adicionar novas contas Microsoft**: Defina essa opção como **Bloquear** para impedir os usuários de adicionar novas contas Microsoft ao dispositivo. Quando definido como **Não configurado** (padrão), os usuários podem usar contas da Microsoft no dispositivo.
- **Logon remoto sem senha**: A opção **Habilitar** permite a conexão de contas locais com senhas em branco usando o teclado do dispositivo. **Não configurado** (padrão) permite a conexão de contas locais com senhas em branco de locais que não sejam o dispositivo físico.

#### <a name="admin"></a>Administrador

- **Conta do administrador local**: Defina essa opção como **Habilitado** para permitir a conta do administrador local. Defina essa opção como **Não configurado** (padrão) para desabilitar a conta de administrador local.
- **Renomear a conta do administrador**: Defina um nome de conta diferente a ser associado ao SID (identificador de segurança) da conta do administrador.

#### <a name="guest"></a>Convidado

- **Conta Convidado**: Defina essa opção como **Habilitado** para permitir a conta Convidado local. Defina essa opção como **Não configurado** (padrão) para desabilitar a conta Convidado local.
- **Renomear a conta Convidado**: Defina um nome de conta diferente a ser associado ao SID (identificador de segurança) da conta Convidado.

### <a name="devices"></a>Dispositivos

- **Desencaixar dispositivo sem logon**: Defina essa opção como **Bloquear** para que os usuários possam pressionar um botão ejetar físico do dispositivo portátil encaixado para desencaixar o dispositivo com segurança. **Não configurado** (padrão) exige que o usuário entre no dispositivo e receba permissão para desencaixar o dispositivo.
- **Instalar drivers de impressora para impressoras compartilhadas**: Quando essa opção é definida como **Habilitado**, qualquer usuário pode instalar um driver de impressora como parte da conexão com uma impressora compartilhada. Quando essa opção é **Não configurado** (padrão), somente os Administradores podem instalar um driver de impressora como parte da conexão a uma impressora compartilhada.
- **Restringir o acesso de CD-ROM ao usuário ativo local**: Quando essa opção é definida como **Habilitado**, somente o usuário conectado interativamente pode usar a mídia de CD-ROM. Se essa política está habilitada e ninguém está conectado interativamente, o CD-ROM é acessado pela rede. Quando essa opção é **Não configurado** (padrão), qualquer pessoa tem acesso ao CD-ROM.
- **Formatar e ejetar a mídia removível**: Defina quem tem permissão para formatar e ejetar a mídia NTFS removível:
  - **Não configurado**
  - **Administradores**
  - **Administradores e Usuários Avançados**
  - **Administradores e Usuários Interativos**

### <a name="interactive-logon"></a>Logon interativo

- **Minutos de inatividade da bloqueio de tela até a proteção de tela ser ativada**: Insira o máximo de minutos de inatividade na tela de entrada da área de trabalho interativa até a proteção de tela ser iniciada.
- **Exigir CTRL+ALT+DEL fazer logon**: Defina essa opção como **Habilitar** para que não seja necessário pressionar CTRL+ALT+DEL para os usuários se conectarem. Defina essa opção como **Não configurado** (padrão) para exigir que os usuários pressionem CTRL+ALT+DEL antes de fazer logon no Windows.
- **Comportamento de remoção do cartão inteligente**: Determina o que acontece quando o cartão inteligente de um usuário conectado é removido do leitor de cartão inteligente. Suas opções:

  - **Bloquear Estação de Trabalho**: A estação de trabalho é bloqueada quando o cartão inteligente é removido. Essa opção permite que os usuários deixem a área, levem o cartão inteligente com eles e ainda mantenham uma sessão protegida.
  - **Forçar o Logoff**: É feito o logoff automático do usuário quando o cartão inteligente é removido.
  - **Desconectar em caso de uma sessão dos Serviços de Área de Trabalho Remota**: A remoção do cartão inteligente desconecta a sessão sem fazer logoff do usuário. Essa opção permite que o usuário insira o cartão inteligente e retome a sessão mais tarde, ou em outro computador equipado com o leitor de cartão inteligente, sem precisar entrar novamente. Se a sessão for local, essa política funcionará de modo idêntico a Bloquear a Estação de Trabalho.

    [Opções de LocalPoliciesSecurity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior) fornecem mais detalhes.

#### <a name="display"></a>Vídeo

- **Informações do usuário na tela de bloqueio**: Configure as informações do usuário exibidas quando a sessão é bloqueada. Se não configurado, o nome de exibição do usuário, o domínio e o nome de usuário serão mostrados.
  - **Não configurado**
  - **Nome de exibição do usuário, domínio e nome de usuário**
  - **Somente nome de exibição do usuário**
  - **Não exibir informações do usuário**
- **Ocultar o último usuário conectado**: A opção **Habilitar** oculta o nome de usuário. **Não configurado** (padrão) mostra o nome de usuário.
- **Ocultar o nome de usuário nas credenciais**: A opção **Habilitar** oculta o nome de usuário. **Não configurado** (padrão) mostra o nome de usuário.
- **Título da mensagem de logon**: Defina o título da mensagem para os usuários que estão se conectando.
- **Texto da mensagem de logon**: Defina o texto da mensagem para os usuários que estão se conectando.

### <a name="network-access-and-security"></a>Acesso e segurança de rede

- **Acesso anônimo a Compartilhamentos e Pipes Nomeados**: A opção **Não configurado** (padrão) restringe o acesso anônimo às configurações de compartilhamento e Pipe Nomeado. Aplica-se às configurações que podem ser acessadas anonimamente.
- **Enumeração anônima de contas do SAM**: **Permita** que usuários anônimos enumerem as contas do SAM. O Windows permite que usuários anônimos enumerem os nomes de contas de domínio e compartilhamentos de rede.
- **Enumeração anônima de compartilhamentos e contas do SAM**: A opção **Não configurado** (padrão) significa que os usuários anônimos podem enumerar os nomes de contas de domínio e compartilhamentos de rede. Para impedir a enumeração anônima de contas e compartilhamentos SAM, defina como **Bloquear**.
- **Valor do hash do LAN Manager armazenado na alteração de senha**: Na próxima alteração de senha, escolha **Permitir** para que o LM (LAN Manager) armazene o valor do hash para a nova senha. Quando essa opção está definida como **Não configurado** (padrão), o valor de hash não é armazenado.
- **Solicitações de autenticação PKU2U**: **Bloqueie** solicitações de autenticação PKU2U para que esse dispositivo use identidades online. **Não configurado** (padrão) permite essas solicitações.
- **Restringir conexões RPC remotas com o SAM**: **Permita** que a cadeia de caracteres da Linguagem de Definição do Descritor de Segurança padrão negue chamadas remotas ao SAM feitas por usuários e grupos. **Não configurado** (padrão) a cadeia de caracteres de Linguagem de Definição do Descritor de Segurança padrão para permitir que os usuários e grupos façam chamadas remotas para o SAM.
  - **Descritor de segurança**

### <a name="recovery-console-and-shutdown"></a>Console de recuperação e desligamento

- **Limpar arquivo de paginação de memória virtual ao desligar**: Defina essa opção como **Habilitar** para limpar o arquivo de paginação de memória virtual quando o dispositivo estiver sendo desligado. A opção **Não configurado** não limpa a memória virtual.
- **Desligar sem fazer logon**: A opção **Bloquear** oculta a opção de desligamento na tela de entrada do Windows. Os usuários precisam entrar no dispositivo e, em seguida, desligá-lo. A opção **Não configurado** (padrão) permite que os usuários desliguem o dispositivo na tela de entrada do Windows.

### <a name="user-account-control"></a>Controle de conta de usuário

- **Integridade de UIA sem localização segura**: Quando essa opção é definida como **Habilitar**, os aplicativos em uma localização segura no sistema de arquivos são executados somente com a integridade de UIAccess. A opção **Não configurado** (padrão) permite que os aplicativos sejam executados com a integridade de UIAccess, mesmo se eles não estiverem em um local seguro no sistema de arquivos.
- **Virtualizar falhas de gravação de arquivos e do Registro para locais por usuário**: Quando essa opção é definida como **Bloquear**, as falhas de gravação de aplicativos são direcionadas em tempo de execução a locais de usuário definidos no sistema de arquivos e no Registro. Quando essa opção está definida como **Não configurado** (padrão), ocorre uma falha dos aplicativos que gravam dados em locais protegidos.
- **Elevar somente arquivos executáveis assinados e validados**: Defina essa opção como **Habilitado** para impor a validação de caminho de certificação de PKI para um arquivo executável antes que ele possa ser executado. Defina essa opção como **Não configurado** (padrão) para não impor a validação de caminho de certificação de PKI antes da execução de um arquivo executável.

#### <a name="uia-elevation-prompt-behavior-settings"></a>Configurações de comportamento da solicitação de elevação de UIA

- **Solicitação de elevação para administradores**: Defina o comportamento da solicitação de elevação de administradores no Modo de Aprovação de Administrador:
  - **Elevar sem solicitar**
  - **Solicitar credenciais na área de trabalho protegida**
  - **Solicitar consentimento na área de trabalho protegida**
  - **Solicitar credenciais**
  - **Solicitar consentimento**
  - **Não configurado**: Solicitar consentimento para binários não Windows
- **Solicitação de elevação para usuários padrão**: Defina o comportamento da solicitação de elevação para usuários padrão:
  - **Negar automaticamente solicitações de elevação**
  - **Solicitar credenciais na área de trabalho protegida**
  - **Não configurado**: Solicitar credenciais
- **Encaminhar solicitações de elevação para a área de trabalho interativa do usuário**: Escolha **Habilitar** para que todas as solicitações de elevação sejam encaminhadas para a área de trabalho do usuário interativo, não para a área de trabalho protegida. As configurações de política de comportamento de solicitação para administradores e usuários padrão são usadas. A opção **Não configurado** (padrão) força todas as solicitações de elevação a serem encaminhadas para a área de trabalho protegida, independentemente das configurações de política de comportamento de prompts para administradores e usuários padrão.
- **Prompt com privilégios elevados para instalações de aplicativo**: Quando essa opção é definida como **Bloquear**, os pacotes de instalação de aplicativo não são detectados nem solicitados para elevação. Quando essa opção é definida como **Não configurado** (padrão) e um pacote de instalação de aplicativo exige privilégios elevados, o usuário deve fornecer um nome de usuário administrativo e uma senha.
- **Solicitação de elevação de UIA sem a área de trabalho protegida**: A opção **Habilitar** permite que aplicativos de UIAccess solicitem elevação sem usar a área de trabalho protegida. Quando essa opção está definida como **Não configurado** (padrão), as solicitações de elevação usam uma área de trabalho protegida.

#### <a name="admin-approval-mode-settings"></a>Configurações do Modo de Aprovação de Administrador

- **Modo de Aprovação de Administrador para conta de administrador interno**: A opção **Habilitado** permite que a conta de administrador interno use o Modo de Aprovação de Administrador. Qualquer operação que exija a elevação de privilégio solicita que o usuário aprove a operação. A opção **Não configurado** (padrão) executa todos os aplicativos com privilégios completos de administrador.
- **Executar todos os administradores no Modo de Aprovação de Administrador**: Defina essa opção como **Bloquear** para desabilitar o Modo de Aprovação de Administrador e todas as configurações de política UAC relacionadas. A opção **Não configurado** (padrão) habilita o Modo de Aprovação de Administrador.

### <a name="microsoft-network-client"></a>Cliente da Rede Microsoft

- **Assinar as comunicações digitalmente (se o servidor concordar)**: Determina se o cliente SMB negocia a assinatura de pacotes SMB. Quando essa opção está definida como **Não configurado** ou habilitado (padrão), o cliente de rede da Microsoft solicita que o servidor execute a assinatura do pacote SMB após a configuração da sessão. Se a assinatura de pacote estiver habilitada no servidor, a assinatura de pacote será negociada. Se essa opção está definida como **Desabilitar**, o cliente SMB nunca negocia a assinatura do pacote SMB.
- **Enviar senha não criptografada para servidores SMB de terceiros**: Quando essa opção é definida como **Habilitar**, o redirecionador do protocolo SMB pode enviar senhas em texto não criptografado para servidores SMB não Microsoft que não dão suporte à criptografia de senha durante a autenticação. Quando essa opção está definida como **Não configurado** (padrão), as senhas são criptografadas.

### <a name="microsoft-network-server"></a>Microsoft Network Server

- **Assinar as comunicações digitalmente (se o cliente concordar)**: Determina se o servidor SMB negocia a assinatura de pacote SMB com clientes que a solicitam. Quando essa opção está definida como **Habilitar**, o servidor de rede da Microsoft negocia a assinatura do pacote SMB, conforme solicitado pelo cliente. Ou seja, se a assinatura de pacote estiver habilitada no cliente, a assinatura de pacote será negociada. Quando **Não configurada** ou desabilitada (padrão), o cliente SMB nunca negocia a assinatura de pacote SMB.
- **Assinar as comunicações digitalmente (sempre)**: Determina se a assinatura de pacote é exigida pelo componente do servidor SMB. Quando essa opção está definida como **Habilitar**, o servidor de rede da Microsoft não se comunica com um cliente de rede da Microsoft, a menos que o cliente concorde em executar a assinatura do pacote SMB. Quando essa opção está definida como **Não configurado** ou desabilitado (padrão), a assinatura do pacote SMB é negociada entre o cliente e o servidor.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Definir configurações de proteções de ponto de extremidade em dispositivos [macOS](endpoint-protection-macos.md).
