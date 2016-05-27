---
# required metadata

title: Conexões VPN (rede virtual privada) | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Conexões VPN no Microsoft Intune
 Redes virtuais privadas (VPN) permitem oferecer aos usuários acesso remoto seguro à rede da empresa. Os usuários remotos podem trabalhar como se o dispositivo estivesse fisicamente conectado à rede. Dispositivos usam um perfil de conexão VPN para iniciar uma conexão com o servidor VPN. Use **perfis de VPN** no Microsoft Intune para implantar configurações de VPN para usuários e dispositivos na organização. Ao implantar essas configurações, você minimiza o esforço do usuário final necessário para conectar-se aos recursos na rede da empresa.

Por exemplo, você deseja provisionar todos os dispositivos iOS com as configurações necessárias para conectar a um compartilhamento de arquivos na rede corporativa. Você cria um perfil de VPN contendo as configurações necessárias para conectar à rede corporativa e implanta esse perfil a todos os usuários com dispositivos iOS. Os usuários veem a conexão VPN na lista de redes disponíveis e podem se conectar com mínimo esforço.

Você pode configurar os seguintes tipos de dispositivo com perfis VPN:

* Dispositivos que executam o Android 4 e versões posteriores
* Dispositivos que executam o iOS 7.1 e versões posteriores
* Dispositivos que executam Mac OS X 10.9 e versões posteriores
* Dispositivos registrados que executam o Windows 8.1 e versões posteriores
* Dispositivos que executam o Windows Phone 8.1 e versões posteriores
* Dispositivos que executam o Windows 10 Desktop e Mobile.

As opções de configuração do perfil VPN serão diferente dependendo do tipo de dispositivo selecionado.

## Tipos de conexão VPN

O Intune dá suporte para a criação de perfis de VPN que usam os seguintes tipos de conexão:




Tipo de conexão |iOS e Mac OS X  |Android  |Windows 8.1|Windows RT|Windows RT 8.1|Windows Phone 8.1  |Windows 10 Desktop e Mobile |
---------|---------|---------|---------|---------|---------
Cisco AnyConnect |Sim |Sim   |Não    |     Não    |Não  |Não    | Sim, (OMA-URI, somente celulares)|     
Pulse Secure |Sim  |Sim |Sim   |Não  |Sim  |Sim| Sim|        
F5 Edge Client |Sim |Sim |Sim |Não  |Sim  |   Sim |  Sim|   
Dell SonicWALL Mobile Connect |Sim |Sim |Sim |Não  |Sim |Sim |Sim|         
CheckPoint Mobile VPN |Sim |Sim |Sim |Sim |Sim|Sim|Sim|




> [!IMPORTANT] Antes de poder usar perfis VPN implantados em um dispositivo, você deve instalar o aplicativo VPN aplicável para o perfil. Você pode usar as informações no tópico [Deploy apps with Microsoft Intune](deploy-apps-in-microsoft-intune.md) (Implantar aplicativos com o Microsoft Intune) para ajudá-lo a implantar o aplicativo desejado usando o Intune.  

 Saiba como criar perfis de VPN personalizados usando configurações de URI em [Custom configurations for VPN profiles](custom-configurations-for-vpn-profiles.md) (Configurações personalizadas para perfis de VPN).     

## Como os perfis VPN são protegidos

Perfis VPN podem usar uma série de tipos de conexão e protocolos diferentes, de fabricantes diferentes. Essas conexões são geralmente protegidas usando um destes dois métodos:

### Certificados

Ao criar o perfil de VPN, você escolhe um perfil de certificado SCEP ou .PFX criado anteriormente no Intune.

Isso é conhecido como certificado de identidade e é usado para autenticar em relação a um perfil de certificado confiável (ou um certificado raiz) que você criou para estabelecer que o dispositivo do usuário tem permissão para se conectar. O certificado confiável é implantado no computador que autentica a conexão de VPN, em geral, o servidor VPN.

Para obter mais informações sobre como criar e usar perfis de certificado no Intune, consulte [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Proteger o acesso a recursos com perfis de certificado).

### Nome de usuário e senha

O usuário autentica para o servidor VPN, fornecendo seu nome de usuário e senha.

## Criar um perfil VPN

1. No [Console de Administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política > Adicionar Política**.
2. Selecione um modelo para a nova política expandindo o tipo de dispositivo relevante e escolha o perfil VPN para o dispositivo:
    * **Perfil de VPN (Android 4 e posterior)**
    * **Perfil de VPN (iOS 7.1 e posterior)**
    * **Perfil VPN (Mac OS X 10.9 e superior)**
    * **Perfil de VPN (Windows 8.1 e posterior)**
    * **Perfil de VPN (Windows Phone 8.1 e posterior)**
    * **Perfil da VPN (Windows 10 Desktop e Mobile e posterior)**

    Você só pode criar e implantar uma política personalizada do perfil VPN. Configurações recomendadas não estão disponíveis.

3. Use a tabela a seguir para ajudá-lo a definir configurações de perfil de VPN:

Nome da configuração  |Mais informações  
---------|---------
**Nome**     |Insira um nome exclusivo para o perfil de VPN que ajude a identificá-lo no console do Intune.         
**Descrição**     |Forneça uma descrição que indica uma visão geral do perfil de VPN e outras informações relevantes que o ajudarão a localizá-lo.         
**Nome da conexão VPN (exibido aos usuários)**     |Especifique um nome para o perfil VPN. Esse é o nome que os usuários verão na lista de conexões VPN disponíveis em seus dispositivos.         
**Tipo de conexão**     |  Selecione um dos seguintes tipos de conexão para usar no perfil de VPN: **Cisco AnyConnect** (não está disponível para Windows 8.1 ou Windows Phone 8.1), **Pulse Secure**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**
**Descrição do servidor VPN**     | Especifique uma descrição para o servidor VPN ao qual os dispositivos se conectarão. **Exemplo:** Servidor VPN Contoso. Quando o tipo de conexão é **F5 Edge Client**, use o campo **Lista de servidores** para especificar uma lista de descrições de servidores e endereços IP.
**Endereço IP do servidor ou o FQDN**    |Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos vão se conectar. **Exemplos:** 192.168.1.1, vpn.contoso.com.  Quando o tipo de conexão é **F5 Edge Client**, use o campo **Lista de servidores** para especificar uma lista de descrições de servidores e endereços IP.         |         
**Lista de servidores**     |Clique em **Adicionar** para adicionar um novo servidor VPN a ser usado para a conexão VPN. Você também pode especificar qual servidor deve ser o padrão para a conexão. Essa opção somente é exibida quando o tipo de conexão é **F5 Edge Client**.         
**Enviar todo o tráfego de rede através da conexão VPN**     |Se você selecionar essa opção, todo o tráfego é enviado pela conexão VPN. Se você não selecionar essa opção, o cliente negocia dinamicamente as rotas para criar um túnel dividido ao se conectar ao servidor VPN de terceiros. Apenas as conexões com a rede da empresa são enviadas por um túnel VPN. O túnel VPN não é usado quando você se conecta aos recursos na Internet.
**Método de autenticação**| Selecione o método de autenticação usado pela conexão VPN: **Certificados** ou **Nome de Usuário e Senha**. (Nome de Usuário e Senha não está disponível quando o tipo de conexão é Cisco AnyConnect.) A opção **Método de Autenticação** não está disponível para Windows 8.1.
**Lembrar as credenciais do usuário a cada logon**|Selecione esta opção para garantir que as credenciais do usuário sejam lembradas para que o usuário não precise digitar as credenciais sempre que uma conexão for estabelecida.
**Selecione um certificado de cliente para autenticação de cliente (certificado de identidade)**|Selecione o certificado do protocolo SCEP cliente que você criou anteriormente e que será usado para autenticar a conexão do VPN. Para obter mais informações sobre como usar perfis de certificado no Intune, consulte [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Proteger o acesso a recursos com perfis de certificado). Essa opção é exibida somente quando o método de autenticação é **Certificados**.
**Função**| Especifique o nome da função do usuário que tem acesso a essa conexão. Uma função de usuário define configurações pessoais, opções e habilita ou desabilita determinados recursos de acesso. Essa opção somente é exibida quando o tipo de conexão é **Pulse Secure**.
**Território**|Especifique o nome do território de autenticação que você deseja usar. Um realm de autenticação é um agrupamento de recursos de autenticação usado pelo tipo de conexão Pulse Secure. Essa opção somente é exibida quando o tipo de conexão é **Pulse Secure**.
**Grupo de logon ou domínio**|Especifique o nome do grupo de logon ou domínio ao qual você deseja se conectar. Essa opção somente é exibida quando o tipo de conexão é **Dell SonicWALL Mobile Connect**.
**Impressão digital**|Especifique uma cadeia de caracteres, por exemplo "Código de impressões digitais da Contoso" que será usado para verificar se o servidor VPN é confiável. Uma impressão digital pode ser: enviada ao cliente para que ele saiba que pode confiar em qualquer servidor que apresentar essa impressão digital durante a conexão. Se o dispositivo ainda não tiver a impressão digital, ele solicitará ao usuário para confiar no servidor VPN enquanto mostra a impressão digital (o usuário verifica a impressão digital manualmente e clica em **Confiar** para se conectar). Essa opção somente é exibida quando o tipo de conexão é **CheckPoint Mobile VPN**.
**VPN por aplicativo**|Selecione esta opção se você deseja associar essa conexão VPN a um aplicativo iOS do Mac OS X para que a conexão seja aberta quando o aplicativo é executado. Você pode associar o perfil VPN a um aplicativo ao implantar o software. Para obter mais informações, consulte [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) (Implantar aplicativos no Microsoft Intune)
**Detectar automaticamente as configurações de proxy** (iOS, Mac OS X, Windows 8.1 e Windows Phone 8.1 apenas)|Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja que os dispositivos detectem automaticamente as configurações de conexão. Para obter mais informações, consulte a documentação do Windows Server.
**Usar script de configuração automática** (iOS, Mac OS X, Windows 8.1 e Windows Phone 8.1 apenas)|Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja usar um script de configuração automática para definir as configurações e especifique uma URL para o arquivo que contém as configurações. Para obter mais informações, consulte a documentação do Windows Server.
**Usar servidor proxy** (iOS, Mac OS X, Windows 8.1 e Windows Phone 8.1 apenas)|Se o servidor VPN exigir um servidor proxy para a conexão, selecione essa opção e especifique o número de porta e endereço do servidor proxy. Para obter mais informações, consulte a documentação do Windows Server.
**Bypass de configurações de proxy para endereços locais** (iOS, Mac OS X, Windows 8.1 e Windows Phone 8.1 apenas)|Se o servidor VPN exigir um servidor proxy para a conexão, selecione esta opção se você não quiser usar o servidor proxy para endereços locais que você especificar. Para obter mais informações, consulte a documentação do Windows Server.
**XML personalizado** (Windows 8.1 e posterior e Windows Phone 8.1 e posterior)|Permite que você especifique comandos XML personalizados para configurar a conexão VPN. Exemplos. Para **Pulse Secure**: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. Para **CheckPoint Mobile VPN**: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true"  debug="3" /&gt;. Para **Dell SonicWALL Mobile Connect**: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. Para **F5 Edge Client**: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;/f5-vpn-conf&gt;. Consulte a documentação do VPN de cada fabricante para obter mais informações sobre como escrever comandos XML personalizados.
**Lista de pesquisa de sufixo DNS** (somente Windows Phone 8.1)|Especifique um sufixo DNS em cada linha. Cada sufixo DNS que você especificar será pesquisado durante a conexão com um site usando um nome curto. Por exemplo, especifique os sufixos DNS **domain1.contoso.com** e **domain2.contoso.com**, acesse a URL **http://mywebsite**, e as URLs **http://mywebsite.domain1.contoso.com** e **http://mywebsite.domain2.contoso.com** serão pesquisadas.
**Bypass de VPN quando conectado à rede da Wi-Fi empresarial** (somente Windows Phone 8.1)|Especifica que a conexão VPN não será usada quando o dispositivo estiver conectado à rede Wi-Fi da empresa.
**Bypass de VPN quando conectado à rede Wi-Fi doméstica** (somente Windows Phone 8.1)|Especifica que a conexão VPN não será usada quando o dispositivo estiver conectado a uma rede Wi-Fi doméstica.

As configurações adicionais a seguir estão disponíveis para dispositivos Windows 10 Desktop e Mobile

Nome da configuração  |Mais informações  
---------|---------
**Regras de tráfego de rede**| Defina quais protocolos, portas local e remota e os intervalos de endereços serão habilitados para a conexão VPN. Se você não criar uma regra de tráfego de rede, todos os protocolos, portas e intervalos de endereços serão habilitados. Depois de criar uma regra, somente os protocolos, portas e intervalos de endereços que você especificar na regra ou em regras adicionais serão usados pela conexão VPN.
**Rotas**|Quais rotas usarão a conexão VPN.
**Servidores DNS**| Quais servidores DNS são usados pela conexão VPN depois de a conexão ser estabelecida.         
**Aplicativos associados**     | Você pode fornecer uma lista de aplicativos que usarão automaticamente a conexão VPN. O tipo de aplicativo determinará o identificador do aplicativo. Para aplicativos universais – forneça o Nome da Família de Pacotes, e para aplicativos de desktop – forneça o caminho do arquivo do aplicativo.          


Aqui está um exemplo de quando você pode usar as configurações de limites corporativos. Se você quiser habilitar VPN apenas para a área de trabalho remota, crie uma regra de tráfego de rede que permita o tráfego para o número de protocolo 27 na porta externa 3996. Nenhum outro tráfego usará a VPN.

Definir rotas em limites corporativos é útil quando o tipo de conexão VPN não permite definir como o tráfego é tratado no túnel dividido. Nesse caso, use **Rotas** para listar as rotas que usarão VPN.

Você pode restringir o uso de VPN do dispositivo Windows 10 para aplicativos específicos criando uma configuração personalizada do URI OMA.

A nova política é exibida no nó **Políticas de configuração** do espaço de trabalho **Política** .

## Implantar a política

1.  No espaço de trabalho **Política**, selecione a política que deseja implantar e clique em **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar implantação** :

    -   **Para implantar a política** - Selecione um ou mais grupos nos quais deseja implantar a política e clique em **Adicionar** &gt; **OK**.

    -   **Para fechar a caixa de diálogo sem implantá-la** - Clique em **Cancelar**.


Após a implantação bem-sucedida, os usuários verão o nome da conexão VPN especificado na lista de conexões de VPN em seu dispositivo.

Um resumo de status e alertas na página **Visão geral** do espaço de trabalho **Política** identifica problemas com a política que exigem atenção. Além disso, um resumo de status aparece no espaço de trabalho Painel.



<!--HONumber=May16_HO1-->


