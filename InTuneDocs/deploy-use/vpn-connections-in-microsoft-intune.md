---
title: "Conexões VPN | Microsoft Docs"
description: "Use perfis de VPN para implantar as configurações de VPN para usuários e dispositivos na sua organização."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0154e3bfeac0457de57257045e3e7ce833325bce
ms.openlocfilehash: a462bcfa107bf1a37ea4e84bc3d88d0dd81f9fc8
ms.lasthandoff: 02/03/2017


---

# <a name="vpn-connections-in-microsoft-intune"></a>Conexões VPN no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Redes virtuais privadas (VPN) oferecem aos usuários acesso remoto seguro à rede da empresa. Dispositivos usam um *perfil de conexão VPN* para iniciar uma conexão com o servidor VPN. Use *perfis de VPN* no Microsoft Intune para implantar configurações de VPN para usuários e dispositivos na organização, para que eles possam se conectar à rede de forma fácil e segura.

Por exemplo, suponha que você deseje provisionar todos os dispositivos iOS com as configurações necessárias para conectar a um compartilhamento de arquivos na rede corporativa. Você cria um perfil de VPN que contém as configurações necessárias para conectar à rede corporativa e implanta esse perfil a todos os usuários com dispositivos iOS. Os usuários veem a conexão VPN na lista de redes disponíveis e podem se conectar com esforço mínimo.

Você pode configurar os seguintes tipos de dispositivo usando perfis VPN:

* Dispositivos que executam o Android 4 e posterior
* Dispositivos Android for Work
* Dispositivos que executam o iOS 8.0 e posterior
* Dispositivos que executam Mac OS X 10.9 e versões posteriores
* Dispositivos registrados que executam o Windows 8.1 e versões posteriores
* Dispositivos que executam o Windows Phone 8.1 e versões posteriores
* Dispositivos que executam o Windows 10 Desktop e Mobile

As opções de configuração do perfil VPN são diferentes dependendo do tipo de dispositivo selecionado.

## <a name="vpn-connection-types"></a>Tipos de conexão VPN

O Intune dá suporte para a criação de perfis de VPN que usam os seguintes tipos de conexão:


Tipo de conexão |iOS e Mac OS X  |Android e Android for Work|Windows 8.1|Windows RT 8.1|Windows Phone 8.1|Windows 10 Desktop e Mobile |
----------------|------------------|-------|-----------|----------|--------------|-----------------|----------------------|
Cisco AnyConnect|Sim |Sim   |Não    |Não  |Não    | Sim (OMA-URI, somente celulares)|     
Cisco (IPsec)|Sim |Sim   |Não  |Não  |Não | Não|
Citrix|Sim |Sim (Somente Android)   |Não  |Não  |Não | Não|
Pulse Secure|Sim  |Sim |Sim   |Sim  |Sim| Sim|        
F5 Microsoft Edge Client|Sim |Sim |Sim |Sim  |   Sim |  Sim|   
Dell SonicWALL Mobile Connect|Sim |Sim |Sim |Sim |Sim |Sim|         
CheckPoint Mobile VPN|Sim |Sim |Sim |Sim|Sim|Sim|
Microsoft SSL (SSTP)|Não |Não |Não |Não|Não|VPNv1 OMA-URI*|
Microsoft Automatic|Não |Não |Não |Não|Sim (OMA-URI)|Sim|
IKEv2|Perfil personalizado do iOS|Não |Não |Não|Sim (OMA-URI)|Sim|
PPTP|Perfil personalizado do iOS|Não |Não |Não|Não|Sim|
L2TP|Perfil personalizado do iOS|Não |Não |Não|Sim (OMA-URI)|Sim|

\* Sem configurações adicionais que estariam disponíveis para o Windows 10.

> [!IMPORTANT]
> Antes de poder usar perfis VPN implantados em um dispositivo, você deve instalar o aplicativo VPN aplicável para o perfil. Você pode usar as informações no tópico [Implantar aplicativos com o Microsoft Intune](deploy-apps-in-microsoft-intune.md) para ajudá-lo a implantar o aplicativo desejado usando o Intune.  

 Saiba como criar perfis de VPN personalizados usando configurações de URI em [Configurações personalizadas para perfis de VPN](create-custom-vpn-profiles.md).     

## <a name="methods-of-securing-vpn-profiles"></a>Métodos para proteger perfis de VPN

Perfis VPN podem usar uma série de tipos de conexão e protocolos diferentes, de fabricantes diferentes. Essas conexões geralmente são protegidas usando um destes dois métodos.

### <a name="certificates"></a>Certificados

Ao criar o perfil de VPN, você escolhe um perfil de certificado SCEP ou .PFX criado anteriormente no Intune. Isso é conhecido como certificado de identidade. Ele é usado para autenticar um perfil de certificado confiável (ou *certificado raiz*) que você criou para estabelecer que o dispositivo do usuário tem permissão para se conectar. O certificado confiável é implantado no computador que autentica a conexão de VPN, em geral, o servidor VPN.

Para obter mais informações sobre como criar e usar perfis de certificado no Intune, consulte [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Proteger o acesso a recursos com perfis de certificado).

### <a name="user-name-and-password"></a>Nome e senha do usuário

O usuário autentica no servidor VPN, fornecendo seu nome de usuário e senha.

## <a name="create-a-vpn-profile"></a>Criar um perfil VPN

1. No [console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** > **Adicionar Política**.
2. Selecione um modelo para a nova política expandindo o tipo de dispositivo relevante e escolha o perfil VPN para o dispositivo:
    * **Perfil de VPN (Android 4 e posterior)**
    * **Perfil de VPN (Android for Work)**
    * **Perfil de VPN (iOS 8.0 e posterior)**
    * **Perfil de VPN (Mac OS X 10.9 e posterior)**
    * **Perfil de VPN (Windows 8.1 e posterior)**
    * **Perfil de VPN (Windows Phone 8.1 e posterior)**
    * **Perfil da VPN (Windows 10 Desktop e Mobile e posterior)**

 Você só pode criar e implantar uma política personalizada do perfil VPN. Configurações recomendadas não estão disponíveis.

> [!Note]
> Um perfil VPN para dispositivos Android for Work habilitará uma conexão VPN apenas para aplicativos instalados no perfil de trabalho do dispositivo.
>
> Alguns tipos de conexão VPN dão suporte a VPN por aplicativo para dispositivos Android for Work e para habilitar VPN por aplicativo em aplicativos distribuídos por meio do Intune.  

3. Use a tabela a seguir para ajudá-lo a definir configurações de perfil de VPN:

Nome da configuração  |Mais informações  
---------|---------
**Nome**     |Insira um nome exclusivo para o perfil de VPN que ajude a identificá-lo no console do Intune.         
**Descrição**     |Forneça uma descrição que indica uma visão geral do perfil de VPN e outras informações relevantes que o ajudarão a localizá-lo.         
**Nome da conexão VPN (exibido aos usuários)**     |Especifique um nome para o perfil VPN. Esse é o nome que os usuários verão na lista de conexões VPN disponíveis em seus dispositivos.         
**Tipo de conexão**     |  Selecione um dos seguintes tipos de conexão para usar no perfil de VPN: **Cisco AnyConnect** (não está disponível para Windows 8.1 ou Windows Phone 8.1), **Pulse Secure**, **Citrix**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**.
**Descrição do servidor VPN**     | Especifique uma descrição para o servidor VPN ao qual os dispositivos se conectarão. Exemplo: **Servidor VPN Contoso**. Quando o tipo de conexão é **F5 Microsoft Edge Client**, use o campo **Lista de servidores** para especificar uma lista de descrições de servidores e endereços IP.
**Endereço IP do servidor ou o FQDN**    |Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos vão se conectar. Exemplos: **192.168.1.1**, **vpn.contoso.com**.  Quando o tipo de conexão é **F5 Microsoft Edge Client**, use o campo **Lista de servidores** para especificar uma lista de descrições de servidores e endereços IP.         |         
**Lista de servidores**     |Clique em **Adicionar** para adicionar um novo servidor VPN a ser usado para a conexão VPN. Você também pode especificar qual servidor será o padrão para a conexão. Essa opção somente é exibida somente quando o tipo de conexão é **F5 Microsoft Edge Client**.         
**Enviar todo o tráfego de rede através da conexão VPN**     |Se você selecionar essa opção, todo o tráfego é enviado pela conexão VPN. Se você não selecionar essa opção, o cliente negociará dinamicamente as rotas para criar um túnel dividido ao se conectar ao servidor VPN de terceiros. Apenas as conexões com a rede da empresa são enviadas por um túnel VPN. O túnel VPN não é usado quando você se conecta aos recursos na Internet.
**Método de autenticação**| Selecione o método de autenticação usado pela conexão VPN: **Certificados** ou **Nome de Usuário e Senha**. (**Nome de Usuário e Senha** não está disponível quando o tipo de conexão é Cisco AnyConnect.) A opção **Método de Autenticação** não está disponível para Windows 8.1.
**Lembrar as credenciais do usuário a cada logon**|Selecione esta opção para garantir que as credenciais do usuário sejam lembradas para que o usuário não precise digitar as credenciais sempre que uma conexão for estabelecida.
**Selecione um certificado de cliente para autenticação de cliente (certificado de identidade)**|Selecione o certificado do protocolo SCEP cliente que você criou anteriormente e que será usado para autenticar a conexão do VPN. Para obter mais informações sobre como usar perfis de certificado no Intune, consulte [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Proteger o acesso a recursos com perfis de certificado). Essa opção é exibida somente quando o método de autenticação é **Certificados**.
**Função**| Especifique o nome da função do usuário que tem acesso a essa conexão. Uma função de usuário define configurações e opções pessoais e habilita ou desabilita determinados recursos de acesso. Essa opção é exibida somente quando o tipo de conexão é **Pulse Secure** ou **Citrix**.
**Território**|Especifique o nome do território de autenticação que você deseja usar. Um realm de autenticação é um agrupamento de recursos de autenticação usado pelos tipos de conexão Pulse Secure ou Citrix. Essa opção é exibida somente quando o tipo de conexão é **Pulse Secure** ou **Citrix**.
**Grupo de logon ou domínio**|Especifique o nome do grupo de logon ou domínio ao qual você deseja se conectar. Essa opção é exibida somente quando o tipo de conexão é **Dell SonicWALL Mobile Connect**.
**Impressão digital**|Especifique uma cadeia de caracteres, (por exemplo "Código de impressões digitais da Contoso") que será usado para verificar se o servidor VPN é confiável. Uma impressão digital pode ser enviada ao cliente para que ele saiba que pode confiar em qualquer servidor que apresentar essa impressão digital durante a conexão. Se o dispositivo não tiver a impressão digital, ele solicitará ao usuário para confiar no servidor VPN durante a conexão enquanto mostra a impressão digital. (O usuário verifica a impressão digital e manualmente clica em **confiar** para se conectar.) Essa opção é exibida somente quando o tipo de conexão é **CheckPoint Mobile VPN**.
**Por VPN de Aplicativo**|Selecione esta opção se você deseja associar essa conexão VPN a um aplicativo iOS ou Mac OS X para que a conexão seja aberta quando o aplicativo é executado. Você pode associar o perfil VPN a um aplicativo ao implantar o software. Para obter mais informações, consulte [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) (Implantar aplicativos no Microsoft Intune).
**VPN sob demanda**|Você pode configurar a VPN sob demanda para dispositivos iOS 8.0 e posteriores. Confira as instruções para configurar isso em [VPN sob demanda para dispositivos iOS](#on-demand-vpn-for-ios-devices).
**Detectar automaticamente as configurações de proxy** (iOS, Mac OS X, Windows 8.1 e Windows Phone 8.1 apenas)|Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja que os dispositivos detectem automaticamente as configurações de conexão. Para obter mais informações, consulte a documentação do Windows Server.
**Usar script de configuração automática** (iOS, Mac OS X, Windows 8.1 e Windows Phone 8.1 apenas)|Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja usar um script de configuração automática para definir as configurações e especifique uma URL para o arquivo que contém as configurações. Para obter mais informações, consulte a documentação do Windows Server.
**Usar servidor proxy** (iOS, Mac OS X, Windows 8.1 e Windows Phone 8.1 apenas)|Se o servidor VPN exigir um servidor proxy para a conexão, selecione essa opção e especifique o número da porta e endereço do servidor proxy. Para obter mais informações, consulte a documentação do Windows Server.
**Bypass de configurações de proxy para endereços locais** (iOS, Mac OS X, Windows 8.1 e Windows Phone 8.1 apenas)|Se o servidor VPN exigir um servidor proxy para a conexão, selecione esta opção se você não quiser usar o servidor proxy para endereços locais que você especificar. Para obter mais informações, consulte a documentação do Windows Server.
**XML personalizado** (Windows 8.1 e posterior e Windows Phone 8.1 e posterior)|Especifique comandos XML personalizados para configurar a conexão VPN. Exemplo para **Pulse Secure**: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. Exemplo para **CheckPoint Mobile VPN**: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;. Exemplo para **Dell SonicWALL Mobile Connect**: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. Exemplo para **F5 Edge Client**: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. Consulte a documentação do VPN de cada fabricante para obter mais informações sobre como escrever comandos XML personalizados.
**Lista de pesquisa de sufixo DNS** (somente Windows Phone 8.1)|Especifique um sufixo DNS em cada linha. Cada sufixo DNS que você especificar será pesquisado durante a conexão com um site usando um nome curto. Por exemplo, especifique os sufixos DNS **domain1.contoso.com** e **domain2.contoso.com**, acesse a URL **http://mywebsite**, e as URLs **http://mywebsite.domain1.contoso.com** e **http://mywebsite.domain2.contoso.com** serão pesquisadas.
**Bypass de VPN quando conectado à rede da Wi-Fi empresarial** (somente Windows Phone 8.1)|Selecione esta opção para especificar que a conexão VPN não será usada quando o dispositivo estiver conectado à rede Wi-Fi da empresa.
**Bypass de VPN quando conectado à rede Wi-Fi doméstica** (somente Windows Phone 8.1)|Selecione esta opção para especificar que a conexão VPN não será usada quando o dispositivo estiver conectado à rede Wi-Fi doméstica.

As configurações adicionais a seguir estão disponíveis para dispositivos Windows 10 Desktop e Mobile.

Nome da configuração  |Mais informações  
---------|---------
**Regras de tráfego de rede**|Selecione quais protocolos e quais portas local e remota e os intervalos de endereços serão habilitados para a conexão VPN. Se você não criar uma regra de tráfego de rede, todos os protocolos, portas e intervalos de endereços serão habilitados. Após você criar uma regra, a conexão VPN usará somente os protocolos, portas e intervalos de endereços que você especificar na regra.
**Rotas**|Selecione quais rotas usarão a conexão VPN.
**Servidores DNS**| Selecione quais servidores DNS a conexão VPN usará depois que a conexão for estabelecida.         
**Aplicativos associados**|Forneça uma lista de aplicativos que usarão automaticamente a conexão VPN. O tipo de aplicativo determinará o identificador do aplicativo. Para um aplicativo universal, forneça o nome da família de pacotes. Para um aplicativo da área de trabalho, forneça o caminho do arquivo do aplicativo.          


> [!IMPORTANT]
> É recomendável que você proteja todas as listas de aplicativos compiladas para uso na configuração de VPN por aplicativo. Se um usuário não autorizado modificar sua lista e você o importar para a lista de aplicativo VPN por aplicativo, você potencialmente autorizará o acesso VPN para aplicativos que não deveriam ter acesso. É uma maneira de proteger as listas de aplicativo usando uma ACL (lista de controle de acesso).

Aqui está um exemplo de quando você pode usar configurações para limites corporativos. Se você quiser habilitar VPN apenas para a área de trabalho remota, crie uma regra de tráfego de rede que permita o tráfego para o protocolo 27 na porta externa 3996. Nenhum outro tráfego usará a VPN.

Definir rotas em limites corporativos é útil quando o tipo de conexão VPN não permite definir como o tráfego é tratado no túnel dividido. Nesse caso, use **Rotas** para listar as rotas que usarão VPN.

Você pode restringir o uso de VPN para dispositivos Windows 10 a aplicativos específicos criando uma configuração personalizada do URI OMA.

A nova política aparece no nó **Políticas de configuração** do espaço de trabalho **Política**.

### <a name="on-demand-vpn-for-ios-devices"></a>VPN sob demanda para dispositivos iOS
Você pode configurar a VPN sob demanda para dispositivos iOS 8.0 e posterior.

> [!NOTE]
>  
> É possível usar a VPN por aplicativo e a VPN sob demanda na mesma política.

1. Na página de configuração da política, localize **Regras sob demanda para esta conexão VPN**. As colunas recebem o nome de **Correspondência**, que é a condição que as regras devem conferir, e **Ação**, a ação que a política disparará quando houver correspondência da condição.
2. Escolha **Adicionar** para criar uma regra. Há dois tipos de correspondências que podem ser definidas na regra. Você só pode configurar um desses tipos por regra.
  - **SSIDs**, que se refere a redes sem fio.
  - **Domínios de pesquisa de DNS**, que são...  Você pode usar nomes de domínio totalmente qualificados, como *team.corp.contoso.com*, ou usar domínios como *contoso.com*, que é o equivalente a usar * .contoso.com. **
3. Opcional: forneça uma investigação de cadeia de caracteres de URL, que é uma URL usada pela regra como um teste. Se o dispositivo no qual esse perfil está instalado for capaz de acessar essa URL sem redirecionamento, a VPN será estabelecida e o dispositivo se conectará à URL de destino. O usuário não verá o site da investigação de cadeia de caracteres de URL. Um exemplo de uma investigação de cadeia de caracteres de URL é o endereço de um servidor Web de auditoria que verifica a conformidade do dispositivo antes da conexão com a VPN. Outra possibilidade é que a URL teste a capacidade da VPN de se conectar a um site, antes de conectar o dispositivo à URL de destino por meio da VPN.
4. Escolha uma destas ações:
  - **Conectar**
  - **Avaliar conexão**, que tem três configurações a. **Ação de domínio** - escolha **Conectar se necessário** ou **Nunca se conectar**
     b. **Lista de domínios separados por vírgulas** - configure essa opção somente se você escolher uma **Ação de domínio** do tipo **Conectar se necessário** 
     c. **Investigação de cadeia de caracteres de URL necessária** - uma URL HTTP ou HTTPS (preferencial) URL, como *https://vpntestprobe.contoso.com*. A regra verificará se há uma resposta proveniente desse endereço. Se não houver, e a **Ação de domínio** for **Conectar se necessário**, a VPN será disparada.
      
     > [!TIP]
     >
     >Um exemplo de quando você pode usar essa ação é quando alguns sites em sua rede corporativa exigirem uma conexão de rede corporativa de VPN ou direta, mas outros não. Se você listar em **Lista separada por vírgulas de domínios de pesquisa DNS** *corp.contoso.com*, poderá escolher **Conectar se necessário** e listar sites específicos dentro dessa rede que podem exigir a VPN, como *sharepoint.corp.contoso.com*. Em seguida, a regra verificará se *vpntestprobe.contoso.com* pode ser acessado. Se não puder, a VPN será disparada para o site do SharePoint.
  - **Ignorar** - isso não causa qualquer alteração na conectividade da VPN. Se a VPN estiver conectada, deixe-a conectada, e se não estiver conectada, não a conecte. Por exemplo, talvez você tenha uma regra que conecta a VPN a todos os seus sites corporativos internos, mas você queira disponibilizar um desses sites internos somente quando o dispositivo estiver realmente conectado à rede corporativa. Nesse caso, crie uma regra ignorar para esse site.
  - **Desconectar** - desconecte dispositivos da VPN quando as condições forem atendidas. Por exemplo, você pode listar suas redes sem fio corporativas no campo **SSIDs** e criar uma regra que desconecta os dispositivos da VPN quando eles se conectarem a uma dessas redes.

As regras específicas de domínio são avaliadas antes das regras de todos os domínios.


## <a name="deploy-the-policy"></a>Implantar a política

1.  No espaço de trabalho **Política**, selecione a política que deseja implantar e selecione **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar implantação**:

    -   Para implantar a política, selecione um ou mais grupos aos quais você deseja implantar a política e selecione **Adicionar** &gt; **OK**.

    -   Para fechar a caixa de diálogo sem implantá-la, escolha **Cancelar**.


Após a implantação bem-sucedida, os usuários verão o nome da conexão VPN especificado na lista de conexões de VPN em seus dispositivos.

Um resumo de status e alertas na página **Visão geral** do espaço de trabalho **Política** identifica problemas com a política que exigem atenção. Além disso, um resumo de status aparece no espaço de trabalho Painel.

