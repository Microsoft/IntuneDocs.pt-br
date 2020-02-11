---
title: Gerenciar o acesso à Web corporativo com um navegador protegido por política
titleSuffix: Microsoft Intune
description: Use um navegador protegido por política atribuído pelo Intune para gerenciar a navegação na Web corporativa e a transferência de dados da Web.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/27/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: babe556d6810ad027a1b0b3cae6364c99bc9a07c
ms.sourcegitcommit: b0d683917af83170f85022b270270d8ced8e301c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76812508"
---
# <a name="manage-web-access-using-a-microsoft-intune-policy-protected-browser"></a>Gerenciar o acesso à Web usando um navegador protegido por políticas do Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Usando um navegador protegido com a política do Intune (Microsoft Edge ou Intune Managed Browser), é possível garantir que sites corporativos sempre sejam acessados com proteções em vigor.  Quando configurados com o Intune, os navegadores protegidos podem usar o seguinte:

- Políticas de proteção do aplicativo
- Acesso condicional
- Logon único
- Definições da configuração do aplicativo
- Integração do proxy do aplicativo do Azure

> [!IMPORTANT]
> O Intune Managed Browser será desativado. Use o Microsoft Edge para obter uma experiência de navegação protegida no Intune. 

## <a name="microsoft-edge-support"></a>Suporte ao Microsoft Edge

Use o Microsoft Edge para cenários empresariais em dispositivos iOS e Android. O Microsoft Edge dá suporte aos mesmos cenários de gerenciamento do Intune Managed Browser com a adição de melhorias na experiência do usuário final. Os seguintes recursos corporativos do Microsoft Edge habilitados pelas políticas do Microsoft Intune incluem:

- **Identidade Dupla**: os usuários podem adicionar uma conta corporativa e uma conta pessoal para navegação. Há uma separação completa entre as duas identidades, o que é semelhante à arquitetura e a experiência no Office 365 e no Outlook. Administradores do Intune poderão definir as políticas desejadas para uma experiência de navegação protegida dentro da conta de trabalho. 
- **Integração de política de proteção de aplicativo do Intune**: agora, os administradores podem direcionar políticas de proteção de aplicativo ao Microsoft Edge, inclusive o controle de ações de recortar, copiar e colar, impedir capturas de tela e garantir que links selecionados pelo usuário abram somente em outros aplicativos gerenciados.
- **Integração de Proxy de Aplicativo Azure**: os administradores podem controlar o acesso a aplicativos SaaS e aplicativos Web, ajudando a garantir que somente aplicativos baseados em navegador sejam executados no navegador seguro Microsoft Edge, mesmo se os usuários finais se conectarem da rede corporativa ou da Internet. 
- **Favoritos Gerenciados e atalhos da Home Page**: para facilitar o acesso, os administradores podem definir que as URLs apareçam sob os favoritos quando os usuários finais estiverem em seu contexto corporativo. Os administradores podem definir um atalho da home page, que aparecerá como o atalho primário quando o usuário corporativo abrir uma nova página ou uma nova guia no Microsoft Edge.

As políticas de proteção do Microsoft Intune para o Microsoft Edge ajudam a proteger os dados e recursos da sua organização. O Microsoft Edge protegido pelo Intune garante que os recursos da sua empresa sejam protegidos não apenas dentro de aplicativos instalados nativamente, mas também quando forem acessados pelo navegador da Web.

## <a name="getting-started"></a>Introdução

O Microsoft Edge e o Intune Managed Browser são aplicativos de navegador da Web que você e seus usuários finais podem baixar de lojas públicas de aplicativos para uso em sua organização. 

Requisitos de sistema operacional para políticas de navegador:
- Android 4 e posterior ou
- iOS 8.0 e posterior.

Versões anteriores do Android e do iOS poderão continuar usando o Managed Browser, mas não será possível instalar novas versões do aplicativo e acessar todos os recursos do aplicativo. Atualize esses dispositivos para uma versão de sistema operacional com suporte.

>[!NOTE]
>O Managed Browser não dá suporte ao protocolo criptográfico SSLv3 (Secure Sockets Layer versão 3).


## <a name="application-protection-policies-for-protected-browsers"></a>Políticas de proteção de aplicativo para navegadores protegidos

Como o Microsoft Edge e o Managed Browser têm integração com o SDK do Intune, você também pode aplicar políticas de proteção de aplicativos a eles, incluindo:
- Controlar o uso de recortar, copiar e colar.
- Impedir capturas de tela.
- Garantir que links corporativas sejam abertos somente dentro de aplicativos e navegadores gerenciados.

Para ver mais detalhes, consulte [O que são políticas de proteção de aplicativo?](app-protection-policy.md)

Você pode aplicar estas configurações a:

- Dispositivos que estão registrados no Intune
- Registrados com outro produto de MDM
- Dispositivos não gerenciados

>[!NOTE]
>Se os usuários instalarem o Managed Browser por meio da loja de aplicativos e o Intune não gerenciá-lo, ele poderá ser usado como um navegador da Web básico, com suporte para Logon Único por meio do site do Microsoft MyApps. Os usuários são levados diretamente ao site do MyApps, no qual poderão ver todos os seus aplicativos SaaS provisionados.
Embora o Managed Browser e o Microsoft Edge não sejam gerenciados pelo Intune, eles não podem acessar dados de outros aplicativos gerenciados pelo Intune. 


## <a name="conditional-access-for-protected-browsers"></a>Acesso condicional para navegadores protegidos

Agora o Managed Browser é um aplicativo cliente aprovado para acesso condicional. Isso significa que você pode restringir o acesso do navegador móvel a aplicativos Web conectados ao Azure AD, em que os usuários só podem usar o Managed Browser bloqueando o acesso de outros navegadores desprotegidos como Safari ou Chrome. Essa proteção pode ser aplicada aos recursos do Azure como o Exchange Online e o SharePoint Online, o Centro de administração do Microsoft 365 e até mesmo sites locais que você tenha exposto a usuários externos por meio do [Proxy de Aplicativo do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). 

Para restringir os aplicativos Web conectados ao Azure AD para usarem o Intune Managed Browser em plataformas móveis, é possível criar uma política de Acesso Condicional que requer aplicativos cliente aprovados. 

> [!TIP]  
> O Acesso Condicional é uma tecnologia do Azure AD (Azure Active Directory). O nó Acesso Condicional acessado no *Intune* é o mesmo nó que o acessado no *Azure AD*.  

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Acesso Condicional** > **Nova política**.
3. Adicione o **Nome** da política. 
4. Na seção **Atribuições**, selecione **Condições** > **Aplicativos cliente**. O painel **Aplicativos cliente** é exibido.
5. Clique em **Sim** em **Configurar** para aplicar a política a aplicativos cliente específicos.
6. Verifique se o **Navegador** está selecionado como um aplicativo cliente.

    ![Azure AD – Managed Browser – Selecionar aplicativos cliente](./media/app-configuration-managed-browser/managed-browser-conditional-access-02.png)

    > [!NOTE]
    > Se desejar restringir quais aplicativos nativos (aplicativos que não são navegadores) poderão acessar esses aplicativos de nuvem, também será possível selecionar **Aplicativos móveis e clientes de desktop**.

7. Clique em **Concluído** > **Concluído**.
8. Na seção **Atribuições**, selecione **Usuários e grupos** e escolha os usuários ou grupos aos quais você deseja atribuir essa política. Clique em **Concluído** para fechar o painel.
9. Na seção **Atribuições**, selecione **Aplicativos de nuvem ou ações** para escolher quais aplicativos proteger com essa política. Clique em **Concluído** para fechar o painel.
10. Selecione **Conceder** na seção **Controles de acesso** do painel. 
11. Clique em **Conceder acesso** e em **Exigir aplicativo cliente aprovado**. 
12. Clique em **Selecionar** no painel **Conceder**. Esta política deve ser atribuída aos aplicativos de nuvem que você deseja tornar acessíveis apenas ao aplicativo Intune Managed Browser.

    ![Microsoft Azure AD – política de Acesso Condicional do Managed Browser](./media/app-configuration-managed-browser/managed-browser-conditional-access-01.png)



Depois que a política acima estiver configurada, os usuários serão forçados a usar o Intune Managed Browser para acessar os aplicativos Web conectados ao Azure AD que você protegeu com esta política. Se os usuários tentarem usar um navegador não gerenciado neste cenário, eles verão um aviso de que o Intune Managed Browser deverá ser usado.

O Navegador Gerenciado não é compatível com políticas de Acesso Condicional clássicas. Para obter mais informações, consulte [Migrar políticas clássicas no Portal do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-migration).

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>Logon único para aplicativos Web conectados ao Azure AD nos navegadores protegidos por política

O Microsoft Edge e o Intune Managed Browser no iOS e Android podem usar SSO para todos os aplicativos Web (SaaS e locais) conectados ao Azure AD. Quando o aplicativo Microsoft Authenticator estiver presente no iOS ou no aplicativo Portal da Empresa do Intune no Android, os usuários de um navegador protegido por política poderão acessar aplicativos Web conectados ao Azure AD sem precisar inserir suas credenciais novamente.

O SSO requer que seu dispositivo seja registrado pelo aplicativo Microsoft Authenticator no iOS ou pelo Portal da Empresa do Intune no Android. Os usuários com o aplicativo Authenticator ou com o Portal da Empresa do Intune deverão registrar seu dispositivo quando navegarem até um aplicativo Web conectado ao Azure AD em um navegador protegido por política se o dispositivo ainda não tiver sido registrado por outro aplicativo. Depois que o dispositivo for registrado com a conta gerenciada pelo Intune, essa conta terá o SSO habilitado para aplicativos Web conectados ao Azure AD. 

> [!NOTE]
> O registro do dispositivo é um simples check-in com o serviço do Azure AD. Ele não requer o registro de dispositivo completo e não dá à TI nenhum privilégio adicional no dispositivo.

## <a name="create-a-protected-browser-app-configuration"></a>Criar uma configuração de aplicativo de navegador protegido

>[!IMPORTANT]
>Para configurações de aplicativo a serem aplicadas, o navegador protegido do usuário ou outro aplicativo no dispositivo já deve ser gerenciado pela [política de Proteção de Aplicativo do Intune]( ../app-protection-policy.md)

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Políticas de configuração de aplicativo** > **Adicionar** > **Aplicativos gerenciados**.
3. Na página **Conceitos Básicos** do painel **Criar política de configuração de aplicativo**, insira um **Nome** e uma **Descrição** opcional para as definições de configuração do aplicativo.
4. Escolha **Selecionar o aplicativo público**, depois escolha o **Managed Browser** e/ou **Microsoft Edge** para iOS, Android ou ambos.
5. Clique em **Selecionar** para retornar ao painel **Criar política de configuração de aplicativo**.
6. Clique em **Avançar** para exibir a página **Configurações**.
7. Na página **Configurações**, defina os pares de chaves e valores para fornecer as configurações ao aplicativo. Use as próximas seções deste artigo para saber mais sobre os diferentes pares de chave e valor que podem ser definidos.
8. Clique em **Avançar** para exibir a página **Atribuição** e clique em **Selecionar grupos para incluir** e/ou **Selecionar grupos para excluir**.
9. Clique em **Avançar** para exibir a página **Revisar + criar**.
10. Clique em **Criar** depois de analisar a política de configuração de aplicativo.

A nova configuração é criada e exibida no painel **Política de configuração de aplicativo**.


## <a name="assign-the-configuration-settings-you-created"></a>Atribuir as definições de configuração criadas

Atribua as configurações a grupos de usuários do Azure AD. Se esse usuário tiver o aplicativo de navegador protegido direcionado instalado, o aplicativo será gerenciado pelas configurações especificadas.

1. No painel **Aplicativos** do painel de gerenciamento de aplicativo móvel do Intune, escolha **Políticas de configuração de aplicativo**.
2. Na lista de configurações de aplicativo, selecione aquela que você deseja atribuir.
3. No próximo painel, escolha **Atribuições**.
4. No painel **Atribuições**, selecione o grupo do Azure AD ao qual você deseja atribuir a configuração de aplicativo e, em seguida, escolha **OK**.

## <a name="how-to-set-microsoft-edge-as-the-protected-browser-for-your-organization"></a>Como definir o Microsoft Edge como navegador protegido para a organização

Essa definição permite configurar se os usuários serão direcionados para o Microsoft Edge ou para o Intune Managed Browser, supondo que os dois navegadores sejam direcionados com a política de proteção do aplicativo. **Essa definição de política de configuração de aplicativo deve ser direcionada para os aplicativos gerenciados do Intune dos quais o link da Web é aberto.** 

Se essa configuração for definida como "True":

- Os usuários serão direcionados para o Microsoft Edge ao abrir links de aplicativos gerenciados do Intune direcionados com essa configuração. 
- Caso ainda não tenham o aplicativo, eles serão solicitados a baixar o Microsoft Edge da loja, mesmo que já tenham baixado o Intune Managed Browser.

Se essa configuração for definida como "False":

- Caso os usuários já tenham baixado o Managed Browser **e** o Microsoft Edge, o Managed Browser será inicializado. 
- Caso os usuários **já** tenham baixado o Managed Browser **ou** o Microsoft Edge, o aplicativo do navegador será inicializado. 
- No entanto, se ainda não baixaram nenhum dos navegadores, eles serão solicitados a baixar o Managed Browser.

Use o procedimento descrito acima para criar uma configuração de aplicativo do Microsoft Edge. Forneça o seguinte par de chave e valor ao escolher as **Definições de configuração**, no painel **Configuração** (etapa 9):

| Chave                              |  Valor   |
|----------------------------------|----------|
| **com.microsoft.intune.useEdge** | **true** |

> [!NOTE]
> Na política de proteção de aplicativo que gerencia o Microsoft Edge e os aplicativos associados especificados na configuração do aplicativo, verifique se as seguintes configurações de política de proteção de dados estão definidas:
> - Enviar dados da organização para outros aplicativos: **Aplicativos gerenciados pela política**
> - Restringir a transferência de conteúdo Web com outros aplicativos: **Navegadores gerenciados por política**

## <a name="how-to-configure-application-proxy-settings-for-protected-browsers"></a>Como definir as configurações de Proxy de Aplicativo para navegadores protegidos

O Microsoft Edge, o Intune Managed Browser e o [Proxy de Aplicativo do Azure AD]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) podem ser usados juntos para dar suporte aos seguintes cenários para os usuários de dispositivos iOS e Android:

- Um usuário baixa e entra no aplicativo Microsoft Outlook. As políticas de Proteção de Aplicativo do Intune são aplicadas automaticamente. Elas criptografam os dados salvos e impedem o usuário de transferir arquivos corporativos para aplicativos não gerenciados ou locais no dispositivo. Quando o usuário clica em um link para um site da intranet no Outlook, você pode especificar que o link será aberto em um aplicativo de navegador protegido, em vez de outro navegador. O navegador protegido reconhece que este site de intranet foi exposto ao usuário por meio do Proxy de Aplicativo. O usuário será automaticamente roteado por meio do Proxy de Aplicativo para se autenticar com qualquer autenticação multifator aplicável e Acesso Condicional, antes de alcançar o site da intranet. Este site, que anteriormente não pôde ser encontrado enquanto o usuário estava remoto, agora está acessível e o link no Outlook funciona conforme o esperado.
- Um usuário remoto abre o aplicativo de navegador protegido e navega para um site da intranet usando a URL interna. O navegador protegido reconhece que este site de intranet foi exposto ao usuário por meio do Proxy de Aplicativo. O usuário será automaticamente roteado por meio do Proxy de Aplicativo para se autenticar com qualquer autenticação multifator aplicável e Acesso Condicional, antes de alcançar o site da intranet. Este site, que anteriormente não pôde ser encontrado enquanto o usuário estava remoto, agora está acessível.

### <a name="before-you-start"></a>Antes de começar

- Configure os aplicativos internos por meio do Proxy de Aplicativo do Azure AD.
  - Para configurar o Proxy de Aplicativo e publicar aplicativos, consulte a [documentação de instalação](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy). 
  - [Os usuários devem ser atribuídos](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application#add-a-user-for-testing) ao Aplicativo empresarial para o qual o redirecionamento deverá ocorrer. Isso deverá ser feito mesmo se o aplicativo estiver definido no Modo de Passagem para pré-autenticação e se o requisito de atribuição do usuário tiver sido desativado nas configurações do Proxy de Aplicativo.
- Você deve estar usando pelo menos a versão mínima 1.2.0 do aplicativo Managed Browser.
- Os usuários do aplicativo Managed Browser ou Microsoft Edge têm uma [política de proteção do aplicativo do Intune](app-protection-policy.md) atribuída ao aplicativo.

    > [!NOTE]
    > Os dados de redirecionamento do Proxy de Aplicativo atualizados podem levar até 24 horas para entrarem em vigor no Managed Browser e no Microsoft Edge.


#### <a name="step-1-enable-automatic-redirection-to-a-protected-browser-from-outlook"></a>Etapa 1: Habilitar o redirecionamento automático do Outlook para um navegador protegido
O Outlook deve ser configurado com uma política de proteção do aplicativo que habilita a configuração para **Restringir conteúdo da Web para exibição no Managed Browser**.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-protected-browser"></a>Etapa 2: Aplicar uma política de configuração de aplicativo atribuída ao navegador protegido
Este procedimento configura o aplicativo Managed Browser ou Microsoft Edge para usar o redirecionamento de proxy de aplicativo. 

Abra a guia do **Microsoft Edge** nas definições de configuração da política e escolha **Habilitar** para o valor de redirecionamento do Proxy de Aplicativo. Habilitando esta configuração, os usuários podem acessar links corporativos e aplicativos Web locais publicados por meio do proxy de aplicativo do Azure.

Para saber mais sobre como o Managed Browser, o Microsoft Edge e o Proxy de Aplicativo do Azure AD podem ser usados em conjunto para obter um acesso contínuo (e protegido) a aplicativos Web locais, confira a postagem no blog Enterprise Mobility + Security [Melhores juntos: O Intune e o Azure Active Directory se unem para melhorar o acesso do usuário](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access).

## <a name="how-to-configure-the-homepage-for-a-protected-browser"></a>Como configurar a página inicial de um navegador protegido

Essa definição permite configurar a página inicial que os usuários visualizam ao iniciar um navegador protegido ou criar uma nova guia. 
- Essa configuração mostrará a página da Web no Managed Browser.  Ao invés disso, o Microsoft Edge exibirá um atalho da página inicial.
- O ícone de atalho da página inicial é exibido como um ícone sob o controle de pesquisa.  Ele não pode ser editado ou excluído.
- O atalho da página inicial exibirá o nome da sua organização para diferenciá-lo.  Ele sempre será exibido como o primeiro ícone.

Usando o procedimento para criar uma configuração do aplicativo Microsoft Edge ou Managed Browser, forneça o seguinte par de chave e valor:

|                                Chave                                |                                                           Valor                                                            |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| <strong>com.microsoft.intune.mam.managedbrowser.homepage</strong> | Especifique uma URL válida. URLs incorretas são bloqueadas como medida de segurança.<br>Exemplo: `https://www.bing.com` |

## <a name="how-to-configure-bookmarks-for-a-protected-browser"></a>Como configurar indicadores para um navegador protegido

Essa definição permite configurar um conjunto de indicadores disponível para usuários do Microsoft Edge ou do Managed Browser.

- Esses indicadores não podem ser excluídos ou modificados pelos usuários
- Eles são exibidos na parte superior da lista. Todos os indicadores que os usuários criar são exibidos abaixo desses indicadores.
- Se você tiver habilitado o redirecionamento do Proxy de Aplicativo, será possível adicionar aplicativos Web do Proxy de Aplicativo usando sua URL interna ou externa.

Usando o procedimento para criar uma configuração do aplicativo Microsoft Edge ou Managed Browser, forneça o seguinte par de chave e valor:

|                                Chave                                 |                                                                                                                                                                                                                                                         Valor                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <strong>com.microsoft.intune.mam.managedbrowser.bookmarks</strong> | O valor dessa configuração é uma lista de indicadores. Cada indicador consiste no título e na URL do indicador. Separe o título e a URL com o caractere <strong>&#124;</strong>.<br><br>Exemplo:<br> <code>Microsoft Bing&#124;https://www.bing.com</code><br><br>Para configurar vários indicadores, separe cada par com caractere duplo, <strong>&#124;&#124;</strong><br><br>Exemplo:<br> <code>Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;https://www.contoso.com</code> |

## <a name="how-to-specify-allowed-and-blocked-urls-for-a-protected-browser"></a>Como especificar URLs permitidas e bloqueadas para um navegador protegido

Usando o procedimento para criar uma configuração do aplicativo Microsoft Edge ou Managed Browser, forneça o seguinte par de chave e valor:

|Chave|Valor|
|-|-|
|Escolha:<br><ul><li>Especifique as URLs permitidas (apenas essas URLs são permitidas; nenhum outro site pode ser acessado):<br> **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br></li><li>Especifique as URLs bloqueadas (todos os outros sites podem ser acessados):<br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**</li></ul>|O valor correspondente para a chave é uma lista de URLs. Insira todas as URLs que você deseja permitir ou bloquear como um único valor, separado por um caractere de barra vertical **&#124;** .<br><br>Exemplos:<br><br><code>URL1&#124;URL2&#124;URL3</code><br><code>http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com</code>|

>[!IMPORTANT]
>Não especifique as duas chaves. Se as duas chaves forem direcionadas para o mesmo usuário, a chave de permissão será usada, pois é a opção mais restritiva.
>Além disso, lembre-se de não bloquear páginas importantes como os sites de sua empresa.

### <a name="url-format-for-allowed-and-blocked-urls"></a>Formato de URL para URLs permitidas e bloqueadas
Use as informações a seguir para saber mais sobre os formatos permitidos e caracteres curinga que você pode usar ao especificar URLs para as listas de permitidas e bloqueadas:

- Você pode usar o símbolo de caractere curinga ( **&#42;** ) de acordo com as regras na lista de padrões permitidos a seguir:

- Certifique-se de prefixar todas as URLs com **http** ou **https** ao inseri-las na lista.

- Você pode especificar os números de porta no endereço. Se você não especificar um número da porta, os valores usados serão:

  - Porta 80 para https

  - Porta 443 para https

  Não há suporte para o uso de caracteres curinga no número da porta. Por exemplo, `http://www.contoso.com:;` e `http://www.contoso.com: /;` não são compatíveis.

- Use a tabela a seguir para aprender sobre os padrões permitidos que você pode usar para especificar URLs:

|                  URL                  |                     Detalhes                      |                                                Corresponde a                                                |                                Não corresponde a                                 |
|---------------------------------------|--------------------------------------------------|-------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
|        `http://www.contoso.com`         |              Corresponde a uma única página               |                                            `www.contoso.com`                                            |  `host.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`contoso.com`/   |
|          `http://contoso.com`           |              Corresponde a uma única página               |                                             `contoso.com/`                                              | `host.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`www.contoso.com` |
|    `http://www.contoso.com/&#42;`     | Corresponde a todas as URLs iniciadas por `www.contoso.com` |      `www.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`www.contoso.com/videos/tvshows`      |              `host.contoso.com`<br /><br />`host.contoso.com/images`              |
|    `http://*.contoso.com/*`     |     Corresponde a todos os subdomínios em contoso.com     | `developer.contoso.com/resources`<br /><br />`news.contoso.com/images`<br /><br />`news.contoso.com/videos` |                               `contoso.host.com`                                |
|     `http://www.contoso.com/images`     |             Corresponde a uma única pasta              |                                        `www.contoso.com/images`                                         |                          `www.contoso.com/images/dogs`                          |
|       `http://www.contoso.com:80`       |  Corresponde a uma única página, usando um número da porta   |                                       `http://www.contoso.com:80`                                       |                                                                               |
|        `https://www.contoso.com`        |          Corresponde a uma única página segura           |                                        `https://www.contoso.com`                                        |                            `http://www.contoso.com`                             |
| `http://www.contoso.com/images/&#42;` |    Corresponde a uma única pasta e todas as subpastas    |                  `www.contoso.com/images/dogs`<br /><br />`www.contoso.com/images/cats`                   |                            `www.contoso.com/videos`                             |

- A seguir, exemplos de algumas das entradas que você não pode especificar:

  - `*.com`

  - `*.contoso/*`

  - `www.contoso.com/*images`

  - `www.contoso.com/*images*pigs`

  - `www.contoso.com/page*`

  - Endereços IP

  - `https://*`

  - `http://*`

  - `http://www.contoso.com:*`

  - `http://www.contoso.com: /*`
  
## <a name="soft-transitions-from-work-to-personal-accounts"></a>Transições reversíveis de contas corporativas para contas pessoais

A base da experiência corporativa móvel do Microsoft Edge é o modelo de identidade dupla. Isso significa que o Microsoft Edge tem suporte para identidades corporativas e pessoais. Assim como ocorre nos aplicativos do Office 365 e do Outlook, esse modelo de identidade dupla permite aos usuários finais usar o Microsoft Edge para todas as necessidades de navegação e alternar facilmente entre as duas experiências, com base nas políticas de conteúdo definidas pelo administrador. A navegação no contexto pessoal não é afetada, e as informações corporativas são mantidas estritamente no contexto de trabalho dentro do Microsoft Edge. 

Uma das vantagens desse modelo é que, quando os usuários tentam abrir um link (como um artigo de jornal etc.) para um site não permitido pela organização, eles podem fazê-lo no contexto pessoal que é mantido totalmente separado do contexto de trabalho. Essas transições reversíveis são habilitadas por padrão. 

Usando o procedimento para criar uma configuração do aplicativo Microsoft Edge ou Managed Browser, forneça o seguinte par de chave e valor:

| Chave                                                                | Valor                                                 |
|--------------------------------------------------------------------|-------------------------------------------------------|
| **com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock** | **False** impede a ocorrência dessas transições reversíveis |

## <a name="how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios"></a>Como acessar logs de aplicativos gerenciados usando o Managed Browser no iOS

Os usuários finais com o Browser gerenciado instalado em seu dispositivo iOS podem exibir o status de gerenciamento de todos os aplicativos publicados da Microsoft. Eles podem enviar logs para solucionar problemas de seus aplicativos iOS gerenciados.

1. Abra as **Configurações** do iOS.
2. Selecione as configurações do aplicativo **Browser** gerenciado.
3. Ative **Habilitar Diagnóstico do Intune** para colocar o navegador no modo de solução de problemas.
4. Abra o Managed **Browser**. Clique em **Exibir o Status do Aplicativo Intune** para examinar as configurações de política de aplicativo individual.
5. Pressione **Comece a Usar** e **Compartilhar Logs** ou **Enviar Logs para a Microsoft** para enviar os logs de solução de problemas para seu administrador de TI ou para a Microsoft.

Também é possível abrir o Browser no modo de solução de problemas de dentro do aplicativo.

1. Abra o Managed Browser.
2. Digite `about:intunehelp` na caixa de endereço.
O Browser inicia o modo de solução de problemas.

Para obter uma lista das configurações armazenadas nos logs de aplicativo, consulte [Revisar logs de proteção do aplicativo no Managed Browser](app-protection-policy-settings-log.md).

## <a name="security-and-privacy-for-the-managed-browser"></a>Segurança e privacidade do Managed Browser

- O Managed Browser não usa as configurações feitas pelos usuários para o navegador interno em seus dispositivos. O Managed Browser não tem acesso a essas configurações.

- Se você configurar as opções **Exigir PIN simples para acesso** ou **Exigir credenciais corporativas para acesso** em uma política de proteção de aplicativo associada ao Managed Browser e um usuário selecionar o link de ajuda na página de autenticação, será possível navegar por sites da Internet, independentemente dele ter sido adicionado a uma lista de bloqueio na política.

- O Managed Browser pode bloquear o acesso a sites apenas quando eles são acessados diretamente. Ele não bloqueia o acesso quando serviços intermediários (como um serviço de tradução) são usados para acessar o site.

- Para permitir a autenticação e acessar a documentação do Intune, **&#42;.microsoft.com** é isento das configurações da lista de permissão ou de bloqueio. Ela é sempre permitida.

### <a name="turn-off-usage-data"></a>Desligar os dados de uso
A Microsoft coleta automaticamente dados anônimos sobre o desempenho e o uso do Managed Browser para melhorar os produtos e serviços Microsoft. Os usuários podem desligar a coleta de dados usando a configuração **Dados de Uso** em seus dispositivos. Você não tem controle sobre a coleta desses dados.

- Em dispositivos iOS, sites visitados por usuários que têm um certificado expirado ou não confiável não pode ser abertos.

## <a name="next-steps"></a>Próximas etapas

- [O que são políticas de proteção do aplicativo?](app-protection-policy.md) 
