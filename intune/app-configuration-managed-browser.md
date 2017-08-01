---
title: Gerenciar o acesso via Web com o aplicativo Managed Browser
titleSuffix: Intune on Azure
description: "Implante o aplicativo Managed Browser para restringir a navegação na Web e a transferência de dados da Web para outros aplicativos."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e85306934b68f64bad8c223ac117190607db8473
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2017
---
# <a name="manage-internet-access-using-managed-browser-policies-with-microsoft-intune"></a>Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Managed Browser é um aplicativo de navegação na Web que pode ser baixado em lojas públicas de aplicativos para uso em sua organização. Quando configurado com o Intune, o Managed Browser gerenciado pode ser:
- Usado para acessar sites corporativos e aplicativos SaaS com o Logon Único por meio do serviço MyApps, ao mesmo tempo que mantém os dados da Web protegidos.
- Pré-configurado com uma lista de URLs e domínios para restringir os sites que o usuário pode acessar no contexto corporativo.
- Pré-configurado com uma página inicial e indicadores que você especificar.

Como esse aplicativo tem integração com o SDK do Intune, você também poderá aplicar políticas de proteção de aplicativo a ele, incluindo:
- Controlar o uso de recortar, copiar e colar
- Impedir capturas de tela
- Garantir que os links para conteúdo que os usuários selecionam sejam abertos somente em outros aplicativos gerenciados.

Para ver mais detalhes, consulte [O que são políticas de proteção de aplicativo?](/intune/app-protection-policy)

Aplique essas configurações a dispositivos registrados no Intune, registrados em outro produto de gerenciamento de dispositivos ou a dispositivos que não são gerenciados.

Se os usuários instalarem o Managed Browser por meio da loja de aplicativos e o Intune não gerenciá-lo, ele poderá ser usado como um navegador da Web básico, com suporte para Logon Único por meio do site do Microsoft MyApps. Os usuários são levados diretamente ao site do MyApps, no qual poderão ver todos os seus aplicativos SaaS provisionados.
Embora o Managed Browser não seja gerenciado pelo Intune, ele não pode acessar dados de outros aplicativos gerenciados pelo Intune. 

O Managed Browser não dá suporte ao protocolo criptográfico SSLv3 (Secure Sockets Layer versão 3).

Você pode criar políticas do Managed Browser para os seguintes tipos de dispositivo:

-   Dispositivos que executam o Android 4 e posterior.

-   Dispositivos que executam o iOS 8.0 e posterior

O Intune Managed Browser dá suporte à abertura de conteúdo da Web de [parceiros de aplicativos do Microsoft Intune](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx).

## <a name="create-a-managed-browser-app-configuration"></a>Criar uma configuração de aplicativo do Managed Browser

1.  Entre no portal do Azure.
2.  Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3.  Na folha **Aplicativos móveis** da lista Gerenciar, escolha **Políticas de configuração de aplicativo**.
4.  Na folha **Políticas de configuração de aplicativo**, escolha **Adicionar**.
5.  Na folha **Adicionar configuração de aplicativo**, insira um **Nome** e uma **Descrição** opcional para as definições de configuração de aplicativo.
6.  Para o tipo **Registro de dispositivo**, escolha **Não registrado com o Intune**.
7.  Escolha **Selecionar aplicativos necessários** e, em seguida, na folha **Aplicativos direcionados**, escolha o **Managed Browser** para iOS, Android ou ambos.
8.  Escolha **OK** para retornar à folha **Adicionar configuração de aplicativo**.
9.  Escolha **Definições de Configuração**. Na folha **Configuração**, defina os pares de chave e valor para fornecer as configurações do Managed Browser. Use as próximas seções deste tópico para saber mais sobre os diferentes pares de chave e valor que podem ser definidos.
10. Quando terminar, escolha **OK**.
11. Na folha **Adicionar configuração de aplicativo**, escolha **Criar**.
12. A nova configuração é criada e exibida na folha **Configuração de aplicativo**.

>[!IMPORTANT]
>No momento, o Managed Browser depende de registro automático. Para configurações de aplicativo a serem aplicados, outro aplicativo no dispositivo já deve ser gerenciado pelas políticas de Proteção de Aplicativo do Intune.

## <a name="assign-the-configuration-settings-you-created"></a>Atribuir as definições de configuração criadas

Atribua as configurações a grupos de usuários do Azure AD. Se esse usuário tiver o aplicativo Managed Browser instalado, o aplicativo será gerenciado pelas configurações especificadas.

1. Na folha **Configurações** do painel de gerenciamento de aplicativo móvel do Intune, escolha **Configuração de aplicativo**.
2. Na lista de configurações de aplicativo, selecione aquela que você deseja atribuir.
3. Na próxima folha, escolha **Grupos de Usuários**.
4. Na folha **Grupos de usuários**, selecione o grupo do Azure AD ao qual você deseja atribuir a configuração de aplicativo e, em seguida, escolha **OK**.


## <a name="how-to-configure-application-proxy-settings-for-the-managed-browser"></a>Como definir as configurações de Proxy de Aplicativo para o Managed Browser

O Intune Managed Browser e o [Proxy de Aplicativo do Azure AD]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) podem ser usados juntos para dar suporte aos seguintes cenários para os usuários de dispositivos iOS e Android:

- Um usuário baixa e entra no aplicativo Microsoft Outlook.  As políticas de Proteção de Aplicativo do Intune são aplicadas automaticamente. Elas criptografam os dados salvos e impedem o usuário de transferir arquivos corporativos para aplicativos não gerenciados ou locais no dispositivo. Quando o usuário clica em um link para um site da intranet no Outlook, você pode especificar que o link será aberto no aplicativo Managed Browser, em vez de outro navegador.
O Managed Browser reconhece que este site de intranet foi exposto ao usuário por meio do Proxy de Aplicativo. O usuário será roteado automaticamente por meio do Proxy de Aplicativo para autenticação com qualquer autenticação multifator aplicável e acesso condicional antes de alcançar o site de intranet. Este site, que anteriormente não pôde ser encontrado enquanto o usuário estava remoto, agora está acessível e o link no Outlook funciona conforme o esperado.  

- Um usuário remoto abre o aplicativo Managed Browser e navega para um site da intranet usando a URL interna. O Managed Browser reconhece que este site de intranet foi exposto ao usuário por meio do Proxy de Aplicativo. O usuário será roteado automaticamente por meio do Proxy de Aplicativo para autenticação com qualquer autenticação multifator aplicável e acesso condicional antes de alcançar o site de intranet.
Este site, que anteriormente não pôde ser encontrado enquanto o usuário estava remoto, agora está acessível.  

### <a name="before-you-start"></a>Antes de começar

- Verifique se seus aplicativos internos foram publicados pelo Proxy de Aplicativo do Azure AD.
- Para configurar o Proxy de Aplicativo e publicar aplicativos, consulte a [documentação de instalação]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started#how-to-get-started). 
- Você deve estar usando pelo menos a versão mínima 1.2.0 do aplicativo Managed Browser.
- Usuários do aplicativo Managed Browser tem uma [política de Proteção do Aplicativo Intune]( app-protection-policy.md) atribuída ao aplicativo.
- A só poderá ver o redirecionamento automático para aplicativos de proxy de aplicativo que foram atribuídos a ele.

#### <a name="step-1-enable-automatic-redirection-to-the-managed-browser-from-outlook"></a>Etapa 1: habilitar o redirecionamento automático para do Outlook para o Managed Browser
O Outlook deve ser configurado com uma política de proteção do aplicativo que habilita a configuração para **Restringir conteúdo da Web para exibição no Managed Browser**.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-managed-browser"></a>Etapa 2: atribua uma política de configuração de aplicativo atribuída para o Managed Browser.
Este procedimento configura o aplicativo Managed Browser para usar o redirecionamento de proxy de aplicativo. Usando o procedimento para criar uma configuração do aplicativo Managed Browser, forneça o seguinte par de chave e valor:

|||
|-|-|
|Chave|Valor|
|**com.microsoft.intune.mam.managedbrowser.AppProxyRedirection**|**true**|


## <a name="how-to-configure-the-homepage-for-the-managed-browser"></a>Como configurar a página inicial para o Managed Browser

Essa definição permite configurar a página inicial que os usuários veem ao iniciar o Managed Browser ou criar uma nova guia. Usando o procedimento para criar uma configuração do aplicativo Managed Browser, forneça o seguinte par de chave e valor:

|||
|-|-|
|Chave|Valor|
|**com.microsoft.intune.mam.managedbrowser.homepage**|Especifique uma URL válida. URLs incorretas são bloqueadas como medida de segurança.<br>Exemplo: **https://www.bing.com**|


## <a name="how-to-configure-bookmarks-for-the-managed-browser"></a>Como configurar indicadores para o Managed Browser

Essa definição permite que você configure um conjunto de indicadores disponível para os usuários do Managed Browser.

- Esses indicadores não podem ser excluídos ou modificados pelos usuários
- Eles são exibidos na parte superior da lista. Todos os indicadores que os usuários criar são exibidos abaixo desses indicadores.

Usando o procedimento para criar uma configuração do aplicativo Managed Browser, forneça o seguinte par de chave e valor:

|||
|-|-|
|Chave|Valor|
|**com.microsoft.intune.mam.managedbrowser.bookmarks**|O valor dessa configuração é uma lista de indicadores. Cada indicador consiste no título e na URL do indicador. Separe o título e a URL com o caractere **&#124;**.<br><br>Exemplo: **Microsoft Bing&#124;https://www.bing.com**<br><br>Para configurar vários indicadores, separe cada par com caractere duplo, **&#124;&#124;**<br><br>Exemplo: **Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;https://www.contoso.com**|

## <a name="how-to-specify-allowed-and-blocked-urls-for-the-managed-browser"></a>Como especificar URLs permitidas e bloqueadas para o Managed Browser

Usando o procedimento para criar uma configuração do aplicativo Managed Browser, forneça o seguinte par de chave e valor:

|||
|-|-|
|Chave|Valor|
|Escolha:<br><br>Especificar as URLs permitidas (apenas essas URLs são permitidas; nenhum outro site pode ser acessado): **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br>- Especifique as URLs bloqueadas (todos os outros sites podem ser acessados): <br><br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**|O valor correspondente para a chave é uma lista de URLs. Insira todas as URLs que você deseja permitir ou bloquear como um único valor, separado por um caractere de barra vertical **&#124;**.<br><br>Exemplos:<br><br>-**URL1&#124;URL2&#124;URL3**<br>-**http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com**|

>[!IMPORTANT]
>Não especifique as duas chaves. Se as duas chaves forem direcionadas para o mesmo usuário, a chave de permissão será usada, pois é a opção mais restritiva.
>Além disso, lembre-se de não bloquear páginas importantes como os sites de sua empresa.

### <a name="url-format-for-allowed-and-blocked-urls"></a>Formato de URL para URLs permitidas e bloqueadas
Use as informações a seguir para saber mais sobre os formatos permitidos e caracteres curinga que você pode usar ao especificar URLs para as listas de permitidas e bloqueadas:

-   Você pode usar o símbolo de caractere curinga (**&#42;**) de acordo com as regras na lista de padrões permitidos a seguir:

-   Certifique-se de prefixar todas as URLs com **http** ou **https** ao inseri-las na lista.

-   Você pode especificar os números de porta no endereço. Se você não especificar um número da porta, os valores usados serão:

    -   Porta 80 para https

    -   Porta 443 para https

    Não há suporte para o uso de caracteres curinga no número da porta. Por exemplo, não há suporte para **http&colon;//www&period;contoso&period;com:*;** e **http&colon;//www&period;contoso&period;com: /*;**.

-   Use a tabela a seguir para aprender sobre os padrões permitidos que você pode usar para especificar URLs:

|URL|Detalhes|Corresponde a|Não corresponde a|
    |-------|---------------|-----------|------------------|
    |http://www.contoso.com|Corresponde a uma única página|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
    |http://contoso.com|Corresponde a uma única página|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
    |http://www.contoso.com/&#42;|Corresponde a todas as URLs iniciadas por www.contoso.com|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
    |http://&#42;.contoso.com/&#42;|Corresponde a todos os subdomínios em contoso.com|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
    |http://www.contoso.com/images|Corresponde a uma única pasta|www.contoso.com/images|www.contoso.com/images/dogs|
    |http://www.contoso.com:80|Corresponde a uma única página, usando um número da porta|http://www.contoso.com:80|
    |https://www.contoso.com|Corresponde a uma única página segura|https://www.contoso.com|http://www.contoso.com|
    |http://www.contoso.com/images/&#42;|Corresponde a uma única pasta e todas as subpastas|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   A seguir, exemplos de algumas das entradas que você não pode especificar:

    -   &#42;.com

    -   &#42;.contoso/&#42;

    -   www.contoso.com/&#42;images

    -   www.contoso.com/&#42;images&#42;pigs

    -   www.contoso.com/page&#42;

    -   Endereços IP

    -   https://&#42;

    -   http://&#42;

    -   http://www.contoso.com:&#42;

    -   http://www.contoso.com: /&#42;

## <a name="security-and-privacy-for-the-managed-browser"></a>Segurança e privacidade do Managed Browser

-   Em dispositivos iOS, sites visitados por usuários que têm um certificado expirado ou não confiável não pode ser abertos.

-   O Managed Browser não usa as configurações feitas pelos usuários para o navegador interno em seus dispositivos. O Managed Browser não tem acesso a essas configurações.

-   Se você configurar as opções **Exigir PIN simples para acesso** ou **Exigir credenciais corporativas para acesso** em uma política de proteção de aplicativo associada ao Managed Browser e um usuário selecionar o link de ajuda na página de autenticação, será possível navegar por sites da Internet, independentemente dele ter sido adicionado a uma lista de bloqueio na política.

-   O Managed Browser pode bloquear o acesso a sites apenas quando eles são acessados diretamente. Ele não bloqueia o acesso quando serviços intermediários (como um serviço de tradução) são usados para acessar o site.

-   Para permitir a autenticação e acessar a documentação do Intune, **&#42;.microsoft.com** é isento das configurações da lista de permissão ou de bloqueio. Ela é sempre permitida.

### <a name="turn-off-usage-data"></a>Desligar os dados de uso
A Microsoft coleta automaticamente dados anônimos sobre o desempenho e o uso do Managed Browser para melhorar os produtos e serviços Microsoft. Os usuários podem desligar a coleta de dados usando a configuração **Dados de Uso** em seus dispositivos. Você não tem controle sobre a coleta desses dados.


