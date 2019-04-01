---
title: Configurações de recurso de dispositivo iOS no Microsoft Intune – Azure | Microsoft Docs
description: Veja todas as configurações de dispositivos iOS para AirPrint, layout da tela inicial, notificações do aplicativo, dispositivo compartilhado, logon único e filtro de conteúdo da Web no Microsoft Intune. Use essas configurações em um perfil de configuração de dispositivo para configurar dispositivos iOS e usar esses recursos diferentes da Apple em sua organização.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/13/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 34f0869b46323606d69891c3761bfbc154f3b6a3
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566617"
---
# <a name="ios-device-settings-to-use-common-ios-features-in-intune"></a>configurações de dispositivo iOS para usar recursos comuns do iOS no Intune

O Intune inclui algumas configurações internas que permitem aos usuários de iOS utilizarem recursos diferentes da Apple em seus dispositivos. Por exemplo, os administradores podem controlar como os usuários de iOS utilizam impressoras AirPrint, adicionam aplicativos e pastas ao dock e às páginas na tela inicial, mostram notificações de aplicativo, mostram detalhes da marca de ativo na tela de bloqueio, usam a autenticação de logon único e autenticam usuários com certificados.

Use esses recursos para controlar os dispositivos iOS como parte de sua solução MDM (gerenciamento) do dispositivo móvel.

Este artigo lista essas configurações e descreve o que cada uma faz.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração de dispositivo iOS](device-features-configure.md#create-a-device-profile).

## <a name="airprint-settings"></a>Configurações de AirPrint

Esse recurso permite que os usuários de iOS imprimam em impressoras do AirPrint conhecidas.

1. Em **Ajustes**, escolha **AirPrint**. Insira as seguintes propriedades do servidor AirPrint:

    - **Endereço IP**: insira o endereço IPv4 ou IPv6 da impressora. Se você usar nomes de host para identificar as impressoras, obtenha o endereço IP ao executar o ping da impressora no terminal. Obter o endereço IP e o caminho (neste artigo) fornece mais detalhes.
    - **Caminho**: geralmente, o caminho é `ipp/print` para impressoras na rede. Obter o endereço IP e o caminho (neste artigo) fornece mais detalhes.
    - **Porta**: insira a porta de escuta do destino do AirPrint. Se você deixar essa propriedade em branco, o AirPrint usará a porta padrão. Disponível no iOS 11.0 e posterior.
    - **TLS**: escolha **Habilitar** para proteger as conexões do AirPrint com o protocolo TLS. Disponível no iOS 11.0 e posterior.

2. Selecione **Adicionar**. O servidor do AirPrint é adicionado à lista. Você pode adicionar vários servidores do AirPrint.

    Você também pode **Importar** um arquivo .csv (separado por vírgula) com essas informações. Depois de criar a lista, você também pode **Exportar** sua lista de servidores do AirPrint.

3. Quando terminar, escolha **OK** para salvar sua lista.

Para adicionar servidores AirPrinter, você precisa ter o endereço IP da impressora, o caminho do recurso e a porta. As etapas a seguir mostram como obter essas informações.

1. Em um Mac conectado à mesma rede local (sub-rede) que as impressoras AirPrint, abra o **Terminal** (em **/Applications/Utilities**).
2. No Terminal, digite `ippfind` e escolha Enter.

    Anote as informações da impressora. Por exemplo, pode retornar algo semelhante a `ipp://myprinter.local.:631/ipp/port1`. A primeira parte é o nome da impressora. A última parte (`ipp/port1`) é o caminho do recurso.

3. No Terminal, digite `ping myprinter.local` e escolha Enter.

   Anote o endereço IP. Por exemplo, pode retornar algo semelhante a `PING myprinter.local (10.50.25.21)`.

4. Use os valores do endereço IP e do caminho de recursos. Neste exemplo, o endereço IP é `10.50.25.21` e o caminho do recurso é `/ipp/port1`.

## <a name="home-screen-layout-settings"></a>Configurações de layout da Tela inicial

Essas configurações definem o layout do aplicativo e as pastas no dock e na tela inicial de dispositivos iOS. Para usar esse recurso, os dispositivos iOS devem estar no modo supervisionado e executam o iOS 9.3 ou posterior.

### <a name="dock"></a>Dock

Use as configurações do **Dock** para adicionar até seis itens ou pastas ao dock na tela do iOS. Muitos dispositivos dão suporte a menos itens. Por exemplo, iPhones dão suporte a até quatro itens. Nesse caso, só os primeiros quatro itens adicionados aparecerão no dispositivo.

1. Em **Ajustes**, selecione **Layout da tela inicial (somente supervisionado)** > **Dock** > **Adicionar**. Você pode adicionar até **seis** itens (aplicativos e pastas combinados) ao dock do dispositivo.
2. Em **Tipo**, escolha adicionar um **Aplicativo** ou uma **Pasta**.

    - **Adicionar um aplicativo**: escolha esta opção para adicionar aplicativos ao encaixe na tela. Insira:

      - **Nome do aplicativo**: insira um nome para o aplicativo. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo iOS.
      - **ID do Pacote de Aplicativos**: insira a ID do pacote de aplicativos do aplicativo. Confira [IDs do lote para aplicativos iOS internos](#bundle-ids-for-built-in-ios-apps) (neste artigo) para obter alguns exemplos.

      Selecione **OK** para salvar suas alterações.

    - **Adicionar uma pasta**: escolha esta opção para adicionar uma pasta ao encaixe na tela. 

      Os aplicativos adicionados a uma página em uma pasta são dispostos da esquerda para a direita, e na mesma ordem da lista. Se você adicionar mais aplicativos do que uma página comporta, eles serão movidos para outra página.

      1. Insira um **Nome de pasta**. Esse nome é exibido aos usuários em seus dispositivos.
      2. Escolha **Adicionar** e insira as seguintes propriedades:

          - **Nome da página**: insira um nome para a página. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo iOS.
          - **Nome do aplicativo**: insira um nome para o aplicativo. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo iOS.
          - **ID do Pacote de Aplicativos**: insira a ID do pacote de aplicativos do aplicativo. Confira [IDs do lote para aplicativos iOS internos](#bundle-ids-for-built-in-ios-apps) (neste artigo) para obter alguns exemplos.

      3. Escolha **Adicionar**. Você pode adicionar até **20** páginas para o dock do dispositivo.
      4. Selecione **OK** para salvar suas alterações.

#### <a name="example"></a>Exemplo

No exemplo a seguir, a tela do dock mostra apenas os aplicativos Safari, Mail e Bolsa. O aplicativo Mail está selecionado para mostrar suas propriedades:

![Exemplo de configurações do dock do iOS](./media/FfFiUcP.png)

Quando você atribui a política a um iPhone, o dock será semelhante à imagem a seguir:

![Exemplo de layout do dock do iOS no iPhone](./media/bAgCe8F.png)

### <a name="pages"></a>Páginas

Adicione as páginas que você deseja exibir na tela inicial, e os aplicativos que aparecerão em cada página. Os aplicativos adicionados a uma página são dispostos da esquerda para a direita, na mesma ordem da lista. Se você adicionar mais aplicativos do que uma página comporta, eles serão movidos para outra página.

> [!TIP]
> Para reorganizar itens em quaisquer listas de páginas e na Tela inicial, arraste e solte-os.

1. Em **Ajustes**, selecione **Layout da Tela Inicial (somente supervisionado)** > **Páginas** > **Adicionar**. Você pode adicionar até **40** páginas em um dispositivo.
2. Insira um **Nome de página**. Esse nome é usado para sua referência no portal do Azure e *não é exibido* no dispositivo iOS. 

    Selecione **Adicionar**. Você pode adicionar até **60** itens (aplicativos e a pasta combinados) em um dispositivo.

3. Em **Tipo**, escolha adicionar um **Aplicativo** ou uma **Pasta**.

    - **Adicionar um aplicativo**: escolha esta opção para adicionar aplicativos a uma página na tela. Insira:

      - **Nome do aplicativo**: insira um nome para o aplicativo. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo iOS.
      - **ID do Pacote de Aplicativos**: insira a ID do pacote de aplicativos do aplicativo. Confira [IDs do lote para aplicativos iOS internos](#bundle-ids-for-built-in-ios-apps) (neste artigo) para obter alguns exemplos.

      Selecione **OK** para salvar suas alterações.

    - **Adicionar uma pasta**: escolha esta opção para adicionar uma pasta ao encaixe na tela. 

      Os aplicativos adicionados a uma página em uma pasta são dispostos da esquerda para a direita, e na mesma ordem da lista. Se você adicionar mais aplicativos do que uma página comporta, eles serão movidos para outra página.

      1. Insira um **Nome de pasta**. Esse nome é exibido aos usuários em seus dispositivos.
      2. Escolha **Adicionar** e insira as seguintes propriedades:

          - **Nome da página**: insira um nome para a página. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo iOS.
          - **Nome do aplicativo**: insira um nome para o aplicativo. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo iOS.
          - **ID do Pacote de Aplicativos**: insira a ID do pacote de aplicativos do aplicativo. Confira [IDs do lote para aplicativos iOS internos](#bundle-ids-for-built-in-ios-apps) (neste artigo) para obter alguns exemplos.

      3. Escolha **Adicionar**.
      4. Selecione **OK** para salvar suas alterações.

#### <a name="example"></a>Exemplo

No exemplo a seguir, uma nova página chamada **Contoso** é adicionada. A página mostra os aplicativos Buscar Amigos e Ajustes. O aplicativo Ajustes está selecionado para mostrar suas propriedades:

![Exemplo de ajustes na Tela inicial do iOS](./media/Jc2OxyX.png)

Quando você atribui a política a um iPhone, a página será semelhante à imagem a seguir:

![Dispositivo iOS com Tela inicial modificada](./media/Bd37PHa.png)

## <a name="app-notifications-settings"></a>Ajustes de notificações de aplicativo

Escolha como os aplicativos instalados em um dispositivo iOS enviam notificações. Essa configuração dá suporte a dispositivos supervisionados que executam o iOS 9.3 e posterior.

1. Em **Ajustes**, selecione **Notificações do Aplicativo (somente supervisionado)** > **Adicionar**:

    ![Adicionar notificação do aplicativo no perfil do iOS no Intune](./media/ios-macos-app-notifications.png)

2. Insira as seguintes propriedades:

    - **ID do pacote de aplicativos**: insira a **ID do pacote de aplicativos** do aplicativo que você deseja adicionar. Confira [IDs do lote para aplicativos iOS internos](#bundle-ids-for-built-in-ios-apps) (neste artigo) para obter alguns exemplos.
    - **Nome do aplicativo**: insira o nome do aplicativo que você deseja adicionar. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo.
    - **Editor**: insira o editor do aplicativo que você está adicionando. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo.
    - **Notificações**: **habilite** ou **desabilite** o envio de notificações do aplicativo para o dispositivo.
       - **Mostrar no Centro de Notificações**: **Habilitar** permite que o aplicativo mostre as notificações no Centro de Notificações do dispositivo. **Desabilite** para permitir que o aplicativo mostre as notificações no Centro de Notificações.
       - **Mostrar na Tela de Bloqueio**: selecione **Habilitar** para ver as notificações do aplicativo na tela de bloqueio do dispositivo. **Desabilite** para permitir que o aplicativo mostre as notificações na tela de bloqueio.
       - **Tipo de alerta**: quando o dispositivo for desbloqueado, escolha como a notificação é mostrada. Suas opções:
         - **Nenhum**: nenhuma notificação é exibida.
         - **Faixa**: uma faixa aparece brevemente com a notificação.
         - **Modal**: a notificação é exibida e o usuário deve descartá-la manualmente antes de continuar a usar o dispositivo.
       - **Notificação no ícone do aplicativo**: selecione **habilitar** para adicionar uma notificação ao ícone do aplicativo. A notificação indica que o aplicativo enviou uma notificação.
       - **Sons**: selecione **Habilitar** para tocar um som quando uma notificação for entregue.

3. Selecione **OK** para salvar suas alterações. Continue adicionando os aplicativos que você deseja. Quando terminar, selecione **OK**.

## <a name="lock-screen-message-settings"></a>Configurações da mensagem da tela de bloqueio

Use essas configurações para mostrar uma mensagem ou um texto personalizado na janela de entrada e na tela de bloqueio. Por exemplo, insira uma mensagem "Em caso de perda, devolver a" e informações da tag do ativo. 

Esse recurso dá suporte a dispositivos supervisionados que executam:

- iOS 9.3 e posterior

1. Em **Configurações**, selecione **Mensagem da Tela de Bloqueio (somente supervisionado)**.
2. Insira as seguintes configurações:

    - **Informações de marca do ativo**: insira informações sobre a marca do ativo do dispositivo. Por exemplo, insira `Owned by Contoso Corp` ou `Serial Number: {{serialnumber}}`. 

      O texto inserido é mostrado na janela de entrada e na tela de bloqueio do dispositivo.

    - **Nota de rodapé de tela de bloqueio**: se o dispositivo for perdido ou roubado, insira uma observação que pode ajudar a reaver o dispositivo. É possível inserir qualquer texto desejado. Por exemplo, insira algo como `If found, call Contoso at ...`.

    Os tokens de dispositivo também podem ser usados para adicionar informações específicas do dispositivo a esses campos. Por exemplo, para mostrar o número de série, insira `Serial Number: {{serialnumber}}`. Na tela de bloqueio, o texto mostra algo semelhante a `Serial Number 123456789ABC`. Ao inserir variáveis, lembre-se de usar chaves `{{ }}`. [Tokens de configuração de aplicativo](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) inclui uma lista das variáveis que podem ser usadas. Use também `deviceName` ou qualquer outro valor específico do dispositivo.

    > [!NOTE]
    > Variáveis não são validadas na interface do usuário. Como resultado, você pode ver perfis salvos com uma entrada incorreta. Por exemplo, se você digitar `{{Devicename}}` em vez de `{{devicename}}`, a cadeia de caracteres literal será mostrada em lugar do nome exclusivo do dispositivo.

3. Após terminar, selecione **OK** para salvar suas alterações.

## <a name="single-sign-on-settings"></a>Configurações de logon único

A maioria dos aplicativos LOB (Linha de Negócios) exigem algum nível de autenticação de usuário para dar suporte à segurança. Em muitos casos, a autenticação exige que o usuário insira as mesmas credenciais várias vezes, o que é frustrante para os usuários. Para melhorar a experiência do usuário, os desenvolvedores podem criar aplicativos que usam o logon único (SSO). O logon único reduz o número de vezes que um usuário precisa inserir credenciais.

Para usar o logon único, verifique se você tem:

- um aplicativo codificado para procurar o repositório de credenciais do usuário no logon único no dispositivo.
- Intune configurado para logon único de dispositivo iOS.

1. Em **Ajustes**, selecione **Logon único**:

   ![Painel de logon único](./media/sso-blade.png)

2. Insira as seguintes configurações:

    - **Atributo de nome de usuário do AAD**: o Intune procura esse atributo para cada usuário no Azure AD. Depois, o Intune preenche o respectivo campo (como o UPN) antes de gerar o conteúdo XML instalado no dispositivo. Suas opções:

      - **Nome UPN**: o UPN é analisado da seguinte maneira:

        ![Atributo de nome de usuário](media/User-name-attribute.png)

        Você também pode substituir o realm pelo texto inserido na caixa de texto **Realm**.

        Por exemplo, Contoso tem várias regiões, incluindo Europa, Ásia e América do Norte. A Contoso deseja que os usuários na Ásia usem o SSO, e o aplicativo exige o UPN no formato `username@asia.contoso.com`. Quando você seleciona **Nome UPN**, o realm de cada usuário é obtido do Azure AD, que é `contoso.com`. Portanto, para os usuários na Ásia, selecione **nome UPN** e insira `asia.contoso.com`. O UPN do usuário final se torna `username@asia.contoso.com`, em vez de `username@contoso.com`.

      - **ID do dispositivo do Intune**: o Intune seleciona automaticamente a ID do Dispositivo Intune.

        Por padrão, aplicativos precisam usar somente a ID do dispositivo. Porém, se o aplicativo usar o realm e a ID do dispositivo, você poderá digitar o realm na caixa de texto Realm.

        > [!NOTE]
        > Por padrão, mantenha o realm vazio se você usar a ID do dispositivo.

      - **Id do dispositivo do Azure AD**

    - **Realm**: insira a parte do domínio da URL. Por exemplo, insira `contoso.com`.
    - **Prefixos de URL que usarão Logon Único**: escolha **Adicionar** todas as URLs em sua organização que exigem autenticação de logon único de usuário.

        Por exemplo, quando um usuário se conecta a qualquer um desses sites, o dispositivo iOS usa as credenciais de logon único. O usuário não precisa inserir credenciais adicionais. No entanto, se a autenticação multifator estiver habilitada, os usuários deverão inserir a segunda autenticação.

        > [!NOTE]
        > Essas URLs devem ter FQDN corretamente formatado. A Apple exige que estejam no formato `http://<yourURL.domain>`.

        Os padrões de correspondência de URL devem começar com um `http://` ou `https://`. Uma correspondência de cadeia de caracteres simples é executada, de modo que o prefixo da URL `http://www.contoso.com/` não corresponda a `http://www.contoso.com:80/`. Com o iOS 10.0 ou posterior, um único curinga \* pode ser usado para inserir todos os valores correspondentes. Por exemplo, `http://*.contoso.com/` corresponde tanto a `http://store.contoso.com/` quanto a `http://www.contoso.com`.

        Os padrões `http://.com` e `https://.com` correspondem a todas as URLs HTTP e HTTPS, respectivamente.

    - **Aplicativos que usarão o Logon Único**: escolha **Adicionar** aplicativos em dispositivos dos usuários finais que podem usar logon único.

        A matriz `AppIdentifierMatches` deve incluir cadeias de caracteres que correspondam a IDs de lote de aplicativo. Essas cadeias de caracteres podem ser correspondências exatas (como `com.contoso.myapp`), ou insira uma correspondência de prefixo na ID de lote usando o caractere curinga \*. O caractere curinga deve aparecer após um caractere de ponto (.) e pode aparecer apenas uma vez, no final da cadeia de caracteres, como `com.contoso.*`. Quando um caractere curinga for incluído, qualquer aplicativo cuja ID do pacote comece com o prefixo receberá acesso à conta.

        Use **Nome do Aplicativo** para inserir um nome amigável para ajudá-lo a identificar a ID do pacote.

    - **Certificado de renovação de credencial**: se estiver usando certificados para autenticação (não senhas), selecione o certificado SCEP ou PFX existente como o certificado de autenticação. Normalmente, esse é o mesmo certificado implantado para o usuário para outros perfis, como VPN, Wi-Fi ou email.

3. Após terminar, selecione **OK** para salvar suas alterações.

## <a name="web-content-filter-settings"></a>Configurações do filtro de conteúdo da Web

Essas configurações controlam o acesso de URL do navegador em dispositivos iOS.

1. Em **Ajustes**, selecione **Filtro de Conteúdo da Web (somente supervisionado)**.
2. Escolha o **Tipo de Filtro**. Suas opções:

    - **Configurar URLs**: use o filtro da Web interno da Apple que procura termos adultos, incluindo profanação ou linguagem pornográfica. Esse recurso avalia cada página da web conforme ela é carregada e identifica e bloqueia conteúdo inadequado. Adicione também as URLs que você não deseja verificar usando o filtro. Ou bloqueie URLs específicas, independentemente dos ajustes de filtro da Apple.

      - **URLs permitidas**: **Add** as URLs que você deseja permitir. Essas URLs ignoram o filtro da Web da Apple.

        > [!NOTE]
        > As URLs inseridas são as URLs que você não quer avaliar com o filtro da Web da Apple. Essas URLs não são uma lista de sites permitidos. Para criar uma lista de sites permitidos, defina o **Tipo de Filtro** como **Somente sites específicos**.

        Selecione **OK** para salvar suas alterações.

      - **URLs bloqueadas**: **Adicione** as URLs que você deseja parar de abrir, independentemente das configurações de filtro da Web da Apple.

        Selecione **OK** para salvar suas alterações.

    - **Somente para sites específicos** (somente para o navegador da Web Safari): essas URLs são adicionadas aos indicadores do navegador Safari. O usuário **só** tem permissão para visitar esses sites; nenhum outro site pode ser aberto. Use essa opção somente se você conhecer a lista exata de URLs que os usuários podem acessar.

      - **URL**: insira a URL do site que você deseja permitir. Por exemplo, insira `https://www.contoso.com`.
      - **Caminho do indicador**: insira o caminho para armazenar o indicador. Por exemplo, insira `/Contoso/Business Apps`. Se você não adicionar um indicador, ele será adicionado à pasta de indicadores padrão no dispositivo.
      - **Título**: insira um título descritivo para o indicador.

      Se você não inserir URLs, os usuários finais não poderão acessar nenhum site, exceto `microsoft.com`, `microsoft.net` e `apple.com`. Essas URLs são permitidas automaticamente pelo Intune.

      Selecione **OK** para salvar suas alterações.

## <a name="wallpaper-settings"></a>Configurações de papel de parede

Adicione uma imagem .png, .jpg ou .jpeg personalizada aos seus dispositivos iOS supervisionados. Por exemplo, use um logotipo da empresa na tela de bloqueio.

Você pode enfrentar um comportamento inesperado quando um perfil sem nenhuma imagem é atribuído a dispositivos com uma imagem existente. Por exemplo, você pode criar um perfil sem uma imagem. Este perfil é atribuído a dispositivos que já têm uma imagem. Nesse cenário, a imagem pode ser alterada para o padrão do dispositivo ou a imagem original pode permanecer no dispositivo. Esse comportamento é controlado e limitado pela plataforma de MDM da Apple.

- **Local de exibição de papel de parede**: escolha um local no dispositivo para mostrar a imagem. Suas opções:
  - **Não configurado**: uma imagem personalizada não será adicionada ao dispositivo. O dispositivo usa o sistema operacional padrão.
  - **Tela de bloqueio**: adiciona a imagem para a tela de bloqueio.
  - **Tela inicial**: adiciona a imagem à tela inicial.
  - **Tela de bloqueio e tela inicial do**: usa a mesma imagem na tela de bloqueio e tela inicial.
- **Imagem de papel de parede**: carregue uma imagem .png, .jpg ou .jpeg que você quer usar. Verifique se o tamanho do arquivo é menor do que 750 KB. Você também pode **remover** uma imagem adicionada.

> [!TIP]
> Para exibir imagens diferentes na tela de bloqueio e na tela inicial, crie um perfil com a imagem de tela de bloqueio. Crie outro perfil com a imagem de tela inicial. Atribua os dois perfis aos seus grupos de usuários ou dispositivos iOS.

## <a name="bundle-ids-for-built-in-ios-apps"></a>IDs de pacote para aplicativos iOS internos

A lista a seguir mostra a ID do pacote de alguns aplicativos iOS nativos comuns. Para localizar a ID do pacote de outros aplicativos, entre em contato com seu fornecedor de software.

| ID do Pacote                   | Nome do Aplicativo     | Editor |
|-----------------------------|--------------|-----------|
| com.apple.AppStore          | Loja de aplicativos    | Apple     |
| com.apple.calculator        | Calculadora   | Apple     |
| com.apple.mobilecal         | Calendário     | Apple     |
| com.apple.camera            | Câmera       | Apple     |
| com.apple.mobiletimer       | Relógio        | Apple     |
| com.apple.compass           | Bússola      | Apple     |
| com.apple.MobileAddressBook | Contacts     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.DocumentsApp      | Arquivos        | Apple     |
| com.apple.mobileme.fmf1     | Buscar Amigos | Apple     |
| com.apple.mobileme.fmip1    | Buscar iPhone  | Apple     |
| com.apple.gamecenter        | Game Center  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Integridade       | Apple     |
| com.apple.Home              | Início         | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.iMovie            | iMovie       | Apple     |
| com.apple.itunesconnect.mobile | iTunes Connect | Apple |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Email         | Apple     |
| com.apple.Maps              | Mapas         | Apple     |
| com.apple.MobileSMS         | Mensagens     | Apple     |
| com.apple.Music             | Música        | Apple     |
| com.apple.news              | News         | Apple     |
| com.apple.mobilenotes       | Anotações        | Apple     |
| com.apple.Numbers           | Números      | Apple     |
| com.apple.Pages             | Páginas        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Fotos       | Apple     |
| com.apple.podcasts          | Podcasts     | Apple     |
| com.apple.reminders         | Lembretes    | Apple     |
| com.apple.mobilesafari      | Safari       | Apple     |
| com.apple.Preferences       | Configurações     | Apple     |
| com.apple.SiriViewService   | Siri         | Apple     |
| com.apple.stocks            | Bolsa       | Apple     |
| com.apple.tips              | Dicas         | Apple     |
| com.apple.TV                | TV           | Apple     |
| com.apple.videos            | Vídeos       | Apple     |
| com.apple.VoiceMemos        | VoiceMemos   | Apple     |
| com.apple.Passbook          | Carteira       | Apple     |
| com.apple.Bridge            | Assistir        | Apple     |
| com.apple.weather           | Clima      | Apple     |

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

Você também pode criar perfis de recurso do dispositivo para dispositivos [macOS](macos-device-features-settings.md).
