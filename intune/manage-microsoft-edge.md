---
title: Gerenciar o Microsoft Edge para iOS e Android com o Intune
titleSuffix: ''
description: Use as políticas de Proteção de Aplicativo do Intune com o Microsoft Edge para garantir que sites corporativos sempre sejam acessados com proteções em vigor.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3fb2f050-ec94-42ab-be05-c3d4101148bb
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8ec1af80d52a8331c2bef136cd0947b81beaa3ea
ms.sourcegitcommit: b1ddc7f4a3d520b7d6755c7a423a46d1e2548592
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69651166"
---
# <a name="manage-web-access-by-using-microsoft-edge-with-microsoft-intune"></a>Gerenciar o acesso via Web usando o Microsoft Edge com o Microsoft Intune

Usar as políticas de proteção de aplicativo do Intune com o Microsoft Edge ajuda a garantir que sites corporativos sempre sejam acessados com as proteções em vigor. Os seguintes recursos corporativos do Microsoft Edge habilitados pelas políticas do Intune estão disponíveis:

- **Identidade Dupla.** Os usuários podem adicionar uma conta corporativa e uma conta pessoal para navegação. Há uma separação completa entre as duas identidades, o que é semelhante à arquitetura e a experiência no Office 365 e no Outlook. Os administradores do Intune poderão definir as políticas desejadas para uma experiência de navegação protegida dentro da conta de trabalho.
- **Integração de política de proteção de aplicativo do Intune.** Como o Microsoft Edge está integrado ao SDK do Intune, é possível aplicar políticas de proteção de aplicativo para protegê-los contra a perda de dados. Essas funcionalidades incluem controlar os recursos de recortar, copiar e colar, impedir capturas de tela e garantir que os links selecionados pelo usuário sejam abertos apenas em outros aplicativos gerenciados.
- **Integração de Proxy do Aplicativo Azure.** Possibilita controlar o acesso a aplicativos SaaS (software como serviço) e a aplicativos Web. Isso ajuda a garantir que somente aplicativos baseados em navegador sejam executados no navegador seguro Microsoft Edge, mesmo se os usuários finais se conectarem na rede corporativa ou na Internet.
- **Configuração de aplicativo.** Você pode usar as definições de configuração de aplicativo para fortalecer a postura de segurança da sua organização e configurar recursos fáceis de usar para seus usuários finais. Por exemplo, é possível definir indicadores, um atalho da home page, sites permitidos ou bloqueados e o Proxy do Aplicativo Azure AD (Azure Active Directory).

As políticas de proteção do Microsoft Intune para o Microsoft Edge ajudam a proteger os dados e recursos da sua organização. O uso dessas políticas com o Microsoft Edge garante que os recursos da sua empresa sejam protegidos não apenas dentro de aplicativos instalados nativamente, mas também quando forem acessados pelo navegador da Web.

## <a name="getting-started"></a>Introdução

Você e seus usuários finais podem baixar o Microsoft Edge em lojas de aplicativos públicas para uso em suas organizações. Os requisitos do sistema operacional para políticas de navegador são um dos seguintes:
- Android 4 e posterior
- iOS 8.0 e posterior

## <a name="application-protection-policies-for-microsoft-edge"></a>Políticas de proteção de aplicativo para Microsoft Edge

Como o Microsoft Edge está integrado com o SDK do Intune, você pode aplicar políticas de proteção de aplicativos a eles.

Você pode aplicar estas configurações a:
- Dispositivos que estão registrados no Intune.
- Dispositivos registrados em outro produto de gerenciamento de dispositivo móvel.
- Dispositivos não gerenciados.

Se o Microsoft Edge não for alvo da política do Intune, os usuários não poderão usá-lo para acessar dados de outros aplicativos gerenciados pelo Intune, como aplicativos do Office. 

## <a name="conditional-access-for-microsoft-edge"></a>Acesso Condicional para o Microsoft Edge

Você pode usar o Acesso Condicional do Azure AD para redirecionar os usuários para acessar o conteúdo corporativo somente pelo Microsoft Edge. Isso restringe ao Microsoft Edge protegido por política o acesso do navegador móvel a aplicativos Web conectados ao Azure AD. Isso bloqueia o acesso de outros navegadores desprotegidos, como Safari ou Chrome. É possível aplicar o Acesso Condicional a recursos do Azure como o Exchange Online e o SharePoint Online, o centro de administração do Microsoft 365 e até mesmo a sites locais que você tenha exposto a usuários externos por meio do [Proxy de Aplicativo do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

Para restringir os aplicativos Web conectados ao Azure AD a usar o Microsoft Edge no iOS e Android:
1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. No nó do Intune, selecione **Acesso Condicional** > **Nova Política**.
3. Selecione **Conceder** na seção **Controles de acesso** da folha.
4. Selecione **Exigir aplicativo cliente aprovado**.
5. Escolha **Selecionar** na folha **Conceder**. Esta política deve ser atribuída aos aplicativos de nuvem que você deseja tornar acessíveis apenas ao aplicativo Intune Managed Browser.

    ![Captura de tela da política de Acesso Condicional – Conceder](./media/manage-microsoft-edge/manage-microsoft-edge-01.png)

6. Na seção Atribuições, selecione **Condições** > **Aplicativos cliente**. A folha **Aplicativos cliente** é exibida.
7. Em **Configurar**, selecione **Sim** para aplicar a política a aplicativos cliente específicos.
8. Verifique se o **Navegador** está selecionado como um aplicativo cliente.

    ![Política de Acesso Condicional – Selecionar aplicativos clientes](./media/manage-microsoft-edge/manage-microsoft-edge-02.png)

    > [!NOTE]
    > Se desejar restringir quais aplicativos nativos (aplicativos que não são navegadores) poderão acessar esses aplicativos de nuvem, também será possível selecionar **Aplicativos móveis e clientes de desktop**.

9. Na seção **Atribuições**, selecione **Usuários e grupos** e, em seguida, escolha os usuários ou grupos para os quais você quer atribuir essa política.

10. Na seção **Atribuições**, selecione **Aplicativos de nuvem** para escolher quais aplicativos proteger com esta política.

Depois que a política acima estiver configurada, os usuários serão forçados a usar o Microsoft Edge para acessar os aplicativos Web conectados ao Azure AD que você protegeu com essa política. Se os usuários tentarem usar um navegador não gerenciado neste cenário, receberão uma mensagem de que devem usar o Microsoft Edge.

> [!TIP]
> O Acesso Condicional é uma tecnologia do Azure AD. O nó Acesso condicional acessado no Intune é o mesmo nó acessado no Azure AD.

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>Logon único para aplicativos Web conectados ao Azure AD nos navegadores protegidos por política

O Microsoft Edge no iOS e Android pode usar o SSO (Logon único) em todos os aplicativos Web (SaaS e locais) conectados ao Azure AD. O SSO permite que os usuários acessem aplicativos Web conectados ao Azure AD por meio do Microsoft Edge sem precisar digitar novamente suas credenciais.

O SSO requer que seu dispositivo seja registrado pelo aplicativo Microsoft Authenticator para dispositivos iOS ou pelo Portal da Empresa do Intune no Android. Quando os usuários têm um deles, são solicitados a registrar o dispositivo ao acessarem um aplicativo Web conectado ao Azure AD em um navegador protegido por política. (Isso só ocorrerá se o dispositivo ainda não estiver registrado.) Depois que o dispositivo for registrado com a conta gerenciada do usuário pelo Intune, essa conta terá o SSO habilitado para aplicativos Web conectados ao Azure AD.

> [!NOTE]
> O registro do dispositivo é um simples check-in com o serviço do Azure AD. Ele não requer o registro de dispositivo completo e não fornece ao TI nenhum privilégio adicional no dispositivo.

## <a name="create-a-protected-browser-app-configuration"></a>Criar uma configuração de aplicativo de navegador protegido

Para criar a configuração de aplicativo do Microsoft Edge:

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Aplicativos de cliente** > **Políticas de configuração de aplicativo** > **Adicionar**.
3. Na folha **Adicionar política configuração**, insira um **Nome** e uma **Descrição** opcional para as definições de configuração do aplicativo.
4. Para o tipo **Registro de Dispositivo**, escolha **Aplicativos gerenciados**.
5. Escolha **Selecione o aplicativo necessário**. Em seguida, na folha **Aplicativos direcionados**, escolha o **Managed Browser** ou **Edge** para iOS, Android ou ambos.
6. Selecione **OK** para retornar à folha **Adicionar política de configuração**.
7. Selecione **Definições de configuração**. Na folha **Configuração**, defina os pares de chave e valor para fornecer as configurações para o Microsoft Edge. Use as próximas seções deste artigo para saber mais sobre os diferentes pares de chave e valor que podem ser definidos.

    > [!NOTE]
    > O Microsoft Edge usa os mesmos pares de chave e valor do Managed Browser. 

8. Ao terminar, selecione **OK**.
9. Na folha **Adicionar política de configuração**, escolha **Adicionar**.<br>
    A nova configuração é criada e exibida na folha **Configuração de aplicativos**.

## <a name="assign-the-configuration-settings-you-created"></a>Atribuir as definições de configuração criadas 

Atribua as configurações a grupos de usuários do Azure AD. Se esse usuário tiver o aplicativo de navegador protegido direcionado instalado, o aplicativo será gerenciado pelas configurações especificadas.

1. Na folha **Aplicativos cliente** do painel de gerenciamento de aplicativo móvel do Intune, selecione **Políticas de configuração de aplicativo**.
2. Na lista de configurações de aplicativo, selecione aquela que você deseja atribuir.
3. Na próxima folha, selecione **Atribuições**.
4. Na folha **Atribuições**, selecione o grupo do Azure AD ao qual você deseja atribuir a configuração de aplicativo e, em seguida, selecione **OK**.

## <a name="direct-users-to-microsoft-edge-instead-of-the-intune-managed-browser"></a>Direcionar usuários para o Microsoft Edge em vez do Intune Managed Browser 

O Intune Managed Browser e o Microsoft Edge podem ser usados como navegadores protegidos por política. Para garantir que seus usuários sejam direcionados para usar o aplicativo de navegador correto, direcione todos os seus aplicativos gerenciados pelo Intune (por exemplo, Outlook, OneDrive e SharePoint) com a seguinte definição de configuração:

|    Chave    |    Valor    |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.useEdge`    |    O valor `true` direcionará os usuários para baixar usar o Microsoft Edge.<br>O valor `false` permitirá aos usuários usar o Intune Managed Browser.    |

Se esse valor de configuração de aplicativos **não** for definido, a lógica a seguir definirá qual navegador será usado para abrir links corporativos.

No Android:
- O Intune Managed Browser será aberto se um usuário tiver o Intune Managed Browser e o Microsoft Edge baixados no dispositivo. 
- O Microsoft Edge será aberto se apenas o Microsoft Edge estiver baixado no dispositivo e se for direcionado pela política do Intune.
- O Managed Browser será aberto se só houver ele no dispositivo e se for direcionado pela política do Intune.

No iOS, para aplicativos integrados com o SDK do Intune para iOS v. 9.0.9 e superiores:
- O Intune Managed Browser será aberto se o Managed Browser e o Microsoft Edge estiverem no dispositivo.  
- O Microsoft Edge será aberto se houver somente o Microsoft Edge no dispositivo e se for o direcionado pela política do Intune.
- O Managed Browser será aberto se só houver ele no dispositivo e se for direcionado pela política do Intune.

## <a name="configure-application-proxy-settings-for-microsoft-edge"></a>Definir as configurações de Proxy de Aplicativo para o Microsoft Edge

O Microsoft Edge e o [Proxy de Aplicativo do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) podem ser usados juntos para fornecer aos usuários acesso a sites de intranet nos dispositivos móveis deles. 

Estes são alguns exemplos dos cenários que o proxy de aplicativo do Azure AD permite: 

- Um usuário está usando o aplicativo móvel do Outlook, que é protegido pelo Intune. Em seguida, ele clica em um link para um site de intranet em um email e o Microsoft Edge reconhece que esse site de intranet foi exposto ao usuário por meio do proxy de aplicativo. O usuário será roteado automaticamente por meio do proxy de aplicativo para ser autenticado com qualquer autenticação multifator aplicável e Acesso Condicional antes de chegar ao site de intranet. Agora o usuário pode acessar sites internos, mesmo nos dispositivos móveis dele, e o link no Outlook funciona conforme o esperado.
- Um usuário abre o Microsoft Edge no seu dispositivo iOS ou Android. Se o Microsoft Edge estiver protegido com o Intune e o proxy de aplicativo estiver habilitado, o usuário poderá acessar um site da intranet usando a URL interna que está acostumado a usar. O Microsoft Edge reconhece que esse site da intranet foi exposto ao usuário por meio do proxy de aplicativo. O usuário será automaticamente roteado para autenticação por meio do proxy de aplicativo antes de chegar ao site da intranet. 

### <a name="before-you-start"></a>Antes de começar

- Configure os aplicativos internos por meio do proxy de aplicativo do Azure AD.
  - Para configurar o Proxy de Aplicativo e publicar aplicativos, consulte a [documentação de instalação](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).
- O aplicativo do Microsoft Edge deve ter a [política de Proteção de Aplicativo do Intune](app-protection-policy.md) atribuída.

> [!NOTE]
> Os dados de redirecionamento do Proxy de Aplicativo atualizados podem levar até 24 horas para entrarem em vigor no Managed Browser e no Microsoft Edge.

#### <a name="step-1-enable-automatic-redirection-to-microsoft-edge-from-outlook"></a>Etapa 1: Habilitar o redirecionamento automático do Outlook para o Microsoft Edge
Configure o Outlook com uma política de proteção de aplicativo que habilita a configuração **Compartilhar o conteúdo da Web com navegadores gerenciados por política**.

![Captura de tela da política de proteção de aplicativo – compartilhar o conteúdo da Web com navegadores gerenciados por política](./media/manage-microsoft-edge/manage-microsoft-edge-03.png)

#### <a name="step-2-set-the-app-configuration-setting-to-enable-app-proxy"></a>Etapa 2: Definir a configuração de aplicativos para habilitar o proxy de aplicativo
Defina o Microsoft Edge como o destino do seguinte par chave-valor para habilitar o proxy de aplicativo para o Microsoft Edge:

|    Chave    |    Valor    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.AppProxyRedirection    |    verdadeiro    |

Para saber mais sobre como usar o Microsoft Edge e o Proxy de Aplicativo do Azure AD em conjunto para obter um acesso contínuo (e protegido) a aplicativos Web locais, confira [Melhores juntos: O Intune e o Azure Active Directory se unem para melhorar o acesso do usuário](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access). Esta postagem no blog faz referência ao Intune Managed Browser, mas o conteúdo também se aplica ao Microsoft Edge.

## <a name="configure-a-homepage-shortcut-for-microsoft-edge"></a>Configurar um atalho de home page para o Microsoft Edge

Esta configuração permite que você configure um atalho de home page para o Microsoft Edge. O atalho de home page que você configurar aparece como o primeiro ícone abaixo da barra de pesquisa quando o usuário abre uma nova guia no Microsoft Edge. O usuário não pode editar ou excluir esse atalho no contexto gerenciado. O atalho da home page exibe o nome da sua organização para diferenciá-lo. 

Use o par chave-valor a seguir para configurar um atalho de home page:

|    Chave    |    Valor    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.homepage   |    Especifique uma URL válida. URLs incorretas são bloqueadas como medida de segurança.<br>**Exemplo:**  <`https://www.bing.com`>

## <a name="configure-your-organizations-logo-and-brand-color-for-new-tab-pages-in-microsoft-edge"></a>Configure o logotipo e a cor da marca de sua organização para páginas nova guia no Microsoft Edge

Essas configurações permitem personalizar a página Nova guia do Microsoft Edge para exibir o logotipo e a cor da marca de sua organização como página de plano de fundo.

Para carregar o logotipo e a cor da organização, primeiro realize estas etapas:
- No portal do Azure, navegue até Intune -> Aplicativos cliente -> Identidade visual e personalização -> Identidade Visual da Empresa
- Para definir o logotipo da marca, em "Exibição", escolha "Logotipo da empresa". É recomendável usar logotipos de plano fundo transparentes. 
- Para definir a cor da tela de fundo da marca, em "Exibição" selecione "Cor do Tema". O Microsoft Edge aplica um tom mais claro da cor na página Nova guia, o que garante a alta legibilidade da página. 

Em seguida, use os seguintes pares chave-valor para adicionar a identidade visual de sua organização ao Microsoft Edge:

|    Chave    |    Valor    |
|--------------------------------------------------------------------|------------|
|    com.microsoft.intune.mam.managedbrowser.NewTabPage.BrandLogo    |    verdadeiro    |
|    com.microsoft.intune.mam.managedbrowser.NewTabPage.BrandColor    |    verdadeiro    |

## <a name="configure-managed-bookmarks-for-microsoft-edge"></a>Configurar indicadores gerenciados para o Microsoft Edge

Para facilidade de acesso, você pode configurar os indicadores que gostaria que os usuários tivessem disponíveis quando estiverem usando o Microsoft Edge. 

Aqui estão alguns detalhes:

- Esses indicadores serão exibidos para os usuários apenas quando eles estiverem usando o modo corporativo do Microsoft Edge. 
- Esses indicadores não podem ser excluídos ou modificados pelos usuários.
- Eles são exibidos na parte superior da lista. Todos os indicadores que os usuários criar serão exibidos abaixo desses indicadores.
- Se você tiver habilitado o redirecionamento do proxy de aplicativo, poderá adicionar aplicativos Web do proxy de aplicativo usando sua URL interna ou externa.

Use o seguinte par chave-valor para configurar indicadores gerenciados:

|    Chave    |    Valor    |
|---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.bookmarks    |    O valor dessa configuração é uma lista de indicadores. Cada indicador consiste no título e na URL do indicador. Separe o título e a URL com o caractere `|`.      Exemplo:<br>`Microsoft Bing|https://www.bing.com`<br>Para configurar vários indicadores, separe cada par com caractere duplo, `||`.<p>Exemplo:<br>`Microsoft Bing|https://www.bing.com||Contoso|https://www.contoso.com`    |

## <a name="display-myapps-within-microsoft-edge-bookmarks"></a>Exibir MyApps nos indicadores do Microsoft Edge

Por padrão, são mostrados para os usuários os sites de MyApps que estão configurados para eles dentro de uma pasta nos indicadores do Microsoft Edge. A pasta é rotulada com o nome da sua organização.

|    Chave    |    Valor    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.MyApps    |    **True** mostra o MyApps nos indicadores do Microsoft Edge.<p>**False** oculta o MyApps no Microsoft Edge.    |

## <a name="specify-allowed-or-blocked-sites-list-for-microsoft-edge"></a>Especificar a lista de sites permitidos ou bloqueados para o Microsoft Edge
Você pode usar a configuração de aplicativos para definir quais sites os usuários podem acessar ao usar o seu perfil de trabalho. Se você usar uma lista de permissões, os usuários poderão acessar apenas os sites listados explicitamente. Se você usar uma lista de bloqueados, os usuários poderão acessar todos os sites, exceto os sites bloqueados explicitamente. Imponha apenas uma lista de bloqueados ou de permissões, não ambas. Se você impuser ambas, a lista de permissões será respeitada.  

Use os pares chave-valor abaixo para configurar uma lista de sites permitidos ou bloqueados para o Microsoft Edge. 

|    Chave    |    Valor    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Escolha:<p>1. Especifique as URLs permitidas (apenas essas URLs são permitidas; nenhum outro site pode ser acessado):<br>`com.microsoft.intune.mam.managedbrowser.AllowListURLs`<p>2. Especifique as URLs bloqueadas (todos os outros sites podem ser acessados):<br>`com.microsoft.intune.mam.managedbrowser.BlockListURLs`    |    O valor correspondente para a chave é uma lista de URLs. Insira todas as URLs que você deseja permitir ou bloquear como um único valor, separado por um caractere de barra vertical `|`.<br>**Exemplos:**<br>`URL1|URL2|URL3`<br>`http://.contoso.com/|https://.bing.com/|https://expenses.contoso.com`  |

### <a name="url-formats-for-allowed-and-blocked-site-list"></a>Formatos de URL para a lista de sites permitidos e bloqueados 
Você pode usar vários formatos de URL para criar suas listas de sites permitidos/bloqueados. Esses padrões permitidos são detalhados na tabela a seguir. Algumas observações antes de começar: 
- Certifique-se de prefixar todas as URLs com **http** ou **https** ao inseri-las na lista.
- Você pode usar o símbolo de caractere curinga (\*) de acordo com as regras na lista de padrões permitidos abaixo.
- Um caractere curinga só pode corresponder a todo um componente do nome do host (separado por pontos) ou partes inteiras do caminho (separadas por barras). Por exemplo, **não** há suporte para `http://*contoso.com`.
- Você pode especificar os números de porta no endereço. Se você não especificar um número da porta, os valores usados serão:
  - Porta 80 para https
  - Porta 443 para https
- O uso de caracteres curinga no número da porta **não** é compatível. Por exemplo, `http://www.contoso.com:*` e `http://www.contoso.com:*/` não são compatíveis. 

    |    URL    |    Detalhes    |    Corresponde a    |    Não corresponde a    |
    |-------------------------------------------|--------------------------------------------------------|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
    |    `http://www.contoso.com`    |    Corresponde a uma única página    |    `www.contoso.com`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`contoso.com/`    |
    |    `http://contoso.com`    |    Corresponde a uma única página    |    `contoso.com/`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com`    |
    |    `http://www.contoso.com/*;`   |    Corresponde a todas as URLs iniciadas por `www.contoso.com`    |    `www.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com/videos/tvshows`    |    `host.contoso.com`<br>`host.contoso.com/images`    |
    |    `http://*.contoso.com/*`    |    Corresponde a todos os subdomínios em `contoso.com`    |    `developer.contoso.com/resources`<br>`news.contoso.com/images`<br>`news.contoso.com/videos`    |    `contoso.host.com`
    |    `http://*contoso.com/*`    |    Corresponde a todos os subdomínios terminados em `contoso.com/`    |    `http://news-contoso.com`<br>`http://news-contoso.com.com/daily`    |    `http://news-contoso.host.com`    |
    `http://www.contoso.com/images`    |    Corresponde a uma única pasta    |    `www.contoso.com/images`    |    `www.contoso.com/images/dogs`    |
    |    `http://www.contoso.com:80`    |    Corresponde a uma única página, usando um número da porta    |    `http://www.contoso.com:80`    |         |
    |    `https://www.contoso.com`    |    Corresponde a uma única página segura    |    `https://www.contoso.com`    |    `http://www.contoso.com`    |
    |    `http://www.contoso.com/images/*`    |    Corresponde a uma única pasta e todas as subpastas    |    `www.contoso.com/images/dogs`<br>`www.contoso.com/images/cats`    |    `www.contoso.com/videos`    |
  
- Veja a seguir exemplos de algumas das entradas que você não pode especificar:
  - `*.com`
  - `*.contoso/*`
  - `www.contoso.com/*images`
  - `www.contoso.com/*images*pigs`
  - `www.contoso.com/page*`
  - Endereços IP
  - `https://*`
  - `http://*`
  - `https://*contoso.com`
  - `http://www.contoso.com:*`
  - `http://www.contoso.com: /*`

## <a name="define-behavior-when-users-try-to-access-a-blocked-site"></a>Definir o comportamento quando os usuários tentarem acessar um site bloqueado

Com o modelo de identidade dupla incorporado ao Microsoft Edge, você pode habilitar uma experiência mais flexível para seus usuários finais do que era possível com o Intune Managed Browser. Quando os usuários acessam um site bloqueado no Microsoft Edge, você pode solicitar que eles abram o link no contexto pessoal, em vez de fazerem isso no contexto de trabalho. Isso permite que eles fiquem protegidos, enquanto mantém os recursos corporativos seguros. Por exemplo, se um usuário receber um link para um artigo de notícias por meio do Outlook, ele poderá abrir o link em seu contexto pessoal ou em uma guia InPrivate. O contexto de trabalho não permite sites de notícias. Por padrão, essas transições são permitidas.

Use o par chave-valor a seguir para configurar se essas transições reversíveis são permitidas:

|    Chave    |    Valor    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock`    |    **True** permite que o Microsoft Edge faça a transição de usuários para o seu contexto pessoal para abrir sites bloqueados.<p>**Block** impede que o Microsoft Edge faça a transição de usuários. Os usuários simplesmente recebem uma mensagem informando que o site que estão tentando acessar está bloqueado.    |

## <a name="use-microsoft-edge-on-ios-to-access-managed-app-logs"></a>Usar o Microsoft Edge no iOS para acessar os logs de aplicativo gerenciado 

Os usuários com o Microsoft Edge instalado em seus dispositivos iOS podem exibir o status de gerenciamento de todos os aplicativos publicados da Microsoft. Eles podem enviar logs para solucionar problemas de seus aplicativos iOS gerenciados. Aqui está como:
1. Abra o Microsoft Edge em seu dispositivo iOS.
2. Digite `about:intunehelp` na caixa de endereço. 
3. O Microsoft Edge inicia o modo de solução de problemas.

Para obter uma lista das configurações armazenadas nos logs de aplicativo, consulte [Revisar logs de proteção do aplicativo no Managed Browser](app-protection-policy-settings-log.md).

Para ver como exibir os logs em dispositivos Android, confira [Enviar logs para o administrador de TI por email](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## <a name="security-and-privacy-for-microsoft-edge"></a>Segurança e privacidade para o Microsoft Edge

A seguir estão as considerações adicionais de segurança e privacidade do Microsoft Edge:

- O Microsoft Edge não consome as configurações que os usuários definem para o navegador nativo em seus dispositivos, porque não tem acesso a essas configurações.
- Você pode configurar a opção **Exigir PIN simples para acesso** ou **Exigir credenciais corporativas para acesso** em uma política de proteção de aplicativo associada ao Microsoft Edge. Se um usuário selecionar o link de ajuda na página de autenticação, poderá navegar em qualquer site da Internet, não importa se ele foi adicionado a uma lista bloqueada na política.
- O Microsoft Edge pode bloquear o acesso a sites apenas quando eles são acessados diretamente. Ele não bloqueia o acesso quando serviços intermediários (como um serviço de tradução) são usados para acessar o site.
- Para permitir a autenticação e acessar a documentação do Intune, * **.microsoft.com** é isento das configurações da lista de permissão ou de contatos bloqueados. É sempre permitido.
- Os usuários podem desativar a coleta de dados. A Microsoft coleta automaticamente dados anônimos sobre o desempenho e o uso do Managed Browser para melhorar os produtos e serviços Microsoft. Os usuários podem desligar a coleta de dados usando a configuração **Dados de Uso** em seus dispositivos. Você não tem controle sobre a coleta desses dados. Em dispositivos iOS, sites visitados por usuários que têm um certificado expirado ou não confiável não podem ser abertos.

## <a name="next-steps"></a>Próximas etapas

- [O que são políticas de proteção do aplicativo?](app-protection-policy.md) 
