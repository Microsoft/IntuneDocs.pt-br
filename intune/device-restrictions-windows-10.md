---
title: Configurações de restrições de dispositivo para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Veja uma lista de todas as configurações e suas descrições para a criação de restrições de dispositivo no Windows 10 e em versões posteriores. Use essas configurações em um perfil de configuração para controlar capturas de tela, requisitos de senha, configurações de quiosque, aplicativos na loja, navegador Microsoft Edge, Windows Defender, acesso à nuvem, menu Iniciar e muito mais no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/05/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 943b5dc8c0fe1c9b55b9c4971be2087353b60428
ms.sourcegitcommit: e0374b3ced83c8876a4f78b326869c10588a55e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56307882"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>Configurações de dispositivo Windows 10 (e mais recente) para permitir ou restringir recursos usando o Intune

Este artigo lista e descreve todas as diferentes configurações que você pode controlar em dispositivos Windows 10 e mais recente. Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, definir regras de senha, personalizar a tela de bloqueio, usar o Windows Defender e muito mais.

Essas configurações são adicionadas a um perfil de configuração do dispositivo no Intune e, em seguida, atribuídas ou implantadas em dispositivos Windows 10.

> [!Note]
> Nem todas as opções estão disponíveis em todas as edições do Windows

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](device-restrictions-configure.md).

## <a name="app-store"></a>Loja de aplicativos

- **App Store (somente dispositivo móvel)**: Habilite ou bloqueie o uso da loja de aplicativos em dispositivos Windows 10 Mobile.
- **Atualização automática de aplicativos da store**: Permite que aplicativos instalados da Microsoft Store sejam atualizados automaticamente.
- **Instalação de aplicativo confiável**: Permite que os aplicativos assinados com um certificado de confiança sejam carregados por sideload.
- **Desbloqueio do desenvolvedor**: Permite que configurações de desenvolvedor do Windows, como a permissão de sideload de aplicativos, sejam modificadas pelo usuário final.
- **Dados de aplicativo do usuário compartilhados**: Permite que os aplicativos compartilhem dados entre usuários diferentes no mesmo dispositivo.
- **Usar somente repositório particular**: Habilite essa opção para permitir que os usuários finais baixem aplicativos somente de seu repositório particular.
- **Inicialização de aplicativo proveniente do repositório**: Usado para desabilitar todos os aplicativos que foram pré-instalados no dispositivo ou baixados na Microsoft Store.
- **Instalar dados de aplicativo no volume do sistema**: Impede que os aplicativos armazenem dados no volume do sistema do dispositivo.
- **Instalar aplicativos na unidade do sistema**: Impede que os aplicativos armazenem dados na unidade do sistema do dispositivo.
- **DVR de Jogos (somente área de trabalho)**: Configura se a gravação e a difusão de jogos são permitidas.
- **Somente aplicativos da loja**: Configura se os usuários podem instalar aplicativos de locais que não sejam a App Store.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade

- **Canal de dados da rede celular**: Impede que os usuários usem dados, como navegar na Web, quando estiverem conectados a uma rede celular. 
- **Roaming de dados**: Permita o roaming entre redes durante o acesso de dados.
- **VPN pela rede celular**: Controla se o dispositivo pode acessar conexões VPN quando conectado a uma rede celular.
- **Roaming de VPN na rede celular**: Controla se o dispositivo pode acessar conexões VPN quando estiver em roaming ou em uma rede celular.
- **Bluetooth**: Controla se o usuário pode habilitar e configurar o Bluetooth no dispositivo.
- **Detectabilidade de Bluetooth**: Permite que o dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth.
- **Pré-emparelhamento Bluetooth**: Permite configurar dispositivos Bluetooth específicos para emparelhá-los automaticamente com um dispositivo host.
- **Anúncios do Bluetooth**: Permite que o dispositivo receba anúncios via Bluetooth.
- **Serviço de dispositivos conectados**: Permite escolher se o serviço de dispositivos conectados será permitido, o que habilita a descoberta e a conexão com outros dispositivos Bluetooth.
- **NFC**: Permite que o usuário habilite e configure recursos de NFC (comunicação a curta distância) no dispositivo.
- **Wi-Fi**: Permite que o usuário habilite e configure o Wi-Fi no dispositivo (somente Windows 10 Mobile).
- **Conectar-se automaticamente a hotspots Wi-Fi**: Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceite os possíveis termos e condições da conexão automaticamente.
- **Configuração manual de Wi-Fi**: Controla se o usuário pode configurar suas próprias conexões Wi-Fi ou se pode usar somente as conexões configuradas por um perfil Wi-Fi (somente Windows 10 Mobile).
- **Intervalo de verificação de Wi-Fi**: Especifique com que frequência os dispositivos devem procurar redes Wi-Fi. Especifique um valor de 1 (mais frequentes) a 500 (menos frequente).
- **Serviços Bluetooth permitidos**: Especifique uma lista de serviços e perfis Bluetooth permitidos como cadeias de caracteres hexadecimais.

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento

- **Conta Microsoft**: Permite que o usuário associe uma conta da Microsoft ao dispositivo.
- **Conta não Microsoft**: Permite que os usuários adicionem ao dispositivo contas de email que não estejam associadas a uma conta Microsoft.
- **Sincronização de configurações de conta Microsoft**: Permite que as configurações de dispositivo e de aplicativo associadas a uma conta Microsoft sejam sincronizadas entre dispositivos.
- **Assistente de conexão de conta da Microsoft**: Escolha **Desabilitar** para impedir que os usuários finais controlem o serviço de Assistente de Entrada da Microsoft (wlidsvc), como interromper ou iniciar o serviço manualmente. Quando definido como **Não configurado**, o serviço do wlidsvc NT usa o sistema operacional (SO) padrão, que pode permitir que os usuários finais iniciem e parem o serviço. Esse serviço é usado pelo sistema operacional para permitir que os usuários entre em suas contas da Microsoft.

## <a name="cloud-printer"></a>Impressora de Nuvem

- **URL de descoberta de impressora**: Insira a URL para localizar impressoras em nuvem.
- **URL de autoridade de acesso à impressora**: Insira a URL de ponto de extremidade da Autenticação para obter tokens OAuth. Por exemplo, insira algo como `https://login.microsoftonline.com/your Azure AD Tenant ID`.
- **GUID do aplicativo cliente nativo do Azure**: Insira o GUID de um aplicativo cliente com permissão para obter tokens OAuth da OAuthAuthority.
- **URI de recurso do serviço de impressão**: Insira o URI de recurso OAuth do serviço de impressão configurado no portal do Azure. Por exemplo, insira algo como `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Número máximo de impressoras a serem consultadas (somente Mobile)**: Insira o número máximo de impressoras a serem consultadas. Por exemplo, insira `10`.
- **URI de recurso do serviço de descoberta de impressora**: Insira o URI de recurso OAuth do serviço de descoberta de impressora configurado no portal do Azure. Por exemplo, insira algo como `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Depois de instalar uma [Impressão de Nuvem Híbrida do Windows Server](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview), você poderá definir essas configurações e, em seguida, implantar em dispositivos do Windows.

## <a name="control-panel-and-settings"></a>Painel de controle e configurações

- **Aplicativo de configurações**: Bloqueia o acesso ao aplicativo de configurações do Windows.
  - **Sistema**: Bloqueia o acesso à área de sistema do aplicativo de configurações.
    - **Modificação das configurações de energia e suspensão (somente área de trabalho)**: Impede que o usuário final altere as configurações de energia e suspensão no dispositivo.
  - **Dispositivos**: Bloqueia o acesso à área de dispositivos do aplicativo de configurações.
  - **Rede e Internet**: Bloqueia o acesso à área de rede e da Internet do aplicativo de configurações.
  - **Personalização**: Bloqueia o acesso à área de personalização do aplicativo de configurações.
  - **Contas**: Bloqueia o acesso à área de contas do aplicativo de configurações.
  - **Hora e Idioma**: Bloqueia o acesso à área de hora e idioma do aplicativo de configurações.
    - **Modificação do horário do sistema**: Impede que o usuário final altere a data e hora do dispositivo.
    - **Modificação das configurações de região (somente área de trabalho)**: Impede que o usuário final altere as configurações de região no dispositivo.
    - **Modificação das configurações de idioma (somente área de trabalho)**: Impede que o usuário altere as configurações de idioma no dispositivo.
  - **Jogos**: Bloqueia o acesso ao aplicativo Jogos nas Configurações.
  - **Facilidade de Acesso**: Bloqueia o acesso à área de facilidade de acesso do aplicativo de configurações.
  - **Privacidade**: Bloqueia o acesso à área de privacidade do aplicativo de configurações.
  - **Atualização e Segurança**: Bloqueia o acesso à área de atualizações e segurança do aplicativo de configurações.

## <a name="display"></a>Vídeo

- **Ligar o ajuste de GDI para aplicativos**
- **Desligar o ajuste de GDI para aplicativos**

  O Ajuste de DPI GDI permite que aplicativos sem reconhecimento de DPI tenham reconhecimento de DPI por monitor. Insira os aplicativos herdados que têm o Ajuste de DPI GDI ativado. Com o Ajuste de DPI GDI configurado para ser ativado e desativado em um aplicativo, o dimensionamento fica desativado para o aplicativo.

## <a name="general"></a>Geral

- **Captura de tela (somente dispositivo móvel)**: Permite que o usuário capture a tela do dispositivo como uma imagem.
- **Copiar e colar (somente dispositivo móvel)**: Permite ações de copiar e colar entre aplicativos no dispositivo.
- **Cancelamento de registro manual**: Permite que o usuário exclua manualmente a conta da empresa do dispositivo.
  - Essa configuração de política não será aplicada se o computador estiver ingressado no Azure AD e o registro automático estiver habilitado. 
  - Essa configuração de política não se aplica a computadores que executam o Windows 10 Home.
- **Instalação manual de certificado raiz (somente dispositivo móvel)**: Impede que o usuário instale certificados raiz e certificados CAP intermediários manualmente.

- **Câmera**: Permite ou bloqueia o uso da câmera do dispositivo.
- **Sincronização de arquivos do OneDrive**: Bloqueia a sincronização de arquivos do dispositivo com o OneDrive.
- **Armazenamento removível**: Especifica se dispositivos de armazenamento externo, como cartões SD, podem ser usados com o dispositivo.
- **Localização geográfica**: Especifica se o dispositivo pode usar informações de serviços de localização.
- **Compartilhamento da Internet**: Permitir usar o compartilhamento de conexão com a Internet no dispositivo móvel.
- **Redefinição do telefone**: Controla se o usuário pode apagar seu dispositivo.
- **Conexão USB (somente dispositivo móvel)**: Controla se os dispositivos podem acessar dispositivos de armazenamento externo por meio de uma conexão USB.
- **Modo AntiTheft (somente dispositivo móvel)**: Configure se o modo Antitheft do Windows está habilitado.
- **Cortana**: Habilitar ou desabilitar a assistente de voz Cortana.
- **Gravação de voz (somente dispositivo móvel)**: Permita ou bloqueie o uso do gravador de voz do dispositivo.
- **Modificação do nome do dispositivo**: Impede que o usuário final altere o nome do dispositivo (somente Windows 10 Mobile)
- **Adicionar pacotes de provisionamento**: Bloqueia o agente de configuração de tempo de execução que instala os pacotes de provisionamento.
- **Remover pacotes de provisionamento**: Bloqueia o agente de configuração de tempo de execução que remove os pacotes de provisionamento.
- **Descoberta de dispositivo**: Bloqueia a descoberta de um dispositivo por outros dispositivos.
- **Alternador de Tarefas (somente dispositivo móvel)**: Bloqueia o alternador de tarefas no dispositivo.
- **Caixa de diálogo de erro do cartão SIM (somente dispositivo móvel)**: Bloqueia a exibição de uma mensagem de erro no dispositivo se nenhum cartão SIM é detectado.
- **Workspace do Ink**: Impede que os usuários acessem o Workspace do Ink. **Não configurado** habilita o espaço de trabalho do Ink e o usuário tem permissão para usá-lo na tela de bloqueio.
- **Reimplantação automática**: Permite que os usuários com direitos administrativos excluam todos os dados e configurações de usuário usando **CTRL+Win+R** na tela de bloqueio do dispositivo. O dispositivo é reconfigurado automaticamente e registrado novamente no gerenciamento.
- **Exigir que os usuários se conectem à rede durante a instalação do dispositivo (somente Participante do Programa Windows Insider)**: Escolha **Exigir** para que o dispositivo se conecte a uma rede antes de continuar, após a página Rede, durante a instalação do Windows 10. Embora esse recurso esteja na versão prévia, um Windows Insider build 1809 ou posterior é necessário para usar essa configuração.
- **Acesso Direto à Memória**: **Bloquear** impede o DMA (acesso direto à memória) para todas as portas downstream PCI com hot-plug até um usuário entre no Windows. **Habilitado** (padrão) permite o acesso a DMA, mesmo quando um usuário não esteja conectado.

  CSP: [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **Encerrar processos do Gerenciador de Tarefas**: Essa configuração determina se não administradores podem usar o Gerenciador de Tarefas para encerrar tarefas. **Bloquear** impede que os usuários padrão (não administradores) usem o Gerenciador de Tarefas para encerrar um processo ou uma tarefa no dispositivo. A opção **Não configurado** (padrão) permite que os usuários padrão encerrem um processo ou uma tarefa usando o Gerenciador de Tarefas.

## <a name="kiosk-preview---obsolete"></a>Quiosque (versão prévia) – obsoleto

Essas configurações são somente leitura e não podem ser alteradas. Para configurar o modo de quiosque, confira [Configurações de quiosque no Windows 10 e posterior](kiosk-settings.md).

Um dispositivo de quiosque geralmente executa um aplicativo ou um conjunto específico de aplicativos. Os usuários ficam impedidos de acessar quaisquer recursos ou funções no dispositivo.

- **Modo de quiosque**: Identifica o tipo de modo de quiosque compatível com a política. As opções incluem:

  - **Não configurado** (padrão): A política não habilita o modo de quiosque no dispositivo.
  - **Quiosque de aplicativo único**: O perfil habilita o dispositivo a executar somente um aplicativo. Quando o usuário faz logon, um aplicativo específico inicia. Esse modo também impede que o usuário abrir novos aplicativos ou alterar o aplicativo em execução.
  - **Quiosques de vários aplicativos**: O perfil permite que o dispositivo execute vários aplicativos. Somente os aplicativos que você adicionar estão disponíveis ao usuário. O benefício de um quiosque de vários aplicativos ou de um dispositivo com finalidade fixa é proporcionar uma experiência fácil para as pessoas entenderem apenas acessando os aplicativos de que precisam e removendo da exibição os aplicativos desnecessários.

#### <a name="single-app-kiosks"></a>Quiosques de aplicativo único

Insira as seguintes configurações:

- **Conta de usuário**: Insira a conta de usuário local (do dispositivo), uma conta de domínio do AD ou uma conta do Azure AD associada ao aplicativo de quiosque.
  - Conta local: Insira como `devicename\accountname`, `.\accountname` ou `accountname`
  - Conta de domínio: Insira como `domain\accountname`
  - Conta do Azure AD: Insira como `AzureAD\emailaddress`. Insira "AzureAD", porque ele é um nome de domínio fixo. Em seguida, siga com o endereço de email do Azure AD. Por exemplo, insira `AzureAD\user@contoso.onmicrosoft.com`.

    Para quiosques em ambientes de público com logon automático habilitado, um tipo de usuário com o privilégio mínimo (como a conta de usuário padrão local) deve ser usado. Se estiver usando uma conta do Azure AD para o modo de quiosque, não se esqueça de inserir `AzureAD\user@yourorganization.com`.

- **ID de modelo de usuário do aplicativo (AUMID) do aplicativo**: Insira a AUMID do aplicativo de quiosque. Para saber mais, consulte [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (Encontrar a ID do modelo de usuário do aplicativo de um aplicativo instalado).

#### <a name="multi-app-kiosks"></a>Quiosques de vários aplicativos

[Quiosques de vários aplicativos](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) usam uma configuração de quiosque que lista os aplicativos permitidos e outras configurações. 

Use o botão **Adicionar** para criar uma configuração de quiosque (ou selecionar uma configuração existente). Então, insira as seguintes configurações:

- **Nome da configuração de quiosque**: Insira um nome amigável usado para identificar a configuração.

- **Aplicativos de quiosque**: Insira os aplicativos que estão disponíveis no menu Iniciar. Os aplicativos que você adicionar são os únicos aplicativos que o usuário pode abrir.

  - **Tipo de Aplicativo**: Escolha o tipo de aplicativo de quiosque:
    - **Aplicativo Win32**: Um aplicativo da área de trabalho tradicional. Você precisa do nome do caminho totalmente qualificado do executável com relação ao dispositivo.
    - **Aplicativo UWP**: Um aplicativo universal do Windows. Você precisa do [AUMID do aplicativo](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

  - **Identificador**: Insira o nome do caminho totalmente qualificado do arquivo executável (aplicativos Win32) ou a [AUMID do aplicativo](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (aplicativos UWP).

- **Barra de tarefas**: Escolha **Habilitar** (mostrar) a barra de tarefas ou mantenha-a como **Não configurada** (oculta) no quiosque.

- **Layout do menu Iniciar**: Insira um arquivo XML que descreva como os aplicativos são exibidos no menu Iniciar. [Personalizar e exportar o layout inicial](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) fornece algumas diretrizes e XML de exemplo.

  [Criar um quiosque Windows 10 que executa aplicativos](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) fornece mais detalhes sobre como usar e criar arquivos XML.

- **Usuários atribuídos**: Adicione uma ou mais contas de usuário que podem usar os aplicativos adicionados. Quando a conta se conecta, apenas os aplicativos definidos na configuração estão disponíveis. A conta pode ser local para o dispositivo ou para uma conta do Azure AD associada ao aplicativo de quiosque.

    Para quiosques em ambientes de público com logon automático habilitado, um tipo de usuário com o privilégio mínimo (como a conta de usuário padrão local) deve ser usado. Para configurar uma conta do Azure AD (Active Directory) para o modo de quiosque, use o formato `domain\user@tenant.com`.

## <a name="locked-screen-experience"></a>Experiência na tela bloqueada

- **Notificações da central de ações (somente dispositivo móvel)**: Permite que as notificações da central de ações sejam exibidas na tela de bloqueio do dispositivo (somente Windows 10 Mobile).
- **URL da imagem de tela bloqueada (somente Área de Trabalho)**: Insira a URL para uma imagem no formato JPEG que será usada como o papel de parede da tela de bloqueio do Windows. Essa configuração bloqueia a imagem. A imagem não pode ser alterada posteriormente.
- **Tempo limite de tela configurável do usuário (somente dispositivos móveis)**: Permite que os usuários configurem o tempo 
- **Cortana na tela bloqueada (somente área de trabalho)**: Não permite que o usuário interaja com a Cortana quando o dispositivo está na tela de bloqueio (somente Windows 10 Desktop).
- **Notificações do sistema na tela bloqueada**: Bloqueia a exibição de mensagens de alerta na tela de bloqueio do dispositivo.
- **Tempo limite de tela (somente dispositivos móveis)**: Especifica o tempo em segundos, após o bloqueio da tela, em que ela será desligada.

## <a name="messaging"></a>Sistema de mensagens

- **Sincronização de mensagem (somente dispositivos móveis)**: Desabilite as Mensagens em qualquer lugar e o backup e a restauração de mensagens de texto.
- **MMS (somente dispositivos móveis)**: Desabilite a funcionalidade de envio/recebimento de MMS no dispositivo.
- **RCS (somente dispositivos móveis)**: Desabilite a funcionalidade de envio/recebimento dos Serviços de Comunicação Avançados no dispositivo.

## <a name="microsoft-edge-browser"></a>Navegador Microsoft Edge

### <a name="start-experience"></a>Experiência de inicialização

- **Iniciar o Microsoft Edge com**: Escolha quais páginas são abertas quando o Microsoft Edge é iniciado. Suas opções:
  - **Páginas iniciais**: O Microsoft Edge é iniciado com a página inicial padrão definida pelo sistema operacional
  - **Página Nova Guia**: O Microsoft Edge carrega o que estiver definido na configuração **URL da página Nova Guia**
  - **Página da última sessão**: O Microsoft Edge carrega a página da última sessão 
  - **Página inicial personalizada**: O Microsoft Edge carrega a página inicial definida pelo administrador de TI
- **O usuário pode alterar as páginas iniciais**: Com a opção **Permitir**, os usuários podem alterar as páginas iniciais. Os administradores podem usar `EdgeHomepageUrls` para inserir páginas iniciais que os usuários veem por padrão ao abrir o Microsoft Edge. **Não configurado** impede que os usuários alterem as páginas iniciais.
- **URL da página Nova Guia**: Insira a URL a ser aberta na página Nova Guia. Por exemplo, insira `https://www.bing.com`.
- **Abrir o conteúdo da Web na página Nova Guia**: Escolha **Bloquear** para impedir o Microsoft Edge de abrir um site em uma nova guia. Quando essa opção estiver bloqueada, a nova guia abre em branco. **Não configurado** usa o comportamento padrão do sistema operacional no dispositivo, que pode permitir que os usuários escolham o que é exibido.
- **Botão Página Inicial**: Escolha o que acontece quando o botão Página Inicial é selecionado. Suas opções:
  - **Páginas iniciais**: Abre a opção escolhida para a configuração **Abrir o Microsoft Edge com** é aberta
  - **Página Nova Guia**: Abre a opção escolhida para a configuração **URL da página Nova Guia**
  - **URL personalizada do botão Página Inicial**: Abre a opção escolhida para a configuração **URL do botão Página Inicial**
  - **Ocultar o botão Página Inicial**: Oculta o botão Página Inicial
- **O usuário pode alterar o botão Página Inicial**: Com a opção **Permitir**, os usuários podem alterar o botão Página Inicial. As alterações do usuário substituem as configurações do administrador para o botão Página Inicial. **Não configurado** usa o comportamento padrão do sistema operacional no dispositivo, o que pode impedir que os usuários alterem o modo como o administrador configurou o botão Página Inicial.
- **Mostrar a página da tela de apresentação**: A opção **Bloquear** impede a exibição da página de introdução na primeira vez que o Microsoft Edge é executado. Esse recurso permite que empresas, como as registradas em cenários de emissões zero, bloqueiem esta página. **Não configurado** mostra a página de introdução.
  - **URL da tela de apresentação**: Insira a URL da página a ser mostrada na primeira vez que um usuário executar o Microsoft Edge (somente Windows 10 Mobile).
- **Pop-ups**: Escolha **Bloquear** para impedir janelas pop-up no navegador. Aplica-se somente ao Windows 10 Desktop. **Não configurado** permite pop-ups no navegador da Web.
- **Enviar tráfego da intranet para o Internet Explorer**: Com a opção **Permitir**, os usuários podem abrir sites da intranet no Internet Explorer, em vez do Microsoft Edge (somente Windows 10 Desktop). **Não configurado** permite que os usuários usem o Microsoft Edge.
- **Localização do Enterprise Mode Site List**: Insira a URL que inclui uma lista de sites que são abertos no modo Empresarial. Os usuários não podem alterar essa lista. Aplica-se somente ao Windows 10 Desktop.
- **Mensagem ao abrir sites no Internet Explorer**: Use essa configuração para definir o Microsoft Edge para mostrar uma notificação antes de abrir um site no Internet Explorer 11. Suas opções:
  - **Não configurado**: Usa o comportamento padrão do sistema operacional, que pode não mostrar uma mensagem.
  - **Mostrar mensagem sem a opção para abrir sites no Microsoft Edge**: Mostra a mensagem ao abrir sites no IE. Os sites abrem no Internet Explorer. Não há uma opção para abrir sites no Microsoft Edge.
  - **Mostrar mensagem ao abrir sites no Microsoft Edge**: Mostra a mensagem ao abrir sites no IE. A mensagem contém um link para **Continuar no Microsoft Edge** de forma que os usuários podem escolher o Microsoft Edge ao invés do IE.

  > [!IMPORTANT]
  > Essa configuração exige que você habilite a opção **Configurar a Lista de Sites do Modo Empresarial**, a opção **Enviar todos os sites da Intranet para o Internet Explorer 11** ou ambas.

- **Lista de compatibilidade da Microsoft**: A opção **Bloquear** impede o uso da lista de compatibilidade da Microsoft no Microsoft Edge. Essa lista da Microsoft ajuda o Microsoft Edge a exibir corretamente sites com problemas de compatibilidade conhecidos. **Não configurado** permite o uso de uma lista de compatibilidade da Microsoft.
- **Pré-carregar as páginas iniciais e a página Nova Guia**: Escolha **Bloquear** para impedir o Microsoft Edge de pré-carregar as páginas iniciais e a página Nova Guia. O pré-carregamento reduz o tempo para iniciar o Microsoft Edge e carregar uma nova guia. **Não configurado** usa o comportamento padrão do sistema operacional, que pode ser pré-carregar essas páginas.
- **Pré-iniciar as páginas iniciais e a página Nova Guia**: Escolha **Bloquear** para impedir o Microsoft Edge de pré-iniciar as páginas iniciais e a página Nova Guia. A pré-inicialização ajuda o desempenho do Microsoft Edge e reduz o tempo necessário para iniciar o Microsoft Edge. **Não configurado** usa o comportamento padrão do sistema operacional, que pode ser pré-iniciar essas páginas.

### <a name="favorites-and-search"></a>Favoritos e pesquisa

- **Barra de favoritos**: Escolha o que acontece com a barra de favoritos em qualquer página do Microsoft Edge. Suas opções:
  - **Não configurado**: Usa o comportamento padrão do sistema operacional, que pode ocultar a barra de favoritos em todas as páginas. Os usuários podem alterar essa configuração.
  - **Ocultar**: Oculta a barra de favoritos em todas as páginas. Os usuários não podem alterar essa configuração.
  - **Mostrar**: Mostra a barra de favoritos em todas as páginas. Os usuários não podem alterar essa configuração.
- **Lista de Favoritos**: Adiciona uma lista de URLs ao arquivo de favoritos. Por exemplo, adicione `http://contoso.com/favorites.html`.
- **Restringir alterações aos Favoritos**: Escolha **Bloquear** para impedir os usuários de adicionar, importar, classificar ou editar a lista de Favoritos. **Não configurado** usa o padrão do sistema operacional, que pode permitir que os usuários alterem a lista.
- **Sincronizar favoritos entre navegadores da Microsoft (somente área de trabalho)**: A opção **Exigir** força o Windows a sincronizar favoritos entre o Internet Explorer e o Microsoft Edge. Adições, exclusões, modificações e alterações da ordem dos favoritos são compartilhadas entre navegadores.  **Não configurado** usa o padrão do sistema operacional, o que pode dar aos usuários a opção de sincronizar favoritos entre navegadores.
- **Mecanismo de pesquisa padrão**: Escolha o mecanismo de pesquisa padrão no dispositivo. Os usuários finais podem alterar esse valor a qualquer momento. Suas opções:
  - Padrão
  - Bing
  - Google
  - Yahoo
  - Valor personalizado
- **Pesquisar sugestões**: A opção **Não configurado** permite que o mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa na barra de endereços. **Bloquear** impede esse recurso.

### <a name="privacy-and-security"></a>Segurança e privacidade

- **Navegação InPrivate**: A opção **Bloquear** impede os usuários finais de abrir sessões de navegação InPrivate. **Não configurado** permite o uso desse recurso.
- **Salvar o histórico de navegação**: A opção **Bloquear** impede o Microsoft Edge de salvar o histórico de navegação. **Não configurado** permite salvar o histórico de navegação.
- **Limpar dados de navegação ao sair (somente Desktop)**: A opção **Exigir** limpa o histórico e os dados de navegação quando o usuário sai do Microsoft Edge. **Não configurado** usa o padrão do sistema operacional, que pode armazenar em cache os dados de navegação.
- **Sincronizar as configurações do navegador entre os dispositivos do usuário**: Escolha como deseja sincronizar as configurações do navegador entre dispositivos. Suas opções:
  - **Permitir**: Permite a sincronização de configurações do navegador Microsoft Edge entre os dispositivos do usuário
  - **Bloquear e habilitar a substituição do usuário**: Bloqueia a sincronização de configurações do navegador Microsoft Edge entre os dispositivos do usuário. Os usuários podem substituir essa configuração.
  - **Bloquear**: Bloqueia a sincronização de configuração do navegador Microsoft Edge entre os dispositivos do usuário. Os usuários não podem substituir essa configuração.
- **Gerenciador de senhas**: A opção **Bloquear** desabilita o recurso Gerenciador de Senhas do Microsoft Edge. **Não configurado** permite o uso desse recurso.
- **Cookies**: Escolha como lidar com os cookies no navegador da Web. Suas opções:
  - **Permitir**: Os cookies são armazenados no dispositivo.
  - **Bloquear todos os cookies**: Os cookies não são armazenados no dispositivo.
  - **Bloquear somente cookies de terceiros**: Cookies de terceiros ou de parceiros não são armazenados no dispositivo.
- **Preenchimento Automático**: A opção **Bloquear** desabilita o recurso Preenchimento Automático no dispositivo. **Não configurado**: permite que os usuários alterem as configurações de preenchimento automático no navegador (somente para computadores com Windows 10).
- **Enviar cabeçalhos Do Not Track**: A opção **Não configurado** exige que os dispositivos enviem cabeçalhos Do Not Track a sites que solicitam informações de acompanhamento (recomendado). Escolha **Bloquear** para impedir que o dispositivo envie esses cabeçalhos, o que permite que os sites rastreiem o usuário.
- **Endereço IP do localhost de WebRtc**: A opção **Bloquear** impede a exibição do endereço IP do localhost dos usuários ao fazer chamadas telefônicas usando o protocolo da Web RTC. **Não configurado** permite que os endereços IP de localhost dos usuários sejam mostrados ao fazer chamadas telefônicas usando esse protocolo.
- **Coleta de dados do Bloco Dinâmico**: Escolha **Bloquear** para impedir o Windows de coletar informações do Bloco Dinâmico quando um site é fixado no menu Iniciar por meio do Microsoft Edge. **Não configurado** permite que essas informações sejam coletadas.
- **O usuário pode substituir os erros de certificado**: A opção **Bloquear** impede os usuários de acessar sites que tenham erros SSL ou TLS. **Não configurado** permite que os usuários acessem esses sites.

### <a name="additional"></a>Adicional

- **Navegador Microsoft Edge (somente dispositivos móveis)**: Escolha **Bloquear** para impedir o uso do Microsoft Edge no dispositivo. Se você bloquear o Microsoft Edge, as configurações individuais serão aplicadas apenas à área de trabalho. **Não configurado** permite o uso do navegador da Web Microsoft Edge no dispositivo.
- **Lista suspensa da barra de endereços (somente área de trabalho)**: A opção **Bloquear** impede o Microsoft Edge de exibir uma lista de sugestões em uma lista suspensa quando você digita. Essa opção ajuda a minimizar o uso de largura de banda da rede entre o Microsoft Edge e os serviços da Microsoft. **Não configurado** permite que o Microsoft Edge mostre uma lista de sugestões.
- **Tela inteira**: Escolha **Bloquear** para impedir o Microsoft Edge de mostrar apenas o conteúdo da Web e ocultar o Microsoft Edge (modo de tela inteira). **Não configurado** usa o padrão do sistema operacional, que permite que o Microsoft Edge use o modo de tela inteira.
- **Sobre sinalizadores**: A opção **Bloquear** impede os usuários finais de acessar a página `about:flags` no Microsoft Edge, que inclui configurações experimentais e de desenvolvedor. **Não configurado** usa o padrão do sistema operacional, que pode permitir o acesso à página `about:flags`.
- **Ferramentas para desenvolvedores**: A opção **Bloquear** impede os usuários finais de abrir as ferramentas para desenvolvedores do Microsoft Edge. **Não configurado** permite que os usuários abram as ferramentas para desenvolvedores.
- **Extensões**: A opção **Não configurado** permite que os usuários finais instalem extensões do Microsoft Edge no dispositivo. **Bloquear** impede a instalação.
- **Extensões do desenvolvedor do sideload**: A opção **Bloquear** impede o Microsoft Edge de fazer sideload, que instala e executa extensões não verificadas usando o recurso **Carregar extensões**. **Não configurado** usa o padrão do sistema operacional, que pode permitir o sideloading.
- **Extensões obrigatórias**: Escolha quais extensões não podem ser desligadas pelos usuários finais no Microsoft Edge. Insira os nomes das famílias de pacotes e selecione **Adicionar**. As listas [Localizar um nome da família de pacotes (PFN)](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) oferecem algumas orientações.

  Você também pode **Importar** um arquivo CSV que inclui os nomes das famílias de pacotes.

- **JavaScript**: Escolha **Bloquear** para impedir a execução de scripts Java no navegador do dispositivo. **Não configurado** permite que scripts, como JavaScript, sejam executados no navegador Microsoft Edge.

## <a name="network-proxy"></a>Proxy de rede

- **Detectar automaticamente as configurações de proxy**: Quando essa opção é habilitada, o dispositivo tenta localizar o caminho para um script PAC.
- **Usar script de proxy**: Selecione essa opção para inserir um caminho para um script PAC a fim de configurar o servidor proxy.
  - **Configurar URL do endereço de script**: Insira a URL de um script PAC que deseja usar para configurar o servidor proxy.
- **Usar um servidor proxy manual**: Selecione essa opção para inserir manualmente as informações do servidor proxy.
  - **Endereço**: Insira o nome ou o endereço IP do servidor proxy.
  - **Número da porta**: Insira o número da porta do servidor proxy.
  - **Exceções de proxy**: Insira as URLs que não devem usar o servidor proxy. Use um ponto e vírgula para separar cada item.
  - **Ignorar servidor proxy para endereço local**: Caso não deseje usar o servidor proxy para endereços locais na intranet, habilite essa opção.

## <a name="password"></a>Senha

- **Senha**: Exige que o usuário final insira uma senha para acessar o dispositivo.
  - **Tipo de senha necessária**: Especifica se a senha precisa ser apenas numérica ou alfanumérica.
  - **Comprimento mínimo da senha**: Aplica-se somente ao Windows 10 Mobile.
  - **Número de falhas de início de sessão antes de limpar o dispositivo**: Para dispositivos que executam o Windows 10: Se o dispositivo tiver o BitLocker habilitado, ele será colocado no modo de recuperação do BitLocker depois que a conexão falhar o número de vezes especificado. Se o dispositivo não tiver o BitLocker habilitado, essa configuração não se aplica. Para dispositivos que executam o Windows 10 Mobile: Depois que a conexão falhar o número de vezes especificado, o dispositivo será apagado.
  - **Máximo de minutos de inatividade até a tela ser bloqueada**: Especifica o período que um dispositivo deve permanecer ocioso antes da tela ser bloqueada.
  - **Expiração da senha (dias)**: Especifica o período após o qual a senha do dispositivo deve ser alterada.
  - **Evitar a reutilização de senhas anteriores**: Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo.
  - **Exigir senha quando o dispositivo retorna do estado ocioso (somente Mobile)**: Especifica que o usuário deverá inserir uma senha para desbloquear o dispositivo (somente para Windows 10 Mobile).
  - **Senhas simples**: Permite o uso de senhas simples, como 1111 ou 1234. Essa configuração também permite ou bloqueia o uso de senhas de imagem do Windows.

## <a name="per-app-privacy-exceptions"></a>Exceções de privacidade por aplicativo

Você pode adicionar aplicativos que devem ter um comportamento de privacidade diferente do definido em "Privacidade padrão".

- **Nome do Pacote**: Nome da família do pacote do aplicativo.
- **Nome do Aplicativo**: O nome do aplicativo.

### <a name="exceptions"></a>Exceções

- **Informações da conta**: Defina se esse aplicativo pode acessar o nome de usuário, a imagem e outras informações de contato.
- **Aplicativos em segundo plano**: Defina se esse aplicativo pode ser executado em segundo plano.
- **Calendário**: Defina se esse aplicativo pode acessar o calendário.
- **Histórico de chamadas**: Defina se esse aplicativo pode acessar o histórico de chamadas.
- **Câmera**: Defina se esse aplicativo pode acessar a câmera.
- **Contatos**: Defina se esse aplicativo pode acessar os contatos.
- **Email**: Defina se esse aplicativo pode acessar e enviar emails.
- **Localização**: Defina se esse aplicativo pode acessar informações de localização.
- **Mensagens**: Defina se esse aplicativo pode ler ou enviar mensagens de texto ou MMS.
- **Microfone**: Defina se esse aplicativo pode usar o microfone.
- **Movimento**: Defina se esse aplicativo pode acessar informações de movimento do dispositivo.
- **Notificações**: Defina se esse aplicativo pode acessar as notificações.
- **Telefone**: Defina se esse aplicativo pode acessar o telefone.
- **Rádios**: Alguns aplicativos usam rádios (por exemplo, Bluetooth) no dispositivo para enviar e receber dados e precisam ativar ou desligar essas rádios. Defina se este aplicativo pode controlar essas rádios.
- **Tarefas**: Defina se esse aplicativo pode acessar suas tarefas.
- **Dispositivos confiáveis**: Escolha se esse aplicativo pode usar dispositivos confiáveis, ou seja, o hardware que você já conectou ou que acompanha o dispositivo. Por exemplo, usar TVs, projetores e assim por diante como dispositivos confiáveis.
- **Comentários e diagnóstico**: Defina se esse aplicativo pode acessar informações de diagnóstico.
- **Sincronização com dispositivos**: Escolha se esse aplicativo pode compartilhar e sincronizar automaticamente informações com dispositivos sem fio que não são emparelhados explicitamente com o dispositivo.

## <a name="personalization"></a>Personalização

- **URL da imagem de tela de fundo da área de trabalho (somente Desktop)**: Insira a URL para uma imagem no formato JPEG que você deseja usar como o papel de parede da área de trabalho do Windows. Os usuários não podem alterar a foto.

## <a name="printer"></a>Impressora

- **Impressoras**: Lista de impressoras locais que foram adicionadas.
- **Impressora padrão**: Defina a impressora padrão.
- **Acesso de usuário à adição de novas impressoras**: Permita ou bloqueie o uso de impressoras locais.

## <a name="privacy"></a>Privacidade

- **Personalização de entrada**: Não permita o uso de serviços de fala baseados em nuvem para a Cortana, ditado ou aplicativos da Microsoft Store. Se você permitir esses serviços, a Microsoft poderá coletar dados de voz para melhorar o serviço.
- **Aceitação automática das solicitações de consentimento do usuário de privacidade e emparelhamento**: Permita que o Windows aceite automaticamente mensagens de consentimento de privacidade e emparelhamento ao executar aplicativos.
- **Publicar atividades do usuário**: A opção **Bloquear** impede o compartilhamento de experiências e a descoberta de recursos usados recentemente no alternador de tarefas.
- **Apenas atividades locais**: A opção **Bloquear** impede o compartilhamento de experiências e a descoberta de recursos usados recentemente no alternador de tarefas, com base somente em atividades locais.

Você pode configurar as informações que todos os aplicativos no dispositivo podem acessar. Você pode definir exceções de acordo com o aplicativo que usa **Exceções de privacidade por aplicativo**.

### <a name="exceptions"></a>Exceções

- **Informações da conta**: Defina se esse aplicativo pode acessar o nome de usuário, a imagem e outras informações de contato.
- **Aplicativos em segundo plano**: Defina se esse aplicativo pode ser executado em segundo plano.
- **Calendário**: Defina se esse aplicativo pode acessar o calendário.
- **Histórico de chamadas**: Defina se esse aplicativo pode acessar o histórico de chamadas.
- **Câmera**: Defina se esse aplicativo pode acessar a câmera.
- **Contatos**: Defina se esse aplicativo pode acessar os contatos.
- **Email**: Defina se esse aplicativo pode acessar e enviar emails.
- **Localização**: Defina se esse aplicativo pode acessar informações de localização.
- **Mensagens**: Defina se esse aplicativo pode ler ou enviar mensagens de texto ou MMS.
- **Microfone**: Defina se esse aplicativo pode usar o microfone.
- **Movimento**: Defina se esse aplicativo pode acessar informações de movimento do dispositivo.
- **Notificações**: Defina se esse aplicativo pode acessar as notificações.
- **Telefone**: Defina se esse aplicativo pode acessar o telefone.
- **Rádios**: Alguns aplicativos usam rádios (por exemplo, Bluetooth) no dispositivo para enviar e receber dados e precisam ativar ou desligar essas rádios. Defina se este aplicativo pode controlar essas rádios.
- **Tarefas**: Defina se esse aplicativo pode acessar suas tarefas.
- **Dispositivos confiáveis**: Escolha se esse aplicativo pode usar dispositivos confiáveis. Dispositivos confiáveis são o hardware que você já conectou ou que acompanha o dispositivo. Por exemplo, usar TVs, projetores etc. como dispositivos confiáveis.
- **Comentários e diagnóstico**: Escolha se esse aplicativo pode acessar informações de diagnóstico.
- **Sincronização com dispositivos** – defina se este aplicativo pode compartilhar e sincronizar automaticamente informações com dispositivos sem fio que não emparelham explicitamente com este computador, tablet ou telefone.

## <a name="projection"></a>Projeção

- **Entrada do usuário de receptores de vídeo sem fio**: Bloqueia a entrada do usuário de receptores de vídeo sem fio.
- **Projeção neste computador**: Impede que outros dispositivos localizem o computador para projeção.
- **Exigir um PIN para emparelhamento**: Exija um PIN ao se conectar a um dispositivo de projeção.

## <a name="reporting-and-telemetry"></a>Relatório e telemetria

- **Compartilhar dados de uso**: Escolha o nível de dados de diagnóstico que são enviados. Suas opções:
  - Segurança 
  - Basic
  - Avançado
  - Completo
- **Enviar dados de navegação do Microsoft Edge para a Análise do Microsoft 365**: Para usar esse recurso, defina as configurações **Compartilhar dados de uso** como **Avançado** ou **Completo**. Esse recurso controla quais dados de dispositivos corporativos com uma ID comercial configurada o Microsoft Edge envia para a Análise do Microsoft 365. Suas opções:
  - **Não configurado**: Usa o padrão do sistema operacional, que pode não enviar dados do histórico de navegação
  - **Enviar somente dados da intranet**: Permite que o administrador envie o histórico de dados da intranet
  - **Enviar somente dados da Internet**: Permite que o administrador envie o histórico de dados da Internet
  - **Enviar dados da intranet e da Internet**: Permite que o administrador envie o histórico de dados da intranet e da Internet
- **Servidor proxy de telemetria**: Insira o FQDN (nome de domínio totalmente qualificado) ou o endereço IP de um servidor proxy para encaminhar solicitações de Experiência do Usuário Conectado e Telemetria usando uma conexão do protocolo SSL. O formato para essa configuração é *servidor*:*porta*. Se o proxy nomeado falhar ou se não for inserido um proxy ao habilitar essa política, os dados de Experiências e Telemetria do Usuário Conectado não serão enviados e permanecerão no dispositivo local.

  Formatos de exemplo:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

## <a name="search"></a>Pesquisar

- **Pesquisa Segura (somente dispositivos móveis)**: Controla como a Cortana filtra o conteúdo para adulto nos resultados da pesquisa. Você pode selecionar **Estrito**, **Moderado** ou permitir que o usuário final escolha suas próprias configurações.
- **Exibir resultados da Web na pesquisa**: Bloqueie ou permita que os resultados da Web sejam exibidos nas pesquisas feitas no dispositivo.

## <a name="start"></a>Inicie o

- **Layout do menu Iniciar**: Para personalizar o menu Iniciar em dispositivos de desktop, você pode carregar um arquivo XML que inclua suas personalizações, incluindo a ordem em que os aplicativos são listados, entre outros. Os usuários não podem alterar o layout do menu Iniciar que você inserir.
- **Fixar sites como blocos no menu Iniciar**: Importe imagens do Microsoft Edge mostradas como links no menu Iniciar do Windows para dispositivos de desktop.
- **Desafixar aplicativos da barra de tarefas**: Escolha **Bloquear** para impedir o usuário de desafixar aplicativos da barra de tarefas.
- **Troca Rápida de Usuário**: Escolha **Bloquear** para impedir a troca entre os usuários que estão conectados simultaneamente sem fazer logoff.
- **Aplicativos mais usados**: Escolha **Bloquear** para ocultar a exibição dos aplicativos mais usados no menu Iniciar. Isso também desabilita a alternância correspondente no aplicativo Configurações.
- **Aplicativos adicionados recentemente**: Escolha **Bloquear** para ocultar a exibição dos aplicativos adicionados recentemente no menu Iniciar. Isso também desabilita a alternância correspondente no aplicativo Configurações.
- **Modo de tela inicial**: Escolha como a tela inicial é mostrada. Escolha exibi-la como **Tela inteira** ou **Tela não inteira**.
- **Itens abertos recentemente nas Listas de Atalhos**: Escolha **Bloquear** para ocultar a exibição das listas de atalhos recentes no menu Iniciar e na barra de tarefas. Isso também desabilita a alternância correspondente no aplicativo Configurações.
- **Lista de aplicativos**: Escolha como o aplicativo Configurações é exibido. Suas opções: 
  - Recolher
  - Recolher e desabilitar o aplicativo Configurações 
  - Remove e desabilita o aplicativo Configurações
- **Botão de energia**: Escolha **Bloquear** para ocultar a exibição do botão de energia no menu Iniciar.
- **Bloco do Usuário**: Escolha **Bloquear** para ocultar a exibição do bloco do usuário no menu Iniciar.
  - **Bloqueio**: Escolha **Bloquear** para ocultar a exibição da opção `Lock` no bloco do usuário no menu Iniciar.
  - **Sair**: Escolha **Bloquear** para ocultar a exibição da opção `Sign out` no bloco do usuário no menu Iniciar.
- **Desligar**: Escolha **Bloquear** para ocultar a exibição das opções `Update and shut down` e `Shut down` no botão de energia no menu Iniciar.
- **Suspender**: Escolha **Bloquear** para ocultar a exibição da opção `Sleep` no botão de energia no menu Iniciar.
- **Hibernar**: Escolha **Bloquear** para ocultar a exibição da opção `Hibernate` no botão de energia no menu Iniciar.
- **Trocar Conta**: Escolha **Bloquear** para ocultar a exibição de `Switch account` no bloco do usuário no menu Iniciar.
- **Opções de Reinicialização**:  Escolha **Bloquear** para ocultar a exibição das opções `Update and restart` e `Restart` no botão de energia no menu Iniciar.
- **Documentos em Iniciar**: Oculte ou mostre a pasta Documentos no menu Iniciar do Windows.
- **Downloads em Iniciar**: Oculte ou mostre a pasta Downloads no menu Iniciar do Windows.
- **Explorador de Arquivos em Iniciar**: Oculte ou mostre o aplicativo Explorador de Arquivos no menu Iniciar do Windows.
- **HomeGroup em Iniciar**: Oculte ou mostre a pasta HomeGroup no menu Iniciar do Windows.
- **Música em Iniciar**: Oculte ou mostre a pasta Música no menu Iniciar do Windows.
- **Rede em Iniciar**: Oculte ou mostre a pasta Rede no menu Iniciar do Windows.
- **Pasta Pessoal em Iniciar**: Oculte ou mostre a pasta Pessoal no menu Iniciar do Windows.
- **Imagens em Iniciar**: Oculte ou mostre a pasta de imagens no menu Iniciar do Windows.
- **Configurações em Iniciar**: Oculte ou mostre o aplicativo Configurações no menu Iniciar do Windows.
- **Vídeos em Iniciar**: Oculte ou mostre a pasta de vídeos no menu Iniciar do Windows.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **SmartScreen para Microsoft Edge**: Habilite o SmartScreen do Microsoft Edge para acessar downloads do site e de arquivos.
- **Acesso a sites mal-intencionados**: Impeça os usuários de ignorar os avisos de Filtro do Windows Defender SmartScreen e impeça-os de visitar o site.
- **Download de arquivo não verificado**: Impeça os usuários de ignorar os avisos de Filtro do Windows Defender SmartScreen e impeça-os de baixar arquivos não verificados.

## <a name="windows-spotlight"></a>Destaque do Windows

- **Destaque do Windows**: Use essa configuração para bloquear todas as funcionalidades do Destaque do Windows em dispositivos Windows 10. Se você bloquear essa configuração, as configurações a seguir não ficarão disponíveis.
  - **Destaque do Windows na tela de bloqueio**: Impeça a exibição de informações do Destaque do Windows na tela de bloqueio do dispositivo.
  - **Sugestões de terceiros no Destaque do Windows**: Impeça a sugestão do Destaque do Windows de conteúdo não publicado pela Microsoft.
  - **Recursos de Consumidor**: Permite bloquear recursos de consumidor, como sugestões no menu Iniciar e notificações de associação.
  - **Dicas do Windows**: Permite bloquear a exibição de dicas pop-up no Windows.
  - **Destaque do Windows na central de ações**: Bloqueie a exibição de sugestões do Destaque do Windows, como um novo aplicativo ou conteúdo de segurança, na central de ações do Windows.
  - **Personalização do Destaque do Windows**: Impede o Destaque do Windows de personalizar os resultados com base no uso de um dispositivo.
  - **Experiência de Boas-vindas do Windows**: Bloqueie a experiência de Boas-vindas do Windows, que mostra ao usuário informações sobre recursos novos ou atualizados.

## <a name="windows-defender-antivirus"></a>Windows Defender Antivírus

- **Monitoramento em tempo real**: Habilita a verificação em tempo real de malware, spyware e outros softwares indesejados.
- **Monitoramento de comportamento**: Permite que o Defender verifique se há certos padrões de atividade suspeita nos dispositivos.
- **NIS (Sistema de Inspeção de Rede)**: O NIS ajuda a proteger dispositivos contra explorações baseadas em rede. Ele utiliza assinaturas de vulnerabilidades conhecidas do Microsoft Endpoint Protection Center para ajudar a detectar e bloquear o tráfego mal-intencionado.
- **Examinar todos os downloads**: Controla se o Defender examina todos os arquivos baixados da Internet.
- **Examinar scripts carregados em navegadores da Web da Microsoft**: Permite que o Defender examine scripts que são usados no Internet Explorer.
- **Acesso do usuário final ao Defender**: Controla se a interface do usuário do Windows Defender está oculta para usuários finais. Quando alterada, esta configuração entra em vigor na próxima vez em que o computador do usuário final for reiniciado.
- **Intervalo de atualização de assinaturas (em horas)**: Especifica o intervalo no qual o Defender verifica novos arquivos de assinatura.
- **Monitorar a atividade de arquivos e de programas**: Permite que o Defender monitore a atividade de arquivos e programas nos dispositivos.
- **Dias antes da exclusão de malware em quarentena**: Permite que o Defender continue a rastrear o malware resolvido pelo número de dias que especificado para que você possa examinar manualmente os dispositivos infectados anteriormente. Se você definir o número de dias como **0**, o malware permanecerá na pasta de Quarentena e não será removido automaticamente.
- **Limite de uso da CPU durante um exame**: Permite limitar a quantidade de CPU que as verificações têm permissão para usar (de **1** a **100**).
- **Examinar arquivos mortos**: Permite que o Defender examine arquivos armazenados como arquivos Zip ou Cab.
- **Examinar mensagens de email recebidas**: Permite que o Defender examine mensagens de email assim que elas chegarem ao dispositivo.
- **Examinar unidades removíveis durante um exame completo**: Permite que o Defender examine unidades removíveis, como cartões USB.
- **Examinar unidades de rede mapeadas durante um exame completo**: Permite que o Defender examine arquivos em unidades de rede mapeadas.
  Se os arquivos na unidade forem somente leitura, o Defender não consegue remover nenhum malware encontrado ali.
- **Examinar arquivos abertos em pastas de rede**: Permite que o Defender examine arquivos em unidades de rede compartilhadas (por exemplo, arquivos acessados em um caminho UNC). Se os arquivos na unidade forem somente leitura, o Defender não consegue remover nenhum malware encontrado ali.
- **Proteção de nuvem**: Permite ou bloqueia o Microsoft Active Protection Service de receber informações sobre a atividade de malware de dispositivos gerenciados. Essas informações são usadas para aprimorar o serviço futuramente.
- **Perguntar aos usuários antes do envio de amostras**: Controla se arquivos potencialmente mal-intencionados que possam exigir análise adicional são enviados automaticamente para a Microsoft.
- **Hora para realizar um exame rápido diário**: Permite agendar uma verificação rápida que ocorre diariamente na hora que você selecionar.
- **Tipo de exame do sistema a ser realizado**: Insira o nível de exame que é executado quando você agenda um exame do sistema.
- **Detectar aplicativos potencialmente indesejados**: Escolha o nível de proteção quando o Windows detecta aplicativos potencialmente indesejados entre:
  - **Bloquear**
  - **Auditoria**. Para saber mais sobre aplicativos potencialmente indesejados, consulte [Detectar e bloquear aplicativos potencialmente indesejados](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
- **Ações contra ameaças de malware detectadas**: Use essa opção para escolher as ações que o Defender executará para cada nível de ameaça detectado (Baixo, Moderado, Alto e Grave). Suas opções:
  - **Apagar**
  - **Quarentena**
  - **Removerr**
  - **Permitir**
  - **Definido pelo usuário**
  - **Bloquear**

### <a name="windows-defender-antivirus-exclusions"></a>Exclusões do Windows Defender Antivírus

- **Arquivos e pastas a serem excluídos de exames e da proteção em tempo real**: Adiciona um ou mais arquivos e pastas como **C:\Path** ou **ProgramFiles%\Path\filename.exe** à lista de exclusões. Esses arquivos e pastas não serão incluídos em verificações em tempo real ou programadas.
- **Extensões de arquivo a serem excluídas de exames e da proteção em tempo real**: Adicionar uma ou mais extensões de arquivo como **jpg** ou **txt** à lista de exclusões. Qualquer arquivo com essas extensões serão excluídos de verificações em tempo real ou programadas.
- **Processos a serem excluídos de exames e da proteção em tempo real**: Adicionar um ou mais processos do tipo **.exe**, **.com**, ou **. scr** à lista de exclusões. Esses processos serão excluídos em verificações em tempo real ou programadas.

## <a name="next-steps"></a>Próximas etapas

Confira os detalhes técnicos adicionais sobre cada configuração e quais edições do Windows são compatíveis em [Referência do CSP de Política do Windows 10](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
