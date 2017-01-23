---
title: Configurar a infraestrutura de certificado para o SCEP | Microsoft Docs
description: Infraestrutura para criar e implantar perfis de certificado SCEP.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4ae137ae-34e5-4a45-950c-983de831270f
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 4140c310bb14faf1731e3c316e1dafae5dc0f97a

---
# <a name="configure-certificate-infrastructure-for-scep"></a>Configurar a infraestrutura de certificado para SCEP

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico descreve qual infraestrutura é necessária para criar e implantar perfis de certificado SCEP.

### <a name="on-premises-infrastructure"></a>Infraestrutura local

-    **Domínio do Active Directory**: todos os servidores listados nesta seção (exceto pelo Servidor Proxy de Aplicativo Web) devem ser ingressados em seu domínio do Active Directory.

-  **AC (Autoridade de Certificação)**: uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. Para ver instruções sobre como configurar uma autoridade de certificação, consulte [Instalar a autoridade de certificação](http://technet.microsoft.com/library/jj125375.aspx).
    Se a sua AC executar o Windows Server 2008 R2, você deve [instalar o hotfix de KB2483564](http://support.microsoft.com/kb/2483564/).
I
-  **Servidor NDES**: em um servidor que executa o Windows Server 2012 R2 ou posterior, você deve configurar o NDES (Serviço de Registro de Dispositivo de Rede). O Intune não dá suporte ao uso do NDES quando ele é executado em um servidor que também executa a AC Corporativa. Consulte [Network Device Enrollment Service Guidance](http://technet.microsoft.com/library/hh831498.aspx) (Diretrizes de Serviço de Registro de Dispositivo de Rede) para obter instruções sobre como configurar o Windows Server 2012 R2 para hospedar o Serviço de Registro de Dispositivo de Rede. O servidor NDES deve ter ingressado no domínio que hospeda a AC e não estar no mesmo servidor que a AC. Para obter mais informações sobre como implantar o servidor NDES em uma floresta separada, rede isolada ou domínio interno podem ser encontradas em [Using a Policy Module with the Network Device Enrollment Service](https://technet.microsoft.com/en-us/library/dn473016.aspx) (Usando um módulo de política com o Serviço de Registro de Dispositivo de Rede).

-  **Conector de Certificado do Microsoft Intune**: você usa o console de administração do Intune para baixar o instalador do **Conector de Certificado** (**ndesconnectorssetup.exe**). Em seguida, você pode executar **ndesconnectorssetup.exe** no computador em que deseja instalar o Conector de Certificado.
-  **Servidor Proxy de Aplicativos Web** (opcional): você pode usar um servidor que executa o Windows Server 2012 R2 ou posterior como servidor WAP (Proxy de Aplicativo Web). Essa configuração:
    -  Permite que os dispositivos recebam certificados usando uma conexão com a Internet.
    -  Trata-se de uma recomendação de segurança quando os dispositivos se conectam pela Internet para receber e renovar certificados.

 > [!NOTE]           
> -    O servidor que hospeda o WAP [deve instalar uma atualização](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) que habilita o suporte para as URLs longas que são usadas pelo Serviço de Registro de Dispositivo de Rede. Essa atualização está incluída no [pacote cumulativo de atualizações de dezembro de 2014](http://support.microsoft.com/kb/3013769)ou individualmente no [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Além disso, o servidor que hospeda o WAP deve ter um certificado SSL que corresponde ao nome que está sendo publicado para clientes externos, bem como confiar no certificado SSL que é usado no servidor NDES. Esses certificados habilitam o servidor WAP a encerrar a conexão SSL de clientes e a criar uma nova conexão SSL com o servidor NDES.
    Para obter mais informações sobre certificados de WAP, consulte a seção **Planejar certificados** de [Planejando Publicar Aplicativos Usando o Proxy de Aplicativo Web](https://technet.microsoft.com/library/dn383650.aspx). Para obter informações gerais sobre servidores WAP, consulte [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx) (Trabalhando com o Proxy de Aplicativo Web).|

### <a name="network-requirements"></a>Requisitos de rede

Da Internet para a rede de perímetro, permitir a porta 443 de todos os endereços IP/ hosts na internet para o servidor NDES.

Da rede de perímetro para a rede confiável, permitir todas as portas e protocolos necessários para acesso ao domínio no servidor NDES associado por domínio. O servidor NDES precisa acessar servidores de certificados, servidores DNS, servidores do Configuration Manager e controladores de domínio.

É recomendável publicar o servidor NDES através de um proxy, como o [Proxy de aplicativo do Azure AD](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-publish/), o [Proxy do Web Access](https://technet.microsoft.com/en-us/library/dn584107.aspx) ou um proxy de terceiros.


### <a name="a-namebkmkcertsandtemplatesacertificates-and-templates"></a><a name="BKMK_CertsAndTemplates"></a>Certificados e modelos

|Objeto|Detalhes|
|----------|-----------|
|**Modelo de certificado**|Você configura este modelo na AC emissora.|
|**Certificado de autenticação de cliente**|Solicitado pela AC emissora ou pública, você instala este certificado no servidor de NDES.|
|**Certificado de autenticação de servidor**|Solicitado da AC emissora pública, você instala e associa o certificado SSL no IIS no servidor de NDES.|
|**Certificado de AC raiz confiável**|Você o exporta como um arquivo **.cer** da AC raiz ou de qualquer dispositivo que confie na AC raiz e a implante nos dispositivos usando o perfil de certificado de autoridade de certificação confiável.<br /><br />Você usa um único certificado de AC raiz confiável por plataforma de sistema operacional e o associa a cada perfil de certificado de raiz confiável que criar.<br /><br />Você pode usar certificados de AC raiz confiável adicionais quando necessário. Por exemplo, você pode fazer isso para fornecer uma relação de confiança a uma AC que conecta os certificados de autenticação do servidor aos pontos de acesso Wi-Fi.|

### <a name="a-namebkmkaccountsaaccounts"></a><a name="BKMK_Accounts"></a>Contas

|Nome|Detalhes|
|--------|-----------|
|**Conta de serviço de NDES**|Especifique uma conta de usuário de domínio para usar como conta de serviço de NDES.|

## <a name="a-namebkmkconfigureinfrastructureaconfigure-your-infrastructure"></a><a name="BKMK_ConfigureInfrastructure"></a>Configure sua infraestrutura
Antes de configurar perfis de certificado, você deve concluir as seguintes tarefas que exigem conhecimento do Windows Server 2012 R2 e dos AD CS (Serviços de Certificados do Active Directory):

**Tarefa 1**: criar uma conta de serviço de NDES

**Tarefa 2**: configurar modelos de certificado na autoridade de certificação

**Tarefa 3**: configurar pré-requisitos no servidor NDES

**Tarefa 4**: configurar o NDES para uso com o Intune

**Tarefa 5**: habilitar, instalar e configurar o Conector de Certificado do Intune

### <a name="task-1---create-an-ndes-service-account"></a>Tarefa 1 - Criar uma conta de serviço de NDES

Crie uma conta de usuário de domínio para usar como conta de serviço de NDES. Especifique essa conta ao configurar modelos na AC emissora antes de instalar e configurar o NDES. Verifique se o usuário tem os direitos padrão, que são os direitos **Logon Localmente**, **Logon como um Serviço** e **Logon como um trabalho em lotes**. Algumas organizações têm políticas de proteção que desabilitam esses direitos de proteção.




### <a name="task-2---configure-certificate-templates-on-the-certification-authority"></a>Tarefa 2 – Configurar modelos de certificado na autoridade de certificação
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
        > Para modelos de certificado do iOS e Mac OS X, na guia **Extensões**, edite **Uso da Chave** e verifique se **A assinatura é uma prova de origem** não está selecionado.

    -   Na guia **Segurança**, adicione a conta de serviço NDES e dê a ela permissões para **Registrar** no modelo. Administradores do Intune que criarão perfis SCEP exigem direitos de **leitura** para que possam navegar no modelo durante a criação de perfis SCEP.

    > [!NOTE]
    > Para revogar certificados, a conta de serviço do NDES precisa de direitos de *Emitir e Gerenciar Certificados* para cada modelo de certificado usado por um perfil de certificado.

3.  Examine o **Período de validade** na guia **Geral** do modelo. Por padrão, o Intune usa o valor configurado no modelo. No entanto, você tem a opção de configurar a AC para permitir que o solicitante especifique um valor diferente, que você pode definir de dentro do Console do administrador do Intune. Se você quiser usar sempre o valor no modelo, ignore o restante desta etapa.

    > [!IMPORTANT]
    > As plataformas do iOS e Mac OS X sempre usam o valor definido no modelo, independentemente de outras configurações que você fizer.

Aqui estão as capturas de tela de um exemplo de configuração de modelo.

![Modelo, guia de tratamento de solicitação](..\media\scep_ndes_request_handling.png)

![Modelo, guia de nome da entidade](..\media\scep_ndes_subject_name.jpg)

![Modelo, guia de segurança](..\media\scep_ndes_security.jpg)

![Modelo, guia de extensões](..\media\scep_ndes_extensions.jpg)

![Modelo, guia de requisitos de emissão](..\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > Para Políticas de Aplicativo (na captura de tela 4), adicione somente as políticas de aplicativo necessárias. Confirme suas escolhas com seus administradores de segurança.



Para configurar a AC para permitir que o solicitante especifique o período de validade, execute os seguintes comandos na AC:

   1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   2.  **net stop certsvc**

   3.  **net start certsvc**

4.  Na AC emissora, use o snap-in da Autoridade de Certificação para publicar o modelo de certificado.

    1.  Selecione o nó **Modelos de Certificado**, clique em **Ação**-&gt; **Novo** &gt; **Modelo de Certificado a Ser Emitido** e selecione o modelo que você criou na etapa 2.

    2.  Valide a publicação do modelo exibindo-o na pasta **Modelos de Certificado** .


### <a name="task-3---configure-prerequisites-on-the-ndes-server"></a>Tarefa 3 - Configurar pré-requisitos no servidor NDES
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

### <a name="task-4---configure-ndes-for-use-with-intune"></a>Tarefa 4 - Configurar o NDES para uso com o Intune
Nesta tarefa, você vai:

-   Configurar o NDES para uso com a AC emissora

-   Associar o certificado de autenticação do servidor (SSL) no IIS

-   Configurar a Filtragem de Solicitações no IIS

##### <a name="to-configure-ndes-for-use-with-intune"></a>Para configurar o NDES para uso com o Intune

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

    ![Comprimento máximo de URL e consulta do IIS](..\media\SCEP_IIS_max_URL.png)

5.  Reinicie o servidor. Executar **iisreset** no servidor não será suficiente para finalizar as alterações.
6. Navegue até http://*FQDN*/certsrv/mscep/mscep.dll. Você deve ver uma página NDES semelhante a esta:

    ![Testar NDES](..\media\SCEP_NDES_URL.png)

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

##### <a name="to-configure-iis-request-filtering"></a>Para configurar a Filtragem de Solicitações do IIS

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

### <a name="task-5---enable-install-and-configure-the-intune-certificate-connector"></a>Tarefa 5 - Habilitar, instalar e configurar o Conector de Certificado do Intune
Nesta tarefa, você vai:

Habilitar o suporte para NDES no Intune.

Baixar, instalar e configurar o Conector de Certificado no Servidor NDES.

##### <a name="to-enable-support-for-the-certificate-connector"></a>Para habilitar o suporte ao Conector de Certificado

1.  Abra o [Console de administração do Intune](https://manage.microsoft.com), clique em **Administrador** &gt; **Conector de Certificado**.

2.  Clique em **Configurar Conector de Certificado Local**.

3.  Selecione **Habilitar Conector de Certificado**e clique em **OK**.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>Para baixar, instalar e configurar o Conector de Certificado

1.  Abra o [Console de administração do Intune](https://manage.microsoft.com) e, em seguida, clique em **Administrador** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Conector de Certificado** &gt; **Baixar Conector de Certificado**.

2.  Após a conclusão do download, execute o instalador baixado (**ndesconnectorssetup.exe**) em um servidor Windows Server 2012 R2. O instalador também instala o módulo de política para NDES e o Serviço Web de CRP. (O Serviço Web de CRP, CertificateRegistrationSvc, é executado como um aplicativo no IIS).

    > [!NOTE]
    > Quando você instala o NDES para o Intune autônomo, o serviço de CRP é instalado automaticamente com o Conector de Certificado. Quando você usa o Intune com o Configuration Manager, instala o Ponto de Registro de Certificado como uma função de sistema de site separada.

3.  Quando for solicitado o certificado de cliente do Conector de Certificado, clique em **Selecionar**e selecione o certificado de **autenticação de cliente** instalado no Servidor NDES na Tarefa 3.

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

**https:// &lt;FQDN_do_seu_servidor_NDES&gt;/certsrv/mscep/mscep.dll**

## <a name="next-steps"></a>Próximas etapas
Agora você está pronto para configurar perfis de certificado, conforme descrito em [Configure certificate profiles](Configure-Intune-certificate-profiles.md) (Configurar perfis de certificado).



<!--HONumber=Dec16_HO2-->


