---
title: "Configurações de restrições de dispositivo do Intune para iOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações e as funcionalidades do dispositivo em dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73590192-54ca-4833-9f1d-83e1b654399f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eec078fa0ddc0414b2912e3df841841d96b2e79e
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2017
---
# <a name="ios-device-restriction-settings-in-microsoft-intune"></a>Configurações de restrição de dispositivo iOS no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Geral
    
-   **Envio de dados de diagnóstico** – Permitir ou bloquear a habilidade do dispositivo enviar dados de diagnóstico para a Apple.
-   **Captura de tela** – Permitir ao usuário capturar os conteúdos da tela como uma imagem.
    - **Observação de tela remota pelo aplicativo Classroom (somente supervisionado)** – Permitir ou bloquear que o aplicativo Classroom da Apple exiba a tela de dispositivos iOS.
    - **Observação de tela não solicitada pelo aplicativo Classroom (somente supervisionado)** – se permitido, os professores podem observar silenciosamente a tela dos dispositivos iOS dos alunos usando o aplicativo Classroom sem o conhecimento dos alunos.
-   **Certificados TLS não confiáveis** – Permitir certificados do protocolo TLS não confiáveis no dispositivo.
-   **Aplicativos de confiança da empresa** – Permitir que o usuário opte por confiar em aplicativos que não foram baixados da loja de aplicativos.
- **Modificação de conta (somente com supervisão)** - Quando é bloqueada, impede que o usuário modifique as configurações específicas do dispositivo no aplicativo de configurações do iOS, como a criação de novas contas de dispositivo e alteração do nome de usuário ou senha.
Isso também se aplica às configurações acessadas no aplicativo de configurações do iOS, como Mail, Contatos, Calendário, Facebook e Twitter. Isso não se aplica a aplicativos com configurações de conta que não podem ser definidas no aplicativo de configurações do iOS, por exemplo, o aplicativo Microsoft Outlook.
- **Habilitar restrições nas configurações do dispositivo (somente supervisionado)** – Permitir que o usuário configure restrições de dispositivo (controles dos pais) no dispositivo.
- **Usar o apagamento total do conteúdo e das opções de configurações no dispositivo (somente supervisionado)** – Permitir que o usuário utilize a opção de apagar todo o conteúdo e as configurações no dispositivo.
- **Modificação do nome de dispositivo (somente supervisionado)** – Permitir que o usuário altere o nome do dispositivo.
- **Modificação das configurações de notificação (somente supervisionado)** – Permitir que o usuário altere as configurações de notificação do dispositivo.
- **Modificação do papel de parede (somente supervisionado)** – Permitir que o usuário altere o papel de parede do dispositivo.
- **Modificação das configurações de aplicativo de confiança da empresa** – Permitir que o usuário opte por confiar em aplicativos que não foram baixados da loja de aplicativos.
- **Alterações de perfil de configuração** – Permitir que o usuário instale perfis de configuração.
- **Bloqueio de Ativação (somente supervisionado)** – Habilitar o Bloqueio de Ativação em dispositivos iOS supervisionados.

## <a name="password"></a>Senha
-   **Senha** – Exige que o usuário final insira uma senha para acessar o dispositivo.
    -   **Senhas simples** – Permitir senhas simples como 0000 e 1234.
    -   **Tipo de senha exigida** – Especificar o tipo de senha necessária, como apenas numérica ou alfanumérica.
    -   **Número de caracteres não alfanuméricos na senha** – Especifique o número de caracteres de símbolo (como **#** ou **@**) que devem ser incluídos na senha.
    -   **Tamanho mínimo de senha** – Especificar o número mínimo de caracteres na senha.
    -   **Número de falhas de entrada antes de apagar o dispositivo** – Especificar o número de tentativas de logon antes de essa configuração apagar o dispositivo.
    -   **Máximo de minutos após o bloqueio de tela antes da senha ser necessária**<sup>1</sup> – Especifique quanto tempo o dispositivo pode permanecer ocioso antes que o usuário precise digitar novamente sua senha.
    -   **Máximo de minutos de inatividade até o bloqueio de tela**<sup>1</sup> – Especifique o número de minutos antes que a tela do dispositivo seja desativada.
    -   **Expiração da senha (dias)** – Especifique o número de dias antes que a senha do dispositivo precise ser alterada.
    -   **Impedir a reutilização de senhas anteriores** – Especifique o número de senhas usadas anteriormente que o dispositivo lembra.
    -   **Desbloqueio por impressão digital** – Permite usar uma impressão digital para desbloquear dispositivos compatíveis.
- **Modificação da senha (somente supervisionada)** – Impede que a senha seja alterada, adicionada ou removida. 
    - **Modificação de impressão digital (somente supervisionada)** – Impede que o usuário altere, adicione ou remova configurações de TouchID.

<sup>1</sup>Quando você configura as definições **Máximo de minutos inatividade até o bloqueio de tela** e **Máximo de minutos após o bloqueio de tela antes da senha ser necessária**, eles são aplicados em sequência. Por exemplo, se você define o valor de ambas as configurações para **5** minutos, a tela desliga automaticamente após 5 minutos e o dispositivo é bloqueado após outros 5 minutos. No entanto, se o usuário desliga a tela manualmente, a segunda configuração é aplicada imediatamente. No mesmo exemplo, o dispositivo é bloqueado 5 minutos depois de o usuário desligar a tela.

## <a name="locked-screen-experience"></a>Experiência de tela bloqueada

-   **Controlar acesso à central quando o dispositivo está bloqueado** – Permitir ao usuário acessar o aplicativo de Central de Controle quando o dispositivo estiver bloqueado.
-   **Notificações enquanto o dispositivo está bloqueado** – Permitir ao usuário acessar a exibição de notificações sem desbloquear o dispositivo.
-   **Passbook enquanto o dispositivo está bloqueado** – Permitir ao usuário acessar o aplicativo Passbook enquanto o dispositivo estiver bloqueado.
-   **Exibição Hoje enquanto o dispositivo está bloqueado** – Permitir que o usuário veja o a exibição Hoje quando o dispositivo estiver bloqueado.

## <a name="app-store-doc-viewing-gaming"></a>Loja de Aplicativos, Exibição de Documentos, Jogos


-   **Loja de aplicativos** – Bloquear o acesso à loja de aplicativos em dispositivos supervisionados.
    - **Instalar aplicativos da App Store (apenas no modo supervisionado)** – Bloqueia a loja de aplicativos da tela inicial do dispositivo. Os usuários finais podem continuar a usar o iTunes ou o Apple Configurator para instalar aplicativos.
    - **Downloads de aplicativo automáticos (somente supervisionados)** – Impede que os aplicativos que foram comprados em outro dispositivo iOS sejam baixados nesse dispositivo.
-   **Senha para acessar a loja de aplicativos** – Exigir que o usuário insira uma senha antes de visitar a loja de aplicativos.
-   **Compras no aplicativo** – Permitir que compras da loja sejam feitas de um aplicativo em execução.
-   **Conteúdo explícito de música, podcast ou notícias do iTunes (somente supervisionado)** – Permitir que o dispositivo acesse conteúdo classificado como adulto na loja.
-   **Baixar o conteúdo do iBook Store marcado como “Erótico”** – Permitir que o usuário baixe livros da categoria “Erótico”.
-   **Exibir documentos corporativos em aplicativos não gerenciados** – Permitir que documentos corporativos sejam exibidos em qualquer aplicativo.<br>**Exemplo:** você deseja impedir que os usuários salvem arquivos do aplicativo OneDrive no Dropbox. Defina essa configuração como não. Depois que o dispositivo receber a política (por exemplo, após uma reinicialização), ele não permitirá mais salvar.
-   **Exibir documentos não corporativos em aplicativos corporativos** – Permitir que qualquer documento seja exibido nos aplicativos corporativos gerenciados.
-   **Tratar o AirDrop como um destino não gerenciado** – Impede que aplicativos gerenciados possam enviar dados por meio dele. Airdrop.
-   **Adicionar amigos no Game Center (somente supervisionado)** – Permitir que o usuário adicione amigos no Game Center.
-   **Game Center (somente supervisionado)** – Bloquear ou habilitar o uso do aplicativo Game Center.
-   **Jogos multijogador (somente supervisionado)** – Permitir que o usuário execute jogos com vários participantes no dispositivo.
-   **Região das classificações** – Escolha a região de classificações para o qual você deseja configurar os downloads permitidos, e escolha as classificações permitidas para **Filmes** e **Programas de TV**.
-   **Aplicativos** – Escolha a classificação de idade dos aplicativos que os usuários poderão baixar, ou então escolha **Permitir todos os aplicativos**.

## <a name="built-in-apps"></a>Aplicativos internos

-   **Câmera** – Especifica se a câmera no dispositivo pode ser usada. 
    -   **FaceTime** – Permitir que o aplicativo FaceTime seja usado no dispositivo.
-   **Siri** – Permitir o uso da assistente de voz Siri no dispositivo.
    -   **Siri quando o dispositivo estiver bloqueado** – Permitir o uso da Assistente de voz Siri no dispositivo enquanto ele estiver bloqueado.
    -   **Filtro de profanação da Siri (somente supervisionado)** – Impede que a Siri dite ou use linguagem ofensiva.
    -   **Siri deve consultar o conteúdo gerado pelo usuário da Internet (somente supervisionado)** – Permitir que Siri acesse sites da Web para responder a perguntas.
- **Apple News (somente supervisionado)** – Permitir o uso do aplicativo Apple News.
- **iBooks Store (somente supervisionado)** – Permitir que o usuário procure e compre livros da iBooks Store.
- **Aplicativo de mensagens no dispositivo (somente supervisionado)** – Permite usar o aplicativo de Mensagens para enviar e ler mensagens de texto.
- **Podcasts (somente supervisionado)** – Permitir o uso do aplicativo Podcasts.
- **Serviço de Música (somente supervisionado)** – Permitir o uso do aplicativo Apple Music.
- **Serviço do iTunes Radio (somente supervisionado)** – Permitir o uso do aplicativo iTunes Radio.
- **Alterações nas configurações de aplicativo de Find My Friends (somente supervisionados)** – Permitir que o usuário altere as configurações para o aplicativo Find My Friends.
- **Pesquisa de destaque retorna resultados da internet (somente supervisionado)** – Permitir que a pesquisa de Destaque se conecte à Internet para fornecer mais resultados.

## <a name="restricted-apps"></a>Aplicativos restritos

Na lista de aplicativos restritos, você pode configurar uma das seguintes listas:

Uma lista de **Aplicativos proibidos** – Listar os aplicativos (não gerenciados pelo Intune) que os usuários não têm permissão para instalar e executar.
Uma lista de **Aplicativos aprovados** – Listar os aplicativos que os usuários têm permissão para instalar. Para permanecer compatível, os usuários não devem instalar aplicativos que não estão listados. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.

Para configurar a lista, clique em **Adicionar**, especifique um nome de sua preferência, o editor do aplicativo (opcional) e a URL para o aplicativo na loja de aplicativos.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Como especificar a URL de um aplicativo na loja

Para especificar uma URL de aplicativo na lista de aplicativos, use o seguinte formato:

Usando um mecanismo de pesquisa, encontre o aplicativo que você deseja usar na iTunes App Store e abra a página do aplicativo.
Copie a URL da página e use-a como a URL para configurar a lista de aplicativos permitidos ou proibidos ou o aplicativo que você deseja executar no modo de quiosque.
Os perfis de dispositivo que contêm configurações de aplicativo restrito devem ser atribuídos para grupos de usuários.

Exemplo: pesquisar por Microsoft Word para iPad. A URL que você usará será https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Você também pode usar o software iTunes para encontrar o aplicativo e usar o comando **Copiar Link** para obter a URL do aplicativo.



### <a name="additional-options"></a>Opções adicionais

Você também pode clicar em **Importar** para popular a lista de um arquivo csv no formato <*url do aplicativo*>, <*nome do aplicativo*>, <*editor do aplicativo*>, ou clique em **Exportar** para criar um arquivo csv que inclui o conteúdo da lista de aplicativos restritos no mesmo formato.

## <a name="show-or-hide-apps-supervised-only"></a>Mostrar ou ocultar aplicativos (somente supervisionado)

Na lista de aplicativos Mostrar ou ocultar, você pode configurar uma destas listas (requer dispositivos supervisionados com iOS 9.3 ou posterior).

Uma lista de **Aplicativos ocultos** – Especifique uma lista de aplicativos que serão ocultados dos usuários. Os usuários não podem exibir nem iniciar esses aplicativos.
Uma lista de **Aplicativos visíveis** – Especifique uma lista de aplicativos que os usuários podem exibir e iniciar. Nenhum outro aplicativo pode ser exibido ou iniciado.

Para configurar a lista, clique em **Adicionar**, especifique um nome de sua preferência, o editor do aplicativo (opcional) e a URL para o aplicativo na loja de aplicativos.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Como especificar a URL de um aplicativo na loja

Para especificar uma URL de aplicativo na lista de aplicativos, use o seguinte formato:

Usando um mecanismo de pesquisa, encontre o aplicativo que você deseja usar na iTunes App Store e abra a página do aplicativo.
Copie a URL da página e use-a como a URL para configurar a lista de aplicativos permitidos ou proibidos ou o aplicativo que você deseja executar no modo de quiosque.

Exemplo: pesquisar por Microsoft Word para iPad. A URL que você usará será https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Você também pode usar o software iTunes para encontrar o aplicativo e usar o comando **Copiar Link** para obter a URL do aplicativo.

### <a name="additional-options"></a>Opções adicionais

Você também pode clicar em **Importar** para popular a lista de um arquivo csv no formato <*url do aplicativo*>, <*nome do aplicativo*>, <*editor do aplicativo*>, ou clique em **Exportar** para criar um arquivo csv que inclui o conteúdo da lista de aplicativos ocultos e visíveis no mesmo formato.


## <a name="wireless"></a>Sem fio
-   **Roaming de dados** – Permitir roaming de dados quando o dispositivo estiver em uma rede de celular.
-   **Obtenção de tela de fundo global durante o roaming** – Permite ao dispositivo buscar dados, como emails, durante roaming na rede celular.
-   **Discagem por voz** – Permitir o uso do recurso de discagem por voz no dispositivo.
-   **Roaming de voz** – Permitir roaming de voz quando o dispositivo estiver em uma rede de celular.
-   **Alterações nas configurações de uso de dados de celular da rede celular do aplicativo (somente supervisionado)** – Permite ao usuário controlar quais aplicativos podem usar dados da rede celular.
-   **Ponto de acesso pessoal** – não permitir que o dispositivo seja usado como um ponto de acesso pessoal. Essa configuração pode não ser compatíveis com algumas operadoras.
-   **Ingressar em redes Wi-Fi usando apenas perfis de configuração (apenas supervisionado)** – Permitir apenas que o dispositivo ingresse em redes Wi-Fi que foram configuradas com um perfil de Wi-Fi do Intune.

- **Regras de uso de celular (somente aplicativos gerenciados)** – permite que você defina os tipos de dados que os aplicativos gerenciados podem usar quando estão em redes celulares. Escolha:
    - **Bloquear uso de dados da rede celular**
    - **Bloquear o uso de dados da rede celular quando em roaming**

## <a name="connected-devices"></a>Dispositivos conectados

-   **AirDrop (somente supervisionado)** – Permitir o uso do recurso AirDrop para trocar conteúdo com dispositivos próximos.
-   **Emparelhamento de Apple Watch (somente supervisionado)** – Permite que o dispositivo seja emparelhado com um Apple Watch.
-   **Detecção de pulso para Apple Watch emparelhado** – Quando habilitada, o Apple Watch não exibirá notificações quando não estiver sendo usado.
-   **Modificação de Bluetooth (somente supervisionado)** – Impede o usuário final de alterar as configurações de Bluetooth no dispositivo.
-   **Emparelhamento de host para controlar os dispositivos aos quais um dispositivo iOS pode ser emparelhado (somente supervisionado)** – Permitir emparelhamento de host para que o administrador controle com quais dispositivos um dispositivo iOS pode ser emparelhado.
-   **Exigir uma senha de emparelhamento de solicitações de saída do AirPlay** – Exigir uma senha emparelhamento quando o usuário usar AirPlay para transmitir o conteúdo para outros dispositivos da Apple.

## <a name="keyboard-and-dictionary"></a>Teclado e dicionário

-   **Pesquisa por definição de palavra (somente supervisionado)** – Permitir o recurso do iOS que permite realçar uma palavra e pesquisar sua definição.
-   **Teclados preditivos (somente supervisionado)** – Permitir o uso de teclados preditivos que sugerem palavras que o usuário pode querer.
-   **Correção automática (somente supervisionado)** – Permite que o dispositivo corrija automaticamente palavras incorretas.
-   **Verificação ortográfica do teclado (somente supervisionada)**  – Permite usar o verificador de ortografia do dispositivo.
-   **Atalhos de teclado (somente supervisionado)** – Permite o uso de atalhos de teclado.
-   **Ditado (somente supervisionado)** – Impede que o usuário use entrada de voz para inserir texto.

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento
-   **Backup para iCloud** – Permitir ao usuário fazer backup do dispositivo no iCloud.
-   **Sincronização de documentos para iCloud (somente supervisado)** – Permitir a sincronização de documento e chave-valor para o espaço de armazenamento no iCloud.
-   **Sincronização de fluxo de fotografias para iCloud** – Permite que os usuários habilitem o **Meu Fluxo de Fotos** em seus dispositivos, o que permite que as fotos sejam sincronizadas com o iCloud e fiquem disponíveis em todos os dispositivos dos usuários.
-   **Backup criptografado** – Exigir que quaisquer backups de dispositivo sejam criptografados.
-   **Biblioteca de Fotos do iCloud** – Se for definido como **Não**, desabilitará o uso da biblioteca de fotos do iCloud, o que permite aos usuários armazenar fotos e vídeos na nuvem.    As fotos que não forem totalmente baixadas na biblioteca de fotos do iCloud para o dispositivo serão removidas do dispositivo se essa opção for definida como **Não**.
-   **Sincronizar aplicativos gerenciados com a nuvem** – Permitir que os aplicativos que você gerencia com o Intune sincronizem dados com a conta do iCloud do usuário.
-   **Fluxo de fotos compartilhado** – Defina como **Não** para desabilitar o **Compartilhamento de Fotos do iCloud** no dispositivo.
-   **Continuação da atividade** – Permitir que o usuário continue, em outro dispositivo iOS ou macOS, o trabalho iniciado em um dispositivo iOS (Handoff).

## <a name="autonomous-single-app-mode-supervised-only"></a>Modo autônomo de único aplicativo (somente supervisionado)

Use estas configurações para configurar dispositivos iOS para executar aplicativos especificados no modo autônomo de aplicativo único. Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado para que ele só possa executar esse aplicativo. Um exemplo disso é quando você configura um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

### <a name="settings"></a>Configurações

- **Nome do aplicativo** - insira o nome do aplicativo como ele aparecerá na lista de aplicativos desta folha.
- **ID do Pacote de Aplicativos** - insira a ID do pacote de aplicativos do aplicativo. Para obter ajuda, veja **Referência da ID de Pacote para aplicativos iOS internos** neste tópico.

Depois de especificar o nome de cada aplicativo e a ID de pacote, escolha **Adicionar** para acrescentá-los à lista.

- **Importar** - importe um arquivo .csv (valores separados por vírgulas) contendo uma lista de nomes de aplicativo e suas IDs de pacote associadas.
- **Exportar** - exporte os nomes de aplicativo e as IDs de pacote associadas configuradas para um arquivo .csv (valores separados por vírgulas).

### <a name="bundle-id-reference-for-built-in-ios-apps"></a>Referência de ID de Pacote para aplicativos iOS internos

Esta lista mostra a ID de pacote de alguns aplicativos iOS internos comuns. Para localizar a ID do pacote de outros aplicativos, entre em contato com seu fornecedor de software.

```
,com.apple.AppStore,App Store,Apple
,com.apple.calculator,Calculator,Apple
,com.apple.mobilecal,Calendar,Apple
,com.apple.camera,Camera,Apple
,com.apple.mobiletimer,Clock,Apple
,com.apple.compass,Compass,Apple
,com.apple.MobileAddressBook,Contacts,Apple
,com.apple.facetime,FaceTime,Apple
,com.apple.mobileme.fmf1,Find Friends,Apple
,com.apple.mobileme.fmip1,Find iPhone,Apple
,com.apple.gamecenter,Game Center,Apple
,com.apple.mobilegarageband,GarageBand,Apple
,com.apple.Health,Health,Apple
,com.apple.iBooks,iBooks,Apple
,com.apple.MobileStore,iTunes Store,Apple
,com.apple.itunesu,iTunes U,Apple
,com.apple.Keynote,Keynote,Apple
,com.apple.mobilemail,Mail,Apple
,com.apple.MapsMaps,Apple
,com.apple.MobileSMS,Messages,Apple
,com.apple.Music,Music,Apple
,com.apple.news,News,Apple
,com.apple.mobilenotes,Notes,Apple
,com.apple.Numbers,Numbers,Apple
,com.apple.Pages,Pages,Apple
,com.apple.Photo-Booth,Photo Booth,Apple
,com.apple.mobileslideshow,Photos,Apple
,com.apple.podcasts,Podcasts,Apple
,com.apple.reminders,Reminders,Apple
,com.apple.mobilesafariSafari,Apple
,com.apple.Preferences,Settings,Apple
,com.apple.stocks,Stocks,Apple
,com.apple.tips,Tips,Apple
,com.apple.videos,Videos,Apple
,com.apple.VoiceMemos,VoiceMemos,Apple
,com.apple.Passbook,Wallet,Apple
,com.apple.Bridge,Watch,Apple
,com.apple.weather,Weather,Apple


```


## <a name="kiosk-supervised-only"></a>Quiosque (somente supervisionado)
-   **Aplicativo que é executado no modo de quiosque** – Escolha **Aplicativo Gerenciado** para selecionar um aplicativo que você adicionou ao Intune, ou **Aplicativo da Loja** para especificar a URL para um aplicativo na loja. Nenhum outro aplicativo poderá ser executado no dispositivo. Para obter mais ajuda, consulte "How to specify URLs to app stores" (Como especificar URLs para lojas de aplicativos) mais adiante neste tópico.
    -   **Toque auxiliar** – Habilitar ou desabilitar a configuração de acessibilidade **Toque auxiliar**, que ajuda o usuário a executar gestos na tela que podem ser difíceis de executar.
    -   **Inverter cores** – Habilitar ou desabilitar a configuração de acessibilidade Inverter Cores que ajusta a exibição para ajudar os usuários com deficiências visuais.
    -   **Áudio mono** – Habilitar ou desabilitar a configuração de acessibilidade Áudio mono.
    -   **VoiceOver** – Habilitar ou desabilitar a configuração de acessibilidade **VoiceOver**, que lê em voz alta o texto na tela do dispositivo.
    -   **Zoom** – Habilitar ou desabilitar a configuração de acessibilidade de **Zoom** que permite ao usuário usar o toque para ampliar a tela do dispositivo de acessibilidade.
    -   **Bloqueio automático**- Habilitar ou desabilitar o bloqueio automático do dispositivo.
    -   **Botão de toque** – Habilitar ou desabilitar a opção de botão de toque (mudo) no dispositivo.
    -   **Rotação da tela** – Habilitar ou desabilitar a alteração da orientação da tela quando o usuário gira o dispositivo.
    -   **Botão de suspensão da tela** – Habilitar ou desabilitar o botão de suspensão e ativação da tela no dispositivo.
    -   **Toque** – Habilitar ou desabilitar a tela touch no dispositivo.
    -   **Botões de volume** – Habilitar ou desabilitar o uso dos botões de volume no dispositivo.
    -   **Controle de toque auxiliar** – Habilitar ou desabilitar os ajustes de toque auxiliar que permitem ao usuário ajustar a função de toque auxiliar.
    -   **Controle de inversão e cores** – Habilitar ou desabilitar ajustes de inverter ajustes que permite ao usuário ajustar a função inverter cores.
    -   **Falar texto selecionado** – Habilitar ou desabilitar as configurações de acessibilidade Seleção de fala que podem ler em voz alta o texto que o usuário selecionar.
    -   **Controle VoiceOver** – Habilitar ou desabilitar os ajustes de narração que permitem que o usuário ajuste a função VoiceOver (por exemplo, a rapidez que o texto na tela é lido em voz alta).
    -   **Controle de Zoom** – Habilitar ou desabilitar os ajustes de zoom que permitem ao usuário ajustar a função de zoom.

>[!NOTE]
> Antes de configurar um dispositivo iOS para o modo de quiosque, você deve usar a ferramenta Apple Configurator ou o Programa de registro de dispositivos da Apple para colocar o dispositivo no modo supervisionado. Para obter mais informações sobre a ferramenta Apple Configurator, consulte sua documentação da Apple.
>Se o aplicativo iOS que você especificar for instalado após a atribuição do perfil, o dispositivo só entrará no modo de quiosque depois de ser reiniciado.

## <a name="safari"></a>Safari
-   **Safari (somente supervisado)** – Especifique se o navegador Safari pode ser usado no dispositivo.
-   **Preenchimento automático** – Permite que o usuário possa alterar as configurações de preenchimento automático no navegador.
-   **Cookies** – Permitir que o navegador use cookies.
-   **JavaScript** – Permitir a execução de scripts Java no navegador.
-   **Avisos de fraude** – Permitir avisos de fraude no navegador.
-   **Pop-ups** – Habilitar ou desabilitar o bloqueador de pop-ups do navegador.


## <a name="domains"></a>Domínios

### <a name="unmarked-email-domains"></a>Domínios de email desmarcados

No campo **URL do Domínio de Email**, adicione uma ou mais URLs à lista. Quando os usuários finais receberem um email de um domínio diferente daqueles configurados por você, o email será marcado como não confiável no aplicativo Mail do iOS.


### <a name="managed-web-domains"></a>Domínios da web gerenciados

No campo **URL do Domínio da Web**, adicione uma ou mais URLs à lista. Quando os documentos forem baixados dos domínios especificados, eles serão considerados gerenciados. Essa configuração só se aplica a documentos baixados usando o navegador Safari.


### <a name="safari-password-auto-fill-domains"></a>Domínios de preenchimento automático de senha do Safari

No campo **URL do Domínio**, adicione uma ou mais URLs à lista. Os usuários só podem salvar senhas da Web das URLs nesta lista. Essa configuração se aplica somente ao navegador Safari e aos dispositivos com iOS 9.3 e posteriores no modo supervisionado. Se você não especificar URLs, será possível salvar senhas de todos os sites.
