---
title: Gerenciar o acesso via Web com o navegador gerenciado | Microsoft Docs
description: "Implante o aplicativo de navegador gerenciado para restringir a navegação na Web e a transferência de dados da Web para outros aplicativos."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc946303-e09b-4d73-8bf4-87742299bc54
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: 3982f05e4c81c26d2eb8bdab3a266597d6aab4df


---

# <a name="manage-internet-access-using-managed-browser-policies-with-microsoft-intune"></a>Gerenciar o acesso à internet usando políticas de navegador gerenciado com o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O navegador gerenciado é um aplicativo de navegação na Web que você pode implantar em sua organização usando o Microsoft Intune. Uma política de navegador gerenciado configura uma lista de permitidos ou uma lista de contatos bloqueados que restringe os sites que podem ser visitados pelos usuários do navegador gerenciado.

Já que este aplicativo é um aplicativo gerenciado, você também pode aplicar políticas de gerenciamento de aplicativos móveis para o aplicativo. Essas políticas podem incluir controlar o uso de recortar, copiar e colar, impedir capturas de tela e garantir que os links para conteúdo que os usuários selecionem sejam abertos somente em outros aplicativos gerenciados. Para detalhes, consulte [Configure and deploy mobile application management policies in the Microsoft Intune console (Configurar e implantar políticas de gerenciamento de aplicativo móvel no console do Microsoft Intune)](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> [!IMPORTANT]
>Se os usuários instalarem o navegador gerenciado da loja de aplicativos e ele não for gerenciado pelo Intune, o seguinte comportamento se aplicará:<br /><br />
iOS – o aplicativo de navegador gerenciado pode ser usado como um navegador da Web básico, mas alguns recursos não estarão disponíveis e ele não será capaz de acessar dados de outros aplicativos gerenciados pelo Intune.<br />
Android – o aplicativo de navegador gerenciado não pode ser usado.<br /><br />
Se os usuários instalarem o navegador gerenciado em um dispositivo iOS com uma versão anterior ao iOS 9, ele não será gerenciado por nenhuma das políticas que você criar. Para garantir que o navegador seja gerenciado pelo Intune, os usuários deverão desinstalar o aplicativo antes de você implantá-lo como um aplicativo gerenciado. No iOS 9 e versões posteriores, se o usuário instalar o navegador gerenciado, será solicitado que ele permita que o navegador seja gerenciado pela política.

Você pode criar políticas de navegador gerenciado para os seguintes tipos de dispositivo:

-   Dispositivos que executam o Android 4 e posterior.

-   Dispositivos que executam o iOS 8.0 e posterior

O navegador gerenciado do Intune dá suporte à abertura de conteúdo da Web de [parceiros de aplicativos do Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

## <a name="create-a-managed-browser-policy"></a>Criar uma política de navegador gerenciado

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** &gt; **Adicionar Política**.

2.  Configure um dos seguintes tipos de política de **Software** :

    -   **Managed Browser (Android 4 e posterior)**

    -   **Managed Browser (iOS 8.0 e posterior)**

    Para obter mais informações sobre como criar e implantar políticas, consulte o tópico [Manage settings and features on your devices with Microsoft Intune Policies (Gerenciar configurações e recursos em seus dispositivos com as políticas do Microsoft Intune)](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Use a tabela a seguir para ajudá-lo a definir as configurações da política de navegador gerenciado:

    - **Nome**. Insira um nome exclusivo para a política de navegador gerenciado para ajudar a identificá-lo no console do Intune.
    - **Descrição**. Forneça uma descrição que proporciona uma visão geral da política de navegador gerenciado e outras informações relevantes que o ajudarão a localizá-la.
    - **Habilite uma lista de permitidas ou lista de bloqueadas para restringir as URLs que o navegador gerenciado pode abrir**. Selecione uma das seguintes opções:
        - **Permitir que o navegador gerenciado abra apenas as URLs listadas abaixo (lista de permissões)**. Especifique uma lista de URLs que o navegador gerenciado pode abrir.
        - **Impedir que o navegador gerenciado abra as URLs listadas abaixo**. Especifique uma lista de URLs cuja abertura pelo navegador gerenciado será bloqueada.
**Observação:** você não pode incluir URLs permitidas e bloqueadas na mesma política de navegador gerenciado.
Para obter mais informações sobre os formatos de URL que pode especificar, consulte **Formato de URL para URLs permitidas e bloqueadas** neste tópico.

4.  Quando tiver terminado, selecione **Salvar Política**.

A nova política aparece no nó **Políticas de configuração** do espaço de trabalho **Política**.

## <a name="create-a-deployment-for-the-managed-browser-app"></a>Crie uma implantação para o aplicativo de navegador gerenciado
Depois de ter criado a política de navegador gerenciado, você pode criar uma implantação de software para o aplicativo de navegador gerenciado e associá-la à política de navegador gerenciado que você criou.

> [!IMPORTANT]
> Políticas de navegador gerenciado não são implantadas da mesma maneira que outras políticas do Intune. Esse tipo de política deve ser associado ao pacote de software gerenciado do navegador.

Implantar o aplicativo, garantindo que você selecione a política de navegador gerenciado na página **Gerenciamento de Aplicativo Móvel** para associar a política ao aplicativo.

Para mais informações sobre como implantar aplicativos, consulte [Deploy apps in Microsoft Intune (Implantar aplicativos no Microsoft Intune)](deploy-apps-in-microsoft-intune.md).

## <a name="security-and-privacy-for-the-managed-browser"></a>Segurança e privacidade para o navegador gerenciado

-   Em dispositivos iOS, sites visitados por usuários que têm um certificado expirado ou não confiável não pode ser abertos.

-   As configurações realizadas pelos usuários para o navegador interno em seus dispositivos não são usadas pelo navegador gerenciado. Isso ocorre porque o navegador gerenciado não tem acesso a essas configurações.

-   Se você configurar as opções **Exigir PIN simples para acesso** ou **Exigir credenciais corporativas para acesso** em uma política de gerenciamento de aplicativo móvel associada ao navegador gerenciado e um usuário selecionar o link de ajuda na página de autenticação, eles poderão navegar por qualquer site da Internet, independentemente dele ter sido adicionado a uma lista de bloqueados na política de navegador gerenciado.

-   O navegador gerenciado pode bloquear o acesso a sites apenas quando eles são acessados diretamente. Ele não pode bloquear o acesso quando serviços intermediários (como um serviço de tradução) são usados para acessar o site.

-   Para permitir a autenticação e garantir que a documentação possa ser acessada, **&#42;.microsoft.com** é isenta das configurações da lista de permitidos ou bloqueados. Ela é sempre permitida.

### <a name="turn-off-usage-data"></a>Desligar os dados de uso
A Microsoft coleta automaticamente dados anônimos sobre o desempenho e o uso do navegador gerenciado para aprimorar os produtos e serviços Microsoft. Os usuários podem desligar a coleta de dados usando a configuração **Dados de Uso** em seus dispositivos. Você não tem controle sobre a coleta desses dados.

## <a name="reference-information"></a>Informações de referência

### <a name="url-format-for-allowed-and-blocked-urls"></a>Formato de URL para URLs permitidas e bloqueadas
Use as informações a seguir para saber mais sobre os formatos permitidos e caracteres curinga que você pode usar ao especificar URLs para as listas de permitidas e bloqueadas:

-   Você pode usar o símbolo de caractere curinga (**&#42;**) de acordo com as regras na lista de padrões permitidos abaixo.

-   Certifique-se de prefixar todas as URLs com **http** ou **https** ao inseri-las na lista.

-   Você pode especificar os números de porta no endereço. Se você não especificar um número de porta, os valores usados serão:

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
    |http://www.contoso.com:80|Corresponde a uma única página, usando um número da porta|http://www.contoso.com:80||
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

### <a name="how-conflicts-between-the-allow-and-block-list-are-resolved"></a>Como os conflitos entre a lista de permissões e bloqueios são resolvidos
Se várias políticas de navegador gerenciado forem implantadas em um dispositivo e houver conflitos entre as configurações, o modo (permitir ou bloquear) e as listas de URLs são avaliados quanto aos conflitos. Em caso de conflitos, o comportamento a seguir se aplica:

-   Se os modos de cada política forem os mesmos, mas as listas de URLs forem diferentes, as URLs não serão impostas ao dispositivo.

-   Se os modos de cada política forem diferentes, mas as listas de URLs forem as mesmas, as URLs não serão impostas ao dispositivo.

-   Se um dispositivo estiver recebendo políticas de navegador gerenciado pela primeira vez e houver conflito entre duas políticas, as URLs não serão impostas ao dispositivo. Use o nó **Conflitos de Política** do espaço de trabalho **Política** para ver os conflitos.

-   Se um dispositivo já tiver recebido uma política de navegador gerenciado e uma segunda política for implantada com configurações conflitantes, as configurações originais permanecerão no dispositivo. Use o nó **Conflitos de Política** do espaço de trabalho **Política** para ver os conflitos.



<!--HONumber=Dec16_HO5-->


