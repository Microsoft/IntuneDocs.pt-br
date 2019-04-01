---
title: Configurações de restrições de dispositivo para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações e suas descrições para a criação de restrições de dispositivo no Windows 10 e em versões posteriores. Use essas configurações em um perfil de configuração para controlar capturas de tela, requisitos de senha, configurações de quiosque, aplicativos na loja, navegador Microsoft Edge, Windows Defender, acesso à nuvem, menu Iniciar e muito mais no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/13/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8190365ad2b50dfa7369b8899e8984b6a52f1cba
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566736"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>Configurações de dispositivo Windows 10 (e mais recente) para permitir ou restringir recursos usando o Intune

Este artigo lista e descreve todas as diferentes configurações que você pode controlar em dispositivos Windows 10 e mais recente. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, definir regras de senha, personalizar a tela de bloqueio, usar o Windows Defender e muito mais.

Essas configurações são adicionadas a um perfil de configuração do dispositivo no Intune e, em seguida, atribuídas ou implantadas em dispositivos Windows 10.

> [!Note]
> Nem todas as opções estão disponíveis em todas as edições do Windows

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](device-restrictions-configure.md#create-the-profile).

## <a name="app-store"></a>Loja de aplicativos

- **Loja de aplicativos (somente dispositivo móvel)**: habilitar ou bloquear o uso da loja de aplicativos em dispositivos com Windows 10 Mobile.
- **Atualizar aplicativos automaticamente do repositório**: permite que os aplicativos instalados da Microsoft Store sejam atualizados automaticamente.
- **Instalação de aplicativo confiável**: permite que os aplicativos assinados com um certificado de confiança sejam carregados por sideload.
- **Desbloqueio do desenvolvedor**: permite que configurações de desenvolvedor do Windows, como a permissão de sideload de aplicativos, sejam modificadas pelo usuário final.
- **Dados de aplicativo do usuário compartilhados**: permite que os aplicativos compartilhem dados entre usuários diferentes no mesmo dispositivo.
- **Usar somente repositório particular**: habilite para permitir que somente os usuários finais possam baixar aplicativos de sua loja privada.
- **Inicialização de aplicativo originado do repositório**: usada para desabilitar todos os aplicativos previamente instalados no dispositivo ou baixados da Microsoft Store.
- **Instalar dados de aplicativo no volume do sistema**: impede que os aplicativos armazenem dados no volume do sistema do dispositivo.
- **Instalar aplicativos na unidade do sistema**: impede que os aplicativos armazenem dados na unidade do sistema do dispositivo.
- **DVR de Jogos (somente desktop)**: define se é permitido gravar e transmitir jogos.
- **Apenas aplicativos da loja**: define se os usuários podem instalar aplicativos de locais que não sejam a loja de aplicativos.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade

- **Canal de dados da rede celular**: impedir que os usuários usem dados, como navegar na Web, quando estiverem conectados a uma rede celular. 
- **Roaming de dados**: permitir roaming entre redes ao acessar os dados.
- **VPN em rede celular**: controla se o dispositivo pode acessar conexões VPN quando estiver conectado a uma rede celular.
- **Roaming VPN em rede celular**: controla se o dispositivo pode acessar conexões VPN quando estiver conectado a uma rede celular em roaming.
- **Bluetooth**: controla se o usuário pode habilitar e configurar o Bluetooth no dispositivo.
- **Detectabilidade de Bluetooth**: permite que o dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth.
- **Pré-emparelhamento Bluetooth**: permite configurar dispositivos Bluetooth específicos para emparelhar automaticamente com um dispositivo host.
- **Anúncio de Bluetooth**: permite que o dispositivo receba anúncios via Bluetooth.
- **Serviço de dispositivos conectados**: possibilita optar por permitir o serviço de dispositivos conectados, que habilita a descoberta e a conexão com outros dispositivos Bluetooth.
- **NFC**: permite que o usuário habilite e configure recursos de NFC (comunicação a curta distância) no dispositivo.
- **Wi-Fi**: permite que o usuário habilite e configure o Wi-Fi no dispositivo (somente Windows 10 Mobile).
- **Conectar-se automaticamente a pontos de acesso Wi-Fi**: permite que o dispositivo se conecte automaticamente a pontos de acesso Wi-Fi gratuitos e aceite os possíveis termos e condições da conexão automaticamente.
- **Configuração manual do Wi-Fi**: controla se o usuário pode configurar suas próprias conexões Wi-Fi ou se pode usar somente as conexões configuradas por um perfil Wi-Fi (somente Windows 10 Mobile).
- **Intervalo de verificação de Wi-Fi**: especifique com que frequência os dispositivos devem procurar por redes Wi-Fi. Especifique um valor de 1 (mais frequentes) a 500 (menos frequente).
- **Serviços Bluetooth permitidos**: especifique uma lista de serviços e perfis de Bluetooth permitidos usando cadeias de caracteres hexadecimais.

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento

- **Conta da Microsoft**: permite que o usuário associe uma conta da Microsoft ao dispositivo.
- **Conta não Microsoft**: permite que o usuário adicione contas de email ao dispositivo que não estão associadas a uma conta da Microsoft.
- **Sincronização de configurações para a conta da Microsoft**: permitir a sincronização de configurações de dispositivos e aplicativos associadas a uma conta da Microsoft entre dispositivos.
- **Assistente de Conexão de Conta Microsoft**: escolha **Desabilitar** para impedir que os usuários finais controlem o serviço de Assistente de Entrada da Microsoft (wlidsvc), como interromper ou iniciar o serviço manualmente. Quando definido como **Não configurado**, o serviço do wlidsvc NT usa o sistema operacional (SO) padrão, que pode permitir que os usuários finais iniciem e parem o serviço. Esse serviço é usado pelo sistema operacional para permitir que os usuários entre em suas contas da Microsoft.

## <a name="cloud-printer"></a>Impressora de Nuvem

- **URL de descoberta da impressora**: insira a URL para localizar impressoras na nuvem.
- **URL de autoridade para acesso à impressora**: insira a URL de ponto de extremidade para adquirir tokens OAuth. Por exemplo, insira algo como `https://login.microsoftonline.com/your Azure AD Tenant ID`.
- **GUID do aplicativo cliente nativo do Azure**: insira o GUID de um aplicativo cliente com permissão para obter tokens OAuth do OAuthAuthority.
- **URI de recurso do serviço de impressão**: insira o URI de recurso OAuth para o serviço de impressão configurado no portal do Azure. Por exemplo, insira algo como `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Máximo de impressoras para consultar (somente celular)**: insira o número máximo de impressoras a consultar. Por exemplo, insira `10`.
- **URI de recurso do serviço de descoberta da impressora**: insira o URI de recurso do OAuth para o serviço de descoberta da impressora configurado no portal do Azure. Por exemplo, insira algo como `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Depois de instalar uma [Impressão de Nuvem Híbrida do Windows Server](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview), você poderá definir essas configurações e, em seguida, implantar em dispositivos do Windows.

## <a name="control-panel-and-settings"></a>Painel de controle e configurações

- **Aplicativo Configurações**: bloqueia o acesso ao aplicativo de configurações do Windows.
  - **Sistema**: bloqueia o acesso à área de sistema do aplicativo de configurações.
    - **Modificação de configurações de ligar e hibernar (somente Desktop)**: impede que o usuário final altere as configurações de energia e suspensão no dispositivo.
  - **Dispositivos**: bloqueia o acesso à área de dispositivos do aplicativo de configurações.
  - **Rede e Internet**: bloqueia o acesso à área de rede e Internet do aplicativo de configurações.
  - **Personalização**: bloqueia o acesso à área de personalização do aplicativo de configurações.
  - **Contas**: bloqueia o acesso à área de contas do aplicativo de configurações.
  - **Hora e Idioma**: bloqueia o acesso à área de hora e idioma do aplicativo de configurações.
    - **Modificação do Horário do Sistema**: impede que o usuário final altere a data e a hora do dispositivo.
    - **Modificação de configurações de região (somente desktop)**: impede que o usuário final altere as configurações de região no dispositivo.
    - **Modificação das configurações de idioma (somente área de trabalho)**: impede que o usuário altere as configurações de idioma no dispositivo.
  - **Jogos**: bloqueia o acesso ao aplicativo Jogos nas Configurações.
  - **Facilidade de Acesso**: bloqueia o acesso à área de facilidade de acesso do aplicativo de configurações.
  - **Privacidade**: bloqueia o acesso à área de privacidade do aplicativo de configurações.
  - **Atualização e Segurança**: bloqueia o acesso à área de atualizações e segurança do aplicativo de configurações.

## <a name="display"></a>Vídeo

- **Ligar o ajuste de GDI para aplicativos**
- **Desligar o ajuste de GDI para aplicativos**

  O Ajuste de DPI GDI permite que aplicativos sem reconhecimento de DPI tenham reconhecimento de DPI por monitor. Insira os aplicativos herdados que têm o Ajuste de DPI GDI ativado. Com o Ajuste de DPI GDI configurado para ser ativado e desativado em um aplicativo, o dimensionamento fica desativado para o aplicativo.

## <a name="general"></a>Geral

- **Captura de tela (somente dispositivo móvel)**: permite que o usuário capture a tela do dispositivo como uma imagem.
- **Copiar e colar (somente dispositivo móvel)**: permitir utilizar ações de copiar e colar entre os aplicativos do dispositivo.
- **Cancelamento de registro manual**: permite que o usuário exclua manualmente a conta de trabalho do dispositivo.
  - Essa configuração de política não será aplicada se o computador estiver ingressado no Azure AD e o registro automático estiver habilitado. 
  - Essa configuração de política não se aplica a computadores que executam o Windows 10 Home.
- **Instalação manual do certificado raiz (somente dispositivo móvel)**: impede que o usuário instale manualmente os certificados raiz e certificados CAP intermediários.

- **Câmera**: permite ou bloqueia o uso da câmera do dispositivo.
- **Sincronização de arquivos do OneDrive**: bloqueia a sincronização de arquivos do dispositivo com o OneDrive.
- **Armazenamento removível**: especifica se é possível usar dispositivos de armazenamento externo, como cartões SD, no dispositivo.
- **Geolocalização**: especifica se o dispositivo pode usar informações dos serviços de localização.
- **Compartilhamento da Internet**: permite o uso do compartilhamento da conexão com a Internet no dispositivo.
- **Redefinição do telefone**: controla se o usuário pode apagar o dispositivo.
- **Conexão USB (somente dispositivos móveis)**: controla se os dispositivos podem acessar dispositivos de armazenamento externo por meio de uma conexão USB.
- **Modo AntiTheft (somente dispositivos móveis)**: configure se o modo AntiTheft do Windows está habilitado.
- **Cortana**: habilitar ou desabilitar a assistente de voz Cortana.
- **Gravação de voz (somente dispositivos móveis)**: permitir ou bloquear o uso do gravador de voz do dispositivo.
- **Modificação do nome do dispositivo**: impede que o usuário final altere o nome do dispositivo (apenas Windows 10 Mobile)
- **Adicionar pacotes de provisionamento**: bloqueia o agente de configuração de tempo de execução que instala os pacotes de provisionamento.
- **Remover pacotes de provisionamento**: bloqueia o agente de configuração de tempo de execução que remove os pacotes de provisionamento.
- **Descoberta de dispositivos**: bloqueia a descoberta de um dispositivo por outros dispositivos.
- **Alternador de tarefas (somente dispositivos móveis)**: bloqueia o alternador de tarefas no dispositivo.
- **Diálogo de erro do cartão SIM (somente dispositivos móveis)**: bloqueia a exibição de uma mensagem de erro no dispositivo se nenhum cartão SIM for detectado.
- **Espaço de Trabalho do Ink**: impedir que usuários acessem o espaço de trabalho do Ink. **Não configurado** habilita o espaço de trabalho do Ink e o usuário tem permissão para usá-lo na tela de bloqueio.
- **Reimplantação automática**: permite que usuários com direitos administrativos excluam todos os dados e configurações de usuário usando **Ctrl+Win+R** na tela de bloqueio do dispositivo. O dispositivo é reconfigurado automaticamente e registrado novamente no gerenciamento.
- **Exigir que os usuários se conectem à rede durante a instalação de dispositivo (somente para Windows Insider)**: escolha **Exigir** para que o dispositivo se conecte a uma rede após da página Rede e antes de continuar, durante a instalação do Windows 10. Embora esse recurso esteja na versão prévia, um Windows Insider build 1809 ou posterior é necessário para usar essa configuração.
- **Acesso Direto à Memória**: **Bloquear** impede o DMA (acesso direto à memória) para todas as portas downstream PCI com hot-plug até um usuário entre no Windows. **Habilitado** (padrão) permite o acesso a DMA, mesmo quando um usuário não esteja conectado.

  CSP: [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **Encerrar os processos do Gerenciador de tarefas**: essa configuração determina se o não-administradores podem usar o Gerenciador de tarefas para finalizar tarefas. **Bloquear** impede que os usuários padrão (não administradores) usem o Gerenciador de Tarefas para encerrar um processo ou uma tarefa no dispositivo. A opção **Não configurado** (padrão) permite que os usuários padrão encerrem um processo ou uma tarefa usando o Gerenciador de Tarefas.


## <a name="locked-screen-experience"></a>Experiência na tela bloqueada

- **Notificações da central de ações (somente dispositivos móveis)**: permite que notificações da Central de Ações apareçam na tela de bloqueio do dispositivo (somente Windows 10 Mobile).
- **URL da imagem de tela bloqueada (somente Desktop)**: insira a URL para uma imagem no formato JPEG que deve ser usada como papel de parede na tela bloqueada do Windows. Essa configuração bloqueia a imagem. A imagem não pode ser alterada posteriormente.
- **Tempo limite de tela configurável do usuário (somente em dispositivos móveis)**: permite que usuários configurem o período 
- **Cortana na tela bloqueada (somente Desktop)**: não permitir que o usuário interaja com a Cortana quando o dispositivo estiver na tela de bloqueio (somente Windows 10 para área de trabalho).
- **Notificações do sistema na tela bloqueada**: impeça que mensagens de alerta sejam exibidas na tela de bloqueio do dispositivo.
- **Tempo limite da tela (somente dispositivos móveis)**: especifica o tempo em segundos, depois do bloqueio da tela, em que ela será desligada.

## <a name="messaging"></a>Sistema de mensagens

- **Sincronização de mensagem (somente móvel)**: desabilite as Mensagens em qualquer lugar e o backup e a restauração de mensagens de texto.
- **MMS (somente móvel)**: desabilite o recurso de envio/recebimento de MMS no dispositivo.
- **RCS (somente móvel)**: desabilite a funcionalidade de envio/recebimento dos Serviços de Comunicação Avançados no dispositivo.

## <a name="microsoft-edge-browser"></a>Navegador Microsoft Edge

### <a name="use-microsoft-edge-kiosk-mode"></a>Usar o modo de quiosque do Microsoft Edge

Alterar as configurações disponíveis dependendo do que você escolhe. Suas opções:

- **Não** (padrão): Microsoft Edge não está em execução no modo de quiosque. Todas as configurações do Microsoft Edge estão disponíveis para você altere e configurar.
- **Sinalização de digitais/interativo (quiosque de aplicativo único)**: configurações de borda de filtros que são aplicáveis para o modo de quiosque de borda de sinalização Digital/interativo para uso apenas em quiosques de aplicativo único do Windows 10. Escolha esta configuração para abrir uma tela inteira da URL e mostrar apenas o conteúdo no site. [Configurar sinais digitais](https://docs.microsoft.com/windows/configuration/setup-digital-signage) fornece mais informações sobre esse recurso.
- **Público a navegação inPrivate (quiosque de aplicativo único)**: configurações de borda de filtros que são aplicáveis para o modo InPrivate quiosque de borda de navegação público para uso em quiosques de aplicativo único do Windows 10. Executa uma versão com várias guia do Microsoft Edge.
- **Modo normal (quiosque de vários aplicativos)**: configurações de borda de filtros que são aplicáveis para o modo de quiosque de borda Normal. Executa uma versão completa do Microsoft Edge com todos os recursos de navegação.
- **Público (quiosque de vários aplicativos) de navegação**: configurações de borda de filtros que são aplicáveis para navegação pública em um quiosque de vários aplicativos do Windows 10.  Executa uma versão com várias guia do Microsoft Edge InPrivate.

> [!TIP]
> Para obter mais informações sobre o que fazem essas opções, consulte [tipos de configuração de modo de quiosque do Microsoft Edge](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

Este perfil de restrições de dispositivo está diretamente relacionado ao perfil do kiosk você cria usando o [as configurações de quiosque do Windows](kiosk-settings-windows.md). Para resumir:

1. Criar o [as configurações de quiosque do Windows](kiosk-settings-windows.md) perfil para executar o dispositivo no modo de quiosque. Selecione Microsoft Edge como o aplicativo e defina o modo de quiosque de borda no perfil de quiosque.
2. Criar o perfil de restrições de dispositivo descrito neste artigo e configurar recursos específicos e as configurações de permissão no Microsoft Edge. Certifique-se de escolher o mesmo tipo de modo de quiosque de borda conforme selecionado no seu perfil de quiosque ([as configurações de quiosque do Windows](kiosk-settings-windows.md)). 

    [Suporte para configurações do modo de quiosque](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-policies-for-kiosk-mode) é um excelente recurso.

> [!IMPORTANT] 
> Certifique-se de atribuir a esse perfil do Microsoft Edge para os mesmos dispositivos como seu perfil de quiosque ([as configurações de quiosque do Windows](kiosk-settings-windows.md)).

CSP: [ConfigureKioskMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)

### <a name="start-experience"></a>Experiência de inicialização

- **Abrir o Microsoft Edge com**: escolha quais páginas abrir ao iniciar o Microsoft Edge. Suas opções:
  - **Páginas iniciais**: o Microsoft Edge abre com a página inicial padrão definida pelo sistema operacional
  - **Página Nova Guia**: o Microsoft Edge carrega o que estiver definido na configuração de **URL da página Nova Guia**
  - **Página da última sessão**: o Microsoft Edge carrega a página da última sessão 
  - **Página inicial personalizada**: o Microsoft Edge carrega a página inicial definida pelo administrador de TI
- **O usuário pode alterar páginas Iniciais**: **Permitir** deixa os usuários alterar as páginas iniciais. Os administradores podem usar `EdgeHomepageUrls` para inserir páginas iniciais que os usuários veem por padrão ao abrir o Microsoft Edge. **Não configurado** impede que os usuários alterem as páginas iniciais.
- **URL da página Nova Guia**: insira a URL para abrir na página da nova guia. Por exemplo, insira `https://www.bing.com`.
- **Abrir conteúdo da Web na página Nova Guia**: escolha **Bloquear** para impedir que o Microsoft Edge abra um site em uma nova guia. Quando essa opção estiver bloqueada, a nova guia abre em branco. **Não configurado** usa o comportamento padrão do sistema operacional no dispositivo, que pode permitir que os usuários escolham o que é exibido.
- **Botão Página Inicial**: escolha o que acontece ao selecionar o botão Página Inicial. Suas opções:
  - **Páginas iniciais**: abre a opção que você escolheu para a configuração **Abrir o Microsoft Edge com**
  - **Página Nova Guia**: abre a opção que você escolheu para a configuração **URL da página Nova Guia**
  - **URL personalizada do botão Página Inicial**: abre a opção que você escolheu para a configuração **URL do botão Página Inicial**
  - **Ocultar o botão Página Inicial**: oculta o botão Página Inicial
- **O usuário pode alterar o botão Página Inicial**: **Permitir** deixa os usuários alterarem o botão Página Inicial. As alterações do usuário substituem as configurações do administrador para o botão Página Inicial. **Não configurado** usa o comportamento padrão do sistema operacional no dispositivo, o que pode impedir que os usuários alterem o modo como o administrador configurou o botão Página Inicial.
- **Mostrar a página Experiência de Primeira Execução**: **Bloquear** impede que a página de introdução seja exibida na primeira vez que o Microsoft Edge for executado. Esse recurso permite que empresas, como as registradas em cenários de emissões zero, bloqueiem esta página. **Não configurado** mostra a página de introdução.
  - **URL de Experiência de Primeira Execução**: insira a URL da página a exibir na primeira vez que um usuário executar o Microsoft Edge (somente Windows 10 Mobile).
- **Atualize o navegador após o tempo ocioso**: insira o número de minutos ociosos até que o navegador for atualizado, de 0 a 1440 minutos. O padrão é `5` minutos. Quando definido como `0` (zero), o navegador não atualizar depois de ficar ocioso.

  Essa configuração só está disponível durante a execução no [Navegação InPrivate pública (quiosque de aplicativo único)](#use-microsoft-edge-kiosk-mode).

  CSP: [ConfigureKioskResetAfterIdleTimeout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskresetafteridletimeout)

- **Pop-ups**: escolha **Bloquear** para impedir janelas pop-up no navegador. Aplica-se somente ao Windows 10 Desktop. **Não configurado** permite pop-ups no navegador da Web.
- **Enviar tráfego da intranet para o Internet Explorer**: **Permitir** deixa os usuários abrirem sites da Intranet no Internet Explorer ao invés de usar o Microsoft Edge (somente para computadores com Windows 10). **Não configurado** permite que os usuários usem o Microsoft Edge.
- **Local da lista de sites do Modo Empresarial**: insira a URL que contém uma lista de sites a abrir no modo Empresarial. Os usuários não podem alterar essa lista. Aplica-se somente ao Windows 10 Desktop.
- **Mensagem ao abrir sites no Internet Explorer**: use essa opção para configurar o Microsoft Edge para mostrar uma notificação antes de abrir um site no Internet Explorer 11. Suas opções:
  - **Não configurado**: usa o comportamento padrão do sistema operacional, o que pode não mostrar uma mensagem.
  - **Mostrar mensagem sem a opção para abrir sites no Microsoft Edge**: mostrar a mensagem ao abrir sites no Internet Explorer. Os sites abrem no Internet Explorer. Não há uma opção para abrir sites no Microsoft Edge.
  - **Mostrar mensagem ao abrir sites no Microsoft Edge**: mostrar a mensagem ao abrir sites no Internet Explorer. A mensagem contém um link para **Continuar no Microsoft Edge** de forma que os usuários podem escolher o Microsoft Edge ao invés do IE.

  > [!IMPORTANT]
  > Essa configuração exige que você habilite a opção **Configurar a Lista de Sites do Modo Empresarial**, a opção **Enviar todos os sites da Intranet para o Internet Explorer 11** ou ambas.

- **Lista de compatibilidade da Microsoft**: **Bloquear** impede a lista de compatibilidade no Microsoft Edge. Essa lista da Microsoft ajuda o Microsoft Edge a exibir corretamente sites com problemas de compatibilidade conhecidos. **Não configurado** permite o uso de uma lista de compatibilidade da Microsoft.
- **Pré-carregar as Páginas Iniciais e a página Nova Guia**: escolha **Bloquear** para impedir o Microsoft Edge de pré-carregar páginas iniciais e a página de nova guia. O pré-carregamento reduz o tempo para iniciar o Microsoft Edge e carregar uma nova guia. **Não configurado** usa o comportamento padrão do sistema operacional, que pode ser pré-carregar essas páginas.
- **Pré-lançar as Páginas Iniciais e a página Nova Guia**: escolha **Bloquear** para impedir o Microsoft Edge de iniciar previamente as páginas iniciais e a página de nova guia. A pré-inicialização ajuda o desempenho do Microsoft Edge e reduz o tempo necessário para iniciar o Microsoft Edge. **Não configurado** usa o comportamento padrão do sistema operacional, que pode ser pré-iniciar essas páginas.

### <a name="favorites-and-search"></a>Favoritos e pesquisa

- **Barra de favoritos**: escolha o que acontece com a barra de favoritos em qualquer página do Microsoft Edge. Suas opções:
  - **Não configurado** usa o comportamento padrão do sistema operacional, que pode ocultar a barra de favoritos em todas as páginas. Os usuários podem alterar essa configuração.
  - **Ocultar**: oculta a barra de favoritos em todas as páginas. Os usuários não podem alterar essa configuração.
  - **Mostrar**: exibe a barra de favoritos em todas as páginas. Os usuários não podem alterar essa configuração.
- **Lista de favoritos**: adicionar uma lista de URLs ao arquivo de favoritos. Por exemplo, adicione `http://contoso.com/favorites.html`.
- **Restringir alterações aos Favoritos**: escolha **Bloquear** para impedir que os usuários adicionem, importem, classifiquem ou editem a lista de Favoritos. **Não configurado** usa o padrão do sistema operacional, que pode permitir que os usuários alterem a lista.
- **Sincronizar favoritos entre navegadores da Microsoft (somente Desktop)**: escolha **Exigir** para que o Windows sincronize os favoritos entre o Internet Explorer e o Microsoft Edge. Adições, exclusões, modificações e alterações da ordem dos favoritos são compartilhadas entre navegadores.  **Não configurado** usa o padrão do sistema operacional, o que pode dar aos usuários a opção de sincronizar favoritos entre navegadores.
- **Mecanismo de pesquisa padrão**: escolha o mecanismo de pesquisa padrão do dispositivo. Os usuários finais podem alterar esse valor a qualquer momento. Suas opções:
  - Padrão
  - Bing
  - Google
  - Yahoo
  - Valor personalizado
- **Sugestões de Pesquisa**: **Não configurado** permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa na barra de endereços. **Bloquear** impede esse recurso.
- **Permitir alterações para o mecanismo de pesquisa**: **Sim** (padrão) permite aos usuários adicionar novos mecanismos de pesquisa, ou alterar o mecanismo de pesquisa padrão no Microsoft Edge. Escolher **não** para impedir que os usuários personalizem o mecanismo de pesquisa.

  Essa configuração só está disponível durante a execução no [modo Normal (quiosque de vários aplicativos)](#use-microsoft-edge-kiosk-mode).

  CSP: [AllowSearchEngineCustomization](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsearchenginecustomization)

### <a name="privacy-and-security"></a>Segurança e privacidade

- **Navegação InPrivate**: **Bloquear** impede que os usuários finais abram sessões de navegação InPrivate. **Não configurado** permite o uso desse recurso.
- **Salvar o histórico de navegação**: **Bloquear** impede que o Microsoft Edge salve o histórico de navegação. **Não configurado** permite salvar o histórico de navegação.
- **Limpar dados de navegação na saída (somente Desktop)**: **Exigir** limpa o histórico e os dados de navegação quando o usuário sai do Microsoft Edge. **Não configurado** usa o padrão do sistema operacional, que pode armazenar em cache os dados de navegação.
- **Sincronizar as configurações do navegador entre os dispositivos do usuário**: escolha como você deseja sincronizar as configurações de navegador entre os dispositivos. Suas opções:
  - **Permitir**: autoriza a sincronização de configurações do navegador Microsoft Edge entre os dispositivos do usuário
  - **Bloquear e habilitar substituição do usuário**: bloquear a sincronização das configurações do navegador Microsoft Edge entre os dispositivos do usuário. Os usuários podem substituir essa configuração.
  - **Bloquear**: bloqueia a sincronização de configurações do navegador Microsoft Edge entre os dispositivos do usuário. Os usuários não podem substituir essa configuração.
- **Gerenciador de senhas**: **Bloquear** desabilita o recurso do Gerenciador de senhas do Microsoft Edge. **Não configurado** permite o uso desse recurso.
- **Cookies**: escolha como lidar com os cookies no navegador da Web. Suas opções:
  - **Permitir**: os cookies são armazenados no dispositivo.
  - **Bloquear todos os cookies**: os cookies não são armazenados no dispositivo.
  - **Bloquear somente cookies de terceiros**: os cookies de parceiros ou terceiros não são armazenados no dispositivo.
- **Preenchimento automático**: **Bloquear** desabilita o recurso de preenchimento automático no dispositivo. **Não configurado**: permite que os usuários alterem as configurações de preenchimento automático no navegador (somente para computadores com Windows 10).
- **Enviar cabeçalhos Do Not Track**: **Não configurado** exige que os dispositivos enviem cabeçalhos para não rastrear a sites que solicitam informações de rastreamento (recomendado). Escolha **Bloquear** para impedir que o dispositivo envie esses cabeçalhos, o que permite que os sites rastreiem o usuário.
- **Endereço IP do localhost WebRtc**: **Bloquear** impede a exibição do endereço IP do localhost de usuários ao fazer chamadas telefônicas usando o protocolo RTC da Web. **Não configurado** permite que os endereços IP de localhost dos usuários sejam mostrados ao fazer chamadas telefônicas usando esse protocolo.
- **Coleção de dados do Bloco Dinâmico**: escolha **Bloquear** para impedir que o Windows colete informações de Blocos Dinâmicos quando um site estiver fixado no menu Iniciar do Microsoft Edge. **Não configurado** permite que essas informações sejam coletadas.
- **O usuário pode substituir os erros de certificado**: **Bloquear** evita que os usuários acessem os sites que têm erros de SSL ou TLS. **Não configurado** permite que os usuários acessem esses sites.

### <a name="additional"></a>Adicional

- **Navegador Microsoft Edge (somente dispositivo móvel)**: escolha **Bloquear** para impedir o uso do Microsoft Edge no dispositivo. Se você bloquear o Microsoft Edge, as configurações individuais serão aplicadas apenas à área de trabalho. **Não configurado** permite o uso do navegador da Web Microsoft Edge no dispositivo.
- **Menu suspenso da barra de endereços (somente Desktop)**: **Bloquear** impede que o Microsoft Edge exiba uma lista de sugestões em uma lista suspensa ao digitar. Essa opção ajuda a minimizar o uso de largura de banda da rede entre o Microsoft Edge e os serviços da Microsoft. **Não configurado** permite que o Microsoft Edge mostre uma lista de sugestões.
- **Tela inteira**: escolha **Bloquear** para impedir que o Microsoft Edge mostre apenas o conteúdo da Web, ocultando o Microsoft Edge (modo de tela inteira). **Não configurado** usa o padrão do sistema operacional, que permite que o Microsoft Edge use o modo de tela inteira.
- **Sinalizadores**: **Bloquear** impede que os usuários finais acessem a página `about:flags` no Microsoft Edge, que inclui configurações experimentais e de desenvolvedor. **Não configurado** usa o padrão do sistema operacional, que pode permitir o acesso à página `about:flags`.
- **Ferramentas de desenvolvedor**: **Bloquear** impede que os usuários finais abram as ferramentas para desenvolvedores do Microsoft Edge. **Não configurado** permite que os usuários abram as ferramentas para desenvolvedores.
- **Extensões**: **Não configurado** permite aos usuários finais instalarem extensões do Microsoft Edge no dispositivo. **Bloquear** impede a instalação.
- **Sideload das extensões do desenvolvedor**: **Bloquear** impede que o Microsoft Edge faça sideloading, que instala e executa as extensões não verificadas usando o recurso **Carregar extensões**. **Não configurado** usa o padrão do sistema operacional, que pode permitir o sideloading.
- **Extensões necessárias**: escolher quais extensões não podem ser desativadas pelos usuários finais no Microsoft Edge. Insira os nomes das famílias de pacotes e selecione **Adicionar**. As listas [Localizar um nome da família de pacotes (PFN)](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) oferecem algumas orientações.

  Você também pode **Importar** um arquivo CSV que inclui os nomes das famílias de pacotes.

- **JavaScript**: escolha **Bloquear** para impedir que os scripts Java sejam executados no navegador do dispositivo. **Não configurado** permite que scripts, como JavaScript, sejam executados no navegador Microsoft Edge.

## <a name="network-proxy"></a>Proxy de rede

- **Detectar automaticamente as configurações de proxy**: quando habilitado, o dispositivo tenta localizar o caminho para um script PAC.
- **Usar script de proxy**: selecione esta opção para inserir um caminho para um script PAC a fim de configurar o servidor proxy.
  - **Configurar URL do endereço do script**: insira a URL de um script PAC que você deseja usar para configurar o servidor proxy.
- **Usar um servidor proxy manual**: selecione esta opção para inserir manualmente as informações do servidor proxy.
  - **Endereço**: insira o nome ou o endereço IP do servidor proxy.
  - **Número da porta**: insira o número de porta de seu servidor proxy.
  - **Exceções de proxy**: insira todas as URLs que não devem usar o servidor proxy. Use um ponto e vírgula para separar cada item.
  - **Ignorar proxy para endereço local**: habilite esta opção se não quiser usar o servidor proxy para endereços locais na Intranet.

## <a name="password"></a>Senha

- **Senha**: exige que o usuário final insira uma senha para acessar o dispositivo.
  - **Tipo de senha exigida**: especifica se a senha deve ser apenas numérica ou alfanumérica.
  - **Comprimento mínimo da senha**: aplicável somente a Windows 10 Mobile.
  - **Número de falhas de entrada antes de apagar o dispositivo**: para dispositivos que executam o Windows 10, se este tiver o BitLocker habilitado, será colocado no modo de recuperação do BitLocker após a entrada falhar o número de vezes especificado. Se o dispositivo não tiver o BitLocker habilitado, essa configuração não se aplica. Para dispositivos que executam o Windows Mobile 10, após a entrada falhar o número de vezes especificado, o dispositivo será apagado.
  - **Máximo de minutos de inatividade até o bloqueio de tela**: especifica o período que um dispositivo deve permanecer ocioso antes de a tela ser bloqueada.
  - **Expiração de senha (dias)**: especifica o período após o qual a senha do dispositivo deve ser alterada.
  - **Impedir a reutilização de senhas anteriores**: especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo.
  - **Exigir senha quando o dispositivo retorna do estado inativo (somente dispositivos móveis)**: especifica que o usuário deve inserir uma senha para desbloquear o dispositivo (somente Windows 10 Mobile).
  - **Senhas simples**: permite o uso de senhas simples, como 1111 ou 1234. Essa configuração também permite ou bloqueia o uso de senhas de imagem do Windows.

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
- **Dispositivos confiáveis**: defina se este aplicativo pode usar dispositivos confiáveis, isto é, hardware que você já conectou ou que acompanha o dispositivo. Por exemplo, usar TVs, projetores e assim por diante como dispositivos confiáveis.
- **Comentários e diagnóstico**: defina se este aplicativo pode acessar informações de diagnóstico.
- **Sincronização com dispositivos**: escolha se este aplicativo pode compartilhar e sincronizar automaticamente informações com dispositivos sem fio que não emparelham explicitamente com este dispositivo.

## <a name="personalization"></a>Personalização

- **URL da imagem de tela de fundo da área de trabalho (somente Desktop)**: insira a URL para uma imagem no formato JPEG que deseja usar como o papel de parede da área de trabalho do Windows. Os usuários não podem alterar a foto.

## <a name="printer"></a>Impressora

- **Impressoras**: lista de impressoras locais que foram adicionadas.
- **Impressora padrão**: defina a impressora padrão.
- **Acesso de usuário à adição de novas impressoras**: permita ou bloqueie o uso de impressoras locais.

## <a name="privacy"></a>Privacidade

- **Personalização de entrada**: não permite o uso de serviços de voz baseados em nuvem para a Cortana, o ditado ou aplicativos da Microsoft Store. Se você permitir esses serviços, a Microsoft poderá coletar dados de voz para melhorar o serviço.
- **Aceitação automática das solicitações de consentimento do usuário de privacidade e emparelhamento**: permitir que o Windows aceite automaticamente mensagens de consentimento de emparelhamento e privacidade ao executar aplicativos.
- **Publicar as atividades do usuário**: **bloquear** evita o compartilhamento de experiências e a descoberta de recursos usados recentemente no alternador de tarefas.
- **Apenas atividades locais**: **bloquear** evita o compartilhamento de experiências e a descoberta de recursos usados recentemente no alternador de tarefas com base somente em atividades locais.

Você pode configurar as informações que todos os aplicativos no dispositivo podem acessar. Você pode definir exceções de acordo com o aplicativo que usa **Exceções de privacidade por aplicativo**.

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
- **Dispositivos confiáveis**: escolha se este aplicativo pode usar dispositivos confiáveis. Dispositivos confiáveis são o hardware que você já conectou ou que acompanha o dispositivo. Por exemplo, usar TVs, projetores etc. como dispositivos confiáveis.
- **Comentários e diagnóstico**: defina se este aplicativo pode acessar informações de diagnóstico.
- **Sincronização com dispositivos** – defina se este aplicativo pode compartilhar e sincronizar automaticamente informações com dispositivos sem fio que não emparelham explicitamente com este computador, tablet ou telefone.

## <a name="projection"></a>Projeção

- **Entrada do usuário de receptores de exibição sem fio**: bloqueia a entrada do usuário de receptores de vídeo sem fio.
- **Projeção para este computador**: impede que outros dispositivos localizem o PC para projeção.
- **Exigir um PIN para emparelhamento**: exige um PIN durante a conexão com um dispositivo de projeção.

## <a name="reporting-and-telemetry"></a>Relatório e telemetria

- **Compartilhar dados de uso**: escolha o nível de dados de diagnóstico que são enviados. Suas opções:
  - Segurança 
  - Basic
  - Avançado
  - Completo
- **Enviar dados de navegação do Microsoft Edge para a Análise do Microsoft 365**: para usar esse recurso, defina as configurações de **Compartilhar dados de uso** como **Avançado** ou **Completo**. Esse recurso controla quais dados de dispositivos corporativos com uma ID comercial configurada o Microsoft Edge envia para a Análise do Microsoft 365. Suas opções:
  - **Não configurado**: usa o padrão do sistema operacional, que pode não enviar dados do histórico de navegação
  - **Enviar somente dados da Intranet**: permite que o administrador envie o histórico de dados da Intranet
  - **Enviar somente dados da Internet**: permite que o administrador envie o histórico de dados da Internet
  - **Enviar dados da Intranet e da Internet**: permite que o administrador envie o histórico de dados da Intranet e da Internet
- **Servidor proxy de telemetria**: insira o FQDN (nome de domínio totalmente qualificado) ou o endereço IP de um servidor proxy para encaminhar solicitações de Experiências e Telemetria de Usuário Conectado usando uma conexão SSL (Secure Sockets Layer). O formato para essa configuração é *servidor*:*porta*. Se o proxy nomeado falhar ou se não for inserido um proxy ao habilitar essa política, os dados de Experiências e Telemetria do Usuário Conectado não serão enviados e permanecerão no dispositivo local.

  Formatos de exemplo:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

## <a name="search"></a>Pesquisar

- **Pesquisa Segura (dispositivo móvel)**: controla como a Cortana filtra o conteúdo adulto nos resultados da pesquisa. Você pode selecionar **Estrito**, **Moderado** ou permitir que o usuário final escolha suas próprias configurações.
- **Exibir resultados da Web na pesquisa**: bloquear ou permitir que os resultados da Web sejam exibidos em pesquisas feitas no dispositivo.

## <a name="start"></a>Inicie o

- **Layout do menu Iniciar**: para personalizar o menu Iniciar nos dispositivos da área de trabalho, você pode carregar um arquivo XML que contém suas personalizações, incluindo a ordem em que os aplicativos são listados e muito mais. Os usuários não podem alterar o layout do menu Iniciar que você inserir.
- **Fixar sites da Web como blocos no menu Iniciar**: importe imagens do Microsoft Edge exibidas como links no menu Iniciar do Windows para dispositivos de área de trabalho.
- **Desafixar aplicativos da barra de tarefas**: selecione **Bloquear** para impedir o usuário de desafixar aplicativos na barra de tarefas.
- **Troca rápida de usuário**: selecione **Bloquear** para impedir a troca entre os usuários que estão conectados simultaneamente sem fazer logoff.
- **Aplicativos mais usados**: selecione **Bloquear** para ocultar os aplicativos mais usados no menu Iniciar. Isso também desabilita a alternância correspondente no aplicativo Configurações.
- **Aplicativos adicionados recentemente**: selecione **Bloquear** para ocultar os aplicativos adicionados recentemente no menu Iniciar. Isso também desabilita a alternância correspondente no aplicativo Configurações.
- **Iniciar modo de tela**: escolha como a tela inicial é exibida. Escolha exibi-la como **Tela inteira** ou **Tela não inteira**.
- **Itens abertos recentemente nas Listas de Atalhos**: selecione **Bloquear** para ocultar as listas de atalhos recentes no menu Iniciar e na barra de tarefas. Isso também desabilita a alternância correspondente no aplicativo Configurações.
- **Lista de aplicativos**: escolha como o aplicativo Configurações é exibido. Suas opções: 
  - Recolher
  - Recolher e desabilitar o aplicativo Configurações 
  - Remove e desabilita o aplicativo Configurações
- **Botão de energia**: selecione **Bloquear** para ocultar o botão de energia no menu Iniciar.
- **Bloco do Usuário**: selecione **Bloquear** para ocultar o bloco do usuário no menu Iniciar.
  - **Bloquear**: selecione **Bloquear** para ocultar a opção `Lock` no bloco de usuário no menu Iniciar.
  - **Sair**: selecione **Bloquear** para ocultar a opção `Sign out` no bloco do usuário no menu Iniciar.
- **Desligar**: selecione **Bloquear** para ocultar as opções `Update and shut down` e `Shut down` no botão de energia no menu Iniciar.
- **Suspender**: selecione **Bloquear** para ocultar a opção `Sleep` no botão de energia no menu Iniciar.
- **Hibernar**: selecione **Bloquear** para ocultar a opção `Hibernate` no botão de energia no menu Iniciar.
- **Alternar Conta**: selecione **Bloquear** para ocultar `Switch account` no bloco do usuário no menu Iniciar.
- **Opções de Reinicialização**: selecione **Bloquear** para ocultar as opções `Update and restart` e `Restart` no botão de energia no menu Iniciar.
- **Documentos em Iniciar**: oculta ou mostra a pasta Documentos no menu Iniciar do Windows.
- **Downloads em Iniciar**: oculta ou mostra a pasta Downloads no menu Iniciar do Windows.
- **Explorador de Arquivos em Iniciar**: oculta ou mostra o aplicativo Explorador de Arquivos no menu Iniciar do Windows.
- **HomeGroup em Iniciar**: oculta ou mostra a pasta HomeGroup no menu Iniciar do Windows.
- **Música em Iniciar**: oculta ou mostra a pasta Música no menu Iniciar do Windows.
- **Rede em Iniciar**: oculta ou mostra a pasta Rede no menu Iniciar do Windows.
- **Pasta Pessoal em Iniciar**: oculta ou mostra a pasta Pessoal no menu Iniciar do Windows.
- **Imagens em Iniciar**: oculta ou mostra a pasta de imagens no menu Iniciar do Windows.
- **Configurações em Iniciar**: oculta ou mostra o aplicativo Configurações no menu Iniciar do Windows.
- **Vídeos em Iniciar**: oculta ou mostra a pasta de vídeos no menu Iniciar do Windows.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **SmartScreen para Microsoft Edge**: habilite o SmartScreen do Microsoft Edge para acessar downloads de site e de arquivos.
- **Acesso a sites mal-intencionados**: impeça os usuários de ignorar os avisos de Filtro do Windows Defender SmartScreen, e impeça-os de visitar o site.
- **Download de arquivo não verificado**: impeça os usuários de ignorar os avisos de Filtro do Windows Defender SmartScreen, e impeça-os de fazer o download de arquivos não verificados.

## <a name="windows-spotlight"></a>Destaque do Windows

- **Destaque do Windows**: use essa configuração para bloquear todas as funcionalidades do Destaque do Windows em dispositivos com Windows 10. Se você bloquear essa configuração, as configurações a seguir não ficarão disponíveis.
  - **Destaque do Windows na tela de bloqueio**: impedir que o Destaque do Windows exiba informações na tela de bloqueio do dispositivo.
  - **Sugestões de terceiros no Destaque do Windows**: impedir que o Destaque do Windows sugira conteúdo que não tenha sido publicado pela Microsoft.
  - **Recursos de Consumidor**: permite o bloqueio de recursos do consumidor, como sugestões do menu Iniciar e notificações de associação.
  - **Dicas do Windows**: permite bloquear a exibição de dicas pop-up no Windows.
  - **Destaque do Windows no centro de ação**: impedir sugestões do Destaque do Windows, como um novo aplicativo ou conteúdo de segurança, apareça, na Central de Ações do Windows.
  - **Personalização do Destaque do Windows**: impede que o Destaque do Windows personalize os resultados com base no uso de um dispositivo.
  - **Experiência de boas-vindas do Windows**: bloqueia a experiência de boas-vinda do Windows, que mostra as informações do usuário sobre os recursos novos ou atualizados.

## <a name="windows-defender-antivirus"></a>Windows Defender Antivírus

- **Monitoramento em tempo real**: habilita a verificação em tempo real de malware, spyware e outros tipos de software indesejados.
- **Monitoramento de comportamento**: permite que o Defender verifique se há certos padrões de atividade suspeita nos dispositivos.
- **NIS (Sistema de Inspeção de Rede)**: o NIS ajuda a proteger dispositivos contra explorações baseadas em rede. Ele utiliza assinaturas de vulnerabilidades conhecidas do Microsoft Endpoint Protection Center para ajudar a detectar e bloquear o tráfego mal-intencionado.
- **Examinar todos os downloads**: controla se o Defender examina todos os arquivos baixados da Internet.
- **Examinar scripts carregados nos navegadores da Web da Microsoft**: permite que o Defender verifique os scripts que são usados no Internet Explorer.
- **Acesso do usuário final ao Defender**: controla se a interface do usuário do Windows Defender fica oculta para usuários finais. Quando alterada, esta configuração entra em vigor na próxima vez em que o computador do usuário final for reiniciado.
- **Intervalo de atualização da assinatura (em horas)**: especifique o intervalo para o Defender verificar novos arquivos de assinatura.
- **Monitorar a atividade de arquivos e programas**: permite que o Defender monitore a atividade de arquivos e programas nos dispositivos.
- **Dias antes da exclusão de malware em quarentena**: permite que o Defender continue a rastrear o malware resolvido pelo número de dias que for especificado, para que você possa examinar manualmente os dispositivos afetados anteriormente. Se você definir o número de dias como **0**, o malware permanecerá na pasta de Quarentena e não será removido automaticamente.
- **Limite de uso de CPU durante uma verificação**: permite limitar quanto da CPU é usada durante as verificações (de **1** a **100**).
- **Verificar arquivos mortos**: permite que o Defender examine arquivos compactados, como ZIP ou CAB.
- **Examinar mensagens de email de entrada**: permite que o Defender examine mensagens de email assim que elas chegarem ao dispositivo.
- **Examinar unidades removíveis durante a varredura completa**: permite que o Defender examine unidades removíveis como pen drives.
- **Examinar unidades de rede mapeadas durante uma verificação completa**: permite que o Defender examine arquivos em unidades de rede mapeadas.
  Se os arquivos na unidade forem somente leitura, o Defender não consegue remover nenhum malware encontrado ali.
- **Examinar arquivos abertos de pastas de rede**: permite que o Defender verifique arquivos em unidades de rede compartilhadas (por exemplo, arquivos acessados de um caminho UNC). Se os arquivos na unidade forem somente leitura, o Defender não consegue remover nenhum malware encontrado ali.
- **Proteção da nuvem**: permite ou bloqueia o Microsoft Active Protection Service de receber informações sobre a atividade de malware de dispositivos gerenciados. Essas informações são usadas para aprimorar o serviço futuramente.
- **Avisar os usuários antes de envio de amostras**: controla se os arquivos potencialmente mal-intencionados que podem exigir mais análise são enviados automaticamente para a Microsoft.
- **Hora para realizar uma verificação rápida diária**: permite agendar uma verificação rápida que ocorre diariamente na hora que você selecionar.
- **Tipo de verificação do sistema a executar**: insira o nível de verificação executado ao agendar uma verificação do sistema.
- **Detectar aplicativos potencialmente indesejados**: escolha o nível de proteção quando o Windows detecta aplicativos potencialmente indesejados:
  - **Bloquear**
  - **Auditoria**. Para saber mais sobre aplicativos potencialmente indesejados, consulte [Detectar e bloquear aplicativos potencialmente indesejados](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
- **Ações sobre ameaças de malware detectadas**: use esta opção para escolher as ações que o Defender deve realizar para cada nível de ameaça detectada (Baixa, Moderada, Alta e Grave). Suas opções:
  - **Apagar**
  - **Quarentena**
  - **Removerr**
  - **Permitir**
  - **Definido pelo usuário**
  - **Bloquear**

### <a name="windows-defender-antivirus-exclusions"></a>Exclusões do Windows Defender Antivírus

- **Arquivos e pastas a excluir de varredura e da proteção em tempo real**: adiciona um ou mais arquivos e pastas, como **C:\Caminho** ou **%ProgramFiles%\Caminho\nomedoarquivo.exe**, à lista de exclusões. Esses arquivos e pastas não serão incluídos em verificações em tempo real ou programadas.
- **Extensões de arquivo a serem excluídas ao executar uma verificação ou usar a proteção em tempo real**: adicione uma ou mais extensões de arquivo, como **jpg** ou **txt**, à lista de exclusões. Qualquer arquivo com essas extensões serão excluídos de verificações em tempo real ou programadas.
- **Processos a excluir de varreduras e da proteção em tempo real**: adicione um ou mais processos do tipo **.exe**, **.com** ou **.scr** à lista de exclusões. Esses processos serão excluídos em verificações em tempo real ou programadas.

## <a name="next-steps"></a>Próximas etapas

Confira os detalhes técnicos adicionais sobre cada configuração e quais edições do Windows são compatíveis em [Referência do CSP de Política do Windows 10](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
