---
title: Configurar e gerenciar certificados SCEP com o Intune
titleSuffix: Intune Azure preview
description: "Visualização do Intune Azure: aprenda a configurar sua infraestrutura, depois crie e atribua perfis de certificado SCEP no Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d567d85f-e4ee-458e-bef7-6e275467efce
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: a981b0253f56d66292ce77639faf4beba8832a9e
ms.openlocfilehash: 6838993b5b19bc1e23c9efe0911a01a2c66c6886
ms.lasthandoff: 04/19/2017

---
# <a name="configure-and-manage-scep-certificates-with-intune"></a>Configurar e gerenciar certificados SCEP com o Intune
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Este tópico mostra como configurar sua infraestrutura e depois criar e atribuir perfis de certificado de protocolo SCEP (Simple Certificate Enrollment Protocol) com o Intune.

## <a name="configure-on-premises-infrastructure"></a>Configurar a infraestrutura local

-    **Domínio do Active Directory**: todos os servidores listados nesta seção (exceto pelo Servidor Proxy de Aplicativo Web) devem ser ingressados em seu domínio do Active Directory.

-  **AC (Autoridade de Certificação)**: uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. Para obter detalhes, confira [Instalar a Autoridade de Certificação](http://technet.microsoft.com/library/jj125375.aspx).
    Se a sua AC executar o Windows Server 2008 R2, você deve [instalar o hotfix de KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Servidor NDES**: em um servidor que executa o Windows Server 2012 R2 ou posterior, você deve configurar o NDES (Serviço de Registro de Dispositivo de Rede). O Intune não dá suporte ao uso do NDES quando ele é executado em um servidor que também executa a AC Corporativa. Consulte [Network Device Enrollment Service Guidance](http://technet.microsoft.com/library/hh831498.aspx) (Diretrizes de Serviço de Registro de Dispositivo de Rede) para obter instruções sobre como configurar o Windows Server 2012 R2 para hospedar o Serviço de Registro de Dispositivo de Rede.
O servidor NDES deve ter ingressado no domínio que hospeda a AC e não estar no mesmo servidor que a AC. Para obter mais informações sobre como implantar o servidor NDES em uma floresta separada, rede isolada ou domínio interno podem ser encontradas em [Using a Policy Module with the Network Device Enrollment Service](https://technet.microsoft.com/library/dn473016.aspx) (Usando um módulo de política com o Serviço de Registro de Dispositivo de Rede).

-  **Conector de Certificado do Microsoft Intune**: use o portal do Intune para baixar o instalador do **Conector de Certificado** (**ndesconnectorssetup.exe**). Em seguida, você pode executar **ndesconnectorssetup.exe** no computador em que deseja instalar o Conector de Certificado.
-  **Servidor Proxy de Aplicativos Web** (opcional): use um servidor que executa o Windows Server 2012 R2 ou posterior como servidor WAP (Proxy de Aplicativo Web). Essa configuração:
    -  Permite que os dispositivos recebam certificados usando uma conexão com a Internet.
    -  Trata-se de uma recomendação de segurança quando os dispositivos se conectam pela Internet para receber e renovar certificados.

 > [!NOTE]           
> -    O servidor que hospeda o WAP [deve instalar uma atualização](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) que habilita o suporte para as URLs longas que são usadas pelo Serviço de Registro de Dispositivo de Rede. Essa atualização está incluída no [pacote cumulativo de atualizações de dezembro de 2014](http://support.microsoft.com/kb/3013769)ou individualmente no [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Além disso, o servidor que hospeda o WAP deve ter um certificado SSL que corresponde ao nome que está sendo publicado para clientes externos, bem como confiar no certificado SSL que é usado no servidor NDES. Esses certificados habilitam o servidor WAP a encerrar a conexão SSL de clientes e a criar uma nova conexão SSL com o servidor NDES.
    Para obter mais informações sobre certificados de WAP, consulte a seção **Planejar certificados** de [Planejando Publicar Aplicativos Usando o Proxy de Aplicativo Web](https://technet.microsoft.com/library/dn383650.aspx). Para obter informações gerais sobre servidores WAP, consulte [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx) (Trabalhando com o Proxy de Aplicativo Web).|

### <a name="network-requirements"></a>Requisitos de rede

Da Internet para a rede de perímetro, permitir a porta 443 de todos os endereços IP/ hosts na internet para o servidor NDES.

Da rede de perímetro para a rede confiável, permitir todas as portas e protocolos necessários para acesso ao domínio no servidor NDES associado por domínio. O servidor NDES precisa acessar servidores de certificados, servidores DNS, servidores do Configuration Manager e controladores de domínio.

É recomendável publicar o servidor NDES através de um proxy, como o [Proxy de aplicativo do Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), o [Proxy do Web Access](https://technet.microsoft.com/library/dn584107.aspx) ou um proxy de terceiros.


### <a name="certificates-and-templates"></a>Certificados e modelos

|Objeto|Detalhes|
|----------|-----------|
|**Modelo de certificado**|Configure este modelo na AC emissora.|
|**Certificado de autenticação de cliente**|Solicitado pela AC emissora ou pública, você instala este certificado no servidor de NDES.|
|**Certificado de autenticação de servidor**|Solicitado da AC emissora pública, você instala e associa o certificado SSL no IIS no servidor de NDES.|
|**Certificado de AC raiz confiável**|Você o exporta como um arquivo **.cer** da AC raiz ou de qualquer dispositivo que confie na AC raiz e a atribui aos dispositivos usando o perfil de certificado de AC Confiável.<br /><br />Você usa um único certificado de AC raiz confiável por plataforma de sistema operacional e o associa a cada perfil de certificado de raiz confiável que criar.<br /><br />Você pode usar certificados de AC raiz confiável adicionais quando necessário. Por exemplo, você pode fazer isso para fornecer uma relação de confiança a uma AC que conecta os certificados de autenticação do servidor aos pontos de acesso Wi-Fi.|

### <a name="accounts"></a>Contas

|Nome|Detalhes|
|--------|-----------|
|**Conta de serviço de NDES**|Especifique uma conta de usuário de domínio para usar como conta de serviço de NDES.|

## <a name="configure-your-infrastructure"></a>Configure sua infraestrutura
Antes de configurar perfis de certificado, você deve concluir as seguintes tarefas que exigem conhecimento do Windows Server 2012 R2 e dos AD CS (Serviços de Certificados do Active Directory):

**Etapa 1**: Criar uma conta de serviço de NDES

**Etapa 2**: Configurar modelos de certificado na autoridade de certificação

**Etapa 3**: Configurar pré-requisitos no servidor NDES

**Etapa 4**: Configurar o NDES para uso com o Intune

**Etapa 5**: Habilitar, instalar e configurar o Conector de Certificado do Intune

#### <a name="step-1---create-an-ndes-service-account"></a>Etapa 1 - Criar uma conta de serviço de NDES

Crie uma conta de usuário de domínio para usar como conta de serviço de NDES. Especifique essa conta ao configurar modelos na AC emissora antes de instalar e configurar o NDES. Verifique se o usuário tem os direitos padrão, que são os direitos **Logon Localmente**, **Logon como um Serviço** e **Logon como um trabalho em lotes**. Algumas organizações têm políticas de proteção que desabilitam esses direitos de proteção.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Etapa 2 - Configurar modelos de certificado na autoridade de certificação
Nesta tarefa, você vai:

-   Configurar um modelo de certificado para o NDES

-   Publicar o modelo de certificado para o NDES

##### <a name="to-configure-the-certification-authority"></a>Para configurar a autoridade de certificação

1.  Faça logon como administrador corporativo.

2.  Na AC emissora, use o snap-in de Modelos de Certificado para criar um novo modelo personalizado ou copie um modelo existente (como o modelo de Usuário) e o edite para uso com o NDES.

    O modelo deve ter as seguintes configurações:

    -   Especifique um **Nome amigável de exibição do modelo** para o modelo.

    -   Na guia **Nome da Entidade** , selecione **Fornecer na solicitação**. (A segurança é imposta pelo módulo de política do Intune para o NDES).

    -   Na guia **Extensões** , verifique se a **Descrição das Políticas de Aplicativo** inclui **Autenticação de Cliente**.

        > [!IMPORTANT]
        > Para modelos de certificado do iOS e macOS, na guia **Extensões**, edite **Uso da Chave** e verifique se a opção **A assinatura é uma prova de origem** não está selecionada.

    -   Na guia **Segurança**, adicione a conta de serviço NDES e dê a ela permissões para **Registrar** no modelo. Administradores do Intune que criarão perfis SCEP exigem direitos de **leitura** para que possam navegar no modelo durante a criação de perfis SCEP.

    > [!NOTE]
    > Para revogar certificados, a conta de serviço do NDES precisa de direitos de *Emitir e Gerenciar Certificados* para cada modelo de certificado usado por um perfil de certificado.

3.  Examine o **Período de validade** na guia **Geral** do modelo. Por padrão, o Intune usa o valor configurado no modelo. No entanto, você tem a opção de configurar a AC para permitir que o solicitante especifique um valor diferente, que você pode definir de dentro do Console do administrador do Intune. Se você quiser usar sempre o valor no modelo, ignore o restante desta etapa.

    > [!IMPORTANT]
    > O iOS e o macOS sempre usam o valor definido no modelo, independentemente de outras configurações que você fizer.

Aqui estão as capturas de tela de um exemplo de configuração de modelo.

![Modelo, guia de tratamento de solicitação](.\media\scep_ndes_request_handling.png)

![Modelo, guia de nome da entidade](.\media\scep_ndes_subject_name.jpg)

![Modelo, guia de segurança](.\media\scep_ndes_security.jpg)

![Modelo, guia de extensões](.\media\scep_ndes_extensions.jpg)

![Modelo, guia de requisitos de emissão](.\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > Para Políticas de Aplicativo, adicione somente as políticas de aplicativo necessárias. Confirme suas escolhas com seus administradores de segurança.



Para configurar a AC para permitir que o solicitante especifique o período de validade:

1. Na AC, execute os seguintes comandos:
    - **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
    - **net stop certsvc**
    - **net start certsvc**
2. Na AC emissora, use o snap-in da Autoridade de Certificação para publicar o modelo de certificado.
    Selecione o nó **Modelos de Certificado**, clique em **Ação**-&gt; **Novo** &gt; **Modelo de Certificado a Ser Emitido** e selecione o modelo que você criou na etapa 2.
3. Valide a publicação do modelo exibindo-o na pasta **Modelos de Certificado** .


#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>Etapa 3 - Configurar pré-requisitos no servidor NDES
Nesta tarefa, você vai:

-   Adicionar o NDES a um Windows Server e configurar o IIS para dar suporte ao NDES

-   Adicionar a conta de serviço de NDES ao grupo IIS_IUSR

-   Definir o SPN da conta de serviço de NDES




   1.  No servidor que hospeda o NDES, você deve fazer logon como **Administrador Corporativo**e usar o [Assistente de Adição de Funções e Recursos](https://technet.microsoft.com/library/hh831809.aspx) para instalar o NDES:

    1.  No assistente, selecione **Serviços de Certificados do Active Directory** para acessar os Serviços de Função do AD CS. Selecione o **Serviço de Registro de Dispositivo de Rede**, desmarque **Autoridade de Certificação**e conclua o assistente.

        > [!TIP]
        > Na página **Progresso da Instalação** do assistente, não clique em **Fechar**. Em vez disso, clique no link para **Configurar os Serviços de Certificados do Active Directory no servidor de destino**. Isso abre o assistente de **Configuração AD CS** que você usa para a próxima tarefa. Após Configuração AD CS abrir, você pode fechar o Assistente de Adição de Funções e Recursos.

    2.  Quando o NDES é adicionado ao servidor, o assistente também instala o IIS. Verifique se o IIS tem as seguintes configurações:

        -   **Servidor Web** &gt; **Segurança** &gt; **Filtragem de Solicitações**

        -   **Servidor Web** &gt; **Desenvolvimento de Aplicativos** &gt; **ASP.NET 3.5**. Instalar o ASP.NET 3.5 instalará o .NET Framework 3.5. Ao instalar o .NET Framework 3.5, instale o recurso **.NET Framework 3.5** principal e o **Ativação HTTP**.

        -   **Servidor Web** &gt; **Desenvolvimento de Aplicativos** &gt; **ASP.NET 4.5**. Instalar o ASP.NET 4,5 instalará o .NET Framework 4,5. Ao instalar o .NET Framework 4.5, instale o recurso principal do **.NET Framework 4.5**, o **ASP.NET 4.5** e o recurso **Serviços WCF** &gt; **Ativação HTTP**.

        -   **Ferramentas de gerenciamento** &gt; **Compatibilidade de gerenciamento do IIS 6** &gt; **Compatibilidade de metabase do IIS 6**

        -   **Ferramentas de gerenciamento** &gt; **Compatibilidade de gerenciamento do IIS 6** &gt; **Compatibilidade de WMI do IIS 6**

  2.  No servidor, adicione a conta de serviço de NDES como membro do grupo **IIS_IUSR**.

   3.  Em um prompt de comandos com privilégios elevados, execute o seguinte comando para definir o SPN da conta de serviço de NDES:

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   Por exemplo, se seu servidor de NDES se chamar **Server01**, seu domínio for **Contoso.com**e a conta de serviço for **NDESService**, use:

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Etapa 4 - Configurar o NDES para uso com o Intune
Nesta tarefa, você vai:

-   Configurar o NDES para uso com a AC emissora

-   Associar o certificado de autenticação do servidor (SSL) no IIS

-   Configurar a filtragem de solicitações no IIS


1.  No servidor de NDES, abra o Assistente de Configuração do AD CS e faça as seguintes configurações.

    > [!TIP]
    > Se você clicou no link na tarefa anterior, o assistente já está aberto. Caso contrário, abra o Gerenciador do Servidor para acessar a configuração pós-implantação dos Serviços de Certificados do Active Directory.

    -   Na página **Serviços de Função** , selecione **Serviço de Registro de Dispositivo de Rede**.

    -   Na página **Conta de Serviço para NDES** , especifique a Conta de Serviço de NDES.

    -   Na página **AC para NDES** , clique em **Selecionar**e selecione a AC emissora em que você configurou o modelo de certificado.

    -   Na página **Criptografia para NDES** , defina o comprimento de chave para atender aos requisitos da sua empresa.

    Na página **Confirmação** , clique em **Configurar** para concluir o assistente.

2.  Após concluir o assistente, edite a seguinte chave do Registro no Servidor de NDES:

    -   **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**

    Para editar essa chave, identifique a **Finalidade** do modelo de certificado, conforme encontrada na guia **Tratamento de Solicitação**, e edite a entrada correspondente no Registro substituindo os dados existentes pelo nome do modelo de certificado (não o nome de exibição do modelo) que você especificou na Tarefa 1. A tabela a seguir mapeia a finalidade do modelo de certificado de acordo com os valores do Registro:

    |Finalidade do modelo de certificado (na guia Tratamento de Solicitação)|Valor de registro a ser editado|O valor mostrado no console de administração do Intune para o perfil do protocolo SCEP|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |Assinatura|SignatureTemplate|Assinatura digital|
    |Criptografia|EncryptionTemplate|Codificação de chave|
    |Assinatura e criptografia|GeneralPurposeTemplate|Codificação de chave<br /><br />Assinatura digital|
    Por exemplo, se a Finalidade do seu modelo de certificado for **Criptografia**, edite o valor de **EncryptionTemplate** como o nome do seu modelo de certificado.

3. O servidor NDES receberá URLs muito longas (consultas), o que exige que você adicione duas entradas de Registro:

    |Local|Valor|Tipo|Dados|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534 (decimal)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534 (decimal)|


4. No Gerenciador do IIS, escolha **Site Padrão** -> **Filtragem de Solicitações** -> **Editar Configuração do Recurso** e altere o **Comprimento máximo da URL** e **Cadeia de caracteres de consulta máxima** para *65534*, conforme mostrado.

    ![Comprimento máximo de URL e consulta do IIS](.\media\SCEP_IIS_max_URL.png)

5.  Reinicie o servidor. Executar **iisreset** no servidor não será suficiente para finalizar as alterações.
6. Navegue até http://*FQDN*/certsrv/mscep/mscep.dll. Você deve ver uma página NDES semelhante a esta:

    ![Testar NDES](.\media\SCEP_NDES_URL.png)

    Se você receber **503 Serviço indisponível**, verifique o Visualizador de Eventos. É provável que o pool de aplicativos seja interrompido devido a um direito ausente para o usuário NDES. Esses direitos são descritos na Tarefa 1.

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a>Para instalar e associar os certificados no Servidor de NDES

1.  No seu Servidor de NDES, solicite e instale um certificado de **autenticação de servidor** por meio da sua AC interna ou pública. Em seguida, você associará esse certificado SSL no IIS.

    > [!TIP]
    > Depois de associar o certificado SSL no IIS, você também instalará um certificado de autenticação de cliente. Esse certificado pode ser emitido por qualquer AC em que o Servidor de NDES confie. Embora não seja uma prática recomendada, você pode usar o mesmo certificado para autenticação de servidor e cliente, desde que o certificado tenha os dois EKUs (Usos Avançados de Chave). Examine as etapas a seguir para obter informações sobre esses certificados de autenticação.

    1.  Depois de obter o certificado de autenticação de servidor, abra o **Gerenciador do IIS**, selecione o **Site Padrão** no painel **Conexões** e clique em **Ligações** no painel **Ações** .

    2.  Clique em **Adicionar**, defina o **Tipo** como **https**e verifique se a porta é **443**. (Somente a porta 443 tem suporte para o Intune autônomo).

    3.  Para **Certificado SSL**, especifique o certificado de autenticação de servidor.

        > [!NOTE]
        > Se o servidor de NDES usar um nome interno e externo para um único endereço de rede, o certificado de autenticação de servidor deverá ter um **Nome da Entidade** com um nome de servidor público externo e um **Nome Alternativo da Entidade** que inclua o nome do servidor interno.

2.  No seu Servidor de NDES, solicite e instale um certificado de **autenticação de cliente** da sua AC interna ou uma AC pública. Pode ser o mesmo certificado que o certificado de autenticação de servidor se o certificado tiver os dois recursos.

    O certificado de autenticação de cliente deve ter as seguintes propriedades:

    **Uso Avançado de Chave** - Isso deve incluir a **Autenticação de Cliente**.

    **Nome da Entidade**: deve ser igual ao nome DNS do servidor em que você está instalando o certificado (o Servidor de NDES).

##### <a name="to-configure-iis-request-filtering"></a>Para configurar a filtragem de solicitações do IIS

1.  No Servidor de NDES, abra o **Gerenciador do IIS**, selecione o **Site Padrão** no painel **Conexões** e abra a **Filtragem de Solicitações**.

2.  Clique em **Editar Configurações de Recurso**e defina o seguinte:

    **cadeia de caracteres de consulta (Bytes)** = **65534**

    **Tamanho máximo da URL (Bytes)** = **65534**

3.  Examine a seguinte chave do Registro:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Certifique-se de que os seguintes valores sejam definidos como entradas DWORD:

    Nome: **MaxFieldLength**, com um valor decimal de **65534**

    Nome: **MaxRequestBytes**, com um valor decimal de **65534**

4.  Reinicialize o servidor NDES. Agora, o servidor está pronto para dar suporte ao Conector de Certificado.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Etapa 5 - Habilitar, instalar e configurar o Conector de Certificado do Intune
Nesta tarefa, você vai:

Habilitar o suporte para NDES no Intune.

Baixar, instalar e configurar o Conector de Certificado no Servidor NDES.

##### <a name="to-enable-support-for-the-certificate-connector"></a>Para habilitar o suporte ao Conector de Certificado

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
4. Na folha **Configurações do Dispositivo**, escolha **Autoridade de Certificação**.
5.  Selecione **Habilitar Certificate Connector**.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Para baixar, instalar e configurar o Conector de Certificado

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
4. Na folha **Configurações do Dispositivo**, escolha **Autoridade de Certificação**.
5. Escolha **Baixar Certificate Connector**.
6.  Após a conclusão do download, execute o instalador baixado (**ndesconnectorssetup.exe**) em um servidor Windows Server 2012 R2. O instalador também instala o módulo de política para NDES e o Serviço Web de CRP. (O Serviço Web de CRP, CertificateRegistrationSvc, é executado como um aplicativo no IIS).

    > [!NOTE]
    > Quando você instala o NDES para o Intune autônomo, o serviço de CRP é instalado automaticamente com o Conector de Certificado. Quando você usa o Intune com o Configuration Manager, instala o Ponto de Registro de Certificado como uma função de sistema de site separada.

3.  Quando for solicitado o certificado de cliente do Certificate Connector, escolha **Selecionar** e selecione o certificado de **autenticação de cliente** instalado no Servidor NDES na Tarefa 3.

    Depois de selecionar o certificado de autenticação de cliente, você retornará para a superfície do **Certificado de Cliente para o Conector de Certificado do Microsoft Intune** . Embora o certificado selecionado não seja exibido, clique em **Avançar** para ver as propriedades do certificado. Em seguida, clique em **Avançar**e clique em **Instalar**.

4.  Após a conclusão do assistente, mas antes de fechá-lo, clique em **Iniciar a Interface do Usuário do Conector de Certificado**.

    > [!TIP]
    > Se fechar o assistente antes de iniciar a interface do usuário do Conector de Certificado, você poderá reabri-la executando o seguinte comando:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  Na interface do usuário do **Conector de Certificado** :

    Clique em **Entrar** e insira suas credenciais de administrador de serviços do Intune ou as credenciais de um administrador de locatários com permissão de administração global.

    Se sua organização usa um servidor proxy e o proxy é necessário para o servidor NDES acessar a Internet, clique em **Usar servidor proxy** e informe o nome do servidor proxy, a porta e as credenciais de conta usadas para a conexão.

    Selecione a guia **Avançado** e forneça credenciais para uma conta que tenha a permissão **Emitir e Gerenciar Certificados** na sua Autoridade de Certificação emissora e clique em **Aplicar**.

    Agora você pode fechar a interface do usuário do Conector de Certificado.

6.  Abra um prompt de comando e digite **services.msc**, pressione **Enter**, clique com o botão direito do mouse em **Serviço de Conector do Intune** e clique em **Reiniciar**.

Para validar que o serviço está em execução, abra um navegador e digite a seguinte URL, que deve retornar um erro **403** :

**http:// &lt;FQDN_do_seu_servidor_NDES&gt;/certsrv/mscep/mscep.dll**

## <a name="how-to-create-a-scep-certificate-profile"></a>Como criar um perfil de certificado SCEP

1. No Portal do Azure, selecione a carga de trabalho **Configurar dispositivos**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de certificado SCEP.
5. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado SCEP. No momento, é possível escolher uma das seguintes plataformas para as configurações de restrição de dispositivo:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **Certificado SCEP**.
7. Na folha **Certificado SCEP**, defina as seguintes configurações:
    - **Período de validade do certificado** – Se você executar o comando **certutil – setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** na AC emissora, o que permite usar um período de validade personalizado, poderá especificar a quantidade de tempo restante antes que o certificado expire.<br>Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também tem que ser inferior ao período de validade restante do certificado da AC emissora. 
    - **KSP (provedor de armazenamento de chaves)** (Windows Phone 8.1, Windows 8.1 e Windows 10) – Especifique o local em que a chave do certificado será armazenada. Escolha um destes valores:
        - **Registrar no KSP do TPM (Trusted Platform Module) se existir; caso contrário, no KSP de Software**
        - **Registrar no KSP do TPM (Trusted Platform Module); caso contrário, falha**
        - **Registrar no Passport; caso contrário, falha (Windows 10 e posterior)**
        - **Registrar no Software KSP**
    - **Formato de nome da entidade** – Na lista, selecione como o Intune cria automaticamente o nome da entidade na solicitação de certificado. Se o certificado for para um usuário, você também pode incluir o endereço de email do usuário no nome da entidade. Escolha:
        - **Não configurado**
        - **Nome comum**
        - **Nome comum incluindo email**
        - **Nome comum como email**
    - **Nome alternativo da entidade** – Especifique como o Intune criará automaticamente os valores para o SAN (nome alternativo da entidade) na solicitação de certificado. Se tiver selecionado um tipo de certificado de usuário, por exemplo, você pode incluir o UPN no nome alternativo da entidade. Se o certificado do cliente for usado para autenticar em um Servidor de Políticas de Rede, você deve definir o nome alternativo da entidade como o UPN. 
    - **Uso de chave** – Especifique as opções de uso de chave para o certificado. Você pode escolher entre as seguintes opções: 
        - **Codificação de chave:** permitir a troca de chaves apenas quando a chave for criptografada. 
        - **Assinatura digital:** permitir a troca de chaves apenas quando uma assinatura digital ajudar a proteger a chave. 
    - **Tamanho da chave (bits)** – Selecione o número de bits que estão contidos na chave. 
    - **Algoritmo de hash:** (Android, Windows Phone 8.1, Windows 8.1 e Windows 10) – Selecione um dos tipos de algoritmo de hash disponíveis para ser usado com esse certificado. Selecione o nível mais alto de segurança que dá suporte aos dispositivos de conexão. 
    - **Certificado Raiz** – Escolha um perfil de certificado de AC raiz configurado anteriormente e atribuído ao usuário ou dispositivo. Esse certificado AC deve ser o certificado raiz da AC que emite o certificado que você está configurando nesse perfil de certificado. 
    - **Uso estendido da chave** – Escolha **Adicionar** para adicionar valores para a finalidade desejada do certificado. Na maioria dos casos, o certificado exigirá **Autenticação de cliente** para que o usuário ou dispositivo possa autenticar-se em um servidor. No entanto, você pode adicionar outros usos da chave conforme necessário. 
    - **Configurações de Registro**
        - **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
        - **URLs de servidor SCEP** – Especifique uma ou mais URLs para os servidores de NDES que emitirão certificados por meio do protocolo SCEP. 
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.

>[!Note]
> Somente para dispositivos iOS: em Formato de nome da entidade, selecione Personalizado para inserir um formato de nome da entidade personalizado.
> As duas variáveis que atualmente têm suporte para o formato personalizado são **Nome Comum (CN)** e **Email (E)**. Usando uma combinação dessas cadeias de caracteres variáveis e estáticas, é possível criar um formato de nome de entidade personalizado, como este: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** Nesse exemplo, você criou um formato de nome de entidade que, além das variáveis CN e E, usa cadeias de caracteres para os valores de Unidade Organizacional, Organização, Local, Estado e País. [Este tópico](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) mostra a função **CertStrToName** função e suas cadeias de caracteres com suporte.

## <a name="how-to-assign-the-certificate-profile"></a>Como atribuir o perfil de certificado

Antes de atribuir perfis de certificado a grupos, considere o seguinte:

- Quando você atribui perfis de certificado a grupos, o arquivo de certificado do perfil do Certificado de Autoridade de Certificação Confiável é instalado no dispositivo. O dispositivo usa o perfil de certificado SCEP para criar uma solicitação de certificado pelo dispositivo.
- Os perfis de certificado são instalados somente em dispositivos que executam a plataforma que você usa ao criar o perfil.
- Você pode atribuir perfis de certificado para coleções de usuários ou coleções de dispositivos.
- Para publicar um certificado em um dispositivo rapidamente depois que o dispositivo for registrado, atribua o perfil de certificado a um grupo de usuários em vez de um grupo de dispositivos. Se você atribuir um grupo de dispositivos, um registro de dispositivo completo será necessário para que o dispositivo receba políticas.
- Embora você atribuir cada perfil separadamente, também precisará atribuir a AC Raiz Confiável e o perfil SCEP ou PKCS. Caso contrário, a política de certificação SCEP ou PKCS falhará.

Para saber mais sobre como atribuir perfis, confira [Como atribuir perfis de dispositivo](how-to-assign-device-profiles.md).


