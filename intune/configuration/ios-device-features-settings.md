---
title: Configurações dos recursos de dispositivos iOS/iPadOS no Microsoft Intune – Azure | Microsoft Docs
description: Veja todas as configurações de AirPrint, layout da tela inicial, notificações de aplicativo, dispositivos compartilhados, conexão única e filtro de conteúdo da Web que podem ser definidas para dispositivos iOS e iPadOS no Microsoft Intune. Use essas configurações em um perfil de configuração de dispositivo para configurar dispositivos iOS/iPadOS e usar esses recursos da Apple em sua organização.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
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
ms.openlocfilehash: 7f19ccfb6949dbfa0de62a8b711436ab9cde8c9c
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512935"
---
# <a name="ios-and-ipados-device-settings-to-use-common-iosipados-features-in-intune"></a>Configurações de dispositivos iOS e iPadOS para usar recursos comuns do iOS/iPadOS no Intune

O Intune inclui algumas configurações internas que permitem que os usuários do iOS/iPadOS utilizem diferentes recursos da Apple em seus dispositivos. Por exemplo, os administradores podem controlar como os usuários do iOS/iPadOS utilizam impressoras AirPrint, adicionam aplicativos e pastas ao encaixe e às páginas na tela inicial, mostram notificações de aplicativo, mostram detalhes da marca de ativo na tela de bloqueio, usam a autenticação de logon único e autenticam usuários com certificados.

Use esses recursos para controlar dispositivos iOS/iPadOS como parte de sua solução de MDM (gerenciamento de dispositivo móvel).

Este artigo lista essas configurações e descreve o que cada uma faz. Para obter mais informações sobre esses recursos, acesse [Adicionar configurações de recurso do dispositivo iOS/iPadOS ou macOS](../device-features-configure.md).

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração de dispositivo iOS/iPadOS](../device-features-configure.md).

> [!NOTE]
> Essas configurações se aplicam a diferentes tipos de registro, com algumas configurações sendo aplicadas a todas as opções de registro. Para obter mais informações sobre os diferentes tipos de registro, confira [Registro do iOS/iPadOS](../ios-enroll.md).

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a(o): Todos os tipos de registro

> [!NOTE]
> Adicione todas as impressoras ao mesmo perfil. A Apple impede que vários perfis do AirPrint tenham como alvo o mesmo dispositivo.

- **Endereço IP**: Insira o endereço IPv4 ou IPv6 da impressora. Se você usar nomes de host para identificar as impressoras, obtenha o endereço IP ao executar o ping da impressora no terminal. Obter o endereço IP e o caminho (neste artigo) fornece mais detalhes.
- **Caminho**: Geralmente, o caminho é `ipp/print` para impressoras na rede. Obter o endereço IP e o caminho (neste artigo) fornece mais detalhes.
- **Porta**: Insira a porta de escuta do destino do AirPrint. Se você deixar essa propriedade em branco, o AirPrint usará a porta padrão. Disponível no iOS 11.0+ e no iPadOS 13.0+.
- **TLS**: Escolha **Habilitar** para proteger as conexões do AirPrint com o protocolo TLS. Disponível no iOS 11.0+ e no iPadOS 13.0+.

Para adicionar servidores do AirPrint, você pode:

- **Adicionar** adiciona o servidor do AirPrint à lista. Vários servidores do AirPrint podem ser adicionados.
- **Importar** um arquivo .csv (separado por vírgula) com essas informações. Ou **Exportar** para criar uma lista dos servidores do AirPrint que você adicionou.

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

- iOS 9.3 ou mais recente
- iPadOS 13.0 e versões mais recentes

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

### <a name="dock"></a>Dock

Use as configurações de **Encaixe** para adicionar até seis itens ou pastas ao encaixe na tela do iOS/iPadOS. Muitos dispositivos dão suporte a menos itens. Por exemplo, iPhones dão suporte a até quatro itens. Nesse caso, só os primeiros quatro itens adicionados aparecerão no dispositivo.

Você pode adicionar até **seis** itens (aplicativos e pastas combinados) ao dock do dispositivo.

- **Adicionar**: adiciona aplicativos ou pastas ao dock no dispositivo.
- **Tipo**: Adicionar um **aplicativo** ou uma **pasta**:

  - **Aplicativo**: Escolha esta opção para adicionar aplicativos ao dock na tela. Insira:

    - **Nome do Aplicativo**: insira um nome para o aplicativo. Esse nome é usado para sua referência no centro de administração do Microsoft Endpoint Manager. Ele *não* aparece no dispositivo iOS/iPadOS.
    - **ID de Lote de Aplicativo**: Insira a ID do pacote do aplicativo. Confira alguns exemplos em [IDs de pacote para aplicativos iOS/iPadOS internos](bundle-ids-built-in-ios-apps.md).

  - **Pasta**: Escolha esta opção para adicionar uma pasta ao dock na tela.

    Os aplicativos adicionados a uma página em uma pasta são dispostos da esquerda para a direita, e na mesma ordem da lista. Se você adicionar mais aplicativos do que uma página comporta, eles serão movidos para outra página.

    - **Nome da pasta**: insira o nome do aplicativo. Esse nome é exibido aos usuários em seus dispositivos.
    - **Lista de páginas**: **Adicione** uma página e insira as seguintes propriedades:

      - **Nome da página**: Insira um nome para a página. Esse nome é usado para sua referência no centro de administração do Microsoft Endpoint Manager. Ele *não* aparece no dispositivo iOS/iPadOS.
      - **Nome do Aplicativo**: insira um nome para o aplicativo. Esse nome é usado para sua referência no centro de administração do Microsoft Endpoint Manager. Ele *não* aparece no dispositivo iOS/iPadOS.
      - **ID de Lote de Aplicativo**: Insira a ID do pacote do aplicativo. Confira alguns exemplos em [IDs de pacote para aplicativos iOS/iPadOS internos](bundle-ids-built-in-ios-apps.md).

      Você pode adicionar até **20** páginas para o dock do dispositivo.

> [!NOTE]
> Quando você adiciona ícones usando as configurações de Encaixe, os ícones na Tela Inicial e páginas estão bloqueados e não podem ser movidos. Isso pode ser feito por design com as políticas de MDM do iOS/iPadOS e da Apple.

#### <a name="example"></a>Exemplo

No exemplo a seguir, a tela do dock mostra apenas os aplicativos Safari, Mail e Bolsa. O aplicativo Mail está selecionado para mostrar suas propriedades:

![Exemplo de configurações de encaixe do iOS/iPadOS](./media/ios-device-features-settings/FfFiUcP.png)

Quando você atribui a política a um iPhone, o dock será semelhante à imagem a seguir:

![Exemplo de layout de encaixe do iOS/iPadOS no iPhone](./media/ios-device-features-settings/bAgCe8F.png)

### <a name="pages"></a>Páginas

Adicione as páginas que você deseja exibir na tela inicial, e os aplicativos que aparecerão em cada página. Os aplicativos adicionados a uma página são dispostos da esquerda para a direita, na mesma ordem da lista. Se você adicionar mais aplicativos do que uma página comporta, eles serão movidos para outra página.

> [!TIP]
> Para reorganizar itens em quaisquer listas de páginas e na Tela inicial, arraste e solte-os.

Você pode adicionar até **40** páginas em um dispositivo.

- **Lista de páginas**: **Adicione** uma página e insira as seguintes propriedades:

  - **Nome da página**: Insira um nome para a página. Esse nome é usado para sua referência no centro de administração do Microsoft Endpoint Manager e *não* é mostrado no dispositivo iOS/iPadOS.

  Você pode adicionar até **60** itens (aplicativos e a pasta combinados) em um dispositivo.

  - **Adicionar**: adiciona aplicativos ou pastas a uma página no dispositivo.

    - **Tipo**: Adicionar um **aplicativo** ou uma **pasta**:

      - **Aplicativo**: Escolha esta opção para adicionar aplicativos a uma página na tela. Insira também:

        - **Nome do Aplicativo**: insira um nome para o aplicativo. Esse nome é usado para sua referência no centro de administração do Microsoft Endpoint Manager. Ele *não* aparece no dispositivo iOS/iPadOS.
        - **ID de Lote de Aplicativo**: Insira a ID do pacote do aplicativo. Confira alguns exemplos em [IDs de pacote para aplicativos iOS/iPadOS internos](bundle-ids-built-in-ios-apps.md).

      - **Pasta**: Escolha esta opção para adicionar uma pasta ao dock na tela.

        Os aplicativos adicionados a uma página em uma pasta são dispostos da esquerda para a direita, e na mesma ordem da lista. Se você adicionar mais aplicativos do que uma página comporta, eles serão movidos para outra página.

        - **Nome da pasta**: insira um nome para a pasta. Esse nome é mostrado aos usuários nos dispositivos.
        - **Adicionar**: adiciona páginas à pasta. Além disso, insira as seguintes propriedades:

          - **Nome da página**: Insira um nome para a página. Esse nome é usado para sua referência no centro de administração do Microsoft Endpoint Manager. Ele *não* aparece no dispositivo iOS/iPadOS.
          - **Nome do Aplicativo**: insira um nome para o aplicativo. Esse nome é usado para sua referência no centro de administração do Microsoft Endpoint Manager. Ele *não* aparece no dispositivo iOS/iPadOS.
          - **ID de Lote de Aplicativo**: Insira a ID do pacote do aplicativo. Confira alguns exemplos em [IDs de pacote para aplicativos iOS/iPadOS internos](bundle-ids-built-in-ios-apps.md).

#### <a name="example"></a>Exemplo

No exemplo a seguir, uma nova página chamada **Contoso** é adicionada. A página mostra os aplicativos Buscar Amigos e Ajustes. O aplicativo Ajustes está selecionado para mostrar suas propriedades:

![Exemplo de configurações da tela inicial do iOS/iPadOS no Intune](./media/ios-device-features-settings/Jc2OxyX.png)

Quando você atribui a política a um iPhone, a página será semelhante à imagem a seguir:

![Dispositivo iOS/iPadOS com a tela inicial modificada no Intune](./media/ios-device-features-settings/Bd37PHa.png)

## <a name="app-notifications"></a>Notificações de aplicativos

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Adicionar**: Adicione notificações para aplicativos:

    ![Adicionar notificação do aplicativo no perfil do iOS/iPadOS no Intune](./media/ios-device-features-settings/ios-macos-app-notifications.png)

  - **ID de lote de aplicativo**: Insira **ID de Lote de Aplicativos** do aplicativo que você deseja adicionar. Confira alguns exemplos em [IDs de pacote para aplicativos iOS/iPadOS internos](bundle-ids-built-in-ios-apps.md).
  - **Nome do aplicativo**: Insira o nome do aplicativo que você deseja adicionar. Esse nome é usado para sua referência no centro de administração do Microsoft Endpoint Manager. Ele *não* aparece no dispositivo.
  - **Editor**: Insira o editor do aplicativo que você está adicionando. Esse nome é usado para sua referência no centro de administração do Microsoft Endpoint Manager. Ele *não* aparece no dispositivo.
  - **Notificações**: **habilite** ou **desabilite** o envio de notificações do aplicativo para o dispositivo.
    - **Mostrar no Centro de Notificação**: **habilite** para permitir que o aplicativo mostre as notificações no Centro de Notificações do dispositivo. **Desabilite** para permitir que o aplicativo mostre as notificações no Centro de Notificações.
    - **Mostrar na tela de bloqueio**: selecione **Habilitar** para ver as notificações do aplicativo na tela de bloqueio do dispositivo. **Desabilite** para permitir que o aplicativo mostre as notificações na tela de bloqueio.
    - **Tipo de alerta**: quando o dispositivo for desbloqueado, escolha como a notificação é mostrada. Suas opções:
      - **Nenhum**: Nenhuma notificação é exibida.
      - **Faixa**: uma faixa aparece brevemente com a notificação.
      - **Modal**: a notificação é exibida e o usuário deve descartá-la manualmente antes de continuar a usar o dispositivo.
    - **Notificação no ícone do aplicativo**: selecione **Habilitar** para adicionar uma notificação ao ícone do aplicativo. A notificação indica que o aplicativo enviou uma notificação.
    - **Sons**: selecione **Habilitar** para tocar um som quando uma notificação for entregue.

## <a name="lock-screen-message"></a>Mensagem da tela de bloqueio

Esse recurso aplica-se a:

- iOS 9.3 e posterior
- iPadOS 13.0 e versões mais recentes

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Informações da tag do ativo**: Insira informações sobre a tag do ativo do dispositivo. Por exemplo, insira `Owned by Contoso Corp` ou `Serial Number: {{serialnumber}}`.

  O texto inserido é mostrado na janela de entrada e na tela de bloqueio do dispositivo.

- **Nota de rodapé da tela de bloqueio**: Em caso de perda ou roubo do dispositivo, insira uma observação que pode ajudar na devolução do dispositivo. É possível inserir qualquer texto desejado. Por exemplo, insira algo como `If found, call Contoso at ...`.

  Os tokens de dispositivo também podem ser usados para adicionar informações específicas do dispositivo a esses campos. Por exemplo, para mostrar o número de série, insira `Serial Number: {{serialnumber}}`. Na tela de bloqueio, o texto mostra algo semelhante a `Serial Number 123456789ABC`. Ao inserir variáveis, lembre-se de usar chaves `{{ }}`. [Tokens de configuração de aplicativo](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) inclui uma lista das variáveis que podem ser usadas. Use também `deviceName` ou qualquer outro valor específico do dispositivo.

  > [!NOTE]
  > As variáveis não são validadas na interface do usuário e diferenciam maiúsculas de minúsculas. Como resultado, você pode ver perfis salvos com uma entrada incorreta. Por exemplo, se você digitar `{{DeviceID}}` em vez de `{{deviceid}}`, a cadeia de caracteres literal será mostrada no lugar do ID exclusivo do dispositivo. Insira as informações corretas.

## <a name="single-sign-on"></a>Logon único

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): registro de dispositivo, registro de dispositivo automatizado (supervisionado)

- **Atributo de nome de usuário do AAD**: o Intune procura esse atributo para cada usuário no Azure AD. Depois, o Intune preenche o respectivo campo (como o UPN) antes de gerar o conteúdo XML instalado no dispositivo. Suas opções:

  - **Nome principal do usuário**: o UPN é analisado da seguinte maneira:

    ![Atributo de SSO do nome de usuário do iOS/iPadOS no Intune](./media/ios-device-features-settings/User-name-attribute.png)

    Você também pode substituir o realm pelo texto inserido na caixa de texto **Realm**.

    Por exemplo, Contoso tem várias regiões, incluindo Europa, Ásia e América do Norte. A Contoso deseja que os usuários na Ásia usem o SSO, e o aplicativo exige o UPN no formato `username@asia.contoso.com`. Quando você seleciona **Nome UPN**, o realm de cada usuário é obtido do Azure AD, que é `contoso.com`. Portanto, para os usuários na Ásia, selecione **nome UPN** e insira `asia.contoso.com`. O UPN do usuário final se torna `username@asia.contoso.com`, em vez de `username@contoso.com`.

  - **ID de dispositivo do Intune**: o Intune seleciona automaticamente a ID do Dispositivo Intune.

    Por padrão, aplicativos precisam usar somente a ID do dispositivo. Porém, se o aplicativo usar o realm e a ID do dispositivo, você poderá digitar o realm na caixa de texto Realm.

    > [!NOTE]
    > Por padrão, mantenha o realm vazio se você usar a ID do dispositivo.

  - **Id do dispositivo do Azure AD**

- **Realm**: insira a parte do domínio da URL. Por exemplo, insira `contoso.com`.
- **Prefixos de URL que usarão Logon Único**: **adicione** quaisquer URLs em sua organização que exijam autenticação de logon único do usuário.

  Por exemplo, quando um usuário se conecta a qualquer um desses sites, o dispositivo iOS/iPadOS usa as credenciais de logon único. O usuário não precisa inserir credenciais adicionais. No entanto, se a autenticação multifator estiver habilitada, os usuários deverão inserir a segunda autenticação.

  > [!NOTE]
  > Essas URLs devem ter FQDN corretamente formatado. A Apple exige que estejam no formato `http://<yourURL.domain>`.

  Os padrões de correspondência de URL devem começar com um `http://` ou `https://`. Uma correspondência de cadeia de caracteres simples é executada, de modo que o prefixo da URL `http://www.contoso.com/` não corresponda a `http://www.contoso.com:80/`. Com o iOS 10.0+ e o iPadOS 13.0+, um curinga \* pode ser usado para inserir todos os valores correspondentes. Por exemplo, `http://*.contoso.com/` corresponde tanto a `http://store.contoso.com/` quanto a `http://www.contoso.com`.

  Os padrões `http://.com` e `https://.com` correspondem a todas as URLs HTTP e HTTPS, respectivamente.

- **Aplicativos que usarão o Logon Único**: **adicione** aplicativos em dispositivos dos usuários finais que podem usar o logon único.

  A matriz `AppIdentifierMatches` deve incluir cadeias de caracteres que correspondam a IDs de lote de aplicativo. Essas cadeias de caracteres podem ser correspondências exatas (como `com.contoso.myapp`), ou insira uma correspondência de prefixo na ID de lote usando o caractere curinga \*. O caractere curinga deve aparecer após um caractere de ponto (.) e pode aparecer apenas uma vez, no final da cadeia de caracteres, como `com.contoso.*`. Quando um caractere curinga for incluído, qualquer aplicativo cuja ID do pacote comece com o prefixo receberá acesso à conta.

  Use **Nome do Aplicativo** para inserir um nome amigável para ajudá-lo a identificar a ID do pacote.

- **Certificado de renovação de credencial**: Se estiver usando certificados para autenticação (não senhas), selecione o certificado SCEP ou PFX existente como o certificado de autenticação. Normalmente, esse é o mesmo certificado implantado para o usuário para outros perfis, como VPN, Wi-Fi ou email.

## <a name="web-content-filter"></a>Filtro de conteúdo da Web

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Tipo de filtro**: escolha permitir sites específicos. Suas opções:

  - **Configurar URLs**: use o filtro da Web interno da Apple que procura termos adultos, incluindo profanação ou linguagem pornográfica. Esse recurso avalia cada página da web conforme ela é carregada e identifica e bloqueia conteúdo inadequado. Adicione também as URLs que você não deseja verificar usando o filtro. Ou bloqueie URLs específicas, independentemente dos ajustes de filtro da Apple.

    - **URLs permitidas**: **Adicione** as URLs que você deseja permitir. Essas URLs ignoram o filtro da Web da Apple.

        > [!NOTE]
        > As URLs inseridas são as URLs que você não quer avaliar com o filtro da Web da Apple. Essas URLs não são uma lista de sites permitidos. Para criar uma lista de sites permitidos, defina o **Tipo de Filtro** como **Somente sites específicos**.

    - **URLs bloqueadas**: **Adicione** as URLs que você deseja parar de abrir, independentemente das configurações de filtro da Web da Apple.

  - **Somente sites específicos** (apenas para o navegador Safari): Essas URLs são adicionadas aos Favoritos do navegador Safari. O usuário **só** tem permissão para visitar esses sites; nenhum outro site pode ser aberto. Use essa opção somente se você conhecer a lista exata de URLs que os usuários podem acessar.

    - **URL**: insira a URL do site que você deseja permitir. Por exemplo, insira `https://www.contoso.com`.
    - **Caminho do Indicador**: a Apple alterou esta configuração. Todos os indicadores vão para a pasta **Sites Aprovados**. Os indicadores não vão para o caminho de indicador que você inserir.
    - **Título**: insira um título descritivo para o indicador.

    Se você não inserir URLs, os usuários finais não poderão acessar nenhum site, exceto `microsoft.com`, `microsoft.net` e `apple.com`. Essas URLs são permitidas automaticamente pelo Intune.

## <a name="single-sign-on-app-extension"></a>Extensão do aplicativo de logon único

Esse recurso aplica-se a:

- iOS 13.0 e posterior
- iPadOS 13.0 e posterior

### <a name="settings-apply-to-all-enrollment-types"></a>As configurações se aplicam a(o): Todos os tipos de registro

- **Tipo de extensão de aplicativo de SSO**: escolha o tipo de extensão de aplicativo de SSO. Suas opções:

  - **Não configurado**: as extensões de aplicativo não são usadas. Para desabilitar uma extensão de aplicativo, você pode alterar o tipo de extensão do aplicativo de SSO para **Não configurado**.
  - **Redirecionar**: use uma extensão de aplicativo de redirecionamento genérica e personalizável para executar o SSO com fluxos de autenticação modernos. Você precisa saber a ID da extensão de aplicativo de sua organização.
  - **Credencial**: use uma extensão de aplicativo de credencial genérica e personalizável para fazer o SSO com fluxos de autenticação de desafio e resposta. Você precisa saber a ID da extensão de aplicativo de sua organização.
  - **Kerberos**: use a extensão Kerberos interna da Apple, que está incluída no iOS 13.0+ e no iPadOS 13.0+. Essa opção é uma versão específica para Kerberos da extensão do aplicativo de **Credencial**.

  > [!TIP]
  > Com os tipos **Redirecionamento** e **Credencial**, você adiciona seus próprios valores de configuração para passar pela extensão. Se você estiver usando **Credencial**, considere usar definições de configuração internas fornecidas pela Apple no tipo **Kerberos**.

- **ID da extensão** (Redirecionamento e Credencial): insira o identificador do pacote que identifica a extensão do aplicativo de SSO, como `com.apple.extensiblesso`.

- **ID da equipe** (Redirecionamento e Credencial): insira o identificador de equipe da extensão do aplicativo de SSO. Um identificador de equipe é uma cadeia de caracteres alfanuméricos (números e letras) de 10 caracteres gerada pela Apple, como `ABCDE12345`. A ID da equipe não é necessária.

  [Localizar sua ID da equipe](https://help.apple.com/developer-account/#/dev55c3c710c) (abre o site da Apple) tem mais informações.

- **Realm** (Credencial e Kerberos): insira o nome do seu realm de autenticação. O nome de realm deve estar em letras maiúsculas, como `CONTOSO.COM`. Normalmente, o nome de realm é igual ao nome de domínio DNS, mas em letras maiúsculas.

- **Domínios** (Credencial e Kerberos): insira os nomes de domínio ou de host dos sites que podem ser autenticados por meio do SSO. Por exemplo, se seu site for `mysite.contoso.com`, `mysite` será o nome do host e `contoso.com` será o nome de domínio. Quando os usuários se conectam a qualquer um desses sites, a extensão do aplicativo cuida do desafio de autenticação. Essa autenticação permite que os usuários usem Face ID, Touch ID ou PIN/senha da Apple para entrar.

  - Todos os domínios em sua extensão de aplicativo de logon único em perfis do Intune devem ser exclusivos. Não é possível repetir um domínio em nenhum perfil de extensão de aplicativo de logon, mesmo se você estiver usando tipos diferentes de extensões de aplicativo SSO.
  - Esses domínios não diferenciam maiúsculas de minúsculas.

- **URLs** (somente Redirecionamento): insira os prefixos de URL de seus provedores de identidade em cujo nome a extensão do aplicativo de redirecionamento faz o SSO. Quando um usuário é redirecionado para essas URLs, a extensão do aplicativo de SSO será intermediária e avisará o SSO.

  - Todas as URLs em seus perfis de extensão do aplicativo de logon único do Intune devem ser exclusivas. Não é possível repetir um domínio em nenhum perfil de extensão do aplicativo de SSO, mesmo que você esteja usando tipos diferentes de extensões do aplicativo de SSO.
  - As URLs devem começar com http:// ou https://.

- **Configuração adicional** (Redirecionamento e Credencial): insira dados específicos de extensão adicionais a serem passados para a extensão do aplicativo de SSO:
  - **Chave**: insira o nome do item que você deseja adicionar, como `user name`.
  - **Tipo**: insira o tipo de dados. Suas opções:

    - Cadeia de caracteres
    - Booliano: em **Valor de configuração**, insira `True` ou `False`.
    - Inteiro: em **Valor de configuração**, insira um número.
    
  - **Valor**: insira os dados.

  - **Adicionar**: selecione para adicionar suas chaves de configuração.

- **Uso do conjunto de chaves** (somente Kerberos): escolha **Bloquear** para impedir que as senhas sejam salvas e armazenadas no conjunto de chaves. **Não configurado** (padrão) permite que as senhas sejam salvas e armazenadas no conjunto de chaves.
- **Face ID, Touch ID ou senha** (somente Kerberos): **Exigir** força os usuários a inserir Face ID, Touch ID ou senha da Apple para entrar nos domínios que você adicionou. **Não configurado** (padrão) não exige que os usuários usem a biometria ou a senha para entrar.
- **Realm padrão** (somente Kerberos): escolha **Habilitar** para definir o valor de **Realm** que você inseriu como o realm padrão. **Não configurado** (padrão) não define um realm padrão.

  > [!TIP]
  > - **Habilite** essa configuração se você estiver configurando várias extensões de aplicativo de SSO do Kerberos em sua organização.
  > - **Habilite** essa configuração se você estiver usando vários realms. Ela define o valor de **Realm** que você inseriu como o realm padrão.
  > - Se você tiver apenas um realm, deixe-o **Não configurado** (padrão).

- **Nome da entidade de segurança** (somente Kerberos): insira o nome de usuário da entidade de segurança do Kerberos. Você não precisa incluir o nome de realm. Por exemplo, em `user@contoso.com`, `user` é o nome da entidade de segurança e `contoso.com` é o nome de realm.

  > [!TIP]
  > - Você também pode usar variáveis no nome da entidade de segurança. Basta inserir chaves `{{ }}`. Por exemplo, para mostrar o nome de usuário, insira `Username: {{username}}`. 
  > - No entanto, tenha cuidado com a substituição de variáveis, porque as variáveis não são validadas na interface do usuário e diferenciam maiúsculas de minúsculas. Insira as informações corretas.

- **Código do site do Active Directory** (somente Kerberos): insira o nome do site do Active Directory que a extensão do Kerberos deve usar. Talvez não seja necessário alterar esse valor, pois a extensão do Kerberos pode localizar automaticamente o código do site do Active Directory.
- **Nome do cache** (somente Kerberos): insira o nome GSS (Generic Security Services) do cache do Kerberos. É mais provável que você não precise definir esse valor.
- **IDs do pacote de aplicativo** (somente Kerberos): **adicione** os identificadores do pacote de aplicativo que devem usar o logon único em seus dispositivos. Esses aplicativos recebem acesso ao tíquete de concessão de tíquete do Kerberos e ao tíquete de autenticação. Também autenticam usuários para serviços que eles estão autorizados a acessar.
- **Mapeamento de realm de domínio** (somente Kerberos): **adicione** os sufixos DNS de domínio que devem ser mapeados para seu realm. Use essa configuração quando os nomes DNS dos hosts não corresponderem ao nome de realm. É mais provável que você não precise criar esse mapeamento de domínio personalizado para realm.
- **Certificado PKINIT** (somente Kerberos): **selecione** o certificado PKINIT (criptografia por chave pública para autenticação inicial) que pode ser usado para autenticação do Kerberos. Você pode escolher entre os certificados [PKCS](../protect/certficates-pfx-configure.md) ou [SCEP](../protect/certificates-scep-configure.md) que adicionou no Intune. Para obter mais informações sobre certificados, consulte [usar certificados para autenticação no Microsoft Intune](../protect/certificates-configure.md).

## <a name="wallpaper"></a>Papel de parede

Você pode enfrentar um comportamento inesperado quando um perfil sem nenhuma imagem é atribuído a dispositivos com uma imagem existente. Por exemplo, você pode criar um perfil sem uma imagem. Este perfil é atribuído a dispositivos que já têm uma imagem. Nesse cenário, a imagem pode ser alterada para o padrão do dispositivo ou a imagem original pode permanecer no dispositivo. Esse comportamento é controlado e limitado pela plataforma de MDM da Apple.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>As configurações se aplicam a(o): Registro de dispositivo automatizado (supervisionado)

- **Local de exibição do papel de parede**: escolha um local no dispositivo para mostrar a imagem. Suas opções:
  - **Não configurado**: Uma imagem personalizada não é adicionada ao dispositivo. O dispositivo usa o sistema operacional padrão.
  - **Tela de bloqueio**: adiciona a imagem à tela de bloqueio.
  - **Tela inicial**: adiciona a imagem à tela inicial.
  - **Tela de bloqueio e Tela inicial**: usa a mesma imagem na tela de bloqueio e na tela inicial.
- **Imagem de papel de parede**: carregue uma imagem .png, .jpg ou .jpeg que você quer usar. Verifique se o tamanho do arquivo é menor do que 750 KB. Você também pode **remover** uma imagem adicionada.

> [!TIP]
> Para exibir imagens diferentes na tela de bloqueio e na tela inicial, crie um perfil com a imagem de tela de bloqueio. Crie outro perfil com a imagem de tela inicial. Atribua os dois perfis aos seus grupos de usuários ou dispositivos iOS/iPadOS.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](../device-profile-assign.md) e [monitorar seu status](../device-profile-monitor.md).

Você também pode criar perfis de recurso do dispositivo para dispositivos [macOS](macos-device-features-settings.md).
