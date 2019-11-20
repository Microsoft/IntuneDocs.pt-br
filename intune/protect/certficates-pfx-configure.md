---
title: Usar certificados de chave pública e privada no Microsoft Intune – Azure | Microsoft Docs
description: Usar certificados PKCS (Public Key Cryptography Standards) com o Microsoft Intune. Isso inclui trabalhar com certificados raiz e modelos de certificado, instalar o NDES (Conector de Certificado do Intune) e os perfis de configuração de dispositivo para um Certificado PKCS.
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
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3db085e6e88f8f57eb0276afa77290df8574568f
ms.sourcegitcommit: b5e719fb507b1bc4774674e76c856c435e69f68c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2019
ms.locfileid: "73801682"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Configurar e usar certificados PKCS com o Intune

O Intune dá suporte ao uso de certificados de par de chaves privadas e públicas (PCKS). Este artigo pode ajudá-lo a configurar a infraestrutura necessária, como conectores de certificado locais, exportar um certificado PKCS e, em seguida, adicioná-lo a um perfil de configuração do dispositivo do Intune.

O Microsoft Intune inclui configurações internas de uso de certificados PKCS para acesso e autenticação nos recursos de sua organização. Os certificados autenticam e protegem o acesso aos recursos corporativos como uma VPN ou uma rede WiFi. Implante essas configurações em dispositivos usando perfis de configuração do dispositivo no Intune.

Para obter informações sobre como usar certificados PKCS importados, confira [Certificados PFX Importados](certificates-imported-pfx-configure.md).


## <a name="requirements"></a>Requisitos

Para usar certificados PKCS com o Intune, será necessária a seguinte infraestrutura:

- **Domínio do Active Directory**:  
  Todos os servidores listados nesta seção precisam ser ingressados no domínio do Active Directory.

  Para saber mais sobre como instalar e configurar o AD DS (Active Directory Domain Services), confira [Planejamento e Design do AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Autoridade de certificação**:  
   uma AC (autoridade de certificação corporativa).

  Para saber mais sobre como instalar e configurar o AD CS (Serviços de Certificados do Active Directory), confira [Guia passo a passo dos Serviços de Certificados do Active Directory](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]  
  > O Intune exige que você execute o AD CS com uma AC (Autoridade de Certificação) Corporativa, não com uma AC Autônoma.

- **Um cliente**:  
  para se conectar à AC corporativa.

- **Certificado raiz**:  
  Uma cópia exportada de seu certificado raiz de sua AC Corporativa.

- O **Microsoft Intune Certificate Connector** (também chamado de *Certificate Connector NDES*):  
  No portal do Intune, acesse **Configuração do dispositivo** > **Conectores do Certificado** > **Adicionar** e siga as *Etapas para instalar o conector para PKCS n º 12*. Use o link de download no portal para começar o download do instalador do conector do certificado **NDESConnectorSetup.exe**.  

  O Intune dá suporte a até 100 instâncias deste conector por locatário. Cada instância do conector precisa estar em um servidor do Windows separado. Você pode instalar uma instância desse conector no mesmo servidor de uma instância do Certificate Connector PFX do Microsoft Intune. Quando você usa vários conectores, a infraestrutura do conector tem suporte para alta disponibilidade e balanceamento de carga, já que qualquer instância de conector disponível pode processar suas solicitações de certificado PKCS. 

  Esse conector processa solicitações de certificado PCKS usadas para autenticação ou assinatura de email S/MIME.

  O Microsoft Intune Certificate Connector também é compatível com o modo do padrão FIPS. O FIPS não é necessário, mas você poderá emitir e revogar certificados quando estiver habilitado.

- **Conector do Certificado PFX do Microsoft Intune**:  
  se você planeja usar a criptografia de email S/MIME, use o portal do Intune para baixar o *Conector de Certificado PFX* que dá suporte à importação de certificados PFX.  Acesse **Configuração do dispositivo** > **Conectores do Certificado** > **Adicionar** e siga as *Etapas para instalar o conector para Certificados PFX importados*. Use o link de download no portal para começar o download do instalador **PfxCertificateConnectorBootstrapper.exe**. 

  Cada locatário do Intune tem suporte para uma única instância desse conector. É possível instalar esse conector no mesmo servidor de uma instância do Microsoft Intune Certificate Connector.

  Este conector manipula as solicitações para arquivos PFX importados para o Intune para criptografia de email S/MIME de um usuário específico.  

  Este conector poderá atualizar-se automaticamente quando novas versões forem disponibilizadas. Para usar a funcionalidade de atualização, faça é necessário:
  - Instalar o Conector de Certificado PFX do Microsoft Intune em seu servidor.  
  - Para receber automaticamente atualizações importantes, verifique se os firewalls estão abertos que permitem que o conector contate **autoupdate.msappproxy.net** na porta **443**.   

  Para obter mais informações sobre todos os pontos de extremidade de rede que o Intune e o conector acessam, confira [Pontos de extremidade de rede do Microsoft Intune](../fundamentals/intune-endpoints.md).

- **Windows Server**:  
  use um Windows Server para hospedar:

  - Microsoft Intune Certificate Connector – para cenários de autenticação e assinatura de email S/MIME
  - Conector do Certificado PFX do Microsoft Intune – para cenários de criptografia de email S/MIME.

  O Intune dá suporte para a instalação do *Conector de Certificado PFX* no mesmo servidor do *Microsoft Intune Certificate Connector*.
  
## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Exportar o certificado raiz da AC Corporativa

Para autenticar um dispositivo com VPN, WiFi ou outros recursos, um dispositivo precisa de um certificado de Autoridade de Certificação raiz ou intermediário. As etapas a seguir explicam como obter o certificado necessário de sua AC Corporativa.

**Usar uma linha de comando**:  
1. faça logon no servidor da Autoridade de Certificação Raiz com a Conta Administrador.
 
2. Acesse **Iniciar** > **Executar** e, em seguida, insira **Cmd** para abrir o prompt de comando. 
    
3. Especifique **certutil -ca.cert ca_name.cer** para exportar o certificado raiz como um arquivo chamado *ca_name.cer*.



## <a name="configure-certificate-templates-on-the-ca"></a>Configurar modelos de certificado na AC

1. Entre na sua AC corporativa com uma conta que tenha privilégios administrativos.
2. Abra o console da **Autoridade de Certificação**, clicar com o botão direito do mouse em **Modelos de Certificado** e selecione **Gerenciar**.
3. Localize o modelo de certificado do **Usuário**, clique nele com o botão direito do mouse e escolha **Duplicar Modelo** para abrir as **Propriedades do Novo Modelo**.

    > [!NOTE]
    > Para os cenários de autenticação e criptografia de email S/MIME, muitos administradores usam certificados separados para autenticação e criptografia. Caso esteja usando os Serviços de Certificados do Microsoft Active Directory, use o modelo **Trocar Somente Assinatura** para certificados de autenticação de email S/MIME e o modelo **Trocar Usuário** para certificados de criptografia S/MIME.  Caso esteja usando uma autoridade de certificação de terceiros, é recomendável examinar suas diretrizes para configurar modelos de autenticação e de criptografia.

4. Na guia **Compatibilidade**:

    - Defina **Autoridade de Certificação** como **Windows Server 2008 R2**
    - Defina **Destinatário do certificado** como **Windows 7/Server 2008 R2**

5. Na guia **Geral**, defina **Nome de exibição do modelo** como algo significativo para você.

    > [!WARNING]
    > **Nome do modelo** é, por padrão, o mesmo que o **Nome de exibição do modelo** *sem espaços*. Observe o nome do modelo, pois ele será necessário mais tarde.

6. Em **Tratamento de Solicitação**, selecione **Permitir que a chave privada seja exportada**.
7. Em **Criptografia**, confirme se o **Tamanho mínimo da chave** está definido como 2048.
8. Em **Nome da Entidade**, escolha **Fornecer na solicitação**.
9. Em **Extensões**, confirme a existência de Encrypting File System, Email Seguro e Autenticação de Cliente em **Políticas de Aplicativo**.

    > [!IMPORTANT]
    > Para modelos de certificado do iOS, na guia **Extensões**, atualize **Uso da Chave** e confirme se a opção **A assinatura é uma prova de origem** não está selecionada.

10. Em **Segurança**, adicione a Conta de Computador do servidor de instalação do Microsoft Intune Certificate Connector. Atribua as permissões **Leitura** e **Inscrição** à essa conta.
11. Selecione **Aplicar** > **OK** para salvar o modelo de certificado. Feche o **Console de Modelos de Certificado**.
12. No console da **Autoridade de Certificação**, clique com o botão direito em **Modelos de Certificados** > **Novo** > **Modelo de certificado a ser emitido**. Escolha o modelo que você criou nas etapas anteriores. Selecione **OK**.
13. Para que o servidor gerencie certificados de usuários e dispositivos registrados, use as seguintes etapas:

    1. Clique com o botão direito na Autoridade de Certificação e escolha **Propriedades**.
    2. Na guia Segurança, adicione a conta de Computador do servidor em que você executa os conectores (**Microsoft Intune Certificate Connector** ou **Conector do Certificado PFX do Microsoft Intune**). 
    3. Conceda as permissões **Emitir e Gerenciar Certificados** e **Solicitar Certificados** à conta de computador.

14. Saia da AC corporativa.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Baixar, instalar e configurar o Microsoft Intune Certificate Connector

> [!IMPORTANT]  
> O Microsoft Intune Certificate Connector não pode ser instalado na AC (Autoridade de Certificação) emissora; em vez disso, deve ser instalado em um servidor Windows separado.  

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Administração de locatários** > **Conectores e tokens** > **Conectores de certificado** >  **+ Adicionar**.

3. Clique em *Baixar o software do conector de certificado* do conector para PKCS 12 e salve o arquivo em um local que possa ser acessado no servidor em que o conector será instalado.

   ![Baixar o Microsoft Intune Certificate Connector](./media/certficates-pfx-configure/download-ndes-connector.png)
 
4. Após a conclusão do download, entre no servidor. Em seguida:

    1. Verifique se o .NET 4.5 Framework ou superior está instalado, pois ele é necessário para o conector do Certificado NDES. O .NET 4.5 Framework é automaticamente incluído no Windows Server 2012 R2 e versões mais recentes.
    2. Execute o instalador (NDESConnectorSetup.exe) e aceite a localização padrão. Ele instala o conector para `\Program Files\Microsoft Intune\NDESConnectorUI`. Nas Opções do Instalador, selecione **Distribuição de PFX**. Continue e conclua a instalação.
    3. Por padrão, o serviço do conector é executado na conta Sistema Local. Se for necessário usar um proxy para acessar a Internet, confirme se a conta de serviço local pode acessar as configurações de proxy no servidor.

5. O Microsoft Intune Certificate Connector abre a guia **Registro**. Para habilitar a conexão com o Intune, selecione **Entrar** e insira uma conta com permissões administrativas globais.
6. Na guia **Avançado**, recomenda-se deixar a opção **Usar a conta SISTEMA deste computador (padrão)** selecionada.
7. **Aplicar** > **Fechar**
8. Retorne para o portal do Intune (**Intune** > **Configuração do Dispositivo** > **Conectores de Certificação**). Depois de alguns minutos, uma marca de seleção verde é exibida e o **Status da conexão** fica **Ativo**. O servidor do conector agora pode se comunicar com o Intune.
9. Se você tiver um proxy da Web em seu ambiente de rede, talvez seja necessário configurações adicionais para habilitar o funcionamento do conector. Para obter mais informações, consulte [Trabalhar com servidores de proxy locais existentes](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) na documentação do Azure Active Directory.

> [!NOTE]  
> O Microsoft Intune Certificate Connector é compatível com o TLS 1.2. Se o TLS 1.2 estiver instalado no servidor que hospeda o conector, este usará o TLS 1.2. Caso contrário, o TLS 1.1 será usado. Atualmente, o TLS 1.1 é usado para autenticação entre os dispositivos e o servidor.

## <a name="create-a-trusted-certificate-profile"></a>Criar um perfil de certificado confiável

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.

   ![Navegue até o Intune e crie um perfil para um certificado confiável](./media/certficates-pfx-configure/certificates-pfx-configure-profile-new.png)

3. Insira as seguintes propriedades:

    - **Nome** do perfil
    - Opcionalmente, defina uma descrição
    - **Plataforma** na qual implantar o perfil
    - Defina o **Tipo de perfil** como **Certificado confiável**

4. Selecione **Configurações** e especifique o arquivo .cer do Certificado de Autoridade de Certificação Raiz exportado anteriormente.

   > [!NOTE]
   > Dependendo da plataforma escolhida na **Etapa 2**, você poderá ou não ter a opção de escolher o **Armazenamento de destino** do certificado.

   ![Criar um perfil e carregar um certificado confiável](./media/certficates-pfx-configure/certificates-pfx-configure-profile-fill.png)

5. Selecione **OK** > **Criar** para salvar seu perfil.

6. Para atribuir o novo perfil a um ou mais dispositivos, confira [Atribuir perfis de dispositivo do Microsoft Intune](../configuration/device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Criar um perfil de certificado PKCS

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione e vá a **Dispositivos** > **Perfis de configuração** > **Criar perfil**.

3. Insira as seguintes propriedades:

    - **Nome** do perfil
    - Opcionalmente, defina uma descrição
    - **Plataforma** na qual implantar o perfil
    - Defina o **Tipo de perfil** como **Certificado PKCS**

4. Selecione **Configurações** e defina as propriedades que se aplicam à plataforma selecionada:
   
   |Setting     | Plataforma     | Detalhes   |
   |------------|------------|------------|
   |**Limite de renovação (%)**        |Tudo         |O recomendado é 20%  | 
   |**Período de validade do certificado**  |Tudo         |Se você não alterou o modelo de certificado, essa opção pode ser definida como um ano. |
   |**KSP (provedor de armazenamento de chaves)**   |Windows 10  | Para o Windows, selecione o local em que as chaves serão armazenadas no dispositivo. |
   |**Autoridade de certificação**      |Tudo         |Exibe o FQDN (nome de domínio totalmente qualificado) interno da AC corporativa.  |
   |**Nome da autoridade de certificação** |Tudo         |Lista o nome da AC corporativa, como "Autoridade de Certificação da Contoso". |
   |**Tipo de certificado**             |macOS       |Selecione um tipo: <br> **-** Os certificados de **Usuário** podem conter atributos de usuário e de dispositivo na entidade e no SAN do certificado. <br><br>**-** Os certificados de **Dispositivo** podem conter somente os atributos do dispositivo na entidade e no SAN do certificado. Use Dispositivo para cenários como dispositivos sem usuário, como quiosques, ou para dispositivos compartilhados.  <br><br> Essa seleção afeta o formato do nome da entidade. |
   |**Formato de nome de entidade**          |Tudo         |Para a maioria das plataformas, defina essa opção como **Nome comum**, a menos que seja exigido o contrário.<br><br>Para macOS, o formato de nome da entidade é determinado pelo tipo de certificado. Confira [Formato de nome da entidade para macOS](#subject-name-format-for-macos) mais adiante neste artigo. |
   |**Nome alternativo da entidade**     |Tudo         |Defina essa opção como **Nome UPN**, a menos que seja exigido o contrário. |
   |**Uso estendido de chave**           |**-** Administrador do dispositivo Android <br>**-** Android Enterprise (*Proprietário do Dispositivo*, *Perfil de Trabalho*) <br> **-** Windows 10 |Normalmente, os certificados exigirão *Autenticação de cliente* para que o usuário ou dispositivo possa autenticar-se em um servidor. |
   |**Permitir que todos os aplicativos acessem a chave privada** |macOS  |Configure como **Habilitar** para dar aos aplicativos configurados para o dispositivo Mac associado acesso à chave privada dos certificados PKCS. <br><br> Para obter mais informações sobre essa configuração, confira *AllowAllAppsAccess* na seção de Conteúdo do Certificado da [Referência do Perfil de Configuração](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf) na documentação do desenvolvedor da Apple. |
   |**Certificado raiz**             |**-** Administrador do dispositivo Android <br> **-** Android Enterprise (*Proprietário do Dispositivo*, *Perfil de Trabalho*) |Selecione um perfil de Certificado de Autoridade de Certificação raiz ‘que foi atribuído anteriormente. |

5. Selecione **OK** > **Criar** para salvar seu perfil.

6. Para atribuir o novo perfil a um ou mais dispositivos, confira [Atribuir perfis de dispositivo do Microsoft Intune](../configuration/device-profile-assign.md).

   > [!NOTE]
   > Em dispositivos com um perfil do Android Enterprise, os certificados instalados por meio de um perfil de certificado PKCS não ficam visíveis no dispositivo. Para confirmar se o certificado foi implantado com êxito, verifique o status do perfil no console do Microsoft Intune.

### <a name="subject-name-format-for-macos"></a>Formato de nome de entidade para macOS

Quando você cria um perfil de certificado PKCS do macOS, as opções para o formato de nome da entidade dependem do Tipo de certificado selecionado, **Usuário** ou **Dispositivo**.  

> [!NOTE]  
> Há um problema conhecido no uso do PKCS para obter certificados, [que é o mesmo problema observado no uso do SCEP](certificates-profile-scep.md#avoid-certificate-signing-requests-with-escaped-special-characters), quando o nome da entidade na CSR (Solicitação de Assinatura de Certificado) resultante inclui um dos seguintes caracteres como um caractere de escape (seguido por uma barra invertida \\):
> - \+
> - ;
> - ,
> - =

- **Tipo de certificado de usuário**  
  As opções de formato para o *Formato de nome da entidade* incluem duas variáveis: **Nome Comum (NC)** e **Email (E)** . **CN (Nome Comum)** pode ser definido para qualquer uma das seguintes variáveis:

  - **CN={{UserName}}** : O nome UPN do usuário, como janedoe@contoso.com.
  - **CN={{AAD_Device_ID}}** : Uma ID atribuída ao registrar um dispositivo no Azure AD (Active Directory). Essa ID normalmente é usada para autenticar com o Azure AD.
  - **CN={{SERIALNUMBER}}** : O SN (número de série) exclusivo normalmente usado pelo fabricante para identificar um dispositivo.
  - **CN={{IMEINumber}}** : O número exclusivo do IMEI (Identidade Internacional de Equipamento Móvel) usado para identificar um celular.
  - **CN={{OnPrem_Distinguished_Name}}** : Uma sequência de nomes diferenciados relativos separados por vírgula, como *CN=Leila Dias,OU=UserAccounts,DC=corp,DC=contoso,DC=com*.

    Para usar a variável *{{OnPrem_Distinguished_Name}}* , sincronize o atributo de usuário *onpremisesdistinguishedname* com o Azure AD usando o [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

  - **CN={{onPremisesSamAccountName}}** : Os administradores podem sincronizar o atributo samAccountName do Active Directory para o Azure AD usando o Azure AD Connect em um atributo chamado *onPremisesSamAccountName*. O Intune pode substituir essa variável como parte de uma solicitação de emissão de certificados na entidade de um certificado. O atributo samAccountName é o nome de entrada do usuário usado para dar suporte a clientes e servidores de uma versão anterior do Windows (pré-Windows 2000). O formato do nome de entrada do usuário é: *DomainName\testUser* ou apenas *testUser*.

    Para usar a variável *{{onPremisesSamAccountName}}* , sincronize o atributo de usuário *onPremisesSamAccountName* com o Azure AD usando o [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

  Usando uma combinação de uma ou mais dessas variáveis e cadeias de caracteres estáticas, é possível criar um formato de nome de entidade personalizado, como:  
  - **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**
  
  Este exemplo inclui um formato de nome de entidade que usa as variáveis CN e E e cadeias de caracteres para os valores Unidade Organizacional, Organização, Localização, Estado e País. [Função CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) descreve essa função e suas cadeias de caracteres compatíveis.

- **Tipo de certificado de dispositivo**  
  As opções de formato para o Formato de nome da entidade incluem as seguintes variáveis: 
  - **{{AAD_Device_ID}}**
  - **{{Device_Serial}}**
  - **{{Device_IMEI}}**
  - **{{SerialNumber}}**
  - **{{IMEINumber}}**
  - **{{AzureADDeviceId}}**
  - **{{WiFiMacAddress}}**
  - **{{IMEI}}**
  - **{{DeviceName}}**
  - **{{FullyQualifiedDomainName}}** *(Aplicável somente aos dispositivos Windows e ingressados no domínio)*
  - **{{MEID}}**

  Especifique essas variáveis, seguidas pelo texto da variável, na caixa de texto. Por exemplo, o nome comum para um dispositivo chamado *Device1* pode ser adicionado como **CN={{DeviceName}}Device1**.

  > [!IMPORTANT]  
  > - Ao especificar uma variável, coloque o nome da variável entre chaves { }, como mostrado no exemplo, para evitar um erro.  
  > - As propriedades do dispositivo usadas na *entidade* ou no *SAN* de um certificado de dispositivo, como **IMEI**, **SerialNumber** e **FullyQualifiedDomainName**, são propriedades que podem ser falsificadas por uma pessoa com acesso ao dispositivo.
  > - Um dispositivo precisa dar suporte a todas as variáveis especificadas em um perfil de certificado para que esse perfil seja instalado nesse dispositivo.  Por exemplo, se **{{IMEI}}** for usado no nome da entidade de um perfil SCEP e for atribuído a um dispositivo que não tenha um número IMEI, o perfil não será instalado.  
 


## <a name="whats-new-for-connectors"></a>Novidades nos Conectores

São lançadas periodicamente atualizações para os dois conectores de certificado. Quando atualizamos um conector, é possível ler sobre as mudanças aqui.

O *Conector de Certificados PFX do Microsoft Intune* [dá suporte a atualizações automáticas](#requirements), enquanto o *Intune Certificate Connector* é atualizado manualmente.

### <a name="may-17-2019"></a>17 de maio de 2019

- **Conector do Certificado PFX do Microsoft Intune – versão 6.1905.0.404**  
  Alterações nessa versão:  
  - Correção de um problema em que os certificados PFX existentes continuam a ser reprocessados, o que faz com que o conector pare de processar novas solicitações. 

### <a name="may-6-2019"></a>6 de maio de 2019

- **Conector do Certificado PFX do Microsoft Intune – versão 6.1905.0.402**  
  Alterações nessa versão:  
  - O intervalo de sondagem para o conector é reduzido de 5 minutos para 30 segundos.
 
### <a name="april-2-2019"></a>2 de abril de 2019

- **Conector do certificado Intune – versão 6.1904.1.0**  
  Alterações nessa versão:  
  - correção de um problema em que o conector poderia não conseguir se registrar no Intune após se conectar ao conector com uma conta de administrador global.  
  - Inclui correções de confiabilidade para revogação de certificado.  
  - Inclui correções de desempenho para aumentar a rapidez com que as solicitações de certificados PKCS são processadas.  

- **Conector do Certificado PFX do Microsoft Intune – versão 6.1904.0.401**
  > [!NOTE]  
  > A atualização automática para essa versão do conector PFX não estará disponível até 11 de abril de 2019.  

  Alterações nessa versão:  
  - correção de um problema em que o conector poderia não conseguir se registrar no Intune após se conectar ao conector com uma conta de administrador global.  


## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](../configuration/device-profile-assign.md) e [monitore seu status](../configuration/device-profile-monitor.md).

[Use o SCEP para certificados](certificates-scep-configure.md) ou [emita Certificados PKCS por meio de um serviço Web do Symantec PKI Manager](certificates-digicert-configure.md).
