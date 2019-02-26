---
title: Usar certificados SCEP com o Microsoft Intune – Azure | Microsoft Docs
description: Para usar certificados SCEP no Microsoft Intune, configure seu domínio do AD local, crie uma autoridade de certificação, configure o servidor NDES e instale o Conector de Certificado do Intune. Em seguida, crie um perfil de certificado SCEP e atribua esse perfil a grupos. Consulte também as IDs de eventos diferentes e suas descrições e os códigos de diagnósticos para o serviço do conector do Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cdc0f02aa09edd05314d0d4a6a2abacc98c94bf2
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742730"
---
# <a name="configure-and-use-scep-certificates-with-intune"></a>Configurar e usar certificados SCEP com o Intune

Este artigo mostra como configurar sua infraestrutura e depois criar e atribuir perfis de certificado de protocolo SCEP (Simple Certificate Enrollment Protocol) com o Intune.

## <a name="configure-on-premises-infrastructure"></a>Configurar a infraestrutura local

- **Domínio do Active Directory**: Todos os servidores listados nesta seção (exceto pelo Servidor Proxy de Aplicativo Web) devem ser associados ao seu domínio do Active Directory.

- **AC (Autoridade de certificação)**: Deve ser uma AC (Autoridade de Certificação) Corporativa da Microsoft que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. Para obter detalhes, confira [Instalar a Autoridade de Certificação](http://technet.microsoft.com/library/jj125375.aspx).
    Se a sua AC executar o Windows Server 2008 R2, você deve [instalar o hotfix de KB2483564](http://support.microsoft.com/kb/2483564/).

- **Servidor NDES**: Em um Windows Server 2012 R2 ou posterior, configure a função de servidor NDES (Serviço de Registro de Dispositivo de Rede). O Intune não é compatível com o uso do NDES em um servidor que também executa a AC corporativa. Confira [Diretrizes do Serviço de Registro de Dispositivo de Rede](http://technet.microsoft.com/library/hh831498.aspx) para obter instruções sobre como configurar o Windows Server 2012 R2 para hospedar o NDES.
O servidor do NDES deve ser associado a um domínio na mesma floresta que a AC corporativa. Há mais informações sobre como implantar o servidor NDES em uma floresta separada, rede isolada ou domínio interno em [Usando um Módulo de Política com o Serviço de Registro de Dispositivo de Rede](https://technet.microsoft.com/library/dn473016.aspx).

- **Microsoft Intune Certificate Connector**: Baixe o instalador do **Certificate Connector** (**NDESConnectorSetup.exe**) no portal de administração do Intune. Você executará esse instalador no servidor com a função de NDES.  

  - O conector do Certificado NDES também dá suporte ao modo do padrão FIPS. O FIPS não é necessário, mas você poderá emitir e revogar certificados quando estiver habilitado.

- **Servidor Proxy de Aplicativo Web** (opcional): Use um servidor que execute o Windows Server 2012 R2 ou posterior como servidor WAP (Proxy de aplicativo Web). Essa configuração:
  - Permite que os dispositivos recebam certificados usando uma conexão com a Internet.
  - Trata-se de uma recomendação de segurança quando os dispositivos se conectam pela Internet para receber e renovar certificados.
  
- **Proxy de Aplicativo do Azure AD** (opcional): O Proxy de Aplicativo do Azure AD pode ser usado em vez de um servidor WAP (Proxy de aplicativo Web) dedicado para publicar o servidor NDES na Internet. Para obter mais informações, confira [Como fornecer acesso remoto seguro a aplicativos locais](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

#### <a name="additional"></a>Adicional

- O servidor que hospeda o WAP [deve instalar uma atualização](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) que habilita o suporte para as URLs longas que são usadas pelo Serviço de Registro de Dispositivo de Rede. Essa atualização está incluída no [pacote cumulativo de atualizações de dezembro de 2014](http://support.microsoft.com/kb/3013769)ou individualmente no [KB3011135](http://support.microsoft.com/kb/3011135).
- O servidor WAP deve ter um certificado SSL que corresponda ao nome que está sendo publicado para clientes externos e confiar no certificado SSL usado no servidor NDES. Esses certificados habilitam o servidor WAP a encerrar a conexão SSL de clientes e a criar uma nova conexão SSL com o servidor NDES.

Para obter mais informações, consulte [Planejar certificados WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates) e [informações gerais sobre servidores WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)).

### <a name="network-requirements"></a>Requisitos de rede

Se você não usar um proxy reverso, como WAP ou Proxy de Aplicativo do Azure AD, permita o tráfego TCP na porta 443 de todos os endereços IP/hosts na Internet para o servidor NDES.

Permita todas as portas e protocolos necessários entre o servidor NDES e qualquer infraestrutura de suporte. Por exemplo, o servidor NDES precisa se comunicar com a AC, os servidores DNS, os servidores do Configuration Manager, os controladores de domínio e possivelmente outros serviços em seu ambiente.

Recomendamos publicar o servidor NDES por meio de um proxy reverso, como o [Proxy de Aplicativo do Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), o [Proxy do Acesso via Web](https://technet.microsoft.com/library/dn584107.aspx) ou um proxy de terceiros.

### <a name="certificates-and-templates"></a>Certificados e modelos  

|Objeto|Detalhes|
|----------|-----------|
|**Modelo de certificado**|Configure este modelo na AC emissora.|
|**Certificado de autenticação de cliente**|Solicitado pela AC emissora ou pública, você instala este certificado no servidor de NDES.|
|**Certificado de autenticação de servidor**|Solicitado da AC emissora pública, você instala e associa o certificado SSL no IIS no servidor de NDES. Se o certificado tiver o conjunto de usos de chave de autenticação de cliente e servidor (**Usos de Chave Avançados**), você poderá usar o mesmo certificado.|
|**Certificado de AC raiz confiável**|Exporte esse certificado como um arquivo **.cer** da AC raiz ou de qualquer dispositivo que confie em sua AC raiz. Em seguida, atribua-o a usuários, dispositivos ou a ambos, usando o perfil do Certificado de Autoridade de Certificação confiável.<br /><b>OBSERVAÇÃO:<b /> quando um perfil de certificado SCEP for atribuído, certifique-se de atribuir o perfil do Certificado raiz confiável referenciado no perfil de certificado SCEP ao mesmo grupo de dispositivos ou usuários.<br /><br />Você usa um único certificado de AC raiz confiável por plataforma de sistema operacional e o associa a cada perfil de certificado de raiz confiável que criar.<br /><br />Você pode usar certificados de AC raiz confiável adicionais quando necessário. Por exemplo, você pode fazer isso para fornecer uma relação de confiança a uma AC que conecta os certificados de autenticação do servidor aos pontos de acesso Wi-Fi.|

### <a name="accounts"></a>Contas

|Nome|Detalhes|
|--------|-----------|
|**Conta de serviço de NDES**|Insira uma conta de usuário de domínio para usar como conta de Serviço NDES. |

## <a name="configure-your-infrastructure"></a>Configure sua infraestrutura
Antes de configurar perfis de certificado, conclua as tarefas a seguir. Estas etapas exigem conhecimento do Windows Server 2012 R2 ou posterior e do ADCS (Serviços de Certificados do Active Directory):

#### <a name="step-1---create-an-ndes-service-account"></a>Etapa 1 - Criar uma conta de serviço de NDES

Crie uma conta de usuário de domínio para usar como conta de serviço de NDES. Insira essa conta ao configurar modelos na AC emissora antes de instalar e configurar o NDES. Verifique se o usuário tem os direitos padrão, que são os direitos **Logon Localmente**, **Logon como Serviço** e **Logon como um trabalho em lotes**. Algumas organizações têm políticas de proteção que desabilitam esses direitos de proteção.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Etapa 2 - Configurar modelos de certificado na autoridade de certificação
Nesta etapa:

- Configurar um modelo de certificado para o NDES
- Publicar o modelo de certificado para o NDES

##### <a name="configure-the-certification-authority"></a>Configurar a autoridade de certificação

1. Entre como administrador corporativo.

2. Na AC emissora, use o snap-in de Modelos de Certificado para criar um novo modelo personalizado. Ou copie um modelo existente e, em seguida, atualize esse modelo existente (como o Modelo de Usuário) para uso com o NDES.

   >[!NOTE]
   > O modelo de certificado NDES deve ser baseado em um Modelo de Certificado v2 (com a compatibilidade para Windows 2003).

   O modelo deve ter as seguintes configurações:

   - Em **Geral**:
   
       - Confirme que a propriedade **Publicar certificado no Active Directory** **não** está marcada.
       - Insira um **Nome de exibição do modelo** amigável para o modelo.

   - Em **Nome da Entidade**, selecione **Fornecimento na solicitação**. (A segurança é imposta pelo módulo de política do Intune para o NDES).

   - Em **Extensões**, conforme que a **Descrição das Políticas de Aplicativo** inclui **Autenticação de Cliente**.

     > [!IMPORTANT]
     > Para modelos de certificado do iOS e macOS, na guia **Extensões**, edite **Uso da Chave** e confirme que a opção **A assinatura é uma prova de origem** não está selecionada.

   - Em **Segurança**, adicione a conta de serviço NDES e dê a ela permissões para **Registrar** no modelo. Os administradores do Intune que criam perfis SCEP exigem direitos de **leitura** para poderem navegar no modelo durante a criação de perfis SCEP.

     > [!NOTE]
     > Para revogar certificados, a conta de serviço do NDES precisa de direitos de *Emitir e Gerenciar Certificados* para cada modelo de certificado usado por um perfil de certificado.

3. Examine o **Período de validade** na guia **Geral** do modelo. Por padrão, o Intune usa o valor configurado no modelo. No entanto, você pode configurar a AC para permitir que o solicitante insira um valor diferente, que pode ser definido dentro do console do Administrador do Intune. Se quiser usar sempre o valor no modelo, ignore o restante desta etapa.

   > [!IMPORTANT]
   > O iOS e o macOS sempre usam o valor definido no modelo, independentemente de outras configurações que você fizer.

Exemplo de configuração de modelo:

![Modelo, guia de tratamento de solicitação](./media/scep_ndes_request_handling.png)

![Modelo, guia de nome da entidade](./media/scep_ndes_subject_name.jpg)

![Modelo, guia de segurança](./media/scep_ndes_security.jpg)

![Modelo, guia de extensões](./media/scep_ndes_extensions.jpg)

![Modelo, guia de requisitos de emissão](./media/scep_ndes_issuance_reqs.jpg)

> [!IMPORTANT]
> Para Políticas de Aplicativo, adicione somente as políticas de aplicativo necessárias. Confirme suas escolhas com seus administradores de segurança.

Configurar a AC para permitir que o solicitante insira o período de validade:

1. Na AC, execute os seguintes comandos:
   - **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   - **net stop certsvc**
   - **net start certsvc**

2. Na AC emissora, use o snap-in da Autoridade de Certificação para publicar o modelo de certificado.
   Selecione o nó **Modelos de Certificado**, clique em **Ação** > **Novo** > **Modelo de Certificado a Ser Emitido** e selecione o modelo que você criou na etapa 2.

3. Valide a publicação do modelo exibindo-o na pasta **Modelos de Certificado** .

#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>Etapa 3 - Configurar pré-requisitos no servidor NDES
Nesta etapa:

- Adicionar o NDES a um Windows Server e configurar o IIS para dar suporte ao NDES
- Adicionar a conta de serviço de NDES ao grupo IIS_IUSR
- Configurar o SPN (nome da entidade de serviço) para a conta de serviço de NDES

1. No servidor que hospeda o NDES, entre como **Administrador Corporativo** e use o [Assistente de Adição de Funções e Recursos](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) para instalar o NDES:

   1. No assistente, selecione **Serviços de Certificados do Active Directory** para acessar os Serviços de Função do AD CS. Selecione o **Serviço de Registro de Dispositivo de Rede**, desmarque **Autoridade de Certificação**e conclua o assistente.

      > [!TIP]
      > Em **Andamento da instalação**, não marque **Fechar**. Em vez disso, selecione o link **Configurar Serviços de Certificados do Active Directory no servidor de destino**. O assistente de **Configuração do AD CS**, que você usará para a próxima etapa. Após Configuração AD CS abrir, você pode fechar o Assistente de Adição de Funções e Recursos.

   2. Quando o NDES é adicionado ao servidor, o assistente também instala o IIS. Verifique se o IIS tem as seguintes configurações:

       - **Servidor Web** > **Segurança** > **Filtragem de Solicitações**

       - **Servidor Web** > **Desenvolvimento de Aplicativos** > **ASP.NET 3.5** 

            Instalar o ASP.NET 3.5 instala o .NET Framework 3.5. Ao instalar o .NET Framework 3.5, instale o recurso **.NET Framework 3.5** principal e o **Ativação HTTP**.

       - **Servidor Web** > **Desenvolvimento de Aplicativos** > **ASP.NET 4.5** 

            Instalar o ASP.NET 4.5 instala o .NET Framework 4.5. Ao instalar o .NET Framework 4.5, instale o recurso principal do **.NET Framework 4.5**, o **ASP.NET 4.5** e o recurso **Serviços WCF** > **Ativação HTTP**.

       - **Ferramentas de Gerenciamento** > **Compatibilidade com Gerenciamento do IIS 6** > **Compatibilidade com Metabase do IIS 6**

       - **Ferramentas de Gerenciamento** > **Compatibilidade com Gerenciamento do IIS 6** > **Compatibilidade com WMI do IIS 6**

       - No servidor, adicione a conta de serviço de NDES como membro do grupo **IIS_IUSR** local.

2. Em um prompt de comandos com privilégios elevados, execute o seguinte comando para definir o SPN da conta de serviço de NDES:

    `setspn -s http/<DNS name of NDES Server> <Domain name>\<NDES Service account name>`

    Por exemplo, se seu servidor de NDES se chamar **Server01**, seu domínio for **Contoso.com**e a conta de serviço for **NDESService**, use:

    `setspn –s http/Server01.contoso.com contoso\NDESService`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Etapa 4 - Configurar o NDES para uso com o Intune
Nesta etapa:

- Configurar o NDES para uso com a AC emissora
- Associar o certificado de autenticação do servidor (SSL) no IIS
- Configurar a filtragem de solicitações no IIS

1. No servidor NDES, abra o Assistente de Configuração do AD CS e faça as seguintes atualizações:

    > [!TIP]
    > Se você clicou no link na etapa anterior, o assistente já estará aberto. Caso contrário, abra o Gerenciador do Servidor para acessar a configuração pós-implantação dos Serviços de Certificados do Active Directory.

   - Na página **Serviços de Função**, selecione **Serviço de Registro de Dispositivo de Rede**
   - Em **Conta de Serviço para NDES**, insira Conta de Serviço do NDES
   - EM **AC para NDES**, clique em **Selecionar** e selecione a AC emissora em que você configurou o modelo de certificado
   - Em **Criptografia para NDES**, defina o comprimento da chave para atender aos requisitos da sua empresa.
   - Em **Confirmação**, selecione **Configurar** para concluir o assistente.

2. Após concluir o assistente, atualize a seguinte chave do Registro no Servidor de NDES:

    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`

    Para atualizar essa chave, identifique a **Finalidade** do modelo de certificado (encontrada na guia **Tratamento de Solicitação**). Em seguida, atualize a entrada do Registro correspondente, substituindo os dados existentes pelo nome do modelo de certificado (não o nome de exibição do modelo) que você especificou na Etapa 2. A tabela a seguir mapeia a finalidade do modelo de certificado de acordo com os valores do Registro:

    |Finalidade do modelo de certificado (na guia Tratamento de Solicitação)|Valor de registro a ser editado|O valor mostrado no console de administração do Intune para o perfil do protocolo SCEP|
    |---|---|---|
    |Assinatura|SignatureTemplate|Assinatura digital|
    |Criptografia|EncryptionTemplate|Codificação de chave|
    |Assinatura e criptografia|GeneralPurposeTemplate|Codificação de chave<br/>Assinatura digital|

    Por exemplo, se a Finalidade do seu modelo de certificado for **Criptografia**, edite o valor de **EncryptionTemplate** como o nome do seu modelo de certificado.

3. O servidor NDES recebe URLs longas (consultas), que exigem que você adicione duas entradas de registro:


   |                        Local                        |      Valor      | Tipo  |      Dados       |
   |--------------------------------------------------------|-----------------|-------|-----------------|
   | HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters | MaxFieldLength  | DWORD | 65534 (decimal) |
   | HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters | MaxRequestBytes | DWORD | 65534 (decimal) |

4. No Gerenciador do IIS, selecione **Site Padrão** > **Filtragem de Solicitação** > **Editar Configuração do Recurso**. Altere o **Comprimento máximo da URL** e a **Cadeia de caracteres de consulta máxima** para *65534*, conforme mostrado:

    ![Comprimento máximo de URL e consulta do IIS](./media/SCEP_IIS_max_URL.png)

5. Reinicie o servidor. Não use **iisreset**, pois não finaliza essas alterações.
6. Navegue até `http://*FQDN*/certsrv/mscep/mscep.dll`. Você deve ver uma página NDES semelhante a esta:

    ![Testar NDES](./media/SCEP_NDES_URL.png)

    Se você receber a mensagem **503 Serviço indisponível**, verifique o visualizador de eventos. É provável que o pool de aplicativos seja interrompido devido a um direito ausente para o usuário NDES. Esses direitos são descritos na Etapa 1.

##### <a name="install-and-bind-certificates-on-the-ndes-server"></a>Para instalar e associar os certificados no Servidor de NDES

1. No seu Servidor de NDES, solicite e instale um certificado de **autenticação de servidor** por meio da sua AC interna ou pública. Em seguida, associe esse certificado SSL no IIS.

    > [!TIP]
    > Depois de associar o certificado SSL no IIS, instale um certificado de autenticação de cliente. Esse certificado pode ser emitido por qualquer AC em que o Servidor de NDES confie. O mesmo certificado poderá ser usado se ele tiver o conjunto de usos de chave de autenticação de cliente e servidor (**Usos de Chave Avançados**). Examine as etapas a seguir para obter informações sobre esses certificados de autenticação.

   1. Depois de obter o certificado de autenticação de servidor, abra **Gerenciador do IIS** e selecione o **Site Padrão**. No painel **Ações**, selecione **Associações**.

   2. Selecione **Adicionar**, defina **Tipo** como **https** e, em seguida, confirme que a porta é **443**. Somente a porta 443 é compatível com o Intune autônomo.

   3. Para **Certificado SSL**, insira o certificado de autenticação de servidor.

      > [!NOTE]
      > Se o servidor NDES usar nomes interno e externo para um único endereço de rede, o certificado de autenticação de servidor deverá ter:
      > - Um **Nome da Entidade** com um nome do servidor público externo
      > - Um **Nome Alternativo da Entidade** que inclua o nome do servidor interno

2. No seu Servidor de NDES, solicite e instale um certificado de **autenticação de cliente** da sua AC interna ou uma AC pública. Este certificado poderá ser o mesmo que o certificado de autenticação de servidor caso tenha as duas funcionalidades.

    O certificado de autenticação de cliente deve ter as seguintes propriedades:

    - **Uso avançado de chave**: Esse valor deve incluir a **Autenticação do Cliente**

    - **Nome da Entidade**: O valor deve ser igual ao nome DNS do servidor no qual você está instalando o certificado (o Servidor de NDES)

##### <a name="configure-iis-request-filtering"></a>Configurar filtragem de solicitações do IIS

1. No Servidor de NDES, abra o **Gerenciador do IIS**, selecione o **Site Padrão** no painel **Conexões** e abra a **Filtragem de Solicitações**.

2. Selecione **Editar Configurações de Recurso** e defina os valores:

    - **cadeia de caracteres de consulta (Bytes)** = **65534**
    - **Tamanho máximo da URL (Bytes)** = **65534**

3. Examine a seguinte chave do Registro:

    `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters`

    Confirme que os seguintes valores estão definidos como entradas DWORD:

    - Nome: **MaxFieldLength**, com um valor decimal de **65534**
    - Nome: **MaxRequestBytes**, com um valor decimal de **65534**

4. Reinicialize o servidor NDES. Agora, o servidor está pronto para dar suporte ao Conector de Certificado.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Etapa 5 - Habilitar, instalar e configurar o Conector de Certificado do Intune
Nesta etapa:

- Habilitar o suporte para NDES no Intune.
- Baixe, instale e configure o Certificate Connector no servidor que hospeda a função do NDES (Serviço de Registro de Dispositivo de Rede) em seu ambiente. Para aumentar a escala da implementação do NDES em sua organização, você pode instalar vários servidores de NDES com um Microsoft Intune Certificate Connector em cada servidor do NDES.

##### <a name="download-install-and-configure-the-certificate-connector"></a>Baixar, instalar e configurar o conector de certificado

> [!IMPORTANT] 
> O Microsoft Intune Certificate Connector **deve** ser instalado em um servidor Windows separado. Não pode ser instalado na AC (autoridade de certificação) emissora. Também **deve** ser instalado no mesmo servidor que a função do Serviço de Registro de Dispositivo de Rede (NDES).

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Autoridade de certificação** > **Adicionar**
3. Faça o download e salve o arquivo do conector. Salve-o em uma localização acessível por meio do servidor no qual você instalará o conector.

    ![ConnectorDownload](./media/certificates-download-connector.png)

4. Após a conclusão do download, acesse o servidor que hospeda a função do NDES (Serviço de Registro de Dispositivo de Rede). Em seguida:

    1. Verifique se o .NET 4.5 Framework está instalado, pois ele é necessário para o conector do Certificado NDES. O .NET 4.5 Framework é automaticamente incluído no Windows Server 2012 R2 e versões mais recentes.
    2. Execute o instalador (**NDESConnectorSetup.exe**). O instalador também instala o módulo de política para NDES e o Serviço Web de CRP. O Serviço Web de CRP, CertificateRegistrationSvc, é executado como um aplicativo no IIS.

    > [!NOTE]
    > Quando você instala o NDES para o Intune autônomo, o serviço de CRP é instalado automaticamente com o Conector de Certificado. Quando você usa o Intune com o Configuration Manager, instala o Ponto de Registro de Certificado como uma função de sistema de site separada.

5. Quando for solicitado o certificado do cliente para o Certificate Connector, escolha **Selecionar** e selecione o certificado de **autenticação de cliente** instalado no Servidor NDES na Etapa 4.

    Depois de selecionar o certificado de autenticação de cliente, você retornará para a superfície do **Certificado de Cliente para o Conector de Certificado do Microsoft Intune** . Embora o certificado selecionado não seja exibido, selecione **Avançar** para exibir as propriedades do certificado. Selecione **Avançar** e, em seguida, **Instalar**.

    > [!IMPORTANT]
    > A Configuração de Segurança Reforçada do Internet Explorer [deve ser desabilitada no servidor NDES](https://technet.microsoft.com/library/cc775800(v=WS.10).aspx) hospedando o Intune Certificate Connector.

6. Após a conclusão do assistente, mas antes de fechá-lo, escolha **Iniciar a Interface do Usuário do Conector de Certificado**.

    > [!TIP]
    > Se fechar o assistente antes de iniciar a interface do usuário do Conector de Certificado, você poderá reabri-la executando o seguinte comando:
    >
    > <caminho_instalação>\NDESConnectorUI\NDESConnectorUI.exe

7. Na interface do usuário do **Conector de Certificado** :

    Selecione em **Entrar** e insira suas credenciais de administrador de serviços do Intune ou as credenciais de um administrador de locatários com permissão de administração global. Depois que você entrar, o Intune Certificate Connector baixará um certificado do Intune. Esse certificado é usado para autenticação entre o conector e o Intune.

    > [!IMPORTANT]
    > A conta de usuário deve ter uma licença válida do Intune. Se a conta de usuário não tiver uma licença válida do Intune, o NDESConnectorUI.exe falhará.

    Se a sua organização usar um servidor proxy e o proxy for necessário para o servidor NDES acessar a Internet, selecione **Usar servidor proxy**. Em seguida, insira as credenciais de conta, a porta e nome do servidor proxy para se conectar.

    Selecione a guia **Avançado** e insira credenciais para uma conta que tenha a permissão **Emitir e Gerenciar Certificados** na sua Autoridade de Certificação emissora. **Aplique** suas alterações.

    Agora você pode fechar a interface do usuário do Conector de Certificado.

8. Abra um prompt de comando, digite **services.msc** e, em seguida, **Enter**. Clique com o botão direito do mouse em **Serviço do Conector do Intune** > **Reiniciar**.

Para validar se o serviço está em execução, abra um navegador e insira a URL a seguir. Ele deverá retornar um erro **403**:

`http://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`

> [!NOTE]
> O suporte ao TLS 1.2 é incluído no conector do Certificado NDES. Se o servidor com o conector do Certificado NDES instalado dá suporte ao TLS 1.2, o protocolo TLS 1.2 é usado. Se o servidor não dá suporte ao TLS 1.2, o TLS 1.1 é usado. Atualmente, o TLS 1.1 é usado para autenticação entre os dispositivos e o servidor.

## <a name="create-a-scep-certificate-profile"></a>Criar um perfil de certificado SCEP

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira um **Nome** e uma **Descrição** para o perfil de certificado SCEP.
4. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado SCEP. No momento, é possível selecionar uma das seguintes plataformas para as configurações de restrição de dispositivo:
   - **Android**
   - **Android Enterprise**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 e posterior**
   - **Windows 10 e posterior**
5. Na lista suspensa de tipos de **Perfil**, selecione **Certificado SCEP**.
6. Insira as seguintes configurações:

   - **Tipo de certificado**: Escolha **Usuário** para ver os certificados de usuário. Escolha **Dispositivo** para dispositivos sem usuário, como quiosques. Os certificados do **dispositivo** estão disponíveis para as seguintes plataformas:  
     - Android Enterprise
     - iOS
     - macOS
     - Windows 8.1 e posterior
     - Windows 10 e posterior


   - **Formato de nome de entidade**: Selecione como o Intune cria automaticamente o nome da entidade na solicitação de certificado. As opções serão alteradas se você escolher um tipo de certificado de **usuário** ou um tipo de certificado de **dispositivo**. 

        **Tipo de certificado de usuário**  

        É possível incluir o endereço de email do usuário no nome da entidade. Escolha:

        - **Não configurado**
        - **Nome comum**
        - **Nome comum incluindo email**
        - **Nome comum como email**
        - **IMEI (Identificação Internacional de Equipamento Móvel)**
        - **Número de série**
        - **Personalizado**: Ao selecionar essa opção, a caixa de texto **Personalizado** também é exibida. Use esse campo para inserir um formato de nome de entidade personalizado, incluindo variáveis. O formato personalizado dá suporte a duas variáveis: **Nome Comum (NC)** e **Email (E)**. **CN (Nome Comum)** pode ser definido para qualquer uma das seguintes variáveis:

            - **CN={{UserName}}**: O nome principal do usuário, tal como janedoe@contoso.com
            - **CN={{AAD_Device_ID}}**: Uma ID atribuída ao registrar um dispositivo no Azure AD (Active Directory). Essa ID normalmente é usada para autenticar com o Azure AD.
            - **CN={{SERIALNUMBER}}**: O número de série (SN) exclusivo normalmente usado pelo fabricante para identificar um dispositivo
            - **CN={{IMEINumber}}**: O número exclusivo do IMEI (Identidade Internacional de Equipamento Móvel) usado para identificar um celular
            - **CN={{OnPrem_Distinguished_Name}}**: Uma sequência de nomes distintos relativos separados por vírgula, como `CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com`

                Para usar a variável `{{OnPrem_Distinguished_Name}}`, sincronize o atributo de usuário `onpremisesdistingishedname` usando o [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) com seu Azure AD.

            - **CN={{onPremisesSamAccountName}}**: Os administradores podem sincronizar o atributo samAccountName do Active Directory para o Azure AD usando o Azure AD Connect em um atributo chamado `onPremisesSamAccountName`. O Intune pode substituir essa variável como parte de uma solicitação de emissão de certificado no assunto de um certificado do protocolo SCEP.  O atributo samAccountName é o nome de logon do usuário usado para dar suporte a clientes e servidores de uma versão anterior do Windows (pré-Windows 2000). O formato de nome de logon do usuário é: `DomainName\testUser`, ou apenas `testUser`.

                Para usar a variável `{{onPremisesSamAccountName}}`, sincronize o atributo de usuário `onPremisesSamAccountName` usando o [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) com seu Azure AD.

            Usando uma combinação de uma ou mais dessas variáveis e cadeias de caracteres estáticas, é possível criar um formato de nome de entidade personalizado, como:  

            **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**

            Neste exemplo, você criou um formato de nome de entidade que, além das variáveis CN e E, usa cadeias de caracteres para os valores Unidade Organizacional, Organização, Local, Estado e País. [Função CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) descreve essa função e suas cadeias de caracteres compatíveis.

        **Tipo de certificado de dispositivo**  

        Quando você usa o tipo de certificado **Dispositivo**, você também pode usar as seguintes variáveis de certificado do dispositivo para o valor:  

        ```
        "{{AAD_Device_ID}}",
        "{{Device_Serial}}",
        "{{Device_IMEI}}",
        "{{SerialNumber}}",
        "{{IMEINumber}}",
        "{{AzureADDeviceId}}",
        "{{WiFiMacAddress}}",
        "{{IMEI}}",
        "{{DeviceName}}",
        "{{FullyQualifiedDomainName}}",
        "{{MEID}}",
        ```

        Essas variáveis podem ser adicionadas com texto estático em uma caixa de texto de valor personalizada. Por exemplo, o nome comum pode ser adicionado como `CN = {{DeviceName}}text`.

        > [!IMPORTANT]
        >  - No texto estático da entidade, chaves **{ }** não incluídas em uma variável resolvem um erro. 
        >  - Ao usar uma variável de certificado do dispositivo, coloque a variável entre chaves **{}**.
        >  - `{{FullyQualifiedDomainName}}` funciona somente para dispositivos Windows e unidos ao domínio. 
        >  -  Ao usar propriedades do dispositivo, como IMEI, número de série e nome de domínio totalmente qualificado no assunto ou SAN para um certificado de dispositivo, esteja ciente de que essas propriedades podem ser falsificadas por uma pessoa com acesso ao dispositivo.
        >  - O perfil não será instalado no dispositivo se não houver suporte para as variáveis de dispositivo especificadas. Por exemplo, se {{IMEI}} for usado no nome da entidade do perfil SCEP atribuído a um dispositivo que não tem um número IMEI, ocorrerá falha na instalação do perfil. 


   - **Nome alternativo da entidade**: Informe como o Intune cria automaticamente os valores para o nome alternativo da entidade (SAN) na solicitação de certificado. As opções serão alteradas se você escolher um tipo de certificado de **usuário** ou um tipo de certificado de **dispositivo**. 

        **Tipo de certificado de usuário**  

        Os seguintes atributos estão disponíveis:

        - Endereço de email
        - UPN (Nome UPN)

            Por exemplo, se você selecionar um tipo de certificado de usuário, poderá incluir o nome UPN no nome alternativo da entidade. Se um certificado do cliente for usado para se autenticar em um Servidor de Políticas de Rede, defina o nome alternativo da entidade como o UPN. 

        **Tipo de certificado de dispositivo**  

        Uma caixa de texto em formato de tabela que você pode personalizar. Os seguintes atributos estão disponíveis:

        - DNS

        Com o tipo de certificado **Dispositivo**, é possível usar as seguintes variáveis de certificado do dispositivo para o valor:  

        ```
        "{{AAD_Device_ID}}",
        "{{Device_Serial}}",
        "{{Device_IMEI}}",
        "{{SerialNumber}}",
        "{{IMEINumber}}",
        "{{AzureADDeviceId}}",
        "{{WiFiMacAddress}}",
        "{{IMEI}}",
        "{{DeviceName}}",
        "{{FullyQualifiedDomainName}}",
        "{{MEID}}",
        ```

        Essas variáveis podem ser adicionadas com texto estático na caixa de texto de valor personalizada. Por exemplo, o atributo DNS pode ser adicionado como `DNS name = {{AzureADDeviceId}}.domain.com`.

        > [!IMPORTANT]
        >  - No texto estático do SAN, chaves **{ }**, barras verticais **|** e ponto e vírgulas **;** não funcionam. 
        >  - Ao usar uma variável de certificado do dispositivo, coloque a variável entre chaves **{}**.
        >  - `{{FullyQualifiedDomainName}}` funciona somente para dispositivos Windows e unidos ao domínio. 
        >  -  Ao usar propriedades do dispositivo, como IMEI, número de série e nome de domínio totalmente qualificado no assunto ou SAN para um certificado de dispositivo, esteja ciente de que essas propriedades podem ser falsificadas por uma pessoa com acesso ao dispositivo.
        >  - O perfil não será instalado no dispositivo se não houver suporte para as variáveis de dispositivo especificadas. Por exemplo, se {{IMEI}} for usado no nome alternativo da entidade do perfil SCEP atribuído a um dispositivo que não tem um número IMEI, ocorrerá falha na instalação do perfil.  

   - **Período de validade do certificado**: Se você executou o comando `certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE` na AC emissora, que permite um período de validade personalizado, pode inserir a quantidade de tempo restante antes que o certificado expire.<br>Você pode inserir um valor inferior ao período de validade no modelo de certificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você poderá inserir um valor de um ano, mas não de cinco anos. O valor também tem que ser inferior ao período de validade restante do certificado da AC emissora. 
   - **Provedor de armazenamento de chaves (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10): Insira onde a chave para o certificado será armazenada. Escolha um destes valores:
     - **Registrar no KSP do TPM (Trusted Platform Module) se existir; caso contrário, no KSP de Software**
     - **Registrar no KSP do TPM (Trusted Platform Module); caso contrário, falha**
     - **Registrar no Passport; caso contrário, falha (Windows 10 e posterior)**
     - **Registrar no Software KSP**

   - **Uso de chave**: Insira as opções de uso de chave para o certificado. Suas opções:
     - **Codificação de chave**: Permite a troca de chaves apenas se ela estiver criptografada
     - **Assinatura digital**: Permite a troca de chaves apenas quando uma assinatura digital ajuda a proteger a chave
   - **Tamanho da chave (bits)**: Selecione o número de bits contidos na chave
   - **Algoritmo de hash** (Android, Windows Phone 8.1, Windows 8.1, Windows 10): Selecione um dos tipos de algoritmo de hash disponíveis para uso com esse certificado. Selecione o nível mais alto de segurança que dá suporte aos dispositivos de conexão.
   - **Certificado Raiz**: Escolha um perfil de Certificado de Autoridade de Certificação raiz configurado anteriormente e atribuído ao usuário e/ou dispositivo. Esse certificado de Autoridade de Certificação deve ser o certificado raiz da Autoridade de Certificação que emite o certificado que você está configurando neste perfil de certificado. Certifique-se de atribuir esse perfil de certificado raiz confiável ao mesmo grupo atribuído no perfil de certificado SCEP.
   - **Uso estendido de chave**: **Adicionar** valores para a finalidade desejada do certificado. Na maioria dos casos, o certificado exige a **Autenticação de cliente** para que o usuário ou dispositivo possa autenticar-se em um servidor. No entanto, você pode adicionar outros usos da chave conforme necessário.
   - **Configurações de Registro**
     - **Limite de renovação (%)**: Insira o percentual do tempo de vida restante do certificado antes da renovação das solicitações de dispositivo do certificado.
     - **URLs de servidor SCEP**: Insira uma ou mais URLs para os servidores NDES que emitem certificados por meio do protocolo SCEP. Por exemplo, insira algo como `https://ndes.contoso.com/certsrv/mscep/mscep.dll`.
     - Selecione **OK** e **Criar** seu perfil.

O perfil é criado e aparece no painel da lista de perfis.

## <a name="assign-the-certificate-profile"></a>Atribuir o perfil de certificado

Antes de atribuir perfis de certificado a grupos, considere o seguinte:

- Quando você atribui perfis de certificado a grupos, o arquivo de certificado do perfil do Certificado de Autoridade de Certificação Confiável é instalado no dispositivo. O dispositivo usa o perfil de certificado SCEP para criar uma solicitação de certificado pelo dispositivo.
- Os perfis de certificado são instalados somente em dispositivos que executam a plataforma que você usa ao criar o perfil.
- Você pode atribuir perfis de certificado para coleções de usuários ou coleções de dispositivos.
- Para publicar um certificado em um dispositivo rapidamente depois que o dispositivo for registrado, atribua o perfil de certificado a um grupo de usuários em vez de um grupo de dispositivos. Se você atribuir um grupo de dispositivos, um registro de dispositivo completo será necessário para que o dispositivo receba políticas.
- Embora você atribuir cada perfil separadamente, também precisará atribuir a AC Raiz Confiável e o perfil SCEP ou PKCS. Caso contrário, a política de certificação SCEP ou PKCS falhará.

    > [!NOTE]
    > Para iOS, espere ver várias cópias do certificado no perfil de gerenciamento se você implantar vários perfis de recursos que usem o mesmo perfil de certificado.

Para obter mais informações sobre como atribuir perfis, confira [Atribuir perfis de dispositivo](device-profile-assign.md).

## <a name="intune-connector-setup-verification-and-troubleshooting"></a>Verificação de instalação e solução de problemas do Conector do Intune

Para solucionar problemas e verificar a instalação do Conector do Intune, confira [Amostras de script da Autoridade de Certificação](https://aka.ms/intuneconnectorverificationscript)

## <a name="intune-connector-events-and-diagnostic-codes"></a>Eventos e códigos de diagnósticos do Intune Connector

Da versão 6.1806.x.x em diante, o Serviço do Conector do Intune registra em log os eventos no **Visualizador de Eventos** (**Logs de Aplicativos e Serviços** > **Conector do Microsoft Intune**). Use esses eventos para ajudar a solucionar possíveis problemas na configuração do Intune Connector. Esses eventos registram em log êxitos e falhas de uma operação, e também contêm códigos de diagnósticos com mensagens para ajudar o administrador de TI a solucionar problemas.

### <a name="event-ids-and-descriptions"></a>IDs e descrições de eventos

> [!NOTE]
> Para obter detalhes sobre os Códigos de Diagnóstico Relacionados para cada evento, use a tabela **Códigos de diagnósticos** (neste artigo).

| ID do evento      | Nome do Evento    | Descrição do Evento | Códigos de Diagnósticos Relacionados |
| ------------- | ------------- | -------------     | -------------            |
| 10010 | StartedConnectorService  | Serviço do conector iniciado | 0x00000000, 0x0FFFFFFF |
| 10020 | StoppedConnectorService  | Serviço do conector parado | 0x00000000, 0x0FFFFFFF |
| 10100 | CertificateRenewal_Success  | Certificado de registro do conector renovado com êxito | 0x00000000, 0x0FFFFFFF |
| 10102 | CertificateRenewal_Failure  | Falha na renovação do certificado de registro do conector. Reinstale o conector. | 0x00000000, 0x00000405, 0x0FFFFFFF |
| 10302 | RetrieveCertificate_Error  | Falha ao recuperar o certificado de registro do conector do Registro. Examine os detalhes do evento para a impressão digital do certificado relacionada a esse evento. | 0x00000000, 0x00000404, 0x0FFFFFFF |
| 10301 | RetrieveCertificate_Warning  | Verifique as informações de diagnóstico nos detalhes do evento. | 0x00000000, 0x00000403, 0x0FFFFFFF |
| 20100 | PkcsCertIssue_Success  | Certificado PKCS emitido com êxito. Examine os detalhes do evento para obter a ID do dispositivo, a ID de usuário, o nome da Autoridade de Certificação, o nome do modelo de certificado e a impressão digital do certificado relacionados a esse evento. | 0x00000000, 0x0FFFFFFF |
| 20102 | PkcsCertIssue_Failure  | Falha ao emitir um certificado PKCS. Examine os detalhes do evento para obter a ID do dispositivo, a ID de usuário, o nome da Autoridade de Certificação, o nome do modelo de certificado e a impressão digital do certificado relacionados a esse evento. | 0x00000000, 0x00000400, 0x00000401, 0x0FFFFFFF |
| 20200 | RevokeCert_Success  | Certificado revogado com êxito. Examine os detalhes do evento para obter a ID do dispositivo, a ID de usuário, o nome da Autoridade de Certificação e o número de série do certificado relacionado a esse evento. | 0x00000000, 0x0FFFFFFF |
| 20202 | RevokeCert_Failure | Falha ao revogar o certificado. Examine os detalhes do evento para obter a ID do dispositivo, a ID de usuário, o nome da Autoridade de Certificação e o número de série do certificado relacionado a esse evento. Para obter mais informações, consulte os Logs de SVC do NDES.   | 0x00000000, 0x00000402, 0x0FFFFFFF |
| 20300 | Upload_Success | Dados de revogação ou solicitação do certificado carregados com sucesso. Examine os detalhes do evento para obter os detalhes do upload. | 0x00000000, 0x0FFFFFFF |
| 20302 | Upload_Failure | Falha ao carregar os dados de revogação ou solicitação do certificado. Examine os detalhes do evento > Estado de Upload para determinar o ponto de falha.| 0x00000000, 0x0FFFFFFF |
| 20400 | Download_Success | Solicitação para assinar um certificado, baixar um certificado de cliente ou revogar um certificado baixada com sucesso. Examine os detalhes do evento para obter os detalhes do download.  | 0x00000000, 0x0FFFFFFF |
| 20402 | Download_Failure | Falha ao baixar a solicitação para assinar um certificado, baixar certificado de cliente ou revogar um certificado. Examine os detalhes do evento para obter os detalhes do download. | 0x00000000, 0x0FFFFFFF |
| 20500 | CRPVerifyMetric_Success  | O Ponto de Registro de Certificado verificou com êxito um desafio do cliente | 0x00000000, 0x0FFFFFFF |
| 20501 | CRPVerifyMetric_Warning  | O Ponto de Registro de Certificado foi concluído, mas rejeitou a solicitação. Veja o código e a mensagem de diagnóstico para obter mais detalhes. | 0x00000000, 0x00000411, 0x0FFFFFFF |
| 20502 | CRPVerifyMetric_Failure  | O Ponto de Registro de Certificado falhou ao verificar um desafio de cliente. Veja o código e a mensagem de diagnóstico para obter mais detalhes. Veja os detalhes da mensagem de evento para a ID do Dispositivo correspondente ao desafio. | 0x00000000, 0x00000408, 0x00000409, 0x00000410, 0x0FFFFFFF |
| 20600 | CRPNotifyMetric_Success  | O Ponto de Registro de Certificado concluiu com êxito o processo de notificação e enviou o certificado ao dispositivo cliente. | 0x00000000, 0x0FFFFFFF |
| 20602 | CRPNotifyMetric_Failure  | O Ponto de Registro de Certificado falhou ao concluir o processo de notificação. Veja os detalhes da mensagem de evento para obter informações sobre a solicitação. Verifique a conexão entre o servidor NDES e a autoridade de certificação. | 0x00000000, 0x0FFFFFFF |

### <a name="diagnostic-codes"></a>Códigos de diagnóstico

| Código de Diagnóstico | Nome do Diagnóstico | Mensagem de Diagnóstico |
| -------------   | -------------   | -------------      |
| 0x00000000 | Êxito  | Êxito |
| 0x00000400 | PKCS_Issue_CA_Unavailable  | A autoridade de certificação não é válida ou está inacessível. Verifique se que a autoridade de certificação está disponível e se o servidor pode se comunicar com ela. |
| 0x00000401 | Symantec_ClientAuthCertNotFound  | O Certificado de Autenticação de Cliente da Symantec não foi encontrado no repositório de certificados local. Veja o artigo [Instalar o certificado autorização de registro da Symantec](https://docs.microsoft.com/intune/certificates-symantec-configure#install-the-symantec-registration-authorization-certificate) para obter mais informações.  |
| 0x00000402 | RevokeCert_AccessDenied  | A conta especificada não tem permissões para revogar um certificado da autoridade de certificação. Veja o campo Nome da Autoridade de Certificação nos detalhes da mensagem do evento para determinar a autoridade de certificação emissora.  |
| 0x00000403 | CertThumbprint_NotFound  | Não foi possível localizar um certificado correspondente à sua entrada. Registre o conector de certificado e tente novamente. |
| 0x00000404 | Certificate_NotFound  | Não foi possível localizar um certificado correspondente à entrada fornecida. Registre o conector de certificado outra vez e tente novamente. |
| 0x00000405 | Certificate_Expired  | Um certificado expirou. Registre o conector de certificado outra vez para renovar o certificado e tente novamente. |
| 0x00000408 | CRPSCEPCert_NotFound  | Não foi possível localizar o certificado de criptografia de CRP. Verifique se que NDES e o Intune Connector estão configurados corretamente. |
| 0x00000409 | CRPSCEPSigningCert_NotFound  | Não foi possível recuperar o certificado de assinatura. Verifique se o Serviço do Intune Connector está configurado corretamente e se o Serviço do Intune Connector está em execução. Verifique também se os eventos de download de certificado foram bem-sucedidos. |
| 0x00000410 | CRPSCEPDeserialize_Failed  | Falha ao desserializar a solicitação de desafio do protocolo SCEP. Verifique se o NDES e o Intune Connector estão configurados corretamente. |
| 0x00000411 | CRPSCEPChallenge_Expired  | Solicitação negada devido a desafio de certificado expirado. O dispositivo cliente pode tentar novamente depois de obter um novo desafio do servidor de gerenciamento. |
| 0x0FFFFFFFF | Unknown_Error  | Não foi possível concluir sua solicitação porque ocorreu um erro no lado do servidor. Tente novamente. |

## <a name="next-steps"></a>Próximas etapas

- [Usar certificados PKCS](certficates-pfx-configure.md) ou [emitir certificados PKCS de um serviço Web do gerenciador do Symantec PKI](certificates-symantec-configure.md)
- [Adicionar uma AC de terceiros para usar o SCEP com o Intune](certificate-authority-add-scep-overview.md)
- Para obter assistência adicional, use a guia [Solucionar problemas na implantação do perfil de certificado SCEP no Microsoft Intune](https://support.microsoft.com/help/4457481/troubleshooting-scep-certificate-profile-deployment-in-intune).
