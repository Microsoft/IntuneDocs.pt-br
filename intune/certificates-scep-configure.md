---
title: Usar certificados SCEP com o Microsoft Intune – Azure | Microsoft Docs
description: Para usar certificados SCEP no Microsoft Intune, configure seu domínio do AD local, crie uma autoridade de certificação, configure o servidor NDES e instale o Conector de Certificado do Intune. Em seguida, crie um perfil de certificado SCEP e atribua esse perfil a grupos.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dabf8d67b4d0bd7252f306d6b21949cf501eca8d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="configure-and-use-scep-certificates-with-intune"></a>Configurar e usar certificados SCEP com o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra como configurar sua infraestrutura e depois criar e atribuir perfis de certificado de protocolo SCEP (Simple Certificate Enrollment Protocol) com o Intune.

## <a name="configure-on-premises-infrastructure"></a>Configurar a infraestrutura local

- **Domínio do Active Directory**: todos os servidores listados nesta seção (exceto pelo Servidor Proxy de Aplicativo Web) devem ser ingressados em seu domínio do Active Directory.

- **AC (Autoridade de Certificação)**: uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. Para obter detalhes, confira [Instalar a Autoridade de Certificação](http://technet.microsoft.com/library/jj125375.aspx).
    Se a sua AC executar o Windows Server 2008 R2, você deve [instalar o hotfix de KB2483564](http://support.microsoft.com/kb/2483564/).

- **Servidor NDES**: em um servidor que executa o Windows Server 2012 R2 ou posterior, você deve configurar o NDES (Serviço de Registro de Dispositivo de Rede). O Intune não dá suporte ao uso do NDES quando ele é executado em um servidor que também executa a AC Corporativa. Consulte [Network Device Enrollment Service Guidance](http://technet.microsoft.com/library/hh831498.aspx) (Diretrizes de Serviço de Registro de Dispositivo de Rede) para obter instruções sobre como configurar o Windows Server 2012 R2 para hospedar o Serviço de Registro de Dispositivo de Rede.
O servidor NDES deve ter ingressado no domínio que hospeda a AC e não estar no mesmo servidor que a AC. Há mais informações sobre como implantar o servidor NDES em uma floresta separada, rede isolada ou domínio interno em [Usando um Módulo de Política com o Serviço de Registro de Dispositivo de Rede](https://technet.microsoft.com/library/dn473016.aspx).

- **Microsoft Intune Certificate Connector**: use o Portal do Azure para baixar o instalador do **Conector de Certificado** (**ndesconnectorssetup.exe**). Então, você pode executar **ndesconnectorssetup.exe** no servidor que hospeda a função do NDES (Serviço de Registro de Dispositivo de Rede) em que você deseja instalar o Certificate Connector. 
- **Servidor Proxy de Aplicativos Web** (opcional): use um servidor que executa o Windows Server 2012 R2 ou posterior como servidor WAP (Proxy de Aplicativo Web). Essa configuração:
  -  Permite que os dispositivos recebam certificados usando uma conexão com a Internet.
  -  Trata-se de uma recomendação de segurança quando os dispositivos se conectam pela Internet para receber e renovar certificados.

> [!NOTE]
> - O servidor que hospeda o WAP [deve instalar uma atualização](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) que habilita o suporte para as URLs longas que são usadas pelo Serviço de Registro de Dispositivo de Rede. Essa atualização está incluída no [pacote cumulativo de atualizações de dezembro de 2014](http://support.microsoft.com/kb/3013769)ou individualmente no [KB3011135](http://support.microsoft.com/kb/3011135).
> - O servidor WAP deve ter um certificado SSL que corresponda ao nome que está sendo publicado para clientes externos e confiar no certificado SSL usado no servidor NDES. Esses certificados habilitam o servidor WAP a encerrar a conexão SSL de clientes e a criar uma nova conexão SSL com o servidor NDES.
> 
>   Para obter informações sobre certificados para WAP, consulte os [Certificados do plano](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates).
> 
>   Para obter informações gerais sobre servidores WAP, consulte [Trabalhando com o Proxy de Aplicativo Web](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)).

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
|**Certificado de AC raiz confiável**|Exporte esse certificado como um arquivo **.cer** da Autoridade de Certificação raiz ou de qualquer dispositivo que confie na AC raiz e atribua-o aos dispositivos usando o perfil de certificado de Autoridade de Certificação Confiável.<br /><br />Você usa um único certificado de AC raiz confiável por plataforma de sistema operacional e o associa a cada perfil de certificado de raiz confiável que criar.<br /><br />Você pode usar certificados de AC raiz confiável adicionais quando necessário. Por exemplo, você pode fazer isso para fornecer uma relação de confiança a uma AC que conecta os certificados de autenticação do servidor aos pontos de acesso Wi-Fi.|

### <a name="accounts"></a>Contas

|Nome|Detalhes|
|--------|-----------|
|**Conta de serviço de NDES**|Insira uma conta de usuário de domínio para usar como conta de Serviço NDES.|

## <a name="configure-your-infrastructure"></a>Configure sua infraestrutura
Para poder configurar perfis de certificado, conclua as tarefas a seguir. Essas tarefas exigem conhecimento do Windows Server 2012 R2 e do ADCS (Serviços de Certificados do Active Directory):

**Etapa 1**: Criar uma conta de serviço de NDES

**Etapa 2**: Configurar modelos de certificado na autoridade de certificação

**Etapa 3**: Configurar pré-requisitos no servidor NDES

**Etapa 4**: Configurar o NDES para uso com o Intune

**Etapa 5**: Habilitar, instalar e configurar o Conector de Certificado do Intune

#### <a name="step-1---create-an-ndes-service-account"></a>Etapa 1 - Criar uma conta de serviço de NDES

Crie uma conta de usuário de domínio para usar como conta de serviço de NDES. Insira essa conta ao configurar modelos na AC emissora antes de instalar e configurar o NDES. Verifique se o usuário tem os direitos padrão, que são os direitos **Logon Localmente**, **Logon como Serviço** e **Logon como um trabalho em lotes**. Algumas organizações têm políticas de proteção que desabilitam esses direitos de proteção.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Etapa 2 - Configurar modelos de certificado na autoridade de certificação
Nesta tarefa, você vai:

- Configurar um modelo de certificado para o NDES
- Publicar o modelo de certificado para o NDES

##### <a name="configure-the-certification-authority"></a>Configurar a autoridade de certificação

1. Entre como administrador corporativo.

2. Na AC emissora, use o snap-in de Modelos de Certificado para criar um novo modelo personalizado. Ou copie um modelo existente e, em seguida, atualize esse modelo existente (como o Modelo de Usuário) para uso com o NDES.

   >[!NOTE]
   > O modelo de certificado NDES deve ser baseado em um Modelo de Certificado v2 (com a compatibilidade para Windows 2003).

   O modelo deve ter as seguintes configurações:

   - Insira um **Nome de exibição do modelo** amigável para o modelo.

   - Em **Nome da Entidade**, selecione **Fornecimento na solicitação**. (A segurança é imposta pelo módulo de política do Intune para o NDES).

   - Em **Extensões**, conforme que a **Descrição das Políticas de Aplicativo** inclui **Autenticação de Cliente**.

     > [!IMPORTANT]
     > Para modelos de certificado do iOS e macOS, na guia **Extensões**, edite **Uso da Chave** e confirme que a opção **A assinatura é uma prova de origem** não está selecionada.

   - Em **Segurança**, adicione a conta de serviço NDES e dê a ela permissões para **Registrar** no modelo. Os administradores do Intune que criam perfis SCEP exigem direitos de **leitura** para poderem navegar no modelo durante a criação de perfis SCEP.

     > [!NOTE]
     > Para revogar certificados, a conta de serviço do NDES precisa de direitos de *Emitir e Gerenciar Certificados* para cada modelo de certificado usado por um perfil de certificado.

3. Examine o **Período de validade** na guia **Geral** do modelo. Por padrão, o Intune usa o valor configurado no modelo. No entanto, você tem a opção de configurar a AC para permitir que o solicitante insira um valor diferente, que você pode definir de dentro do Console do Administrador do Intune. Se você quiser usar sempre o valor no modelo, ignore o restante desta etapa.

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
Nesta tarefa, você vai:

- Adicionar o NDES a um Windows Server e configurar o IIS para dar suporte ao NDES
- Adicionar a conta de serviço de NDES ao grupo IIS_IUSR
- Definir o SPN da conta de serviço de NDES

1. No servidor que hospeda o NDES, entre como **Administrador Corporativo** e use o [Assistente de Adição de Funções e Recursos](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) para instalar o NDES:

   1. No assistente, selecione **Serviços de Certificados do Active Directory** para acessar os Serviços de Função do AD CS. Selecione o **Serviço de Registro de Dispositivo de Rede**, desmarque **Autoridade de Certificação**e conclua o assistente.

      > [!TIP]
      > Em **Progresso da instalação**, não marque **Fechar**. Em vez disso, selecione o link **Configurar Serviços de Certificados do Active Directory no servidor de destino**. É aberto o assistente de **Configuração do AD CS**, que você usa para a próxima tarefa. Após Configuração AD CS abrir, você pode fechar o Assistente de Adição de Funções e Recursos.

   2. Quando o NDES é adicionado ao servidor, o assistente também instala o IIS. Verifique se o IIS tem as seguintes configurações:

   3. **Servidor Web** > **Segurança** > **Filtragem de Solicitações**

   4. **Servidor Web** > **Desenvolvimento de Aplicativos** > **ASP.NET 3.5**. Instalar o ASP.NET 3.5 instala o .NET Framework 3.5. Ao instalar o .NET Framework 3.5, instale o recurso **.NET Framework 3.5** principal e o **Ativação HTTP**.

   5. **Servidor Web** > **Desenvolvimento de Aplicativos** > **ASP.NET 4.5**. Instalar o ASP.NET 4.5 instala o .NET Framework 4.5. Ao instalar o .NET Framework 4.5, instale o recurso principal do **.NET Framework 4.5**, o **ASP.NET 4.5** e o recurso **Serviços WCF** > **Ativação HTTP**.

   6. **Ferramentas de Gerenciamento** > **Compatibilidade com Gerenciamento do IIS 6** > **Compatibilidade com Metabase do IIS 6**

   7. **Ferramentas de Gerenciamento** > **Compatibilidade com Gerenciamento do IIS 6** > **Compatibilidade com WMI do IIS 6**

   8. No servidor, adicione a conta de serviço de NDES como membro do grupo **IIS_IUSR**.

2. Em um prompt de comandos com privilégios elevados, execute o seguinte comando para definir o SPN da conta de serviço de NDES:

    `setspn -s http/<DNS name of NDES Server> <Domain name>\<NDES Service account name>`

    Por exemplo, se seu servidor de NDES se chamar **Server01**, seu domínio for **Contoso.com**e a conta de serviço for **NDESService**, use:

    `setspn –s http/Server01.contoso.com contoso\NDESService`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Etapa 4 - Configurar o NDES para uso com o Intune
Nesta tarefa, você vai:

- Configurar o NDES para uso com a AC emissora
- Associar o certificado de autenticação do servidor (SSL) no IIS
- Configurar a filtragem de solicitações no IIS

1. No servidor NDES, abra o Assistente de Configuração do AD CS e faça as seguintes atualizações:

    > [!TIP]
    > Se você clicou no link na tarefa anterior, o assistente já está aberto. Caso contrário, abra o Gerenciador do Servidor para acessar a configuração pós-implantação dos Serviços de Certificados do Active Directory.

   - Na página **Serviços de Função**, selecione **Serviço de Registro de Dispositivo de Rede**
   - Em **Conta de Serviço para NDES**, insira Conta de Serviço do NDES
   - EM **AC para NDES**, clique em **Selecionar** e selecione a AC emissora em que você configurou o modelo de certificado
   - Em **Criptografia para NDES**, defina o comprimento da chave para atender aos requisitos da sua empresa.
   - Em **Confirmação**, selecione **Configurar** para concluir o assistente.

2. Após concluir o assistente, atualize a seguinte chave do Registro no Servidor de NDES:

    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`

    Para atualizar essa chave, identifique a **Finalidade** do modelo de certificado (encontrada na guia **Tratamento de Solicitação**). Em seguida, atualize a entrada do registro correspondente, substituindo os dados existentes pelo nome do modelo de certificado (não o nome de exibição do modelo) que você especificou na Tarefa 1. A tabela a seguir mapeia a finalidade do modelo de certificado de acordo com os valores do Registro:

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

5. Reinicie o servidor. Executar **iisreset** no servidor não é suficiente para finalizar essas alterações.
6. Navegue até `http://*FQDN*/certsrv/mscep/mscep.dll`. Você deve ver uma página NDES semelhante a esta:

    ![Testar NDES](./media/SCEP_NDES_URL.png)

    Se você receber a mensagem **503 Serviço indisponível**, verifique o visualizador de eventos. É provável que o pool de aplicativos seja interrompido devido a um direito ausente para o usuário NDES. Esses direitos são descritos na Tarefa 1.

##### <a name="install-and-bind-certificates-on-the-ndes-server"></a>Para instalar e associar os certificados no Servidor de NDES

1. No seu Servidor de NDES, solicite e instale um certificado de **autenticação de servidor** por meio da sua AC interna ou pública. Em seguida, associe esse certificado SSL no IIS.

    > [!TIP]
    > Depois de associar o certificado SSL no IIS, instale um certificado de autenticação de cliente. Esse certificado pode ser emitido por qualquer AC em que o Servidor de NDES confie. Embora não seja uma prática recomendada, é possível usar o mesmo certificado para autenticação de servidor e de cliente, desde que o certificado tenha ambos os EKUs (Usos Avançados de Chave). Examine as etapas a seguir para obter informações sobre esses certificados de autenticação.

   1. Depois de obter o certificado de autenticação de servidor, abra **Gerenciador do IIS** e selecione o **Site Padrão**. No painel **Ações**, selecione **Associações**.

   2. Selecione **Adicionar**, defina **Tipo** como **https** e, em seguida, confirme que a porta é **443**. Somente a porta 443 é compatível com o Intune autônomo.

   3. Para **Certificado SSL**, insira o certificado de autenticação de servidor.

      > [!NOTE]
      > Se o servidor NDES usar nomes interno e externo para um único endereço de rede, o certificado de autenticação de servidor deverá ter:
      > - Um **Nome da Entidade** com um nome do servidor público externo
      > - Um **Nome Alternativo da Entidade** que inclua o nome do servidor interno

2. No seu Servidor de NDES, solicite e instale um certificado de **autenticação de cliente** da sua AC interna ou uma AC pública. Pode ser o mesmo certificado que o certificado de autenticação de servidor se o certificado tiver os dois recursos.

    O certificado de autenticação de cliente deve ter as seguintes propriedades:

    - **Uso Avançado de Chave**: esse valor deve incluir a **Autenticação de Cliente**

    - **Nome da entidade**: esse valor deve ser igual ao nome DNS do servidor em que você está instalando o certificado (o Servidor de NDES)

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
Nesta tarefa, você vai:

- Habilitar o suporte para NDES no Intune.
- Baixe, instale e configure o Certificate Connector no servidor que hospeda a função do NDES (Serviço de Registro de Dispositivo de Rede) em seu ambiente. Para aumentar a escala da implementação do NDES em sua organização, você pode instalar vários servidores de NDES com um Microsoft Intune Certificate Connector em cada servidor do NDES.

##### <a name="download-install-and-configure-the-certificate-connector"></a>Baixar, instalar e configurar o conector de certificado
![ConnectorDownload](./media/certificates-download-connector.png)

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** e, em seguida, selecione **Autoridade de Certificação**.
4. Selecione **Adicionar** e **Baixar o arquivo do conector**. Salve o download em um local em que você possa acessá-lo pelo servidor no qual você vai instalá-lo.
5. Após a conclusão do download, execute o instalador baixado (**ndesconnectorssetup.exe**) no servidor que hospeda a função do NDES (Serviço de Registro de Dispositivo de Rede). O instalador também instala o módulo de política para NDES e o Serviço Web de CRP. (O Serviço Web de CRP, CertificateRegistrationSvc, é executado como um aplicativo no IIS).

    > [!NOTE]
    > Quando você instala o NDES para o Intune autônomo, o serviço de CRP é instalado automaticamente com o Conector de Certificado. Quando você usa o Intune com o Configuration Manager, instala o Ponto de Registro de Certificado como uma função de sistema de site separada.

6. Quando for solicitado o certificado de cliente do Certificate Connector, escolha **Selecionar** e selecione o certificado de **autenticação de cliente** instalado no Servidor NDES na Tarefa 3.

    Depois de selecionar o certificado de autenticação de cliente, você retornará para a superfície do **Certificado de Cliente para o Conector de Certificado do Microsoft Intune** . Embora o certificado selecionado não seja exibido, selecione **Avançar** para exibir as propriedades do certificado. Selecione **Avançar** e, em seguida, **Instalar**.

7. Após a conclusão do assistente, mas antes de fechá-lo, escolha **Iniciar a Interface do Usuário do Conector de Certificado**.

    > [!TIP]
    > Se fechar o assistente antes de iniciar a interface do usuário do Conector de Certificado, você poderá reabri-la executando o seguinte comando:
    >
    > <caminho_instalação>\NDESConnectorUI\NDESConnectorUI.exe

8. Na interface do usuário do **Conector de Certificado** :

    Selecione em **Entrar** e insira suas credenciais de administrador de serviços do Intune ou as credenciais de um administrador de locatários com permissão de administração global.

    > [!IMPORTANT]
    > A conta de usuário deve ter uma licença válida do Intune. Se a conta de usuário não tiver uma licença válida do Intune, o NDESConnectorUI.exe falhará.

    Se a sua organização usar um servidor proxy e o proxy for necessário para o servidor NDES acessar a Internet, selecione **Usar servidor proxy** e insira o nome do servidor proxy, a porta e as credenciais da conta para conectar-se.

    Selecione a guia **Avançado** e insira credenciais para uma conta que tenha a permissão **Emitir e Gerenciar Certificados** na sua Autoridade de Certificação emissora. **Aplique** suas alterações.

    Agora você pode fechar a interface do usuário do Conector de Certificado.

9. Abra um prompt de comando, digite **services.msc** e, em seguida, **Enter**. Clique com o botão direito do mouse em **Serviço do Conector do Intune** e escolha **Reiniciar**.

Para validar se o serviço está em execução, abra um navegador e insira a URL a seguir. Ele deverá retornar um erro **403**:

`http://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`

## <a name="create-a-scep-certificate-profile"></a>Criar um perfil de certificado SCEP

1. No Portal do Azure, abra o Microsoft Intune.
2. Selecione **Configuração do dispositivo**, **Perfis** e **Criar perfil**.
3. Insira um **Nome** e uma **Descrição** para o perfil de certificado SCEP.
4. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado SCEP. No momento, é possível selecionar uma das seguintes plataformas para as configurações de restrição de dispositivo:
   - **Android**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 e posterior**
   - **Windows 10 e posterior**
5. Na lista suspensa de tipos de **Perfil**, selecione **Certificado SCEP**.
6. No painel **Certificado SCEP**, defina as seguintes configurações:

   - **Período de validade do certificado**: se você tiver executado o comando `certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE` na AC emissora, o que permite um período de validade personalizado, será possível inserir o tempo restante antes da expiração do certificado.<br>Você pode inserir um valor inferior ao período de validade no modelo de certificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você poderá inserir um valor de um ano, mas não de cinco anos. O valor também tem que ser inferior ao período de validade restante do certificado da AC emissora. 
   - **KSP (provedor de armazenamento de chaves)** (Windows Phone 8.1, Windows 8.1 e Windows 10): insira o local em que a chave do certificado é armazenada. Escolha um destes valores:
     - **Registrar no KSP do TPM (Trusted Platform Module) se existir; caso contrário, no KSP de Software**
     - **Registrar no KSP do TPM (Trusted Platform Module); caso contrário, falha**
     - **Registrar no Passport; caso contrário, falha (Windows 10 e posterior)**
     - **Registrar no Software KSP**

   - **Formato de nome da entidade**: na lista, selecione como o Intune cria automaticamente o nome da entidade na solicitação de certificado. Se o certificado for para um usuário, você também pode incluir o endereço de email do usuário no nome da entidade. Escolha:
     - **Não configurado**
     - **Nome comum**
     - **Nome comum incluindo email**
     - **Nome comum como email**
     - **IMEI (Identificação Internacional de Equipamento Móvel)**
     - **Número de série**
     - **Personalizado** – ao selecionar essa opção, outro campo suspenso será exibido. Use esse campo para inserir um formato de nome da entidade personalizado. O formato personalizado é compatível com duas variáveis: **CN (Nome Comum)** e **E (Email)**. **CN (Nome Comum)** pode ser definido para qualquer uma das seguintes variáveis:
       - **CN = {{UserName}}**: o nome de princípio do usuário, como janedoe@contoso.com
       - **CN = {{AAD_Device_ID}}**: uma ID atribuída ao registrar um dispositivo no Azure AD (Active Directory). Essa ID normalmente é usada para autenticar com o Azure AD.
       - **CN = {{SERIALNUMBER}}**: o SN (número de série) exclusivo normalmente usado pelo fabricante para identificar um dispositivo
       - **CN = {{IMEINumber}}**: o número exclusivo do IMEI (Identidade Internacional de Equipamento Móvel) usado para identificar um celular
       - **CN = {{OnPrem_Distinguished_Name}}**: uma sequência de nomes distintos relativos separados por vírgula, como `CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com`

       > [!TIP]
       > Para usar a variável `{{OnPrem_Distinguished_Name}}`, sincronize o atributo de usuário `onpremisesdistingishedname` usando o [Azure AD (Active Directory) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) com seu Azure AD.

       Usando uma combinação de uma ou diversas dessas variáveis e cadeias de caracteres estáticas, você pode criar um formato de nome de entidade personalizado, como: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**. <br/> Neste exemplo, você criou um formato de nome de entidade que, além das variáveis CN e E, usa cadeias de caracteres para os valores Unidade Organizacional, Organização, Local, Estado e País. [Função CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) descreve essa função e suas cadeias de caracteres compatíveis.




- **Nome alternativo da entidade**: insira como o Intune criará automaticamente os valores para o SAN (nome alternativo da entidade) na solicitação de certificado. Por exemplo, se você selecionar um tipo de certificado de usuário, poderá incluir o nome UPN no nome alternativo da entidade. Se o certificado do cliente for usado para autenticar em um Servidor de Políticas de Rede, será necessário definir o nome alternativo da entidade como o UPN.
- **Uso de chave**: insira as opções de uso de chave para o certificado. Suas opções:
  - **Criptografia de chave:** permita a troca de chaves apenas quando a chave for criptografada
  - **Assinatura digital**: permita a troca de chaves apenas quando uma assinatura digital ajudar a proteger a chave
- **Tamanho da chave (bits)**: selecione o número de bits contidos na chave
- **Algoritmo de hash:** (Android, Windows Phone 8.1, Windows 8.1 e Windows 10): selecione um dos tipos de algoritmo de hash disponíveis para ser usado com esse certificado. Selecione o nível mais alto de segurança que dá suporte aos dispositivos de conexão.
- **Certificado Raiz**: escolha um perfil de Certificado de Autoridade de Certificação raiz configurado anteriormente e atribuído ao usuário ou dispositivo. Esse certificado de Autoridade de Certificação deve ser o certificado raiz da Autoridade de Certificação que emite o certificado que você está configurando neste perfil de certificado.
- **Uso estendido de chave**: escolha **Adicionar** valores para a finalidade desejada do certificado. Na maioria dos casos, o certificado exige a **Autenticação de cliente** para que o usuário ou dispositivo possa autenticar-se em um servidor. No entanto, você pode adicionar outros usos da chave conforme necessário.
- **Configurações de Registro**
  - **Limite de renovação (%)**: insira o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
  - **URLs de servidor SCEP**: insira uma ou mais URLs para os servidores NDES que emitem certificados por meio do protocolo SCEP.
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
    
Para saber mais sobre como atribuir perfis, confira [Como atribuir perfis de dispositivo](device-profile-assign.md).
