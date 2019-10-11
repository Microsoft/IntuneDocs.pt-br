---
title: Emitir certificados PKCS da DigiCert com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Instale e configure o Intune Certificate Connector a fim de emitir certificados PKCS da plataforma DigiCert PKI para dispositivos gerenciados pelo Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1679eb656e04296e53d8994dcd47144621c99d0c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721767"
---
# <a name="set-up-intune-certificate-connector-for-digicert-pki-platform"></a>Configurar o Intune Certificate Connector para a plataforma DigiCert PKI  

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Use o Intune Certificate Connector a fim de emitir certificados PKCS da plataforma DigiCert PKI para dispositivos gerenciados pelo Intune. Você pode usar o conector com apenas uma AC (autoridade de certificação) DigiCert ou com uma AC DigiCert e uma AC Microsoft.  
> [!TIP]  
> A DigiCert adquiriu a Segurança de Site da Symantec e o negócio de Soluções de PKI associado. Para saber mais sobre essa mudança, confira o [artigo de suporte técnico da Symantec](https://support.symantec.com/en_US/article.INFO4722.html).

Se você já usa o Intune Certificate Connector para emitir certificados de uma AC Microsoft usando PKCS ou System Center Endpoint Protection, pode usar esse mesmo conector para configurar e emitir certificados PKCS de uma AC DigiCert. Após concluir a configuração para dar suporte à AC da DigiCert, o Intune Certificate Connector é capaz de emitir os seguintes certificados:

* Certificados PKCS de uma AC Microsoft
* Certificados PKCS de uma AC DigiCert
* Certificados Endpoint Protection de uma AC Microsoft

Se você não tem o conector instalado, mas planeja usá-lo em uma AC Microsoft e em uma AC DigiCert, conclua a configuração do conector para a AC Microsoft primeiro. Depois, retorne a este artigo para configurar o conector a fim de também dar suporte à DigiCert. Para saber mais sobre perfis de certificado e sobre o conector, confira [Configurar um perfil de certificado para seus dispositivos no Microsoft Intune](certificates-configure.md).  

Se você usar o conector somente com a AC DigiCert, poderá usar as instruções neste artigo para instalá-lo e configurá-lo. 

## <a name="prerequisites"></a>Pré-requisitos  
- **Uma assinatura ativa da AC DigiCert**: a assinatura é necessária para obter um certificado AR (autoridade de registro) da AC DigiCert.

## <a name="install-the-digicert-ra-certificate"></a>Instalar o certificado AR da DigiCert  
 
1. Salve o seguinte trecho de código como um arquivo chamado **certreq.ini** e atualize-o conforme a necessidade (por exemplo: *Nome da entidade no formato CN*).
 
        [Version] 
        Signature="$Windows NT$" 
        
        [NewRequest] 
        ;Change to your,country code, company name and common name 
        Subject = "Subject Name in CN format"
        
        KeySpec = 1 
        KeyLength = 2048 
        Exportable = TRUE 
        MachineKeySet = TRUE 
        SMIME = False 
        PrivateKeyArchive = FALSE 
        UserProtected = FALSE 
        UseExistingKeySet = FALSE 
        ProviderName = "Microsoft RSA SChannel Cryptographic Provider" 
        ProviderType = 12 
        RequestType = PKCS10 
        KeyUsage = 0xa0 
        
        [EnhancedKeyUsageExtension] 
        OID=1.3.6.1.5.5.7.3.2 ; Client Authentication  // Uncomment if you need a mutual TLS authentication
        
        ;----------------------------------------------- 

2. Abra um prompt de comando com privilégios elevados e gere uma CSR (solicitação de assinatura de certificado) usando o seguinte comando:

   `Certreq.exe -new certreq.ini request.csr`

3. Abra o arquivo request.csr no Bloco de Notas e copie o conteúdo da CSR que está no seguinte formato:


        -----BEGIN NEW CERTIFICATE REQUEST-----
        MIID8TCCAtkCAQAwbTEMMAoGA1UEBhMDVVNBMQswCQYDVQQIDAJXQTEQMA4GA1UE
        …
        …
        fzpeAWo=
        -----END NEW CERTIFICATE REQUEST-----


4. Entre na AC DigiCert e navegue até **Obter um certificado AR** nas tarefas.

   a. Na caixa de texto, forneça o conteúdo da CSR da etapa 3. 

   b. Forneça um nome amigável ao certificado.

   c. Selecione **Continuar**. 

   d. Use o link fornecido a fim de baixar o certificado AR para o computador local.

5. Importe o certificado AR para o repositório de certificados do Windows:

   a. Abra um console do MMC.

   b. Selecione **Arquivo** > **Adicionar ou remover snap-ins** > **Certificado** > **Adicionar**. 

   c. Selecione **Conta de Computador** > **Avançar**.

   d. Selecione **Computador Local** > **Concluir**. 

   e. Selecione **OK** na janela **Adicionar ou Remover Snap-ins**. Expanda **Certificados (Computador Local)**  > **Pessoal** > **Certificados**.

   f. Clique com o botão direito no nó **Certificados** e selecione **Todas as Tarefas** > **Importar**.  

   g. Selecione o local do certificado AR que você baixou da AC DigiCert e selecione **Avançar**.

   h. Selecione **Repositório de Certificados Pessoal** > **Avançar**. 

   i. Selecione **Concluir** a fim de importar o certificado AR e sua chave privada para o repositório **Computador Local-Pessoal**.  

6. Exportar e importar o certificado de chave privada: 

   a. Expanda **Certificados (Computador Local)**  > **Pessoal** > **Certificados**.

   b. Selecione o certificado que foi importado na etapa anterior.

   c. Clique com o botão direito do mouse no certificado e selecione **Todas as Tarefas** > **Exportar**.

   d. Selecione **Avançar** e insira a senha.

   e. Selecione o local para o qual exportar e selecione **Concluir**.

   f. Use o procedimento da Etapa 5 a fim de importar o certificado de chave privada para o repositório **Computador Local-Pessoal**.

   g. Copie a impressão digital do certificado AR sem espaços. Abaixo temos um exemplo de impressão digital: 

        RA Cert Thumbprint: “EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5”
    
    > [!NOTE]
    > Para obter ajuda na obtenção do certificado AR da AC DigiCert, entre em contato com o [suporte ao cliente da DigiCert](mailto:enterprise-pkisupport@digicert.com).  

## <a name="prepare-to-install-intune-certificate-connector"></a>Preparar-se para a instalação do Intune Certificate Connector
> [!TIP]  
> Está seção se aplicará quando você usar o Intune Certificate Connector apenas com uma AC DigiCert. Se você usar o Intune Certificate Connector com uma AC da Microsoft e quiser adicionar o suporte da AC da DigiCert, pule para [Configurar o conector para dar suporte à DigiCert](#configure-the-connector-to-support-digicert).  

1. Escolha uma das versões do sistema operacional Windows na lista abaixo e instale-a em um computador:
   * Windows Server 2012 R2 Datacenter
   * Windows Server 2012 R2 Standard
   * Windows Server 2016 Datacenter
   * Windows Server 2016 Standard

2. Crie um usuário com privilégios administrativos e use-o para concluir as etapas a seguir.

3. Verifique as atualizações do Windows mais recentes e instale as que estiverem disponíveis. Depois de instalar atualizações do Windows, reinicie o computador.

4. Instale o .NET Framework 3.5:

   a. Abra **Painel de Controle** > **Programas e Recursos** > **Ativar ou Desativar recursos do Windows**.

   b. Selecione **.NET Framework 3.5** e instale-o.  

## <a name="install-intune-certificate-connector-for-use-with-digicert"></a>Instalar o Intune Certificate Connector para uso com a DigiCert  

> [!TIP]  
> Se você usar o Intune Certificate Connector com uma AC da Microsoft e quiser adicionar o suporte da AC da DigiCert, pule para [Configurar o conector para dar suporte à DigiCert](#configure-the-connector-to-support-digicert).  

Baixe o Intune Certificate Connector mais recente do portal de administração do Intune e siga estas instruções.

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).  

2. Selecione **Configuração do dispositivo** > **Conectores de certificado** >  **+ Adicionar**.  

3. Selecione **Baixar o software do conector de certificado**. Salve o software em um local que pode ser acessado pelo servidor no qual você vai instalá-lo.  

   ![Baixar o software do conector](./media/certificates-digicert-configure/connector-download.png)
   
4. No servidor em que você deseja instalar o conector, execute **NDESConnectorSetup.exe** com privilégios elevados. 

5. Na página **Opções de Instalação**, selecione **Distribuição de PFX**.  
   
   ![Selecionar Distribuição de PFX](./media/certificates-digicert-configure/digicert-ca-connector-install.png)

   > [!IMPORTANT]
   > Se você vai usar o Intune Certificate Connector para emitir certificados de uma CA da Microsoft e de uma AC DigiCert, selecione **Distribuição de Perfil SCEP e PFX**. 

6. Use as seleções padrão para concluir a configuração do conector.

## <a name="configure-the-connector-to-support-digicert"></a>Configurar o conector para dar suporte à DigiCert

Por padrão, o Intune Certificate Connector é instalado em **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc**.

1. Na pasta **NDESConnectorSvc**, abra o arquivo **NDESConnector.exe.config** no Bloco de Notas.

   a. Atualize o valor da chave `RACertThumbprint` com o valor de impressão digital do certificado que você copiou na seção anterior. Por exemplo:

        <add key="RACertThumbprint"
        value="EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5"/>
   
   b. Salve e feche o arquivo.

2. Abra **services.msc**:

   a. Selecione **Serviço do Conector do Intune**.

   b. Interrompa o serviço e, depois, inicie o serviço.

   c. Feche a janela do serviço.

## <a name="set-up-the-intune-administrator-account"></a>Configurar a conta de administrador do Intune  

> [!TIP]  
> Se você usar o Intune Certificate Connector com uma AC Microsoft e quiser adicionar o suporte da AC DigiCert, pule para [Criar um perfil de certificado confiável](#create-a-trusted-certificate-profile).   
 
1. Abra a interface do usuário do conector NDES com o executável **%ProgramFiles%\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe**.  

2. Na guia **Registro**, selecione **Entrar**.

3. Forneça suas credenciais de administrador de locatário do Intune.

4. Selecione **Entrar** e, em seguida, **OK** para confirmar um registro com êxito. Feche a interface do usuário do Conector NDES.
   
   ![Interface do Conector NDES com a mensagem "Registrado com êxito"](./media/certificates-digicert-configure/certificates-digicert-configure-connector-configure.png)



## <a name="create-a-trusted-certificate-profile"></a>Criar um perfil de certificado confiável

Os certificados PKCS que você implanta em dispositivos gerenciados pelo Intune devem ser encadeados com um certificado raiz confiável. Para estabelecer essa cadeia, crie um perfil de certificado confiável do Intune com o certificado raiz da AC DigiCert.

1. Obtenha um certificado raiz confiável da AC DigiCert:

    a. Entre no portal de administração da AC DigiCert.

    b. Selecione **Gerenciar ACs** em **Tarefas**. 

    c. Selecione na lista a AC apropriada.  

    d. Selecione **Baixar certificado raiz** para baixar o certificado raiz confiável.

2. Crie um perfil de certificado confiável no portal do Intune:

   a. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

   b. Selecione **Configuração do dispositivo** > **Gerenciar** > **Perfis** > **Criar perfil**.

   c. Insira **Nome** e **Descrição** para o perfil de certificado confiável.

   d. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado confiável.

   e. Na lista suspensa **Tipo de perfil**, selecione **Certificado confiável**.

   f. Navegue até o arquivo da AC .cer de raiz confiável que você obteve da AC DigiCert na etapa anterior e selecione **OK**.

   g. Somente para dispositivos Windows 8.1 e Windows 10, selecione o repositório de destino para o certificado confiável de:    
      - **Repositório de certificados do computador – Raiz**  
      - **Repositório de certificados do computador – Intermediário**  
      - **Repositório de certificados do usuário – Intermediário** 

   h. Quando terminar, selecione **OK**, volte para o painel **Criar perfil** e selecione **Criar**.  
 
O perfil é exibido na lista de perfis no painel **Configuração do dispositivo – Perfis**, com um tipo de perfil **Certificado confiável**.  Atribua esse perfil a dispositivos que receberão certificados. Para atribuir o perfil a grupos, confira [Atribuir perfis de dispositivo](../configuration/device-profile-assign.md).


## <a name="get-the-certificate-profile-oid"></a>Obter o OID do perfil de certificado  

O OID do perfil de certificado está associado a um modelo de perfil de certificado na AC DigiCert. Para criar um perfil de certificado PKCS no Intune, o nome do modelo de certificado deve estar na forma de um OID de perfil de certificado associado a um modelo de certificado na AC DigiCert.

1. Entre no portal de administração da AC DigiCert.
2. Selecione **Gerenciar Perfis de Certificado**.
3. Selecione o perfil de certificado que você deseja usar.
4. Copie o OID do perfil de certificado. Ele é semelhante ao exemplo a seguir:

 
       Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109 
 

> [!NOTE]
> Se você precisar de ajuda para obter o OID do perfil de certificado, entre em contato com o [suporte ao cliente da DigiCert](mailto:enterprise-pkisupport@digicert.com).

## <a name="create-a-pkcs-certificate-profile"></a>Criar um perfil de certificado PKCS

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).  

2. Vá para **Configuração do dispositivo** >  **Perfis** e selecione **Criar perfil**.

3. Insira **Nome** e **Descrição** para o perfil de certificado PKCS.  

4. Na lista suspensa **Plataforma**, selecione uma plataforma de dispositivo com suporte.

5. Na lista suspensa **Tipo de perfil**, selecione **Certificado PKCS**.
 
6. No painel **Certificado PKCS**, configure parâmetros com os valores da tabela a seguir. Esses valores são necessários para emitir certificados PKCS de uma AC DigiCert por meio do Intune Certificate Connector. 

   |Parâmetro de certificado PKCS | Valor | Descrição |
   | --- | --- | --- |
   | Autoridade de certificação | pki-ws.symauth.com | Esse valor deve ser um FQDN de serviço base da AC DigiCert sem barras à direita. Se você não tiver certeza de que esse é o FQDN de serviço base correto para sua assinatura da AC DigiCert, entre em contato com o suporte ao cliente da DigiCert. <br><br>*Com a alteração da Symantec para a DigiCert, essa URL permaneceu inalterada*. <br><br> Se o FQDN estiver incorreto, o Intune Certificate Connector não emitirá Certificados PKCS da AC DigiCert.| 
   | Nome da autoridade de certificação | Symantec | Esse valor deve ser a cadeia de caracteres **Symantec**. <br><br> Se houver alguma alteração nesse valor, o Intune Certificate Connector não emitirá certificados PKCS da AC DigiCert.|
   | Nome do modelo de certificado | OID do perfil de certificado da AC DigiCert. Por exemplo: **2.16.840.1.113733.1.16.1.2.3.1.1.61904612**| Esse valor deve ser um OID de perfil de certificado [obtido na seção anterior](#get-the-certificate-profile-oid) do modelo de perfil de certificado da AC DigiCert. <br><br> Se o Intune Certificate Connector não puder localizar um modelo de certificado associado a esse OID de perfil de certificado na AC DigiCert, ele não emitirá certificados PKCS da AC DigiCert.|  

   ![Seleções para modelo de certificado e de AC](./media/certificates-digicert-configure/certificates-digicert-pkcs-example.png)  

   > [!NOTE]
   > Os perfis de certificado PKCS para plataformas do Windows não precisam ser associados a um perfil de certificado confiável. Mas isso é necessário para perfis que não são de plataformas do Windows, como Android.
7. Conclua a configuração do perfil para atender às suas necessidades de negócios e selecione **OK** para salvá-lo. 

8. Selecione **Atribuições** e configure um grupo apropriado para receber esse perfil. Pelo menos um usuário ou dispositivo deve fazer parte do grupo atribuído.
 
Depois de concluir as etapas anteriores, o Intune Certificate Connector emitirá certificados PKCS da AC DigiCert para dispositivos gerenciados pelo Intune no grupo atribuído. Esses certificados estarão disponíveis no repositório **Pessoal** do repositório de certificados do **Usuário Atual** no dispositivo gerenciado pelo Intune.

### <a name="supported-attributes-for-the-pkcs-certificate-profile"></a>Atributos com suporte para o perfil de certificado PKCS

|Atributo | Formatos com suporte pelo Intune | Formatos com suporte da AC DigiCert Cloud | result |
| --- | --- | --- | --- |
| Nome da entidade |O Intune dá suporte ao nome da entidade apenas nos três formatos a seguir: <br><br> 1. Nome comum <br> 2. Nome comum que inclui email <br> 3. Nome comum como email <br><br> Por exemplo: <br><br> `CN = IWUser0 <br><br> E = IWUser0@samplendes.onmicrosoft.com` | A AC da DigiCert dá suporte a mais atributos.  Se você quiser selecionar mais atributos, eles deverão ser definidos com valores fixos no modelo de perfil de certificado da DigiCert.| Usamos o nome comum ou email da solicitação de Certificado PKCS. <br><br> Eventual incompatibilidade na seleção de atributos entre o perfil de certificado do Intune e do modelo de perfil de certificado da DigiCert resultará na não emissão de certificados da AC DigiCert.|
| SAN | O Intune dá suporte apenas aos seguintes valores de campo de SAN: <br><br> **AltNameTypeEmail** <br> **AltNameTypeUpn** <br> **AltNameTypeOtherName** (valor codificado) | A AC da DigiCert Cloud também dá suporte a esses parâmetros. Se você quiser selecionar mais atributos, eles deverão ser definidos com valores fixos no modelo de perfil de certificado da DigiCert. <br><br> **AltNameTypeEmail**: se esse tipo não for encontrado na rede SAN, o Intune Certificate Connector usará o valor de **AltNameTypeUpn**.  Se **AltNameTypeUpn** também não for encontrado na rede SAN, o Intune Certificate Connector usará o valor do nome do assunto se ele estiver no formato de email.  Se o tipo ainda assim não for encontrado, o Intune Certificate Connector não emitirá os certificados. <br><br> Exemplo: `RFC822 Name=IWUser0@ndesvenkatb.onmicrosoft.com`  <br><br> **AltNameTypeUpn**: se esse tipo não for encontrado na rede SAN, o Intune Certificate Connector usará o valor de **AltNameTypeEmail**. Se **AltNameTypeEmail** também não for encontrado na rede SAN, o Intune Certificate Connector usará o valor do nome do assunto se ele estiver no formato de email. Se o tipo ainda assim não for encontrado, o Intune Certificate Connector não emitirá os certificados.  <br><br> Exemplo: `Other Name: Principal Name=IWUser0@ndesvenkatb.onmicrosoft.com` <br><br> **AltNameTypeOtherName**: se esse tipo não for encontrado na rede SAN, o Intune Certificate Connector não emitirá os certificados. <br><br> Exemplo: `Other Name: DS Object Guid=04 12 b8 ba 65 41 f2 d4 07 41 a9 f7 47 08 f3 e4 28 5c ef 2c` <br><br>  Observe que o valor desse campo só tem suporte da AC DigiCert no formato codificado (valor hexadecimal). Em relação a qualquer valor nesse campo, o Intune Certificate Connector o converterá em codificado em base 64 antes de enviar a solicitação de certificado. *O Intune Certificate Connector não valida se este valor já está codificado ou não.* | Não |

## <a name="troubleshooting"></a>Solução de problemas

Os logs do serviço Intune Certificate Connector estão disponíveis em **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\Logs\Logs** no computador do Conector NDES. Abra os logs no [SvcTraceViewer](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) e procure por mensagens de erro ou exceções.

| Problema/mensagem de erro | Etapas de resolução |
| --- | --- |
| Não é possível entrar com a conta de administrador de locatário do Intune na interface do usuário do Conector NDES. | Isso pode acontecer quando o conector de certificado local não está habilitado no portal de administração do Intune. Para resolver esse problema, use um dos seguintes procedimentos: <br><br> Na interface do usuário do Silverlight: <br> 1. Entre no [portal de administração do Intune](https://admin.manage.microsoft.com). <br> 2. Selecione **ADMINISTRADOR**. <br> 3. Selecione **Gerenciamento de Dispositivo Móvel** > **Certificate Connector**. <br> 4. Selecione **Configurar Conector de Certificado Local**. <br> 5. Marque a caixa de seleção **Habilitar Conector de Certificado**. <br> 6. Selecione **OK**. <br><br> Na interface do usuário do Portal do Azure: <br> 1. Entre no [Portal do Azure](https://portal.azure.com). <br> 2. Acesse o Microsoft Intune. <br> 3. Selecione **Configuração do Dispositivo** > **Autoridade de Certificação**. <br> 4. Selecione **Habilitar**. <br><br> Depois de concluir as etapas anteriores na interface do usuário do Silver Light ou do portal do Azure, tente entrar com a mesma conta de administrador de locatário do Intune na interface do usuário do Conector NDES. |
| Não foi possível encontrar o certificado do Conector NDES. <br><br> System.ArgumentNullException: O valor não pode ser nulo. | O Intune Certificate Connector mostra esse erro se a conta de administrador de locatário do Intune nunca tiver entrado na interface do usuário do Conector NDES. <br><br> Se esse erro persistir, reinicie o conector do serviço Intune. <br><br> 1. Abra **services.msc**. <br> 2. Selecione **Serviço do Conector do Intune**. <br> 3. Clique com o botão direito e selecione **Reiniciar**.|
| Conector NDES - IssuePfx -Generic Exception: <br> System.NullReferenceException: a referência de objeto não está definida em uma instância de um objeto. | Esse erro é transitório. Reinicie o conector do serviço Intune. <br><br> 1. Abra **services.msc**. <br> 2. Selecione **Serviço do Conector do Intune**. <br> 3. Clique com o botão direito e selecione **Reiniciar**. |
| Provedor DigiCert – falha ao obter a política da DigiCert. <br><br>"A operação atingiu o tempo limite." | O Intune Certificate Connector recebeu um erro de tempo limite da operação durante a comunicação com a AC DigiCert. Se esse erro persistir, aumente o valor de tempo limite da conexão e tente novamente. <br><br> Para aumentar o tempo limite da conexão: <br> 1. Acesse o computador do Conector NDES. <br>2. Abra o arquivo **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config** no Bloco de Notas. <br> 3. Aumente o valor de tempo limite para o seguinte parâmetro: <br><br> `CloudCAConnTimeoutInMilliseconds` <br><br> 4. Reinicie o serviço Intune Certificate Connector. <br><br> Se o problema persistir, entre em contato com o atendimento ao cliente da DigiCert. |
| Provedor da DigiCert – falha ao obter o certificado do cliente. | O Intune Certificate Connector não conseguiu recuperar o certificado de autorização de recursos do repositório de certificados Computador Local-Pessoal. Para resolver esse problema, instale o certificado de autorização de recursos no repositório de certificados Computador Local-Pessoal junto com sua chave privada. <br><br> O certificado de autorização de recursos deve ser obtido da AC DigiCert. Para obter mais detalhes, entre em contato com o suporte ao cliente da DigiCert. | 
| Provedor DigiCert – falha ao obter a política da DigiCert. <br><br>"A solicitação foi anulada: não foi possível criar um canal SSL/TLS seguro". | Esse erro ocorre nos seguintes cenários: <br><br> 1. O serviço Intune Certificate Connector não tem permissões para ler o certificado de autorização de recursos junto com sua chave privada do repositório de certificados Computador Local-Pessoal. Para resolver esse problema, verifique a conta de contexto em execução do serviço conector em services.msc. O serviço conector deve ser executado no contexto NT AUTHORITY\SYSTEM. <br><br> 2. O perfil do certificado PKCS no portal de administração do Intune pode estar configurado com um FQDN do serviço de base inválido para a AC DigiCert. O FQDN é semelhante a **pki-ws.symauth.com**. Para resolver esse problema, verifique com o atendimento ao cliente da DigiCert se a URL está correta para sua assinatura. <br><br> 3. O Intune Certificate Connector não consegue fazer a autenticação na AC DigiCert por meio do certificado de autorização de recursos porque não consegue recuperar a chave privada. Para resolver esse problema, instale o certificado de autorização de recursos, junto com sua chave privada, no repositório de certificados Computador Local-Pessoal. <br><br> Se o problema persistir, entre em contato com o atendimento ao cliente da DigiCert. |
| Provedor DigiCert – falha ao obter a política da DigiCert. <br><br>"Um elemento de solicitação não é compreendido." | O Intune Certificate Connector não conseguiu obter o modelo de perfil de certificado da DigiCert, pois o OID do perfil de cliente não corresponde ao perfil de certificado do Intune. Em outra hipótese, o Intune Certificate Connector não consegue localizar o modelo de perfil de certificado associado ao OID do perfil de cliente na AC DigiCert. <br><br> Para resolver esse problema, obtenha o OID do perfil de cliente correto do modelo de certificado da DigiCert na AC DigiCert. Em seguida, atualize o perfil do certificado PKCS no portal de administração do Intune. <br><br> Obtenha o OID do perfil de cliente da AC DigiCert: <br> 1. Entre no portal de administração da AC DigiCert. <br> 2. Selecione **Gerenciar Perfis de Certificado**. <br> 3. Selecione o perfil de certificado que você deseja usar. <br> 4. Obtenha o OID do perfil de certificado. Ele é semelhante ao exemplo a seguir: <br> `Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109` <br><br> Atualize o perfil de certificado PKCS com o OID do perfil de certificado correto: <br>1. Entre no portal de administração do Intune. <br> 2. Vá para o Perfil de Certificado PKCS e selecione **Editar**. <br> 3. Atualize o OID do perfil de certificado na atualização no campo de nome do modelo de certificado. <br> 4. Salve o perfil de certificado PKCS. |
| Provedor da DigiCert – falha na verificação da política. <br><br> O atributo não se enquadra na lista de atributos do modelo de certificado com suporte pela DigiCert. | A AC DigiCert mostra esta mensagem quando há discrepância entre o modelo do perfil de certificado da DigiCert e o perfil de certificado do Intune. Esse problema provavelmente ocorreu devido à incompatibilidade do atributo em **SubjectName** ou **SubjectAltName**. <br><br> Para resolver esse problema, selecione os atributos com suporte pelo Intune para **SubjectName** e **SubjectAltName** no modelo de perfil de certificado da DigiCert. Para saber mais, confira os atributos com suporte do Intune na seção **Parâmetros de Certificado**. |
| Alguns dispositivos de usuário não estão recebendo certificados PKCS da AC DigiCert. | É um problema que ocorre quando o UPN do usuário contém caracteres especiais, como sublinhado (exemplo: `global_admin@intune.onmicrosoft.com`). <br><br> A AC da DigiCert não dá suporte a caracteres especiais em **mail_firstname** e **mail_lastname**. <br><br> As etapas a seguir ajudam a resolver esse problema: <br><br> 1. Entre no portal de administração da AC DigiCert. <br> 2. Vá para **Gerenciar Perfis de Certificado**. <br> 3. Clique no perfil de certificado usado para o Intune. <br> 4. Selecione o link **Personalizar opções**. <br> 5. Selecione o botão **Opções avançadas**. <br> 6. Em **Campos de certificado – DN do Assunto**, adicione um campo **CN (Nome Comum)** e exclua o campo **CN (Nome Comum)** existente. As operações de adição e exclusão devem ser executadas juntas. <br> 7. Selecione **Salvar**. <br><br> Com a alteração anterior, o perfil de certificado da DigiCert solicita **"CN =<upn>"** em vez de **mail_firstname** e **mail_lastname**. |
| Usuário excluído manualmente já implantou o certificado do dispositivo. | O Intune reimplanta o mesmo certificado durante o próximo check-in ou imposição da política. Nesse caso, o Conector de NDES não recebe uma solicitação de certificado PKCS. |

## <a name="next-steps"></a>Próximas etapas

Use as informações deste artigo, além das informações em [O que são perfis de dispositivo do Microsoft Intune?](../configuration/device-profiles.md) para gerenciar os dispositivos de sua organização e os certificados contidos neles.

