---
title: "Encapsular aplicativos iOS com Ferramenta de Disposição do Aplicativo | Microsoft Intune"
description: "Use as informações neste tópico para aprender a encapsular seus aplicativos iOS sem modificar o código do aplicativo em si. Prepare os aplicativos para que você possa aplicar políticas de gerenciamento de aplicativo móvel."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: matgates
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bebf57269ae41f04a47240063cde4a4dd0bf334f
ms.openlocfilehash: 3d9def8f906746cf6e3d014d251b94406d839067


---

# Preparar aplicativos iOS para gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune
Use a **Ferramenta de Encapsulamento de Aplicativos do Microsoft Intune para iOS** para modificar o comportamento de aplicativos iOS internamente restringindo as funcionalidades do aplicativo sem modificar seu código.

A ferramenta é um aplicativo de linha de comando do Mac OS que cria um "wrapper" em torno de um aplicativo. Após um aplicativo ser processado, você pode alterar sua funcionalidade usando [políticas de gerenciamento de aplicativo móvel](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) que você configurar.

Para baixar a ferramenta, consulte [Microsoft Intune App Wrapping Tool for iOS - Português (Brasil)](http://www.microsoft.com/en-us/download/details.aspx?id=45218).

## Etapa 1: Cumprir os pré-requisitos para usar a ferramenta de encapsulamento de aplicativos
Leia [esta postagem de blog](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) para saber mais sobre os pré-requisitos e como defini-los.

|Requisito|Mais informações|
|---------------|--------------------------------|
|Sistema operacional e conjunto de ferramentas com suporte|Você deve executar a ferramenta de encapsulamento de aplicativo em um computador Mac que execute o OS X 10.8.5 ou posterior e que tenha a versão 5 do conjunto de ferramentas XCode ou posterior instalada.|
|Certificado de autenticação e perfil de provisionamento|Você precisa ter um perfil de provisionamento e um certificado de autenticação da Apple. Consulte sua [Apple developer documentation (Documentação para desenvolvedores da Apple)](https://developer.apple.com/).|
|Processamento de um aplicativo com a Ferramenta de Encapsulamento de Aplicativo|Os aplicativos devem ser desenvolvidos e assinados por sua empresa ou por um ISV (fornecedor de software independente). Você não pode usar essa ferramenta para processar aplicativos da Apple Store. O aplicativo deve ser escrito para iOS 7.1 ou posterior. Aplicativos devem estar no formato PIE (Position Independent Executable). Para obter mais informações sobre o formato PIE, consulte sua documentação para desenvolvedor da Apple. O aplicativo deve ter a extensão de formato **.app**ou **.ipa**.|
|Aplicativos que a ferramenta de encapsulamento não pode processar|Aplicativos criptografados, não assinados e com atributos de arquivo estendido.|
|Aplicativos que usam a Informações para aplicativos que usam a ADAL (Biblioteca do Active Directory do Azure)|Se seu aplicativo usar ADAL, o aplicativo deverá incorporar uma versão da ADAL maior ou igual à 1.0.2 e o desenvolvedor deve conceder ao aplicativo acesso ao recurso de Gerenciamento de Aplicativos Móveis do Intune.<br /><br />Consulte as [Informações para aplicativos que usam a Biblioteca do Azure Active Directory](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#information-for-apps-that-use-the-azure-active-directory-library) neste artigo para ver mais detalhes sobre como usar o ADAL.|
|Direitos de configuração para seu aplicativo|Você deve definir direitos, que concedem ao aplicativo permissões adicionais e recursos além daqueles normalmente concedidos, antes de você encapsular o aplicativo. Consulte [Configurando direitos de aplicativo](#setting-app-entitlements) para obter instruções.|

## Etapa 2: Instalar a ferramenta de encapsulamento de aplicativos

1.  Na página da **Ferramenta de Encapsulamento de Aplicativos do Microsoft Intune para iOS** no [Centro de Download da Microsoft](https://www.microsoft.com/download/details.aspx?id=45218), baixe o arquivo de instalação da ferramenta de encapsulamento do aplicativo para um computador Mac.

2.  No computador Mac, clique duas vezes no arquivo de instalação **Microsoft Intune App Wrapping Tool for iOS.dmg**.

3.  Escolha em **Concordo** para aceitar o EULA (Contrato de licença de usuário final). O instalador é montado e exibido no computador Mac.

4.  Abra o instalador e copie os arquivos exibidos em uma nova pasta no computador. Agora, você pode desconectar a unidade montada do instalador.

    Agora, você está pronto para executar a ferramenta de encapsulamento de aplicativo.

## Etapa 3: Executar a ferramenta de encapsulamento de aplicativos

1.  No computador Mac, abra uma janela de Terminal e navegue até a pasta em que você salvou os arquivos. Como o executável fica dentro do pacote, você precisará executar o comando da seguinte maneira:
```
    ./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -a <client ID of input app> -r <reply URI of input app> -v true
```
    > [!NOTE]
    > Some parameters are optional as shown in the table below.

    **Example:** The following example command runs the app wrapping tool on an app named **MyApp.ipa**. A provisioning profile and SHA-1 hash are specified. The processed app is created and stored in the **/users/myadmin/Documents** on the Mac computer.

    ```
    /users/myadmin/Downloads/IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager -i /users/myadmin/Downloads/MyApp.ipa -o /users/myadmin/Documents/MyApp_Wrapped.ipa -p /users/myadmin/Downloads/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB –a 20e1cd0d-268e-4308-9583-02ae97dd353e –r https://contoso/ -v true
    ```
    You can use the following command line properties with the app wrapping tool:

|Propriedade|Mais informações|
  |------------|--------------------|
  |**-h**|Exibe as propriedades de linha de comando disponíveis para a ferramenta de encapsulamento de aplicativo.|
  |**-i**|Especifica o caminho e o nome do arquivo do aplicativo de entrada.|
  |**-o**|Especifica o caminho no qual salvar o aplicativo processado.|
  |**-p**|Especifica o caminho para o perfil de provisionamento para aplicativos iOS.|
  |**-c**|Especifica o hash SHA1 do certificado de autenticação.|
  |**-a**|ID do cliente do aplicativo de entrada (no formato GUID) se o aplicativo usar as Bibliotecas do Active Directory do Azure (opcional).|
  |**-r**|Redirecione o URI do aplicativo de entrada se o aplicativo usar as Bibliotecas do Active Directory do Azure (opcional).|
  |**-v**|Mensagens detalhadas de saída para o console (opcional).|

2. Após a conclusão do processamento, a mensagem **O aplicativo foi encapsulado com êxito** será exibida.

    Se ocorrer um erro, consulte [Mensagens de erro](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages) para obter ajuda.

3.  O aplicativo encapsulado é salvo na pasta de saída especificada anteriormente. Agora, você pode carregar o aplicativo no [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] e associá-lo a uma política de gerenciamento de aplicativos móveis.

    > [!IMPORTANT]
    > Você deve carregar o aplicativo como um novo aplicativo. Você não pode atualizar uma versão mais antiga, não encapsulada do aplicativo.

    Agora você pode implantar o aplicativo em seus grupos [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], e o aplicativo será executado no dispositivo usando as restrições de aplicativo que você especificar.

## Mensagens de erro e arquivos de log
Use as seguintes informações para solucionar problemas com a ferramenta de encapsulamento de aplicativo.

### Mensagens de erro
Se a ferramenta de encapsulamento de aplicativos não for concluída com êxito, uma das seguintes mensagens de erro será exibida:

|Mensagem de erro|Mais informações|
|-----------------|--------------------|
|Você deve especificar um perfil de provisionamento do iOS válido.|Seu perfil de provisionamento pode não ser válido. Verifique se você tem as permissões corretas para os dispositivos e se o seu perfil está voltado corretamente para o desenvolvimento ou distribuição. Seu perfil de provisionamento também pode estar expirado.|
|Especifique um nome de aplicativo de entrada válido.|Certifique-se de que o nome do aplicativo de entrada especificado está correto.|
|Especifique um caminho válido para o aplicativo de saída.|Certifique-se de que o caminho para o aplicativo de saída especificado existe e está correto.|
|Especifique um perfil de provisionamento de entrada válido.|Verifique se que você forneceu um nome e uma extensão de perfil de provisionamento válidos. Seu perfil de provisionamento pode ter direitos faltando ou você pode não ter incluído a opção de linha de comando **– p**.|
|O aplicativo de entrada especificado não foi encontrado. Especifique um nome de aplicativo de entrada e um caminho válido.|Verifique se o caminho do aplicativo de entrada é válido e existe. Verifique se que o aplicativo de entrada existe nesse local.|
|O arquivo de perfil de provisionamento de entrada especificado não foi encontrado. Especifique um arquivo de perfil de provisionamento de entrada válido.|Certifique-se de que o caminho para o arquivo de provisionamento de entrada é válido e de que o arquivo especificado existe.|
|A pasta do aplicativo de saída especificada não foi encontrada. Especifique um caminho válido para o aplicativo de saída.|Certifique-se de que o caminho de saída especificado é válido e existe.|
|O aplicativo de saída não tem a extensão .ipa.|Somente aplicativos com as extensões **.app** e **.ipa** são aceitos pelo a ferramenta de encapsulamento de aplicativo. Verifique se que o arquivo de saída tem uma extensão válida.|
|Um certificado de autenticação inválido foi especificado. Especifique um certificado de autenticação válido da Apple.|Verifique se que você baixou o certificado de autenticação correto do portal do desenvolvedor da Apple. O certificado também pode ter expirado. Se o seu perfil de provisionamento e certificado da Apple puderem ser usados para assinar corretamente um aplicativo no Xcode, eles são válidos para a ferramenta de encapsulamento de aplicativo.|
|O aplicativo de entrada especificado é inválido. Especifique um aplicativo válido.|Verifique se que você tem um aplicativo iOS válido que foi compilado como um arquivo .app ou .ipa.|
|O aplicativo de entrada especificado está criptografado. Especifique um aplicativo não criptografado válido.|A ferramenta de encapsulamento de aplicativo não dá suporte a aplicativos criptografados. Especifique um aplicativo sem criptografia.|
|O aplicativo de entrada especificado não está no formato PIE (Position Independent Executable). Especifique um aplicativo válido no formato PIE.|Aplicativos PIE (Position Independent Executable) podem ser carregados em um endereço de memória aleatório quando executados, o que pode ter benefícios de segurança. Para obter mais informações, consulte sua documentação para desenvolvedores da Apple.|
|O aplicativo de entrada especificado já foi encapsulado. Especifique um aplicativo não encapsulado válido.|Você não pode processar um aplicativo que já foi processado pela ferramenta. Se você quiser processar um aplicativo novamente, execute a ferramenta usando a versão original do aplicativo.|
|O aplicativo de entrada especificado não está assinado. Especifique um aplicativo assinado válido.|A ferramenta de encapsulamento de aplicativo requer que os aplicativos sejam assinados. Consulte a documentação do desenvolvedor para saber como assinar um aplicativo encapsulado.|
|O aplicativo de entrada especificado deve estar no formato .ipa ou .app.|Somente as extensões .app e .ipa são aceitas pela ferramenta de encapsulamento de aplicativo. Verifique se o arquivo de entrada tem uma extensão válida e foi compilado como um arquivo .app ou .ipa.|
|O aplicativo de entrada especificado já foi encapsulado e está na versão mais recente de modelo de política.|A ferramenta de encapsulamento de aplicativo não encapsula novamente aplicativo existente com a versão mais recente do modelo de política.|
|A ID de Cliente do Active Directory do Azure determinada não é um GUID bem formado. Especifique uma ID de cliente válida.|Ao usar o parâmetro de ID do Cliente, verifique se você forneceu uma ID de Cliente válida no formato GUID.|
|A URI de resposta do Active Directory do Azure determinada não é um URI bem formado. Especifique uma URI de resposta válida.|Ao usar a propriedade de linha de comando de URI de resposta, certifique-se de que você forneceu uma URI de resposta válida.|
|AVISO: você não especificou um hash de certificado SHA1. Certifique-se de que seu aplicativo encapsulado esteja assinado antes da implantação.|Verifique se você especificou um hash SHA (usando a propriedade de linha de comando **–c** ).|

### Arquivos de log para a ferramenta de encapsulamento de aplicativo
Aplicativos que foram encapsulados usando a ferramenta de encapsulamento de aplicativo geram logs que são gravados no console do dispositivo de cliente do iOS. Essas informações são úteis em situações em que você tiver problemas com o aplicativo e precisar diagnosticar se o problema está relacionado à ferramenta de encapsulamento de aplicativo. Para recuperar as informações, execute as seguintes etapas:

1.  Reproduza o problema executando o aplicativo.

2.  Colete a saída do console seguindo as instruções da Apple para [Depurar aplicativos iOS implantados](https://developer.apple.com/library/ios/qa/qa1747/_index.html).

3.  Filtre os logs salvos para ver a saída de Restrições de aplicativo inserindo o seguinte script no console:

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    Você pode enviar os logs filtrados para a Microsoft.

    > [!NOTE]
    > No arquivo de log, o item "build version" representa a versão da compilação do Xcode.

    Aplicativos de encapsulamento também apresentam aos usuários a opção de enviar logs diretamente do dispositivo por email após o aplicativo falhar. Os usuários podem enviar o log para você examinar e encaminhar à Microsoft, se necessário.

## Informações para aplicativos que usam a Biblioteca do Azure Active Directory
As informações nesta seção se aplicam somente aos aplicativos que usam a ADAL (Biblioteca do Active Directory do Azure). Se você não tiver certeza se seu aplicativo usa essa biblioteca, contate o desenvolvedor do aplicativo.

O aplicativo deve incorporar uma versão da ADAL maior que ou superior à 1.0.2.

Para aplicativos que usam a ADAL, as afirmações seguir devem ser verdadeiras:

-   O aplicativo deve incorporar uma versão da ADAL maior que ou superior à 1.0.2

-   Os desenvolvedores devem conceder acesso ao aplicativo para o recurso de Gerenciamento de aplicativo móvel do Intune, conforme descrito em [Etapas a seguir para aplicativos que usam a AD](#steps-to-follow-for-apps-that-use-adal).

### Visão geral dos identificadores que você precisa obter
Aplicativos que usam a ADAL devem ser registrados através do portal de gerenciamento do Azure para obter dois identificadores exclusivos para seu aplicativo:

|Identificador|Mais informações|Valor padrão|
|--------------|--------------------|-----------------|
|**ID do Cliente**|Um identificador GUID exclusivo é gerado para cada aplicativo após ele ser registrado com o Active Directory do Azure.<br /><br />Se souber a ID de cliente específica do aplicativo, você pode especificar esse valor. Caso contrário, o valor padrão deve ser usado.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**URI de redirecionamento**|Um valor de URI que os desenvolvedores podem fornecer ao registrar seu aplicativo no Active Directory do Azure para garantir os tokens de autenticação sejam retornados especificamente ao ponto de extremidade.<br /><br />Fornecer um URI de redirecionamento é um parâmetro opcional para a ferramenta de encapsulamento de aplicativo. Se não for especificado, um URI padrão será usado.|urn:ietf:wg:oauth:2.0:oob|


### Etapas a seguir para aplicativos que usam a ADAL

1.  Examine a [Visão geral dos identificadores que você precisa obter](#overview-of-identifiers-you-need-to-get) para identificar os valores que você precisa para começar.

2.  Configure o acesso ao gerenciamento de aplicativos móveis no Active Directory do Azure fazendo o seguinte:

    1. Faça logon em uma conta existente do Active Directory do Azure no portal de gerenciamento do Azure.

    2.  Clique em **registro de aplicativo de LOB existente** no Active Directory do Azure.

    3.  Na seção de configuração, escolha **Configurar o Acesso às APIs da Web em outros aplicativos**.

    4.  Na seção **Permission to other applications (Permissão para outros aplicativos)**, na primeira lista suspensa, escolha **Gerenciamento de aplicativo móvel do Intune**.

        Agora você pode usar a ID do Cliente do aplicativo na ferramenta de disposição do aplicativo. Você pode encontrar a ID do Cliente do aplicativo no portal de gerenciamento do Azure Active Directory conforme descrito na seção [Visão geral dos identificadores que você precisa obter](#overview-of-identifiers-you-need-to-get).

3.  Use os valores de **Client-ID** (usando a propriedade **–a**) e **Redirect-URI** como propriedades de linha de comando na ferramenta de encapsulamento de aplicativo. Se você não tiver esses valores, os valores padrão são usados. Você deve especificar os dois valores ou o usuário final não poderá autenticar o aplicativo processado com êxito.

### Requisitos de autenticação, perfil de provisionamento e certificado

|Requisito|Detalhes|
|---------------|-----------|
|Perfil de provisionamento|**Certifique-se de que o perfil de provisionamento é válido antes de incluí-lo** - A ferramenta de encapsulamento do aplicativo não verifica se o perfil de provisionamento expirou durante o processamento de um aplicativo iOS. Se um perfil de provisionamento expirado for especificado, a ferramenta de encapsulamento do aplicativo incluirá o perfil de provisionamento expirado e você não saberá que há um problema até que o aplicativo não possa ser instalado em um dispositivo iOS.|
|Certificate|**Certifique-se de que o certificado é válido antes de especificá-lo** - A ferramenta não verifica se um certificado expirou durante o processamento de aplicativos iOS. Se o hash de um certificado expirado for fornecido, a ferramenta processará e assinará o aplicativo, mas ele não será instalado em dispositivos.<br /><br />**Certifique-se de que o certificado fornecido para assinar o aplicativo empacotado tenha uma correspondência no perfil de provisionamento** - A ferramenta não é validada se o perfil de provisionamento tiver uma correspondência para o certificado fornecido para assinar o aplicativo encapsulado.|
|Autenticação|Um dispositivo deve ter um PIN definido para criptografia funcionar. Em dispositivos nos quais você implantou um aplicativo encapsulado, tocar a barra de status no dispositivo exige que o usuário autentique novamente no [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. A política padrão em um aplicativo encapsulado é *autenticação na nova inicialização*. O iOS lida qualquer notificação externa (por exemplo, uma chamada telefônica) como saindo do aplicativo e então reiniciando-o.<br /><br />Para aplicativos encapsulados, o primeiro usuário que assina qualquer aplicativo encapsulado do mesmo editor é armazenado em cache. Depois disso, somente esse usuário tem permissão para acessar o aplicativo. Para redefinir o usuário, o dispositivo deve ter o registro cancelado e, em seguida, ser registrado novamente.|

### Notas técnicas e solução de problemas sobre a ADAL

-   Se nenhum recurso da ADAL for encontrado, a ferramenta incluirá a biblioteca dinâmica da ADAL. A ferramenta pesquisará a biblioteca da ADAL com o nome **ADALiOS.bundle** na pasta raiz.

-   A ferramenta não pesquisará binários da ADAL (se houver) no aplicativo. Se o aplicativo se conectar a uma versão desatualizada, pode haver erros de tempo de execução durante o logon se as políticas de autenticação estiverem habilitadas.

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] busca o token do AAD para a ID de recurso do MAM do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] para autenticação. No entanto, não é usado em qualquer chamada que, por sua vez, verificaria a validade do token. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] apenas lê o UPN do usuário conectado para determinar o acesso do aplicativo. O token do AAD não é usado para outras chamadas de serviço.

-   Tokens de autenticação são compartilhados entre aplicativos do mesmo editor, pois eles são armazenados no conjunto de chaves compartilhado. Se quiser isolar um aplicativo específico, você deve usar um certificado de autenticação e um perfil de provisionamento diferente para esse aplicativo.

-   Prompts de logon duplo são impedidos se você fornecer a Id de cliente e o URI de redirecionamento do aplicativo cliente. Essa ID de cliente precisa ser registrada para acessar a ID do recurso de MAM [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] publicado no painel do AAD. Deixar de fazer isso resultará em uma falha de logon quando o aplicativo for executado.

## Definindo direitos de aplicativo
Antes de encapsular seu aplicativo, você pode conceder **direitos** para conceder ao aplicativo permissões e recursos adicionais que excedem o que um aplicativo normalmente pode fazer.  Um **arquivo de direito** é usado durante a assinatura de código para especificar permissões especiais dentro de seu aplicativo (por exemplo, acesso a um conjunto de chaves compartilhado). Serviços de aplicativos específicos, chamados **funcionalidades**, são habilitados em Xcode durante o desenvolvimento do aplicativo. Uma vez habilitadas, as funcionalidades são refletidas no arquivo de direitos. Para obter mais informações sobre os recursos e funcionalidades, consulte [Adicionando Funcionalidades](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) na Biblioteca do Desenvolvedor iOS. Para obter uma lista completa de funcionalidades com suporte, consulte [Supported capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html) (Funcionalidades com suporte).

### Funcionalidades com suporte para a Ferramenta de Encapsulamento de Aplicativos para iOS

|Funcionalidade|Descrição|Diretrizes recomendadas|
|--------------|---------------|------------------------|
|Grupos de aplicativo|Use grupos de aplicativos para permitir que vários aplicativos acessem contêineres compartilhados e permitir comunicação entre processos adicional entre aplicativos.<br /><br />Para habilitar grupos de aplicativos, abra o painel **Funcionalidades** e clique no botão **LIGAR** na seção **Grupos de Aplicativos**. Você pode adicionar grupos de aplicativos ou selecionar grupos existentes.|Ao usar Grupos de aplicativos, use a notação inversa de DNS:<br /><br />*group.com.companyName.AppGroup*|
|Modos de tela de fundo|Habilitar modos de segundo plano permite que seu aplicativo iOS continue em execução em segundo plano.||
|Proteção de dados|A proteção de dados adiciona um nível de segurança para arquivos armazenados em disco por seu aplicativo iOS. A proteção de dados usa o hardware de criptografia interna presente em dispositivos específicos para armazenar arquivos em um formato criptografado no disco. Seu aplicativo precisa ser provisionado para usar a proteção de dados.||
|Compras no aplicativo|As Compras no aplicativo incorporam uma loja diretamente ao seu aplicativo, permitindo que você se conecte à loja e processe com segurança pagamentos do usuário. Você pode usar a Compra no aplicativo para coletar pagamentos por uma funcionalidade avançada ou conteúdo adicional usado pelo seu aplicativo.||
|Compartilhamento de conjunto de chaves|Habilitar o compartilhamento de conjunto de chaves permite que seu aplicativo compartilhe senhas do conjunto de chaves com outros aplicativos desenvolvidos pela sua equipe.|Ao usar o Compartilhamento de conjunto de chaves, use a notação inversa de DNS:<br /><br />*com.companyName.KeychainGroup*|
|VPN pessoal|Habilite VPN pessoal para permitir que seu aplicativo crie e controle uma configuração de VPN personalizada do sistema usando a estrutura de extensão de rede.||
|Notificações por push|O APNs (Apple Push Notification Service) permite que um aplicativo que não está em execução em primeiro plano notifique o usuário de que ele tem informações para o usuário.|Para que as notificações por push funcionem, você precisa usar um perfil de provisionamento específico ao aplicativo.<br /><br />Siga as etapas na [Apple developer documentation](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) (Documentação para desenvolvedores da Apple).|
|Configuração de acessório sem fio|Habilitar a configuração de acessório sem fio adiciona a estrutura External Accessory ao seu projeto e permite que seu aplicativo configure acessórios MFi Wi-Fi.||

### Etapas para habilitar direitos

1.  Habilite as funcionalidades em seu aplicativo:

    1.  No Xcode, navegue até o destino do aplicativo e clique no painel **Funcionalidades**.

    2.  Habilite as funcionalidades apropriadas. Para obter informações detalhadas sobre cada funcionalidade e como determinar os valores corretos, consulte [Adicionando Funcionalidades](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) na Biblioteca do Desenvolvedor iOS.

    3.  Tome nota de quaisquer IDs que você criar durante o processo.

    4.  Compile e assine seu aplicativo a ser encapsulado.

2.  Habilite os direitos no seu perfil de provisionamento:

    1.  Faça logon na Central de Associados do Desenvolvedor da Apple.

    2.  Crie um perfil de provisionamento para seu aplicativo. Para obter instruções, consulte [How to Obtain the Prerequisites for the Intune App Wrapping Tool for iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) (Como obter os pré-requisitos para a Ferramenta de Disposição do Aplicativo do Intune para iOS).

    3.  No seu perfil de provisionamento, habilite os mesmo direitos que você tem em seu aplicativo. Você precisará fornecer as mesmas IDs que especificou durante o desenvolvimento do seu aplicativo.

    4.  Conclua o assistente de perfil de provisionamento e baixe o arquivo.

3.  Certifique-se de que foram satisfeitos todos os pré-requisitos e encapsule o aplicativo.

### Solucionando erros comuns com direitos
Se a Ferramenta de Encapsulamento de Aplicativos para iOS exibir um erro de direito, tente as seguintes etapas de solução de problemas.

|Problema|Causa|Resolução|
|---------|---------|--------------|
|Falha ao analisar direitos gerados do aplicativo de entrada.|A Ferramenta de Encapsulamento de Aplicativos não pode ler o arquivo de direitos que foi extraído do aplicativo. O arquivo de direitos pode estar malformado.|Inspecione o arquivo de direitos de seu aplicativo. Para fazer isso, siga as instruções detalhadas abaixo. Ao inspecionar o arquivo de direitos, verifique se há qualquer sintaxe malformada. O arquivo deve estar no formato XML.|
|Direitos estão ausentes no perfil de provisionamento (direitos ausentes são listados). Empacote novamente o aplicativo com um perfil de provisionamento que tenha esses direitos.|Há uma incompatibilidade entre os direitos habilitados no perfil de provisionamento e os recursos habilitados no aplicativo. Essa incompatibilidade também se aplica às IDs associadas a recursos específicos (por exemplo, grupos de aplicativos, conjunto de chaves acesso etc).|Em geral, você pode criar um novo perfil de provisionamento que habilita os mesmos recursos que o aplicativo. Quando as IDs entre o perfil e o aplicativo não coincidirem, a Ferramenta de Encapsulamento de Aplicativos substituirá as IDs se conseguir fazer isso. Se você ainda receber esse erro depois de criar um novo perfil de provisionamento, você poderá tentar remover direitos do aplicativo usando o parâmetro **–e** (consulte a seção "Usando o parâmetro –e para remover direitos do aplicativo” abaixo).|

### Localizando os direitos existentes de um aplicativo assinado
Para examinar as autorizações existentes de um aplicativo assinado e do perfil de provisionamento:

1.  Localize o arquivo .ipa, altere a extensão para .zip.

2.  Expanda o arquivo .zip. Isso produzirá uma pasta de Carga que contém o pacote .app.

3.  Use a ferramenta codesign para verificar os direitos sobre o pacote .app, como este:

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```
    em que `YourApp.app` é o nome real do seu pacote .app.

4.  Use a ferramenta de segurança para verificar os direitos do perfil de provisionamento incorporado do aplicativo:

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```
    em que `YourApp.app` é o nome real do seu pacote .app.

### Usando o parâmetro –e para remover direitos de um aplicativo
Este comando remove quaisquer funcionalidades habilitadas no aplicativo que não estão no arquivo de direitos. Se você remover as funcionalidades que estão sendo usadas pelo aplicativo, elas poderão interromper seu aplicativo. Um exemplo de onde você poderá remover funcionalidades ausentes é se você tiver um aplicativo produzido pelo fornecedor que tem todas as funcionalidades por padrão.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## Segurança e privacidade da ferramenta de encapsulamento de aplicativo
Use as seguintes práticas recomendadas de segurança e privacidade ao usar a ferramenta de encapsulamento de aplicativo.

-   O certificado de autenticação, perfil de provisionamento e o aplicativo de linha de negócios que você especificar devem estar no mesmo computador Mac que você usar para executar a ferramenta de encapsulamento de aplicativo. Se os arquivos estiverem em um caminho UNC, certifique-se de que eles são acessíveis no computador Mac. O caminho deve ser protegido por assinatura SMB ou IPsec.

    O aplicativo encapsulado importado no console [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] deve estar no mesmo computador no qual você executa a ferramenta. Se os arquivos estiverem em um caminho UNC, certifique-se de que eles são acessíveis no computador que executa o console [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. O caminho deve ser protegido por assinatura SMB ou IPsec.

-   O ambiente em que a ferramenta de encapsulamento de aplicativo é baixada do site Centro de Download da Microsoft precisa ser protegido por assinatura SMB ou IPsec.

-   O aplicativo que você processar deve vir de uma fonte confiável para garantir a proteção contra ataques.

-   Certifique-se de que a pasta de saída que você especificar na ferramenta de encapsulamento de aplicativo esteja protegida, principalmente se ela for uma pasta remota.

-   Aplicativos iOS que incluem uma caixa de diálogo de carregamento de arquivos podem permitir que usuários contornem restrições de recortar, copiar e colar aplicadas ao aplicativo. Por exemplo, um usuário poderia usar a caixa de diálogo de carregamento de arquivo para carregar uma captura de tela dos dados do aplicativo.

-   Quando os usuários monitoram a pasta documentos em seu dispositivo de dentro de um aplicativo encapsulado, eles podem ver uma pasta chamada **.msftintuneapplauncher**. Se essa pasta for alterada ou excluída, isso pode afetar o funcionamento correto dos aplicativos restritos.

### Consulte também
- [Decidir como preparar aplicativos para o gerenciamento de aplicativos móveis com o Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [Use o SDK para habilitar aplicativos para o gerenciamento de aplicativos móveis](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Aug16_HO1-->


