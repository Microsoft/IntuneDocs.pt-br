---
title: Configurações de linhas de base de segurança do Intune para o Windows 10
titleSuffix: Microsoft Intune
description: Configurações de linhas de base de segurança do Intune para gerenciar o Windows 10
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 82fa4fc7f9e60dff3c08adf3281351cbfa8eb743
ms.sourcegitcommit: cb76efd3db60a422a65478ebce83d3aea7b5eeed
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66749927"
---
# <a name="windows-security-baseline-settings-for-intune"></a>Configurações de linha de base de segurança do Windows para o Intune  

Exiba as [configurações de linha de base de segurança do Windows](security-baselines.md) compatíveis com Microsoft Intune. Os padrões de linha de base do Windows representam a configuração recomendada para Windows e podem não corresponder aos padrões de linha de base de outras linhas de base de segurança.  

> [!NOTE]  
> As configurações de linha de base de segurança do Windows estão em **Versão Prévia**. Enquanto estiver em versão prévia, a lista de configurações disponíveis e a ordem em que este conteúdo apresenta essas configurações vão variar com o que estiver disponível no portal.  
>  
> Quando as configurações de linha de base saírem da versão prévia, esse conteúdo será atualizado com a lista fora da versão prévia das configurações de linha de base de segurança compatíveis com o Intune.  

## <a name="above-lock"></a>AboveLock  
Para obter mais informações, veja [CSP de política – AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) na documentação do Windows.  

- **Bloquear exibição de notificações do sistema**  
  Essa configuração de política permite impedir que as notificações de aplicativo sejam exibidas na tela de bloqueio. Se você habilitar essa configuração de política, nenhuma notificação de aplicativo será exibida na tela de bloqueio. Se você desabilitar ou não configurar essa política, os usuários poderão escolher quais aplicativos exibem notificações na tela de bloqueio.
  
  **Padrão**: Sim  

## <a name="app-runtime"></a>Tempo de execução do aplicativo    
Para obter mais informações, veja [CSP de política – AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) na documentação do Windows.  

- **Contas da Microsoft opcionais para aplicativos da Windows Store**  
  Essa configuração de política permite controlar se as contas da Microsoft são opcionais para aplicativos da Windows Store que exigem uma conta para entrada. Essa política afeta somente aplicativos da Windows Store que dão suporte a ele. Se você habilitar essa configuração de política, aplicativos da Windows Store que normalmente exigem uma conta Microsoft para entrar permitirá aos usuários entrar com uma conta da empresa em vez disso. Se você desabilitar ou não configurar essa política, os usuários deverão entrar com uma conta Microsoft.  
  
  **Padrão**: habilitado  

## <a name="application-management"></a>Gerenciamento de aplicativos   
Para obter mais informações, veja [CSP de política – ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) na documentação do Windows.  

- **Bloquear DVR de Jogos (somente área de trabalho)**  
  Configura se a gravação e a difusão de jogos são permitidas.
  
  **Padrão**: Sim  

## <a name="auto-play"></a>Reprodução automática   
Para obter mais informações, veja [CSP de política – Reprodução automática](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) na documentação do Windows.  

- **Comportamento de execução automática padrão para reprodução automática**  
  Essa configuração afeta o comportamento padrão para comandos de execução automática. Comandos de execução automática são armazenados em arquivos Autorun.inf e podem iniciar programas de instalação ou outras rotinas. Quando *Habilitado*, os administradores podem alterar o comportamento de execução automática padrão em um dispositivo que execute Windows Vista ou posterior. O comportamento pode ser definido como: a) desabilitar completamente comandos de execução automática ou b) reverter para o comportamento anterior ao Windows Vista de executar automaticamente o comando de execução automática. Quando definidos como *Desabilitados* ou *Não configurados*, dispositivos que executem o Windows Vista ou posterior avisam o usuário sobre se um comando de execução automática deve ser executado.
  
  **Padrão**: Não executar  
  
- **Modo de reprodução automática**  
  Essa configuração de política permite que você desative o recurso de Reprodução Automática. A Reprodução Automática começa a ler de uma unidade assim que você insere a mídia na unidade. Como resultado, o arquivo de instalação de programas e a música na mídia de áudio são iniciados imediatamente. Antes do Windows XP SP2, a reprodução automática estava desabilitada por padrão em unidades removíveis, como a unidade de disquete (mas, não a unidade de CD-ROM) e em unidades de rede. Do Windows XP SP2 em diante, a reprodução automática também está habilitada para unidades removíveis, incluindo unidades Zip e alguns dispositivos de armazenamento em massa USB. Se você habilitar essa configuração de política, a reprodução automática será desabilitada em CD-ROM e unidades de mídia removíveis ou desabilitada em todas as unidades. Essa configuração de política desabilita a Reprodução Automática em outros tipos de unidades. Não é possível usar essa configuração para habilitar a Reprodução Automática em unidades em que ela é desabilitada por padrão. Se você desabilitar ou não configurar essa política, a Reprodução Automática será habilitada. Observação: essa configuração de política é exibida nas pastas Configuração do Computador e Configuração do Usuário. Se as configurações de política estiverem em conflito, a configuração de política em Configuração do Computador terá precedência sobre a configuração de política do usuário.
  
  **Padrão**: desabilitado

- **Bloquear a reprodução automática para dispositivos não de volume**  
  Essa configuração de política não permite a Reprodução Automática para dispositivos MTP como câmeras ou telefones. Se você habilitar essa configuração de política, a Reprodução Automática não será permitida para dispositivos MTP como câmeras ou telefones. Se você desabilitar ou não configurar essa política, a Reprodução Automática será habilitada para dispositivos sem volume.
  
  **Padrão**: habilitado  

## <a name="bitlocker"></a>Bitlocker    
Para obter mais informações, veja [CSP de política – Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) na documentação do Windows.  

- **Política de unidade removível do BitLocker**  
  Essa configuração de política é usada para controlar o método de criptografia e o nível de codificação. Os valores dessa política determinam o nível da criptografia que o BitLocker usa para criptografia. As empresas talvez queiram controlar o nível de criptografia para aumentar a segurança (AES-256 é mais forte do que AES-128). Se você habilitar essa configuração, poderá configurar um algoritmo de criptografia e a intensidade da chave de criptografia para unidades de dados fixas, unidades do sistema operacional e unidades de dados removíveis individualmente. Para unidades de sistemas operacionais e fixas, recomendamos usar o algoritmo XTS-AES. Para unidades removíveis, você deve usar AES-CBC de 128 bits ou AES-CBC de 256 bits caso a unidade seja usada em outros dispositivos que não estejam executando o Windows 10, versão 1511 ou posterior. Alterar o método de criptografia não terá efeito se a unidade já estiver criptografada ou se a criptografia estiver em andamento. Nesses casos, essa configuração de política será ignorada.

  Para a política da unidade removível do BitLocker, defina as seguintes configurações:

    - **Exigir criptografia para acesso de gravação**  
      **Padrão**: Sim  
  
    - **Método de criptografia**  
      **Padrão**: CBC AES de 256 bits  

- **Política de unidade fixa do BitLocker**  
  Essa configuração de política é usada para controlar o método de criptografia e o nível de codificação. Os valores dessa política determinam o nível da criptografia que o BitLocker usa para criptografia. As empresas talvez queiram controlar o nível de criptografia para aumentar a segurança (AES-256 é mais forte do que AES-128). Se você habilitar essa configuração, poderá configurar um algoritmo de criptografia e a intensidade da chave de criptografia para unidades de dados fixas, unidades do sistema operacional e unidades de dados removíveis individualmente. Para unidades de sistemas operacionais e fixas, recomendamos usar o algoritmo XTS-AES. Para unidades removíveis, você deve usar AES-CBC de 128 bits ou AES-CBC de 256 bits caso a unidade seja usada em outros dispositivos que não estejam executando o Windows 10, versão 1511 ou posterior. Alterar o método de criptografia não terá efeito se a unidade já estiver criptografada ou se a criptografia estiver em andamento. Nesses casos, essa configuração de política será ignorada.  
 
   Para a política da unidade fixa do BitLocker, defina as seguintes configurações: 
   - **Método de criptografia**
     **Padrão**: XTS de AES de 256 bits  

- **Política de unidade do sistema do BitLocker**  
  Essa configuração de política é usada para controlar o método de criptografia e o nível de codificação. Os valores dessa política determinam o nível da criptografia que o BitLocker usa para criptografia. As empresas talvez queiram controlar o nível de criptografia para aumentar a segurança (AES-256 é mais forte do que AES-128). Se você habilitar essa configuração, poderá configurar um algoritmo de criptografia e a intensidade da chave de criptografia para unidades de dados fixas, unidades do sistema operacional e unidades de dados removíveis individualmente. Para unidades de sistemas operacionais e fixas, recomendamos usar o algoritmo XTS-AES. Para unidades removíveis, você deve usar AES-CBC de 128 bits ou AES-CBC de 256 bits caso a unidade seja usada em outros dispositivos que não estejam executando o Windows 10, versão 1511 ou posterior. Alterar o método de criptografia não terá efeito se a unidade já estiver criptografada ou se a criptografia estiver em andamento. Nesses casos, essa configuração de política será ignorada.  

   Para a política da unidade de sistema do BitLocker, defina as seguintes configurações:
  - **Método de criptografia**  
    **Padrão**: XTS AES de 256 bits  

## <a name="browser"></a>Navegador  
Para obter mais informações, veja [CSP de política – Navegador](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) na documentação do Windows.  

- **Exigir SmartScreen para Microsoft Edge**  
  O Microsoft Edge usa o Windows Defender SmartScreen (ligado) para proteger os usuários contra possíveis golpes de phishing e software mal-intencionado por padrão. Além disso, por padrão, os usuários não podem desabilitar (desligar) o Windows Defender SmartScreen. A habilitação dessa política desliga o Windows Defender SmartScreen e impede os usuários de ligá-lo. Não configure essa política para permitir que os usuários optem por ligar ou desligar o Windows Defender SmartScreen.  
  
  **Padrão**: Sim  
  
- **Bloquear acesso a sites mal-intencionados**  
  Por padrão, o Microsoft Edge permite que os usuários contornem (ignorem) os avisos do Windows Defender SmartScreen sobre sites potencialmente mal-intencionados, permitindo que eles prossigam para o site. Com essa política, você pode configurar o Microsoft Edge para impedir que os usuários ignorem os avisos, impedindo-os de prosseguir para o site.
  
  **Padrão**: Sim  
  
- **Bloquear download de arquivos não verificados** Por padrão, o Microsoft Edge permite que os usuários contornem (ignorem) os avisos do Windows Defender SmartScreen sobre arquivos potencialmente mal-intencionados, permitindo que eles continuem baixando os arquivos não verificados. Habilitar essa política impede que os usuários ignorem os avisos, impedindo-os de baixar de arquivos não verificados.
  
  **Padrão**: Sim  
  
- **Bloquear Gerenciador de Senhas**  
  Por padrão, Microsoft Edge usa o Gerenciador de Senhas automaticamente, permitindo que os usuários gerenciem as senhas localmente. Desabilitar esta política impede o Microsoft Edge de utilizar o Gerenciador de Senhas. Não configure essa política se você quiser permitir que os usuários optem por salvar e gerenciar senhas localmente usando o Gerenciador de Senhas.
  
  **Padrão**: Sim  
  
- **Prevenir substituições de erro de certificado**  
  Essa configuração de política impede o usuário de ignorar erros de certificado de protocolo SSL/TLS que interrompem a navegação (como "expirado", "revogado" ou erros de "incompatibilidade de nome") no Internet Explorer. Se você habilitar essa configuração de política, o usuário não poderá continuar a navegação. Se você desabilitar ou não configurar essa política, o usuário poderá optar por ignorar erros de certificado e continuar a navegação.
  
  **Padrão**: Sim  

## <a name="connectivity"></a>Conectividade  
Para obter mais informações, veja [CSP de Política – Conectividade](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) na documentação do Windows.  

- **Impedir o download da Internet para publicação na Web e assistentes de pedidos online**  
  Essa configuração de política especifica se o Windows deve baixar uma lista de provedores para a publicação na Web e assistentes de pedidos online. Esses assistentes permitem que os usuários selecionem de uma lista de empresas que oferecem serviços como armazenamento online e impressão fotográfica. Por padrão, o Windows exibe provedores baixados de um site do Windows, além de provedores especificados no Registro. Se você habilitar essa configuração de política, o Windows não baixará provedores e somente os provedores de serviços armazenados em cache no Registro local serão exibidos. Se você desabilitar ou não configurar essa política, uma lista de provedores será baixada quando o usuário usar a publicação na Web ou assistentes de pedidos online. Para obter mais informações que incluem detalhes sobre como especificar provedores de serviço no Registro, confira a documentação para a publicação na Web e assistentes de pedidos online.  
  
  **Padrão**: habilitado  

- **Bloquear o download de drivers de impressão via HTTP**  
  Essa configuração de política especifica se deve permitir que o cliente baixe pacotes de driver de impressão via HTTP. Para configurar a impressão de HTTP, drivers de caixa de entrada não precisam ser baixados por HTTP. Observação: essa configuração de política não impede que o cliente imprima em impressoras na Intranet ou na Internet via HTTP. Ela apenas proíbe o download de drivers que ainda não estão instalados localmente. Se você habilitar essa configuração de política, os drivers de impressão não poderão ser baixados por HTTP. Se você desabilitar ou não configurar essa política, os usuários poderão baixar drivers de impressão via HTTP.
  
  **Padrão**: habilitado  

## <a name="credentials-delegation"></a>Delegação de credenciais  
Para obter mais informações, veja [CSP de política – CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) na documentação do Windows.  

- **Delegação de host remoto de credenciais não exportáveis**  
  O host remoto permite a delegação de credenciais não exportáveis. Ao usar a delegação de credencial, dispositivos fornecem uma versão exportável de credenciais para o host remoto, que expõe os usuários ao risco de roubo de credenciais contra invasores no host remoto. Se você habilitar essa configuração de política, o host dará suporte aos modos de Administração Restrito ou Credential Guard Remoto. Se você desabilitar ou não configurar essa política, não haverá suporte para os modos de Administração Restrita e Credential Guard Remoto. O usuário sempre precisa transmitir suas credenciais para o host.  

  
  **Padrão**: habilitado  

## <a name="credentials-ui"></a>Interface do usuário de credenciais  
Para obter mais informações, veja [CSP de política – CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) na documentação do Windows.  

- **Enumerar administradores** Essa configuração de política controla se as contas de administrador são exibidas quando um usuário tenta elevar um aplicativo em execução. Por padrão, as contas de administrador não são exibidas quando o usuário tenta elevar um aplicativo em execução. Se você habilitar essa configuração de política, todas as contas de administrador local no PC serão exibidas para que o usuário possa escolher uma e inserir a senha correta. Se você desabilitar essa configuração de política, os usuários sempre precisarão inserir um nome de usuário e senha para elevar.  

  
  **Padrão**: desabilitado  

## <a name="data-protection"></a>Proteção de dados  
Para obter mais informações, veja [CSP de política – DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) na documentação do Windows.  

- **Bloquear acesso direto à memória**  
  Essa configuração de política permite que você bloqueie o DMA (acesso direto à memória) para todas as portas downstream PCI com hot-plug até um usuário fazer logon no Windows. Depois que um usuário fizer logon, o Windows vai enumerar os dispositivos PCI conectados às portas host plug PCI. Sempre que o usuário bloqueia o computador, o DMA é bloqueado em portas PCI com hot-plug sem dispositivos filhos até que o usuário faça logon novamente. Os dispositivos que já foram enumerados quando o computador foi desbloqueado continuarão a funcionar até que sejam desconectados. Essa configuração de política é imposta somente quando a criptografia BitLocker ou de dispositivo está habilitada.
  
  
  **Padrão**: Sim  

## <a name="device-guard"></a>Device Guard  
Para obter mais informações, veja [CSP de política – DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) na documentação do Windows.  

- **Credential Guard**  
  Essa configuração permite que os usuários ativem o Credential Guard com segurança baseada em virtualização para ajudar a proteger as credenciais na próxima reinicialização.
   
  **Padrão**: Habilitar com bloqueio UEFI 

- **Habilitar segurança baseada em virtualização**  </br>
  Ativa a VBS (segurança baseada em virtualização) na próxima reinicialização. A segurança baseada em virtualização usa o Hipervisor do Windows para dar suporte aos serviços de segurança.
  
  **Padrão**: Sim  

<!-- not yet available 
- **Enable secure boot with DMA**  
  Among the commands that follow, you can choose settings for Secure Boot and Secure Boot with DMA. In most situations, we recommend that you choose Secure Boot. This option provides Secure Boot with as much protection as is supported by a given computer’s hardware. A computer with input/output memory management units (IOMMUs) will have Secure Boot with DMA protection. A computer without IOMMUs will simply have Secure Boot enabled. In contrast, with Secure Boot with DMA, the setting will enable Secure Boot—and VBS itself—only on a computer that supports DMA, that is, a computer with IOMMUs. With this setting, any computer without IOMMUs won't have VBS or HVCI protection, although it can still have WDAC enabled.
  
  
  **Default**: Yes  
  -->
- **Iniciar proteção do sistema**    
  **Padrão**: habilitado  

## <a name="device-installation"></a>Instalação de dispositivo  
Para obter mais informações, veja [CSP de política – DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) na documentação do Windows.  

- **Instalação de dispositivo de hardware por identificadores de dispositivo**  
  Essa configuração de política permite que você especifique uma lista de IDs de hardware Plug and Play e IDs compatíveis com dispositivos que o Windows é impedido de instalar. Essa configuração de política tem precedência sobre qualquer outra configuração de política que permita ao Windows instalar um dispositivo. Se você habilitar essa configuração de política, o Windows será impedido de instalar um dispositivo cuja ID de hardware ou ID compatível seja exibida na lista que você cria. Se você habilitar essa configuração de política em um servidor de área de trabalho remota, a configuração de política afetará o redirecionamento de dispositivos especificados de um cliente da área de trabalho remota para o servidor de área de trabalho remota. Se você desabilitar ou não configurar essa política, os dispositivos poderão instalar e atualizar conforme permitido ou impedido por outras configurações de política.
  
  **Padrão**: bloquear a instalação de dispositivo de hardware  

    Quando *Bloquear a instalação de dispositivo de hardware* estiver selecionada, as configurações a seguir estarão disponíveis.
  
    - **Remover dispositivos de hardware correspondentes**   
    Essa configuração está disponível apenas quando *Instalação de dispositivo de hardware por identificadores de dispositivo* é definida como *Bloquear instalação de dispositivo de hardware*.
      
      **Padrão**: Sim
  
    - **Identificadores de dispositivo de hardware que estão bloqueados**  
       Essa configuração está disponível apenas quando *Instalação de dispositivo de hardware por identificadores de dispositivo* é definida como *Bloquear instalação de dispositivo de hardware*.
      
      **Padrão**: Sim  
  
- **Instalação de dispositivo de hardware por classes de instalação**  
  Essa configuração de política permite que você especifique uma lista de GUIDs (identificadores globalmente exclusivos) de classe de configuração de dispositivo para drivers de dispositivo que o Windows seja impedido de instalar. Essa configuração de política tem precedência sobre qualquer outra configuração de política que permita ao Windows instalar um dispositivo. Se você habilitar essa configuração de política, o Windows será impedido de instalar ou atualizar drivers de dispositivo cujos GUIDs de classe de instalação do dispositivo apareçam na lista de você cria. Se você habilitar essa configuração de política em um servidor de área de trabalho remota, a configuração de política afetará o redirecionamento de dispositivos especificados de um cliente da área de trabalho remota para o servidor de área de trabalho remota. Se você desabilitar ou não configurar essa política, o Windows poderá instalar e atualizar dispositivos conforme permitido ou impedido por outras configurações de política.
  
  **Padrão**: bloquear a instalação de dispositivo de hardware  

    Quando *Bloquear a instalação de dispositivo de hardware* estiver selecionada, as configurações a seguir estarão disponíveis.
    - **Remover dispositivos de hardware correspondentes**    
    Essa configuração está disponível apenas quando *Instalação de dispositivo de hardware por classes de instalação* é definida como *Bloquear instalação de dispositivo de hardware*.  

      **Padrão**: *nenhuma configuração padrão*  
  
    - **Identificadores de dispositivo de hardware que estão bloqueados**  
      Essa configuração está disponível apenas quando *Instalação de dispositivo de hardware por classes de instalação* é definida como *Bloquear instalação de dispositivo de hardware*.
      
      **Padrão**: *nenhuma configuração padrão*  

## <a name="device-lock"></a>Bloqueio de dispositivo  
Para obter mais informações, veja [CSP de política – DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) na documentação do Windows.  

- **Impedir o uso da câmera**  
  Desabilita o botão de alternância da câmera da tela de bloqueio nas configurações do computador e impede que uma câmera seja invocada na tela de bloqueio. Por padrão, os usuários podem habilitar a invocação de uma câmera disponível na tela de bloqueio. Se você habilitar essa configuração, os usuários não poderão habilitar ou desabilitar o acesso à câmera da tela de bloqueio nas configurações do computador e a câmera não poderá ser invocada na tela de bloqueio. 
  
  **Padrão**: habilitado  

- **Exigir senha**  
  Especifica se o bloqueio de dispositivo está habilitado.
  
  **Padrão**: Sim  
  
    Quando *Exigir senha* estiver definido como *Sim*, as configurações a seguir estarão disponíveis.

    - **Contagem do conjunto de caracteres mínimo da senha**  
      O número de tipos de elementos complexos (letras maiúsculas e minúsculas, números e pontuação) necessário para um PIN ou uma senha forte. O PIN impõe o seguinte comportamento para dispositivos móveis e da área de trabalho: 1: apenas dígitos, 2: dígitos e letras minúsculas são necessários, 3: dígitos, letras minúsculas e letras maiúsculas são necessários. Não é compatível com contas da Microsoft de área de trabalho e contas de domínio. 4: dígitos, letras minúsculas, letras maiúsculas e caracteres especiais são necessários. Não é compatível com a área de trabalho. O valor padrão é 1. 
      
      **Padrão**: 3  
  
    - **Número de falhas de início de sessão antes de limpar o dispositivo**  
      O número de falhas de autenticação permitidas antes que o dispositivo seja apagado. Um valor 0 desabilita a funcionalidade de apagamento do dispositivo.
        
      **Padrão**: 10  
  
    - **Expiração da senha (dias)**  
      A configuração de política de duração máxima da senha determina o período (em dias) pelo qual uma senha pode ser usada antes de o sistema exigir que o usuário a altere. Você pode definir as senhas expirar após um número de dias entre 1 e 999 ou pode especificar que as senhas nunca expirem definindo o número de dias como 0. Se a duração máxima da senha for entre 1 e 999 dias, a duração mínima da senha deverá ser menor do que esse valor. Se a duração máxima da senha for definida como 0, a duração mínima da senha poderá ser qualquer valor entre 0 e 998 dias.
      
      **Padrão**: 60  
  
    - **Tipo de senha necessária**  
      Determina o tipo de PIN ou senha necessária.
      
      **Padrão**: alfanumérico  
  
    - **Comprimento mínimo da senha**  
      A configuração de política de Comprimento mínimo da senha determina o menor número de caracteres que podem formar uma senha para uma conta de usuário. Você pode definir um valor entre 1 e 14 caracteres ou pode estabelecer que nenhuma senha é necessária definindo o número de caracteres como 0.
      
      **Padrão**: 8  
  
    - **Bloquear senhas simples**  
      Especifica se os PINs ou senhas como "1111" ou "1234" são permitidas. Para a área de trabalho, ela também controla o uso de senhas com imagem.
      
      **Padrão**: Sim  
        *Uma configuração de Sim impede o uso de senhas simples.* 

  - **Evitar a reutilização de senhas anteriores**  
    Especifica quantas senhas podem ser armazenadas no histórico e não podem ser usadas. O valor inclui a senha atual do usuário. Por exemplo, com uma configuração de *1*, o usuário não pode reutilizar a senha atual ao escolher uma nova senha. Uma configuração de *5* significa que um usuário não pode definir sua nova senha como a senha atual ou qualquer uma das quatro senhas anteriores.
    
    **Padrão**: 24  

- **Impedir a apresentação de slides**  
  Desabilita as configurações de apresentação de slides da tela de bloqueio nas configurações do computador e impede a reprodução de uma apresentação de slides na tela de bloqueio. Por padrão, os usuários podem habilitar uma apresentação de slides que será executada após bloquearem o computador. Se você habilitar essa configuração, os usuários não poderão modificar as configurações de apresentação de slides nas configurações do computador e nenhuma apresentação de slides será iniciada.
  
    **Padrão**: habilitado  
    *Uma configuração Habilitada impede a execução de apresentações de slides.* 

- **Duração mínima da senha em dias**  
  A configuração de política de duração mínima da senha determina o período (em dias) pelo qual uma senha deve ser usada antes de o usuário poder alterá-la. Você pode definir um valor entre 1 e 998 dias ou pode permitir alterações de senha imediatamente definindo o número de dias como 0. A duração mínima da senha deve ser menor que a duração máxima da senha, a menos que a duração máxima da senha seja definida como 0, indicando que as senhas nunca expirarão. Se a duração máxima da senha for definida como 0, a duração mínima da senha poderá ser definida para qualquer valor entre 0 e 998.
  
    **Padrão**: 1  

## <a name="event-log-service"></a>Serviço de Log de Eventos  
Para obter mais informações, veja [CSP de política – EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) na documentação do Windows.  

- **Tamanho do arquivo máximo do log de segurança em KB**  
  Essa configuração de política especifica o tamanho máximo do arquivo de log em quilobytes. Se você habilitar essa configuração de política, poderá configurar o tamanho máximo do arquivo de log para ser entre 1 megabyte (1.024 quilobytes) e 2 terabytes (2.147.483.647 quilobytes) em incrementos de quilobytes. Se você desabilitar ou não configurar essa política, o tamanho máximo do arquivo de log será definido como o valor configurado localmente. Esse valor pode ser alterado pelo administrador local usando a caixa de diálogo Propriedades de Log e o padrão é 20 megabytes.
  
   **Padrão**: 196608  

- **Tamanho do arquivo máximo do log do sistema em KB**  
  Essa configuração de política especifica o tamanho máximo do arquivo de log em quilobytes. Se você habilitar essa configuração de política, poderá configurar o tamanho máximo do arquivo de log para ser entre 1 megabyte (1.024 quilobytes) e 2 terabytes (2.147.483.647 quilobytes) em incrementos de quilobytes. Se você desabilitar ou não configurar essa política, o tamanho máximo do arquivo de log será definido como o valor configurado localmente. Esse valor pode ser alterado pelo administrador local usando a caixa de diálogo Propriedades de Log e o padrão é 20 megabytes.
  
  **Padrão**: 32768  

- **Tamanho do arquivo máximo do log do aplicativo em KB**  
  Essa configuração de política especifica o tamanho máximo do arquivo de log em quilobytes. Se você habilitar essa configuração de política, poderá configurar o tamanho máximo do arquivo de log para ser entre 1 megabyte (1.024 quilobytes) e 2 terabytes (2.147.483.647 quilobytes) em incrementos de quilobytes. Se você desabilitar ou não configurar essa política, o tamanho máximo do arquivo de log será definido como o valor configurado localmente. Esse valor pode ser alterado pelo administrador local usando a caixa de diálogo Propriedades de Log e o padrão é 20 megabytes.
  
  **Padrão**: 32768  

## <a name="experience"></a>Experiência  
Para obter mais informações, veja [CSP de política – Experiência](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) na documentação do Windows.  

- **Bloquear o Destaque do Windows**  
  Permite que os administradores de TI desativem todos os Recursos de Destaque do Windows: Destaque do Windows na tela de bloqueio, Dicas do Windows, recursos do consumidor da Microsoft e outros recursos relacionados.
  
  **Padrão**: Sim  

  Quando *Bloquear Destaque do Windows* estiver definido como *Sim*, as configurações a seguir estarão disponíveis.
  
  - **Bloquear sugestões de terceiros no Destaque do Windows**  
    Especifica se deve permitir sugestões de aplicativos e conteúdo de editores de software de terceiros nos recursos de Destaque do Windows como o destaque da tela de bloqueio, aplicativos sugeridos no menu Iniciar e dicas do Windows. Os usuários ainda poderão ver sugestões de recursos, aplicativos e serviços da Microsoft.
      
    **Padrão**: Sim  
   - **Bloquear recursos específicos do consumidor**  
      Permite que os administradores de TI habilitem as experiências que normalmente são apenas para consumidores, como Sugestões de início, Notificações de associação, instalação de aplicativo pós-OOBE e redirecionamento de blocos.
      
     **Padrão**: Sim  


## <a name="exploit-guard"></a>Exploit Guard  
Para obter mais informações, veja [CSP de política – ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) na documentação do Windows.  

- **XML de Exploit Protection**  
  Permite que o administrador de TI efetue push de uma configuração que representa as opções de migração de aplicativo e sistema desejadas para todos os dispositivos na organização. A configuração é representada por um XML. O Exploit Protection ajuda a proteger os dispositivos contra malware que usa explorações para se espalhar e infectar. Use o aplicativo de Segurança do Windows ou o PowerShell para criar um conjunto de mitigações (conhecido como uma configuração). Você pode então exportar essa configuração como um arquivo XML e compartilha-lo com vários computadores na sua rede para que todos tenham o mesmo conjunto de configurações de mitigação. Você também pode converter e importar um arquivo XML de configuração EMET existente em um XML de Exploit Protection.
  
  **Padrão**: *o XML de exemplo é fornecido* 
 
## <a name="file-explorer"></a>Explorador de Arquivos  
Para obter mais informações, veja [CSP de política – FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) na documentação do Windows.  

- **Bloquear a prevenção de execução de dados**  
  Desabilitar a prevenção de execução de dados pode permitir que determinados aplicativos de plug-in herdados funcionem sem encerrar o Explorer.
  
  **Padrão**: desabilitado  
   
- **Bloquear o encerramento de heap na corrupção**  
  Desabilitar o encerramento de heap na corrupção pode permitir que determinados aplicativos de plug-in herdados funcionem sem encerrar o Explorer imediatamente, embora o Explorer ainda possa ser encerrado de forma inesperada posteriormente.
  
  **Padrão**: desabilitado  
    

## <a name="internet-explorer"></a>Internet Explorer  
Para obter mais informações, veja [CSP de política – InternetExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) na documentação do Windows.  
<!-- not yet available 
- **Scan incoming mail messages**  
  Allows or disallows scanning of email.
  
  **Default**: Disabled  
  
- **Office apps launch child process type**  
  Office apps won't be allowed to create child processes. This includes Word, Excel, PowerPoint, OneNote, and Access. This is a typical malware behavior, especially for macro-based attacks that attempt to use Office apps to launch or download malicious executables.
  
  **Default**: Disable  
  
- **Defender sample submission consent type**  
  Checks for the user consent level in Windows Defender to send data. If the required consent has already been granted, Windows Defender submits them. If not (and if the user has specified never to ask), the UI is launched to ask for user consent (when Defender/AllowCloudProtection is allowed) before sending data.
  
  **Default**: Disable  
  
- **Signature update interval (in hours)**  
  Defender signature update interval in hours
  
  **Default**: Disabled  
 -->
- **Acesso de zona de internet a fontes de dados do Internet Explorer**  
  Essa configuração de política permite que você gerencie se o Internet Explorer pode acessar dados de outra zona de segurança usando o MSXML (Microsoft XML Parser) ou ADO (ActiveX Data Objects). Se você habilitar essa configuração de política, os usuários poderão carregar uma página na zona que use MSXML ou ADO para acessar dados de outro site na zona. Se você selecionar Solicitar na caixa suspensa, os usuários serão consultados para escolher se desejam permitir que uma página seja carregada na zona que usa MSXML ou ADO para acessar dados de outro site na zona. Se você desabilitar essa configuração de política, os usuários não poderão carregar uma página na zona que use MSXML ou ADO para acessar dados de outro site na zona. Se você não configurar essa política, os usuários não poderão carregar uma página na zona que use MSXML ou ADO para acessar dados de outro site na zona.
  
  **Padrão**: Desabilitar  
  
- **Arrastar conteúdo de domínios diferentes dentro das janelas na zona restrita do Internet Explorer**  
  Esta configuração de política permite que você defina opções sobre o arraste de conteúdo de um domínio para outro quando a origem e o destino estão na mesma janela. Se você habilitar esta configuração de política e clicar em Habilitar, os usuários poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem na mesma janela. Os usuários não podem alterar essa configuração. Se você habilitar esta configuração de política e clicar em Desabilitar, os usuários não poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem na mesma janela. Os usuários não podem alterar essa configuração na caixa de diálogo Opções da Internet. No Internet Explorer 10, se você desabilitar ou não definir esta configuração de política, os usuários não poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem na mesma janela. Os usuários poderão alterar essa configuração na caixa de diálogo Opções da Internet. No Internet Explorer 9 e em versões anteriores, se você desabilitar ou não definir esta configuração de política, os usuários poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem na mesma janela. Os usuários não podem alterar essa configuração na caixa de diálogo Opções da Internet.
  
  **Padrão**: desabilitado
  
- **Aviso de incompatibilidade de endereço do certificado do Internet Explorer**  
  Essa configuração de política permite que você ative o aviso de segurança de incompatibilidade de endereço do certificado. Quando essa configuração de política é ativada, o usuário é avisado ao visitar sites HTTPS (HTTP seguros) que apresentam certificados emitidos para um endereço de site diferente. Esse aviso ajuda a impedir ataques de falsificação. Se você habilitar essa configuração de política, o aviso de incompatibilidade de endereço do certificado sempre aparecerá. Se você desabilitar ou não configurar essa política, o usuário poderá escolher se o aviso de incompatibilidade de endereço do certificado será exibido (usando a página Avançado no painel de controle da Internet).
  
  **Padrão**: habilitado 
  
- **Sites com menos privilégios de zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie se os sites em zonas com menos privilégios, como sites da Internet, podem navegar para essa zona. Se você habilitar essa configuração de política, os sites em zonas com menos privilégios podem abrir novas janelas ou navegar até esta zona. A zona de segurança será executada sem a camada de segurança adicional fornecida pelo recurso de segurança de Proteção contra Elevação de Zona. Se você selecionar Prompt na caixa suspensa, será emitido um aviso para o usuário indicando que uma navegação potencialmente arriscada está prestes a ocorrer. Se você desabilitar essa configuração de política, a navegação possivelmente prejudicial será evitada. O recurso de segurança do Internet Explorer está ativado nessa zona conforme definido pelo controle do recurso de Proteção contra Elevação de Zona. Se você não configurar essa política, as navegações possivelmente prejudiciais serão evitadas. O recurso de segurança do Internet Explorer está ativado nessa zona conforme definido pelo controle do recurso de Proteção contra Elevação de Zona.
  
  **Padrão**: Desabilitar  
  
- **Prompt de download de arquivo automático de zona restrita do Internet Explorer**  
  Essa configuração de política determina se os usuários são notificados para downloads de arquivo não iniciados pelo usuário. Independentemente dessa configuração, os usuários receberão caixas de diálogo de download de arquivo para downloads iniciados pelo usuário. Se você habilitar essa configuração, os usuários receberão uma caixa de diálogo de download de arquivo para tentativas de download automático. Se você desabilitar ou não definir essa configuração, os downloads de arquivos que não são iniciados pelo usuário serão bloqueados e os usuários verão a barra de notificação em vez da caixa de diálogo de download de arquivo. Os usuários podem, então, clicar na barra de notificação para permitir o prompt de download de arquivo.
  
  **Padrão**: desabilitado
  
- **Componentes dependentes de .NET Framework da zona da Internet do Internet Explorer**  
  Essa configuração de política permite que você gerencie se os componentes do .NET Framework não assinados com Authenticode poderão ser executados por meio do Internet Explorer. Esses componentes incluem controles gerenciados referenciados de uma marca de objeto e executáveis gerenciados referenciados por um link. Se você habilitar essa configuração de política, o Internet Explorer executará componentes gerenciados não assinados. Se você selecionar Solicitar na caixa suspensa, o Internet Explorer solicitará que o usuário determine se deve executar componentes gerenciados não assinados. Se você desabilitar essa configuração de política, o Internet Explorer não executará componentes gerenciados não assinados. Se você não configurar essa política, o Internet Explorer executará componentes gerenciados não assinados.
  
  **Padrão**: Desabilitar 
  
- **Permitir uso de controles ActiveX tdc apenas por domínios aprovados em zona da Internet do Internet Explorer**  
  Essa configuração de política controla se o usuário pode executar o controle ActiveX TDC nos sites. Se você habilitar essa configuração de política, o controle ActiveX TDC não será executado diretamente dos sites nessa zona. Se você desabilitar essa configuração de política, o controle ActiveX TDC será executado de todos os sites nessa zona.
  
  **Padrão**: habilitado 
  
- **Janelas iniciadas pelo script de zona restrita do Internet Explorer**  
  Essa configuração de política permite gerenciar as restrições em janelas pop-up iniciadas por script e janelas que incluem barras de título e status. Se você habilitar essa configuração de política, a segurança de Restrições do Windows não se aplicará a esta zona. A zona de segurança é executada sem a camada adicional de segurança fornecida por esse recurso. Se você desabilitar essa configuração de política, as possíveis ações prejudiciais contidas em janelas pop-up iniciadas por script e nas janelas que incluem barras de título e status não poderão ser executadas. Esse recurso de segurança do Internet Explorer está nesta zona conforme determinado pela configuração de controle de recurso de Restrições de Segurança do Windows em script para o processo. Se você não configurar essa política, as possíveis ações prejudiciais contidas em janelas pop-up iniciadas por script e nas janelas que incluem barras de título e status não poderão ser executadas. Esse recurso de segurança do Internet Explorer está nesta zona conforme determinado pela configuração de controle de recurso de Restrições de Segurança do Windows em script para o processo.
  
  **Padrão**: desabilitado 
  
- **Zona de Internet do Internet Explorer inclui o caminho local ao carregar arquivos para o servidor**  
  Essa configuração de política controla se as informações de caminho local são enviadas quando o usuário está carregando um arquivo por meio de um formulário HTML. Se as informações de caminho local forem enviadas, algumas informações poderão ser reveladas acidentalmente no servidor. Por exemplo, os arquivos enviados da área de trabalho do usuário podem conter o nome de usuário como parte do caminho. Se você habilitar essa configuração de política, as informações de caminho serão enviadas quando o usuário estiver carregando um arquivo por meio de um formulário HTML. Se você desabilitar essa configuração de política, as informações de caminho serão removidas quando o usuário estiver carregando um arquivo por meio de um formulário HTML. Se você não configurar essa política, o usuário poderá escolher se as informações de caminho são enviadas quando eles estão carregando um arquivo por meio de um formulário HTML. Por padrão, as informações de caminho são enviadas.
  
  **Padrão**: desabilitado 
  
- **Desabilitar processos do Internet Explorer no Modo Protegido Avançado**  
  Essa configuração de política determina se o Internet Explorer 11 usa processos de 64 bits (para maior segurança) ou processos de 32 bits (para maior compatibilidade) quando em execução no Modo Protegido Avançado em versões de 64 bits do Windows. Importante: algumas barras de ferramentas e controles ActiveX podem não estar disponíveis quando os processos de 64 bits são usados. Se você habilitar essa configuração de política, o Internet Explorer 11 usará os processos de guias de 64 bits durante a execução no Modo Protegido Avançado em versões de 64 bits do Windows. Se você desabilitar essa configuração de política, o Internet Explorer 11 usará os processos de guias de 32 bits durante a execução no Modo Protegido Avançado em versões de 64 bits do Windows. Se você não definir essa configuração de política, os usuários poderão ativar e desativar esse recurso usando as configurações do Internet Explorer. Este recurso está desativado por padrão.
  
  **Padrão**: habilitado 
  
- **Internet Explorer ignora erros de certificado**  
  Essa configuração de política impede o usuário de ignorar erros de certificado de protocolo SSL/TLS que interrompem a navegação (como "expirado", "revogado" ou erros de "incompatibilidade de nome") no Internet Explorer. Se você habilitar essa configuração de política, o usuário não poderá continuar a navegação. Se você desabilitar ou não configurar essa política, o usuário poderá optar por ignorar erros de certificado e continuar a navegação.
  
  **Padrão**: desabilitado 
  
- **Carregamento de arquivos XAML de zona de Internet do Internet Explorer**  
  Essa configuração de política permite que você gerencie o carregamento de arquivos de linguagem XAML. XAML é uma linguagem de marcação declarativa baseada em XML normalmente usada para criar gráficos e interfaces do usuário avançadas que aproveitam o Windows Presentation Foundation. Se você habilitar essa configuração de política e definir a caixa suspensa para Habilitar, os arquivos XAML são carregados automaticamente no Internet Explorer. O usuário não pode alterar esse comportamento. Se você definir a caixa suspensa para Solicitar, será solicitado que o usuário carregue arquivos XAML. Se você desabilitar essa configuração de política, os arquivos XAML não serão carregados no Internet Explorer. O usuário não pode alterar esse comportamento. Se você não configurar essa política, o usuário poderá decidir se deve carregar arquivos XAML dentro do Internet Explorer.
  
  **Padrão**: Desabilitar 
  
- **Prompt de download de arquivo automático de zona de Internet do Internet Explorer**  
  Essa configuração de política determina se os usuários são notificados para downloads de arquivo não iniciados pelo usuário. Independentemente dessa configuração, os usuários receberão caixas de diálogo de download de arquivo para downloads iniciados pelo usuário. Se você habilitar essa configuração, os usuários receberão uma caixa de diálogo de download de arquivo para tentativas de download automático. Se você desabilitar ou não definir essa configuração, os downloads de arquivos que não são iniciados pelo usuário serão bloqueados e os usuários verão a barra de notificação em vez da caixa de diálogo de download de arquivo. Os usuários podem, então, clicar na barra de notificação para permitir o prompt de download de arquivo.
  
  **Padrão**: habilitado  
  
- **Aviso de segurança de zona restrita do Internet Explorer para arquivos potencialmente não seguros**  
  Essa configuração de política controla se a mensagem "Abrir Arquivo – Aviso de Segurança" é exibida quando o usuário tenta abrir arquivos executáveis ou outros arquivos potencialmente não seguros (de um compartilhamento de arquivo da intranet usando o Explorador de Arquivos, por exemplo). Se você habilitar essa configuração de política e definir a caixa de lista suspensa para Habilitar, esses arquivos serão abertos sem um aviso de segurança. Se você definir a caixa de lista suspensa para Consultar, um aviso de segurança será exibido antes da abertura dos arquivos. Se você desabilitar essa configuração de política, esses arquivos não serão abertos. Se você não configurar essa política, o usuário poderá configurar como o computador manipula esses arquivos. Por padrão, esses arquivos são bloqueados na zona restrita, habilitados nas zonas da intranet e do computador local e definidos para consultar nas zonas da Internet e Confiável.
  
  **Padrão**: Desabilitar  
  
- **Filtro de script entre sites de zona de Internet do Internet Explorer**  
  Essa política controla se o filtro de XSS (criação de scripts entre sites) detectará e impedirá injeções de script entre sites em sites desta zona. Se você habilitar essa configuração de política, o filtro XSS será ativado para sites desta zona e tentará bloquear injeções de script entre sites. Se você desabilitar essa configuração de política, o filtro XSS será desativado para sites desta zona e o Internet Explorer permitirá injeções de script entre sites.
  
  **Padrão**: habilitado 
  
- **Fallback do Internet Explorer para SSL3**  
  Essa configuração de política permite bloquear um fallback inseguro para SSL 3.0. Quando essa política estiver habilitada, Internet Explorer tentará se conectar a sites usando o SSL 3.0 ou anterior quando ocorrer falha no TLS 1.0 ou posterior. É recomendável que você não permita fallback inseguro para evitar um ataque man-in-the-middle. Essa política não afeta quais protocolos de segurança estão habilitados. Se você desabilitar essa política, os padrões do sistema serão usados.
  
  **Default**: Sem sites 
  
- **SmartScreen da zona de Internet bloqueada do Internet Explorer**  
  Essa configuração de política controla se o filtro SmartScreen verifica páginas nesta zona quanto a conteúdo malicioso. Se você habilitar essa configuração de política, o filtro SmartScreen verificará páginas nesta zona quanto a conteúdo malicioso. Se você desabilitar essa configuração de política, o filtro SmartScreen não verificará páginas nesta zona quanto a conteúdo malicioso. Se você não configurar essa configuração de política, o usuário poderá escolher se o filtro SmartScreen verifica ou não páginas nesta zona quanto a conteúdo malicioso. Observação: no Internet Explorer 7, essa configuração de política controla se o filtro de Phishing examina as páginas desta zona quanto a conteúdo malicioso.
  
  **Padrão**: habilitado 
  
- **Inicializar aplicativos e arquivos em um iFrame na zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie se os aplicativos podem ser executados e os arquivos podem ser baixados de uma referência IFRAME no HTML das páginas nesta zona. Se você habilitar essa configuração de política, os usuários poderão executar aplicativos e baixar arquivos de IFRAMEs nas páginas dessa zona sem intervenção do usuário. Se você selecionar Consultar na caixa suspensa, os usuários serão consultados para escolher se desejam executar aplicativos e baixar arquivos de IFRAMEs nas páginas nesta zona. Se você desabilitar essa configuração de política, os usuários serão impedidos de executar aplicativos e baixar arquivos de IFRAMEs nas páginas nesta zona. Se você não configurar essa política, os usuários serão impedidos de executar aplicativos e baixar arquivos de IFRAMEs nas páginas nesta zona.
  
  **Padrão**: Desabilitar 
  
- **Ignorar avisos SmartScreen do Internet Explorer sobre arquivos incomuns**  
  Essa configuração de política determina se o usuário pode ignorar os avisos do Filtro SmartScreen. O Filtro SmartScreen avisa o usuário sobre os arquivos executáveis que os usuários do Internet Explorer não baixam comumente da Internet. Se você habilitar essa configuração de política, os avisos do Filtro SmartScreen bloquearão o usuário. Se você desabilitar ou não configurar essa política, o usuário poderá ignorar os avisos do Filtro SmartScreen.
  
  **Padrão**: desabilitado  
  
- **Bloqueador de pop-ups da zona de Internet do Internet Explorer**  
  Essa configuração de política permite que você gerencie se janelas pop-up indesejadas aparecem ou não. Janelas pop-up que são abertas quando o usuário final clica em um link não são bloqueadas. Se você habilitar essa configuração de política, a maioria das janelas pop-up indesejadas serão impedidas de aparecer. Se você desabilitar essa configuração de política, as janelas pop-up não serão impedidas de aparecer. Se você não configurar essa política, a maioria das janelas pop-up indesejadas serão impedidas de aparecer.
  
  **Padrão**: Habilitar  
  
- **Tratamento de MIME consistente de processos do Internet Explorer**  
  O Internet Explorer contém comportamentos binários dinâmicos: componentes que encapsulam funcionalidades específicas para os elementos HTML ao quais eles estão anexados. Essa configuração de política controla se a configuração de Restrição de Segurança de Comportamento Binário é impedida ou permitida. Se você habilitar essa configuração de política, os comportamentos binários serão impedidos para os processos do Explorador de Arquivos e do Internet Explorer. Se você desabilitar essa configuração de política, os comportamentos binários serão permitidos para os processos do Explorador de Arquivos e do Internet Explorer. Se você não configurar essa política, os comportamentos binários serão impedidos para os processos do Explorador de Arquivos e do Internet Explorer.
  
  **Padrão**: habilitado  
  
- **Permissões de Java da zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie permissões para miniaplicativos Java. Se habilitar essa configuração de política, você poderá escolher uma das opções a seguir da lista suspensa. Personalizado, para controlar as configurações de permissões individualmente. Segurança Baixa permite que os miniaplicativos executem todas as operações. A Segurança Média permite que aplicativos sejam executados na área restrita (uma área na memória fora da qual o programa não pode fazer chamadas), além de funcionalidades como o espaço transitório (uma área de armazenamento segura e protegida no computador cliente) e E/S de arquivo controlada pelo usuário. Segurança Alta permite que aplicativos sejam executados nas respectivas áreas restritas. Desabilite o Java para impedir a execução de todos os miniaplicativos. Se você desabilitar essa configuração de política, não será possível executar miniaplicativos Java. Se você não configurar essa política, os miniaplicativos Java serão desabilitados.
  
  **Padrão**: Desabilitar Java  
    
  
- **Controles ActiveX do Internet Explorer no modo protegido**  
  Esta configuração de política impede que os controles ActiveX sejam executados no Modo Protegido quando o Modo Protegido Avançado estiver habilitado. Quando um usuário tem instalado um controle ActiveX que não é compatível com o Modo Protegido Avançado e um site tenta carregar o controle, o Internet Explorer notifica o usuário e oferece a opção de executar o site no Modo Protegido regular. Esta configuração de política desabilita essa notificação e força todos os sites a serem executados no Modo Protegido Avançado. O Modo Protegido Avançado confere proteção adicional contra sites mal-intencionados, usando processos de 64 bits em versões de 64 bits do Windows. Para computadores que executam pelo menos o Windows 8 ou posterior, o Modo Protegido Avançado também limita os locais do Registro e do sistema de arquivos que o Internet Explorer pode ler. Quando o Modo Protegido Avançado está habilitado e um usuário encontra um site que tenta carregar um controle ActiveX incompatível com esse modo, o Internet Explorer notifica o usuário e oferece a opção de desabilitar o Modo Protegido Avançado para esse site específico. Se você habilitar essa configuração de política, o Internet Explorer não oferecerá ao usuário a opção de desabilitar o Modo Protegido Avançado. Todos os sites no Modo Protegido serão executados no Modo Protegido Avançado. Se você desabilitar ou não definir esta configuração de política, o Internet Explorer notificará os usuários e oferecerá a opção de executar sites com controles ActiveX incompatíveis no Modo Protegido regular.  
  
  **Padrão**: desabilitado  
  
- **Carregamento de arquivos XAML de zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie o carregamento de arquivos de linguagem XAML. XAML é uma linguagem de marcação declarativa baseada em XML normalmente usada para criar gráficos e interfaces do usuário avançadas que aproveitam o Windows Presentation Foundation. Se você habilitar essa configuração de política e definir a caixa suspensa para Habilitar, os arquivos XAML são carregados automaticamente no Internet Explorer. O usuário não pode alterar esse comportamento. Se você definir a caixa suspensa para Solicitar, será solicitado que o usuário carregue arquivos XAML. Se você desabilitar essa configuração de política, os arquivos XAML não serão carregados no Internet Explorer. O usuário não pode alterar esse comportamento. Se você não configurar essa política, o usuário poderá decidir se deve carregar arquivos XAML dentro do Internet Explorer.
  
  **Padrão**: Desabilitar  
  
- **Restrições de segurança de janela com scripts de processos do Internet Explorer**  
  O Internet Explorer permite que os scripts abram, redimensionem e reposicionem janelas de vários tipos programaticamente. O recurso de segurança de Restrições de Janela restringe janelas pop-up e proíbe que os scripts exibam janelas nas quais as barras de título e de status não são visíveis para o usuário ou ofuscam as barras de título e de status de outras janelas. Se você habilitar essa configuração de política, as janelas com script serão restritas para todos os processos. Se você desabilitar ou não configurar essa política, as janelas com script não serão restritas.
  
  **Padrão**: habilitado   
  
- **Zona restrita do Internet Explorer executa plug-ins e controles Active X**  
  Essa configuração de política permite que você gerencie se os plug-ins e controles ActiveX podem ser executados em páginas da zona especificada. Se você habilitar essa configuração de política, os plug-ins e controles poderão ser executados sem intervenção do usuário. Se você selecionou Consultar na caixa suspensa, será solicitado que os usuários escolham se desejam permitir a execução dos controles ou dos plug-ins. Se você desabilitar essa configuração de política, os controles e plug-ins terão a execução impedida. Se você não configurar essa política, os controles e plug-ins terão a execução impedida.
  
  **Padrão**: Desabilitar  
  
- **Controles ActiveX de script da zona restrita do Internet Explorer marcados como seguros para script**  
  Essa configuração de política permite que você gerencie se um controle ActiveX marcado como seguro para script pode interagir com um script. Se você habilitar essa configuração de política, a interação do script poderá ocorrer automaticamente sem intervenção do usuário. Se você selecionar Consultar na caixa suspensa, os usuários serão consultados para escolher se desejam permitir a interação do script. Se você desabilitar essa configuração de política, a interação do script será impedida de ocorrer. Se você não configurar essa política, a interação do script será impedida de ocorrer.
  
  **Padrão**: Desabilitar  
  
- **Opções de logon da zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie as configurações de opções de entrada. Se você habilitar essa configuração de política, poderá escolher entre as opções de entrada a seguir. 
  - *Anônimo* – Use a entrada anônima para desabilitar a autenticação HTTP e usar a conta convidado somente para o protocolo CIFS (Common Internet File System). 
  - *Prompt* – Use solicitar nome de usuário e senha para consultar os usuários para fornecimento de IDs de usuário e senhas. Depois que um usuário é consultado, esses valores poderão ser usados silenciosamente pelo restante da sessão. 
  - *Logon automático somente em zona de intranet* - use essa opção para consultar os usuários para fornecimento de IDs de usuário e senhas em outras zonas. Depois que um usuário é consultado, esses valores poderão ser usados silenciosamente pelo restante da sessão. 
  - *Entrada automática com o nome de usuário e senha atuais*- use essa opção para tentar entrar usando a Resposta de Desafio do Windows NT (também conhecido como autenticação NTLM). Se o servidor for compatível com a resposta de desafio do Windows NT, a entrada usará o nome de usuário de rede e a senha do usuário. Se o servidor não der suporte à Resposta de Desafio do Windows NT, o usuário será consultado para fornecer o nome de usuário e senha. 

  Se você desabilitar essa configuração de política, a entrada será configurada para *Entrada automática somente na zona da intranet*. Se você não configurar essa política, a entrada será definida como *Solicitar* nome de usuário e senha.
  
  **Padrão**: Anônimo  
  
- **Inicializar de zona confiável do Internet Explorer e criar script dos controles do ActiveX não marcados como seguro**  
  Essa configuração de política permite que você gerencie controles ActiveX não marcados como seguros. Se você habilitar essa configuração de política, os controles do ActiveX serão executados, carregados com parâmetros e terão o script gerado sem definir a segurança de objeto para scripts ou dados não confiáveis. Essa configuração não é recomendável, exceto para zonas seguras e administradas. Essa configuração faz com que controles seguros e inseguros sejam inicializados e tenham o script gerado, ignorando os controles de Script ActiveX marcados como seguros para a opção de script. Se você habilitar essa configuração de política e selecionar Solicitar na caixa suspensa, os usuários serão consultados sobre se desejam permitir que o controle seja carregado com parâmetros ou tenham o script gerado. Se você desabilitar essa configuração de política, os controles ActiveX que não puderem ser tornados seguros não serão carregados com parâmetros ou com script. Se você não configurar essa política, os usuários serão consultados sobre se desejam permitir que o controle seja carregado com parâmetros ou tenham o script gerado.
  
  **Padrão**: Desabilitar  
  
- **Verificação da revogação do certificado do servidor pelo Internet Explorer**  
  Essa configuração de política permite que você gerencie se o Internet Explorer verificará o status de revogação de certificados de servidores. Os certificados são revogados quando são comprometidos ou não são mais válidos e essa opção protege os usuários do envio de dados confidenciais para um site que pode ser fraudulento ou não seguro. Se você habilitar essa configuração de política, o Internet Explorer verificará se os certificados do servidor foram revogados. Se você desabilitar essa configuração de política, o Internet Explorer não verificará se os certificados do servidor foram revogados. Se você não configurar essa política, o Internet Explorer não verificará se os certificados do servidor foram revogados.
  
  **Padrão**: habilitado 
  
- **Sites com menos privilégios de zona da Internet do Internet Explorer**  
  Essa configuração de política permite que você gerencie se os sites em zonas com menos privilégios, como sites da restritos, podem navegar para essa zona. Se você habilitar essa configuração de política, os sites em zonas com menos privilégios podem abrir novas janelas ou navegar até esta zona. A zona de segurança será executada sem a camada de segurança adicional fornecida pelo recurso de segurança de Proteção contra Elevação de Zona. Se você selecionar Prompt na caixa suspensa, será emitido um aviso para o usuário indicando que uma navegação potencialmente arriscada está prestes a ocorrer. Se você desabilitar essa configuração de política, as navegações possivelmente prejudiciais são evitadas. O recurso de segurança do Internet Explorer está ativado nessa zona conforme definido pelo controle do recurso de Proteção contra Elevação de Zona. Se você não configurar essa política, os sites em zonas com menos privilégios poderão abrir novas janelas ou navegar até esta zona.
  
  **Padrão**: Desabilitar  
  
- **Downloads de arquivo da zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie se os downloads de arquivo são permitidos da zona. Essa opção é determinada pela zona da página com o link originando o download, não pela zona da qual o arquivo é entregue. Se você habilitar essa configuração de política, os arquivos poderão ser baixados da zona. Se você desabilitar essa configuração de política, o download dos arquivos da zona será impedido. Se você não configurar essa política, o download dos arquivos da zona será impedido.
  
  **Padrão**: Desabilitar  
  
- **Componentes dependentes de .NET Framework executados em zona da Internet do Internet Explorer assinados com Authenticode**  
  Essa configuração de política permite que você gerencie se os componentes do .NET Framework assinados com Authenticode poderão ser executados por meio do Internet Explorer. Esses componentes incluem controles gerenciados referenciados de uma marca de objeto e executáveis gerenciados referenciados por um link. Se você habilitar essa configuração de política, o Internet Explorer executará componentes gerenciados assinados. Se você selecionar Solicitar na caixa suspensa, o Internet Explorer solicitará que o usuário determine se deve executar componentes gerenciados assinados. Se você desabilitar essa configuração de política, o Internet Explorer não executará componentes gerenciados assinados. Se você não configurar essa política, o Internet Explorer não executará componentes gerenciados assinados.
  
  **Padrão**: Desabilitar  
  
- **Internet Explorer impede a instalação de controles ActiveX por usuário**  
  Essa configuração de política permite que você impeça a instalação de controles ActiveX por usuário. Se você habilitar essa configuração de política, os controles ActiveX não poderão instalados por usuário. Se você desabilitar ou não configurar essa política, os controles ActiveX poderão ser instalados por usuário.
  
  **Padrão**: habilitado  
  
- **Internet Explorer impede o gerenciamento do Filtro SmartScreen**  
  Essa configuração de política impede que o usuário gerencie o filtro SmartScreen, que avisa ao usuário se o site que ele visita é conhecido por tentativas fraudulentas de coletar informações pessoais por meio de "phishing" ou é conhecido por hospedar malware. Se você habilitar essa configuração de política, o usuário não será solicitado a ativar o Filtro SmartScreen. Todos os endereços de sites que não estão na lista de permissões do filtro são enviados automaticamente à Microsoft sem solicitar ao usuário. Se você desabilitar ou não configurar essa política, será solicitado ao usuário que ele decida se deseja ativar o Filtro SmartScreen durante a experiência de primeira execução.
  
  **Padrão**: Habilitar  
  
- **O Internet Explorer processa o recurso de segurança de detecção de MIME**  
  Essa configuração de política determina se a detecção de MIME do Internet Explorer impedirá a promoção de um arquivo de um determinado tipo para outro tipo de arquivo mais perigoso. Se você habilitar essa configuração de política, a detecção de MIME nunca promoverá um arquivo de um determinado tipo para outro tipo de arquivo mais perigoso. Se você desabilitar essa configuração de política, os processos do Internet Explorer permitirão que a detecção de MIME promovam um arquivo de um tipo para outro tipo de arquivo mais perigoso. Se você não configurar essa configuração de política, a detecção de MIME nunca promoverá um arquivo de um determinado tipo para outro tipo de arquivo mais perigoso.
  
  **Padrão**: habilitado  
  
- **Download de controles ActiveX assinados de zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie se os usuários poderão baixar controles ActiveX assinados de uma página na zona. Se você habilitar essa política, os usuários poderão baixar controles assinados sem intervenção do usuário. Se você selecionar Consultar na caixa suspensa, os usuários serão consultados se desejam baixar controles assinados por editores não confiáveis. Código assinado por editores confiáveis é baixado silenciosamente. Se você desabilitar a configuração de política, controles assinados não poderão ser baixados. Se você não configurar essa política, os usuários serão consultados se desejam baixar controles assinados por editores não confiáveis. Código assinado por editores confiáveis é baixado silenciosamente.
  
  **Padrão**: Desabilitar  
  
- **Preenchimento automático de Internet Explorer**  
  Esse recurso de preenchimento automático pode lembrar e sugerir os nomes de usuário e senhas em formulários. Se você habilitar essa configuração, o usuário não poderá alterar as opções "Nome de usuário e senhas em formulários" nem "Consultar para salvar senhas". O recurso Preenchimento Automático para nomes de usuário e senhas em formulários é ativado. Você precisa decidir se deseja selecionar "Consultar para salvar senhas". Se você desabilitar essa configuração, o usuário não poderá alterar as opções "Nome de usuário e senhas em formulários" nem "Consultar para salvar senhas". O recurso Preenchimento Automático para nomes de usuário e senhas em formulários é desativado. O usuário também não pode optar por receber solicitações para salvar senhas. Se você não definir essa configuração, o usuário terá a liberdade de ativar o Preenchimento automático para nome de usuário e senhas em formulários, bem como a opção solicitação para salvar senhas. Para exibir essa opção, os usuários abrem a caixa de diálogo Opções da Internet, clicam na guia Conteúdo e clicam no botão Configurações.
  
  **Padrão**: Desabilitar  
  
- **Permitir que o VBscript execute em zona de Internet do Internet Explorer**  
  Essa configuração de política permite que você decida se o VBScript pode ser executado em páginas em zonas específicas do Internet Explorer. As opções incluem: 
  - *Habilitar* – O VBScript é executado em páginas em zonas específicas, sem nenhuma interação. 
  - *Solicitar* – É solicitado aos funcionários que escolham se desejam permitir que o VBScript seja executado na zona. 
  - *Desabilitar* – O VBScript é impedido de ser executado na zona. Se você desabilitar ou não configurar essa política, o VBScript será executado sem nenhuma interação na zona especificada. 
  
  **Padrão**: Desabilitar  
  
- **Permitir uso de controles ActiveX TDC apenas por domínios aprovados em zona restrita do Internet Explorer**  
  Essa configuração de política controla se o usuário pode executar o controle ActiveX TDC nos sites. Se você habilitar essa configuração de política, o controle ActiveX TDC não será executado diretamente dos sites nessa zona. Se você desabilitar essa configuração de política, o controle ActiveX TDC será executado de todos os sites nessa zona.
  
  **Padrão**: habilitado  
  
- **A zona confiável do Internet Explorer não executa o antimalware com relação a controles ActiveX**  
  Essa configuração de política determina se o Internet Explorer executa programas antimalware em controles ActiveX para verificar se é seguro carregá-los nas páginas. Se você habilitar essa configuração de política, o Internet Explorer não verificará com seu programa antimalware se é seguro criar uma instância do controle ActiveX. Se você desabilitar essa configuração de política, o Internet Explorer sempre verificará com seu programa antimalware se é seguro criar uma instância do controle ActiveX. Se você não configurar essa política, o Internet Explorer sempre verificará com seu programa antimalware se é seguro criar uma instância do controle ActiveX. Os usuários podem ativar ou desativar esse comportamento usando as configurações de segurança do Internet Explorer.
  
  **Padrão**: desabilitado 
  
- **Permissões de Java de zona do computador local do Internet Explorer**  
  Essa configuração de política permite que você gerencie permissões para miniaplicativos Java. Se habilitar essa configuração de política, você poderá escolher uma das opções a seguir da lista suspensa. Personalizado, para controlar as configurações de permissões individualmente. Segurança Baixa permite que os miniaplicativos executem todas as operações. A Segurança Média permite que aplicativos sejam executados na área restrita (uma área na memória fora da qual o programa não pode fazer chamadas), além de funcionalidades como o espaço transitório (uma área de armazenamento segura e protegida no computador cliente) e E/S de arquivo controlada pelo usuário. Segurança Alta permite que aplicativos sejam executados nas respectivas áreas restritas. Desabilite o Java para impedir a execução de todos os miniaplicativos. Se você desabilitar essa configuração de política, não será possível executar miniaplicativos Java. Se você não configurar essa política, a permissão será definida como Segurança Média.
  
  **Padrão**: Desabilitar Java 
  
- **A zona de intranet do Internet Explorer não executa antimalware em controles do Active X** Essa configuração de política determina se o Internet Explorer executa programas antimalware em controles ActiveX para verificar se é seguro carregá-los nas páginas. Se você habilitar essa configuração de política, o Internet Explorer não verificará com seu programa antimalware se é seguro criar uma instância do controle ActiveX. Se você desabilitar essa configuração de política, o Internet Explorer sempre verificará com seu programa antimalware se é seguro criar uma instância do controle ActiveX. Se você não configurar essa política, o Internet Explorer não verificará com seu programa antimalware se é seguro criar uma instância do controle ActiveX. Os usuários podem ativar ou desativar esse comportamento usando as configurações de segurança do Internet Explorer.
  
  **Padrão**: desabilitado  

- **Miniscripts de zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie se o usuário pode executar miniscripts. Se você habilitar essa configuração de política, o usuário poderá executar miniscripts. Se você desabilitar essa configuração de política, o usuário não poderá executar miniscripts. Se você não configurar essa política, o usuário poderá habilitar ou desabilitar os miniscripts.
  
  **Padrão**: desabilitado  
  
- **Barra de notificação de processos do Internet Explorer**  
  Essa configuração de política permite que você gerencie se a barra de notificação é exibida para processos do Internet Explorer quando instalações de arquivo ou de código são restritas. Por padrão, a barra de notificação é exibida para processos do Internet Explorer. Se você habilitar essa configuração de política, a barra de notificação será exibida para os processos do Internet Explorer. Se você desabilitar essa configuração de política, a barra de notificação não será exibida para processos do Internet Explorer. Se você não configurar essa política, a barra de notificação não será exibida para processos do Internet Explorer.
  
  **Padrão**: habilitado  
  
- **Download de controles ActiveX assinados de zona de Internet do Internet Explorer**  
  Essa configuração de política permite que você gerencie se os usuários poderão baixar controles ActiveX assinados de uma página na zona. Se você habilitar essa política, os usuários poderão baixar controles assinados sem intervenção do usuário. Se você selecionar Consultar na caixa suspensa, os usuários serão consultados se desejam baixar controles assinados por editores não confiáveis. Código assinado por editores confiáveis é baixado silenciosamente. Se você desabilitar a configuração de política, controles assinados não poderão ser baixados. Se você não configurar essa política, os usuários serão consultados se desejam baixar controles assinados por editores não confiáveis. Código assinado por editores confiáveis é baixado silenciosamente.
  
  **Padrão**: Desabilitar  
  
- **SmartScreen de zona restrita do Internet Explorer**  
  Essa configuração de política controla se o filtro SmartScreen verifica páginas nesta zona quanto a conteúdo malicioso. Se você habilitar essa configuração de política, o filtro SmartScreen verificará páginas nesta zona quanto a conteúdo malicioso. Se você desabilitar essa configuração de política, o filtro SmartScreen não verificará páginas nesta zona quanto a conteúdo malicioso. Se você não configurar essa configuração de política, o usuário poderá escolher se o filtro SmartScreen verifica ou não páginas nesta zona quanto a conteúdo malicioso. Observação: no Internet Explorer 7, essa configuração de política controla se o filtro de Phishing examina as páginas desta zona quanto a conteúdo malicioso.
  
  **Padrão**: habilitado  
  
- **Remover botão Executar desta vez de controles ActiveX desatualizados no Internet Explorer**  
  Essa configuração de política permite impedir que os usuários vejam o botão "Executar desta vez" e executem controles ActiveX desatualizados específicos no Internet Explorer. Se você habilitar essa configuração de política, os usuários só verão o botão "Executar desta vez" na mensagem de aviso que aparece quando o Internet Explorer bloqueia um controle ActiveX desatualizado. Se você desabilitar ou não configurar essa política, os usuários verão o botão "Executar desta vez" na mensagem de aviso que aparece quando o Internet Explorer bloqueia um controle ActiveX desatualizado. Este botão permite que o usuário execute o controle ActiveX desatualizado uma vez. Para obter mais informações, veja "Controles ActiveX desatualizados" na biblioteca de TechNet do Internet Explorer.
  
  **Padrão**: habilitado 
  
- **Inicializar aplicativos e arquivos em um iframe na zona de Internet do Internet Explorer**  
  Essa configuração de política permite que você gerencie se os aplicativos podem ser executados e os arquivos podem ser baixados de uma referência IFRAME no HTML das páginas nesta zona. Se você habilitar essa configuração de política, os usuários poderão executar aplicativos e baixar arquivos de IFRAMEs nas páginas dessa zona sem intervenção do usuário. Se você selecionar Consultar na caixa suspensa, os usuários serão consultados para escolher se desejam executar aplicativos e baixar arquivos de IFRAMEs nas páginas nesta zona. Se você desabilitar essa configuração de política, os usuários serão impedidos de executar aplicativos e baixar arquivos de IFRAMEs nas páginas nesta zona. Se você não configurar essa política, os usuários serão consultados para escolher se desejam executar aplicativos e baixar arquivos de IFRAMEs nas páginas nesta zona
  
  **Padrão**: Desabilitar 
  
- **Janelas e quadros de navegação da zona restrita entre diferentes domínios do Internet Explorer**  
  Esta configuração de política permite que você defina opções sobre o arraste de conteúdo de um domínio para outro quando a origem e o destino estão em janelas diferentes. Se você habilitar esta configuração de política e clicar em Habilitar, os usuários poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem em janelas diferentes. Os usuários não podem alterar essa configuração. Se você habilitar esta configuração de política e clicar em Desabilitar, os usuários não poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem em janelas diferentes. Os usuários não podem alterar essa configuração. No Internet Explorer 10, se você desabilitar ou não definir esta configuração de política, os usuários não poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem em janelas diferentes. Os usuários poderão alterar essa configuração na caixa de diálogo Opções da Internet. No Internet Explorer 9 e em versões anteriores, se você desabilitar ou não definir esta configuração de política, os usuários poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem em janelas diferentes. Os usuários não podem alterar essa configuração.
  
  **Padrão**: Desabilitar  
  
- **SmartScreen de zona de Internet do Internet Explorer**  
  Essa configuração de política controla se o filtro SmartScreen verifica páginas nesta zona quanto a conteúdo malicioso. Se você habilitar essa configuração de política, o filtro SmartScreen verificará páginas nesta zona quanto a conteúdo malicioso. Se você desabilitar essa configuração de política, o filtro SmartScreen não verificará páginas nesta zona quanto a conteúdo malicioso. Se você não configurar essa configuração de política, o usuário poderá escolher se o filtro SmartScreen verifica ou não páginas nesta zona quanto a conteúdo malicioso. Observação: no Internet Explorer 7, essa configuração de política controla se o filtro de Phishing examina as páginas desta zona quanto a conteúdo malicioso.
  
  **Padrão**: habilitado  
  
- **Permissões de Java da zona confiável bloqueadas do Internet Explorer**  
  Essa configuração de política permite que você gerencie permissões para miniaplicativos Java. Se habilitar essa configuração de política, você poderá escolher uma das opções a seguir da lista suspensa. Personalizado, para controlar as configurações de permissões individualmente. Segurança Baixa permite que os miniaplicativos executem todas as operações. A Segurança Média permite que aplicativos sejam executados na área restrita (uma área na memória fora da qual o programa não pode fazer chamadas), além de funcionalidades como o espaço transitório (uma área de armazenamento segura e protegida no computador cliente) e E/S de arquivo controlada pelo usuário. Segurança Alta permite que aplicativos sejam executados nas respectivas áreas restritas. Desabilite o Java para impedir a execução de todos os miniaplicativos. Se você desabilitar essa configuração de política, não será possível executar miniaplicativos Java. Se você não configurar essa política, os miniaplicativos Java serão desabilitados.
  
  **Padrão**: Desabilitar Java 
  
- **Verificar assinaturas de programas baixados no Internet Explorer**  
  Essa configuração de política permite que você gerencie se o Internet Explorer verifica em busca de assinaturas digitais (que identificam o editor de software assinado e verificam que ele não foi modificado ou adulterado) nos computadores dos usuários antes de baixar programas executáveis. Se você habilitar essa configuração de política, o Internet Explorer verificará as assinaturas digitais de programas executáveis e exibirá suas identidades antes de baixá-los nos computadores dos usuários. Se você desabilitar essa configuração de política, o Internet Explorer não verificará as assinaturas digitais de programas executáveis nem exibirá suas identidades antes de baixá-los nos computadores dos usuários. Se você não configurar essa política, o Internet Explorer não verificará as assinaturas digitais de programas executáveis nem exibirá suas identidades antes de baixá-los nos computadores dos usuários.
  
  **Padrão**: habilitado  
  
- **Criação de scripts de controles do navegador da Web da zona restrita do Internet Explorer**  
  Essa configuração de política determina se uma página pode controlar, por meio de script, controles WebBrowser inseridos. Se você habilitar essa configuração de política, o acesso de script ao controle WebBrowser será permitido. Se você desabilitar essa configuração de política, o acesso de script ao controle WebBrowser não será permitido. Se você não configurar essa política, o usuário poderá habilitar ou desabilitar o acesso de script ao controle WebBrowser. Por padrão, o acesso de script ao controle WebBrowser é permitido somente no Computador Local e nas zonas da Intranet.
  
  **Padrão**: desabilitado  
  
- **Filtro de script entre sites de zona restrita do Internet Explorer**  
  Essa política controla se o filtro de XSS (criação de scripts entre sites) detectará e impedirá injeções de script entre sites em sites desta zona. Se você habilitar essa configuração de política, o filtro XSS será ativado para sites desta zona e tentará bloquear injeções de script entre sites. Se você desabilitar essa configuração de política, o filtro XSS será desativado para sites desta zona e o Internet Explorer permitirá injeções de script entre sites.
  
  **Padrão**: habilitado  
  
- **Comportamentos de script e binário em zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie os comportamentos de binários e de scripts dinâmicos: componentes que encapsulam funcionalidades específicas para elementos HTML para os quais eles foram anexados. Se você habilitar essa configuração de política, os comportamentos binários e de script ficarão disponíveis. Se você selecionar Aprovado pelo administrador na caixa suspensa, só os comportamentos listados nos Comportamentos aprovados pelo administrador na política de restrição de segurança de comportamentos binários ficarão disponíveis. Se você desabilitar essa configuração de política, os comportamentos binários e de script não ficarão disponíveis, a menos que os aplicativos tenham implementado um gerenciador de segurança personalizado. Se você não configurar essa política, os comportamentos binários e de script não ficarão disponíveis, a menos que os aplicativos tenham implementado um gerenciador de segurança personalizado.
  
  **Padrão**: Desabilitar  
  
- **Verificação de configurações de segurança do Internet Explorer**  
  Essa configuração de política desativa o recurso de verificação de configurações de segurança, que verifica as configurações de segurança do Internet Explorer para determinar quando as configurações colocam o Internet Explorer em risco. Se você habilitar essa configuração de política, o recurso será desativado. Se você desabilitar ou não configurar essa política, o recurso será ativado.
  
  **Padrão**: habilitado  
  
- **Aviso de segurança de zona da internet do Internet Explorer para arquivos potencialmente não seguros**  
  Essa configuração de política controla se a mensagem "Abrir Arquivo – Aviso de Segurança" é exibida quando o usuário tenta abrir arquivos executáveis ou outros arquivos potencialmente não seguros (de um compartilhamento de arquivo da intranet usando o Explorador de Arquivos, por exemplo). Se você habilitar essa configuração de política e definir a caixa de lista suspensa para Habilitar, esses arquivos serão abertos sem um aviso de segurança. Se você definir a caixa de lista suspensa para Consultar, um aviso de segurança será exibido antes da abertura dos arquivos. Se você desabilitar essa configuração de política, esses arquivos não serão abertos. Se você não configurar essa política, o usuário poderá configurar como o computador manipula esses arquivos. Por padrão, esses arquivos são bloqueados na zona restrita, habilitados nas zonas da intranet e do computador local e definidos para consultar nas zonas da Internet e Confiável.
  
  **Padrão**: Aviso  
  
- **Permissões de Java da zona de intranet do Internet Explorer**  
  Essa configuração de política permite que você gerencie permissões para miniaplicativos Java. Se habilitar essa configuração de política, você poderá escolher uma das opções a seguir da lista suspensa. Personalizado, para controlar as configurações de permissões individualmente. Segurança Baixa permite que os miniaplicativos executem todas as operações. A Segurança Média permite que aplicativos sejam executados na área restrita (uma área na memória fora da qual o programa não pode fazer chamadas), além de funcionalidades como o espaço transitório (uma área de armazenamento segura e protegida no computador cliente) e E/S de arquivo controlada pelo usuário. Segurança Alta permite que aplicativos sejam executados nas respectivas áreas restritas. Desabilite o Java para impedir a execução de todos os miniaplicativos. Se você desabilitar essa configuração de política, não será possível executar miniaplicativos Java. Se você não configurar essa política, a permissão será definida como Segurança Média.
  
  **Padrão**: Alta segurança 
  
- **Bloqueio de controles ActiveX desatualizados no Internet Explorer**  </br>
  Essa configuração de política determina se o Internet Explorer bloqueia controles ActiveX desatualizados específicos. Os controles ActiveX desatualizados nunca são bloqueados na zona da intranet. Se você habilitar essa configuração de política, o Internet Explorer deixará de bloquear controles ActiveX desatualizados. Se você desabilitar ou não definir essa configuração de política, o Internet Explorer continua a bloquear os controles ActiveX desatualizados específicos. Para obter mais informações, veja "Controles ActiveX desatualizados" na biblioteca de TechNet do Internet Explorer.
  
  **Padrão**: habilitado  
  
- **Bloqueador de pop-up da zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie se janelas pop-up indesejadas aparecem ou não. Janelas pop-up que são abertas quando o usuário final clica em um link não são bloqueadas. Se você habilitar essa configuração de política, a maioria das janelas pop-up indesejadas serão impedidas de aparecer. Se você desabilitar essa configuração de política, as janelas pop-up não serão impedidas de aparecer. Se você não configurar essa política, a maioria das janelas pop-up indesejadas serão impedidas de aparecer.
  
  **Padrão**: Habilitar  
  
- **Restrição de segurança de protocolo MK em processos do Internet Explorer**  
  A configuração de política de restrição de segurança de protocolo MK reduz a área de superfície de ataque, impedindo o protocolo MK. Recursos hospedados no protocolo MK falharão. Se você habilitar essa configuração de política, o protocolo MK será proibido para o Explorador de Arquivos e o Internet Explorer e os recursos hospedados no protocolo MK falharão. Se você desabilitar essa configuração de política, os aplicativos poderão usar a API do protocolo MK. Recursos hospedados no protocolo MK funcionarão para os processos do Explorador de Arquivos e do Internet Explorer. Se você não configurar essa política, o protocolo MK será proibido para o Explorador de Arquivos e o Internet Explorer e os recursos hospedados no protocolo MK falharão.
  
  **Padrão**: habilitado  
  
- **Permissões de Java da zona confiável do Internet Explorer**  </br>
  Essa configuração de política permite que você gerencie permissões para miniaplicativos Java. Se habilitar essa configuração de política, você poderá escolher uma das opções a seguir da lista suspensa. Personalizado, para controlar as configurações de permissões individualmente. Segurança Baixa permite que os miniaplicativos executem todas as operações. A Segurança Média permite que aplicativos sejam executados na área restrita (uma área na memória fora da qual o programa não pode fazer chamadas), além de funcionalidades como o espaço transitório (uma área de armazenamento segura e protegida no computador cliente) e E/S de arquivo controlada pelo usuário. Segurança Alta permite que aplicativos sejam executados nas respectivas áreas restritas. Desabilite o Java para impedir a execução de todos os miniaplicativos. Se você desabilitar essa configuração de política, não será possível executar miniaplicativos Java. Se você não configurar essa política, a permissão será definida como Segurança Baixa.
  
  **Padrão**: Alta segurança  
  
- **Criação de scripts de miniaplicativos Java da zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie se miniaplicativos são expostos a scripts dentro da zona. Se você habilitar essa configuração de política, os scripts poderão acessar miniaplicativos automaticamente sem intervenção do usuário. Se você selecionar Consultar na caixa suspensa, os usuários serão consultados para escolher se desejam permitir que os scripts acessem os miniaplicativos. Se você desabilitar essa configuração de política, os scripts serão impedidos de acessar os miniaplicativos. Se você não configurar essa política, os scripts serão impedidos de acessar os miniaplicativos.
  
  **Padrão**: Desabilitar  
  
- **Permissões de Java da zona restrita bloqueadas do Internet Explorer**  </br>
  Essa configuração de política permite que você gerencie permissões para miniaplicativos Java. Se habilitar essa configuração de política, você poderá escolher uma das opções a seguir da lista suspensa. Personalizado, para controlar as configurações de permissões individualmente. Segurança Baixa permite que os miniaplicativos executem todas as operações. A Segurança Média permite que aplicativos sejam executados na área restrita (uma área na memória fora da qual o programa não pode fazer chamadas), além de funcionalidades como o espaço transitório (uma área de armazenamento segura e protegida no computador cliente) e E/S de arquivo controlada pelo usuário. Segurança Alta permite que aplicativos sejam executados nas respectivas áreas restritas. Desabilite o Java para impedir a execução de todos os miniaplicativos. Se você desabilitar essa configuração de política, não será possível executar miniaplicativos Java. Se você não configurar essa política, os miniaplicativos Java serão desabilitados.
  
  **Padrão**: Desabilitar Java 
  
- **Permitir uso de controles ActiveX apenas por domínios aprovados em zona da Internet do Internet Explorer**  </br>
  Essa configuração de política controla se o usuário é solicitado a permitir que os controles ActiveX sejam executados em sites que não o site em que instalou o controle ActiveX. Se você habilitar essa configuração de política, o usuário será solicitado antes da execução de controles ActiveX de sites desta zona. O usuário pode optar por permitir a execução do site atual ou de todos os sites do controle. Se você desabilitar essa configuração de política, o usuário não verá o prompt do ActiveX por site e controles do ActiveX poderão ser executados de todos os sites desta zona.
  
  **Padrão**: habilitado  
  
- **Incluir todos os caminhos de rede no Internet Explorer**  
  Incluir todos os caminhos de rede no Internet Explorer
  
  **Padrão**: desabilitado 
  
- **Modo protegido da zona de Internet do Internet Explorer**  
  Essa configuração de política permite que você ative o modo protegido. O modo protegido ajuda a proteger o Internet Explorer contra vulnerabilidades exploradas reduzindo os locais em que o Internet Explorer pode gravar no Registro e no sistema de arquivos. Se você habilitar essa configuração de política, o Modo Protegido será ativado. O usuário não poderá desligar o modo protegido. Se você desabilitar essa configuração de política, o Modo Protegido será desativado. O usuário não poderá ativar o modo protegido. Se você não configurar essa política, o usuário poderá ligar ou desligar o modo protegido.
  
  **Padrão**: Habilitar 
  
- **Inicializar de zona de Internet do Internet Explorer e criar script dos controles do ActiveX não marcados como seguro**  
  Essa configuração de política permite que você gerencie controles ActiveX não marcados como seguros. Se você habilitar essa configuração de política, os controles do ActiveX serão executados, carregados com parâmetros e terão o script gerado sem definir a segurança de objeto para scripts ou dados não confiáveis. Essa configuração não é recomendável, exceto para zonas seguras e administradas. Essa configuração faz com que controles seguros e inseguros sejam inicializados e tenham o script gerado, ignorando os controles de Script ActiveX marcados como seguros para a opção de script. Se você habilitar essa configuração de política e selecionar Solicitar na caixa suspensa, os usuários serão consultados sobre se desejam permitir que o controle seja carregado com parâmetros ou tenham o script gerado. Se você desabilitar essa configuração de política, os controles ActiveX que não puderem ser tornados seguros não serão carregados com parâmetros ou com script. Se você não configurar essa política, os controles ActiveX que não puderem ser tornados seguros não serão carregados com parâmetros ou com script.
  
  **Padrão**: Desabilitar 
  
- **SmartScreen da zona restrita bloqueadas do Internet Explorer**  </br>
  Essa configuração de política controla se o filtro SmartScreen verifica páginas nesta zona quanto a conteúdo malicioso. Se você habilitar essa configuração de política, o filtro SmartScreen verificará páginas nesta zona quanto a conteúdo malicioso. Se você desabilitar essa configuração de política, o filtro SmartScreen não verificará páginas nesta zona quanto a conteúdo malicioso. Se você não configurar essa configuração de política, o usuário poderá escolher se o filtro SmartScreen verifica ou não páginas nesta zona quanto a conteúdo malicioso. Observação: no Internet Explorer 7, essa configuração de política controla se o filtro de Phishing examina as páginas desta zona quanto a conteúdo malicioso.
  
  **Padrão**: habilitado  
  
- **Detecção de falhas do Internet Explorer**  
  Essa configuração de política permite que você gerencie o recurso de detecção de falhas do gerenciamento de complementos. Se você habilitar essa configuração de política, uma falha no Internet Explorer exibirá o comportamento encontrado no Windows XP Professional Service Pack 1 e versões anteriores, ou seja, invocará o relatório de erros do Windows. Todas as configurações de política para o Relatório de Erros do Windows continuam a se aplicar. Se você desabilitar ou não configurar essa política, o recurso de detecção de falha para o gerenciamento de complementos ficará funcional.
  
  **Padrão**: desabilitado  
  
- **Permissões de Java da zona de Internet do Internet Explorer**  
  Essa configuração de política permite que você gerencie permissões para miniaplicativos Java. Se habilitar essa configuração de política, você poderá escolher uma das opções a seguir da lista suspensa. Personalizado, para controlar as configurações de permissões individualmente. Segurança Baixa permite que os miniaplicativos executem todas as operações. A Segurança Média permite que aplicativos sejam executados na área restrita (uma área na memória fora da qual o programa não pode fazer chamadas), além de funcionalidades como o espaço transitório (uma área de armazenamento segura e protegida no computador cliente) e E/S de arquivo controlada pelo usuário. Segurança Alta permite que aplicativos sejam executados nas respectivas áreas restritas. Desabilite o Java para impedir a execução de todos os miniaplicativos. Se você desabilitar essa configuração de política, não será possível executar miniaplicativos Java. Se você não configurar essa política, a permissão será definida como Segurança Alta.
  
  **Padrão**: Desabilitar Java  
  
- **Criação de scripts ativa de zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie se o código de script em páginas da zona deve ser executado. Se você habilitar essa configuração de política, o código de script em páginas da zona poderá ser executado automaticamente. Se você selecionar Consultar na caixa suspensa, os usuários serão consultados para escolher se desejam permitir a execução de código de script em páginas na zona. Se você desabilitar essa configuração de política, a execução de código de script em páginas da zona será impedida. Se você não configurar essa política, a execução de código de script em páginas da zona será impedida.
  
  **Padrão**: Desabilitar  
  
- **Opções de logon de zona de Internet do Internet Explorer**  
  Essa configuração de política permite que você gerencie as configurações de opções de entrada. Se você habilitar essa configuração de política, poderá escolher entre as opções de entrada a seguir. Logon anônimo para desabilitar a autenticação HTTP e usar a conta de convidado somente para o protocolo CIFS (Common Internet File System). Solicitar nome de usuário e senha para consultar os usuários para fornecimento de IDs de usuário e senhas. Depois que um usuário é consultado, esses valores podem ser usados silenciosamente pelo restante da sessão. Logon automático somente em zona de intranet para consultar os usuários para fornecimento de IDs de usuário e senhas em outras zonas. Depois que um usuário é consultado, esses valores poderão ser usados silenciosamente pelo restante da sessão. Entrada automática com o nome de usuário e senha atuais para tentar fazer logon usando a Resposta de Desafio do Windows NT (também conhecido como autenticação NTLM). Se o servidor for compatível com a resposta de desafio do Windows NT, a entrada usará o nome de usuário de rede e a senha do usuário para logon. Se o servidor não der suporte à Resposta de Desafio do Windows NT, o usuário será consultado para fornecer o nome de usuário e senha. Se você desabilitar essa configuração de política, a entrada será configurada para Logon automático somente na zona da intranet. Se você não definir essa configuração de política, a entrada será configurada para Entrada automática somente na zona da intranet.
  
  **Padrão**: Aviso  
  
- **Permitir que o VBscript execute em zona restrita do Internet Explorer**  </br>  
  Essa configuração de política permite que você gerencie se o VBScript pode ser executado em páginas da zona especificada no Internet Explorer. Se você selecionou Habilitar na caixa suspensa, o VBScript pode ser executado sem intervenção do usuário. Se você selecionou Consultar na caixa suspensa, será solicitado que os usuários escolham se desejam permitir a execução do VBScript. Se você selecionou Desabilitar na caixa suspensa, a execução do VBScript é impedida. Se você não configurar ou desabilitar essa configuração de política, a execução do VBScript será impedida.
  
  **Padrão**: Desabilitar  
  
- **Arrastar conteúdo de domínios diferentes entre janelas na zona de Internet do Internet Explorer**  
  Esta configuração de política permite que você defina opções sobre o arraste de conteúdo de um domínio para outro quando a origem e o destino estão em janelas diferentes. Se você habilitar esta configuração de política e clicar em Habilitar, os usuários poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem em janelas diferentes. Os usuários não podem alterar essa configuração. Se você habilitar esta configuração de política e clicar em Desabilitar, os usuários não poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem em janelas diferentes. Os usuários não podem alterar essa configuração. No Internet Explorer 10, se você desabilitar ou não definir esta configuração de política, os usuários não poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem em janelas diferentes. Os usuários poderão alterar essa configuração na caixa de diálogo Opções da Internet. No Internet Explorer 9 e em versões anteriores, se você desabilitar ou não definir esta configuração de política, os usuários poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem em janelas diferentes. Os usuários não podem alterar essa configuração.
  
  **Padrão**: desabilitado 
  
- **Inicializar de zona de intranet do Internet Explorer e criar script dos controles do ActiveX não marcados como seguro**  
  Essa configuração de política permite que você gerencie controles ActiveX não marcados como seguros. Se você habilitar essa configuração de política, os controles do ActiveX serão executados, carregados com parâmetros e terão o script gerado sem definir a segurança de objeto para scripts ou dados não confiáveis. Essa configuração não é recomendável, exceto para zonas seguras e administradas. Essa configuração faz com que controles seguros e inseguros sejam inicializados e tenham o script gerado, ignorando os controles de Script ActiveX marcados como seguros para a opção de script. Se você habilitar essa configuração de política e selecionar Solicitar na caixa suspensa, os usuários serão consultados sobre se desejam permitir que o controle seja carregado com parâmetros ou tenham o script gerado. Se você desabilitar essa configuração de política, os controles ActiveX que não puderem ser tornados seguros não serão carregados com parâmetros ou com script. Se você não configurar essa política, os controles ActiveX que não puderem ser tornados seguros não serão carregados com parâmetros ou com script.
  
  **Padrão**: Desabilitar 
  
- **Compartimentos de download do Internet Explorer**  
  Essa configuração de política impede que compartimentos (anexos de arquivo) sejam baixados de um feed para o computador do usuário. Se você habilitar essa configuração de política, o usuário não poderá definir o mecanismo de sincronização de feed para baixar um compartimento pela página de propriedades do feed. Um desenvolvedor não pode alterar a configuração de download por meio das APIs de feed. Se você desabilitar ou não configurar essa política, o usuário poderá definir o mecanismo de sincronização de feed para baixar um compartimento pela página de propriedades do feed. Um desenvolvedor pode alterar a configuração de download por meio das APIs de feed.
  
  **Padrão**: desabilitado  
  
- **Download de controles ActiveX não assinados de zona restrita do Internet Explorer**  </br>
  Essa configuração de política permite que você gerencie se os usuários poderão baixar controles ActiveX não assinados da zona. Esse código é potencialmente prejudicial, especialmente quando proveniente de uma zona não confiável. Se você habilitar essa configuração de política, os usuários poderão executar controles sem assinatura sem intervenção do usuário. Se você selecionar Solicitar na caixa suspensa, os usuários serão consultados para escolher se desejam permitir a execução do controle não assinado. Se você desabilitar essa configuração de política, os usuários não poderão executar controles não assinados. Se você não configurar essa política, os usuários não poderão executar controles não assinados.
  
  **Padrão**: Desabilitar  
  
- **Arrastar conteúdo de domínios diferentes em janelas na zona de Internet do Internet Explorer**  
  Essa configuração de política permite que você gerencie se os usuários poderão baixar controles ActiveX não assinados da zona. Esse código é potencialmente prejudicial, especialmente quando proveniente de uma zona não confiável. Se você habilitar essa configuração de política, os usuários poderão executar controles sem assinatura sem intervenção do usuário. Se você selecionar Solicitar na caixa suspensa, os usuários serão consultados para escolher se desejam permitir a execução do controle não assinado. Se você desabilitar essa configuração de política, os usuários não poderão executar controles não assinados. Se você não configurar essa política, os usuários não poderão executar controles não assinados.
  
  **Padrão**: desabilitado  
  
- **Os processos do Internet Explorer restringem a instalação de ActiveX**  </br>
  Essa configuração de política permite que aplicativos que hospedam o Controle de Navegador da Web bloqueiem a solicitação automática de instalação de controles ActiveX. Se você habilitar essa configuração de política, o Controle de Navegador da Web bloqueará a solicitação automática de instalação de controles ActiveX para todos os processos. Se você desabilitar ou não configurar essa política, o Controle de Navegador da Web não bloqueará a solicitação automática de instalação do controle ActiveX para todos os processos.
  
  **Padrão**: habilitado  
  
- **Miniscripts de zona da Internet do Internet Explorer** Essa configuração de política permite que você gerencie se o usuário pode executar miniscripts. Se você habilitar essa configuração de política, o usuário poderá executar miniscripts. Se você desabilitar essa configuração de política, o usuário não poderá executar miniscripts. Se você não configurar essa política, o usuário poderá habilitar ou desabilitar os miniscripts.
  
  **Padrão**: Desabilitar  
  
- **Arrastar e soltar ou copiar e colar arquivos na zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie se os usuários podem arrastar ou copiar/colar arquivos de uma origem dentro da zona. Se você habilitar essa configuração de política, os usuários poderão arrastar ou copiar/colar arquivos dessa zona automaticamente. Se você selecionar Solicitar na caixa suspensa, os usuários serão consultados para escolher se desejam arrastar ou copiar arquivos dessa zona. Se você desabilitar essa configuração de política, os usuários são impedidos de arrastar ou copiar/colar arquivos dessa zona. Se você não configurar essa política, os usuários serão consultados para escolher se desejam arrastar ou copiar arquivos dessa zona.
  
  **Padrão**: Desabilitar  
  
- **Software do Internet Explorer quando a assinatura é inválida** </br>
  Essa configuração de política permite que você gerencie se softwares, assim como controles ActiveX e downloads de arquivos, podem ser instalados ou executados pelo usuário, mesmo que a assinatura seja inválida. Uma assinatura inválida pode indicar que alguém alterou o arquivo. Se você habilitar essa configuração de política, será solicitado aos usuários que confirmem se desejam instalar ou executar arquivos com uma assinatura inválida. Se você desabilitar essa configuração de política, os usuários não poderão instalar nem executar arquivos com uma assinatura inválida. Se você não configurar essa política, os usuários poderão escolher se desejam instalar ou executar arquivos com uma assinatura inválida.
  
  **Padrão**: desabilitado  
  
- **Copiar e colar zona restrita do Internet Explorer por meio de script** </br> Essa configuração de política permite que você gerencie se os scripts podem realizar uma operação de área de transferência (por exemplo, cortar, copiar e colar) em uma região especificada. Se você habilitar essa configuração de política, um script poderá realizar uma operação de área de transferência. Se você selecionar Solicitar na caixa suspensa, os usuários serão consultados a realizar operações de área de transferência. Se você desabilitar essa configuração de política, um script não poderá realizar uma operação de área de transferência. Se você não configurar essa política, um script não poderá realizar uma operação de área de transferência.
  
  **Padrão**: Desabilitar  
  
- **Arrastar conteúdo de domínios diferentes entre janelas na zona restrita do Internet Explorer**  
  Esta configuração de política permite que você defina opções sobre o arraste de conteúdo de um domínio para outro quando a origem e o destino estão em janelas diferentes. Se você habilitar esta configuração de política e clicar em Habilitar, os usuários poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem em janelas diferentes. Os usuários não podem alterar essa configuração. Se você habilitar esta configuração de política e clicar em Desabilitar, os usuários não poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem em janelas diferentes. Os usuários não podem alterar essa configuração. No Internet Explorer 10, se você desabilitar ou não definir esta configuração de política, os usuários não poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem em janelas diferentes. Os usuários poderão alterar essa configuração na caixa de diálogo Opções da Internet. No Internet Explorer 9 e em versões anteriores, se você desabilitar ou não definir esta configuração de política, os usuários poderão arrastar conteúdo de um domínio para outro quando a origem e o destino estiverem em janelas diferentes. Os usuários não podem alterar essa configuração.  <br><br>
  **Padrão**: desabilitado  
  
- **Adição de sites por usuários do Internet Explorer**  
  Impede que os usuários adicionem ou removam sites das zonas de segurança. Uma zona de segurança é um grupo de sites com o mesmo nível de segurança. Se você habilitar essa política, as configurações de gerenciamento do site para as zonas de segurança serão desabilitadas. (Para ver as configurações de gerenciamento do site para zonas de segurança, na caixa de diálogo Opções da Internet, clique na guia Segurança e no botão Sites.) Se você desabilitar essa política ou não a configurar, os usuários poderão adicionar sites a zonas de Sites Confiáveis e Sites Restritos ou removê-los delas e alterar as configurações para a zona da Intranet Local. Essa política impede que os usuários alterem as configurações de gerenciamento de sites para zonas de segurança estabelecidas pelo administrador. Observação: a política "Desabilitar a página Segurança" (localizada em \Configuração do Usuário\Modelos Administrativos\Componentes do Windows\Internet Explorer\Painel de Controle da Internet), que remove a guia Segurança da interface, tem precedência em relação a essa política. Se ela for habilitada, essa política será ignorada. Além disso, consulte a política “Zonas de segurança: use apenas as configurações do computador”.
  
  **Padrão**: desabilitado  
  
- **Janelas iniciadas pelo script de zona de Internet do Internet Explorer**  
  Essa configuração de política permite gerenciar as restrições em janelas pop-up iniciadas por script e janelas que incluem barras de título e status. Se você habilitar essa configuração de política, a segurança de Restrições do Windows não se aplicará a esta zona. A zona de segurança é executada sem a camada adicional de segurança fornecida por esse recurso. Se você desabilitar essa configuração de política, as possíveis ações prejudiciais contidas em janelas pop-up iniciadas por script e nas janelas que incluem barras de título e status não poderão ser executadas. Esse recurso de segurança do Internet Explorer está nesta zona conforme determinado pela configuração de controle de recurso de Restrições de Segurança do Windows em script para o processo. Se você não configurar essa política, as possíveis ações prejudiciais contidas em janelas pop-up iniciadas por script e nas janelas que incluem barras de título e status não poderão ser executadas. Esse recurso de segurança do Internet Explorer está nesta zona conforme determinado pela configuração de controle de recurso de Restrições de Segurança do Windows em script para o processo.
  
  **Padrão**: desabilitado  
  
- **Zonas de segurança do Internet Explorer usam apenas as configurações de computador**  
  Aplica informações da zona de segurança a todos os usuários do mesmo computador. Uma zona de segurança é um grupo de sites com o mesmo nível de segurança. Se você habilitar essa política, as alterações feitas pelo usuário a uma zona de segurança se aplicarão a todos os usuários desse computador. Se você desabilitar essa política ou não a configurar, os usuários do mesmo computador poderão estabelecer suas próprias configurações de zona de segurança. Use essa política para garantir que as configurações de zona de segurança sejam aplicadas uniformemente ao mesmo computador e não variem de um usuário para outro. Além disso, consulte a política "Zonas de segurança: Não permitir que os usuários alterem as políticas".
  
  **Padrão**: habilitado  
  
- **Permissões de Java da zona do computador local bloqueadas do Internet Explorer**  
  Essa configuração de política permite que você gerencie permissões para miniaplicativos Java. Se habilitar essa configuração de política, você poderá escolher uma das opções a seguir da lista suspensa. Personalizado, para controlar as configurações de permissões individualmente. Segurança Baixa permite que os miniaplicativos executem todas as operações. A Segurança Média permite que aplicativos sejam executados na área restrita (uma área na memória fora da qual o programa não pode fazer chamadas), além de funcionalidades como o espaço transitório (uma área de armazenamento segura e protegida no computador cliente) e E/S de arquivo controlada pelo usuário. Segurança Alta permite que aplicativos sejam executados nas respectivas áreas restritas. Desabilite o Java para impedir a execução de todos os miniaplicativos. Se você desabilitar essa configuração de política, não será possível executar miniaplicativos Java. Se você não configurar essa política, os miniaplicativos Java serão desabilitados
  
  **Padrão**: Desabilitar Java 
  
- **Não executar antimalware nos controles Active X em zona restrita do Internet Explorer**  </br>
  Essa configuração de política determina se o Internet Explorer executa programas antimalware em controles ActiveX para verificar se é seguro carregá-los nas páginas. Se você habilitar essa configuração de política, o Internet Explorer não verificará com seu programa antimalware se é seguro criar uma instância do controle ActiveX. Se você desabilitar essa configuração de política, o Internet Explorer sempre verificará com seu programa antimalware se é seguro criar uma instância do controle ActiveX. Se você não configurar essa política, o Internet Explorer sempre verificará com seu programa antimalware se é seguro criar uma instância do controle ActiveX. Os usuários podem ativar ou desativar esse comportamento usando as configurações de segurança do Internet Explorer.
  
  **Padrão**: desabilitado  
  
- **Componentes dependentes de .NET Framework executados em zona restrita do Internet Explorer assinados com authenticode**  
  Essa configuração de política permite que você gerencie se os componentes do .NET Framework assinados com Authenticode poderão ser executados por meio do Internet Explorer. Esses componentes incluem controles gerenciados referenciados de uma marca de objeto e executáveis gerenciados referenciados por um link. Se você habilitar essa configuração de política, o Internet Explorer executará componentes gerenciados assinados. Se você selecionar Solicitar na caixa suspensa, o Internet Explorer solicitará que o usuário determine se deve executar componentes gerenciados assinados. Se você desabilitar essa configuração de política, o Internet Explorer não executará componentes gerenciados assinados. Se você não configurar essa política, o Internet Explorer não executará componentes gerenciados assinados.
  
  **Padrão**: Desabilitar  
  
- **Acesso de zona restrita a fontes de dados do Internet Explorer**  
  Essa configuração de política permite que você gerencie se o Internet Explorer pode acessar dados de outra zona de segurança usando o MSXML (Microsoft XML Parser) ou ADO (ActiveX Data Objects). Se você habilitar essa configuração de política, os usuários poderão carregar uma página na zona que use MSXML ou ADO para acessar dados de outro site na zona. Se você selecionar Solicitar na caixa suspensa, os usuários serão consultados para escolher se desejam permitir que uma página seja carregada na zona que usa MSXML ou ADO para acessar dados de outro site na zona. Se você desabilitar essa configuração de política, os usuários não poderão carregar uma página na zona que use MSXML ou ADO para acessar dados de outro site na zona. Se você não configurar essa política, os usuários não poderão carregar uma página na zona que use MSXML ou ADO para acessar dados de outro site na zona.
  
  **Padrão**: Desabilitar 
  
- **A zona de Internet do Internet Explorer não executa antimalware com relação a controles ActiveX**  </br>
  Essa configuração de política determina se o Internet Explorer executa programas antimalware em controles ActiveX para verificar se é seguro carregá-los nas páginas. Se você habilitar essa configuração de política, o Internet Explorer não verificará com seu programa antimalware se é seguro criar uma instância do controle ActiveX. Se você desabilitar essa configuração de política, o Internet Explorer sempre verificará com seu programa antimalware se é seguro criar uma instância do controle ActiveX. Se você não configurar essa política, o Internet Explorer sempre verificará com seu programa antimalware se é seguro criar uma instância do controle ActiveX. Os usuários podem ativar ou desativar esse comportamento usando as configurações de segurança do Internet Explorer.
  
  **Padrão**: desabilitado  
  
- **Copiar e colar zona da Internet do Internet Explorer por meio de script** </br> Essa configuração de política permite que você gerencie se os scripts podem realizar uma operação de área de transferência (por exemplo, cortar, copiar e colar) em uma região especificada. Se você habilitar essa configuração de política, um script poderá realizar uma operação de área de transferência. Se você selecionar Solicitar na caixa suspensa, os usuários serão consultados a realizar operações de área de transferência. Se você desabilitar essa configuração de política, um script não poderá realizar uma operação de área de transferência. Se você não configurar essa política, um script poderá realizar uma operação de área de transferência.
  
  **Padrão**: Desabilitar  
  
- **Internet Explorer usa o serviço do instalador do ActiveX**  </br>
  Essa configuração de política permite que você especifique como os controles ActiveX são instalados. Se você habilitar essa configuração de política, os controles ActiveX serão instalados somente se o Serviço do Instalador do ActiveX estiver presente e tiver sido configurado para permitir a instalação de controles ActiveX. Se você desabilitar ou não definir essa configuração de política, os controles ActiveX, incluindo controles de usuário individual, serão instalados por meio do processo de instalação padrão.
  
  **Padrão**: habilitado  
  
- **Proteção de processos do Internet Explorer contra elevação de zona**  
  O Internet Explorer impõe restrições a cada página da Web aberta. As restrições variam de acordo com o local da página da Web (Internet, Intranet, zona do Computador Local e assim por diante). Por exemplo, páginas da Web no computador local têm as menores restrições de segurança e estão localizadas na zona de Computador Local, o que torna a zona de segurança do Computador Local o principal alvo para usuários mal-intencionados. Se você habilitar essa configuração de política, qualquer zona poderá ser protegida contra elevação de zona para todos os processos. Se você desabilitar ou não configurar essa política, outros processos além do Internet Explorer ou aqueles listados na lista de processos não receberão essa proteção.
  
  **Padrão**: habilitado  
  
- **Baixar controles do ActiveX não assinados da zona de Internet do Internet Explorer**  </br>
  Essa configuração de política permite que você gerencie se os usuários poderão baixar controles ActiveX não assinados da zona. Esse código é potencialmente prejudicial, especialmente quando proveniente de uma zona não confiável. Se você habilitar essa configuração de política, os usuários poderão executar controles sem assinatura sem intervenção do usuário. Se você selecionar Solicitar na caixa suspensa, os usuários serão consultados para escolher se desejam permitir a execução do controle não assinado. Se você desabilitar essa configuração de política, os usuários não poderão executar controles não assinados. Se você não configurar essa política, os usuários não poderão executar controles não assinados.
  
  **Padrão**: Desabilitar  
  
- **Janelas e quadros de navegação da zona da Internet entre diferentes domínios do Internet Explorer**  </br>
  Essa configuração de política permite que você gerencie a abertura de janelas e quadros para acesso de aplicativos entre diferentes domínios. Se você habilitar essa configuração de política, os usuários poderão abrir janelas e quadros de outros domínios e acessar aplicativos de outros domínios. Se você selecionar Solicitar na caixa suspensa, os usuários serão consultados sobre se desejam permitir que janelas e quadros acessem aplicativos de outros domínios. Se você desabilitar essa configuração de política, os usuários não poderão abrir janelas e quadros para acessar aplicativos de domínios diferentes. Se você não configurar essa política, os usuários poderão abrir janelas e quadros de outros domínios e acessar aplicativos de outros domínios.
  
  **Padrão**: Desabilitar  
  
- **Atualizações da zona da Internet à barra de status por meio de script do Internet Explorer**  
  Essa configuração de política permite que você gerencie se um script pode atualizar a barra de status dentro da zona. Se você habilitar essa configuração de política, os scripts poderão atualizar a barra de status. Se você desabilitar ou não configurar essa política, o script não terá permissão para atualizar a barra de status.
  
  **Padrão**: desabilitado  
  
- **Zona restrita do Internet Explorer inclui o caminho local ao carregar arquivos para o servidor**  </br> Essa configuração de política controla se as informações de caminho local são enviadas quando o usuário está carregando um arquivo por meio de um formulário HTML. Se as informações de caminho local forem enviadas, algumas informações poderão ser reveladas acidentalmente no servidor. Por exemplo, os arquivos enviados da área de trabalho do usuário podem conter o nome de usuário como parte do caminho. Se você habilitar essa configuração de política, as informações de caminho serão enviadas quando o usuário estiver carregando um arquivo por meio de um formulário HTML. Se você desabilitar essa configuração de política, as informações de caminho serão removidas quando o usuário estiver carregando um arquivo por meio de um formulário HTML. Se você não configurar essa política, o usuário poderá escolher se as informações de caminho são enviadas quando ele estão carregando um arquivo por meio de um formulário HTML. Por padrão, as informações de caminho são enviadas.
  
  **Padrão**: desabilitado  
  
- **Os processos do Internet Explorer restringem o download de arquivo**  </br> Essa configuração de política permite que aplicativos que hospedam o Controle de Navegador da Web bloqueiem a solicitação automática de downloads de arquivo não iniciados pelo usuário. Se você habilitar essa configuração de política, o controle do navegador da Web bloqueará a solicitação automática de downloads de arquivo não iniciados pelo usuário para todos os processos. Se você desabilitar essa configuração de política, o controle do navegador da Web não bloqueará a solicitação automática de downloads de arquivo não iniciados pelo usuário para todos os processos.
  
  **Padrão**: habilitado  
  
- **Permitir uso de controles Active X apenas por domínios aprovados em zona restrita do Internet Explorer**  </br>
  Essa configuração de política controla se o usuário é solicitado a permitir que os controles ActiveX sejam executados em sites que não o site em que instalou o controle ActiveX. Se você habilitar essa configuração de política, o usuário será solicitado antes da execução de controles ActiveX de sites desta zona. O usuário pode optar por permitir a execução do site atual ou de todos os sites do controle. Se você desabilitar essa configuração de política, o usuário não verá o prompt do ActiveX por site e controles do ActiveX poderão ser executados de todos os sites desta zona.
  
  **Padrão**: habilitado  
  
- **Inicializar de zona restrita do Internet Explorer e criar script dos controles do ActiveX não marcados como seguro**  
  Essa configuração de política permite que você gerencie controles ActiveX não marcados como seguros. Se você habilitar essa configuração de política, os controles do ActiveX serão executados, carregados com parâmetros e terão o script gerado sem definir a segurança de objeto para scripts ou dados não confiáveis. Essa configuração não é recomendável, exceto para zonas seguras e administradas. Essa configuração faz com que controles seguros e inseguros sejam inicializados e tenham o script gerado, ignorando os controles de Script ActiveX marcados como seguros para a opção de script. Se você habilitar essa configuração de política e selecionar Solicitar na caixa suspensa, os usuários serão consultados sobre se desejam permitir que o controle seja carregado com parâmetros ou tenham o script gerado. Se você desabilitar essa configuração de política, os controles ActiveX que não puderem ser tornados seguros não serão carregados com parâmetros ou com script. Se você não configurar essa política, os controles ActiveX que não puderem ser tornados seguros não serão carregados com parâmetros ou com script.
  
  **Padrão**: Desabilitar  
  
- **Alteração de políticas por usuários do Internet Explorer**  
    Impede que usuários alterem as configurações de zona de segurança. Uma zona de segurança é um grupo de sites com o mesmo nível de segurança. Se você habilitar essa política, o botão Nível Personalizado e o controle deslizante do nível de segurança na guia Segurança na caixa de diálogo Opções da Internet serão desabilitados. Se você desabilitar essa política ou não a configurar, os usuários poderão alterar as configurações para zonas de segurança. Essa política impede que os usuários alterem as configurações de zona de segurança estabelecidas pelo administrador. Observação: a política "Desabilitar a página Segurança" (localizada em \Configuração do Usuário\Modelos Administrativos\Componentes do Windows\Internet Explorer\Painel de Controle da Internet), que remove a guia Segurança do Internet Explorer no Painel de Controle, tem precedência em relação a essa política. Se ela for habilitada, essa política será ignorada. Além disso, consulte a política “Zonas de segurança: use apenas as configurações do computador”.
    
  **Padrão**: desabilitado  
  
- **Modo protegido da zona restrita do Internet Explorer**  
  Essa configuração de política permite que você ative o modo protegido. O modo protegido ajuda a proteger o Internet Explorer contra vulnerabilidades exploradas reduzindo os locais em que o Internet Explorer pode gravar no Registro e no sistema de arquivos. Se você habilitar essa configuração de política, o Modo Protegido será ativado. O usuário não poderá desligar o modo protegido. Se você desabilitar essa configuração de política, o Modo Protegido será desativado. O usuário não poderá ativar o modo protegido. Se você não configurar essa política, o usuário poderá ligar ou desligar o modo protegido.
  
  **Padrão**: Habilitar  
  
- **Persistência de dados de usuário de zona da Internet do Internet Explorer**  
  Essa configuração de política permite que você gerencie a preservação de informações no histórico do navegador, nos favoritos, em um repositório de XML ou diretamente em uma página da Web salva em disco. Quando um usuário retorna a uma página persistente, o estado da página pode ser restaurado se essa configuração de política está configurada adequadamente. Se você habilitar essa configuração de política, os usuários poderão preservar as informações no histórico do navegador, nos favoritos, em um repositório de XML ou diretamente em uma página da Web salva em disco. Se você desabilitar essa configuração de política, os usuários não poderão preservar as informações no histórico do navegador, nos favoritos, em um repositório de XML ou diretamente em uma página da Web salva em disco. Se você não configurar essa política, os usuários poderão preservar as informações no histórico do navegador, nos favoritos, em um repositório de XML ou diretamente em uma página da Web salva em disco.
  
  **Padrão**: desabilitado  
  
- **O script de zona da internet do Internet Explorer de controles do navegador da Web**  
 
  Essa configuração de política determina se uma página pode controlar, por meio de script, controles WebBrowser inseridos. Se você habilitar essa configuração de política, o acesso de script ao controle WebBrowser será permitido. Se você desabilitar essa configuração de política, o acesso de script ao controle WebBrowser não será permitido. Se você não configurar essa política, o usuário poderá habilitar ou desabilitar o acesso de script ao controle WebBrowser. Por padrão, o acesso de script ao controle WebBrowser é permitido somente no Computador Local e nas zonas da Intranet.
  
  **Padrão**: desabilitado  
  
- **Persistência de dados de usuário da zona restrita do Internet Explorer**  
    Essa configuração de política permite que você gerencie a preservação de informações no histórico do navegador, nos favoritos, em um repositório de XML ou diretamente em uma página da Web salva em disco. Quando um usuário retorna a uma página persistente, o estado da página pode ser restaurado se essa configuração de política está configurada adequadamente. Se você habilitar essa configuração de política, os usuários poderão preservar as informações no histórico do navegador, nos favoritos, em um repositório de XML ou diretamente em uma página da Web salva em disco. Se você desabilitar essa configuração de política, os usuários não poderão preservar as informações no histórico do navegador, nos favoritos, em um repositório de XML ou diretamente em uma página da Web salva em disco. Se você não configurar essa política, os usuários não poderão preservar as informações no histórico do navegador, nos favoritos, em um repositório de XML ou diretamente em uma página da Web salva em disco.  
  
  **Padrão**: desabilitado  
  
- **Permissões Java da zona de intranet bloqueadas do Internet Explorer**  
  Essa configuração de política permite que você gerencie permissões para miniaplicativos Java. Se habilitar essa configuração de política, você poderá escolher uma das opções a seguir da lista suspensa. Personalizado, para controlar as configurações de permissões individualmente. Segurança Baixa permite que os miniaplicativos executem todas as operações. A Segurança Média permite que aplicativos sejam executados na área restrita (uma área na memória fora da qual o programa não pode fazer chamadas), além de funcionalidades como o espaço transitório (uma área de armazenamento segura e protegida no computador cliente) e E/S de arquivo controlada pelo usuário. Segurança Alta permite que aplicativos sejam executados nas respectivas áreas restritas. Desabilite o Java para impedir a execução de todos os miniaplicativos. Se você desabilitar essa configuração de política, não será possível executar miniaplicativos Java. Se você não configurar essa política, os miniaplicativos Java serão desabilitados.
  
  **Padrão**: Desabilitar Java  
  
- **Modo protegido aprimorado do Internet Explorer**  
  O Modo Protegido Avançado confere proteção adicional contra sites mal-intencionados, usando processos de 64 bits em versões de 64 bits do Windows. Para computadores que executam pelo menos o Windows 8 ou posterior, o Modo Protegido Avançado também limita os locais do Registro e do sistema de arquivos que o Internet Explorer pode ler. Se você habilitar essa configuração de política, o Modo Protegido Avançado será ativado. Qualquer zona em que o Modo Protegido esteja habilitado usará o Modo Protegido Avançado. Os usuários não poderão desabilitar o Modo Protegido Avançado. Se você desabilitar essa configuração de política, o Modo Protegido Avançado será desativado. Qualquer zona em que o Modo Protegido esteja habilitado usará a versão do Modo Protegido introduzida no Internet Explorer 7 para Windows Vista. Se você não configurar essa política, os usuários poderão ligar ou desligar o Modo Protegido Avançado na guia Avançado da caixa de diálogo Opções da Internet.
  
  **Padrão**: habilitado  
  
- **Ignorar avisos SmartScreen do Internet Explorer**  
  Essa configuração de política determina se o usuário pode ignorar os avisos do Filtro SmartScreen. O Filtro SmartScreen avisa o usuário sobre os arquivos executáveis que os usuários do Internet Explorer não baixam comumente da Internet. Se você habilitar essa configuração de política, os avisos do Filtro SmartScreen bloquearão o usuário. Se você desabilitar ou não configurar essa política, o usuário poderá ignorar os avisos do Filtro SmartScreen.
  
  **Padrão**: desabilitado  
  
- **Meta-atualização de zona restrita do Internet Explorer**  
  Essa configuração de política permite que você gerencie se o navegador do usuário poderá ser redirecionado para outra página da Web se o autor da página da Web usar a opção Meta-Atualização (tag) para redirecionar os navegadores para outra página da Web. Se você habilitar essa configuração de política, o navegador do usuário que carrega uma página contendo uma opção Meta-Atualização ativa poderá ser redirecionado para outra página da Web. Se você desabilitar essa configuração de política, o navegador de um usuário que carrega uma página contendo uma configuração Meta-Atualização ativa não poderá ser redirecionado a outra página da Web. Se você não configurar essa política, o navegador de um usuário que carrega uma página contendo uma configuração Meta-Atualização ativa não poderá ser redirecionado a outra página da Web.
  
  **Padrão**: desabilitado  
  
## <a name="local-policies-security-options"></a>Opções de Segurança de Políticas Locais
Para obter mais informações, veja [CSP de política – LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) na documentação do Windows. 

- **Restringir acesso anônimo a compartilhamentos e pipes nomeados**  
  Quando estiver habilitada, essa configuração de segurança restringirá o acesso anônimo a compartilhamentos e pipes para as configurações para: (1) pipes nomeados que podem ser acessados anonimamente (2) compartilhamentos que podem ser acessados anonimamente
  
  **Padrão**: Sim  
  
- **Segurança mínima de sessão para servidores baseados em NTLM SSP**  
  Essa configuração de segurança permite que um servidor exija a negociação de criptografia de 128 bits e/ou segurança de sessão NTLMv2. Esses valores são dependentes do valor de configuração de segurança no nível de autenticação do Gerenciador de LAN. As opções são: Requer segurança de sessão NTLMv2: A conexão falhará se a integridade da mensagem não for negociada. Exigir criptografia de 128 bits. A conexão falhará se a criptografia forte (128 bits) não for negociada.
  
  **Padrão**: exigir criptografia de 128 bits e NTLM V2  
  
- **Minutos de inatividade do bloqueio de tela até a proteção de tela ser ativada**  
  O Windows percebe a inatividade de uma sessão de logon e, se o tempo de inatividade exceder o limite de inatividade, o protetor de tela será executado, bloqueando a sessão.
  
  **Padrão**: 15
  
- **Exigir que o cliente sempre assine comunicações digitalmente** essa configuração de segurança determina se todo o tráfego de canal seguro iniciado pelo membro do domínio deve ser assinado ou criptografado. Quando um computador ingressa em um domínio, uma conta de computador é criada. Depois disso, quando o sistema é iniciado, ele usa a senha da conta de computador para criar um canal seguro com um controlador de domínio para seu domínio. Esse canal seguro é usado para executar operações, como autenticação de passagem NTLM, Pesquisa de nome/SID de LSA e mais. Essa configuração determina se todo o tráfego de canal seguro iniciado pelo membro do domínio atende aos requisitos mínimos de segurança. Especificamente, ele determina se todo o tráfego de canal seguro iniciado pelo membro do domínio deve ser assinado ou criptografado. Se essa política estiver habilitada, o canal seguro não será estabelecido, a menos que uma assinatura ou criptografia de todo o tráfego do canal seguro seja negociada. Se essa política for desabilitada, a criptografia e a assinatura de todo o tráfego de canal seguro for negociada com o Controlador de Domínio, caso em que o nível de assinatura e criptografia dependerá da versão do Controlador de Domínio e das configurações das duas políticas a seguir: criptografar digitalmente os dados de canal seguro (quando possível) Membro do domínio: assinar digitalmente os dados de canal seguro (quando possível)
  
  **Padrão**: Sim
  
- **Nível de autenticação**  
  Essa configuração de segurança determina qual protocolo de autenticação de desafio/resposta é usado para logons de rede. Essa opção afeta o nível de protocolo de autenticação usado por clientes, o nível de segurança de sessão negociado e o nível de autenticação aceito pelos servidores da seguinte maneira:  
  - *Enviar respostas LM e NTLM*: os clientes usam a autenticação LM e NTLM e nunca usam segurança de sessão NTLMv2; controladores de domínio aceitam autenticações LM, NTLM e NTLMv2. 
  - *Enviar LM e NTLM – NTLMv2 se negociado*: os clientes usarão a autenticação LM e NTLM e usam segurança de sessão NTLMv2 se o servidor for compatível com ela; controladores de domínio aceitam autenticações LM, NTLM e NTLMv2. 
  - *Enviar somente resposta NTLM*: os clientes usarão a autenticação NTLM apenas e usarão segurança de sessão NTLMv2 se o servidor tiver suporte para ela; controladores de domínio aceitam autenticações LM, NTLM e NTLMv2. 
  - *Enviar somente resposta NTLMv2*: os clientes usarão a autenticação NTLMv2 apenas e usarão segurança de sessão NTLMv2 se o servidor tiver suporte para ela; controladores de domínio aceitam autenticações LM, NTLM e NTLMv2. 
  - *Enviar somente resposta NTLMv2. Recusar LM*: os clientes usarão a autenticação NTLMv2 apenas e usarão segurança de sessão NTLMv2 se o servidor tiver suporte para ela; controladores de domínio recusam LM (aceitam apenas autenticações NTLM e NTLMv2). 
  - *Enviar somente resposta NTLMv2. Recusar LM e NTLM*: os clientes usarão a autenticação NTLMv2 apenas e usarão segurança de sessão NTLMv2 se o servidor tiver suporte para ela; controladores de domínio recusam LM e NTLM (aceitam apenas autenticação NTLMv2). 
    
  **Padrão**: enviar somente resposta NTLMv2. Recusar LM e NTLM
  
- **Impedir que os clientes enviem senhas não criptografadas a servidores SMB de terceiros**  
  Se essa configuração de segurança estiver habilitada, o redirecionador de protocolo SMB poderá enviar senhas em texto sem formatação para servidores SMB não Microsoft que não dão suporte a criptografia de senha durante a autenticação. Enviar senhas não criptografadas é um risco à segurança.
  
  **Padrão**: Sim
  
- **Sempre desabilitar servidor assinando digitalmente comunicações**  
  Essa configuração de segurança determina se o cliente SMB tentará negociar a assinatura de pacotes SMB. O protocolo SMB (bloco de mensagens do servidor) fornece a base para o arquivo Microsoft e imprime compartilhamento e muitas outras operações de rede, como administração remota do Windows. Para impedir ataques man-in-the-middle que modificam pacotes SMB em trânsito, o protocolo SMB oferece suporte para assinatura digital de pacotes SMB. Essa configuração de política determina se o componente de cliente SMB tentará negociar a assinatura de pacote SMB quando ele se conectar a um servidor SMB. Se essa configuração estiver habilitada, o cliente de rede Microsoft pedirá ao servidor para executar pacotes SMB na configuração da sessão. Se a assinatura de pacote tiver sido habilitada no servidor, a assinatura de pacote será negociada. Se esta política estiver desabilitada, o cliente SMB nunca negociará a assinatura de pacote SMB.
  
  **Padrão**: Sim
  
- **Comportamento da solicitação de elevação de administrador**  
  Essa configuração de política controla o comportamento da solicitação de elevação para administradores. As opções são: 
    - *Elevar sem avisar*: permite que contas com privilégios realizem uma operação que requer elevação sem exigir consentimento ou credenciais. Observação: só use essa opção nos ambientes mais restritos. 
    - *Solicitar credenciais na área de trabalho protegida*: quando uma operação exige elevação de privilégio, na área de trabalho protegida, o usuário deve inserir um nome de usuário e uma senha com privilégios. Se o usuário inserir credenciais válidas, a operação continuará com o maior privilégio disponível desse usuário. 
    - *Solicitar consentimento na área de trabalho protegida*: quando uma operação requer a elevação de privilégio, na área de trabalho protegida, o usuário deve selecionar Permitir ou Negar. Se o usuário selecionar Permitir, a operação continuará com o privilégio mais alto disponível desse usuário. 
    - *Solicitar credenciais*: quando uma operação exige elevação de privilégio, o usuário é solicitado a inserir um nome de usuário administrativo e uma senha. Se o usuário inserir credenciais válidas, a operação continuará com o privilégio aplicável. 
    - *Solicitar consentimento*: quando uma operação exige a elevação de privilégio, o usuário deve selecionar Permitir ou Negar. Se o usuário selecionar Permitir, a operação continuará com o privilégio mais alto disponível desse usuário.  
    - *Solicitar consentimento para binários que não são do Windows*: quando uma operação para um aplicativo que não é da Microsoft exige a elevação de privilégio, na área de trabalho protegida, o usuário deve selecionar Permitir ou Negar. Se o usuário selecionar Permitir, a operação continuará com o privilégio mais alto disponível desse usuário.   
  
  **Padrão**: solicitar consentimento na área de trabalho protegida
  
- **Segurança mínima de sessão para clientes baseados em NTLM SSP**  
  Essa configuração de segurança permite que um cliente exija a negociação de criptografia de 128 bits e/ou segurança de sessão NTLMv2. Esses valores são dependentes do valor de configuração de segurança no nível de autenticação do Gerenciador de LAN. As opções são:
  - Exigir segurança de sessão NTLMv2: A conexão falhará se o protocolo NTLMv2 não for negociado. 
  - *Exige criptografia de 128 bits*: a conexão falhará se a criptografia forte (128 bits) não for negociada.
  - *Exigir criptografia de 128 bits e NTLM NTLMv2*. 

  **Padrão**: exigir criptografia de 128 do NTLM V2
  
- **Comportamento de remoção do cartão inteligente**  
    Essa configuração de segurança determina o que acontece quando o cartão inteligente de um usuário conectado é removido do leitor de cartão inteligente. As opções são:
     - *Nenhuma ação*. 
     - *Bloquear estação de trabalho* -a estação de trabalho é bloqueada quando o cartão inteligente for removido, permitindo que os usuários deixem a área, levem o cartão inteligente com eles e ainda mantenham a sessão protegida.
     - *Forçar Logoff* – é feito o logoff do usuário automaticamente quando o cartão inteligente é removido.
     - *Desconectar uma sessão de Área de Trabalho Remota* – a remoção do cartão inteligente desconecta a sessão sem fazer logoff do usuário. Isso permite ao usuário inserir o cartão inteligente e retomar a sessão mais tarde ou em outro computador equipado com o leitor de cartão inteligente, sem precisar fazer logon novamente. Se a sessão for local, essa política funcionará de modo idêntico a Bloquear a Estação de Trabalho.  <br><br>
    
  **Padrão**: Bloquear estação de trabalho
  
- **Bloquear enumeração anônima de compartilhamentos e contas do SAM**  
  Essa configuração de segurança determina se a enumeração anônima de contas e compartilhamentos SAM é permitida. O Windows permite que usuários anônimos executem determinadas atividades, como enumeração de nomes de contas de domínio e compartilhamentos de rede. Isso é conveniente, por exemplo, quando um administrador deseja permitir acesso a usuários em um domínio confiável que não mantém uma relação de confiança recíproca. Se você não quiser permitir enumeração anônima de contas e compartilhamentos SAM, defina essa política como *Sim*.
  
  **Padrão**: Sim
  
- **Logon remoto do bloco com senha em branco**  
  Essa configuração de segurança determina se contas locais que não são protegidas por senha podem ser usadas para fazer logon de locais diferentes do console do computador físico. Se habilitada, as contas locais que não são protegidas por senha deverão usar o teclado do computador para fazer logon. 

  *Aviso*: computadores que não estão em locais fisicamente seguros devem sempre aplicar políticas de senha forte para todas as contas de usuário local. Caso contrário, qualquer pessoa com acesso físico ao computador poderá efetuar logon usando uma conta de usuário que não tenha uma senha. Isso é especialmente importante para computadores portáteis. 

  Se você aplicar essa política de segurança ao grupo Todos, ninguém poderá fazer logon por meio dos Serviços de Área de Trabalho Remota. Essa configuração não afeta logons que usam contas de domínio. É possível que aplicativos que usam logons interativos remotos ignorem essa configuração.
  
  **Padrão**: Sim
  
- **Comportamento da solicitação de elevação do usuário padrão**  
  Essa configuração de política controla o comportamento da solicitação de elevação para usuários padrão. 
  - *Negar automaticamente solicitações de elevação*: quando uma operação exige elevação de privilégio, uma mensagem de erro configurável de acesso negado é exibida. Uma empresa que executa áreas de trabalho como um usuário padrão pode escolher essa configuração para ajudar a reduzir telefonemas ao suporte técnico. 
  - *Solicitar credenciais na área de trabalho protegida*: quando uma operação exige elevação de privilégio, na área de trabalho protegida, o usuário deve inserir um nome de usuário e uma senha diferentes. Se o usuário inserir credenciais válidas, a operação continuará com o privilégio aplicável. 
  - *Solicitar credenciais*: quando uma operação exige elevação de privilégio, o usuário é solicitado a inserir um nome de usuário administrativo e uma senha. Se o usuário inserir credenciais válidas, a operação continuará com o privilégio aplicável.  
  
  **Padrão**: negar automaticamente solicitações de elevação
  
- **Exigir o modo de aprovação de administrador para administradores**  
  Essa configuração de política controla o comportamento de todas as configurações de política de UAC (Controle de Conta de Usuário) para o computador. Se você alterar essa configuração de política, precisará reiniciar o computador. As opções são:   
  - *Não configurado*: o Modo de Aprovação de Administrador e todas as configurações de política do UAC relacionadas também são desabilitados. Observação: se essa configuração de política estiver desabilitada, a Central de Segurança notificará o usuário de que a segurança global do sistema operacional foi reduzida. 
  - *Sim*: o Modo de Aprovação de Administrador está habilitado. Essa política deve estar habilitada e as configurações de política do UAC relacionadas devem estar definidas corretamente para permitir que a conta de administrador interno e todos os outros usuários membros do grupo Administradores sejam executados no Modo de Aprovação de Administrador.  
  
  **Padrão**: Sim
  
- **Prevenir enumeração anônima de contas do SAM**  
  Essa configuração de segurança determina quais permissões adicionais são concedidas para conexões anônimas ao computador. O Windows permite que usuários anônimos executem determinadas atividades, como enumeração de nomes de contas de domínio e compartilhamentos de rede. Isso é conveniente, por exemplo, quando um administrador deseja permitir acesso a usuários em um domínio confiável que não mantém uma relação de confiança recíproca. Essa opção de segurança permite que restrições adicionais sejam impostas a conexões anônimas da seguinte maneira: 
  - *Sim*: não permitir enumeração de contas SAM. Esta opção substitui todos os usuários autenticados nas permissões de segurança para recursos.
  - *Não configurado*: Não há restrições adicionais. Dependem de permissões padrão.  
  
  **Padrão**: Sim
  
- **Alocar chamadas remotas ao gerenciador de contas de segurança**  
  Essa configuração de política permite restringir conexões rpc remotas para SAM. Se não estiver selecionada, o descritor de segurança padrão será usado.
  
  **Padrão**: *O:BAG:BAD:(A;;RC;;;BA)*

- **Usar o modo de aprovação de administrador**  
  Essa configuração de política controla o comportamento do modo de aprovação de administrador para a conta de administrador interno. As opções são: 
  - *Sim*: a conta de administrador interno usa o Modo de Aprovação de Administrador. Por padrão, qualquer operação que exija a elevação de privilégios solicitará que o usuário aprove a operação. 
  - *Não configurado*: a conta de administrador interno executa todos os aplicativos com privilégio administrativo total.  

  **Padrão**: Sim
  
- **Permitir que os aplicativos de acesso de interface do usuário para locais seguros**  
  Essa configuração de política controla se os programas de UIAccess ou UIA (Acessibilidade da Interface do Usuário) podem desabilitar automaticamente a área de trabalho protegida para solicitações de elevação usadas por um usuário padrão. 
  - *Sim*: programas UIA, incluindo a Assistência Remota do Windows, desabilitam automaticamente a área de trabalho protegida para prompts de elevação. Se você não desabilitar a configuração de política “Controle de Conta de Usuário: alternar para a área de trabalho protegida ao solicitar elevação”, os prompts serão exibidos na área de trabalho do usuário interativo em vez de na área de trabalho protegida. 
  - *Não configurado*: a área de trabalho protegida só pode ser desabilitada pelo usuário da área de trabalho interativa ou se a configuração de política “Controle de Conta de Usuário: alternar para a área de trabalho protegida ao solicitar elevação" for desabilitada.  

  **Padrão**: Sim

- **Detectar instalações de aplicativos e solicitar elevação**  
  Essa configuração de política controla o comportamento de detecção de instalação de aplicativo para o computador. As opções são: 
  - *Habilitado*: quando é detectado um pacote de instalação de aplicativo que exige elevação de privilégio, o usuário deve inserir um nome de usuário administrativo e uma senha. Se o usuário inserir credenciais válidas, a operação continuará com o privilégio aplicável. 
  - *Desabilitado*: pacotes de instalação do aplicativo não são detectados nem solicitados a fornecer elevação. Empresas que executam áreas de trabalho de usuário padrão e que utilizam tecnologias de instalação delegada, como a Instalação de Software via Política de Grupo ou o SMS (Systems Management Server), devem desabilitar essa configuração de política. Nesse caso, a detecção de Instalador não é necessária.  
  
  **Padrão**: Sim
  
- **Impedir o armazenamento do hash do gerenciador de LAN na próxima alteração de senha**  
  Essa configuração de segurança determina se, na próxima alteração de senha, o valor de hash do LM (Gerenciador de LAN) para a nova senha será armazenado. O hash do LM é relativamente fraco e propenso a ataques em comparação ao hash criptograficamente mais forte do Windows NT. Como o hash do LM é armazenado no computador local no banco de dados de segurança, as senhas poderão ser comprometidas se o banco de dados de segurança for atacado.
  
  **Padrão**: Sim

- **Virtualizar falhas de gravação de arquivos e do Registro para locais por usuário**  
  Essa configuração de política controla se falhas de gravação de aplicativo são redirecionadas para locais do sistema de arquivos e Registro definidos. Essa configuração de política mitiga aplicativos que são executados como administrador e gravam dados de aplicativo em tempo de execução em *%ProgramFiles%* , *%Windir%* , *%Windir%\system32* ou *HKLM\Software*.
  
  **Padrão**: Sim

## <a name="ms-security-guide"></a>Guia de segurança da MS  
Para obter mais informações, veja [CSP de política – MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) na documentação do Windows.  

- **Aplicar restrições de UAC a contas locais no logon de rede**  
  **Padrão**: habilitado
  
- **Configuração de iniciar driver de cliente SMB v1**  
  **Padrão**: Driver desabilitado
  
- **Servidor do SMB v1**  
  **Padrão**: desabilitado
  
- **Autenticação de resumo**  
  **Padrão**: desabilitado
  
- **Proteção contra substituição de tratamento de exceções estruturado**  
  **Padrão**: habilitado
  
## <a name="mss-legacy"></a>Herdado de MSS  
Para obter mais informações, veja [CSP de política – MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) na documentação do Windows.  

- **Nível de proteção de roteamento de origem de IP de rede**  
  **Padrão**: Maior proteção  
  
- **Rede ignora solicitações de liberação de nome do NetBIOS, exceto de servidores WINS**  
  **Padrão**: habilitado
  
- **Nível de proteção de roteamento de origem de IPv6 de rede**  
  **Padrão**: Maior proteção

- **ICMP rede redireciona substituição gerada por OSPF**  
  **Padrão**: desabilitado
  
## <a name="power"></a>Energia  
Para obter mais informações, veja [CSP de política – Ligar/desligar](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) na documentação do Windows.  

- **Exigir senha ao despertar enquanto conectado**  
  Essa configuração de política especifica se o usuário é solicitado a fornecer uma senha quando o sistema sai do modo de suspensão. Se você habilitar ou não configurar essa política, o usuário deverá informar uma senha quando o sistema sair do modo de suspensão. Se você desabilitar essa configuração de política, o usuário não será solicitado a informar uma senha quando o sistema sair do modo de suspensão.
  
  **Padrão**: habilitado
  
- **Estados de espera quando em suspensão enquanto na bateria**  
  Essa configuração de política gerencia se o Windows pode usar estados de espera ao colocar o computador em um estado de suspensão. Se você habilitar ou não configurar essa política, o Windows usará estados de espera para colocar o computador em um estado de suspensão. Se você desabilitar essa configuração de política, os estados de espera (S1-S3) não serão permitidos.
  
  **Padrão**: desabilitado
  
- **Estados de espera quando em suspensão enquanto conectado**  
  Essa configuração de política gerencia se o Windows pode usar estados de espera ao colocar o computador em um estado de suspensão. Se você habilitar ou não configurar essa política, o Windows usará estados de espera para colocar o computador em um estado de suspensão. Se você desabilitar essa configuração de política, os estados de espera (S1-S3) não serão permitidos.
  
  **Padrão**: desabilitado
  
- **Exigir senha ao despertar enquanto estiver na bateria**  
  Essa configuração de política especifica se o usuário é solicitado a fornecer uma senha quando o sistema sai do modo de suspensão. Se você habilitar ou não configurar essa política, o usuário deverá informar uma senha quando o sistema sair do modo de suspensão. Se você desabilitar essa configuração de política, o usuário não será solicitado a informar uma senha quando o sistema sair do modo de suspensão.
  
  **Padrão**: habilitado
  
## <a name="remote-desktop-services"></a>Serviços de área de trabalho remota  
Para obter mais informações, veja [CSP de política – RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) na documentação do Windows.  

- **Bloquear o salvamento de senha**  
  Controla se as senhas podem ser salvas neste computador de Conexão de Área de Trabalho Remota. Se você habilitar essa configuração, a caixa de seleção de salvamento de senha na Conexão de Área de Trabalho Remota será desabilitada e os usuários não poderão salvar senhas. Quando um usuário abre um arquivo RDP usando a Conexão de Área de Trabalho Remota e salva suas configurações, qualquer senha que existia anteriormente no arquivo RDP é excluída. Se você desabilitar essa configuração ou deixá-la não configurada, o usuário poderá salvar senhas usando a Conexão de Área de Trabalho Remota.
  
   **Padrão**: habilitado
  
- **Comunicação de RPC segura**  
  Especifica se um servidor Host da Sessão da Área de Trabalho Remota requer comunicação RPC segura com todos os clientes ou permite comunicação não segura. Você pode usar essa configuração para reforçar a segurança de comunicação RPC com clientes, permitindo somente solicitações autenticadas e criptografadas. Se o status for definido como habilitado, os Serviços de Área de Trabalho Remota aceitarão solicitações de clientes RPC que dão suporte a solicitações seguras e não permitirá comunicação não segura com clientes não confiáveis. Se o status estiver definido como desabilitado, os serviços de área de trabalho remota sempre solicitarão a segurança para todo o tráfego RPC. No entanto, a comunicação não protegida será permitida para clientes RPC que não responderam à solicitação. Se o status estiver definido como não configurado, comunicação não protegida será permitida. Observação: a interface RPC é usada para administrar e configurar Serviços de Área de Trabalho Remota.
  
  **Padrão**: habilitado
  
- **Bloquear o redirecionamento de unidade**  
  Essa configuração de política especifica se o mapeamento de unidades de cliente deve ser impedido em uma sessão de Serviços de Área de Trabalho Remota (redirecionamento de unidade). Por padrão, um servidor Host da Sessão da Área de Trabalho Remota mapeia unidades do cliente de modo automático após a conexão. Unidades mapeadas aparecem na árvore de pasta da sessão no Computador ou no Gerenciador de Arquivos no formato *\<letra_da_unidade>* em *\<nome_do_computador>* . Você pode usar essa configuração de política para substituir esse comportamento. Se você habilitar essa configuração de política, o redirecionamento de unidade do cliente não será permitido em sessões de Serviços de Área de Trabalho Remota e o redirecionamento de cópia de arquivos da Área de Transferência não será permitido em computadores que executam o Windows Server 2003, o Windows 8 e o Windows XP. Se você desabilitar essa configuração de política, o redirecionamento de unidade do cliente sempre será permitido. Além disso, o redirecionamento de cópia de arquivo da Área de Transferência sempre será permitido se o redirecionamento de área de transferência for permitido. Se você não configurar essa política, o redirecionamento de unidade do cliente e o redirecionamento de cópia de arquivo da Área de Transferência não serão especificados no nível de Política de Grupo.
  
  **Padrão**: habilitado
  
- **Solicitação de senha após a conexão**  
  Essa configuração de política especifica se os serviços de área de trabalho remota sempre solicitam uma senha após a conexão cliente. Você pode usar essa configuração para impor uma solicitação de senha para usuários que estejam fazendo logon em serviços de área de trabalho remota, mesmo que eles já tenham fornecido a senha no cliente de Conexão de Área de Trabalho Remota. Por padrão, os Serviços de Área de Trabalho Remota permitem que os usuários façam logon automaticamente inserindo uma senha no cliente de Conexão de Área de Trabalho Remota. Se você habilitar essa configuração de política, os usuários não poderão fazer logon automaticamente nos Serviços de Área de Trabalho Remota fornecendo a senha no cliente de Conexão de Área de Trabalho Remota. Eles deverão fornecer uma senha para fazer logon. Se você desabilitar essa configuração de política, os usuários sempre poderão fazer logon nos Serviços de Área de Trabalho Remota automaticamente fornecendo a senha no cliente de Conexão de Área de Trabalho Remota. Se você não configurar essa política, o logon automático não será especificado no nível de Política de Grupo. 
  
  **Padrão**: habilitado
  
- **Nível de criptografia de conexão de cliente de serviços de área de trabalho remota**  
  Especifica se deve ser exigido o uso de um nível específico de criptografia para proteger as comunicações entre computadores cliente e servidores de Host da Sessão RD durante as conexões de protocolo RDP. Essa política se aplica somente quando você está usando a criptografia de RDP nativa. No entanto, a criptografia de RDP nativa (em vez de criptografia SSL) não é recomendável. Essa política não se aplica a criptografia SSL. Se você habilitar essa configuração de política, todas as comunicações entre clientes e servidores de Host da Sessão RD durante conexões remotas deverão usar o método de criptografia especificado nessa configuração. Por padrão, o nível de criptografia é definido como alto. Os seguintes métodos de criptografia estão disponíveis:  
  - *Alta*: a configuração Alta criptografa os dados enviados do cliente para o servidor e do servidor para o cliente usando criptografia forte de 128 bits. Use esse nível de criptografia em ambientes que contêm somente clientes de 128 bits (por exemplo, clientes que executam a Conexão de Área de Trabalho Remota). Os clientes que não dão suporte a esse nível de criptografia não podem se conectar a servidores de Host da Sessão RD.  
  - *Compatível com cliente*: a configuração compatível com cliente criptografa os dados enviados entre o cliente e o servidor na força da chave máxima com suporte no cliente. Use esse nível de criptografia em ambientes que incluam clientes que não dão suporte à criptografia de 128 bits.  
  - *Baixa*: a configuração Baixa criptografa apenas os dados enviados do cliente ao servidor usando a criptografia de 56 bits.  
  
  Se você desabilitar ou não configurar essa política, o nível de criptografia a ser usado para conexões remotas com servidores de Host da Sessão RD não será imposto pela Política de Grupo. Conformidade com FIPS importante pode ser definida por meio de criptografia de Sistema. Use algoritmos em conformidade com FIPS para configurações de criptografia, hash e assinatura na Política de Grupo (em computador Configuration\Windows Settings\Security Settings\Local Policies\Security Options). A configuração de conformidade com FIPS criptografa e descriptografa os dados enviados do cliente para o servidor e do servidor para o cliente, com os 140 algoritmos de criptografia FIPS (Federal Information Processing Standard), usando os módulos criptográficos da Microsoft. Use esse nível de criptografia quando a comunicação entre clientes e servidores de Host da Sessão RD exigir o nível mais alto de criptografia.
  
  **Padrão**: Alta
  
## <a name="remote-management"></a>Gerenciamento remoto  
Para obter mais informações, veja [CSP de política – RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) na documentação do Windows.  

- **Execução do bloco armazenando como credenciais**  
  Autenticação básica do cliente
  
  **Padrão**: habilitado
  
- **Autenticação básica**  
  Essa configuração de política permite que você gerencie se o serviço WinRM (Windows Remote Management) aceita autenticação básica de um cliente remoto. Se você habilitar essa configuração de política, o serviço WinRM aceitará autenticação básica de um cliente remoto. Se você desabilitar ou não configurar essa política, o serviço WinRM não aceitará a autenticação Básica de um cliente remoto.
  
  **Padrão**: desabilitado
  
- **Autenticação de resumo de cliente do bloco**  
  Essa configuração de política permite que você gerencie se o cliente do WinRM (Windows Remote Management) usa a autenticação de Resumo. Se você habilitar essa configuração de política, o cliente WinRM não usará a autenticação Digest. Se você desabilitar ou não configurar essa política, o cliente WinRM usará a autenticação Digest.
  
  **Padrão**: habilitado
  
- **Tráfego não criptografado**  
  Essa configuração de política permite que você gerencie se o serviço WinRM (Windows Remote Management) envia e recebe mensagens não criptografadas pela rede. Se você habilitar essa configuração de política, o cliente WinRM enviará e receberá mensagens não criptografadas pela rede. Se você desabilitar ou não configurar essa política, o cliente WinRM enviará ou receberá somente mensagens criptografadas pela rede.  
  
  **Padrão**: desabilitado
  
- **Tráfego não criptografado de cliente**  
  Essa configuração de política permite gerenciar se o cliente de Gerenciamento Remoto do Windows (WinRM) envia e recebe mensagens não criptografadas pela rede. Se você habilitar essa configuração de política, o cliente WinRM enviará e receberá mensagens não criptografadas pela rede. Se você desabilitar ou não configurar essa política, o cliente WinRM enviará ou receberá somente mensagens criptografadas pela rede.
  
  **Padrão**: desabilitado
  
- **Autenticação básica do cliente**  
  Essa configuração de política permite que você gerencie se o cliente do WinRM (Windows Remote Management) usa a autenticação Básica. Se você habilitar essa configuração de política, o cliente WinRM usará autenticação Básica. Se o WinRM for configurado para usar o transporte HTTP, o nome de usuário e a senha serão enviados pela rede como texto não criptografado. Se você desabilitar ou não configurar essa política, o cliente WinRM não usará a autenticação Básica.
  
  **Padrão**: desabilitado
  

## <a name="remote-procedure-call"></a>Chamada de Procedimento Remoto  
Para obter mais informações, veja [CSP de política RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) na documentação do Windows.  

- **Opções de cliente RPC não autenticado**  
  Essa configuração de política controla como o tempo de execução do servidor RPC lida com clientes RPC não autenticados conectando-se aos servidores RPC. Essa configuração de política afeta todos os aplicativos RPC. Em um ambiente de domínio, use essa configuração de política com cuidado, pois pode afetar uma ampla variedade de funcionalidades, incluindo a política de grupo de processamento em si. Reverter uma alteração a essa configuração de política pode exigir intervenção manual em cada computador afetado. Essa configuração de política nunca deve ser aplicada a um controlador de domínio. Se você desabilitar essa configuração de política, o tempo de execução do servidor RPC usará o valor de "Autenticado" no cliente do Windows e o valor de "Nenhum" em versões do Windows Server que deem suporte a essa configuração de política. Se você não configurar essa política, ela permanecerá desabilitada. O tempo de execução do servidor RPC se comportará como se tivesse sido habilitado com o valor de "Autenticado" usado para o Cliente do Windows e o valor de "Nenhum" será usado para SKUs de Servidor que dão suporte a essa configuração de política. Se você habilitar essa configuração de política, ela instruirá o tempo de execução do servidor RPC a impedir que clientes RPC não autenticados conectem-se aos servidores RPC em execução em um computador. Um cliente será considerado autenticado se ele usar um pipe nomeado para se comunicar com o servidor ou usar a segurança de RPC. As Interfaces RPC que especificamente solicitaram estar acessíveis por clientes não autenticados podem estar isentas dessa restrição, dependendo do valor selecionado para essa configuração de política.  
  - *Nenhum* permite que todos os clientes RPC conectem-se aos servidores RPC em execução no computador em que a configuração de política é aplicada. 
  - *Autenticado* permite que somente os Clientes RPC autenticados (conforme a definição acima) conectem-se aos servidores RPC em execução no computador em que a configuração de política é aplicada. Isenções são concedidas a interfaces que os solicitaram. 
  - *Autenticado sem exceções* permite que somente os Clientes RPC autenticados (conforme a definição acima) conectem-se aos servidores RPC em execução no computador em que a configuração de política é aplicada. Não são permitidas exceções. Observação: essa configuração de política não será aplicada até que o sistema seja reinicializado.  

  **Padrão**: Autenticado

## <a name="search"></a>Pesquisar 
Para obter mais informações, veja [CSP de política – Pesquisar](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) na documentação do Windows.  

- **Desabilitar a indexação de itens criptografados**  
  Permite ou não a indexação de itens. Essa opção é para o indexador do Windows Search, que controla se os itens criptografados são indexados, como os arquivos protegidos pela WIP (Proteção de Informações do Windows). Quando a política está habilitada, os itens protegido pela WIP são indexados e os metadados sobre eles são armazenados em um local não criptografado. Os metadados incluem coisas como o caminho do arquivo e a data de modificação. Quando a política é desabilitada, os itens protegidos pela WIP não são indexados e não aparecem nos resultados na Cortana ou no Explorador de Arquivos. Também poderá haver um impacto no desempenho em fotos e em aplicativos do Groove se houver muitos arquivos de mídia protegidos pela WIP no dispositivo.
  
**Padrão**: Sim
  
## <a name="smart-screen"></a>Tela inteligente  
Para obter mais informações, veja [CSP de política – SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) na documentação do Windows.  

- **Bloquear a execução de arquivos não verificados**  
  Impedir que o usuário execute arquivos não verificados. 
  - *Não configurado* – os funcionários podem ignorar os avisos do SmartScreen e executar arquivos mal-intencionados. 
  - *Sim* – os funcionários não podem ignorar os avisos do SmartScreen nem executar arquivos mal-intencionados.

  **Padrão**: Sim

<!-- Not currently available? - **Block unverified file download**  
  By default, Microsoft Edge allows users to bypass (ignore) the Windows Defender SmartScreen warnings about potentially malicious files, allowing them to continue downloading the unverified file(s). Enabling this policy prevents users from bypassing the warnings, blocking them from downloading of the unverified file(s).
  
  **Default**: Yes
 --> 
- **Exigir SmartScreen para aplicativos e arquivos**  
  Permite que os Administradores de TI configurem o SmartScreen para Windows.

  **Padrão**: Sim
  
## <a name="system"></a>System (sistema)  
Para obter mais informações, veja [CSP de política – Sistema](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) na documentação do Windows.  

- **Inicialização do driver de inicialização do sistema**  
  Essa configuração de política permite que você especifique quais drivers de inicialização serão inicializados com base em uma classificação determinada por um driver de inicialização Antimalware de Início Antecipado. O driver de inicialização de Antimalware de Início Antecipado pode retornar as seguintes classificações para cada driver de inicialização: 
  - *Boa*: o driver foi assinado e não foi adulterado.  
  - *Inválido* – o driver foi identificado como malware. Recomendamos que você não permita que drivers sabidamente inválidos sejam inicializadas. 
  - *Inválido, mas necessário para a inicialização*: o driver foi identificado como malware, mas o computador não pode ser inicializado com êxito sem carregá-lo. 
  - *Desconhecido* – esse driver não foi atestado por seu aplicativo de detecção de malware e não foi classificado pelo driver de inicialização Antimalware de Início Antecipado.  

  Se você habilitar essa configuração de política, poderá escolher quais drivers de inicialização do computador inicializar na próxima vez em que o computador for iniciado. Se você desabilitar ou não configurar essa definição de política, os drivers de inicialização determinados como sendo Válidos, Desconhecidos ou Inválidos, mas Críticos para Inicialização, serão inicializados e a inicialização dos drivers determinada como inválida será ignorada. Se o aplicativo de detecção de malware não incluir um driver de inicialização Antimalware de Início Antecipado ou se o seu driver de inicialização Antimalware de Início Antecipado tiver sido desabilitado, essa configuração não terá nenhum efeito e todos os drivers de inicialização serão inicializados.  
  
  **Padrão**: válido, desconhecido e inválido crítico


## <a name="wi-fi"></a>Wi-Fi  
Para obter mais informações, veja [CSP de política – Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) na documentação do Windows.  

- **Bloquear compartilhamento de Internet**  
  Especifica se o compartilhamento de Internet é possível no dispositivo.  

  **Padrão**: Sim  

- **Bloquear conexão automática a hotspots Wi-Fi**  
  Permitir ou proibir o dispositivo de conectar-se automaticamente a hotspots Wi-Fi.  

  **Padrão**: Sim  
  
## <a name="windows-connection-manager"></a>Gerenciador de Conexão do Windows  
Para obter mais informações, veja [CSP de política – WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) na documentação do Windows.  

- **Bloquear conexão a redes de fora do domínio**  
  Essa configuração de política impede que computadores conectem-se a uma rede baseada em domínio e a uma rede baseada fora do domínio ao mesmo tempo. Se essa configuração de política estiver habilitada, o computador responderá às tentativas automáticas e manuais de conexão de rede com base nas seguintes circunstâncias: 
  - Tentativas de conexão automática Quando o computador já estiver conectado a uma rede baseada em domínio, todas as tentativas de conexão automática a redes de fora do domínio serão bloqueadas. Quando o computador já está conectado a uma rede com base de fora do domínio, as tentativas de conexão automática de redes com base em domínio são bloqueadas. 
  - Tentativas de conexão manual Quando o computador já estiver conectado a uma rede não baseada em domínio ou uma rede baseada em domínio por mídia que não Ethernet e um usuário tentar criar uma conexão manual a uma rede adicional em violação a essa configuração de política, a conexão de rede existente desconectará e a conexão manual será permitida. Quando o computador já estiver conectado a uma rede não baseada em domínio ou uma rede baseada em domínio pela Ethernet e um usuário tentar criar uma conexão manual a uma rede adicional em violação a esta configuração de política, a conexão de Ethernet existente será mantida e a tentativa de conexão manual será bloqueada.  

  Se essa configuração de política não estiver configurada ou estiver desabilitada, os computadores terão permissão para se conectar simultaneamente ao domínio e redes de fora do domínio.  

  **Padrão**: habilitado
  
## <a name="windows-defender"></a>Windows Defender  
Para obter mais informações, veja [CSP de política – Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) na documentação do Windows.  

- **Examinar mensagens de email recebidas**  
  Permite ou proíbe a verificação de email.
  
  **Padrão**: Sim  

- **Tipo de processo filho de iniciar aplicativos do Office**  
  Aplicativos do Office não terão permissão para criar processos filho. Isso inclui Word, Excel, PowerPoint, OneNote e Access. Esse é um comportamento típico de malware, especialmente para ataques baseados em macro que tentam usar aplicativos do Office para iniciar ou baixar executáveis mal-intencionados.
  
  **Padrão**: Bloquear
  
- **Tipo de consentimento de envio de amostra do Defender**  
  Verifica o nível de consentimento do usuário no Windows Defender para enviar dados. Se o consentimento necessário já tiver sido concedido, o Windows Defender os enviará. Caso contrário (e se o usuário tiver especificou nunca perguntar), a interface do usuário será iniciada para pedir consentimento do usuário (quando o Defender/AllowCloudProtection for permitido) antes de enviar dados.
  
  **Padrão**: enviar amostras seguras automaticamente 
  
- **Intervalo de atualização de assinaturas (em horas)**  
  Intervalo de atualização de assinatura do Defender em horas
  
  **Padrão**: 4
  
- **Gerar script de tipo de execução de payload baixada**  
  Tipo de execução de payload baixada do script do Defender
  
  **Padrão**: Bloquear
  
- **Impedir que o tipo de roubo de credencial**  
  O Windows Defender Credential Guard usa segurança baseada em virtualização para isolar segredos para que apenas o software de sistema privilegiado possa acessá-los. O acesso não autorizado a esses segredos pode levar a ataques de roubo de credenciais, como Pass-the-Hash ou Pass-The-Ticket. O Windows Defender Credential Guard evita esses ataques protegendo os hashes de senha NTLM, Kerberos Ticket Granting Tickets e credenciais armazenadas por aplicativos como credenciais de domínio.
  
  **Padrão**: Habilitar

- **Tipo de execução de conteúdo de email**  
  Essa regra impede que os seguintes tipos de arquivo sejam executados ou iniciados a partir de um email visto no Microsoft Outlook ou webmail (por exemplo, Gmail.com ou Outlook.com): arquivos executáveis (como .exe, .dll ou .scr), arquivos de Script (como um .ps do PowerShell, .vbs do VisualBasic ou o arquivo .js do JavaScript) e arquivos mortos de Script.
  
  **Padrão**: Bloquear
  
- **Tipo de proteção de rede**  
  Esta política permite que você ative ou desative a proteção de rede (bloquear/auditar) no Windows Defender Exploit Guard. A proteção de rede é um recurso do Windows Defender Exploit Guard que protege os funcionários usando qualquer aplicativo do acesso a golpes de phishing, sites que hospedam explorações e conteúdo mal-intencionado na Internet. Isso inclui impedir que navegadores de terceiros se conectem a sites perigosos. O tipo de valor é um inteiro. Se você habilitar essa configuração, a proteção de rede estará ativada e os funcionários não poderão desativá-la. Seu comportamento pode ser controlado pelas seguintes opções: bloquear e auditar. Se você habilitar essa política com a opção "Bloquear", os aplicativos e usuários serão impedidos de se conectar a domínios perigosos. Você poderá ver essa atividade na Central de Segurança do Windows Defender. Se você habilitar essa política com a opção "Auditar", os aplicativos/usuários não serão impedidos de se conectar a domínios perigosos. No entanto, você ainda verá essa atividade na Central de Segurança do Windows Defender. Se você desabilitar essa política, os aplicativos/usuários não serão impedidos de se conectar a domínios perigosos. Você não verá nenhuma atividade de rede na Central de Segurança do Windows Defender. Se você não configurar essa política, o bloqueio de rede estará desabilitado por padrão.
  
  **Padrão**: Habilitar
  
- **Dia da verificação do agendamento do Defender**  
  Dia da verificação do agendamento do Defender.
  
  **Padrão**: Todos os dias
  
- **Proteção entregue na nuvem**  
  Para melhor proteger seu computador, o Windows Defender enviará informações à Microsoft sobre quaisquer problemas encontrados. A Microsoft analisará essas informações, saberá mais sobre os problemas que afetam você e outros clientes e oferecerá soluções aprimoradas.
  
  **Padrão**: Sim  

- **Ação de aplicativo potencialmente indesejado do Defender**  
  O recurso de proteção de PUA (Aplicativo Potencialmente Indesejado) no Windows Defender Antivírus pode identificar e impedir que PUAs baixem e realizem a instalação em pontos de extremidade na sua rede. Esses aplicativos não são considerados vírus, malware ou outros tipos de ameaças, mas podem executar ações nos pontos de extremidade que podem prejudicar seu desempenho ou uso. PUA também pode se referir aos aplicativos que são considerados de má reputação. O comportamento típico de PUA inclui: vários tipos de software agrupando injeção de Ad em drivers de navegadores da Web e otimizadores de registro que detectam problemas, solicitação de pagamento para corrigir os erros, mas permanecem no ponto de extremidade e não fazem alterações ou otimizações (também conhecido como programas de "antivírus de invasores"). Esses aplicativos podem aumentar o risco de a sua rede ser infectada com malware, fazer infecções por malware serem mais difíceis de identificar e podem desperdiçar recursos de TI ao limpar os aplicativos.  
  
  **Padrão**: Bloquear  

- **Tipo de código de macro ocultado de script**  
  Malware e outras ameaças podem tentar ocultar seu código mal-intencionado em arquivos de script. Essa regra impede a execução de scripts que parecem estar ocultos.
  
  **Padrão**: Bloquear
  
- **Examinar unidades removíveis durante um exame completo**  
  Permite que o Windows Defender examine a existência de software mal-intencionado e indesejado em unidades removíveis (por exemplo, pen drives) durante uma verificação completa. O Windows Defender Antivírus examina todos os arquivos nos dispositivos USB antes da execução.
  
  **Padrão**: Sim  
  
- **Verificar arquivos mortos**  
  O Defender verifica arquivos mortos.
  
  **Padrão**: Sim
  
- **Monitoramento de comportamento**  
  Permite ou não a funcionalidade de Monitoramento de Comportamento do Windows Defender. Inseridos no Windows 10, esses sensores coletam e processam sinais comportamentais do sistema operacional e enviam esses dados do sensor à sua instância de nuvem privada e isolada do Microsoft Defender ATP.
  
  **Padrão**: Sim

- **Examinar arquivos abertos em pastas de rede**  
  Se os arquivos forem somente leitura, o usuário não poderá remover nenhum malware detectado.
  
  **Padrão**: Sim

- **Tipo de processo de USB não confiável**  
  Com essa regra, os administradores podem impedir que arquivos executáveis não confiáveis ou não assinados sejam executados de unidades removíveis USB, incluindo cartões SD.
  
  **Padrão**: Bloquear
  
- **Tipo de injeção de outros processos de aplicativos do Office**  
  Os aplicativos do Office, incluindo o Word, o Excel, o PowerPoint e o OneNote, não poderão injetar código em outros processos. Isso normalmente é usado por malware para executar código mal-intencionado em uma tentativa de ocultar a atividade de mecanismos de verificação de antivírus.
  
  **Padrão**: Bloquear
  
- **Tipo de código de macro do Office que permite importações do Win32**  
  O malware pode usar o código de macro em arquivos do Office para importar e carregar DLLs do Win32, que pode ser usado para fazer chamadas à API para permitir a infecção em todo o sistema. Essa regra tenta bloquear arquivos do Office que contêm código de macro que é capaz de importar as DLLs do Win32. Isso inclui o Word, o Excel, o PowerPoint e o OneNote.
  
  **Padrão**: Bloquear  
  
- **Nível de bloco de nuvem do Defender**  
  Nível de bloco de nuvem do Defender.
  
  **Padrão**: Não configurado

- **Monitoramento em tempo real**  
  O Defender exige monitoramento em tempo real.
  
  **Padrão**: Sim
  
- **Tipo de lançamento ou criação de conteúdo executável de aplicativos do Office**  
  Essa regra tem como alvo os comportamentos típicos usados por complementos e scripts (extensões) suspeitos e mal-intencionados que criam ou inicializam arquivos executáveis. Essa é uma técnica de malware típica. As extensões são impedidas de serem usadas pelos aplicativos do Office. Normalmente essas extensões usam o Windows Script Host (arquivos .wsh) para executar scripts que automatizam determinadas tarefas ou fornecem recursos de complemento criados pelo usuário
  
  **Padrão**: Bloquear

## <a name="windows-ink-workspace"></a>Workspace do Windows Ink  
Para obter mais informações, veja [CSP de política – WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) na documentação do Windows.  

- **Workspace do Ink**  
  Especifica se deve permitir que o usuário acesse o Workspace do Ink. 
  - *Desabilitado* – o acesso ao Workspace do Ink está desabilitado. O recurso está desativado.
  - *Habilitado* – o recurso Workspace do Ink está ativado, mas o usuário não pode acessá-lo acima da tela de bloqueio.
  - *Não configurado* – o recurso Workspace do Ink está ativado e o usuário não pode usá-lo acima da tela de bloqueio.  

  **Padrão**: habilitado
 
## <a name="windows-powershell"></a>Windows PowerShell  
Para obter mais informações, veja [CSP de política – WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) na documentação do Windows.  

- **Registro em log do bloco de script do PowerShell**  
  Essa configuração de política habilita o registro em log de toda a entrada de script do PowerShell para o log de eventos Operacional/Microsoft-Windows-PowerShell. Se você habilitar essa configuração de política, o Windows PowerShell registrará o processamento de comandos, blocos de script, funções e scripts – sejam invocados interativamente ou por meio da automação. Se você desabilitar essa configuração de política, o registro em log da entrada de script do PowerShell será desabilitado. Se você habilitar o registro em log da invocação do bloco de script, o PowerShell registrará eventos adicionalmente quando a invocação de um comando, um bloco de script, uma função ou um script for iniciada ou interrompida. Habilitar o registro em log de invocação gera um alto volume de logs de eventos. Observação: essa configuração de política existe na Configuração do Computador e na Configuração do Usuário no Editor de Política de Grupo. A configuração de política de Configuração do computador tem prioridade sobre a configuração de política de Configuração do Usuário.
  
  **Padrão**: habilitado
 
