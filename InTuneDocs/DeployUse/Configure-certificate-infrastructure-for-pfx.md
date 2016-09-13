---
title: Configurar a infraestrutura de certificado para PFX | Microsoft Intune
description: Criar e implantar perfis de certificado .PFX.
keywords: 
author: nbigman
manager: angrobe
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 07d719cadf9c80540ef36f3b6a9187012d715a75
ms.openlocfilehash: 3086bcfd493b45fad3ba2c1bf553203e3396e97c



---
# Configurar a infraestrutura de certificado para PFX
Este tópico descreve o que você precisa para criar e implantar perfis de certificado .PFX.

Para fazer qualquer autenticação baseada em certificado na sua organização, você precisa de uma Autoridade de Certificação Corporativa.

Para usar perfis de certificado .PFX, além da Autoridade de Certificação Corporativa, você também precisa:

-   Um computador que pode se comunicar com a Autoridade de Certificação ou você pode usar o próprio computador da Autoridade de Certificação.

 -  O Conector de Certificado do Intune, que é executado no computador, que pode se comunicar com a Autoridade de Certificação.

## Descrição da infraestrutura local


-    **Domínio do Active Directory**: todos os servidores listados nesta seção (exceto pelo Servidor Proxy de Aplicativo Web) devem ser ingressados em seu domínio do Active Directory.

-  **AC (Autoridade de Certificação)**: uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior. Não há suporte para ACs autônomas. Para ver instruções sobre como configurar uma autoridade de certificação, consulte [Instalar a autoridade de certificação](http://technet.microsoft.com/library/jj125375.aspx).
    Se a sua AC executar o Windows Server 2008 R2, você deve [instalar o hotfix de KB2483564](http://support.microsoft.com/kb/2483564/).

 -  **Computador capaz de se comunicar com a Autoridade de Certificação**: como alternativa, use o próprio computador da Autoridade de Certificação.
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
|**Certificado de AC raiz confiável**|Você o exporta como um arquivo **.cer** da AC emissora ou de qualquer dispositivo que confie na AC emissora e o implanta nos dispositivos usando o perfil de certificado de AC confiável.<br /><br />Você usa um único certificado de AC raiz confiável por plataforma de sistema operacional e o associa a cada perfil de certificado de raiz confiável que criar.<br /><br />Você pode usar certificados de AC raiz confiável adicionais quando necessário. Por exemplo, você pode fazer isso para fornecer uma relação de confiança a uma AC que conecta os certificados de autenticação do servidor aos pontos de acesso Wi-Fi.|


## Configure sua infraestrutura
Antes de configurar perfis de certificado, você deve concluir as seguintes tarefas que exigem conhecimento do Windows Server 2012 R2 e dos AD CS (Serviços de Certificados do Active Directory):

**Tarefa 1** - Configurar modelos de certificado na autoridade de certificação **Tarefa 2** - Habilitar, instalar e configurar o Conector de Certificado do Intune

### Tarefa 1 – Configurar modelos de certificado na autoridade de certificação
Nesta tarefa, você publicará o modelo de certificado

##### Para configurar a autoridade de certificação

1.  Na AC emissora, use o snap-in de Modelos de Certificado para criar um novo modelo personalizado ou copie um modelo existente e o edite para uso (como o modelo de Usuário) com o .pFX.

    O modelo deve ter as seguintes configurações:

    -   Especifique um **Nome amigável de exibição do modelo** para o modelo.

    -   Na guia **Nome da Entidade** , selecione **Fornecer na solicitação**. (A segurança é imposta pelo módulo de política do Intune para o NDES).

    -   Na guia **Extensões** , verifique se a **Descrição das Políticas de Aplicativo** inclui **Autenticação de Cliente**.

        > [!IMPORTANT]
        > Para modelos de certificado do iOS e Mac OS X, na guia **Extensões**, edite **Uso da Chave** e verifique se **A assinatura é uma prova de origem** não está selecionado.


3.  Examine o **Período de validade** na guia **Geral** do modelo. Por padrão, o Intune usa o valor configurado no modelo. No entanto, você tem a opção de configurar a AC para permitir que o solicitante especifique um valor diferente, que você pode definir de dentro do Console do administrador do Intune. Se você quiser usar sempre o valor no modelo, ignore o restante desta etapa.

    > [!IMPORTANT]
    > As plataformas do iOS e Mac OS X sempre usam o valor definido no modelo, independentemente de outras configurações que você fizer.

    Para configurar a AC para permitir que o solicitante especifique o período de validade, execute os seguintes comandos na AC:

    1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    2.  **net stop certsvc**

    3.  **net start certsvc**

4.  Na AC emissora, use o snap-in da Autoridade de Certificação para publicar o modelo de certificado.

    1.  Selecione o nó **Modelos de Certificado**, clique em **Ação**-&gt; **Novo** &gt; **Modelo de Certificado a Ser Emitido** e selecione o modelo que você criou na etapa 2.

    2.  Valide a publicação do modelo exibindo-o na pasta **Modelos de Certificado** .

5.  No computador da AC, certifique-se de que o computador que hospeda o Conector de Certificado do Intune tenha a permissão de registro, para que ele possa acessar o modelo usado na criação do perfil .PFX. Defina essa permissão na guia **Segurança** das propriedades do computador da Autoridade de Certificação.

### Tarefa 2 - Habilitar, instalar e configurar o Conector de Certificado do Intune
Nesta tarefa, você vai:

Baixar, instalar e configurar o Conector de Certificado

##### Para habilitar o suporte ao Conector de Certificado

1.  Abra o [Console de administração do Intune](https://manage.microsoft.com), clique em **Administrador** &gt; **Conector de Certificado**.

2.  Clique em **Configurar Conector de Certificado Local**.

3.  Selecione **Habilitar Conector de Certificado**e clique em **OK**.

##### Para baixar, instalar e configurar o Conector de Certificado

1.  Abra o [Console de administração do Intune](https://manage.microsoft.com) e, em seguida, clique em **Administrador** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Conector de Certificado** &gt; **Baixar Conector de Certificado**.

2.  Após a conclusão do download, execute o instalador baixado (**ndesconnectorssetup.exe**):

  Execute o instalador no computador que é capaz de se conectar à Autoridade de Certificação. Escolha a opção de Distribuição .PFX e clique em Instalar. Quando a instalação for concluída, continue criando um perfil de certificado conforme descrito em [Configure certificate profiles](configure-intune-certificate-profiles.md) (Configurar perfis de certificado).

   <!-- Not sure about step 3 below -->

3.  Quando for solicitado o certificado de cliente do Conector de Certificado, clique em **Selecionar** e selecione o certificado de **autenticação de cliente** instalado na Tarefa 3.

    Depois de selecionar o certificado de autenticação de cliente, você retornará para a superfície do **Certificado de Cliente para o Conector de Certificado do Microsoft Intune** . Embora o certificado selecionado não seja exibido, clique em **Avançar** para ver as propriedades do certificado. Em seguida, clique em **Avançar**e clique em **Instalar**.

4.  Após a conclusão do assistente, mas antes de fechá-lo, clique em **Iniciar a Interface do Usuário do Conector de Certificado**.

    > [!TIP]
    > Se fechar o assistente antes de iniciar a interface do usuário do Conector de Certificado, você poderá reabri-la executando o seguinte comando:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  Na interface do usuário do **Conector de Certificado** :

    Clique em **Entrar** e insira suas credenciais de administrador de serviços do Intune ou as credenciais de um administrador de locatários com permissão de administração global.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    Selecione a guia **Avançado** e forneça credenciais para uma conta que tenha a permissão **Emitir e Gerenciar Certificados** na sua Autoridade de Certificação emissora e clique em **Aplicar**.

    Agora você pode fechar a interface do usuário do Conector de Certificado.

6.  Abra um prompt de comando e digite **services.msc**, pressione **Enter**, clique com o botão direito do mouse em **Serviço de Conector do Intune** e clique em **Reiniciar**.

Para validar que o serviço está em execução, abra um navegador e digite a seguinte URL, que deve retornar um erro **403** :

**http:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**

### Próximas etapas
Agora você está pronto para configurar perfis de certificado, conforme descrito em [Configure certificate profiles](Configure-Intune-certificate-profiles.md) (Configurar perfis de certificado).



<!--HONumber=Aug16_HO4-->


