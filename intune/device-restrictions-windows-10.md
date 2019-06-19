---
title: Configurações de restrições de dispositivo para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações e suas descrições para a criação de restrições de dispositivo no Windows 10 e em versões posteriores. Use essas definições em um perfil de configuração para controlar capturas de tela, requisitos de senha, configurações de quiosque, aplicativos na loja, o navegador Microsoft Edge, o Windows Defender, o acesso à nuvem, o menu Iniciar e muito mais no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/12/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 357d1619fdf051d07ea47c84a79b2aebd1523460
ms.sourcegitcommit: a2bad7465422b98eb3c10f03dc5a24fd99cee78d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041134"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>Configurações de dispositivo Windows 10 (e mais recente) para permitir ou restringir recursos usando o Intune

Este artigo lista e descreve todas as diferentes configurações que você pode controlar em dispositivos Windows 10 e mais recente. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, definir regras de senha, personalizar a tela de bloqueio, usar o Windows Defender e muito mais.

Essas configurações são adicionadas a um perfil de configuração do dispositivo no Intune e, em seguida, atribuídas ou implantadas em dispositivos Windows 10.

> [!Note]
> Nem todas as opções estão disponíveis em todas as edições do Windows. Para ver as edições com suporte, veja [CSPs de política](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) (abre outro site da Microsoft).

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](device-restrictions-configure.md#create-the-profile).

## <a name="app-store"></a>Loja de aplicativos

Essas configurações usam o [CSP da política ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement), que também lista as edições compatíveis do Windows.

- **Loja de aplicativos** (somente dispositivos móveis): **Não configurado** (padrão) permite aos usuários finais acesso à loja de aplicativos em dispositivos móveis. **Bloquear** impede o uso da loja de aplicativos.
- **Atualizar aplicativos automaticamente do repositório**: **Não configurado** (padrão) permite que os aplicativos instalados da Microsoft Store sejam atualizados automaticamente. **Bloquear** impede que as atualizações sejam instaladas automaticamente.
- **Instalação de aplicativo confiável**: escolha se os aplicativos que não fazem parte da Microsoft Store podem ser instalados, processo também conhecido como sideload. O sideload está instalando e, em seguida, executando ou testando um aplicativo que não é certificado pela Microsoft Store. Por exemplo, um aplicativo que é interno apenas à sua empresa. Suas opções:
  - **Não configurado** (padrão): usa o valor do sistema operacional.
  - **Bloquear**: impede o sideload. Aplicativos não pertencentes à Microsoft Store não podem ser instalados.
  - **Permitir**: permite o sideload. Aplicativos não pertencentes à Microsoft Store podem ser instalados.
- **Desbloqueio do desenvolvedor**: permite que configurações de desenvolvedor do Windows, assim como a permissão de sideload de aplicativos, sejam modificadas por usuários finais. Suas opções:
  - **Não configurado** (padrão): usa o valor do sistema operacional.
  - **Bloquear**: bloqueia o modo do desenvolvedor e o sideload de aplicativos.
  - **Permitir**: permite o modo do desenvolvedor e o sideload de aplicativos.

  [Habilitar seu dispositivo para desenvolvimento](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development) tem mais informações sobre esse recurso.

- **Dados de aplicativo do usuário compartilhados**: escolha **Permitir** para compartilhar dados de aplicativo entre usuários diferentes no mesmo dispositivo e com outras instâncias desse aplicativo. **Não configurado** (padrão) impede o compartilhamento de dados com outros usuários e de outras instâncias do mesmo aplicativo.
- **Usar somente o repositório particular**: **Permitir** só permite que os aplicativos sejam baixados de um repositório particular, mas não baixados do repositório público, incluindo de um catálogo de varejo. **Não configurado** (padrão) permite que aplicativos sejam baixados somente de um repositório privado e de um repositório público.
- **Inicialização de aplicativo originado do repositório**: **Bloquear** desabilita todos os aplicativos previamente instalados no dispositivo ou baixados da Microsoft Store. **Não configurado** (padrão) permite que esses aplicativos sejam abertos.
- **Instalar dados de aplicativo no volume do sistema**: **Bloquear** impede que os aplicativos armazenem dados no volume do sistema do dispositivo. **Não configurado** (padrão) permite que os aplicativos armazenem dados no volume de disco do sistema.
- **Instalar aplicativos na unidade do sistema**: **Bloquear** impede que os aplicativos sejam instalados na unidade do sistema do dispositivo. **Não configurado** (padrão) permite que os aplicativos sejam instalados no volume de disco do sistema.
- **DVR de jogos** (somente desktop): **Bloquear** desabilita a gravação e a difusão de Jogos do Windows. **Não configurado** (padrão) permite a gravação e a difusão de jogos.
- **Somente aplicativos da Loja**: **Exigir** força os usuários finais a instalarem somente aplicativos da Windows Store. **Não configurado** permite aos usuários finais instalar aplicativos de locais que não sejam a Windows Store.
- **Forçar a reinicialização de aplicativos em caso de falha de atualização**: quando um aplicativo está em uso, não pode ser atualizado. Use essa configuração para forçar um aplicativo a reiniciar. **Não configurado** (padrão) não força a reinicialização dos aplicativos. **Exigir** permite que os administradores forcem a reinicialização em uma data e hora específicas ou em um agendamento recorrente. Quando definido como **Exigir**, também insira:

  - **Data/hora de início**: escolha uma data específica e hora para reiniciar os aplicativos.
  - **Recorrência**: escolha se é para reiniciar diariamente, semanalmente ou mensalmente.

  [ApplicationManagement/ScheduleForceRestartForUpdateFailures CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

- **Controle de usuário sobre instalações**: quando definido como **Não configurado** (padrão), o Windows Installer impede que usuários alterem as opções de instalação normalmente reservadas para os administradores do sistema, como inserir o diretório para instalar os arquivos. **Bloquear** permite aos usuários alterar essas opções de instalação e alguns dos recursos de segurança do Windows Installer são ignorados.

  [ApplicationManagement/MSIAllowUserControlOverInstall CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msiallowusercontroloverinstall)

- **Instalar aplicativos com privilégios elevados**: quando definido como **Não configurado** (padrão), o sistema aplica as permissões do usuário atual ao instalar programas que um administrador do sistema não implanta ou oferece. **Bloquear** direciona o Windows Installer para usar permissões elevadas ao instalar algum programa em um sistema. Esses privilégios são estendidos para todos os programas.

  [ApplicationManagement/MSIAlwaysInstallWithElevatedPrivileges CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msialwaysinstallwithelevatedprivileges)

- **Aplicativos de inicialização**: insira uma lista de aplicativos a abrir depois que um usuário fizer logon no dispositivo. Certifique-se de usar uma lista delimitada por ponto-e-vírgula dos PFN (Nomes da família de pacotes) de aplicativos do Windows. Para esta política funcionar, o manifesto nos aplicativos do Windows deve usar uma tarefa de inicialização.

  [ApplicationManagement/LaunchAppAfterLogOn CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-launchappafterlogon)

Selecione **OK** para salvar suas alterações.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade

Essas configurações usam CSPs da [política de conectividade](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) e da [política de Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi), que também listam as edições compatíveis do Windows.

- [CSP da política de Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi)

- **Canal de dados da rede celular**: escolha se os usuários finais poderão usar dados, assim como ao navegar na Web, quando estiverem conectados a uma rede celular. Suas opções:
  - **Não configurado** (padrão): usa o sistema operacional padrão, o que pode permitir o canal de dados de celular. Os usuários finais podem desativá-lo.
  - **Bloquear**: não permite o canal de dados de celular. Os usuários finais não podem ativá-lo.
  - **Permitir (não editável)** : permite o canal de dados de celular. Os usuários finais não podem desativá-lo.

- **Roaming de dados**: **Bloquear** impede roaming de dados de celular no dispositivo. **Não configurado** (padrão) permite roaming entre redes ao acessar os dados.
- **VPN em rede celular**: **Bloquear** impede que o dispositivo acesse conexões VPN quando estiver conectado a uma rede celular. **Não configurado** (padrão) permite que a VPN use qualquer conexão, incluindo celulares.
- **Roaming de VPN em rede celular**: **Bloquear** impede que o dispositivo acesse conexões VPN quando estiver conectado a uma rede celular. **Não configurado** (padrão) permite conexões VPN ao fazer roaming.
- **Serviço de dispositivos conectados**: **Bloquear** desabilita o componente CDP (plataforma de dispositivos conectados). O CDP permite a descoberta e conexão a outros dispositivos (por meio de Bluetooth/LAN ou na nuvem) para dar suporte à inicialização de aplicativos remotos, envio remoto de mensagens, sessões de aplicativo remoto e outras experiências entre dispositivos. **Não configurado** (padrão) permite escolher se o serviço de dispositivos conectados será permitido, o que habilita a descoberta e a conexão com outros dispositivos Bluetooth.
- **NFC**: **Bloquear** impede o uso de funcionalidades NFC (comunicações a curta distância). **Não configurado** (padrão) permite aos usuários habilitar e configurar recursos de NFC no dispositivo.
- **Wi-Fi**: **Bloquear** impede que os usuários habilitem, configurem e usem conexões Wi-Fi no dispositivo. **Não configurado** (padrão) permite conexões Wi-Fi.
- **Conectar-se automaticamente a hotspots Wi-Fi**: **Bloquear** impede que dispositivos se conectem automaticamente a hotspots Wi-Fi. **Não configurado** (padrão) permite que dispositivos se conectem automaticamente a hotspots Wi-Fi gratuitos e aceite os possíveis termos e condições da conexão automaticamente.
- **Configuração manual de Wi-Fi**: **Bloquear** impede que dispositivos se conectem ao Wi-Fi fora de redes instaladas fora do servidor MDM. **Não configurado** (padrão) permite que os usuários finais adicionem e configurem suas próprias SSIDs de rede de conexões Wi-Fi.
- **Intervalo de verificação de Wi-Fi**: insira a frequência com que os dispositivos devem procurar por redes Wi-Fi. Insira um valor de 1 (mais frequente) a 500 (menos frequente). O padrão é `0` (zero).

### <a name="bluetooth"></a>Bluetooth

Essas configurações usam o [CSP da política de Bluetooth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth), que também lista as edições compatíveis do Windows.

- **Bluetooth**: **Bloquear** impede que os usuários habilitem o Bluetooth. **Não configurado** (padrão) permite Bluetooth no dispositivo.
- **Detectabilidade de Bluetooth**: **Bloquear** impede que o dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth. **Não configurado** (padrão) permite que outros dispositivos habilitados para Bluetooth, tais como um fone de ouvido, descubram o dispositivo.
- **Pré-emparelhamento Bluetooth**: **Bloquear** impede que dispositivos Bluetooth específicos emparelhem automaticamente com um dispositivo host. **Não configurado** (padrão) permite o emparelhamento automático com o dispositivo host.
- **Anúncio de Bluetooth**: **Bloquear** impede que o dispositivo envie anúncios via Bluetooth. **Não configurado** (padrão) permite que o dispositivo envie anúncios via Bluetooth.
- **Serviços Bluetooth permitidos**: **adicione** uma lista de serviços e perfis de Bluetooth permitidos usando cadeias de caracteres hexadecimais, tais como `{782AFCFC-7CAA-436C-8BF0-78CD0FFBD4AF}`.

  [O guia de uso de ServicesAllowedList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide) tem mais informações sobre a lista de serviços.

Selecione **OK** para salvar suas alterações.

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento

Essas configurações usam o [CSP da política de contas](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts), que também lista as edições compatíveis do Windows.

- **Conta Microsoft**: **Bloquear** impede que os usuários finais associem uma conta Microsoft ao dispositivo. **Não configurado** (padrão) permite a adição e uso de uma conta Microsoft.
- **Conta não Microsoft**: **Bloquear** impede que os usuários finais adicionem uma conta não Microsoft usando a interface do usuário. **Não configurado** (padrão) permite que os usuários adicionem contas de email que não estejam associadas a uma conta Microsoft.
- **Sincronização de configurações para a conta Microsoft**: **Não configurado** (padrão) permite a sincronização de configurações de dispositivos e aplicativos associadas a uma conta Microsoft entre dispositivos. **Bloquear** impede essa sincronização.
- **Assistente de conexão de Conta Microsoft** : quando definido como **Não configurado** (padrão), os usuários finais podem iniciar e interromper o serviço **Assistente de conexão da conta Microsoft** (wlidsvc). Esse serviço de sistema operacional permite que os usuários entrem em suas respectivas contas Microsoft. **Desabilitar** impede que os usuários finais controlem o serviço de Assistente de Conexão da Microsoft (wlidsvc).

Selecione **OK** para salvar suas alterações.

## <a name="cloud-printer"></a>Impressora de Nuvem

Essas configurações usam o [CSP da política EnterpriseCloudPrint](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-enterprisecloudprint), que também lista as edições compatíveis do Windows.

- **URL de descoberta da impressora**: insira a URL para localizar impressoras na nuvem. Por exemplo, insira `https://cloudprinterdiscovery.contoso.com`.
- **URL de autoridade para acesso à impressora**: insira a URL de ponto de extremidade de autenticação para adquirir tokens OAuth. Por exemplo, insira `https://azuretenant.contoso.com/adfs`.
- **GUID do aplicativo cliente nativo do Azure**: insira o GUID de um aplicativo cliente com permissão para obter tokens OAuth do OAuthAuthority. Por exemplo, insira `E1CF1107-FF90-4228-93BF-26052DD2C714`.
- **URI de recurso do serviço de impressão**: insira o URI de recurso OAuth para o serviço de impressão configurado no portal do Azure. Por exemplo, insira `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Máximo de impressoras para consultar**: insira o número máximo de impressoras a consultar. O valor padrão é `20`.
- **URI de recurso do serviço de descoberta da impressora**: insira o URI de recurso do OAuth para o serviço de descoberta da impressora configurado no portal do Azure. Por exemplo, insira `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Depois de instalar uma [Impressão de Nuvem Híbrida do Windows Server](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview), você poderá definir essas configurações e, em seguida, implantar em dispositivos do Windows.

Selecione **OK** para salvar suas alterações.

## <a name="control-panel-and-settings"></a>Painel de controle e configurações

- **Aplicativo de configurações**: **Bloquear** impede que os usuários finais acessem o aplicativo de configurações do Windows. **Não configurado** (padrão) permite aos usuários abrir o aplicativo de configurações no dispositivo.
  - **Sistema**: **Bloquear** impede o acesso à área de sistema do aplicativo de configurações. **Não configurado** (padrão) permite o acesso.
    - **Modificação de configurações de ligar e hibernar (somente desktop)** : **Bloquear** impede que os usuários finais alterem as configurações de energia e suspensão no dispositivo. **Não configurado** (padrão) permite que os usuários alterem as configurações de energia e suspensão.
  - **Dispositivos**: **Bloquear** impede o acesso à área de dispositivos do aplicativo de configurações no dispositivo. **Não configurado** (padrão) permite o acesso.
  - **Internet e rede**: **Bloquear** impede o acesso à área de Internet e rede do aplicativo de configurações no dispositivo. **Não configurado** (padrão) permite o acesso.
  - **Personalização**: **Bloquear** impede o acesso à área de personalização do aplicativo de configurações no dispositivo. **Não configurado** (padrão) permite o acesso.
  - **Aplicativos**: **Bloquear** impede o acesso à área de aplicativos do aplicativo de configurações no dispositivo. **Não configurado** (padrão) permite o acesso.
  - **Contas**: **Bloquear** impede o acesso à área de contas do aplicativo de configurações no dispositivo. **Não configurado** (padrão) permite o acesso.
  - **Hora e idioma**: **Bloquear** impede o acesso à área de hora e idioma do aplicativo de configurações no dispositivo. **Não configurado** (padrão) permite o acesso.
    - **Modificação do Horário do Sistema**: **Bloquear** impede que usuários finais alterem as configurações de data e hora do dispositivo. **Não configurado** permite que os usuários alterem as configurações.
    - **Modificação de configurações de região** (somente desktop): **Bloquear** impede que usuários finais alterem as configurações de região no dispositivo. **Não configurado** permite que os usuários alterem as configurações.
    - **Modificação de configurações de idioma** (somente desktop): **Bloquear** impede que usuários finais altere as configurações de idioma no dispositivo. **Não configurado** permite que os usuários alterem as configurações.

      [CSP de política de configurações](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings)

  - **Jogos**: **Bloquear** impede o acesso à área de jogos do aplicativo de configurações no dispositivo. **Não configurado** (padrão) permite o acesso.
  - **Facilidade de acesso**: **Bloquear** impede o acesso à área de facilidade de acesso do aplicativo de configurações no dispositivo. **Não configurado** (padrão) permite o acesso.
  - **Privacidade**: **Bloquear** impede o acesso à área de privacidade do aplicativo de configurações no dispositivo. **Não configurado** (padrão) permite o acesso.
  - **Atualização e segurança**: **Bloquear** impede o acesso à área de atualização e segurança do aplicativo de configurações no dispositivo. **Não configurado** (padrão) permite o acesso.

Selecione **OK** para salvar suas alterações.

## <a name="display"></a>Monitor

Essas configurações usam o [CSP da política de exibição](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-display), que também lista as edições compatíveis do Windows.

O ajuste de DPI GDI permite que aplicativos sem reconhecimento de DPI tenham reconhecimento de DPI por monitor.

- **Ativar o ajuste de GDI para aplicativos**: **adicione** os aplicativos herdados em que você deseja o ajuste de DPI de GDI ativado. Por exemplo, insira `filename.exe` ou `%ProgramFiles%\Path\Filename.exe`.

  O ajuste de DPI de GDI está ativado para todos os aplicativos herdados em sua lista.

- **Desligar o ajuste de GDI para aplicativos**: **adicione** os aplicativos herdados em que você deseja o ajuste de DPI de GDI desligado. Por exemplo, insira `filename.exe` ou `%ProgramFiles%\Path\Filename.exe`.

  O ajuste de DPI de GDI está desativado para todos os aplicativos herdados em sua lista.

Você também pode **importar** um arquivo .csv com a lista de aplicativos.

Selecione **OK** para salvar suas alterações.

## <a name="general"></a>Geral

Essas configurações usam o [CSP da política de experiência](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience), que também lista as edições compatíveis do Windows. 

- **Captura de tela** (somente dispositivos móveis): **Bloquear** impede que os usuários finais obtenham capturas de tela no dispositivo. **Não configurado** (padrão) permite o uso desse recurso.
- **Copiar e colar (somente dispositivos móveis)** : **Bloquear** impede que os usuários finais usem o recurso de copiar e colar entre aplicativos no dispositivo. **Não configurado** (padrão) permite o uso desse recurso.
- **Cancelamento de registro manual**: **Bloquear** impede que os usuários finais excluam a conta da empresa usando o painel de controle do local de trabalho no dispositivo. **Não configurado** (padrão) permite o uso desse recurso.

  Essa configuração de política não será aplicada se o computador estiver ingressado no Microsoft Azure AD e o registro automático estiver habilitado.

- **Instalação manual do certificado raiz (somente dispositivos móveis)** : **Bloquear** impede que o usuário instale manualmente os certificados raiz e certificados CAP intermediários. **Não configurado** (padrão) permite o uso desse recurso.
- **Câmera**: **Bloquear** impede que os usuários finais usem a câmera no dispositivo. **Não configurado** (padrão) permite o uso desse recurso.
- **Sincronização de arquivos do OneDrive**: **Bloquear** impede que usuários sincronizem arquivos do dispositivo com o OneDrive. **Não configurado** (padrão) permite o uso desse recurso.
- **Armazenamento removível**: **Bloquear** impede que os usuários finais usem dispositivos de armazenamento externo, assim como cartões SD, com o dispositivo. **Não configurado** (padrão) permite o uso desse recurso.
- **Geolocalização**: **Bloquear** impede que os usuários finais ativem serviços de localização no dispositivo. **Não configurado** (padrão) permite o uso desse recurso.
- **Compartilhamento da Internet**: **Bloquear** impede o compartilhamento da conexão com a Internet no dispositivo. **Não configurado** (padrão) permite o uso desse recurso.
- **Redefinição do telefone**: **Bloquear** impede que os usuários finais apaguem a memória do dispositivo ou realizem nele uma redefinição de fábrica. **Não configurado** (padrão) permite o uso desse recurso.
- **Conexão USB**: **Bloquear** impede o acesso do dispositivo a dispositivos de armazenamento externo por meio de uma conexão USB. **Não configurado** (padrão) permite o uso desse recurso. O carregamento via USB não é afetado por essa configuração.
- **Modo AntiTheft** (somente dispositivos móveis): **Bloquear** impede que os usuários finais selecionem a preferência do modo AntiTheft no dispositivo. **Não configurado** (padrão) permite o uso desse recurso.
- **Cortana**: **Bloquear** desabilita a assistente de voz Cortana no dispositivo. Quando a Cortana estiver desativada, os usuários ainda poderão pesquisar para localizar itens no dispositivo. **Não configurado** (padrão) permite o uso da Cortana.
- **Gravação de voz** (somente dispositivos móveis): **Bloquear** impede que os usuários finais usem o gravador de voz do dispositivo. **Não configurado** (padrão) permite a gravação de voz para aplicativos.
- **Modificação do nome do dispositivo** (somente dispositivos móveis): **Bloquear** impede que usuários finais alterem o nome do dispositivo. **Não configurado** (padrão) permite o uso desse recurso.
- **Adicionar pacotes de provisionamento**: **Bloquear** impede que o agente de configuração de tempo de execução instale os pacotes de provisionamento no dispositivo. **Não configurado** (padrão) permite o uso desse recurso.
- **Remover pacotes de provisionamento**: **Bloquear** impede que o agente de configuração de tempo de execução remova os pacotes de provisionamento do dispositivo. **Não configurado** (padrão) permite o uso desse recurso.
- **Descoberta de dispositivos**: **Bloquear** impede a descoberta de um dispositivo por outros dispositivos. **Não configurado** (padrão) permite o uso desse recurso.
- **Alternador de tarefas (somente dispositivos móveis)** : **Bloquear** impede a alternância de tarefas no dispositivo. **Não configurado** (padrão) permite o uso desse recurso.
- **Diálogo de erro do cartão SIM (somente dispositivo móvel)** : **Bloquear** impedirá a exibição de mensagens de erro no dispositivo se nenhum cartão SIM for detectado. **Não configurado** (padrão) mostra as mensagens de erro.
- **Espaço de trabalho do Ink**: escolha se e como o usuário acessa o Espaço de Trabalho do Ink. Suas opções:
  - **Não configurado** (padrão): habilita o Espaço de Trabalho do Ink e o usuário tem permissão para usá-lo na tela de bloqueio.
  - **Desabilitado na tela de bloqueio**: o Espaço de trabalho do Ink é habilitado e o recurso é ativado. Porém, o usuário não pode acessá-lo na tela de bloqueio.
  - **Desabilitado**: o acesso ao Espaço de Trabalho do Ink é desabilitado. O recurso está desativado.

  [CSP da política WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace)

- **Reimplantação automática**: escolha **Permitir** para que usuários com direitos administrativos possam excluir todos os dados e configurações de usuário usando **Ctrl + Win + R** na tela de bloqueio do dispositivo. O dispositivo é reconfigurado automaticamente e registrado novamente no gerenciamento. **Não configurado** (padrão) impede esse recurso.
- **Exigir que os usuários se conectem à rede durante a instalação de dispositivo**: escolha **Exigir** para que o dispositivo se conecte a uma rede antes de passar da página Rede durante a instalação do Windows. **Não configurado** (padrão) permite que os usuários passem pela página de rede, mesmo se eles não estão conectados a uma rede.

  A configuração entra em vigor na próxima vez que o dispositivo é apagado ou redefinido. Como qualquer outra configuração do Intune, o dispositivo deve ser registrado e gerenciado pelo Intune para receber as definições de configuração. Porém, depois de estar registrado e recebendo políticas, a redefinição do dispositivo impõe a configuração durante a próxima Instalação do Windows.

- **Acesso Direto à Memória**: **Bloquear** impede o DMA (acesso direto à memória) para todas as portas downstream PCI com hot-plug até um usuário entre no Windows. **Habilitado** (padrão) permite o acesso a DMA, mesmo quando um usuário não esteja conectado.

  CSP: [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **Encerrar processos do Gerenciador de Tarefas**: essa configuração determina se não administradores podem usar o Gerenciador de Tarefas para encerrar tarefas. **Bloquear** impede que os usuários padrão (não administradores) usem o Gerenciador de Tarefas para encerrar um processo ou uma tarefa no dispositivo. A opção **Não configurado** (padrão) permite que os usuários padrão encerrem um processo ou uma tarefa usando o Gerenciador de Tarefas.

Selecione **OK** para salvar suas alterações.

## <a name="locked-screen-experience"></a>Experiência na tela bloqueada

- **Notificações da central de ações (somente dispositivos móveis)** : **Bloquear** permite que notificações da Central de Ações apareçam na tela de bloqueio do dispositivo. **Não configurado** (padrão) permite aos usuários escolher quais aplicativos mostram notificações na tela de bloqueio.

  [CSP de AboveLock/AllowActionCenterNotifications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowactioncenternotifications)

- **URL da imagem de tela bloqueada (somente desktop)** : insira a URL para uma imagem no formato JPG, JPEG ou PNG que deve ser usada como papel de parede na tela bloqueada do Windows. Por exemplo, insira `https://contoso.com/image.png`. Essa configuração bloqueia a imagem e não pode ser alterada posteriormente.
- **Tempo limite de tela configurável pelo usuário (somente dispositivos móveis)** : **Permitir** permite que usuários configurem o tempo limite de tela. **Não configurado** (padrão) não dá aos usuários essa opção.

  [CSP de DeviceLock/AllowScreenTimeoutWhileLockedUserConfig](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-allowscreentimeoutwhilelockeduserconfig)

- **Cortana na tela bloqueada** (somente desktop): **Bloquear** impede que usuários interajam com a Cortana quando o dispositivo está na tela de bloqueio. **Não configurado** (padrão) permite a interação com a Cortana.

  [CSP de AboveLock/AllowCortanaAboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowcortanaabovelock)

- **Notificações do sistema na tela bloqueada**: **Bloquear** impede que mensagens de alerta sejam exibidas na tela de bloqueio do dispositivo. **Não configurado** (padrão) permite essas notificações.

  [CSP de AboveLock/AllowToasts](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowtoasts)

- **Tempo limite da tela (somente dispositivos móveis)** : defina a duração (em segundos) da tela de bloqueio até a tela ser desligada. Os valores compatíveis estão ente 11 e 1800. Por exemplo, digite `300` para definir esse tempo limite como 5 minutos.

  [CSP de DeviceLock/ScreenTimeoutWhileLocked](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-screentimeoutwhilelocked)

Selecione **OK** para salvar suas alterações.

## <a name="messaging"></a>Mensagens

Essas configurações usam o [CSP da política de mensagens](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-messaging), que também lista as edições compatíveis do Windows.

- **Sincronização de mensagem (somente dispositivos móveis)** : **Bloquear** desabilita o backup e restauração de mensagens de texto e a sincronização de mensagens entre os dispositivos do Windows. Desabilitar os ajuda a evitar que as informações sejam armazenadas em servidores fora do controle da organização. **Não configurado** (padrão) permite que os usuários alterem essas configurações e sincronizem suas mensagens.
- **MMS (somente dispositivos móveis)** : **Bloquear** desabilita o recurso de envio/recebimento de MMS no dispositivo. Para empresas, use essa política para desabilitar o MMS em dispositivos como parte do requisito de auditoria ou de gerenciamento. **Não configurado** (padrão) permite o envio/recebimento de MMS.
- **RCS (somente dispositivos móveis)** : **Bloquear** desabilita a funcionalidade de envio/recebimento dos RCS (Serviços de Comunicação Avançados) no dispositivo. Para empresas, use essa política para desabilitar o RCS em dispositivos como parte do requisito de auditoria ou de gerenciamento. **Não configurado** (padrão) permite o envio/recebimento de RCS.

Selecione **OK** para salvar suas alterações.

## <a name="microsoft-edge-browser"></a>Navegador Microsoft Edge

Essas configurações usam o [CSP da política de navegador](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser), que também lista as edições compatíveis do Windows.

### <a name="use-microsoft-edge-kiosk-mode"></a>Usar o modo de quiosque do Microsoft Edge

As configurações disponíveis mudam dependendo do que você escolhe. Suas opções:

- **Não** (padrão): o Microsoft Edge não está em execução no modo de quiosque. Todas as configurações do Microsoft Edge estão disponíveis para você alterar e configurar.
- **Sinalização Digital/Interativa (quiosque de aplicativo único)** : filtra configurações do Microsoft Edge aplicáveis ao modo de Quiosque do Microsoft Edge de sinalização Digital/Interativa para uso apenas em quiosques de aplicativo único do Windows 10. Escolha esta configuração para abrir uma tela inteira da URL e mostrar apenas o conteúdo no site. [Configurar sinais digitais](https://docs.microsoft.com/windows/configuration/setup-digital-signage) fornece mais informações sobre esse recurso.
- **Navegação Pública inPrivate (quiosque de aplicativo único)** : filtra configurações do Microsoft Edge aplicáveis ao modo de Quiosque do Microsoft Edge de Navegação Pública InPrivate para uso em quiosques de aplicativo único do Windows 10. Executa uma versão com várias guia do Microsoft Edge.
- **Modo normal (quiosque de vários aplicativos)** : filtra configurações do Microsoft Edge aplicáveis ao modo de Quiosque do Microsoft Edge Normal. Executa uma versão completa do Microsoft Edge com todos os recursos de navegação.
- **Navegação pública (quiosque de vários aplicativos)** : filtra configurações do Microsoft Edge aplicáveis a navegação Pública em um quiosque de vários aplicativos do Windows 10.  Executa uma versão com várias guia do Microsoft Edge InPrivate.

> [!TIP]
> Para obter mais informações sobre o que essas opções fazem, veja [Tipos de configuração de modo de quiosque do Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

Este perfil de restrições de dispositivo está diretamente relacionado ao perfil do quiosque você cria usando as [configurações de quiosque do Windows](kiosk-settings-windows.md). Para resumir:

1. Crie o perfil [Configurações de quiosque do Windows](kiosk-settings-windows.md) para executar o dispositivo no modo de quiosque. Selecione o Microsoft Edge como o aplicativo e defina o Modo de Quiosque do Microsoft Edge no perfil Quiosque.
2. Crie o perfil de restrições de dispositivo descrito neste artigo e configure recursos e configurações específicos permitidos no Microsoft Edge. Escolha o mesmo tipo de modo de quiosque do Microsoft Edge que o selecionado no seu perfil de quiosque ([configurações de quiosque do Windows](kiosk-settings-windows.md)). 

    [Configurações do modo de quiosque compatíveis](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-policies-for-kiosk-mode) é um excelente recurso.

> [!IMPORTANT] 
> Atribua esse perfil do Microsoft Edge aos mesmos dispositivos que seu perfil de quiosque ([configurações de quiosque do Windows](kiosk-settings-windows.md)).

[ConfigureKioskMode CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)

### <a name="start-experience"></a>Experiência de inicialização

- **Abrir o Microsoft Edge com**: escolha quais páginas abrir ao iniciar o Microsoft Edge. Suas opções:
  - **Páginas iniciais personalizadas**: insira as páginas iniciais, por exemplo, `http://www.contoso.com`. O Microsoft Edge carrega as páginas iniciais que você insere.
  - **Página da Nova Guia**: o Microsoft Edge carrega o que está inserido na configuração **URL da Nova Guia**.
  - **Página da última sessão**: o Microsoft Edge carrega a página da última sessão.
  - **Páginas iniciais em configurações de aplicativo local**: o Microsoft Edge abre com a página inicial padrão definida pelo sistema operacional.

- **Permitir que o usuário altere páginas iniciais**: **Sim** (padrão) permite aos usuários alterar as páginas iniciais. Os administradores podem usar `EdgeHomepageUrls` para inserir páginas iniciais que os usuários veem por padrão ao abrir o Microsoft Edge. **Não** impede que os usuários alterem as páginas iniciais.
- **Permitir conteúdo da Web na página da nova guia**: quando definido como **Sim** (padrão), o Microsoft Edge abre a URL inserida na configuração **URL da Nova Guia**. Se configuração **URL da Nova Guia** estiver em branco, o Microsoft Edge abrirá a página da nova guia listada nas configurações do Microsoft Edge. Os usuários podem alterá-la. Quando definido como **Não**, o Microsoft Edge abre uma nova guia com uma página em branco. Os usuários não podem alterá-la.
- **URL da Nova Guia**: insira a URL para abrir na página da nova guia. Por exemplo, insira `https://www.bing.com` ou `https://www.contoso.com`.

- **Botão Página Inicial**: escolha o que acontece ao selecionar o botão Página Inicial. Suas opções:
  - **Páginas iniciais**: abre a opção que você escolheu para a configuração **Abrir o Microsoft Edge com**
  - **Página Nova Guia**: abre a URL que você inseriu na configuração **URL da Nova Guia**.
  - **URL do Botão Página Inicial**: insira a URL para abrir. Por exemplo, insira `https://www.bing.com` ou `https://www.contoso.com`.
  - **Ocultar o botão Página Inicial**: oculta o botão Página Inicial
- **Permitir que usuários alterem o botão página inicial**: **Sim** permite aos usuários alterar o botão página inicial. As alterações do usuário substituem as configurações do administrador para o botão Página Inicial. **Não** (padrão) impede que os usuários alterem o modo como o administrador configurou o botão página inicial.
- **Mostrar página Tela de Apresentação (somente para dispositivos móveis)** : **Sim** (padrão) mostra a página de introdução ao primeiro uso no Microsoft Edge. **Não** impede a exibição da página de introdução na primeira vez que o Microsoft Edge é executado. Esse recurso permite que empresas, tais como as registradas em cenários de emissões zero, bloqueiem esta página.
- **Local da lista de URLs de Tela de Apresentação** (somente Windows 10 Mobile): insira a URL que aponta para o arquivo XML que contém as URLs de página de primeira execução. Por exemplo, insira `https://www.contoso.com/sites.xml`.

- **Atualize o navegador após tempo ocioso**: insira o número de minutos ociosos até que o navegador seja atualizado, de 0 a 1440 minutos. O padrão é de `5` minutos. Quando definido como `0` (zero), o navegador não é atualizado depois de ficar ocioso.

  Essa configuração só está disponível durante a execução em [Navegação Pública InPrivate (quiosque de aplicativo único)](#use-microsoft-edge-kiosk-mode).

- **Permitir pop-ups** (somente desktop): **Sim** (padrão) permite pop-ups no navegador da Web. **Não** impede que janelas pop-up sejam exibidas no navegador.
- **Enviar tráfego da intranet para o Internet Explorer** (somente desktop): **Sim** permite aos usuários abrir sites da intranet no Internet Explorer em vez do Microsoft Edge. Essa configuração é compatibilidade com versões anteriores. **Não** (padrão) permite que os usuários usem o Microsoft Edge.
- **Local da lista de sites do modo Empresarial** (somente em desktop): insira a URL que aponta para o arquivo XML que contém uma lista de sites que são abertos no modo Empresarial. Os usuários não podem alterar essa lista. Por exemplo, insira `https://www.contoso.com/sites.xml`.
- **Mensagem ao abrir sites no Internet Explorer**: use essa opção para configurar o Microsoft Edge para mostrar uma notificação antes de abrir um site no Internet Explorer 11. Suas opções:
  - **Não mostrar a mensagem**: usa o comportamento padrão do sistema operacional, o que pode não mostrar uma mensagem.
  - **Mostrar uma mensagem de que o site está aberto no Internet Explorer 11**: mostrar a mensagem ao abrir sites no Internet Explorer. Os sites abrem no Internet Explorer. 
  - **Mostrar mensagem com a opção para abrir sites no Microsoft Edge**: mostrar a mensagem ao abrir sites no Edge. A mensagem contém um link para **Continuar no Microsoft Edge** de forma que os usuários podem escolher o Microsoft Edge ao invés do IE.

  > [!IMPORTANT]
  > Essa configuração exige que você use a configuração **Localização da lista de sites do modo Empresarial**, a configuração **Enviar o tráfego de intranet para o Internet Explorer** ou ambas.

- **Permitir lista de compatibilidade da Microsoft**: **Sim** (padrão) permite o uso de uma lista de compatibilidade da Microsoft. **Não** impede o uso da lista de compatibilidade da Microsoft no Microsoft Edge. Essa lista da Microsoft ajuda o Microsoft Edge a exibir corretamente sites com problemas de compatibilidade conhecidos.
- **Pré-carregar páginas iniciais e a página Nova Guia**: **Sim** (padrão) usa o comportamento padrão do sistema operacional, que pode ser o de pré-carregar essas páginas. O pré-carregamento reduz o tempo para iniciar o Microsoft Edge e carregar novas guias. **Não** impede o Microsoft Edge de pré-carregar as páginas iniciais e a página Nova Guia.
- **Pré-iniciar páginas iniciais e a página Nova Guia**: **Sim** (padrão) usa o comportamento padrão do sistema operacional, que pode ser o de pré-iniciar essas páginas. A pré-inicialização ajuda o desempenho do Microsoft Edge e reduz o tempo necessário para iniciar o Microsoft Edge. **Não** impede que o Microsoft Edge pré-inicie as páginas iniciais e a página Nova Guia.

Selecione **OK** para salvar suas alterações.

### <a name="favorites-and-search"></a>Favoritos e pesquisa

- **Mostrar Barra de Favoritos**: escolha o que acontece com a barra de favoritos em qualquer página do Microsoft Edge. Suas opções:
  - **Nas páginas inicial e de nova guia**: mostra a barra de favoritos quando o Microsoft Edge é iniciado e em todas as páginas de guia. Os usuários finais podem alterar essa configuração.
  - **Em todas as páginas**: exibe a barra de favoritos em todas as páginas. Os usuários finais não podem alterar essa configuração.
  - **Oculta**: oculta a barra de favoritos em todas as páginas. Os usuários finais não podem alterar essa configuração.
- **Permitir alterações aos favoritos**: **Sim** (padrão) usa o padrão do sistema operacional, que permite aos usuários alterar a lista. **Não** impede que os usuários adicionem, importem, classifiquem ou editem a lista de Favoritos.
  - **Lista de favoritos**: adicionar uma lista de URLs ao arquivo de favoritos. Por exemplo, adicione `http://contoso.com/favorites.html`.
- **Sincronizar favoritos entre navegadores da Microsoft (somente desktop)** : **Sim** força o Windows a sincronizar os favoritos entre o Internet Explorer e o Microsoft Edge. Adições, exclusões, modificações e alterações da ordem dos favoritos são compartilhadas entre navegadores.  **Não** (padrão) usa o padrão do sistema operacional, o que pode dar aos usuários a opção de sincronizar favoritos entre navegadores.
- **Mecanismo de pesquisa padrão**: escolha o mecanismo de pesquisa padrão do dispositivo. Os usuários finais podem alterar esse valor a qualquer momento. Suas opções:
  - Mecanismo de pesquisa nas configurações do cliente do Microsoft Edge
  - Bing
  - Google
  - Yahoo
  - Valor personalizado: em **URL de XML OpenSearch**, insira uma URL HTTPS com o arquivo XML que inclui o nome curto e a URL para o mecanismo de pesquisa, no mínimo. Por exemplo, insira `https://www.contoso.com/opensearch.xml`.
- **Mostrar sugestões de pesquisa**: **Sim** (padrão) permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa na barra de endereços. **Não** impede o uso desse recurso.
- **Permitir alterações ao mecanismo de pesquisa**: **Sim** (padrão) permite aos usuários adicionar novos mecanismos de pesquisa ou alterar o mecanismo de pesquisa padrão no Microsoft Edge. Escolha **Não** para impedir que os usuários personalizem o mecanismo de pesquisa.

  Essa configuração só está disponível durante a execução no [modo Normal (quiosque de vários aplicativos)](#use-microsoft-edge-kiosk-mode).

Selecione **OK** para salvar suas alterações.

### <a name="privacy-and-security"></a>Segurança e privacidade

- **Permitir a navegação InPrivate**: **Sim** (padrão) permite a navegação InPrivate no Microsoft Edge. Depois de fechar todas as guias InPrivate, o Microsoft Edge exclui os dados de navegação do dispositivo. **Não** impede que os usuários finais abram sessões de navegação InPrivate.
- **Salvar o histórico de navegação**: **Sim** (padrão) permite o salvamento do histórico de navegação no Microsoft Edge. **Não** impede que o salvamento do histórico de navegação.
- **Limpar dados de navegação na saída (somente desktop)** : **Sim** limpa o histórico e os dados de navegação quando o usuário sai do Microsoft Edge. **Não** (padrão) usa o padrão do sistema operacional, que pode armazenar em cache os dados de navegação.
- **Sincronizar as configurações do navegador entre os dispositivos do usuário**: escolha como você deseja sincronizar as configurações de navegador entre os dispositivos. Suas opções:
  - **Permitir**: autoriza a sincronização de configurações do navegador Microsoft Edge entre os dispositivos do usuário
  - **Bloquear e habilitar substituição do usuário**: bloquear a sincronização das configurações do navegador Microsoft Edge entre os dispositivos do usuário. Os usuários podem substituir essa configuração.
  - **Bloquear**: bloqueia a sincronização de configurações do navegador Microsoft Edge entre os dispositivos do usuário. Os usuários não podem substituir essa configuração.

Quando a opção "bloquear e habilitar a substituição pelo usuário" é selecionada, o usuário pode substituir a designação de administrador.

- **Permitir Gerenciador de Senhas**: **Sim** (padrão) permite que o Microsoft Edge use automaticamente o Gerenciador de Senhas, que por sua vez permite aos usuários salvar e gerenciar senhas no dispositivo. **Não** impede que o Microsoft Edge use o Gerenciador de Senhas.
- **Cookies**: escolha como lidar com os cookies no navegador da Web. Suas opções:
  - **Permitir**: os cookies são armazenados no dispositivo.
  - **Bloquear todos os cookies**: os cookies não são armazenados no dispositivo.
  - **Bloquear somente cookies de terceiros**: os cookies de parceiros ou terceiros não são armazenados no dispositivo.
- **Permitir preenchimento automático em formulários**: **Sim** (padrão) permite aos usuários alterar as configurações de preenchimento automático no navegador e preencher os campos de formulário automaticamente. **Não** desabilita o recurso de Preenchimento Automático no Microsoft Edge.
- **Enviar cabeçalhos Do Not Track**: **Sim** envia cabeçalhos Do Not Track a sites que solicitam informações de acompanhamento (recomendado). **Não** (padrão) não envia cabeçalhos, o que permite que os sites rastreiem o usuário. O usuário pode configurar essa opção.
- **Mostrar endereço IP de localhost WebRTC**: **Sim** (padrão) permite que os endereços IP de localhost dos usuários sejam mostrados ao fazer chamadas telefônicas usando esse protocolo. **Não** impede que o endereço IP do localhost dos usuários seja mostrado. 
- **Permitir a coleta de dados de bloco dinâmico**: **Sim** (padrão) permite que o Microsoft Edge colete informações de blocos dinâmicos fixados no menu Iniciar. **Não** impede a coleta dessas informações, o que pode fornecer aos usuários uma experiência limitada.
- **O usuário pode substituir erros de certificado**: **Sim** (padrão) permite aos usuários acessar sites que têm erros de protocolo SSL/TLS. **Não** (recomendado para aumentar a segurança) impede que os usuários acessem sites com erros de protocolo SSL ou TLS.

Selecione **OK** para salvar suas alterações.

### <a name="additional"></a>Adicional

- **Permitir navegador Microsoft Edge** (somente dispositivos móveis): **Sim** (padrão) permite o uso do navegador da Web Microsoft Edge no dispositivo móvel. **Não** impede o uso do Microsoft Edge no dispositivo. Se você escolher **Não**, as outras configurações individuais serão aplicadas apenas ao desktop.
- **Permitir lista suspensa de barra de endereços**: **Sim** (padrão) permite que o Microsoft Edge mostre a lista suspensa de barra de endereços com uma lista de sugestões. **Não** impede que o Microsoft Edge exiba uma lista de sugestões em uma lista suspensa quando você digita. Quando definido como **Não**, você:
  - Ajuda a minimizar o uso de largura de banda da rede entre o Microsoft Edge e os serviços da Microsoft.
  - Desabilite a opção **Mostrar sugestões de pesquisa e de site conforme eu digitar** em Microsoft Edge > Configurações.
- **Permitir modo de tela inteira**: **Sim** (padrão) permite que o Microsoft Edge use o modo de tela inteira, que mostra apenas o conteúdo da Web e oculta a interface do usuário do Microsoft Edge. **Não** impede o uso do modo de tela inteira no Microsoft Edge.
- **Permitir página Sobre sinalizadores** **Sim** (padrão) usa o padrão do sistema operacional, que pode permitir o acesso à página `about:flags`. A página `about:flags` permite que os usuários alterem as configurações do desenvolvedor e habilitem recursos experimentais. **Não** impede que os usuários finais acessem a página `about:flags` no Microsoft Edge.
- **Permitir ferramentas para desenvolvedores**: **Sim** (padrão) permite que os usuários usem as Ferramentas de Desenvolvedor F12 para criar e depurar páginas da Web por padrão. **Não** impede que os usuários finais usando as Ferramentas de Desenvolvedor F12.
- **Permitir JavaScript**: **Sim** (padrão) permite que scripts, tais como JavaScript, sejam executados no navegador Microsoft Edge. **Não** impede a execução de scripts Java no navegador.
- **O usuário pode instalar extensões**: **Sim** (padrão) permite aos usuários finais instalarem extensões do Microsoft Edge no dispositivo. **Não** impede a instalação.
- **Permitir sideload de extensões do desenvolvedor**: **Sim** (padrão) usa o padrão do sistema operacional, que pode permitir o sideload. O sideload instala e executa extensões não verificadas. **Não** impede que o Microsoft Edge faça sideload usando o recurso **Carregar extensões**. Ele não impede o sideload de extensões por outros meios, tais como o PowerShell.
- **Extensões necessárias**: escolher quais extensões não podem ser desativadas pelos usuários finais no Microsoft Edge. Insira os nomes das famílias de pacotes e selecione **Adicionar**. Algumas diretrizes podem ser encontradas em [Localizar um PFN (nome da família de pacotes)](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn).

  Você também pode **Importar** um arquivo CSV que inclui os nomes das famílias de pacotes. Ou então, **exporte** os nomes de família de pacotes que você inserir.

Selecione **OK** para salvar suas alterações.

## <a name="network-proxy"></a>Proxy de rede

Essas configurações usam o [CSP da política de NetworkProxy](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp), que também lista as edições compatíveis do Windows.

- **Detectar automaticamente as configurações de proxy**: **Bloquear** desabilita a detecção automática de um script PAC (configuração automática de proxy) pelo dispositivo. **Não configurado** (padrão) habilita esse recurso. Quando essa opção é habilitada, o dispositivo tenta localizar o caminho para um script PAC.
- **Usar script de proxy**: escolha **Permitir** para inserir um caminho para o script PAC a fim de configurar o servidor proxy. **Não configurado** (padrão) não permite que você insira a URL para um script PAC.
  - **Configurar URL do endereço do script**: insira a URL de um script PAC que você deseja usar para configurar o servidor proxy.
- **Usar servidor proxy manual**: escolha **Permitir** para inserir manualmente o nome ou endereço IP e número da porta TCP de um servidor proxy. **Não configurado** (padrão) não permite que você insira manualmente os detalhes de um servidor proxy.
  - **Endereço**: insira o nome ou o endereço IP do servidor proxy.
  - **Número da porta**: insira o número de porta de seu servidor proxy.
  - **Exceções de proxy**: insira todas as URLs que não devem usar o servidor proxy. Use um ponto e vírgula para separar cada item.
  - **Ignorar servidor proxy para endereços locais**: **Não configurado** (padrão) impede o uso de um servidor proxy para endereços locais na intranet. **Permitir** usa um servidor proxy para endereços locais.

Selecione **OK** para salvar suas alterações.

## <a name="password"></a>Senha

Essas configurações usam o [CSP da política de DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock), que também lista as edições compatíveis do Windows.

- **Senha**: **Exigir** que o usuário final insira uma senha para acessar o dispositivo. **Não configurado** (padrão) permite o acesso ao dispositivo sem uma senha.
  - **Tipo de senha necessária**: escolha o tipo de senha. Suas opções:
    - **Não configurado**: a senha pode incluir letras e números.
    - **Numérica**: a senha só pode conter números.
    - **Alfanumérica**: a senha precisa ser uma mistura de letras e números.
  - **Tamanho mínimo da senha**: insira o número mínimo de caracteres necessários, de 4 a 16. Por exemplo, digite `6` exigir um comprimento de senha de pelo menos seis caracteres.
  
    > [!IMPORTANT]
    > Quando o requisito de senha é alterado em uma área de trabalho do Windows, os usuários são afetados na próxima vez que fizerem logon, como quando o dispositivo passa de ocioso para ativo. Os usuários com senhas que atendam ao requisito ainda serão solicitados a alterar suas senhas.
    
  - **Número de falhas de conexão antes de apagar o dispositivo**: insira o número de falhas de autenticação repetidas permitidas antes que o dispositivo possa ser apagado, até 11. O número válido inserido dependerá da edição. [CSP DeviceLock/MaxDevicePasswordFailedAttempts](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts) lista os valores com suporte. `0` (zero) pode desabilitar a funcionalidade de apagamento do dispositivo.

    Essa configuração também tem um impacto diferente, dependendo da edição. Para obter detalhes específicos dessa configuração, confira o [CSP de DeviceLock/MaxDevicePasswordFailedAttempts](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts).

  - **Máximo de minutos de inatividade até o bloqueio de tela**: insira o período que um dispositivo deve permanecer ocioso antes de a tela ser bloqueada.
  - **Expiração de senha (dias)** : insira o período de tempo em dias após o qual a senha do dispositivo deve ser alterada, de 1 a 365. Por exemplo, para alterar a senha após 90 dias, insira `90`.
  - **Evite a reutilização de senhas anteriores**: insira o número de senhas usadas anteriormente que não podem ser utilizadas, de 1 a 24. Por exemplo, insira `5` para que os usuários não possam definir uma nova senha como a senha atual nem como nenhuma das quatro senhas anteriores.
  - **Exigir senha quando o dispositivo retorna do estado inativo** (Mobile e Holographic): **Exigir** especifica que o usuário deve inserir uma senha para desbloquear o dispositivo após retornar de um estado ocioso. **Não configurado** (padrão) não requer um PIN ou senha quando o dispositivo retoma do estado ocioso.
  - **Senhas simples**: defina como **Bloquear** para que os usuários não possam criar uma senha simples como `1234` ou `1111`. Definido como **Não configurado** para permitir que os usuários criem senhas como `1234` ou `1111`. Essa configuração também permite ou bloqueia o uso de senhas de imagem do Windows.
- **Criptografia automática durante AADJ**: **Bloquear** impede a criptografia automática de dispositivo de BitLocker quando o dispositivo está preparado para o primeiro uso quando o dispositivo está ingressado no Azure AD. **Não configurado** (padrão) usa o padrão do sistema operacional, que pode habilitar a criptografia. Mais sobre [Criptografia do dispositivo BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption).

  [Security/PreventAutomaticDeviceEncryptionForAzureADJoinedDevices CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-preventautomaticdeviceencryptionforazureadjoineddevices)

- **Política FIPS (Padrão Federal de Processamento de Informações)** : **Permitir** usa a política FIPS (Padrão Federal de Processamento de Informações), que é um padrão do governo dos EUA para criptografia, hash e assinatura. **Não configurado** (padrão) usa o padrão do sistema operacional, que não usa FIPS.

  [Cryptography/AllowFipsAlgorithmPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-cryptography#cryptography-allowfipsalgorithmpolicy)

- **Autenticação de dispositivo Windows Hello**: **Permitir** aos usuários usar um dispositivo complementar Windows Hello, como um telefone, pulseira fitness ou dispositivo de IoT para entrar em um computador com Windows 10. **Não configurado** (padrão) usa o padrão do sistema operacional, que pode impedir que dispositivos complementares do Windows Hello autentiquem-se com o Windows.

  [Authentication/AllowSecondaryAuthenticationDevice CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowsecondaryauthenticationdevice)

- **Conexão na Web**: habilita suporte de entrada no Windows para provedores federados que não são dos Serviços de Federação do Active Directory (AD FS), tais como o SAML (Security Assertion Markup Language). SAML usa tokens de seguros que fornecem a experiência de SSO (logon único) a navegadores da Web. Suas opções:

  - **Não configurado** (padrão): usa o padrão do sistema operacional no dispositivo.
  - **Habilitado**: o provedor de Credenciais da Web está habilitado para entrar.
  - **Desabilitado**: o provedor de Credenciais da Web está desabilitado para entrar.

  [Authentication/EnableWebSignIn CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-enablewebsignin)

- **Domínio de locatário do Azure AD preferencial**: insira um nome de domínio existente na sua organização do Azure AD. Quando os usuários nesse domínio entram, eles não precisam digitar o nome de domínio. Por exemplo, insira `contoso.com`. Usuários no domínio `contoso.com` podem entrar usando seu nome de usuário, como `abby` em vez de `abby@contoso.com`.

  [Authentication/PreferredAadTenantDomainName CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-preferredaadtenantdomainname)

Selecione **OK** para salvar suas alterações.

## <a name="per-app-privacy-exceptions"></a>Exceções de privacidade por aplicativo

Você pode adicionar aplicativos que devem ter um comportamento de privacidade diferente do definido em "Privacidade padrão".

- **Nome do Pacote**: nome de família do pacote de aplicativos.
- **Nome do Aplicativo**: o nome do aplicativo.

### <a name="exceptions"></a>Exceções

- **Informações de conta**: defina se este aplicativo pode acessar o nome de usuário, a imagem e outras informações de contato.
- **Aplicativos em segundo plano**: defina se este aplicativo pode ser executado em segundo plano.
- **Calendário**: defina se este aplicativo pode acessar o calendário.
- **Histórico de chamadas**: defina se este aplicativo pode acessar o histórico de chamadas.
- **Câmera**: defina se este aplicativo pode acessar a câmera.
- **Contatos**: defina se este aplicativo pode acessar os contatos.
- **Email**: defina se este aplicativo pode acessar e enviar emails.
- **Local**: defina se este aplicativo pode acessar informações de localização.
- **Mensagens**: defina se este aplicativo pode ler ou enviar mensagens de texto ou MMS.
- **Microfone**: defina se este aplicativo pode usar o microfone.
- **Movimento**: defina se este aplicativo pode acessar informações de movimentação do dispositivo.
- **Notificações**: defina se este aplicativo pode acessar as notificações.
- **Telefone**: defina se este aplicativo pode acessar o telefone.
- **Rádios**: alguns aplicativos usam rádios (por exemplo, Bluetooth) em seu dispositivo para enviar e receber dados, e precisam ativar ou desativar essas rádios. Defina se este aplicativo pode controlar essas rádios.
- **Tarefas**: defina se este aplicativo pode acessar suas tarefas.
- **Dispositivos confiáveis**: escolha se esse aplicativo pode usar dispositivos confiáveis. Os dispositivos confiáveis são o hardware que você já conectou ou o que acompanha o dispositivo. Por exemplo, usar TVs, projetores e assim por diante como dispositivos confiáveis.
- **Comentários e diagnóstico**: defina se este aplicativo pode acessar informações de diagnóstico.
- **Sincronização com dispositivos**: escolha se este aplicativo pode compartilhar e sincronizar automaticamente informações com dispositivos sem fio que não emparelham explicitamente com este dispositivo.

Selecione **OK** para salvar suas alterações.

## <a name="personalization"></a>Personalização

Essas configurações usam o [CSP da política de personalização](https://docs.microsoft.com/windows/client-management/mdm/personalization-csp), que também lista as edições compatíveis do Windows.

- **URL da imagem de tela de fundo da área de trabalho (somente Desktop)** : insira a URL para uma imagem no formato .jpg, .jpeg ou .png que deseja usar como o papel de parede da área de trabalho do Windows. Os usuários não podem alterar a foto. Por exemplo, insira `https://contoso.com/logo.png`.

Selecione **OK** para salvar suas alterações.

## <a name="printer"></a>Impressora

- **Impressoras**: lista de impressoras locais que foram adicionadas.
- **Impressora padrão**: defina a impressora padrão.
- **Acesso de usuário à adição de novas impressoras**: permita ou bloqueie o uso de impressoras locais.

Selecione **OK** para salvar suas alterações.

## <a name="privacy"></a>Privacidade

Essas configurações usam o [CSP da política de privacidade](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy), que também lista as edições compatíveis do Windows.

- **Personalização de entrada**: **Bloquear** impede o uso de voz para ditado e para comunicação com a Cortana e outros aplicativos que usam o reconhecimento de fala baseado em nuvem da Microsoft. Ele é desabilitado e os usuários não podem habilitar as configurações de uso de reconhecimento de fala online. **Não configurado** (padrão) permite aos usuários escolher. Se você permitir esses serviços, a Microsoft poderá coletar dados de voz para melhorar o serviço.
- **Aceitação automática das solicitações de consentimento do usuário de privacidade e emparelhamento**: escolha **Permitir** para que o Windows possa aceitar automaticamente mensagens de consentimento de emparelhamento e privacidade ao executar aplicativos. **Não configurado** (padrão) impede a aceitação automática da janela de consentimento do usuário para privacidade e emparelhamento ao abrir aplicativos.
- **Publicar as atividades do usuário**: **bloquear** evita o compartilhamento de experiências e a descoberta de recursos usados recentemente no feed de atividade. **Não configurado** (padrão) habilita esse recurso para aplicativos poderem publicar as atividades do usuário final.
- **Apenas atividades locais**: **bloquear** evita o compartilhamento de experiências e a descoberta de recursos usados recentemente no alternador de tarefas com base somente em atividades locais. **Não configurado** (padrão) habilita esse recurso.

Você pode configurar as informações que todos os aplicativos no dispositivo podem acessar. Defina também as exceções de acordo com o aplicativo que usa **Exceções de privacidade por aplicativo**.

Selecione **OK** para salvar suas alterações.

### <a name="exceptions"></a>Exceções

- **Informações de conta**: defina se este aplicativo pode acessar o nome de usuário, a imagem e outras informações de contato.
- **Aplicativos em segundo plano**: defina se este aplicativo pode ser executado em segundo plano.
- **Calendário**: defina se este aplicativo pode acessar o calendário.
- **Histórico de chamadas**: defina se este aplicativo pode acessar o histórico de chamadas.
- **Câmera**: defina se este aplicativo pode acessar a câmera.
- **Contatos**: defina se este aplicativo pode acessar os contatos.
- **Email**: defina se este aplicativo pode acessar e enviar emails.
- **Local**: defina se este aplicativo pode acessar informações de localização.
- **Mensagens**: defina se este aplicativo pode ler ou enviar mensagens de texto ou MMS.
- **Microfone**: defina se este aplicativo pode usar o microfone.
- **Movimento**: defina se este aplicativo pode acessar informações de movimentação do dispositivo.
- **Notificações**: defina se este aplicativo pode acessar as notificações.
- **Telefone**: defina se este aplicativo pode acessar o telefone.
- **Rádios**: alguns aplicativos usam rádios (por exemplo, Bluetooth) em seu dispositivo para enviar e receber dados, e precisam ativar ou desativar essas rádios. Defina se este aplicativo pode controlar essas rádios.
- **Tarefas**: defina se este aplicativo pode acessar suas tarefas.
- **Dispositivos confiáveis**: escolha se esse aplicativo pode usar dispositivos confiáveis. Os dispositivos confiáveis são o hardware que você já conectou ou o que acompanha o dispositivo. Por exemplo, usar TVs, projetores e assim por diante como dispositivos confiáveis.
- **Comentários e diagnóstico**: defina se este aplicativo pode acessar informações de diagnóstico.
- **Sincronização com dispositivos** – defina se este aplicativo pode compartilhar e sincronizar automaticamente informações com dispositivos sem fio que não emparelham explicitamente com este computador, tablet ou telefone.

Selecione **OK** para salvar suas alterações.

## <a name="projection"></a>Projeção

Essas configurações usam o [CSP da política WirelessDisplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wirelessdisplay), que também lista as edições compatíveis do Windows.

- **Entrada do usuário de receptores de vídeo sem fio**: **Bloquear** impede a entrada do usuário de receptores de vídeo sem fio. **Não configurado** (padrão) permite que um vídeo sem fio envie entrada de teclado, de mouse, à caneta e por toque de volta para o dispositivo de origem.
- **Projeção para este computador**: **Bloquear** impede que outros dispositivos localizem o dispositivo para projeção. **Não configurado** (padrão) permite que o dispositivo seja detectável e pode projetar para o dispositivo acima da tela de bloqueio.
- **Exigir um PIN para emparelhamento**: escolha **Exigir** para sempre solicitar um PIN durante a conexão com um dispositivo de projeção. **Não configurado** (padrão) não requer um PIN para emparelhar o dispositivo a um dispositivo de projeção.

Selecione **OK** para salvar suas alterações.

## <a name="reporting-and-telemetry"></a>Relatório e telemetria

- **Compartilhar dados de uso**: escolha o nível de dados de diagnóstico que são enviados. Suas opções:
  - **Não configurado**: nenhum dado é compartilhado.
  - **Segurança**: informações necessárias para ajudar a manter o Windows mais seguro, incluindo dados sobre as configurações de componente de telemetria e experiência do usuário conectado, a ferramenta de Remoção de Software Mal-intencionado e o Windows Defender.
  - **Básico**: informações básicas do dispositivo, incluindo dados de nível de segurança, compatibilidade de aplicativos, dados de uso do aplicativo e dados relacionados à qualidade.
  - **Avançado**: informações adicionais, incluindo: como o Windows, Windows Server, System Center e aplicativos são usados, como eles se comportam, dados de confiabilidade avançados e dados dos níveis Básico e de Segurança.
  - **Completo**: todos os dados necessários para identificar e ajudar a corrigir problemas, além de dados dos níveis de Segurança, Básico e Avançado.

  [CSP System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)

- **Enviar dados de navegação do Microsoft Edge para a Análise do Microsoft 365**: para usar esse recurso, defina as configurações de **Compartilhar dados de uso** como **Avançado** ou **Completo**. Esse recurso controla quais dados de dispositivos corporativos com uma ID comercial configurada o Microsoft Edge envia para a Análise do Microsoft 365. Suas opções:
  - **Não configurado**: usa o padrão do sistema operacional, que pode não enviar dados do histórico de navegação
  - **Enviar somente dados da Intranet**: permite que o administrador envie o histórico de dados da Intranet
  - **Enviar somente dados da Internet**: permite que o administrador envie o histórico de dados da Internet
  - **Enviar dados da Intranet e da Internet**: permite que o administrador envie o histórico de dados da Intranet e da Internet

  [CSP Browser/ConfigureTelemetryForMicrosoft365Analytics CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configuretelemetryformicrosoft365analytics)

- **Servidor proxy de telemetria**: insira o FQDN (nome de domínio totalmente qualificado) ou o endereço IP de um servidor proxy para encaminhar solicitações de Experiências e Telemetria de Usuário Conectado usando uma conexão SSL (Secure Sockets Layer). O formato para essa configuração é *servidor*:*porta*. Se o proxy nomeado falhar ou se não for inserido um proxy durante a habilitação dessa política, os dados de Experiências e Telemetria do Usuário Conectado não serão enviados e permanecerão no dispositivo local.

  Formatos de exemplo:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

  [CSP System/TelemetryProxy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-telemetryproxy)

Selecione **OK** para salvar suas alterações.

## <a name="search"></a>Pesquisar

Essas configurações usam o [CSP da política de pesquisa](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search), que também lista as edições compatíveis do Windows. 

- **Pesquisa Segura (dispositivo móvel)** : controla como a Cortana filtra o conteúdo adulto nos resultados da pesquisa. Suas opções:
  - **Definido pelo usuário**: permite que usuários finais escolham suas próprias configurações.
  - **Restrito**: filtragem mais elevada contra conteúdo para adulto.
  - **Moderado**: filtragem moderada contra conteúdo para adulto. Os resultados da pesquisa válidos não são filtrados.
- **Exibir resultados da Web na pesquisa**: quando definido como **Bloquear**, os usuários não podem pesquisar e os resultados da Web não são mostrados na pesquisa. **Não configurado** (padrão) permite que os usuários pesquisem a Web e os resultados são mostrados no dispositivo.

Selecione **OK** para salvar suas alterações.

## <a name="start"></a>Inicie o

Essas configurações usam o [CSP da política de início](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start), que também lista as edições compatíveis do Windows.  

- **Layout do menu Iniciar**: substitui o layout do Menu Iniciar padrão e personaliza o Menu Iniciar em dispositivos desktop. Carregue um arquivo XML que inclua suas personalizações, incluindo a ordem em que os aplicativos são listados, entre outros. Os usuários não podem alterar o layout do menu Iniciar que você inserir.
- **Fixar sites da Web como blocos no menu Iniciar**: importe imagens do Microsoft Edge exibidas como links no menu Iniciar do Windows para dispositivos de área de trabalho.
- **Desafixar aplicativos da barra de tarefas**: **Bloquear** impede que usuários desafixem aplicativos da barra de tarefas. **Não configurado** (padrão) permite que os usuários desafixem aplicativos da barra de tarefas.
- **Troca rápida de usuário**: **Bloquear** impede a alternância entre usuários que estão conectados simultaneamente sem fazer logoff. **Não configurado** (padrão) mostra a opção **Alternar usuário** no bloco do usuário.
- **Aplicativos mais usados**: **Bloquear** oculta os aplicativos mais usados no menu Iniciar. Isso também desabilita a alternância correspondente no aplicativo Configurações. **Não configurado** (padrão) mostra os aplicativos mais usados.
- **Aplicativos recentemente adicionados**: **Bloquear** oculta os aplicativos recentemente adicionados do menu Iniciar. Isso também desabilita a alternância correspondente no aplicativo Configurações. **Não configurado** (padrão) mostra os aplicativos adicionados recentemente no menu Iniciar.
- **Iniciar modo de tela**: escolha como a tela inicial é exibida. Suas opções:
  - **Definido pelo usuário**: não força o tamanho do menu Iniciar. Os usuários podem definir o tamanho.
  - **Tela inteira**: força um tamanho de tela inteira do menu Iniciar.
  - **Não tela inteira**: força um tamanho que não é de tela inteira para o menu Iniciar.
- **Itens abertos recentemente nas Listas de Atalhos**: **Bloquear** oculta as listas de atalhos recentes no menu Iniciar e na barra de tarefas. Isso também desabilita a alternância correspondente no aplicativo Configurações. **Não configurado** (padrão) mostra os itens abertos recentemente nas listas de atalhos.
- **Lista de aplicativos**: escolha como todas as listas de aplicativos são mostradas. Suas opções:
  - **Definido pelo usuário**: nenhuma configuração é forçada. Os usuários escolhem como a lista de aplicativos é mostrada no dispositivo.
  - **Recolher**: oculta a lista de todos os aplicativos.
  - **Recolher e desabilitar o aplicativo de Configurações**: oculta a lista de todos os aplicativos e desabilita **Mostrar lista de aplicativos no menu Iniciar** no aplicativo de Configurações.
  - **Remover e desabilitar o aplicativo de Configurações**: oculta a lista de todos os aplicativos, remove o botão todos os aplicativos e desabilita **Mostrar lista de aplicativos no menu Iniciar** no aplicativo de Configurações.
- **Botão de energia**: **Bloquear** oculta o botão de energia no menu Iniciar. **Não configurado** (padrão) mostra o botão de energia.
- **Bloco de Usuário**: **Bloquear** oculta o bloco de usuário no menu Iniciar. **Não configurado** (padrão) mostra o bloco do usuário e também define as configurações a seguir:
  - **Bloqueio**: **Bloquear** oculta a exibição da opção **Bloqueio** no bloco do usuário no menu Iniciar. **Não configurado** (padrão) mostra a opção **Bloqueio**.
  - **Sair**: **Bloquear** oculta a exibição da opção **Sair** no bloco do usuário no menu Iniciar. **Não configurado** (padrão) mostra a opção **Sair**.
- **Desligar**: **Bloquear** oculta as opções **Atualizar e desligar** e **Desligar** do botão de energia no menu Iniciar. **Não configurado** (padrão) mostra essas opções.
- **Suspender**: **Bloquear** oculta a opção **Suspender** no botão de energia no menu Iniciar. **Não configurado** (padrão) mostra essa opção.
- **Hibernar**: **Bloquear** oculta a opção **Hibernar** no botão de energia no menu Iniciar. **Não configurado** (padrão) mostra essa opção.
- **Alternar Conta**: **Bloquear** oculta a opção **Alternar conta** no bloco do usuário no menu Iniciar. **Não configurado** (padrão) mostra essa opção.
- **Opções de Reinicialização**: **Bloquear** oculta as opções **Atualizar e desligar** e **Reiniciar** do botão de energia no menu Iniciar. **Não configurado** (padrão) mostra essas opções.
- **Documentos em Iniciar**: oculta ou mostra a pasta Documentos no menu Iniciar do Windows. Suas opções:
  - **Não configurado** (padrão): nenhuma configuração é forçada. Os usuários optam por mostrar ou ocultar o atalho.
  - **Ocultar**: o atalho é oculto e desabilita a configuração no aplicativo de Configurações.
  - **Mostrar**: o atalho é mostrado e desabilita a configuração no aplicativo de Configurações.
- **Downloads em Iniciar**: oculta ou mostra a pasta Downloads no menu Iniciar do Windows. Suas opções:
  - **Não configurado** (padrão): nenhuma configuração é forçada. Os usuários optam por mostrar ou ocultar o atalho.
  - **Ocultar**: o atalho é oculto e desabilita a configuração no aplicativo de Configurações.
  - **Mostrar**: o atalho é mostrado e desabilita a configuração no aplicativo de Configurações.
- **Explorador de Arquivos em Iniciar**: oculta ou mostra o aplicativo Explorador de Arquivos no menu Iniciar do Windows. Suas opções:
  - **Não configurado** (padrão): nenhuma configuração é forçada. Os usuários optam por mostrar ou ocultar o atalho.
  - **Ocultar**: o atalho é oculto e desabilita a configuração no aplicativo de Configurações.
  - **Mostrar**: o atalho é mostrado e desabilita a configuração no aplicativo de Configurações.
- **HomeGroup em Iniciar**: oculta ou mostra o atalho HomeGroup no menu Iniciar do Windows. Suas opções:
  - **Não configurado** (padrão): nenhuma configuração é forçada. Os usuários optam por mostrar ou ocultar o atalho.
  - **Ocultar**: o atalho é oculto e desabilita a configuração no aplicativo de Configurações.
  - **Mostrar**: o atalho é mostrado e desabilita a configuração no aplicativo de Configurações.
- **Música em Iniciar**: oculta ou mostra a pasta Música no menu Iniciar do Windows. Suas opções:
  - **Não configurado** (padrão): nenhuma configuração é forçada. Os usuários optam por mostrar ou ocultar o atalho.
  - **Ocultar**: o atalho é oculto e desabilita a configuração no aplicativo de Configurações.
  - **Mostrar**: o atalho é mostrado e desabilita a configuração no aplicativo de Configurações.
- **Rede em Iniciar**: oculta ou mostra a opção Rede no menu Iniciar do Windows. Suas opções:
  - **Não configurado** (padrão): nenhuma configuração é forçada. Os usuários optam por mostrar ou ocultar o atalho.
  - **Ocultar**: o atalho é oculto e desabilita a configuração no aplicativo de Configurações.
  - **Mostrar**: o atalho é mostrado e desabilita a configuração no aplicativo de Configurações.
- **Pasta Pessoal em Iniciar**: oculta ou mostra a pasta Pessoal no menu Iniciar do Windows. Suas opções:
  - **Não configurado** (padrão): nenhuma configuração é forçada. Os usuários optam por mostrar ou ocultar o atalho.
  - **Ocultar**: o atalho é oculto e desabilita a configuração no aplicativo de Configurações.
  - **Mostrar**: o atalho é mostrado e desabilita a configuração no aplicativo de Configurações.
- **Imagens em Iniciar**: oculta ou mostra a pasta de imagens no menu Iniciar do Windows. Suas opções:
  - **Não configurado** (padrão): nenhuma configuração é forçada. Os usuários optam por mostrar ou ocultar o atalho.
  - **Ocultar**: o atalho é oculto e desabilita a configuração no aplicativo de Configurações.
  - **Mostrar**: o atalho é mostrado e desabilita a configuração no aplicativo de Configurações.
- **Configurações em Iniciar**: oculta ou mostra o atalho Configurações no menu Iniciar do Windows. Suas opções:
  - **Não configurado** (padrão): nenhuma configuração é forçada. Os usuários optam por mostrar ou ocultar o atalho.
  - **Ocultar**: o atalho é oculto e desabilita a configuração no aplicativo de Configurações.
  - **Mostrar**: o atalho é mostrado e desabilita a configuração no aplicativo de Configurações.
- **Vídeos em Iniciar**: oculta ou mostra a pasta de vídeos no menu Iniciar do Windows. Suas opções:
  - **Não configurado** (padrão): nenhuma configuração é forçada. Os usuários optam por mostrar ou ocultar o atalho.
  - **Ocultar**: o atalho é oculto e desabilita a configuração no aplicativo de Configurações.
  - **Mostrar**: o atalho é mostrado e desabilita a configuração no aplicativo de Configurações.

Selecione **OK** para salvar suas alterações.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **SmartScreen para Microsoft Edge**: **Exigir** desativa o Windows Defender SmartScreen e impede os usuários de ativá-lo. A opção **Não configurado** (padrão) ativa o SmartScreen. Ajuda a proteger os usuários contra possíveis ameaças e a impedir que os usuários o desativem.

  O Microsoft Edge usa o Windows Defender SmartScreen (ativado) para proteger os usuários contra possíveis golpes de phishing e software mal-intencionado.

  [CSP Browser/AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)

- **Acesso a sites mal-intencionados**: **Bloquear** impede que os usuários ignorem os avisos de Filtro do Windows Defender SmartScreen e impede-os de visitar o site. **Não configurado** (padrão) permite aos usuários ignorar os avisos e continuar para o site.

  [CSP Browser/PreventSmartScreenPromptOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride)

- **Download de arquivo não verificado**: **Bloquear** impede que os usuários ignorarem os avisos de Filtro do Windows Defender SmartScreen e os impede de baixar arquivos não verificados. **Não configurado** (padrão) permite aos usuários ignorar os avisos e continuar a baixar arquivos não verificados.

  [CSP Browser/PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles)

Selecione **OK** para salvar suas alterações.

## <a name="windows-spotlight"></a>Destaque do Windows

Essas configurações usam o [CSP da política de experiência](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience), que também lista as edições compatíveis do Windows.

- **Destaque do Windows**: **Bloquear** desativa o Destaque do Windows na tela de bloqueio, Dicas do Windows, recursos do consumidor da Microsoft e outros recursos relacionados. Se sua meta for minimizar o tráfego de rede de dispositivos, defina isso como **Bloquear**. **Não configurado** (padrão) permite o uso de recursos de destaque do Windows e seu controle pelos usuários finais. Quando habilitado, você também pode permitir ou bloquear as seguintes configurações:

  - **Destaque do Windows na tela de bloqueio**: **Bloquear** impede que o Destaque do Windows exiba informações na tela de bloqueio do dispositivo. **Não configurado** (padrão) habilita esse recurso.
  - **Sugestões de terceiros no Destaque do Windows**: **Bloquear** impede que o Destaque do Windows sugira conteúdo que não tenha sido publicado pela Microsoft. **Não configurado** (padrão) permite sugestões de aplicativos e conteúdo de editores de software parceiros nos recursos de Destaque do Windows como o destaque da tela de bloqueio, aplicativos sugeridos no menu Iniciar e dicas do Windows.
  - **Recursos de Consumidor**: **Bloquear** desativa experiências que normalmente são apenas para consumidores, como Sugestões de início, Notificações de associação, instalação de aplicativos após a configuração inicial pelo usuário e redirecionamento de blocos. **Não configurado** (padrão) permite esses recursos.
  - **Dicas do Windows**: **Bloquear** desabilita pop-ups de Dicas do Windows. **Não configurado** (padrão) permite a exibição de Dicas do Windows.
  - **Destaque do Windows na central de ações**: **Bloquear** impede que as notificações do Destaque do Windows Apareçam na Central de Ações. **Não configurado** (padrão) pode mostrar notificações na Central de Ações que sugiram aplicativos ou recursos para ajudar os usuários a serem mais produtivos no Windows.
  - **Personalização do Destaque do Windows**: **Bloquear** impede que o Windows use dados de diagnóstico para fornecer experiências personalizadas para o usuário. **Não configurado** (padrão) permite que a Microsoft use dados de diagnóstico para fornecer recomendações personalizadas, dicas e ofertas para adaptar o Windows às necessidades do usuário.
  - **Experiência de boas-vindas do Windows**: **Bloquear** desativa o recurso de experiência de boas-vindas do Windows do Destaque do Windows. A experiência de boas-vindas do Windows não será exibida quando houver atualizações e alterações para o Windows e seus aplicativos. **Não configurado** (padrão) permite a experiência de Boas-vindas do Windows, que mostra ao usuário informações sobre recursos novos ou atualizados.

Selecione **OK** para salvar suas alterações.

## <a name="windows-defender-antivirus"></a>Windows Defender Antivírus

Essas configurações usam o [CSP da política do Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender), que também lista as edições compatíveis do Windows.

- **Monitoramento em tempo real**: **Habilitar** impede a verificação em tempo real de malware, spyware e outros tipos de software indesejados. **Não configurado** (padrão) permite o uso desse recurso.
- **Monitoramento de comportamento**: **Habilitar** impede que o Defender verifique se há certos padrões de atividade suspeita nos dispositivos. **Não configurado** (padrão) permite o monitoramento de comportamento do Windows Defender.
- **NIS (Sistema de Inspeção de Rede)** : o NIS ajuda a proteger dispositivos contra explorações baseadas em rede. Ele utiliza assinaturas de vulnerabilidades conhecidas do Microsoft Endpoint Protection Center para ajudar a detectar e bloquear o tráfego mal-intencionado.
- **Examinar todos os downloads**: controla se o Defender examina todos os arquivos baixados da Internet.
- **Examinar scripts carregados nos navegadores da Web da Microsoft**: **Não configurado** (padrão) permite que o Defender verifique os scripts que são usados no Internet Explorer. **Habilitar** impede essa verificação.
- **Acesso do usuário final ao Defender**: **Bloquear** oculta a interface do usuário do Windows Defender dos usuários finais. Todas as notificações do Windows Defender também são suprimidas. **Não configurado** (padrão) permite o acesso do usuário à interface do usuário do Windows Defender. Quando alterada, esta configuração entra em vigor na próxima vez em que o computador do usuário final for reiniciado.
- **Intervalo de atualização da assinatura (em horas)** : insira o intervalo no qual o Defender verifica novos arquivos de assinatura, de 0 a 24. Suas opções:

  - **Não configurado** (padrão)
  - **Não verificar**: o Defender não verifica se há novos arquivos de assinatura.
  - **1 a 24**: `1` verifica a cada hora, `2` verifica a cada duas horas, `24` verifica a cada dia e assim por diante.
- **Monitorar a atividade de arquivos e programas**: permite que o Defender monitore a atividade de arquivos e programas nos dispositivos.
- **Dias antes da exclusão de malware em quarentena**: continue acompanhando o malware resolvido pelo número de dias inserido para que você possa examinar manualmente os dispositivos afetados anteriormente. Se você definir o número de dias como **0**, o malware permanecerá na pasta de Quarentena e não será removido automaticamente. Quando definido como `90`, itens em quarentena são armazenados por 90 dias no sistema e, em seguida, removidos.
- **Limite de uso de CPU durante uma verificação**: estipule um limite de quanto a CPU pode ser usada durante as verificações, de **1** a **100**.
- **Examinar arquivos mortos**: **Habilitar** impede que o Defender examine arquivos compactados, como ZIP ou CAB. **Não configurado** (padrão) permite essa verificação.
- **Examinar mensagens de email de entrada**: **Habilitar** permite que o Defender examine mensagens de email assim que elas chegam ao dispositivo. **Não configurado** (padrão) impede a verificação de email.
- **Verificar unidades removíveis durante uma verificação completa**: **Habilitar** impede as verificações completas de unidades removíveis. **Não configurado** (padrão) permite que o Defender Examine unidades removíveis, tais como pen drives USB.
- **Examinar unidades de rede mapeadas durante uma verificação completa**: **Habilitar** permite que o Defender examine arquivos em unidades de rede mapeadas. **Não configurado** (padrão) impede a verificação completa. Se os arquivos na unidade forem somente leitura, o Defender não consegue remover nenhum malware encontrado ali.
- **Examinar arquivos abertos de pastas de rede**: **Não configurado** (padrão) permite que o Defender verifique arquivos em unidades de rede compartilhadas, por exemplo, arquivos acessados de um caminho UNC. **Habilitar** impede essa verificação. Se os arquivos na unidade forem somente leitura, o Defender não consegue remover nenhum malware encontrado ali.
- **Proteção da nuvem**: **Não configurado** (padrão) permite que o Microsoft Active Protection Service receba informações sobre a atividade de malware de dispositivos gerenciados. **Habilitar** bloqueia esse recurso.
- **Avisar os usuários antes de envio de amostras**: controla se os arquivos potencialmente mal-intencionados que podem exigir mais análise são enviados automaticamente para a Microsoft. Suas opções:
  - **Não configurado**
  - **Sempre solicitar**
  - **Avisar antes de enviar dados pessoais**
  - **Nunca enviar dados**
  - **Enviar todos os dados sem avisar**: os dados são enviados automaticamente

- **Tempo para executar uma verificação rápida diária**: escolha a hora para executar uma verificação rápida diária. **Não configurado** não executa uma verificação diária. Se você quiser mais personalização, defina a configuração **Tipo de verificação do sistema a executar**.

  [Defender/ScheduleQuickScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)

  > [!WARNING]
  > Essa configuração do Intune no portal do Azure pode mostrar um status de falha. Este é um bug com o recurso de relatório. Depois de reproduzir o comportamento e a solução de problemas, o grupo de produtos do Intune confirmou que o status é na verdade um Êxito. O bug de relatório será corrigido em uma versão futura. Não há um ETA atual, pois os prazos mudam constantemente. Todas as atualizações para esse recurso são anunciadas em [Em desenvolvimento para o Microsoft Intune](in-development.md).

- **Tipo de verificação do sistema a executar**: agende uma verificação do sistema, incluindo o nível de verificação e o dia e a hora para executar o exame. Suas opções:
  - **Não configurado**: não agenda uma verificação do sistema no dispositivo. Os usuários finais podem executar manualmente verificações conforme necessário ou desejado em seus dispositivos.
  - **Desabilitar**: desabilita qualquer verificação do sistema no dispositivo. Escolha esta opção se você estiver usando uma solução de antivírus de parceiro que verifique os dispositivos.
  - **Verificação rápida**: examina os locais comuns em que pode haver malware registrado, como chaves do Registro e pastas de inicialização conhecidas do Windows.
    - **Dia agendado**: escolha o dia para executar o exame.
    - **Hora agendada**: escolha a hora para executar o exame.
  - **Verificação completa**: examina os locais comuns nos quais pode haver malware registrado e também examina cada arquivo e pasta no dispositivo.
    - **Dia agendado**: escolha o dia para executar o exame.
    - **Hora agendada**: escolha a hora para executar o exame.

  Essa configuração pode entrar em conflito com a configuração de **Hora para executar uma verificação rápida diária**. Algumas recomendações:

  - Para executar uma verificação rápida diária, defina a configuração de **Hora para executar uma verificação rápida diária**.
  - Para executar uma verificação rápida diária e uma verificação completa semanal, configure a **Hora para executar uma verificação rápida diária**. Defina **tipo de verificação do sistema a executar** para uma verificação completa com o dia e a hora.
  - Não defina a configuração **Hora para executar uma verificação rápida diária** definindo simultaneamente o **Tipo de verificação do sistema a realizar** como **Verificação rápida**. Essas configurações podem entrar em conflito e uma verificação poderá não ser executada.
  - Para executar uma verificação rápida nas terças-feiras às 6h, defina a configuração **Tipo de verificação do sistema a executar**.

  [Defender/ScanParameter CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter)  
  [Defender/ScheduleScanDay CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday)  
  [Defender/ScheduleScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime)

  > [!WARNING]
  > Essa configuração do Intune no portal do Azure pode mostrar um status de falha. Este é um bug com o recurso de relatório. Depois de reproduzir o comportamento e a solução de problemas, o grupo de produtos do Intune confirmou que o status é na verdade um Êxito. O bug de relatório será corrigido em uma versão futura. Não há um ETA atual, pois os prazos mudam constantemente. Todas as atualizações para esse recurso são anunciadas em [Em desenvolvimento para o Microsoft Intune](in-development.md).

- **Detectar aplicativos potencialmente indesejados**: escolha o nível de proteção quando o Windows detecta aplicativos potencialmente indesejados. Suas opções:
  - **Não configurado** (padrão): a proteção de aplicativos potencialmente indesejados do Windows Defender é desabilitada.
  - **Bloquear**: o Windows Defender detecta aplicativos potencialmente indesejados e os itens detectados são bloqueados. Esses itens são mostrados no histórico, juntamente com outras ameaças.
  - **Auditoria**: o Windows Defender detecta aplicativos potencialmente indesejados, mas não realiza nenhuma ação. Você pode examinar informações sobre os aplicativos com relação aos quais o Windows Defender realizaria alguma ação. Por exemplo, procure eventos criados pelo Windows Defender no Visualizador de Eventos.

  Para obter mais informações sobre aplicativos potencialmente indesejados, consulte [Detectar e bloquear aplicativos potencialmente indesejados](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).

- **Ações sobre ameaças de malware detectadas**: escolha as ações que o Defender deve realizar para cada nível de ameaça detectada: baixa, moderada, alta e grave. Se não for possível, o Windows Defender escolhe a melhor opção para garantir que a ameaça seja corrigida. Suas opções:
  - **Apagar**
  - **Quarentena**
  - **Removerr**
  - **Permitir**
  - **Definido pelo usuário**
  - **Bloquear**

Selecione **OK** para salvar suas alterações.

### <a name="windows-defender-antivirus-exclusions"></a>Exclusões do Windows Defender Antivírus

- **Arquivos e pastas a excluir de varredura e da proteção em tempo real**: adiciona um ou mais arquivos e pastas, como **C:\Caminho** ou **%ProgramFiles%\Caminho\nomedoarquivo.exe**, à lista de exclusões. Esses arquivos e pastas não serão incluídos em verificações em tempo real ou programadas.
- **Extensões de arquivo a serem excluídas ao executar uma verificação ou usar a proteção em tempo real**: adicione uma ou mais extensões de arquivo, como **jpg** ou **txt**, à lista de exclusões. Qualquer arquivo com essas extensões serão excluídos de verificações em tempo real ou programadas.
- **Processos a excluir de varreduras e da proteção em tempo real**: adicione um ou mais processos do tipo **.exe**, **.com** ou **.scr** à lista de exclusões. Esses processos serão excluídos em verificações em tempo real ou programadas.

Selecione **OK** para salvar suas alterações.

## <a name="next-steps"></a>Próximas etapas

Confira os detalhes técnicos adicionais sobre cada configuração e quais edições do Windows são compatíveis em [Referência do CSP de Política do Windows 10](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
