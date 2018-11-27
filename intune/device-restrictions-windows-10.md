---
title: Configurações de restrições de dispositivo para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Conheça as configurações do Microsoft Intune que você pode usar para controlar as configurações e as funcionalidades de dispositivos que executam o Windows 10.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: c49da9c323e1c4124ad76ae64e63a177edfcaa71
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189972"
---
# <a name="device-restriction-for-windows-10-and-newer-settings-in-intune"></a>Restrição de dispositivo para configurações do Windows 10 (e mais recentes) no Intune
Este artigo mostra todas as configurações de restrições de dispositivo do Microsoft Intune que você pode definir para dispositivos que executam o Windows 10.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

> [!Note]
> Nem todas as opções estão disponíveis em todas as edições do Windows

## <a name="general"></a>Geral
- **Captura de tela (somente dispositivo móvel)** – permite que o usuário capture a tela do dispositivo como uma imagem.
- **Copiar e colar (somente dispositivo móvel)** – Permitir utilizar ações de copiar e colar entre os aplicativos do dispositivo.
- **Cancelamento de registro manual** – Permite que o usuário exclua manualmente a conta de trabalho do dispositivo.
   - Essa configuração de política não será aplicada se o computador estiver ingressado no Azure AD e o registro automático estiver habilitado. 
   - Essa configuração de política não se aplica a computadores que executam o Windows 10 Home.
- **Instalação manual do certificado raiz (somente dispositivo móvel)** - impede que o usuário instale manualmente os certificados raiz e certificados CAP intermediários.

- **Câmera** – Permite ou bloqueia o uso da câmera do dispositivo.
- **Sincronização de arquivos do OneDrive** - bloqueia a sincronização de arquivos do dispositivo com o OneDrive.
- **Armazenamento removível** – Especifica se é possível usar dispositivos de armazenamento externo, como cartões SD, no dispositivo.
- **Geolocalização** – Especifica se o dispositivo pode usar informações de serviços de localização.
- **Compartilhamento da Internet** – Permite o uso do compartilhamento de conexão com a Internet no dispositivo.
- **Redefinição do telefone** – controla se o usuário pode realizar um apagamento no dispositivo.
- **Conexão USB (somente dispositivos móveis)** – controla se os dispositivos podem acessar dispositivos de armazenamento externo por meio de uma conexão USB.
- **Modo AntiTheft (somente dispositivos móveis)** – configure se o modo AntiTheft do Windows está habilitado.
- **Cortana** – Habilitar ou desabilitar a assistente de voz Cortana.
- **Gravação de voz (somente dispositivos móveis)** – Permitir ou bloquear o uso do gravador de voz do dispositivo.
- **Modificação do nome do dispositivo** – impede que o usuário final altere o nome do dispositivo (Windows 10 Mobile apenas)
- **Adicionar pacotes de provisionamento** - bloqueia o agente de configuração de tempo de execução que instala os pacotes de provisionamento.
- **Remover pacotes de provisionamento** - bloqueia o agente de configuração de tempo de execução que remove os pacotes de provisionamento.
- **Descoberta de dispositivos** - bloqueia a descoberta de um dispositivo por outros dispositivos.
- **Alternador de tarefas (somente dispositivos móveis)** - bloqueia o alternador de tarefas no dispositivo.
- **Diálogo de erro do cartão SIM (somente dispositivos móveis)** - bloqueia a exibição de uma mensagem de erro no dispositivo se nenhum cartão SIM for detectado.
- **Workspace do Ink** – impedir que usuários acessem o workspace do Ink. Quando definido como **Não configurado**, o workspace do Ink fica habilitado (o recurso é ativado) e o usuário tem permissão para usá-lo sobre a tela de bloqueio.
- **Reimplantação automática** – permite que usuários com direitos administrativos excluam todos os dados e configurações de usuário usando **Ctrl+Win+R** na tela de bloqueio do dispositivo. O dispositivo é reconfigurado automaticamente e registrado novamente no gerenciamento.
- **Exigir que os usuários se conectem à rede durante a instalação de dispositivo (somente para Participante do Programa Windows Insider)** – Escolha **Exigir** para que o dispositivo se conecte a uma rede antes de continuar, após da página Rede, durante a instalação do Windows 10. Embora esse recurso esteja na versão prévia, um Windows Insider build 1809 ou posterior é necessário para usar essa configuração.

## <a name="password"></a>Senha
-   **Senha** – Exige que o usuário final insira uma senha para acessar o dispositivo.
    -   **Tipo de senha exigida** – Especifica se a senha deve ser apenas numérica ou alfanumérica.
    -   **Tamanho mínimo da senha** – Aplicável somente a Windows 10 Mobile.
    -   **Número de falhas de entrada antes de apagar o dispositivo** – Para dispositivos que executam o Windows 10: se o dispositivo tiver o BitLocker habilitado, ele será colocado no modo de recuperação do BitLocker depois que a entrada falhar o número de vezes especificado. Se o dispositivo não tiver o BitLocker habilitado, essa configuração não será aplicada.
Para dispositivos que executam o Windows Mobile 10: depois que a entrada falhar o número de vezes que você especificar, o dispositivo será apagado.
    -   **Máximo de minutos de inatividade para o bloqueio de tela** – Especifica o período que um dispositivo deve permanecer ocioso antes da tela ser bloqueada.
    -   **Expiração de senha (dias)** – Especifica o período após o qual a senha do dispositivo deve ser alterada.
    -   **Impedir a reutilização de senhas anteriores** – Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo.
    -   **Exigir senha quando o dispositivo retorna do estado inativo (somente dispositivos móveis)** – Especifica que o usuário deverá inserir uma senha para desbloquear o dispositivo (somente Windows 10 Mobile).
    -   **Senhas simples** – Permita o uso de senhas simples como 1111 ou 1234. Essa configuração também permite ou bloqueia o uso de senhas de imagem do Windows.
-   **Criptografia** – habilitar a criptografia nos dispositivos de destino.

## <a name="personalization"></a>Personalização

- **URL da imagem de tela de fundo da área de trabalho (somente Desktop)** – Insira a URL para uma imagem no formato JPEG que deseja usar como o papel de parede da área de trabalho do Windows. Os usuários não podem alterar a foto.

## <a name="privacy"></a>Privacidade

-   **Personalização de entrada** – Não permite o uso de serviços de voz baseados em nuvem para aplicativos da Microsoft Store, ditado ou Cortana. Se você permitir esses serviços, a Microsoft poderá coletar dados de voz para melhorar o serviço.
-   **Aceitação automática de solicitações de consentimento do usuário para privacidade e emparelhamento** – Permitir que o Windows aceite automaticamente mensagens de consentimento de emparelhamento e privacidade ao executar aplicativos.
- **Publicar as atividades do usuário**: **bloqueie** para evitar experiências compartilhadas e a descoberta de recursos usados recentemente no alternador de tarefas.
- **Apenas atividades locais**: **bloqueie** para evitar experiências compartilhadas e a descoberta de recursos usados recentemente no alternador de tarefas com base somente em atividades locais.

Você pode definir as informações que todos os aplicativos no dispositivo podem acessar. Você pode definir exceções de acordo com o aplicativo que usa **Exceções de privacidade por aplicativo**.

### <a name="exceptions"></a>Exceções

- **Informações de conta** – defina se este aplicativo pode acessar o nome de usuário, imagem e outras informações de contato.
- **Aplicativos em segundo plano** – defina se este aplicativo pode ser executado em segundo plano.
- **Calendário** – defina se este aplicativo pode acessar o calendário.
- **Histórico de chamadas** – defina se este aplicativo pode acessar meu histórico de chamadas.
- **Câmera** – defina se este aplicativo pode acessar a câmera.
- **Contatos** – defina se este aplicativo pode acessar os contatos.
- **Email** – defina se este aplicativo pode acessar e enviar emails.
- **Local** – defina se este aplicativo pode acessar informações de localização.
- **Mensagens** – defina se este aplicativo pode ler ou enviar mensagens de texto ou MMS.
- **Microfone** – defina se este aplicativo pode usar o microfone.
- **Movimento** – defina se este aplicativo pode acessar informações de movimentação do dispositivo.
- **Notificações** – defina se este aplicativo pode acessar as notificações.
- **Telefone** – defina se este aplicativo pode acessar o telefone.
- **Rádios** – alguns aplicativos usam rádios (por exemplo, Bluetooth) em seu dispositivo para enviar e receber dados, e precisam ativar ou desativar essas rádios. Defina se este aplicativo pode controlar essas rádios.
- **Tarefas** – defina se este aplicativo pode acessar suas tarefas.
- **Dispositivos confiáveis** – Defina se este aplicativo poderá usar dispositivos confiáveis (hardware que você já conectou ou que acompanha este PC, tablet ou telefone). Por exemplo: TVs, projetores etc.
- **Comentários e diagnóstico** – Defina se este aplicativo pode acessar informações de diagnóstico.
- **Sincronização com dispositivos** – defina se este aplicativo pode compartilhar e sincronizar automaticamente informações com dispositivos sem fio que não emparelham explicitamente com este computador, tablet ou telefone.

## <a name="per-app-privacy-exceptions"></a>Exceções de privacidade por aplicativo

Você pode adicionar aplicativos que devem ter um comportamento de privacidade diferente do definido em "Privacidade padrão".

- **Nome do Pacote** – nome de família do pacote de aplicativos.
- **Nome do Aplicativo** – o nome do aplicativo.

### <a name="exceptions"></a>Exceções

- **Informações de conta** – defina se este aplicativo pode acessar o nome de usuário, imagem e outras informações de contato.
- **Aplicativos em segundo plano** – defina se este aplicativo pode ser executado em segundo plano.
- **Calendário** – defina se este aplicativo pode acessar o calendário.
- **Histórico de chamadas** – defina se este aplicativo pode acessar meu histórico de chamadas.
- **Câmera** – defina se este aplicativo pode acessar a câmera.
- **Contatos** – defina se este aplicativo pode acessar os contatos.
- **Email** – defina se este aplicativo pode acessar e enviar emails.
- **Local** – defina se este aplicativo pode acessar informações de localização.
- **Mensagens** – defina se este aplicativo pode ler ou enviar mensagens de texto ou MMS.
- **Microfone** – defina se este aplicativo pode usar o microfone.
- **Movimento** – defina se este aplicativo pode acessar informações de movimentação do dispositivo.
- **Notificações** – defina se este aplicativo pode acessar as notificações.
- **Telefone** – defina se este aplicativo pode acessar o telefone.
- **Rádios** – alguns aplicativos usam rádios (por exemplo, Bluetooth) em seu dispositivo para enviar e receber dados, e precisam ativar ou desativar essas rádios. Defina se este aplicativo pode controlar essas rádios.
- **Tarefas** – defina se este aplicativo pode acessar suas tarefas.
- **Dispositivos confiáveis** – defina se este aplicativo pode usar dispositivos confiáveis (hardware que você já conectou ou que acompanha este PC, tablet ou telefone). Por exemplo: TVs, projetores etc.
- **Comentários e diagnóstico** – defina se este aplicativo pode acessar informações de diagnóstico.
- **Sincronização com dispositivos** – defina se este aplicativo pode compartilhar e sincronizar automaticamente informações com dispositivos sem fio que não emparelham explicitamente com este computador, tablet ou telefone.

## <a name="locked-screen-experience"></a>Experiência na tela bloqueada

- **Notificações da central de ações (somente dispositivos móveis)** – Permite que notificações da Central de Ações apareçam na tela de bloqueio do dispositivo (somente Windows 10 Mobile).
- **URL de imagem da tela bloqueada (somente desktop)** – especifique a URL para uma imagem no formato JPEG que será usada como o papel de parede de tela bloqueada do Windows. Os usuários não podem mudar isso.
-   **Tempo limite configurável de tela do usuário (somente em dispositivos móveis)** – Permite que usuários configurem o período 
-   **Cortana na tela bloqueada (somente no desktop)** – Não permitir que o usuário interaja com a Cortana quando o dispositivo estiver na tela de bloqueio (somente Windows 10 desktop).
-   **Notificações do sistema na tela bloqueada** – Impeça que mensagens de alerta sejam exibidas na tela de bloqueio do dispositivo.
-   **Tempo limite da tela (somente dispositivos móveis)** – Especifica o tempo em segundos, depois do bloqueio da tela, em que ela será desligada.

## <a name="app-store"></a>Loja de aplicativos

-   **Loja de aplicativos (somente dispositivo móvel)** – Habilitar ou bloquear o uso da loja de aplicativos em dispositivos Windows 10 Mobile.
-   **Atualizar aplicativos automaticamente da loja** – Permite que os aplicativos instalados da Microsoft Store sejam atualizados automaticamente.
-   **Instalação de aplicativo confiável** - permite que os aplicativos assinados com um certificado de confiança sejam carregados por sideload.
-   **Desbloqueio do desenvolvedor** - permite que configurações de desenvolvedor do Windows, como a permissão de sideload de aplicativos, sejam modificadas pelo usuário final.
-   **Dados de aplicativo do usuário compartilhados** - permite que os aplicativos compartilhem dados entre usuários diferentes no mesmo dispositivo.
-   **Usar somente armazenamento privado** – Habilite para permitir que somente os usuários finais possam baixar aplicativos de seu armazenamento privado.
-   **Inicialização de aplicativo originado na Store** – Usada para desabilitar todos os aplicativos previamente instalados no dispositivo ou baixados da Microsoft Store.
-   **Instalar dados do aplicativo no volume do sistema** - impede que os aplicativos armazenem dados no volume do sistema do dispositivo.
-   **Instalar aplicativos na unidade do sistema** - impede que os aplicativos armazenem dados na unidade do sistema do dispositivo.
-   **DVR de Jogos (somente desktop)** - Define se é permitido registrar e transmitir jogos.
-   **Apenas aplicativos da loja** – define se os usuários podem instalar aplicativos de locais que não sejam a loja de aplicativos.

## <a name="microsoft-edge-browser"></a>Navegador Microsoft Edge

-   **Navegador Microsoft Edge (somente dispositivo móvel)** – Permita o uso do navegador da Web Microsoft Edge no dispositivo.
-   **Barra de endereço suspensa (somente no desktop)** – Impede que o Microsoft Edge exiba uma lista de sugestões em uma lista suspensa enquanto você digita. Essa opção ajuda a minimizar o uso de largura de banda da rede entre o Microsoft Edge e os serviços da Microsoft.
-   **Sincronizar favoritos entre navegadores da Microsoft (somente no desktop)** – Permite que o Windows sincronize os favoritos entre o Internet Explorer e o Microsoft Edge.
-   **Enviar cabeçalhos Do Not Track** – Configura o navegador Microsoft Edge para enviar cabeçalhos Do Not Track para sites visitados pelos usuários.
-   **Cookies** – Permite que o navegador salve cookies da Internet no dispositivo.
-   **JavaScript** – Permite que scripts, como JavaScript, sejam executados no navegador Microsoft Edge.
-   **Pop-ups** - bloqueia janelas pop-up no navegador (aplica-se a somente a desktops com Windows 10).
-   **Sugestões de Pesquisa** – Permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa.
-   **Enviar tráfego da intranet para o Internet Explorer** – permite aos usuários abrir sites de intranet no Internet Explorer (somente para desktops com Windows 10).
-   **Preenchimento automático** – permite que os usuários alterem completamente as configurações de preenchimento automático no navegador (somente para desktop com Windows 10).
-   **Gerenciador de Senhas** – Habilite ou desabilite o recurso do Gerenciador de Senhas do Microsoft Edge.
-   **Local da lista de sites do modo Empresarial** – Especifica onde encontrar a lista de sites que serão abertos no modo Empresarial. Os usuários não podem editar essa lista.<br>(Somente Windows 10 Desktop).
-   **Ferramentas para desenvolvedores** – Impeça que o usuário final abra as ferramentas para desenvolvedores do Microsoft Edge.
-   **Extensões** – Permita ao usuário final instalar extensões do Microsoft Edge no dispositivo.
-   **Navegação inPrivate** - impede que o usuário final abra sessões de navegação InPrivate.
-   **Mostrar página da primeira execução** – Impede que a página de introdução seja exibida na primeira vez que o Microsoft Edge for executado.
    -   **URL da primeira execução** – Especifica a URL da página que é exibida na primeira vez que um usuário executa o Microsoft Edge (somente Windows 10 Mobile).
-   **Páginas iniciais** – Adicione uma lista de sites que deseja usar como as páginas iniciais no navegador Microsoft Edge (somente desktop).
-   **Alterações na página inicial** – Permite que os usuários alterem as páginas iniciais exibidas quando o Microsoft Edge é aberto. Use a configuração Página inicial para criar a página ou uma lista de páginas que é aberta quando o Microsoft Edge é iniciado.
-   **Bloquear acesso aos about:flags** – Impeça que o usuário final acesse a página about:flags no Microsoft Edge, que contém configurações experimentais e de desenvolvedor.
-   **Endereço IP do localhost WebRtc** – Bloqueie a exibição do endereço IP do localhost de usuários ao fazer chamadas telefônicas usando o protocolo RTC da Web.
-   **Mecanismo de pesquisa padrão** - especifica o mecanismo de pesquisa padrão a ser usado. Os usuários finais podem alterar esse valor a qualquer momento.
-   **Limpar dados de navegação ao sair** – Limpa o histórico e os dados de navegação quando o usuário sai do Microsoft Edge.
-   **Coleta de dados de Blocos Dinâmicos** – Impede que o Windows colete informações de Blocos Dinâmicos quando o usuários fixam um site no menu Iniciar do Microsoft Edge.
-  **Lista de favoritos** – define o caminho para o arquivo de favoritos. Por exemplo, http://contoso.com/favorites.html.
-  **Restringir alterações aos Favoritos** - **Bloqueie** para impedir que os usuários adicionem, importem, classifiquem ou editem a lista de Favoritos. 

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **SmartScreen para Microsoft Edge** – habilite o SmartScreen do Microsoft Edge para acessar downloads do site e de arquivos.
- **Acesso a sites mal-intencionados** – impeça os usuários de ignorar os avisos de Filtro do Windows Defender SmartScreen, e impeça-os de visitar o site.
- **Download de arquivo não verificado** – impeça os usuários de ignorar os avisos de Filtro do Windows Defender SmartScreen, e impeça-os de fazer o download de arquivos não verificados.

## <a name="search"></a>Pesquisar
- **Pesquisa segura (somente dispositivos móveis)** - controla como o Cortana filtra o conteúdo adulto nos resultados da pesquisa. Você pode selecionar **Estrito**, **Moderado** ou permitir que o usuário final escolha suas próprias configurações.
- **Exibir resultados da Web na pesquisa** – bloquear ou permitir que os resultados da Web sejam exibidos em pesquisas feitas no dispositivo.

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento
-   **Conta da Microsoft** – Permite que o usuário associe uma conta da Microsoft ao dispositivo.
-   **Conta não Microsoft** – Permite que o usuário adicione contas de email ao dispositivo que não estão associadas a uma conta da Microsoft.
-   **Sincronização de configurações para conta da Microsoft** – Permitir configurações de dispositivo e aplicativos associadas a uma conta da Microsoft para sincronização entre dispositivos.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade

-   **Canal de dados de rede celular** – Impedir que os usuários usem dados, como ao navegar na Web, quando eles estiverem conectados a uma rede de celular. 
-   **Roaming de dados** – Permitir roaming entre redes ao acessar os dados.
-   **VPN em rede celular** – Controla se o dispositivo pode acessar conexões VPN quando conectado a uma rede celular.
-   **Roaming VPN em rede celular** – Controla se o dispositivo pode acessar conexões VPN quando conectado a uma rede celular em roaming.
-   **Bluetooth** – Controla se o usuário pode habilitar e configurar o Bluetooth no dispositivo.
-   **Descoberta de Bluetooth** – Permite que o dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth.
-   **Pré-emparelhamento Bluetooth** – Permite configurar dispositivos Bluetooth específicos emparelhamento automático com um dispositivo host.
-   **Anúncios por Bluetooth** – Permite que o dispositivo receba anúncios via Bluetooth.
-   **Serviço de dispositivos conectados** – Permite optar por permitir o serviço de dispositivos móveis, que habilita a descoberta e a conexão com outros dispositivos Bluetooth.
-   **NFC** – Permite que o usuário habilite e configure recursos de comunicação a curta distância no dispositivo.
-   **Wi-Fi** – Permite que o usuário habilite e configure o Wi-Fi no dispositivo (somente Windows 10 Mobile).
-   **Conectar automaticamente a hotspots Wi-Fi** – Permite que o dispositivo se conecte automaticamente a hotspots Wi-Fi gratuitos e aceite os possíveis termos e condições da conexão automaticamente.
-   **Configuração manual de Wi-Fi** – Controla se o usuário pode configurar suas próprias conexões Wi-Fi ou se pode usar somente as conexões configuradas por um perfil Wi-Fi (somente Windows 10 Mobile).
-   **Intervalo de verificação de Wi-Fi** – Especifique com que frequência os dispositivos procuram redes Wi-Fi. Especifique um valor de 1 (mais frequentes) a 500 (menos frequente).
-   **Serviços Bluetooth permitidos** – Especifique uma lista de serviços e perfis e permitidos de Bluetooth como cadeias de caracteres hexadecimais.

## <a name="control-panel-and-settings"></a>Painel de controle e configurações

-   **Configurações de aplicativo** - bloqueia o acesso ao aplicativo de configurações do Windows.
    -   **Sistema** - bloqueia o acesso à área de sistema do aplicativo de configurações.
        -   **Modificação das configurações de energia e suspensão (somente desktop)** - impede que o usuário final altere as configurações de energia e suspensão no dispositivo.
    -   **Dispositivos** - bloqueia o acesso à área de dispositivos do aplicativo de configurações.
    -   **Rede e Internet** - bloqueia o acesso à área de rede e internet do aplicativo de configurações.
    -   **Personalização** - bloqueia o acesso à área de personalização do aplicativo de configurações.
    -   **Contas** - bloqueia o acesso à área de contas do aplicativo de configurações.
    -   **Hora e Idioma** - bloqueia o acesso à área de hora e idioma do aplicativo de configurações.
        -   **Modificação do horário do sistema** - impede que o usuário final altere a data e hora do dispositivo.
        -   **Modificação das configurações de região (somente desktop)** - impede que o usuário final altere as configurações de região no dispositivo.
        -   **Modificação das configurações de idioma (somente desktop)** - impede que o usuário altere as configurações de idioma no dispositivo.
    -   **Jogos** – bloqueia o acesso para o aplicativo Jogos nas Configurações.
    -   **Facilidade de Acesso** - bloqueia o acesso à área de facilidade de acesso do aplicativo de configurações.
    -   **Privacidade** - bloqueia o acesso à área de privacidade do aplicativo de configurações.
    -   **Atualização e Segurança** – bloqueia o acesso à área de atualizações e segurança do aplicativo de configurações.

## <a name="start"></a>Inicie o

- **Layout do menu Iniciar** – Para personalizar o menu Iniciar nos dispositivos da área de trabalho, você pode fazer upload de um arquivo XML que inclui suas personalizações, incluindo a ordem em que os aplicativos estão listados e muito mais. Os usuários não poderão alterar o layout do menu Iniciar que você inserir.
- **Fixar sites nos blocos do menu Iniciar** – Importe imagens do Microsoft Edge exibidas como links no menu Iniciar do Windows para dispositivos da área de trabalho.
- **Desafixar aplicativos da barra de tarefas** – Selecione **Bloquear** para impedir o usuário de desafixar aplicativos no menu Iniciar.
- **Troca rápida de usuário** – Selecione **Bloquear** para impedir a troca entre os usuários que estão conectados simultaneamente sem fazer logoff.
- **Aplicativos mais usados** – Selecione **Bloquear** para ocultar os aplicativos mais usados no menu Iniciar. Isso também desabilita a alternância correspondente no aplicativo Configurações.
- **Aplicativos adicionados recentemente** – Selecione **Bloquear** para ocultar os aplicativos adicionados recentemente no menu Iniciar. Isso também desabilita a alternância correspondente no aplicativo Configurações.
- **Iniciar modo de tela** – Escolha como tela inicial é exibida. Escolha exibi-la como **Tela inteira** ou **Tela não inteira**.
- **Itens abertos recentemente nas Listas de Atalhos** – Selecione **Bloquear** para ocultar as listas de atalhos recentes no menu Iniciar e na barra de tarefas. Isso também desabilita a alternância correspondente no aplicativo Configurações.
- **Lista de aplicativos** – Escolha como o aplicativo Configurações é exibido. Suas opções: 
  - Recolher
  - Recolher e desabilitar o aplicativo Configurações 
  - Remove e desabilita o aplicativo Configurações
- **Botão de energia** – Selecione **Bloquear** para ocultar o botão de energia no menu Iniciar.
- **Bloco do Usuário** – Selecione **Bloquear** para ocultar o bloco do usuário no menu Iniciar.
  - **Bloquear** – Selecione **Bloquear** para ocultar a opção `Lock` no bloco de usuário no menu Iniciar.
  - **Sair** – Selecione **Bloquear** para ocultar a opção `Sign out` no bloco do usuário no menu Iniciar.
- **Desligar** – Selecione **Bloquear** para ocultar as opções `Update and shut down` e `Shut down` no botão de energia no menu Iniciar.
- **Suspender** – Selecione **Bloquear** para ocultar a opção `Sleep` no botão de energia no menu Iniciar.
- **Hibernar** – Selecione **Bloquear** para ocultar a opção `Hibernate` no botão de energia no menu Iniciar.
- **Trocar Conta** – Selecione **Bloquear** para ocultar `Switch account` no bloco do usuário no menu Iniciar.
- **Opções de Reinicialização** – Selecione **Bloquear** para ocultar as opções `Update and restart` e `Restart` no botão de energia no menu Iniciar.
- **Documentos em Iniciar** - oculta ou mostra a pasta Documentos no menu Iniciar do Windows.
- **Downloads em Iniciar** - oculta ou mostra a pasta Downloads no menu Iniciar do Windows.
- **Explorador de Arquivos em Iniciar** - oculta ou mostra o aplicativo Explorador de Arquivos no menu Iniciar do Windows.
- **Grupo Doméstico em Iniciar** - oculta ou mostra a pasta Grupo Doméstico no menu Iniciar do Windows.
- **Música em Iniciar** - oculta ou mostra a pasta Música no menu Iniciar do Windows.
- **Rede em Iniciar** - oculta ou mostra a pasta Rede no menu Iniciar do Windows.
- **Pasta Pessoal em Iniciar** - oculta ou mostra a pasta Pessoal no menu Iniciar do Windows.
- **Imagens em Iniciar** - oculta ou mostra a pasta de imagens no menu Iniciar do Windows.
- **Configurações em Iniciar** - oculta ou mostra o aplicativo Configurações no menu Iniciar do Windows.
- **Vídeos em Iniciar** - oculta ou mostra a pasta de vídeos no menu Iniciar do Windows.

## <a name="display"></a>Vídeo

- **Ligar o ajuste de GDI para aplicativos**
- **Desligar o ajuste de GDI para aplicativos**

  O Ajuste de DPI do GDI permite que aplicativos sem reconhecimento de DPI fiquem com reconhecimento de DPI por monitor. especifica os aplicativos herdados que têm o Ajuste de DPI do GDI ativado. Com o Ajuste de DPI do GDI configurado para ser ativado e desativado em um aplicativo, o ajuste é desativado para o aplicativo.

## <a name="kiosk-preview---obsolete"></a>Quiosque (versão prévia) – obsoleto

Essas configurações são somente leitura e não podem ser alteradas. Para configurar o modo de quiosque, confira [Configurações de quiosque no Windows 10 e posterior](kiosk-settings.md).

Um dispositivo de quiosque geralmente executa um aplicativo ou um conjunto específico de aplicativos. Os usuários são impedidos de acessar quaisquer recursos ou funções no dispositivo fora de qualquer aplicativo de quiosque.

- **Modo de quiosque** – identifica o tipo de modo de quiosque compatível com a política. As opções incluem:

  - **Não configurado** (padrão) – A política não habilita um modo de quiosque. 
  - **Quiosque de aplicativo único** – o perfil habilita o dispositivo a executar somente um aplicativo. Quando o usuário faz logon, um aplicativo específico inicia. Esse modo também impede que o usuário abrir novos aplicativos ou alterar o aplicativo em execução.
  - **Quiosque de vários aplicativos** – o perfil permite que o dispositivo execute vários aplicativos. Somente os aplicativos que você adicionar estão disponíveis ao usuário. O benefício de um quiosque de vários aplicativos ou de um dispositivo com finalidade fixa é proporcionar uma experiência fácil para as pessoas entenderem apenas acessando os aplicativos de que precisam e removendo da exibição os aplicativos desnecessários.

#### <a name="single-app-kiosks"></a>Quiosques de aplicativo único
Insira as seguintes configurações:

- **Conta de usuário** – Insira a conta de usuário local (do dispositivo), uma conta de domínio do AD ou uma conta do Azure AD associada ao aplicativo de quiosque.
  - Conta local: insira como `devicename\accountname`, `.\accountname` ou `accountname`
  - Conta de domínio: insira como `domain\accountname`
  - Conta do Azure AD: insira como `AzureAD\emailaddress`. Insira "AzureAD", porque ele é um nome de domínio fixo. Em seguida, siga com o endereço de email do Azure AD. Por exemplo, insira `AzureAD\user@contoso.onmicrosoft.com`.

    Para quiosques em ambientes de público com logon automático habilitado, um tipo de usuário com o privilégio mínimo (como a conta de usuário padrão local) deve ser usado. Se estiver usando uma conta do Azure AD para o modo de quiosque, não se esqueça de inserir `AzureAD\user@yourorganization.com`.

- **AUMID (ID do modelo de usuário do aplicativo)** – insira a AUMID do aplicativo de quiosque. Para saber mais, consulte [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (Encontrar a ID do modelo de usuário do aplicativo de um aplicativo instalado).

#### <a name="multi-app-kiosks"></a>Quiosques de vários aplicativos
[Quiosques de vários aplicativos](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) usam uma configuração de quiosque que lista os aplicativos permitidos e outras configurações. 

Use o botão **Adicionar** para criar uma configuração de quiosque (ou selecionar uma configuração existente). Então, insira as seguintes configurações:

- **Nome da configuração de quiosque** – insira um nome amigável usado para identificar a configuração.

- **Aplicativos de quiosque** – insira os aplicativos disponíveis no menu Iniciar. Os aplicativos que você adicionar são os únicos aplicativos que o usuário pode abrir.

  - **Tipo de aplicativo** – escolha o tipo de aplicativo de quiosque:
    - **Aplicativo Win32** – Um aplicativo da área de trabalho tradicional. Você precisa do nome do caminho totalmente qualificado do executável com relação ao dispositivo.
    - **Aplicativo UWP** – Um aplicativo universal do Windows. Você precisa do [AUMID do aplicativo](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

  - **Identificador** – insira o nome do caminho totalmente qualificado do arquivo executável (aplicativos Win32) ou a [AUMID do aplicativo](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (aplicativos UWP).

- **Barra de tarefas**: escolha **Habilitar** (mostrar) na barra de tarefas ou mantenha-a como **Não configurada** (oculta) no quiosque.

- **Layout do menu Iniciar** – insira um arquivo XML que descreva como os aplicativos aparecem no menu Iniciar. [Personalizar e exportar o layout inicial](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) fornece algumas diretrizes e XML de exemplo.


  [Criar um quiosque Windows 10 que executa vários aplicativos](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) fornece mais detalhes sobre como usar e criar arquivos XML.

- **Usuários atribuídos** – adicione uma ou mais contas de usuário que podem usar os aplicativos que você adicionar. Quando a conta se conecta, apenas os aplicativos definidos na configuração estão disponíveis. A conta pode ser local para o dispositivo ou para uma conta do Azure AD associada ao aplicativo de quiosque.

    Para quiosques em ambientes de público com logon automático habilitado, um tipo de usuário com o privilégio mínimo (como a conta de usuário padrão local) deve ser usado. Para configurar uma conta do Azure AD (Active Directory) para o modo de quiosque, use o formato `domain\user@tenant.com`.

## <a name="windows-defender-antivirus"></a>Windows Defender Antivírus

-   **Monitoramento em tempo real** – Habilita a verificação em tempo real de malware, de spyware e de outros tipos de software indesejados.
-   **Monitoramento de comportamento** – Permite que o Defender verifique se há certos padrões de atividade suspeita nos dispositivos.
-   **NIS (Sistema de Inspeção de Rede)** – O NIS ajuda a proteger dispositivos contra explorações baseadas em rede. Ele utiliza assinaturas de vulnerabilidades conhecidas do Microsoft Endpoint Protection Center para ajudar a detectar e bloquear o tráfego mal-intencionado.
-   **Examinar todos os downloads** – Controla se o Defender examina todos os arquivos baixados da Internet.
-   **Examinar scripts carregados nos navegadores da Web da Microsoft** – Permite que o Defender verifique os scripts que são usados no Internet Explorer.
-   **Acesso do usuário final ao Defender** – Controla se a interface do usuário do Windows Defender está oculta para usuários finais.
Quando alterada, esta configuração entra em vigor na próxima vez em que o computador do usuário final for reiniciado.
-   **Intervalo de atualização de assinatura (em horas)** – Especifique o intervalo no qual o Defender verificará novos arquivos de assinatura.
-   **Monitorar a atividade de arquivos e programas** – Permite que o Defender monitore a atividade de arquivos e programas nos dispositivos.
-   **Dias de espera antes de excluir malware em quarentena** – Permite que o Defender continue a rastrear o malware resolvido pelo número de dias que especificado para que você possa examinar manualmente os dispositivos infectados anteriormente. Se você definir o número de dias para **0**, o malware permanecerá na pasta de Quarentena e não será removido automaticamente.
-   **Limite de uso de CPU durante uma verificação** – Permite limitar a quantidade de CPU que as verificações têm permissão para usar (de **1** a **100**).
-   **Verificar arquivos mortos** – Permite que o Defender examine arquivos mortos, como os arquivos Zip ou Cab.
-   **Examinar mensagens de email de entrada** – Permite que o Defender examine mensagens de email assim que elas chegarem ao dispositivo.
-   **Examinar unidades removíveis durante uma verificação completa** – Permite que o Defender examine unidades removíveis como pen drives.
-   **Examinar unidades de rede mapeadas durante uma verificação completa** – Permite que o Defender examine arquivos em unidades de rede mapeadas.<br>Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.
-   **Verificar arquivos abertos de pastas de rede** – Permite que o Defender verifique arquivos em unidades de rede compartilhadas (por exemplo, arquivos acessados de um caminho UNC).
Se os arquivos na unidade forem somente leitura, o Defender não poderá o remover nenhum malware encontrado neles.
-   **Proteção de nuvem** – Permite ou bloqueia o Microsoft Active Protection Service de receber informações sobre a atividade de malware de dispositivos gerenciados. Essas informações são usadas para aprimorar o serviço futuramente.
-   **Perguntar aos usuários antes de enviar amostras** – Controla se os arquivos potencialmente mal-intencionados que podem exigir mais análise são enviados automaticamente para a Microsoft.
-   **Hora para realizar uma verificação rápida diária** – Permite agendar uma verificação rápida que ocorre diariamente na hora que você selecionar.
-   **Tipo de verificação do sistema a ser executada** – Permite que você especifique o nível de verificação executado ao agendar uma verificação do sistema.
-   **Detectar aplicativos potencialmente indesejados** – Escolha o nível de proteção quando o Windows detecta aplicativos potencialmente indesejados:
        - **Bloquear**
        - **Auditoria** Para obter mais informações sobre aplicativos potencialmente indesejados, consulte [este tópico](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
-   **Ações contra ameaças de malware detectadas** – Habilite esta opção para especificar as ações que o Defender deve realizar para cada nível de ameaça detectada (Baixa, Moderada, Alta e Grave). As ações que podem ser executadas são:
    -   **Apagar**
    -   **Quarentena**
    -   **Removerr**
    -   **Permitir**
    -   **Definido pelo usuário**
    -   **Bloquear**

### <a name="windows-defender-antivirus-exclusions"></a>Exclusões do Windows Defender Antivírus

-   **Arquivos e pastas a serem excluídas da verificação e proteção em tempo real** – Adiciona um ou mais arquivos e pastas como **C:\Path** ou **%ProgramFiles%\Path\filename.exe** à lista de exclusões. Esses arquivos e pastas não serão incluídos em verificações em tempo real ou programadas.
-   **Extensões de arquivos a serem excluídas de verificações e proteção em tempo real** – Adicione uma ou mais extensões de arquivo como **jpg** ou **txt** à lista de exclusões. Qualquer arquivo com essas extensões não serão incluídos em verificações em tempo real ou programadas.
-   **Processos a serem excluídos de verificações e proteção em tempo real** – Adicionar um ou mais processos do tipo **.exe**, **.com** ou **.scr** à lista de exclusões. Esses processos não serão incluídos em verificações em tempo real ou programadas.

## <a name="network-proxy"></a>Proxy de rede

-   **Detectar automaticamente as configurações de proxy** – Quando habilitado, o dispositivo tenta localizar o caminho até um script PAC.
-   **Usar script de proxy** – Selecione esta opção para inserir um caminho até um script PAC para configurar o servidor proxy.
    -   **Configurar URL de endereço do script** - insira a URL de um script PAC que você deseja usar para configurar o servidor proxy.
-   **Usar servidor proxy manual** – Selecione esta opção para inserir manualmente as informações do servidor proxy.
    -   **Endereço** - insira o nome ou o endereço IP do servidor proxy.
    -   **Número da porta** – insira o número de porta de seu servidor proxy.
    -   **Exceções de proxy** - insira todas as URLs que não devem usar o servidor proxy. Use um ponto e vírgula para separar cada item.
    -   **Ignorar servidor proxy para endereços locais** – habilite esta opção se você não quiser usar o servidor proxy para endereços locais na intranet.

## <a name="windows-spotlight"></a>Destaque do Windows

- **Destaque do Windows** – Use essa configuração para bloquear todas as funcionalidades de Destaque do Windows em dispositivos Windows 10. Se você bloquear essa configuração, as configurações a seguir não estarão disponíveis.
    - **Destaque do Windows na tela de bloqueio** – Impedir que o Destaque do Windows exiba informações na tela de bloqueio do dispositivo.
    - **Sugestões de terceiros no Destaque do Windows** – Impedir que o Destaque do Windows sugira conteúdo não publicado pela Microsoft.
    - **Recursos de Consumidor** - permite o bloqueio de recursos do consumidor, como sugestões do menu Iniciar e notificações de associação.
    - **Dicas do Windows** - permite o bloqueio de exibição de dicas pop-up no Windows.
    - **Destaque do Windows na Central de Ações** – Impedir que as sugestões de Destaque do Windows como um novo aplicativo ou conteúdo de segurança apareça no Windows Action Center.
    - **Personalização do Windows Spotlight** – Impede que o Destaque do Windows personalize os resultados com base no uso de um dispositivo.
    - **Experiência de boas-vindas do Windows** – Bloqueia a experiência de boas-vinda do Windows, que mostra as informações do usuário sobre os recursos atualizados ou atualizados.

## <a name="projection"></a>Projeção

- **Entrada do usuário de receptores de vídeo sem fio** - bloqueia a entrada do usuário de receptores de vídeo sem fio.
- **Projeção neste PC** - impede que outros dispositivos descubram o PC para projeção.
- **Exigir PIN para emparelhamento** - exige um PIN durante a conexão com um dispositivo de projeção.

## <a name="cloud-printer"></a>Impressora de Nuvem

- **URL de descoberta da impressora** – Insira a URL para encontrar impressoras de nuvem.
- **URL de autoridade de acesso da impressora** – Insira a URL de ponto de extremidade para adquirir tokens OAuth. Por exemplo, insira algo como `https://login.microsoftonline.com/your Azure AD Tenant ID`.
- **GUID de aplicativo cliente nativo do Azure** – Insira o GUID de um aplicativo cliente autorizado para obter tokens OAuth do OAuthAuthority.
- **URI de recurso de serviço de impressão** – Insira o URI de recurso OAuth do serviço de impressão configurado no portal do Azure. Por exemplo, insira algo como `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Máximo de impressoras para consulta (Somente dispositivo móvel)** – Insira o número máximo de impressoras a serem consultadas. Por exemplo, insira `10`.
- **URI de recurso de serviço de descoberta de impressora** – Insira o URI de recurso do OAuth para serviço de descoberta de impressora configurado no portal do Azure. Por exemplo, insira algo como `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Depois de instalar uma [Impressão de Nuvem Híbrida do Windows Server](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview), você poderá definir essas configurações e, em seguida, implantar em dispositivos do Windows.

## <a name="local-printer"></a>Impressora local
- **Impressoras** – Lista de impressoras locais que foram adicionadas.
- **Impressora padrão** – Defina a impressora padrão.
- **Acesso de usuário à adição de novas impressoras** – Permita ou bloqueie o uso de impressoras locais.

## <a name="reporting-and-telemetry"></a>Relatório e telemetria

- **Compartilhar dados de uso** – selecione o nível de envio de dados de diagnóstico.
- **Servidor de proxy de telemetria**

  Especifique o FQDN (Nome de domínio totalmente qualificado) ou o endereço IP de um servidor proxy para encaminhar solicitações de Experiências do Usuário Conectado e Telemetria usando uma conexão SSL (Secure Sockets Layer). O formato para essa configuração é *servidor*:*porta*. Se o proxy nomeado falhar, ou se não houver um proxy especificado na habilitação dessa política, os dados de Experiências do Usuário Conectado e Telemetria não serão transmitidos e permanecerão no dispositivo local.

   Formatos de exemplo:

   IPv4: 192.246.246.106:100<br>
 IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100<br> FQDN: www.contoso.com:345

## <a name="messaging"></a>Sistema de mensagens

- **Sincronização de mensagem (somente dispositivo móvel)** – Desabilite Mensagens em qualquer lugar e backup e restauração de mensagem de texto.
- **MMS (somente móvel)** – desabilite a funcionalidade de envio/recebimento de MMS no dispositivo.
- **RCS (somente móvel)** – desabilite a funcionalidade de envio/recebimento dos Serviços de Comunicação no dispositivo.

## <a name="more-information"></a>Mais Informações
Confira os detalhes técnicos adicionais sobre cada configuração e quais edições do Windows são compatíveis em [Referência do CSP de Política do Windows 10](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-configuration-service-provider)
