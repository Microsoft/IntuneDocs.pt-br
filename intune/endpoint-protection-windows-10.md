---
title: "Configurações do Intune Endpoint Protection para Windows 10"
titlesuffix: Azure portal
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações do Endpoint Protection, como o BitLocker, em dispositivos Windows 10.”"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 01/16/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8393699a06def8f01c9f70561bb1894bb7cba04e
ms.sourcegitcommit: 967a7c23b863123398c40b812e2eb02c921a0afe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2018
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Configurações do Endpoint Protection para o Windows 10 e posterior no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O perfil do Endpoint Protection permite controlar os recursos de segurança em dispositivos Windows 10, como BitLocker e Windows Defender.

Use as informações neste tópico para saber como criar perfis do Endpoint Protection.

> [!Note]
> Essas configurações não têm suporte nas edições Professional e Home do Windows 10.

## <a name="create-an-endpoint-protection-profile"></a>Criar um perfil de Endpoint Protection

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar perfil**.
4. Na folha **Criar perfil**, insira um **Nome** e uma **Descrição** para o perfil de recursos do dispositivo.
5. Na lista suspensa **Plataforma**, escolha **Windows 10 e posterior**.
6. Na lista suspensa de tipos de **Tipo de perfil**, escolha **Endpoint Protection**.
7. Defina as configurações que você deseja. Use os detalhes neste tópico para ajudar a entender o que cada configuração faz. Quando terminar, escolha **OK**.
8. Volte para a folha **Criar perfil** e escolha **Criar**.

O perfil é criado e exibido na folha da lista de perfis.

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

O Application Guard só está disponível para dispositivos Windows 10 (64 bits). Usando este perfil, você instalará um componente do Win32 para ativar o Application Guard.

- **Application Guard** – abra sites não aprovados em um contêiner de navegação virtualizado do Hyper-V.
- **Comportamento da área de transferência** – escolha quais ações de copiar/colar são permitidas entre o computador local e o navegador virtual do Application Guard.
- **Conteúdo externo em sites corporativos** – bloqueie o carregamento do conteúdo de sites não aprovados.
- **Impressão do navegador virtual** – permita que impressoras de PDF, XPS e/ou de rede local imprimam o conteúdo do navegador virtual.
- **Coletar logs** – colete logs de eventos que ocorrem dentro de uma sessão de navegação do Application Guard.
- **Manter dados do navegador gerados pelo usuário** – permita que os dados de usuário (como senhas, favoritos e cookies) que são criados durante uma sessão de navegação virtual do Application Guard sejam salvos.


## <a name="windows-defender-firewall"></a>Windows Defender Firewall

### <a name="global-settings"></a>Configurações globais

Essas configurações são aplicáveis a todos os tipos de rede.

- **Protocolo FTP** – bloqueie FTP com estado.
- **Tempo ocioso da associação de segurança antes da exclusão** – as associações de segurança serão excluídas quando não for detectado nenhum tráfego de rede durante *n* segundos.
- **Codificação de chave pré-compartilhada** – codifique chaves pré-compartilhadas usando UTF-8.
- **Isenções de IPsec** – configure um tráfego específico como isento do IPsec, incluindo **Códigos de tipo ICMP de IPv6 de descoberta de vizinho**, **ICMP**, **Códigos de tipo ICMP de IPv6 de descoberta de roteador** e **Tráfegos de rede DHCP de IPv4 e IPv6**.
- **Verificação da lista de certificados revogados** – defina um valor para indicar como a verificação da lista de certificados revogados será imposta, incluindo **Desabilitar a verificação de CRL**, **Falhar verificação de CRL somente para certificado revogado** e **Falhar verificação de CRL para qualquer erro encontrado**.
- **Corresponder conjunto de autenticação por módulo de chave de forma oportuna** – defina os módulos de chaves para ignorar o conjunto de autenticação inteiro caso não sejam compatíveis com todos os pacotes de autenticação nesse conjunto.
- **Enfileiramento de pacotes** – especifique como o dimensionamento de software no lado do recebimento será habilitado para o recebimento criptografado e o encaminhamento de texto não criptografado para o cenário de gateway de túnel do IPsec. Isso garante que a ordem de pacotes seja preservada.

### <a name="network-settings"></a>Configurações da rede

Essas configurações aplicam-se a tipos de rede específicos, incluindo **Rede de domínio (local de trabalho)**, **Rede privada (detectável)** e **Rede pública (não detectável)**.

#### <a name="general-settings"></a>Configurações gerais

- **Windows Defender Firewall** – habilite essa configuração para bloquear o tráfego de rede.
- **Modo furtivo** – bloqueie a operação do firewall em modo furtivo. Esse bloqueio permite que você bloqueie a **Isenção de pacote protegido por IPsec**.
- **Blindado** – habilitar essa opção e a configuração de firewall bloqueará todo o tráfego de entrada.
- **Respostas unicast para transmissões multicast** – bloqueie respostas unicast para transmissões multicast. Normalmente, não é interessante receber respostas unicast para mensagens multicast ou de transmissão, pois essas respostas podem indicar um ataque de negação de serviço ou um invasor tentando investigar um computador ativo conhecido.
- **Notificações de entrada** – bloqueie a exibição de notificações para os usuários quando a escuta de um aplicativo estiver bloqueada em uma porta.
- **Ação padrão para conexões de entrada** – bloqueie a ação padrão que o firewall executa nas conexões de entrada.

#### <a name="rule-merging"></a>Mesclagem de regra

- **Regras do Windows Defender Firewall de aplicativo autorizados do repositório local** – aplique regras de firewall autorizadas no repositório local para serem reconhecidas e impostas.
- **Regras do Windows Defender Firewall de porta global do repositório local** – aplique regras de firewall de porta globais no repositório local para serem reconhecidas e impostas.
- **Regras do Windows Defender Firewall do repositório local** – aplique regras de firewall globais no repositório local para serem reconhecidas e impostas.
- **Regras de IPsec do repositório local** – aplique regras de segurança de conexão do repositório local, independentemente das versões de regra de segurança do esquema ou da conexão.

## <a name="windows-defender-smartscreen-settings"></a>Configurações do Windows Defender SmartScreen

- **SmartScreen para aplicativos e arquivos** – habilite o Windows SmartScreen para execução de arquivos e aplicativos em execução.
- **Execução de arquivos não verificados** –impeça que o usuário final execute arquivos que não foram verificados pelo Windows SmartScreen.

## <a name="windows-encryption"></a>Criptografia do Windows

### <a name="windows-settings"></a>Configurações do Windows

Essas configurações aplicam-se a todas as versões do Windows 10.

- **Criptografar dispositivos** – se habilitado, é solicitado que os usuários habilitem a criptografia do dispositivo. Além disso, é solicitado que eles confirmem que a criptografia de outro provedor não foi habilitada. Se a criptografia do Windows for ativada enquanto outro método de criptografia está ativo, o dispositivo pode se tornar instável.
- **Criptografar cartão de memória** – habilite essa configuração para criptografar os cartões de memória removíveis usados pelo dispositivo.


### <a name="bitlocker-base-settings"></a>Configurações base do BitLocker

As configurações básicas são as configurações universais do BitLocker para todos os tipos de unidades de dados. As configurações de política de grupo do BitLocker gerenciam quais tarefas de criptografia de unidade ou opções de configuração o usuário final pode modificar em todos os tipos de unidades de dados.

- **Aviso para outra criptografia de disco** – desabilite a mensagem de aviso para outra criptografia de disco nos computadores dos usuários finais.
- **Configurar métodos de criptografia** – Habilite essa configuração para definir os algoritmos de criptografia para o sistema operacional, dados e unidades removíveis.
    - **Criptografia para unidades do sistema operacional** – Escolha o método de criptografia para unidades do sistema operacional. Recomendamos que você use o algoritmo XTS-AES.
    - **Criptografia para unidades de dados fixas** – Escolha o método de criptografia para unidades de dados fixas (internas). Recomendamos que você use o algoritmo XTS-AES.
    - **Criptografia para unidades de dados removíveis** – Escolha o método de criptografia para unidades de dados removíveis. Se a unidade removível for usada com dispositivos que não executam o Windows 10, é recomendável usar o algoritmo AES-CBC.

### <a name="bitlocker-os-drive-settings"></a>Configurações de unidade do sistema operacional do BitLocker

Essas configurações aplicam-se especificamente às unidades de dados do sistema operacional.

- **Autenticação adicional na inicialização** – configure os requisitos da autenticação de inicialização do computador, incluindo o uso do TPM (Trusted Platform Module).
    - **BitLocker com chip do TPM não compatível**
    - **Inicialização do TPM compatível** – configure se o chip do TPM é permitido, não permitido ou necessário.
    - **PIN de inicialização do TPM compatível** – configure se usar um PIN de inicialização com o chip do TPM é permitido, não permitido ou necessário.
    - **Chave de inicialização do TPM compatível** – configure se usar uma chave de inicialização com o chip do TPM é permitido, não permitido ou necessário.
    - **Chave e PIN de inicialização do TPM compatível** – configure se usar uma chave e um PIN de inicialização com o chip do TPM é permitido, não permitido ou necessário.
- **Tamanho mínimo do PIN** – Habilite essa configuração para configurar um tamanho mínimo para o PIN de inicialização de TPM.
    - **Número mínimo de caracteres** – Insira o número de caracteres necessário para o PIN de inicialização variando de **4**-**20**.
- **Recuperação de unidade do sistema operacional** – habilite essa configuração para controlar como as unidades do sistema operacional protegidas pelo BitLocker são recuperadas quando as informações de inicialização necessária não estão disponíveis.
    - **Agente de recuperação de dados baseada em certificado** – habilite essa configuração se quiser que os agentes de recuperação de dados possam ser usados com as unidades do sistema operacional protegidas pelo BitLocker.
    - **Criação de senha de recuperação pelo usuário** – Configure se é permitido, necessário ou não permitido que os usuários gerem uma senha de recuperação de 48 dígitos.
    - **Criação de chave de recuperação pelo usuário** – Configure se é permitido, necessário ou não permitido que os usuários gerem uma chave de recuperação de 256 bits.
    - **Opções de recuperação no assistente de instalação do BitLocker** – habilite essa configuração para impedir que os usuários vejam ou alterem as opções de recuperação ao ativarem o BitLocker.
    - **Salvar informações de recuperação do BitLocker no AD DS** – Habilita o armazenamento de informações de recuperação do BitLocker no Active Directory.
    - **Informações de recuperação do BitLocker armazenadas no AD DS** – configure quais partes das informações de recuperação do BitLocker são armazenadas no Active Directory. Escolha:
        - **Fazer backup de pacotes de chaves e senhas de recuperação**
        - **Fazer backup somente de senhas de recuperação**
    - **Armazenar informações de recuperação no AD DS antes de habilitar o BitLocker** – habilite essa configuração para impedir que os usuários ativem o BitLocker, a menos que o dispositivo esteja ingressado no domínio e que as informações de recuperação do BitLocker tenham sido armazenadas com êxito no Active Directory.
- **Mensagem e URL de recuperação de pré-inicialização** – habilite essa configuração para definir a mensagem e a URL que serão exibidas na tela de recuperação de chave de pré-inicialização.
    - **Mensagem de recuperação pré-inicialização** – Configure como a mensagem de recuperação pré-inicialização é exibida para os usuários. Escolha:
        - **Usar mensagem e URL de recuperação padrão**
        - **Usar mensagem e URL de recuperação vazia**
        - **Usar mensagem de recuperação personalizada**
        - **Usar URL de recuperação personalizada**


### <a name="bitlocker-fixed-data-drive-settings"></a>Configurações de unidades de dados fixas do BitLocker

- **Acesso de gravação para unidades de dados fixas não protegidas pelo BitLocker** – se habilitado, a proteção do BitLocker deverá ser habilitada em todas as unidades de dados fixas ou internas para que seja possível gravar nelas.
- **Recuperação de unidade fixa** – habilite essa configuração para controlar como as unidades fixas protegidas pelo BitLocker serão recuperadas quando as informações de inicialização necessárias não estiverem disponíveis.
    - **Agente de recuperação de dados** – habilite essa configuração se quiser que os agentes de recuperação de dados possam ser usados com as unidades fixas protegidas pelo BitLocker.
    - **Criação de senha de recuperação pelo usuário** – Configure se é permitido, necessário ou não permitido que os usuários gerem uma senha de recuperação de 48 dígitos.  
    - **Criação de chave de recuperação pelo usuário** – Configure se é permitido, necessário ou não permitido que os usuários gerem uma chave de recuperação de 256 bits.
    - **Opções de recuperação no assistente de instalação do BitLocker** – habilite essa configuração para impedir que os usuários vejam ou alterem as opções de recuperação ao ativarem o BitLocker.
    - **Salvar informações de recuperação do BitLocker no AD DS** – Habilita o armazenamento de informações de recuperação do BitLocker no Active Directory.
    - **Informações de recuperação do BitLocker no AD DS** – configure quais partes das informações de recuperação do BitLocker são armazenadas no Active Directory. Escolha:
        - **Fazer backup de pacotes de chaves e senhas de recuperação**
        - **Fazer backup somente de senhas de recuperação**
    - **Armazenar informações de recuperação no AD DS antes de habilitar o BitLocker** – habilite essa configuração para impedir que os usuários ativem o BitLocker, a menos que o dispositivo esteja ingressado no domínio e que as informações de recuperação do BitLocker tenham sido armazenadas com êxito no Active Directory.

### <a name="bitlocker-removable-data-drive-settings"></a>Configurações de unidade de dados removíveis do BitLocker

- **Acesso de gravação para unidades de dados removíveis não protegidas pelo BitLocker** – especifique se a criptografia do BitLocker é necessária para unidades de armazenamento removíveis.
  - **Acesso de gravação para dispositivos configurados em outra organização** – especifique se é possível gravar em unidades de dados removíveis que pertencem a outra organização.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Use o [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) para gerenciar e reduzir a superfície de ataque de aplicativos usados pelos seus funcionários.

### <a name="attack-surface-reduction"></a>Redução da superfície de ataque

Ajude a [impedir que aplicativos e ações](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard), que normalmente são usados por malwares em busca de exploração, infectem computadores.

#### <a name="rules-to-prevent-office-macro-threats"></a>Regras para impedir ameaças a macros do Office

Impeça que os aplicativos do Office executem as seguintes ações:

- **Injeção de aplicativos do Office em outros processos (sem exceções)**
- **Criação de conteúdo executável por aplicativos/macros do Office**
- **Inicialização de processos filhos por aplicativos do Office**
- **Importações do Win32 de código de macro do Office**

#### <a name="rules-to-prevent-script-threats"></a>Regras para impedir ameaças de script

Bloqueie os itens a seguir para ajudar a evitar ameaças de script:

- **Código de js/vbs/ps/macro ofuscado**
- **Execução de conteúdo baixado da Internet pelo js/vbs (sem exceções)**

#### <a name="rules-to-prevent-email-threats"></a>Regras para impedir ameaças de email

Bloqueie os itens a seguir para ajudar a evitar ameaças de email:

- **Execução de conteúdo executável (exe, dll, ps, js, vbs, etc.) proveniente do email (cliente de webmail/email) (sem exceções)**

#### <a name="attack-surface-reduction-exceptions"></a>Exceções de redução da superfície de ataque

- **Arquivos e pastas a serem excluídos das regras de redução da superfície de ataque** – importe/adicione uma lista de locais a serem excluídos das regras configuradas.

### <a name="controlled-folder-access"></a>Acesso controlado à pasta

Ajude a proteger dados valiosos contra ameaças e aplicativos mal-intencionados, como ransomware.

- **Proteção de pasta** – proteja arquivos e pastas contra alterações indesejadas realizadas por aplicativos mal-intencionados. Você pode importar uma **Lista de aplicativos com acesso a pastas protegidas** ou adicioná-los manualmente. Você também pode adicionar uma **Lista de pastas adicionais que precisam ser protegidas** com um upload ou adicioná-las manualmente.

### <a name="network-filtering"></a>Filtragem de rede

Bloqueie conexões de saída de qualquer aplicativo para IPs/domínios de reputação ruim.

### <a name="exploit-protection"></a>Proteção contra explorações

Impeça que o **Usuário edite a interface do Exploit Protection** carregando um arquivo XML que permite configurar a memória, o fluxo de controle e restrições de política que poderão ser usados para bloquear um aplicativo contra explorações.

Para habilitar o Exploit Protection, crie um arquivo XML que represente as configurações da sua escolha para mitigação do sistema e do aplicativo. Você pode fazer isso usando um destes dois métodos:

 1. PowerShell: use um ou mais dos cmdlets do PowerShell Get-ProcessMitigation, Set-ProcessMitigation e ConvertTo-ProcessMitigationPolicy para definir as configurações de mitigação e exportar uma representação XML delas.

 2. Interface do usuário da Central de Segurança do Windows Defender: na Central de Segurança do Windows Defender, clique no controle de aplicativo e navegador e, em seguida, role até a parte inferior da tela resultante para localizar o Exploit Protection. Primeiro, use as guias Configurações do sistema e Configurações do programa para definir as configurações de mitigação. Em seguida, localize o link Exportar configurações na parte inferior da tela para exportar uma representação XML delas.

## <a name="windows-defender-application-control"></a>Controle de Aplicativos do Windows Defender

Use as **Políticas de integridade de código do controle de aplicativos** para escolher os aplicativos adicionais que precisam ser auditados ou que são confiáveis para serem executados pelo Controle de Aplicativos do Windows Defender. Os componentes do Windows e todos os aplicativos da Windows Store são automaticamente confiáveis para execução.

Os aplicativos não serão bloqueados durante a execução no modo "somente auditoria". O modo "somente auditoria" registra todos os eventos em logs do cliente local.

## <a name="windows-defender-security-center"></a>Central de Segurança do Windows Defender

O aplicativo Central de Segurança do Windows Defender opera como um aplicativo ou processo separado de cada recurso individual e exibirá notificações por meio da Central de Ações. Ele atua como um coletor ou um único lugar para ver o status e executar algumas etapas de configuração para cada um dos recursos. Encontre mais informações nos documentos do [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).

#### <a name="windows-defender-security-center-app-and-notifications"></a>Aplicativo Central de Segurança do Windows Defender e notificações

Bloqueie o acesso de usuário final a várias áreas do aplicativo Central de Segurança do Windows Defender. Ocultar uma seção também bloqueará as notificações relacionadas.

- **Proteção contra vírus e ameaças**
- **Integridade e desempenho do dispositivo**
- **Proteção de firewall e rede**
- **Controle de aplicativo e navegador**
- **Opções da família**
- **Notificações das áreas exibidas do aplicativo** – escolha quais notificações serão exibidas aos usuários finais. As notificações não críticas incluem resumos de atividades do Windows Defender Antivírus, incluindo notificações após a conclusão das verificações. Todas as outras notificações são consideradas críticas.

#### <a name="it-contact-information"></a>Informações de contato de TI

Forneça as informações de contato de TI que aparecem no aplicativo Central de Segurança do Windows Defender e as notificações do aplicativo. Você pode escolher **Exibir no aplicativo e em notificações**, **Exibir somente no aplicativo**, **Exibir somente em notificações** ou **Não exibir**. Você deve definir o **nome da organização de TI** e pelo menos uma das seguintes opções de contato:

- **Número de telefone ou ID do Skype do departamento de TI**
- **Endereço de email do departamento de TI**
- **URL do site de suporte de TI**

## <a name="next-steps"></a>Próximas etapas

Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
