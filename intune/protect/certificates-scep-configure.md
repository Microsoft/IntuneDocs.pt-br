---
title: Configurar a infraestrutura para dar suporte a perfis de Certificado SCEP com o Microsoft Intune – Azure | Microsoft Docs
description: Para usar o SCEP no Microsoft Intune, configure o domínio do AD local, crie uma autoridade de certificação, configure o servidor NDES e instale o Intune Certificate Connector.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 24d0a8160d852a5a44f5df688b7e0bc230d56704
ms.sourcegitcommit: c7c6be3833d9a63d43f31d598b555b49b33cf5cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "76966378"
---
# <a name="configure-infrastructure-to-support-scep-with-intune"></a>Configurar a infraestrutura para dar suporte ao SCEP com o Intune

O Intune dá suporte ao uso do protocolo SCEP para [autenticar conexões com seus aplicativos e recursos corporativos](certificates-configure.md). O SCEP usa o Certificado de Autoridade de Certificação (AC) para proteger a troca de mensagens da CSR (Solicitação de Assinatura de Certificado). Quando a infraestrutura dá suporte ao SCEP, você pode usar perfis do *Certificado SCEP* do Intune (um tipo de perfil de dispositivo no Intune) para implantar os certificados em seus dispositivos. O Microsoft Intune Certificate Connector é necessário para usar perfis de certificado SCEP com o Intune ao usar uma Autoridade de Certificação dos Serviços de Certificados do Active Directory. O conector não é necessário ao usar [autoridades de certificação de terceiros](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration). 

As informações deste artigo podem ajudá-lo a configurar sua infraestrutura para dar suporte ao SCEP ao usar os Serviços de Certificados do Active Directory. Depois que a infraestrutura for configurada, você poderá [criar e implantar perfis de Certificado SCEP](certificates-profile-scep.md) com o Intune.

> [!TIP]
> O Intune também dá suporte ao uso de [certificados Public Key Cryptography Standards nº 12](certficates-pfx-configure.md).

## <a name="prerequisites-for-using-scep-for-certificates"></a>Pré-requisitos para uso do SCEP para certificados

Antes de prosseguir, [crie e implante um perfil de *certificado confiável*](certificates-configure.md#export-the-trusted-root-ca-certificate) para dispositivos que usarão perfis de Certificado SCEP. Os perfis de Certificado SCEP referenciam diretamente o perfil de certificado confiável usado para provisionar dispositivos com um Certificado de Autoridade de Certificação raiz confiável.

### <a name="servers-and-server-roles"></a>Servidores e funções de servidor

A infraestrutura local a seguir precisa ser executada em servidores que ingressaram no domínio no Active Directory, com exceção do servidor proxy de aplicativo Web.

- **Autoridade de Certificação** – use uma AC (autoridade de certificação) corporativa dos Serviços de Certificados do Microsoft Active Directory que seja executada em uma Edição Enterprise do Windows Server 2008 R2 com o service pack 1 ou posterior. A versão usada do Windows Server precisa ter o suporte da Microsoft. Não há suporte para ACs autônomas. Para obter mais informações, confira [Instalar a autoridade de certificação](https://technet.microsoft.com/library/jj125375.aspx). Se a AC executar o Windows Server 2008 R2 SP1, você precisará [instalar o hotfix da KB2483564](https://support.microsoft.com/kb/2483564/).

- **Função de servidor NDES** – é necessário configurar uma função de servidor NDES (Serviço de Registro de Dispositivo de Rede) no Windows Server 2012 R2 ou posterior. Em uma seção posterior deste artigo, orientaremos você na [instalação do NDES](#set-up-ndes).

  - O servidor que hospeda o NDES precisa estar ingressado no domínio e na mesma floresta da AC corporativa.
  - Não é possível usar o NDES instalado no servidor que hospeda a AC corporativa.
  - Você instalará o Microsoft Intune Certificate Connector no mesmo servidor que hospeda o NDES.

  Para saber mais sobre o NDES, confira [Diretrizes do Serviço de Registro de Dispositivo de Rede](https://technet.microsoft.com/library/hh831498.aspx) na documentação do Windows Server e [Como usar um módulo de política com o Serviço de Registro de Dispositivo de Rede](https://technet.microsoft.com/library/dn473016.aspx).

- **Microsoft Intune Certificate Connector** – é necessário ter o Microsoft Intune Certificate Connector para usar perfis de Certificado SCEP com o Intune. Este artigo orientará você na [instalação desse conector](#install-the-intune-certificate-connector).

  O conector dá suporte ao modo do padrão FIPS. O FIPS não é necessário, mas quando habilitado, é possível emitir e revogar certificados.
  - O conector precisa ser executado no mesmo servidor da função de servidor NDES, um servidor que execute o Windows Server 2012 R2 ou posterior.
  - O .NET 4.5 Framework é necessário para o conector e é automaticamente incluído no Windows Server 2012 R2.
  - A Configuração da Segurança Aprimorada do Internet Explorer [precisa ser desabilitada no servidor que hospeda o NDES](https://technet.microsoft.com/library/cc775800(v=WS.10).aspx) e o Microsoft Intune Certificate Connector.

A seguinte infraestrutura local é opcional:

Para permitir que os dispositivos na Internet obtenham certificados, você precisa publicar a URL do NDES externamente na rede corporativa. Use o Proxy de Aplicativo do Azure AD, o servidor proxy de aplicativo Web ou outro proxy reverso.

- **Proxy de Aplicativo do Azure AD** (opcional) – use o Proxy de Aplicativo do Azure AD em vez de um servidor WAP (Proxy de aplicativo Web) dedicado para publicar a URL do NDES na Internet. Isso permite que os dispositivos para a intranet e a Internet obtenham certificados. Para obter mais informações, confira [Como fornecer acesso remoto seguro a aplicativos locais](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- **Servidor Proxy de Aplicativo Web** (opcional) – use um servidor que execute o Windows Server 2012 R2 ou posterior como um servidor WAP (Proxy de aplicativo Web) para publicar a URL do NDES na Internet.  Isso permite que os dispositivos para a intranet e a Internet obtenham certificados.

  O servidor que hospeda o WAP [deve instalar uma atualização](https://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) que habilita o suporte para as URLs longas que são usadas pelo Serviço de Registro de Dispositivo de Rede. Essa atualização está incluída no [pacote cumulativo de atualizações de dezembro de 2014](https://support.microsoft.com/kb/3013769)ou individualmente no [KB3011135](https://support.microsoft.com/kb/3011135).

  O servidor WAP precisa ter um certificado SSL que corresponda ao nome que está sendo publicado para clientes externos e confiar no certificado SSL usado no computador que hospeda o serviço do NDES. Esses certificados permitem que o servidor WAP encerre a conexão SSL de clientes e crie outra conexão SSL com o serviço do NDES.

  Para obter mais informações, consulte [Planejar certificados WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates) e [informações gerais sobre servidores WAP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)).

### <a name="accounts"></a>Contas

- **Conta de serviço do NDES** – antes de configurar o NDES, identifique uma conta de usuário do domínio a ser usada como a conta de serviço do NDES. Você especificará essa conta ao configurar modelos na AC emissora antes de configurar o NDES.

  Essa conta precisa ter os seguintes direitos no servidor que hospeda o NDES:

  - **Logon Localmente**
  - **Logon como Serviço**
  - **Logon como um trabalho em lotes**

  Para obter mais informações, confira [Criar uma conta de usuário do domínio para funcionar como a conta de serviço do NDES](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11)#to-create-a-domain-user-account-to-act-as-the-ndes-service-account).

- **Acesso ao computador que hospeda o serviço do NDES** – você precisará de uma conta de usuário do domínio com permissões para instalar e configurar funções de servidor do Windows no servidor em que o NDES é instalado.

- **Acesso à autoridade de certificação** – você precisará de uma conta de usuário do domínio que tenha direitos para gerenciar a autoridade de certificação.

### <a name="network-requirements"></a>Requisitos de rede

Recomendamos a publicação do serviço do NDES por meio de um proxy reverso, como o [Proxy de Aplicativo do Azure AD, o Proxy do Acesso via Web](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/) ou um proxy de terceiros. Se você não usar um proxy reverso, permita o tráfego TCP na porta 443 de todos os hosts e endereços IP na Internet ao serviço do NDES.

Permita todas as portas e todos os protocolos necessários para a comunicação entre o serviço do NDES e qualquer infraestrutura de suporte no ambiente. Por exemplo, o computador que hospeda o serviço do NDES precisa se comunicar com a AC, os servidores DNS, os controladores de domínio e, possivelmente, outros servidores no ambiente, como o Configuration Manager.

### <a name="certificates-and-templates"></a>Certificados e modelos

Os certificados e os modelos a seguir são usados quando o SCEP é usado.

|Objeto    |Detalhes    |
|----------|-----------|
|**Modelo de Certificado SCEP**         |Modelo que você configurará na AC emissora usado para atender às solicitações do SCEP de dispositivos. |
|**Certificado de autenticação de cliente** |Solicitado da AC emissora ou da AC pública.<br /> Você instala esse certificado no computador que hospeda o serviço do NDES e ele é usado pelo Intune Certificate Connector.<br /> Se o certificado tiver o conjunto de usos de chave de *autenticação de cliente* e *servidor* (**usos avançados de chave**) no modelo de AC usado para emitir esse certificado. Você poderá usar o mesmo certificado para a autenticação de servidor e cliente. |
|**Certificado de autenticação de servidor** |Certificado do servidor Web solicitado da AC emissora ou da AC pública.<br /> Você instala e associa esse certificado SSL no IIS no computador que hospeda o NDES.<br />Se o certificado tiver o conjunto de usos de chave de *autenticação de cliente* e *servidor* (**usos avançados de chave**) no modelo de AC usado para emitir esse certificado. Você poderá usar o mesmo certificado para a autenticação de servidor e cliente. |
|**Certificado de AC raiz confiável**       |Para usar um perfil de Certificado SCEP, os dispositivos precisam confiar na AC (autoridade de certificação) raiz confiável. Use um *perfil de certificado confiável* no Intune para provisionar o Certificado de Autoridade de Certificação raiz confiável para usuários e dispositivos. <br/><br/> **-** Use um único Certificado de Autoridade de Certificação raiz confiável por plataforma de sistema operacional e associe esse certificado a cada perfil de certificado confiável criado. <br /><br /> **-** Use Certificados de Autoridade de Certificação raiz confiáveis adicionais quando necessário. Por exemplo, você pode usar certificados adicionais para fornecer uma relação de confiança a uma AC que assina os certificados de autenticação de servidor para os pontos de acesso Wi-Fi. Crie Certificados de Autoridade de Certificação raiz confiáveis adicionais para ACs emissoras.  No perfil de Certificado SCEP criado no Intune, lembre-se de especificar o perfil de AC raiz confiável para a AC emissora.<br/><br/> Para obter informações sobre o perfil de certificado confiável, confira [Exportar o Certificado de Autoridade de Certificação raiz confiável](certificates-configure.md#export-the-trusted-root-ca-certificate) e [Criar perfis de certificado confiável](certificates-configure.md#create-trusted-certificate-profiles) em *Usar certificados para autenticação no Intune*. |

## <a name="configure-the-certification-authority"></a>Configurar a autoridade de certificação

Na seguintes seções, você vai:

- Configurar e publicar o modelo necessário para o NDES
- Definir as permissões necessárias para a revogação de certificado.

As seções a seguir exigem conhecimento do Windows Server 2012 R2 ou posterior e do AD CS (Serviços de Certificados do Active Directory).

### <a name="access-your-issuing-ca"></a>Acessar a AC emissora

1. Entre na AC emissora com uma conta de domínio com direitos suficientes para gerenciar a AC.

2. Abra o MMC (Console de Gerenciamento Microsoft) da autoridade de certificação. **Execute** 'certsrv.msc' ou, no **Gerenciador do Servidor**, clique em **Ferramentas** e, em seguida, em **Autoridade de Certificação**.

3. Selecione o nó **Modelos de Certificado** e clique em **Ação** > **Gerenciar**.

### <a name="create-the-scep-certificate-template"></a>Criar o modelo de Certificado SCEP

1. Crie um Modelo de Certificado v2 (com compatibilidade com o Windows 2003) para uso como um modelo de Certificado SCEP. Você pode:

   - Usar o snap-in *Modelos de Certificado* para criar um modelo personalizado.
   - Copiar um modelo existente (como o Modelo de usuário) e, em seguida, atualizar a cópia para uso como um modelo do NDES.

2. Defina as seguintes configurações nas guias especificadas do modelo:

   - **Geral**:

     - Desmarque a opção **Publicar certificado no Active Directory**.
     - Especifique um **nome de exibição amigável de Modelo** para que você possa identificar esse modelo mais tarde.

   - **Nome da Entidade**:

     - Selecione **Fornecer na solicitação**. A segurança é imposta pelo módulo de política do Intune para o NDES.

       ![Modelo, guia de nome da entidade](./media/certificates-scep-configure/scep-ndes-subject-name.jpg)

   - **Extensões**:

     - Verifique se **Descrição das Políticas de Aplicativo** inclui **Autenticação de Cliente**.

       > [!IMPORTANT]
       > Adicione apenas as políticas de aplicativo necessárias. Confirme suas escolhas com seus administradores de segurança.

     - Para modelos de certificado do iOS e do macOS, edite também **Uso da Chave** e verifique se a opção **A assinatura é uma prova de origem** não está selecionada.

     ![Modelo, guia de extensões](./media/certificates-scep-configure/scep-ndes-extensions.jpg)  

   - **Segurança**:

     - Adicione a **conta de serviço do NDES**. Esta conta exige permissões de **Leitura** e **Registro** nesse modelo.

     - Adicione contas extras para Administradores do Intune que criarão perfis SCEP. Essas contas exigem permissões de **Leitura** no modelo, de modo a permitir que esses administradores procurem esse modelo durante a criação de perfis SCEP.

     ![Modelo, guia de segurança](./media/certificates-scep-configure/scep-ndes-security.jpg)

   - **Tratamento de Solicitação**:

     A imagem a seguir é um exemplo. A configuração pode variar.  

     ![Modelo, guia de tratamento de solicitação](./media/certificates-scep-configure/scep-ndes-request-handling.png)

   - **Requisitos de Emissão**:

     A imagem a seguir é um exemplo. A configuração pode variar.

     ![Modelo, guia de requisitos de emissão](./media/certificates-scep-configure/scep-ndes-issuance-reqs.jpg)

3. Salve o modelo de certificado.

### <a name="create-the-client-certificate-template"></a>Criar o modelo de certificado do cliente

O Intune Certificate Connector exige um certificado com o uso avançado de chave da *Autenticação de Cliente* e o Nome da entidade igual ao FQDN do computador em que o conector está instalado. É necessário um modelo com as seguintes propriedades:

- **Extensões** > **Políticas de Aplicativo** precisa conter **Autenticação de Cliente**
- **Nome da entidade** > **Fornecer na solicitação**.

Se você já tiver um modelo que inclua essas propriedades, poderá reutilizá-lo; caso contrário, crie outro modelo duplicando um existente ou criando um modelo personalizado.

### <a name="create-the-server-certificate-template"></a>Criar o modelo de certificado do servidor

A comunicação entre os dispositivos gerenciados e o IIS no servidor NDES usa o HTTPS, o que exige o uso de um certificado. Use o modelo de certificado do **servidor Web** para emitir esse certificado. Ou se você preferir ter um modelo dedicado, as seguintes propriedades serão necessárias:

- **Extensões** > **Políticas de Aplicativo** precisa conter **Autenticação de Servidor**
- **Nome da entidade** > **Fornecer na solicitação**.

> [!NOTE]
> Se você tiver um certificado que atenda aos dois requisitos dos modelos de certificado do cliente e do servidor, use um único certificado para o IIS e o Intune Certificate Connector.

### <a name="grant-permissions-for-certificate-revocation"></a>Conceder permissões para a revogação de certificado

Para que o Intune possa revogar certificados que não são mais necessários, é necessário conceder permissões na autoridade de certificação.

No Intune Certificate Connector, use a **conta do sistema** do servidor NDES ou uma conta específica, como a **conta de serviço do NDES**.

1. No console da autoridade de certificação, clique com o botão direito do mouse no nome da Autoridade de Certificação e selecione **Propriedades**.

2. Na guia **Segurança**, clique em **Adicionar**.

3. Conceda a permissão **Emitir e Gerenciar Certificados**:

   - Se você optar por usar a **conta do sistema do servidor NDES**, forneça as permissões ao servidor NDES.
   - Se você optar por usar a **conta de serviço do NDES**, forneça permissões para essa conta.

### <a name="modify-the-validity-period-of-the-certificate-template"></a>Modificar o período de validade do modelo de certificado

É opcional modificar o período de validade do modelo de certificado.  

Depois de [criar o modelo de Certificado SCEP](#create-the-scep-certificate-template), edite o modelo para examinar o **Período de validade** na guia **Geral**.

Por padrão, o Intune usa o valor configurado no modelo. No entanto, você pode configurar a AC para permitir que o solicitante insira outro valor, que pode ser definido no console do Intune.

> [!IMPORTANT]
> Para o iOS e o macOS, use sempre um valor definido no modelo.

#### <a name="to-configure-a-value-that-can-be-set-from-within-the-intune-console"></a>Para configurar um valor que pode ser definido no console do Intune

1. Na AC, execute os seguintes comandos:

   -**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   -**net stop certsvc**
   -**net start certsvc**

2. Na AC emissora, use o snap-in da Autoridade de Certificação para publicar o modelo de certificado. Selecione o nó **Modelos de Certificado**, selecione **Ação** > **Novo** > **Modelo de Certificado a ser Emitido** e, em seguida, selecione o modelo de certificado criado na seção anterior.

3. Valide a publicação do modelo exibindo-o na pasta **Modelos de Certificado**.

## <a name="set-up-ndes"></a>Configurar o NDES

Os procedimentos a seguir podem ajudá-lo a configurar o NDES (Serviço de Registro de Dispositivo de Rede) para uso com o Intune. Para obter mais informações sobre o NDES, confira [Diretrizes do Serviço de Registro de Dispositivo de Rede](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v%3dws.11)).

### <a name="install-the-ndes-service"></a>Instalar o serviço do NDES

1. No servidor que hospedará o serviço do NDES, entre como **Administrador Corporativo** e, em seguida, use o [Assistente de Adição de Funções e Recursos](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) para instalar o NDES:

   1. No assistente, selecione **Serviços de Certificados do Active Directory** para acessar os Serviços de Função do AD CS. Selecione **Serviço de Registro de Dispositivo de Rede**, desmarque **Autoridade de Certificação** e, em seguida, conclua o assistente.

      > [!TIP]
      > Em **Progresso da instalação**, não selecione **Fechar**. Em vez disso, selecione o link **Configurar Serviços de Certificados do Active Directory no servidor de destino**. O assistente de **Configuração do AD CS** será aberto, que você usará para o próximo procedimento neste artigo, *Configurar o serviço do NDES*. Após Configuração AD CS abrir, você pode fechar o Assistente de Adição de Funções e Recursos.

   2. Quando o NDES é adicionado ao servidor, o assistente também instala o IIS. Confirme se o IIS tem as seguintes configurações:

      - **Servidor Web** > **Segurança** > **Filtragem de Solicitações**
      - **Servidor Web** > **Desenvolvimento de Aplicativos** > **ASP.NET 3.5**

        Instalar o ASP.NET 3.5 instala o .NET Framework 3.5. Ao instalar o .NET Framework 3.5, instale o recurso **.NET Framework 3.5** principal e o **Ativação HTTP**.

      - **Servidor Web** > **Desenvolvimento de Aplicativos** > **ASP.NET 4.5**

        Instalar o ASP.NET 4.5 instala o .NET Framework 4.5. Ao instalar o .NET Framework 4.5, instale o recurso principal do **.NET Framework 4.5**, o **ASP.NET 4.5** e o recurso **Serviços WCF** > **Ativação HTTP**.

      - **Ferramentas de Gerenciamento** > **Compatibilidade com Gerenciamento do IIS 6** > **Compatibilidade com Metabase do IIS 6**
      - **Ferramentas de Gerenciamento** > **Compatibilidade com Gerenciamento do IIS 6** > **Compatibilidade com WMI do IIS 6**
      - No servidor, adicione a conta de serviço de NDES como membro do grupo **IIS_IUSR** local.

2. No computador que hospeda o serviço do NDES, execute o comando a seguir em um prompt de comandos com privilégios elevados. O seguinte comando define o SPN da conta de serviço do NDES:

   `setspn -s http/<DNS name of the computer that hosts the NDES service> <Domain name>\<NDES Service account name>`

   Por exemplo, se o computador que hospeda o serviço do NDES se chamar **Server01**, o domínio for **Contoso.com** e a conta de serviço for **NDESService**, use:

   `setspn –s http/Server01.contoso.com contoso\NDESService`  

### <a name="configure-the-ndes-service"></a>Configurar o serviço do NDES

1. No computador que hospeda o serviço do NDES, abra o assistente de **Configuração do AD CS** e, em seguida, faça as seguintes atualizações:

   > [!TIP]
   > Se você está continuando do último procedimento e clicou no link **Configurar os Serviços de Certificados do Active Directory no servidor de destino**, esse assistente já deve estar aberto. Caso contrário, abra o Gerenciador do Servidor para acessar a configuração pós-implantação dos Serviços de Certificados do Active Directory.

   - Em **Serviços de Função**, selecione o **Serviço de Registro de Dispositivo de Rede**.
   - Em **Conta de Serviço para NDES**, especifique a conta de serviço do NDES.
   - Em **AC para NDES**, clique em **Selecionar** e, em seguida, selecione a AC emissora em que você configurou o modelo de certificado.
   - Em **Criptografia para NDES**, defina o comprimento da chave para atender aos requisitos da sua empresa.
   - Em **Confirmação**, selecione **Configurar** para concluir o assistente.

2. Após a conclusão do assistente, atualize a seguinte chave do Registro no computador que hospeda o serviço do NDES:

   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`

   Para atualizar essa chave, identifique a **Finalidade** dos modelos de certificado (encontrada na guia **Tratamento de Solicitação**). Em seguida, atualize a entrada do Registro correspondente substituindo os dados existentes pelo nome do modelo de certificado (não o nome de exibição do modelo) especificado na criação do [modelo de certificado](#create-the-scep-certificate-template).

   A tabela a seguir mapeia a finalidade do modelo de certificado de acordo com os valores do Registro:

   |Finalidade do modelo de certificado (na guia Tratamento de Solicitação)|Valor de registro a ser editado|O valor mostrado no console de administração do Intune para o perfil do protocolo SCEP|
   |------------------------|-------------------------|---|
   |Assinatura               |SignatureTemplate        |Assinatura digital |
   |Criptografia              |EncryptionTemplate       |Codificação de chave  |
   |Assinatura e criptografia|GeneralPurposeTemplate   |Codificação de chave <br/> Assinatura digital |

   Por exemplo, se a Finalidade do seu modelo de certificado for **Criptografia**, edite o valor de **EncryptionTemplate** como o nome do seu modelo de certificado.

3. Configure a Filtragem de Solicitações do IIS para adicionar suporte no IIS às URLs longas (consultas) recebidas pelo serviço do NDES.

   1. No Gerenciador do IIS, selecione **Site Padrão** > **Filtragem de Solicitações** > **Editar Configuração do Recurso** para abrir a página **Editar Configurações da Filtragem de Solicitações**.

   2. Defina as seguintes configurações:

      - **Tamanho máximo da URL (bytes)** = 65.534
      - **Tamanho máximo da cadeia de caracteres de consulta (bytes)** = 65.534

   3. Selecione **OK** para salvar essa configuração e fechar o Gerenciador do IIS.

   4. Valide essa configuração exibindo a seguinte chave do Registro para confirmar se ela tem os valores indicados:

      `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters`

      Os seguintes valores são definidos como entradas DWORD:

      - Nome: **MaxFieldLength**, com um valor decimal de **65534**
      - Nome: **MaxRequestBytes**, com um valor decimal de **65534**

4. Reinicie o servidor que hospeda o serviço do NDES. Não use **iisreset**; iireset não concluirá as alterações necessárias.

5. Navegue até *http://* FQDN_do_Servidor */certsrv/mscep/mscep.dll*. Você deverá ver uma página do NDES semelhante à seguinte imagem:

   ![Testar NDES](./media/certificates-scep-configure/scep-ndes-url.png)

   Se o endereço web retornar uma mensagem **503 Serviço não disponível**, verifique o Visualizador de Eventos dos computadores. Esse erro geralmente ocorre quando o pool de aplicativos é interrompido devido a uma [permissão ausente na conta de serviço do NDES](#accounts).
  
### <a name="install-and-bind-certificates-on-the-server-that-hosts-ndes"></a>Instalar e associar certificados no servidor que hospeda o NDES

> [!TIP]
> No procedimento a seguir, você poderá usar um único certificado para a *autenticação de servidor* e a *autenticação de cliente* quando esse certificado for configurado para atender aos critérios de ambos os usos. Os critérios para cada uso são descritos nas etapas 1 e 3 do procedimento a seguir.

1. Solicite um certificado de **autenticação de servidor** por meio da AC interna ou pública e, em seguida, instale o certificado no servidor.

   Se o servidor usar nomes interno e externo para um único endereço de rede, o certificado de autenticação de servidor precisará ter:

   - Um **Nome da Entidade** com um nome do servidor público externo.
   - Um **Nome Alternativo da Entidade** que inclua o nome do servidor interno.

2. Associar o certificado de autenticação de servidor no IIS:

   1. Depois de instalar o certificado de autenticação de servidor, abra o **Gerenciador do IIS** e selecione o **Site Padrão**. No painel **Ações**, selecione **Associações**.

   1. Selecione **Adicionar**, defina **Tipo** como **https** e, em seguida, confirme que a porta é **443**.
   
   1. Para **Certificado SSL**, especifique o certificado de autenticação de servidor.

3. No seu Servidor de NDES, solicite e instale um certificado de **autenticação de cliente** da sua AC interna ou uma AC pública.

   O certificado de autenticação de cliente deve ter as seguintes propriedades:

   - **Uso avançado de chave**: Esse valor precisa incluir **Autenticação de Cliente**.
   - **Nome da Entidade**: O valor precisa ser igual ao nome DNS do servidor no qual você está instalando o certificado (o Servidor NDES).

4. O servidor que hospeda o serviço do NDES agora está pronto para dar suporte ao Intune Certificate Connector.

## <a name="install-the-intune-certificate-connector"></a>Instalar o Intune Certificate Connector

O Microsoft Intune Certificate Connector é instalado no mesmo servidor que hospeda o serviço do NDES. Não há suporte para uso do NDES ou do Intune Certificate Connector no mesmo servidor da AC (autoridade de certificação) emissora.

### <a name="to-install-the-certificate-connector"></a>Para instalar o Certificate Connector

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Administração de locatários** > **Conectores e tokens** > **Conectores de certificado** > **Adicionar**.

3. Baixe e salve o conector para o arquivo SCEP. Salve-o em uma localização acessível por meio do servidor no qual você instalará o conector.

   ![ConnectorDownload](./media/certificates-scep-configure/download-certificates-connector.png)

4. Após a conclusão do download, acesse o servidor que hospeda a função do NDES (Serviço de Registro de Dispositivo de Rede). Em seguida:

   1. Confirme se o .NET 4.5 Framework está instalado, pois ele é necessário para o Intune Certificate Connector. O .NET 4.5 Framework é incluído automaticamente no Windows Server 2012 R2 e em versões mais recentes.

   2. Execute o instalador (**NDESConnectorSetup.exe**). O instalador também instala o módulo de política para o NDES e o serviço Web de CRP (ponto de registro de certificado) do IIS. O serviço Web de CRP, *CertificateRegistrationSvc*, é executado como um aplicativo no IIS.

      Quando você instala o NDES para o Intune autônomo, o serviço de CRP é instalado automaticamente com o Conector de Certificado.

5. Quando precisar selecionar o certificado do cliente para o Certificate Connector, escolha **Selecionar** e selecione o certificado de **autenticação de cliente** instalado no servidor NDES durante a etapa 3 do procedimento [Instalar e associar certificados no servidor que hospeda o NDES](#install-and-bind-certificates-on-the-server-that-hosts-ndes) anteriormente neste artigo.

   Depois de selecionar o certificado de autenticação de cliente, você retornará para a superfície do **Certificado do Cliente do Microsoft Intune Certificate Connector**. Embora o certificado selecionado não seja mostrado, selecione **Avançar** para exibir as propriedades do certificado. Selecione **Avançar** e, em seguida, **Instalar**.

> [!NOTE]
> É necessário fazer as alterações a seguir para locatários do GCC High antes de iniciar o Intune Certificate Connector.
> 
> Edite os dois arquivos de configuração relacionados abaixo, que atualizarão os pontos de extremidade de serviço do ambiente GCC High. Observe que essas atualizações alteram os sufixos dos URIs de **.com** para **.us**. Há um total de três atualizações de URI, duas atualizações no arquivo de configuração NDESConnectorUI.exe.config e uma atualização no arquivo NDESConnector.exe.config.
> 
> - Nome do arquivo: <install_Path>\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe.config
> 
>   Exemplo: (%programfiles%\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe.config)
>   ```
>    <appSettings>
>        <add key="SignInURL" value="https://portal.manage.microsoft.us/Home/ClientLogon"/>
>        <add key="LocationServiceEndpoint" value="RestUserAuthLocationService/RestUserAuthLocationService/ServiceAddresses"/>
>        <add key="AccountPortalURL" value="https://manage.microsoft.us"/>
>    </appSettings>
>   ```
> 
> - Nome do arquivo: <install_Path>\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config
>
>   Exemplo: (%programfiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config)
>    ```
>    <appSettings>
>        <add key="BaseServiceAddress" value="https://manage.microsoft.us/" />
>    ```
>
> Se essas edições não forem concluídas, os locatários do GCC High receberão este erro: "Acesso negado" "Você não tem autorização para exibir esta página"

6. Após a conclusão do assistente, mas antes de fechá-lo, escolha **Iniciar a Interface do Usuário do Conector de Certificado**.

   Se fechar o assistente antes de iniciar a interface do usuário do Conector de Certificado, você poderá reabri-lo executando o seguinte comando:

   *<install_Path>\NDESConnectorUI\NDESConnectorUI.exe*

7. Na interface do usuário do **Conector de Certificado** :

   1. Selecione em **Entrar** e insira suas credenciais de administrador de serviços do Intune ou as credenciais de um administrador de locatários com permissão de administração global.

   2. A conta usada precisa receber uma licença válida do Intune.

   3. Depois que você entra, o Intune Certificate Connector baixa um certificado do Intune. Esse certificado é usado para autenticação entre o conector e o Intune. Se a conta usada não tiver uma licença do Intune, o conector (NDESConnectorUI.exe) não conseguirá obter o certificado do Intune.  

      Se a sua organização usar um servidor proxy e o proxy for necessário para o servidor NDES acessar a Internet, selecione **Usar servidor proxy**. Em seguida, insira as credenciais de conta, a porta e nome do servidor proxy para se conectar.

   4. Selecione a guia **Avançado** e insira credenciais para uma conta que tenha a permissão **Emitir e Gerenciar Certificados** na sua Autoridade de Certificação emissora. **Aplique** suas alterações.  

    5. Agora você pode fechar a interface do usuário do Conector de Certificado.

8. Abra um prompt de comando, digite **services.msc** e, em seguida, **Enter**. Clique com o botão direito do mouse em **Serviço do Conector do Intune** > **Reiniciar**.

Para validar se o serviço está em execução, abra um navegador e insira a URL a seguir. Ela deverá retornar um erro **403**: `https://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`

> [!NOTE]
> O Intune Certificate Connector dá suporte ao TLS 1.2. Se o servidor que hospeda o conector der suporte ao TLS 1.2, o TLS 1.2 será usado. Se o servidor não dá suporte ao TLS 1.2, o TLS 1.1 é usado. Atualmente, o TLS 1.1 é usado para autenticação entre os dispositivos e o servidor.

## <a name="next-steps"></a>Próximas etapas

[Criar um perfil de certificado SCEP](certificates-profile-scep.md)  
[Solução de problemas do Intune Certificate Connector](troubleshoot-certificate-connector-events.md)
