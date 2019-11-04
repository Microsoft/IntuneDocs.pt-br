---
title: Configurações de recurso de dispositivo iOS no Microsoft Intune – Azure | Microsoft Docs
description: Veja todas as configurações de dispositivos iOS para AirPrint, layout da tela inicial, notificações do aplicativo, dispositivo compartilhado, logon único e filtro de conteúdo da Web no Microsoft Intune. Use essas configurações em um perfil de configuração de dispositivo para configurar dispositivos iOS e usar esses recursos da Apple em sua organização.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/28/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e3e0ea523d71ff036f1f23c9436c65e105328d8b
ms.sourcegitcommit: 807ab3e35f4d9ffa18655410b7d61e5e772ab348
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73057653"
---
# <a name="ios-and-ipados-device-settings-to-use-common-ios-features-in-intune"></a>Configurações de dispositivo iOS e iPadOS para usar recursos comuns do iOS no Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Intune inclui algumas configurações internas que permitem aos usuários de iOS utilizarem recursos diferentes da Apple em seus dispositivos. Por exemplo, os administradores podem controlar como os usuários de iOS utilizam impressoras AirPrint, adicionam aplicativos e pastas ao dock e às páginas na tela inicial, mostram notificações de aplicativo, mostram detalhes da marca de ativo na tela de bloqueio, usam a autenticação de logon único e autenticam usuários com certificados.

Use esses recursos para controlar os dispositivos do iOS como parte de sua solução MDM (gerenciamento de dispositivo móvel).

Este artigo lista essas configurações e descreve o que cada uma faz. Para obter mais informações sobre esses recursos, vá para [Adicionar configurações de recurso de dispositivo IOS ou MacOS](../device-features-configure.md).

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração de dispositivo iOS](../device-features-configure.md).

> [!NOTE]
> Essas configurações se aplicam a diferentes tipos de registro, com algumas configurações sendo aplicadas a todas as opções de registro. Para obter mais informações sobre os diferentes tipos de registro, consulte [registro do IOS](../ios-enroll.md).

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a: todos os tipos de registro

> [!NOTE]
> Certifique-se de adicionar todas as impressoras ao mesmo perfil. A Apple impede que vários perfis de impressões sejam direcionados para o mesmo dispositivo.

- **Endereço IP**: insira o endereço IPv4 ou IPv6 da impressora. Se você usar nomes de host para identificar as impressoras, obtenha o endereço IP ao executar o ping da impressora no terminal. Obter o endereço IP e o caminho (neste artigo) fornece mais detalhes.
- **Caminho**: geralmente, o caminho é `ipp/print` para impressoras na rede. Obter o endereço IP e o caminho (neste artigo) fornece mais detalhes.
- **Porta**: insira a porta de escuta do destino do AirPrint. Se você deixar essa propriedade em branco, o AirPrint usará a porta padrão. Disponível no iOS 11.0 e posterior.
- **TLS**: escolha **Habilitar** para proteger as conexões do AirPrint com o protocolo TLS. Disponível no iOS 11.0 e posterior.

Para adicionar servidores de impressão, você pode:

- **Adicionar** adiciona o servidor do AirPrint à lista. Muitos servidores de impressão de impressões podem ser adicionados.
- **Importar** um arquivo .csv (separado por vírgula) com essas informações. Ou, **Exportar** para criar uma lista de servidores de impressão que você adicionou.

### <a name="get-server-ip-address-resource-path-and-port"></a>Obter o endereço IP do servidor, caminho de recurso e porta

Para adicionar servidores AirPrinter, você precisa ter o endereço IP da impressora, o caminho do recurso e a porta. As etapas a seguir mostram como obter essas informações.

1. Em um Mac conectado à mesma rede local (sub-rede) que as impressoras AirPrint, abra o **Terminal** (em **/Applications/Utilities**).
2. No Terminal, digite `ippfind` e escolha Enter.

    Anote as informações da impressora. Por exemplo, pode retornar algo semelhante a `ipp://myprinter.local.:631/ipp/port1`. A primeira parte é o nome da impressora. A última parte (`ipp/port1`) é o caminho do recurso.

3. No Terminal, digite `ping myprinter.local` e escolha Enter.

   Anote o endereço IP. Por exemplo, pode retornar algo semelhante a `PING myprinter.local (10.50.25.21)`.

4. Use os valores do endereço IP e do caminho de recursos. Neste exemplo, o endereço IP é `10.50.25.21` e o caminho do recurso é `/ipp/port1`.

## <a name="home-screen-layout"></a>Layout da tela inicial

Esse recurso aplica-se a:

- iOS 9,3 ou mais recente

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

### <a name="dock"></a>Dock

Use as configurações do **Dock** para adicionar até seis itens ou pastas ao dock na tela do iOS. Muitos dispositivos dão suporte a menos itens. Por exemplo, iPhones dão suporte a até quatro itens. Nesse caso, só os primeiros quatro itens adicionados aparecerão no dispositivo.

Você pode adicionar até **seis** itens (aplicativos e pastas combinados) ao dock do dispositivo.

- **Adicionar**: adiciona aplicativos ou pastas ao dock no dispositivo.
- **Tipo**: adicionar um **aplicativo** ou uma **pasta**:

  - **Aplicativo**: escolha esta opção para adicionar aplicativos ao dock na tela. Insira:

    - **Nome do Aplicativo**: insira um nome para o aplicativo. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo iOS.
    - **ID do Pacote de Aplicativos**: insira a ID do pacote de aplicativos do aplicativo. Confira alguns exemplos em [IDs do lote para aplicativos iOS internos](bundle-ids-built-in-ios-apps.md).

  - **Pasta**: escolha esta opção para adicionar uma pasta ao dock na tela.

    Os aplicativos adicionados a uma página em uma pasta são dispostos da esquerda para a direita, e na mesma ordem da lista. Se você adicionar mais aplicativos do que uma página comporta, eles serão movidos para outra página.

    - **Nome da pasta**: insira o nome da pasta. Esse nome é exibido aos usuários em seus dispositivos.
    - **Lista de páginas**: **adicione** uma página e insira as seguintes propriedades:

      - **Nome da página**: insira um nome para a página. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo iOS.
      - **Nome do Aplicativo**: insira um nome para o aplicativo. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo iOS.
      - **ID do Pacote de Aplicativos**: insira a ID do pacote de aplicativos do aplicativo. Confira alguns exemplos em [IDs do lote para aplicativos iOS internos](bundle-ids-built-in-ios-apps.md).

      Você pode adicionar até **20** páginas para o dock do dispositivo.

> [!NOTE]
> Quando você adiciona ícones usando as configurações de Encaixe, os ícones na Tela Inicial e páginas estão bloqueados e não podem ser movidos. Isso pode estar ser feito por design com políticas de MDM do iOS e da Apple.

#### <a name="example"></a>Exemplo

No exemplo a seguir, a tela do dock mostra apenas os aplicativos Safari, Mail e Bolsa. O aplicativo Mail está selecionado para mostrar suas propriedades:

![Exemplo de configurações do dock do iOS](./media/ios-device-features-settings/FfFiUcP.png)

Quando você atribui a política a um iPhone, o dock será semelhante à imagem a seguir:

![Exemplo de layout do dock do iOS no iPhone](./media/ios-device-features-settings/bAgCe8F.png)

### <a name="pages"></a>Páginas

Adicione as páginas que você deseja exibir na tela inicial, e os aplicativos que aparecerão em cada página. Os aplicativos adicionados a uma página são dispostos da esquerda para a direita, na mesma ordem da lista. Se você adicionar mais aplicativos do que uma página comporta, eles serão movidos para outra página.

> [!TIP]
> Para reorganizar itens em quaisquer listas de páginas e na Tela inicial, arraste e solte-os.

Você pode adicionar até **40** páginas em um dispositivo.

- **Lista de páginas**: **adicione** uma página e insira as seguintes propriedades:

  - **Nome da página**: insira um nome para a página. Esse nome é usado para sua referência no portal do Azure e *não é exibido* no dispositivo iOS.

  Você pode adicionar até **60** itens (aplicativos e a pasta combinados) em um dispositivo.

  - **Adicionar**: adiciona aplicativos ou pastas a uma página no dispositivo.

    - **Tipo**: adicionar um **aplicativo** ou uma **pasta**:

      - **Aplicativo**: escolha esta opção para adicionar aplicativos a uma página na tela. Insira também:

        - **Nome do Aplicativo**: insira um nome para o aplicativo. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo iOS.
        - **ID do Pacote de Aplicativos**: insira a ID do pacote de aplicativos do aplicativo. Confira alguns exemplos em [IDs do lote para aplicativos iOS internos](bundle-ids-built-in-ios-apps.md).

      - **Pasta**: escolha esta opção para adicionar uma pasta ao dock na tela.

        Os aplicativos adicionados a uma página em uma pasta são dispostos da esquerda para a direita, e na mesma ordem da lista. Se você adicionar mais aplicativos do que uma página comporta, eles serão movidos para outra página.

        - **Nome da pasta**: insira um nome para pasta. Esse nome é mostrado aos usuários nos dispositivos.
        - **Adicionar**: adiciona pastas à página. Além disso, insira as seguintes propriedades:

          - **Nome da página**: insira um nome para a página. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo iOS.
          - **Nome do Aplicativo**: insira um nome para o aplicativo. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo iOS.
          - **ID do Pacote de Aplicativos**: insira a ID do pacote de aplicativos do aplicativo. Confira alguns exemplos em [IDs do lote para aplicativos iOS internos](bundle-ids-built-in-ios-apps.md).

#### <a name="example"></a>Exemplo

No exemplo a seguir, uma nova página chamada **Contoso** é adicionada. A página mostra os aplicativos Buscar Amigos e Ajustes. O aplicativo Ajustes está selecionado para mostrar suas propriedades:

![Exemplo de ajustes na Tela inicial do iOS](./media/ios-device-features-settings/Jc2OxyX.png)

Quando você atribui a política a um iPhone, a página será semelhante à imagem a seguir:

![Dispositivo iOS com Tela inicial modificada](./media/ios-device-features-settings/Bd37PHa.png)

## <a name="app-notifications"></a>Notificações de aplicativos

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Adicionar**: adiciona notificações para aplicativos:

    ![Adicionar notificação do aplicativo no perfil do iOS no Intune](./media/ios-device-features-settings/ios-macos-app-notifications.png)

  - **ID do pacote de aplicativos**: insira a **ID do pacote de aplicativos** do aplicativo que você deseja adicionar. Confira alguns exemplos em [IDs do lote para aplicativos iOS internos](bundle-ids-built-in-ios-apps.md).
  - **Nome do aplicativo**: insira o nome do aplicativo que você deseja adicionar. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo.
  - **Editor**: insira o editor do aplicativo que você está adicionando. Esse nome é usado para sua referência no portal do Azure. Ele *não* aparece no dispositivo.
  - **Notificações**: **habilite** ou **desabilite** o envio de notificações do aplicativo para o dispositivo.
    - **Mostrar no Centro de Notificações**: **Habilitar** permite que o aplicativo mostre as notificações no Centro de Notificações do dispositivo. **Desabilite** para permitir que o aplicativo mostre as notificações no Centro de Notificações.
    - **Mostrar na Tela de Bloqueio**: selecione **Habilitar** para ver as notificações do aplicativo na tela de bloqueio do dispositivo. **Desabilite** para permitir que o aplicativo mostre as notificações na tela de bloqueio.
    - **Tipo de alerta**: quando o dispositivo for desbloqueado, escolha como a notificação é mostrada. Suas opções:
      - **Nenhum**: nenhuma notificação é exibida.
      - **Faixa**: uma faixa aparece brevemente com a notificação.
      - **Modal**: a notificação é exibida e o usuário deve descartá-la manualmente antes de continuar a usar o dispositivo.
    - **Notificação no ícone de aplicativo**: selecione **Habilitar** para adicionar uma notificação ao ícone do aplicativo. A notificação indica que o aplicativo enviou uma notificação.
    - **Sons**: selecione **Habilitar** para tocar um som quando uma notificação for entregue.

## <a name="lock-screen-message"></a>Mensagem da tela de bloqueio

Esse recurso aplica-se a:

- iOS 9.3 e posterior

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Informações de marca do ativo**: insira informações sobre a marca do ativo do dispositivo. Por exemplo, insira `Owned by Contoso Corp` ou `Serial Number: {{serialnumber}}`.

  O texto inserido é mostrado na janela de entrada e na tela de bloqueio do dispositivo.

- **Nota de rodapé de tela de bloqueio**: se o dispositivo for perdido ou roubado, insira uma observação que pode ajudar a reaver o dispositivo. É possível inserir qualquer texto desejado. Por exemplo, insira algo como `If found, call Contoso at ...`.

  Os tokens de dispositivo também podem ser usados para adicionar informações específicas do dispositivo a esses campos. Por exemplo, para mostrar o número de série, insira `Serial Number: {{serialnumber}}`. Na tela de bloqueio, o texto mostra algo semelhante a `Serial Number 123456789ABC`. Ao inserir variáveis, lembre-se de usar chaves `{{ }}`. [Tokens de configuração de aplicativo](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) inclui uma lista das variáveis que podem ser usadas. Use também `deviceName` ou qualquer outro valor específico do dispositivo.

  > [!NOTE]
  > As variáveis não são validadas na interface do usuário e diferenciam maiúsculas de minúsculas. Como resultado, você pode ver perfis salvos com uma entrada incorreta. Por exemplo, se você digitar `{{DeviceID}}` em vez de `{{deviceid}}`, a cadeia de caracteres literal será mostrada no lugar do ID exclusivo do dispositivo. Certifique-se de inserir as informações corretas.

## <a name="single-sign-on"></a>Logon único

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Atributo de nome de usuário do AAD**: o Intune procura esse atributo para cada usuário no Azure AD. Depois, o Intune preenche o respectivo campo (como o UPN) antes de gerar o conteúdo XML instalado no dispositivo. Suas opções:

  - **Nome UPN**: o UPN é analisado da seguinte maneira:

    ![Atributo de nome de usuário](./media/ios-device-features-settings/User-name-attribute.png)

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

## <a name="web-content-filter"></a>Filtro de conteúdo da Web

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Tipo de filtro**: escolha permitir sites específicos. Suas opções:

  - **Configurar URLs**: use o filtro da Web interno da Apple que procura termos adultos, incluindo profanação ou linguagem pornográfica. Esse recurso avalia cada página da web conforme ela é carregada e identifica e bloqueia conteúdo inadequado. Adicione também as URLs que você não deseja verificar usando o filtro. Ou bloqueie URLs específicas, independentemente dos ajustes de filtro da Apple.

    - **URLs permitidas**: **adicione** as URLs que você deseja permitir. Essas URLs ignoram o filtro da Web da Apple.

        > [!NOTE]
        > As URLs inseridas são as URLs que você não quer avaliar com o filtro da Web da Apple. Essas URLs não são uma lista de sites permitidos. Para criar uma lista de sites permitidos, defina o **Tipo de Filtro** como **Somente sites específicos**.

    - **URLs bloqueadas**: **Adicione** as URLs que você deseja parar de abrir, independentemente das configurações de filtro da Web da Apple.

  - **Somente para sites específicos** (somente para o navegador da Web Safari): essas URLs são adicionadas aos indicadores do navegador Safari. O usuário **só** tem permissão para visitar esses sites; nenhum outro site pode ser aberto. Use essa opção somente se você conhecer a lista exata de URLs que os usuários podem acessar.

    - **URL**: insira a URL do site que você deseja permitir. Por exemplo, insira `https://www.contoso.com`.
    - **Caminho do indicador**: a Apple alterou essa configuração. Todos os indicadores vão para a pasta **sites aprovados** . Os indicadores não entram no caminho do indicador que você inserir.
    - **Título**: insira um título descritivo para o indicador.

    Se você não inserir URLs, os usuários finais não poderão acessar nenhum site, exceto `microsoft.com`, `microsoft.net` e `apple.com`. Essas URLs são permitidas automaticamente pelo Intune.

## <a name="single-sign-on-app-extension"></a>Extensão do aplicativo de logon único

Esse recurso aplica-se a:

- iOS 13.0 e posterior
- iPadOS 13,0 e posterior

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a: todos os tipos de registro

- **Tipo de extensão do aplicativo SSO**: escolha o tipo de extensão do aplicativo de SSO de credencial. Suas opções:

  - **Não configurado**: as extensões de aplicativo não são usadas. Para desabilitar uma extensão de aplicativo, você pode alternar o tipo de extensão do aplicativo SSO de **Kerberos** ou **credencial** para **não configurado**.
  - **Credencial**: Use uma extensão de aplicativo de credencial genérica e personalizável para executar o SSO. Certifique-se de que você conhece a ID de extensão para a extensão de aplicativo de SSO da sua organização.
  - **Kerberos**: Use a extensão Kerberos interna da Apple, que está incluída no Ios 13,0 (e mais recente) e iPadOS 13,0 (e mais recente). Essa opção é uma versão específica do Kerberos da extensão do aplicativo de **credencial** .

  > [!TIP]
  > Com o tipo de **credencial** , você adiciona seus próprios valores de configuração para passar pela extensão. Em vez disso, considere o uso de definições de configuração internas fornecidas pela Apple no tipo **Kerberos** .

- **ID da extensão** (somente credencial): Insira o identificador do pacote que identifica a extensão do aplicativo SSO, como `com.apple.extensiblesso`.
- **ID da equipe** (somente credencial): Insira o identificador de equipe de sua extensão de aplicativo SSO. Um identificador de equipe é uma cadeia de caracteres alfanuméricos de 10 caracteres (números e letras) gerada pela Apple, como `ABCDE12345`. A ID da equipe não é necessária.

  [Localize sua ID de equipe](https://help.apple.com/developer-account/#/dev55c3c710c) (abre o site da Apple) tem mais informações.

- **Realm**: Insira o nome do seu realm Kerberos. O nome do Realm deve estar em letras maiúsculas, como `CONTOSO.COM`. Normalmente, o nome do realm é o mesmo que o nome de domínio DNS, mas em letras maiúsculas.

- **Domínios**: Insira os nomes de domínio ou host dos sites que podem autenticar por meio do SSO. Por exemplo, se seu site for `mysite.contoso.com`, `mysite` será o nome do host e `contoso.com` será o nome de domínio. Quando os usuários se conectam a qualquer um desses sites, a extensão do aplicativo trata do desafio de autenticação. Essa autenticação permite que os usuários usem ID de face, Touch ID ou Apple pincode/senha para entrar.

  - Todos os domínios em sua extensão de aplicativo de logon único os perfis do Intune devem ser exclusivos. Não é possível repetir um domínio em nenhum perfil de extensão de aplicativo de logon, mesmo se você estiver usando tipos diferentes de extensões de aplicativo SSO.
  - Esses domínios não diferenciam maiúsculas de minúsculas.

- **Configuração adicional** (somente credencial): Insira dados específicos de extensão adicionais a serem passados para a extensão do aplicativo SSO:
  - **Chave de configuração**: Insira o nome do item que você deseja adicionar, como `user name`.
  - **Tipo de valor**: Insira o tipo de dados. Suas opções:

    - Cadeia de caracteres
    - Booliano: no **valor de configuração**, insira `True` ou `False`.
    - Inteiro: no **valor de configuração**, insira um número.
    
  - **Valor de configuração**: Insira os dados.

  - **Adicionar**: Selecione para adicionar suas chaves de configuração.

- **Uso** do conjunto de chaves (somente Kerberos): escolha **Bloquear** para impedir que as senhas sejam salvas e armazenadas no conjunto de chaves. **Não configurado** (padrão) permite que as senhas sejam salvas e armazenadas no conjunto de chaves.
- **ID de face, ID de toque ou senha** (somente Kerberos): **exigir** força os usuários a inserir sua ID de face, Touch ID ou senha da Apple para entrar nos domínios que você adicionou. **Não configurado** (padrão) não exige que os usuários usem a biometria ou a senha para entrar.
- **Realm padrão** (somente Kerberos): escolha **habilitar** para definir o valor de **Realm** que você inseriu como o realm padrão. **Não configurado** (padrão) não define um realm padrão.

  > [!TIP]
  > - **Habilite** essa configuração se você estiver configurando várias extensões de aplicativo SSO do Kerberos em sua organização.
  > - **Habilite** essa configuração se você estiver usando vários territórios. Ele define o valor de **Realm** que você inseriu como o realm padrão.
  > - Se você tiver apenas um Realm, deixe-o **não configurado** (padrão).

- **Nome da entidade de segurança** (somente Kerberos): Insira o nome de usuário da entidade de segurança Kerberos. Você não precisa incluir o nome do realm. Por exemplo, em `user@contoso.com`, `user` é o nome principal e `contoso.com` é o nome do realm.
- **Active Directory código do site** (somente Kerberos): Insira o nome do site do Active Directory que a extensão Kerberos deve usar. Talvez não seja necessário alterar esse valor, pois a extensão Kerberos pode localizar automaticamente o Active Directory código do site.
- **Nome do cache** (somente Kerberos): Insira o nome GSS (Generic Security Services) do cache Kerberos. É mais provável que você não precise definir esse valor.
- **IDs de pacote de aplicativo** (somente Kerberos): **adicione** os identificadores de pacote de aplicativo que devem usar o logon único em seus dispositivos. Esses aplicativos recebem acesso ao tíquete de concessão de tíquete Kerberos, ao tíquete de autenticação e autenticam usuários para serviços que eles estão autorizados a acessar.
- **Mapeamento de realm de domínio** (somente Kerberos): **adicione** os sufixos DNS de domínio que devem ser mapeados para seu Realm. Use essa configuração quando os nomes DNS dos hosts não corresponderem ao nome do realm. É mais provável que você não precise criar esse mapeamento de domínio para Realm personalizado.

## <a name="wallpaper"></a>Papel de parede

Você pode enfrentar um comportamento inesperado quando um perfil sem nenhuma imagem é atribuído a dispositivos com uma imagem existente. Por exemplo, você pode criar um perfil sem uma imagem. Este perfil é atribuído a dispositivos que já têm uma imagem. Nesse cenário, a imagem pode ser alterada para o padrão do dispositivo ou a imagem original pode permanecer no dispositivo. Esse comportamento é controlado e limitado pela plataforma de MDM da Apple.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a: registro de dispositivo automatizado (supervisionado)

- **Localização de Exibição de Papel de Parede**: escolha uma localização no dispositivo para mostrar a imagem. Suas opções:
  - **Não configurado**: uma imagem personalizada não é adicionada ao dispositivo. O dispositivo usa o sistema operacional padrão.
  - **Tela de bloqueio**: adiciona a imagem à tela de bloqueio.
  - **Tela inicial**: adiciona a imagem à tela inicial.
  - **Tela de bloqueio e tela inicial do**: usa a mesma imagem na tela de bloqueio e na tela inicial.
- **Imagem de papel de parede**: carregue uma imagem .png, .jpg ou .jpeg que você quer usar. Verifique se o tamanho do arquivo é menor do que 750 KB. Você também pode **remover** uma imagem adicionada.

> [!TIP]
> Para exibir imagens diferentes na tela de bloqueio e na tela inicial, crie um perfil com a imagem de tela de bloqueio. Crie outro perfil com a imagem de tela inicial. Atribua os dois perfis aos seus grupos de usuários ou dispositivos iOS.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](../device-profile-assign.md) e [monitorar seu status](../device-profile-monitor.md).

Você também pode criar perfis de recurso do dispositivo para dispositivos [macOS](macos-device-features-settings.md).
