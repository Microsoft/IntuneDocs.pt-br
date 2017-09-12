---
title: Configurar e gerenciar certificados PKCS com o Intune
titlesuffix: Azure portal
description: Saiba como configurar sua infraestrutura e, depois, criar e atribuir perfis de certificado PKCS com o Intune.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e189ebd1-6ca1-4365-9d5d-fab313b7e979
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1dff7d3e00b26b4f186beb71bacf13738ac857a3
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>Configurar e gerenciar certificados PKCS com o Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este tópico mostra como configurar sua infraestrutura, depois criar e atribuir perfis de certificado PKCS com o Intune.

Para fazer qualquer autenticação baseada em certificado na sua organização, você precisa de uma Autoridade de Certificação Corporativa.

Para usar perfis de certificado PKCS, além da Autoridade de Certificação Corporativa, você também precisa:

-   Um computador que pode se comunicar com a Autoridade de Certificação ou você pode usar o próprio computador da Autoridade de Certificação.

-  O Conector de Certificado do Intune, que é executado no computador, que pode se comunicar com a Autoridade de Certificação.

## <a name="important-terms"></a>Termos importantes


-    **Domínio do Active Directory**: todos os servidores listados nesta seção (exceto pelo Servidor Proxy de Aplicativo Web) devem ser ingressados em seu domínio do Active Directory.

-  **Autoridade de Certificação**: uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. Para ver instruções sobre como configurar uma autoridade de certificação, consulte [Instalar a autoridade de certificação](http://technet.microsoft.com/library/jj125375.aspx).
    Se a sua AC executar o Windows Server 2008 R2, você deve [instalar o hotfix de KB2483564](http://support.microsoft.com/kb/2483564/).

-  **Computador capaz de se comunicar com a Autoridade de Certificação**: como alternativa, use o próprio computador da Autoridade de Certificação.
-  **Microsoft Intune Certificate Connector**: no Portal do Azure, baixe o instalador do **Certificate Connector** (**ndesconnectorssetup.exe**). Em seguida, você pode executar **ndesconnectorssetup.exe** no computador em que deseja instalar o Conector de Certificado. Para os perfis de Certificado PKCS, instale o Certificate Connector no computador que se comunica com a Autoridade de Certificação.
-  **Servidor Proxy de Aplicativos Web** (opcional): você pode usar um servidor que executa o Windows Server 2012 R2 ou posterior como servidor WAP (Proxy de aplicativo Web). Essa configuração:
    -  Permite que os dispositivos recebam certificados usando uma conexão com a Internet.
    -  Trata-se de uma recomendação de segurança quando os dispositivos se conectam pela Internet para receber e renovar certificados.

 > [!NOTE]           
> -    O servidor que hospeda o WAP [deve instalar uma atualização](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) que habilita o suporte para as URLs longas que são usadas pelo NDES (Serviço de Registro de Dispositivo de Rede). Essa atualização está incluída no [pacote cumulativo de atualizações de dezembro de 2014](http://support.microsoft.com/kb/3013769)ou individualmente no [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Além disso, o servidor que hospeda o WAP deve ter um certificado SSL que corresponde ao nome que está sendo publicado para clientes externos, bem como confiar no certificado SSL que é usado no servidor NDES. Esses certificados habilitam o servidor WAP a encerrar a conexão SSL de clientes e a criar uma nova conexão SSL com o servidor NDES.
    Para obter mais informações sobre certificados de WAP, consulte a seção **Planejar certificados** de [Planejando Publicar Aplicativos Usando o Proxy de Aplicativo Web](https://technet.microsoft.com/library/dn383650.aspx). Para obter informações gerais sobre servidores WAP, consulte [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx) (Trabalhando com o Proxy de Aplicativo Web).|


## <a name="certificates-and-templates"></a>Certificados e modelos

|Objeto|Detalhes|
|----------|-----------|
|**Modelo de certificado**|Você configura este modelo na AC emissora.|
|**Certificado de AC raiz confiável**|Você o exporta como um arquivo **.cer** da AC emissora ou de qualquer dispositivo que confie na AC emissora e o atribui nos dispositivos usando o perfil de certificado de AC confiável.<br /><br />Você usa um único certificado de AC raiz confiável por plataforma de sistema operacional e o associa a cada perfil de certificado de raiz confiável que criar.<br /><br />Você pode usar certificados de AC raiz confiável adicionais quando necessário. Por exemplo, você pode fazer isso para fornecer uma relação de confiança a uma AC que conecta os certificados de autenticação do servidor aos pontos de acesso Wi-Fi.|


## <a name="configure-your-infrastructure"></a>Configure sua infraestrutura
Para poder configurar perfis de certificado, você deve concluir as etapas a seguir. Essas etapas exigem conhecimento do Windows Server 2012 R2 e do ADCS (Serviços de Certificados do Active Directory):

- **Etapa 1** - Configurar modelos de certificado na autoridade de certificação.
- **Etapa 2** - Habilitar, instalar e configurar o Conector de Certificado do Intune.

## <a name="step-1---configure-certificate-templates-on-the-certification-authority"></a>Etapa 1 - Configurar modelos de certificado na autoridade de certificação

### <a name="to-configure-the-certification-authority"></a>Para configurar a autoridade de certificação

1.  Na AC emissora, use o snap-in Modelos de Certificado para criar um novo modelo personalizado ou copie e edite um modelo existente (como o modelo de Usuário) para uso com o PKCS.

    O modelo deve incluir o seguinte:

    -   Especifique um **Nome amigável de exibição do modelo** para o modelo.

    -   Na guia **Nome da Entidade** , selecione **Fornecer na solicitação**. (A segurança é imposta pelo módulo de política do Intune para o NDES).

    -   Na guia **Extensões** , verifique se a **Descrição das Políticas de Aplicativo** inclui **Autenticação de Cliente**.

        > [!IMPORTANT]
        > Para modelos de certificado do iOS e macOS, na guia **Extensões**, edite **Uso da Chave** e verifique se a opção **A assinatura é uma prova de origem** não está selecionada.

2.  Examine o **Período de validade** na guia **Geral** do modelo. Por padrão, o Intune usa o valor configurado no modelo. No entanto, você tem a opção de configurar a AC para permitir que o solicitante especifique um valor diferente, que você pode definir de dentro do Console do administrador do Intune. Se você quiser usar sempre o valor no modelo, ignore o restante desta etapa.

    > [!IMPORTANT]
    > O iOS e o macOS sempre usam o valor definido no modelo, independentemente de outras configurações que você fizer.

    Para configurar a AC para permitir que o solicitante especifique o período de validade, execute os seguintes comandos na AC:

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  Na AC emissora, use o snap-in da Autoridade de Certificação para publicar o modelo de certificado.

    a.  Selecione o nó **Modelos de Certificado**, clique em **Ação**-&gt; **Novo** &gt; **Modelo de Certificado a Ser Emitido** e selecione o modelo que você criou na etapa 2.

    b.  Valide a publicação do modelo exibindo-o na pasta **Modelos de Certificado** .

4.  No computador da AC, certifique-se de que o computador que hospeda o Intune Certificate Connector tenha a permissão de registro, para que ele possa acessar o modelo usado na criação do perfil de certificado PKCS. Defina essa permissão na guia **Segurança** das propriedades do computador da Autoridade de Certificação.

## <a name="step-2---enable-install-and-configure-the-intune-certificate-connector"></a>Etapa 2 - Habilitar, instalar e configurar o Conector de Certificado do Intune
Nesta etapa, você vai:

- Habilitar o suporte ao Conector de Certificado
- Baixar, instalar e configurar o Conector de Certificado.

### <a name="to-enable-support-for-the-certificate-connector"></a>Para habilitar o suporte ao Conector de Certificado

1.  Entre no portal do Azure.
2.  Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3.  Na folha **Intune**, escolha **Configurar dispositivos**.
2.  Na folha **Configurações do Dispositivo**, escolha **Configuração** > **Autoridade de Certificação**.
2.  Em **Etapa 1**, escolha **Habilitar**.

### <a name="to-download-install-and-configure-the-certificate-connector"></a>Para baixar, instalar e configurar o Conector de Certificado

1.  Na folha **Configurar dispositivos**, escolha **Configuração** > **Autoridade de Certificação**.
2.  escolha **Baixar o conector de certificado**.
2.  Após a conclusão do download, execute o instalador baixado (**ndesconnectorssetup.exe**).
  Execute o instalador no computador que é capaz de se conectar à Autoridade de Certificação. Escolha a opção de Distribuição de PKCS (PFX) e **Instalar**. Quando a instalação for concluída, continue criando um perfil de certificado conforme descrito em [Como configurar perfis de certificado](certificates-configure.md).

3.  Quando for solicitado o certificado de cliente do Certificate Connector, escolha **Selecionar** e selecione o certificado de **autenticação de cliente** instalado.

    Depois de selecionar o certificado de autenticação de cliente, você retornará para a superfície do **Certificado de Cliente para o Conector de Certificado do Microsoft Intune** . Embora o certificado selecionado não seja exibido, escolha **Avançar** para ver as propriedades do certificado. Escolha **Avançar** e **Instalar**.

4.  Após a conclusão do assistente, mas antes de fechá-lo, clique em **Iniciar a Interface do Usuário do Conector de Certificado**.

    > [!TIP]
    > Se fechar o assistente antes de iniciar a interface do usuário do Conector de Certificado, você poderá reabri-la executando o seguinte comando:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  Na interface do usuário do **Conector de Certificado** :

    a. Escolha **Entrar** e insira suas credenciais de administrador de serviços do Intune ou as credenciais de um administrador de locatários com permissão de administração global.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    b. Selecione a guia **Avançado** e forneça credenciais para uma conta que tenha a permissão **Emitir e Gerenciar Certificados** na sua Autoridade de Certificação emissora.

    c. Escolha **Aplicar**.

    Agora você pode fechar a interface do usuário do Conector de Certificado.

6.  Abra um prompt de comando e digite **services.msc**. Em seguida, pressione **Enter**, clique com o botão direito do mouse em **Serviço de Conector Intune** e escolha **Reiniciar**.

Para validar que o serviço está em execução, abra um navegador e digite a seguinte URL, que deve retornar um erro **403** :

**http:// &lt;FQDN_do_seu_servidor_NDES&gt;/certsrv/mscep/mscep.dll**


### <a name="how-to-create-a-pkcs-certificate-profile"></a>Como criar um perfil de certificado PKCS

No Portal do Azure, selecione a carga de trabalho **Configurar dispositivos**.
2. Na folha **Configurações do dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, clique em **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de certificado PKCS.
5. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado PKCS de:
    - **Android**
    - **Android for Work**
    - **iOS**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **Certificado PKCS**.
7. Na folha **Certificado PKCS**, defina as seguintes configurações:
    - **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
    - **Período de validade do certificado** – Se você executar o comando **certutil – setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** na AC emissora, o que permite usar um período de validade personalizado, poderá especificar a quantidade de tempo restante antes que o certificado expire.<br>Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também tem que ser inferior ao período de validade restante do certificado da AC emissora.
    - **KSP (Provedor de Armazenamento de Chave)** (Windows 10) - especifique o local em que a chave do certificado será armazenada. Escolha um destes valores:
        - **Registrar no KSP do TPM (Trusted Platform Module) se existir; caso contrário, no KSP de Software**
        - **Registrar no KSP do TPM (Trusted Platform Module); caso contrário, falha**
        - **Registrar no Passport; caso contrário, falha (Windows 10 e posterior)**
        - **Registrar no Software KSP**
    - **Autoridade de certificação** - uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. Para ver instruções sobre como configurar uma autoridade de certificação, consulte [Instalar a autoridade de certificação](http://technet.microsoft.com/library/jj125375.aspx). Se a sua AC executar o Windows Server 2008 R2, você deve [instalar o hotfix de KB2483564](http://support.microsoft.com/kb/2483564/).
    - **Nome da autoridade de certificação** - insira o nome do sua autoridade de certificação.
    - **Nome do modelo de certificado** – Insira o nome de um modelo de certificado que o Serviço de Registro de Dispositivo de Rede está configurado para usar e que foi adicionado a uma AC emissora.
    Verifique se o nome corresponde exatamente a um dos modelos de certificado relacionados no registro do servidor que executa o Serviço de Registro de Dispositivo de Rede. Certifique-se de especificar o nome do modelo de certificado e não o nome para exibição do modelo de certificado. 
    Para localizar os nomes dos modelos de certificado, navegue até a seguinte chave: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP. Você verá os modelos de certificado listados como os valores para **EncryptionTemplate**, **GeneralPurposeTemplate**e **SignatureTemplate**. Por padrão, o valor para todos os modelos de certificado é IPSECIntermediateOffline, que mapeia até o nome de exibição do modelo do **IPsec (solicitação offline)**. 
    - **Formato de nome da entidade** – Na lista, selecione como o Intune cria automaticamente o nome da entidade na solicitação de certificado. Se o certificado for para um usuário, você também pode incluir o endereço de email do usuário no nome da entidade. Escolha:
        - **Não configurado**
        - **Nome comum**
        - **Nome comum incluindo email**
        - **Nome comum como email**
    - **Nome alternativo da entidade** – Especifique como o Intune criará automaticamente os valores para o SAN (nome alternativo da entidade) na solicitação de certificado. Se tiver selecionado um tipo de certificado de usuário, por exemplo, você pode incluir o UPN no nome alternativo da entidade. Se o certificado do cliente for usado para se autenticar em um Servidor de Políticas de Rede, defina o nome alternativo da entidade como o UPN. 
    Você também pode selecionar **Atributo personalizado do Azure AD**. Ao selecionar essa opção, outro campo suspenso é exibido. No campo suspenso **Atributo personalizado do Azure AD**, há uma opção: **Departamento**. Ao selecionar essa opção, se o departamento não for identificado no Azure AD, o certificado não será emitido. Para resolver esse problema, identifique o departamento e salve as alterações. No próximo check-in do dispositivo, o problema é resolvido e o certificado é emitido. ASN.1 é a notação usada nesse campo. 
    - **Uso estendido da chave** (Android) – Escolha **Adicionar** para adicionar valores para a finalidade desejada do certificado. Na maioria dos casos, o certificado exigirá **Autenticação de cliente** para que o usuário ou dispositivo possa autenticar-se em um servidor. No entanto, você pode adicionar outros usos da chave conforme necessário. 
    - **Certificado Raiz** (Android) – Escolha um perfil de certificado de AC raiz configurado anteriormente e atribuído ao usuário ou dispositivo. Esse certificado de AC raiz deve ser o certificado raiz da AC que emitirá o certificado que você está configurando nesse perfil de certificado. Este é o perfil de certificado confiável que você criou anteriormente.
8. Quando terminar, volte para a folha **Criar Perfil** e clique em **Criar**.

O perfil é criado e exibido na folha da lista de perfis.

## <a name="how-to-assign-the-certificate-profile"></a>Como atribuir o perfil de certificado

Antes de atribuir perfis de certificado a grupos, considere o seguinte:

- Quando você atribui perfis de certificado a grupos, o arquivo de certificado do perfil do Certificado de Autoridade de Certificação Confiável é instalado no dispositivo. O dispositivo usa o perfil de certificado PKCS para criar uma solicitação de certificado pelo dispositivo.
- Os perfis de certificado são instalados somente em dispositivos que executam a plataforma que você usa ao criar o perfil.
- Você pode atribuir perfis de certificado para coleções de usuários ou coleções de dispositivos.
- Para publicar um certificado em um dispositivo rapidamente depois que o dispositivo for registrado, atribua o perfil de certificado a um grupo de usuários em vez de um grupo de dispositivos. Se você atribuir um grupo de dispositivos, um registro de dispositivo completo será necessário para que o dispositivo receba políticas.
- Embora você atribua cada perfil separadamente, também precisará atribuir a AC Raiz Confiável e o perfil PKCS. Caso contrário, a política de certificação PKCS falhará.

Para saber mais sobre como atribuir perfis, confira [Como atribuir perfis de dispositivo](device-profile-assign.md).
