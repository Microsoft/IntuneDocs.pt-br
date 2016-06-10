---
# required metadata

title: Configurar a infraestrutura de certificado | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3a435650-3891-4754-8abc-4bbac244f33b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurar a infraestrutura de certificado
Este tópico descreve o que você precisa para criar e implantar perfis de certificado.

Para fazer qualquer autenticação baseada em certificado na sua organização, você precisa de uma Autoridade de Certificação Corporativa.

Para usar perfis de certificado SCEP, além da Autoridade de Certificação Corporativa, você também precisa:

-   Um servidor que executa o Serviço de Registro de Dispositivo de Rede

-   O Conector de Certificado do Intune, que é instalado no servidor do Windows Server 2012 R2 que executa o NDES

Para usar perfis de certificado .PFX, além da Autoridade de Certificação Corporativa, você também precisa:

-  Um computador que pode se comunicar com a Autoridade de Certificação ou usar o próprio computador da Autoridade de Certificação.

-  O Conector de Certificado do Intune, que é executado no computador, que pode se comunicar com a Autoridade de Certificação.

## Infraestrutura local


-    **Domínio do Active Directory**: todos os servidores listados nesta seção (exceto pelo Servidor Proxy de Aplicativo Web) devem ser ingressados em seu domínio do Active Directory.

-  **AC (Autoridade de Certificação)**: uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. Para ver instruções sobre como configurar uma autoridade de certificação, consulte [Instalar a autoridade de certificação](http://technet.microsoft.com/library/jj125375.aspx).
    Se a sua AC executar o Windows Server 2008 R2, você deve [instalar o hotfix de KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Servidor NDES** (apenas SCEP): em um servidor que executa o Windows Server 2012 R2 ou posterior, você deve configurar o NDES (Serviço de Registro de Dispositivo de Rede). O Intune não dá suporte ao uso do NDES quando ele é executado em um servidor que também executa a AC Corporativa. Consulte [Network Device Enrollment Service Guidance (Diretrizes de serviço de registro de dispositivo de rede)](http://technet.microsoft.com/library/hh831498.aspx) para obter instruções sobre como configurar o Windows Server 2012 R2 para hospedar o Serviço de Registro de Dispositivo de Rede.|
-  **Computador capaz de se comunicar com a Autoridade de Certificação** (apenas .PFX): como alternativa, use o próprio computador da Autoridade de Certificação.
-  **Conector de Certificado do Microsoft Intune**: você usa o console de administração do Intune para baixar o instalador do **Conector de Certificado** (**ndesconnectorssetup.exe**). Em seguida, você pode executar **ndesconnectorssetup.exe** no computador em que deseja instalar o Conector de Certificado. Para os perfis de Certificado .PFX, instale o Conector de Certificado no computador que se comunica com a Autoridade de Certificação.
-  **Servidor Proxy de Aplicativos Web** (opcional): você pode usar um servidor que executa o Windows Server 2012 R2 ou posterior como servidor WAP (Proxy de aplicativo Web). Essa configuração:
    -  Permite que os dispositivos recebam certificados usando uma conexão com a Internet.
    -  Trata-se de uma recomendação de segurança quando os dispositivos se conectam pela Internet para receber e renovar certificados.

> [!NOTE]           
> -    O servidor que hospeda o WAP [deve instalar uma atualização](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) que habilita o suporte para as URLs longas que são usadas pelo Serviço de Registro de Dispositivo de Rede. Essa atualização está incluída no [pacote cumulativo de atualizações de dezembro de 2014](http://support.microsoft.com/kb/3013769)ou individualmente no [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Além disso, o servidor que hospeda o WAP deve ter um certificado SSL que corresponde ao nome que está sendo publicado para clientes externos, bem como confiar no certificado SSL que é usado no servidor NDES. Esses certificados habilitam o servidor WAP a encerrar a conexão SSL de clientes e a criar uma nova conexão SSL com o servidor NDES.
Para obter mais informações sobre certificados de WAP, consulte a seção **Planejar certificados** de [Planejando Publicar Aplicativos Usando o Proxy de Aplicativo Web](https://technet.microsoft.com/library/dn383650.aspx). Para obter informações gerais sobre servidores WAP, consulte [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx) (Trabalhando com o Proxy de Aplicativo Web).|


### Certificados e modelos

|Objeto|Detalhes|
|----------|-----------|
|**Modelo de certificado**|Você configura este modelo na AC emissora.|
|**Certificado de autenticação de cliente**|Solicitado pela AC emissora ou pública, você instala este certificado no servidor de NDES.|
|**Certificado de autenticação de servidor**|Solicitado da AC emissora pública, você instala e associa o certificado SSL no IIS no servidor de NDES.|
|**Certificado de AC raiz confiável**|Você o exporta como um arquivo **.cer** da AC emissora ou de qualquer dispositivo que confie na AC emissora e o implanta nos dispositivos usando o perfil de certificado de AC confiável.<br /><br />Você usa um único certificado de AC raiz confiável por plataforma de sistema operacional e o associa a cada perfil de certificado de raiz confiável que criar.<br /><br />Você pode usar certificados de AC raiz confiável adicionais quando necessário. Por exemplo, você pode fazer isso para fornecer uma relação de confiança a uma AC que conecta os certificados de autenticação do servidor aos pontos de acesso Wi-Fi.|

### Contas

|Nome|Detalhes|
|--------|-----------|
|**Conta de serviço de NDES**|Especifique uma conta de usuário de domínio para usar como conta de serviço de NDES.|

## Configure sua infraestrutura
Antes de configurar perfis de certificado, você deve concluir as seguintes tarefas que exigem conhecimento do Windows Server 2012 R2 e dos AD CS (Serviços de Certificados do Active Directory):

**Tarefa 1**: Configurar modelos de certificado na autoridade de certificação

**Tarefa 2**, apenas perfil SCEP: Configurar pré-requisitos no servidor NDES

**Tarefa 3**, apenas perfil SCEP: Configurar NDES para uso com o Intune

**Tarefa 4**: Habilitar, instalar e configurar o Conector de Certificado do Intune

## Tarefa 1 – Configurar modelos de certificado na autoridade de certificação
Nesta tarefa, você vai:

-   Criar uma conta de serviço de NDES

    > [!NOTE] Para revogar certificados, a conta de serviço do NDES precisa de direitos de *Emitir e Gerenciar Certificados* para cada modelo de certificado usado por um perfil de certificado.

-   Configurar um modelo de certificado para o NDES

-   Publicar o modelo de certificado para o NDES

##### Para configurar a autoridade de certificação

1.  Crie uma conta de usuário de domínio para usar como conta de serviço de NDES. Especifique essa conta ao configurar modelos na AC emissora antes de instalar e configurar o NDES.

2.  Na AC emissora, use o snap-in de Modelos de Certificado para criar um novo modelo personalizado ou copie um modelo existente (como o modelo de Usuário) e o edite para uso com o NDES.

    O modelo deve ter as seguintes configurações:

    -   Especifique um **Nome amigável de exibição do modelo** para o modelo.

    -   Na guia **Nome da Entidade** , selecione **Fornecer na solicitação**. (A segurança é imposta pelo módulo de política do Intune para o NDES).

    -   Na guia **Extensões** , verifique se a **Descrição das Políticas de Aplicativo** inclui **Autenticação de Cliente**.

        > [!IMPORTANT] Para modelos de certificado do iOS e do Mac OS X, na guia **Extensões**, edite **Uso da Chave** e verifique se **A assinatura é uma prova de origem** não está selecionado.

    -   Na guia **Segurança**, adicione a conta de serviço NDES e dê a ela permissões para **Registrar** no modelo.

3.  Examine o **Período de validade** na guia **Geral** do modelo. Por padrão, o Intune usa o valor configurado no modelo. No entanto, você tem a opção de configurar a AC para permitir que o solicitante especifique um valor diferente, que você pode definir de dentro do Console do administrador do Intune. Se você quiser usar sempre o valor no modelo, ignore o restante desta etapa.

    > [!IMPORTANT] As plataformas do iOS e Mac OS X sempre usam o valor definido no modelo, independentemente de outras configurações que você fizer.

    Para configurar a AC para permitir que o solicitante especifique o período de validade, execute os seguintes comandos na AC:

    1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    2.  **net stop certsvc**

    3.  **net start certsvc**

4.  Na AC emissora, use o snap-in da Autoridade de Certificação para publicar o modelo de certificado.

    1.  Selecione o nó **Modelos de Certificado**, clique em **Ação**-&gt; **Novo** &gt; **Modelo de Certificado a Ser Emitido** e selecione o modelo que você criou na etapa 2.

    2.  Valide a publicação do modelo exibindo-o na pasta **Modelos de Certificado** .

5.  Para perfis .PFX: no computador da Autoridade de Certificação, certifique-se de que o computador que hospeda o Conector de Certificado do Intune tenha a permissão de registro, para que ele possa acessar o modelo usado na criação do perfil .PFX. Defina essa permissão na guia **Segurança** das propriedades do computador da Autoridade de Certificação.

## Tarefa 2 (somente perfil SCEP) - configurar pré-requisitos no servidor NDES
Nesta tarefa, você vai:

-   Adicionar o NDES a um Windows Server e configurar o IIS para dar suporte ao NDES

-   Adicionar a conta de serviço de NDES ao grupo IIS_IUSR

-   Definir o SPN da conta de serviço de NDES

##### Para configurar os pré-requisitos para o servidor de NDES

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

3.  Execute o comando a seguir para definir o SPN da conta de serviço de NDES:

    -   **setspn -s http/&lt;nome DNS do servidor NDES&gt; &lt;Nome de domínio&gt;\&lt;nome da conta de serviço de NDES&gt;**

    Por exemplo, se seu servidor de NDES se chamar **Server01**, seu domínio for **Contoso.com**e a conta de serviço for **NDESService**, use:

    -   **setspn –s http/Server01.contoso.com contoso\NDESService**

## Tarefa 3 (apenas perfil SCEP): Configurar NDES para uso com o Microsoft Intune 
Nesta tarefa, você vai:

-   Configurar o NDES para uso com a AC emissora

-   Associar o certificado de autenticação do servidor (SSL) no IIS

-   Configurar a Filtragem de Solicitações no IIS

##### Para configurar o NDES para uso com o Intune

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

3.  Depois de editar o Registro, execute **iisreset** no servidor para forçar o servidor para acompanhar as alterações de configuração recentes.

##### Para instalar e associar os certificados no Servidor de NDES

1.  No seu Servidor de NDES, solicite e instale um certificado de **autenticação de servidor** por meio da sua AC interna ou pública. Em seguida, você associará esse certificado SSL no IIS.

    > [!TIP]
    > Depois de associar o certificado SSL no IIS, você também instalará um certificado de autenticação de cliente. Esse certificado pode ser emitido por qualquer AC em que o Servidor de NDES confie. Embora não seja uma prática recomendada, você pode usar o mesmo certificado para autenticação de servidor e cliente, desde que o certificado tenha os dois EKUs (Usos Avançados de Chave). Examine as etapas a seguir para obter informações sobre esses certificados de autenticação.

    1.  Depois de obter o certificado de autenticação de servidor, abra o **Gerenciador do IIS**, selecione o **Site Padrão** no painel **Conexões** e clique em **Ligações** no painel **Ações** .

    2.  Clique em **Adicionar**, defina o **Tipo** como **https**e verifique se a porta é **443**. (Somente a porta 443 tem suporte para o Intune autônomo).

    3.  Para **Certificado SSL**, especifique o certificado de autenticação de servidor.

        > [!NOTE] Se o servidor NDES usar um nome interno e externo para um único endereço de rede, o certificado de autenticação de servidor deverá ter um **Nome da Entidade** com um nome de servidor público externo e um **Nome Alternativo da Entidade** que inclua o nome do servidor interno.

2.  No seu Servidor de NDES, solicite e instale um certificado de **autenticação de cliente** da sua AC interna ou uma AC pública. Pode ser o mesmo certificado que o certificado de autenticação de servidor se o certificado tiver os dois recursos.

    O certificado de autenticação de cliente deve ter as seguintes propriedades:

    **Uso Avançado de Chave** - Isso deve incluir a **Autenticação de Cliente**.

    **Nome da Entidade**: deve ser igual ao nome DNS do servidor em que você está instalando o certificado (o Servidor de NDES).

##### Para configurar a Filtragem de Solicitações do IIS

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

## Tarefa 4 - Habilitar, instalar e configurar o Conector de Certificado do Intune - para certificados SCEP e .PFX.
Nesta tarefa, você vai:

Habilitar o suporte para NDES no Intune

Baixar, instalar e configurar o Conector de Certificado no Servidor de NDES

##### Para habilitar o suporte ao Conector de Certificado

1.  Abra o [Console de administração do Intune](https://manage.microsoft.com), clique em **Administrador** &gt; **Conector de Certificado**.

2.  Clique em **Configurar Conector de Certificado Local**.

3.  Selecione **Habilitar Conector de Certificado**e clique em **OK**.

##### Para baixar, instalar e configurar o Conector de Certificado

1.  Abra o [Console de administração do Intune](https://manage.microsoft.com) e, em seguida, clique em **Administrador** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Conector de Certificado** &gt; **Baixar Conector de Certificado**.

2.  Após a conclusão do download, execute o instalador baixado (**ndesconnectorssetup.exe**):

    -   Para certificados .PFX, execute o instalador no computador capaz de se conectar à Autoridade de Certificação. Escolha a opção de Distribuição .PFX e clique em Instalar. Quando a instalação for concluída, continue criando um perfil de certificado conforme descrito em [Configure certificate profiles](configure-intune-certificate-profiles.md) (Configurar perfis de certificado).

    -   Para certificados SCEP, execute o instalador em um servidor Windows Server 2012 R2

    Para a opção SCEP, o instalador também instala o módulo de política para NDES e o Serviço Web CRP. (O Serviço Web de CRP, CertificateRegistrationSvc, é executado como um aplicativo no IIS).

    > [!NOTE]
    > Quando você instala o NDES para o Intune autônomo, o serviço de CRP é instalado automaticamente com o Conector de Certificado. Quando você usa o Intune com o Configuration Manager, instala o Ponto de Registro de Certificado como uma função de sistema de site separada.

3.  Quando for solicitado o certificado de cliente do Conector de Certificado, clique em **Selecionar**e selecione o certificado de **autenticação de cliente** instalado no Servidor NDES na Tarefa 3.

    Depois de selecionar o certificado de autenticação de cliente, você retornará para a superfície do **Certificado de Cliente para o Conector de Certificado do Microsoft Intune** . Embora o certificado selecionado não seja exibido, clique em **Avançar** para ver as propriedades do certificado. Em seguida, clique em **Avançar**e clique em **Instalar**.

4.  Após a conclusão do assistente, mas antes de fechá-lo, clique em **Iniciar a Interface do Usuário do Conector de Certificado**.

    > [!TIP] Se fechar o assistente antes de iniciar a interface do usuário do Conector de Certificado, você poderá reabri-lo executando o seguinte comando:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  Na interface do usuário do **Conector de Certificado** :

    Clique em **Entrar** e insira suas credenciais de administrador de serviços do Intune ou as credenciais de um administrador de locatários com permissão de administração global.

    Se sua organização usa um servidor proxy e o proxy é necessário para o servidor NDES acessar a Internet, clique em **Usar servidor proxy** e informe o nome do servidor proxy, a porta e as credenciais de conta usadas para a conexão.

    Selecione a guia **Avançado** e forneça credenciais para uma conta que tenha a permissão **Emitir e Gerenciar Certificados** na sua Autoridade de Certificação emissora e clique em **Aplicar**.

    Agora você pode fechar a interface do usuário do Conector de Certificado.

6.  Abra um prompt de comando e digite **services.msc**, pressione **Enter**, clique com o botão direito do mouse em **Serviço de Conector do Intune** e clique em **Reiniciar**.

Para validar que o serviço está em execução, abra um navegador e digite a seguinte URL, que deve retornar um erro **403** :

**http:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**

### Próximas etapas
Agora você está pronto para configurar perfis de certificado, conforme descrito em [Configure certificate profiles](configure-intune-certificate-profiles.md) (Configurar perfis de certificado).


<!--HONumber=May16_HO4-->


