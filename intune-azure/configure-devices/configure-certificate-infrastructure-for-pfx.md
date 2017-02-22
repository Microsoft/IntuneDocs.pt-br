---
title: "Configurar a infraestrutura de certificado do Intune para o PKCS | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba como configurar sua infraestrutura para usar certificados PKCS com o Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e189ebd1-6ca1-4365-9d5d-fab313b7e979
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f05e0018fb202ab5774e935c3f59855e4aa2e75
ms.openlocfilehash: 74f2cc7221e737371d7db97ec25d872578df273d



---
# <a name="configure-your-intune-certificate-infrastructure-for-pkcs"></a>Configurar sua infraestrutura de certificado do Intune para PKCS
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Este tópico descreve o que você precisa para criar e implantar perfis de certificado PKCS com o Intune.

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
|**Certificado de AC raiz confiável**|Você o exporta como um arquivo **.cer** da AC emissora ou de qualquer dispositivo que confie na AC emissora e o implanta nos dispositivos usando o perfil de certificado de AC confiável.<br /><br />Você usa um único certificado de AC raiz confiável por plataforma de sistema operacional e o associa a cada perfil de certificado de raiz confiável que criar.<br /><br />Você pode usar certificados de AC raiz confiável adicionais quando necessário. Por exemplo, você pode fazer isso para fornecer uma relação de confiança a uma AC que conecta os certificados de autenticação do servidor aos pontos de acesso Wi-Fi.|


## <a name="configure-your-infrastructure"></a>Configure sua infraestrutura
Para poder configurar perfis de certificado, você deve concluir as tarefas a seguir. Essas tarefas exigem conhecimento do Windows Server 2012 R2 e do ADCS (Serviços de Certificados do Active Directory):

- **Tarefa 1** – configurar modelos de certificado na autoridade de certificação.
- **Tarefa 2** - habilitar, instalar e configurar o Conector de Certificado do Intune.

## <a name="task-1---configure-certificate-templates-on-the-certification-authority"></a>Tarefa 1 – Configurar modelos de certificado na autoridade de certificação
Nesta tarefa, você publicará o modelo de certificado.

### <a name="to-configure-the-certification-authority"></a>Para configurar a autoridade de certificação

1.  Na AC emissora, use o snap-in Modelos de Certificado para criar um novo modelo personalizado ou copie e edite um modelo existente (como o modelo de Usuário) para uso com o PKCS.

    O modelo deve incluir o seguinte:

    -   Especifique um **Nome amigável de exibição do modelo** para o modelo.

    -   Na guia **Nome da Entidade** , selecione **Fornecer na solicitação**. (A segurança é imposta pelo módulo de política do Intune para o NDES).

    -   Na guia **Extensões** , verifique se a **Descrição das Políticas de Aplicativo** inclui **Autenticação de Cliente**.

        > [!IMPORTANT]
        > Para modelos de certificado do iOS e Mac OS X, na guia **Extensões**, edite **Uso da Chave** e verifique se **A assinatura é uma prova de origem** não está selecionado.

2.  Examine o **Período de validade** na guia **Geral** do modelo. Por padrão, o Intune usa o valor configurado no modelo. No entanto, você tem a opção de configurar a AC para permitir que o solicitante especifique um valor diferente, que você pode definir de dentro do Console do administrador do Intune. Se você quiser usar sempre o valor no modelo, ignore o restante desta etapa.

    > [!IMPORTANT]
    > As plataformas do iOS e Mac OS X sempre usam o valor definido no modelo, independentemente de outras configurações que você fizer.

    Para configurar a AC para permitir que o solicitante especifique o período de validade, execute os seguintes comandos na AC:

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  Na AC emissora, use o snap-in da Autoridade de Certificação para publicar o modelo de certificado.

    a.  Selecione o nó **Modelos de Certificado**, clique em **Ação**-&gt; **Novo** &gt; **Modelo de Certificado a Ser Emitido** e selecione o modelo que você criou na etapa 2.

    b.  Valide a publicação do modelo exibindo-o na pasta **Modelos de Certificado** .

4.  No computador da AC, certifique-se de que o computador que hospeda o Intune Certificate Connector tenha a permissão de registro, para que ele possa acessar o modelo usado na criação do perfil de certificado PKCS. Defina essa permissão na guia **Segurança** das propriedades do computador da Autoridade de Certificação.

## <a name="task-2---enable-install-and-configure-the-intune-certificate-connector"></a>Tarefa 2 - Habilitar, instalar e configurar o Conector de Certificado do Intune
Nesta tarefa, você vai:

Baixar, instalar e configurar o Conector de Certificado.

### <a name="to-enable-support-for-the-certificate-connector"></a>Para habilitar o suporte ao Conector de Certificado

1.  Entre no portal do Azure.
2.  Escolha **Mais Serviços** > **Outros** > **Intune**.
3.  Na folha **Intune**, escolha **Configurar dispositivos**.
2.  Na folha **Configurações do Dispositivo**, escolha **Configuração** > **Autoridade de Certificação**.
2.  Em **Etapa 1**, escolha **Habilitar**.

### <a name="to-download-install-and-configure-the-certificate-connector"></a>Para baixar, instalar e configurar o Conector de Certificado

1.  Na folha **Configurar dispositivos**, escolha **Configuração** > **Autoridade de Certificação**.
2.  escolha **Baixar o conector de certificado**.
2.  Após a conclusão do download, execute o instalador baixado (**ndesconnectorssetup.exe**).
  Execute o instalador no computador que é capaz de se conectar à Autoridade de Certificação. Escolha a opção de Distribuição de PKCS (PFX) e **Instalar**. Quando a instalação for concluída, continue criando um perfil de certificado conforme descrito em [Como configurar perfis de certificado](how-to-configure-certificates.md).

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

### <a name="next-steps"></a>Próximas etapas
Agora você está pronto para configurar perfis de certificado, conforme descrito em [Como configurar certificados com o Microsoft Intune](how-to-configure-certificates.md).



<!--HONumber=Feb17_HO1-->


