---
title: "Encapsular aplicativos iOS com Ferramenta de Disposição do Aplicativo | Microsoft Intune"
description: "Use as informações neste tópico para aprender a encapsular seus aplicativos iOS sem modificar o código do aplicativo em si. Prepare os aplicativos para que você possa aplicar políticas de gerenciamento de aplicativo móvel."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c67a5042fd177a4c5bd897092e84281db0977f5e
ms.openlocfilehash: 2c187b61b8fe25b2870d0cbc62f8352494583fc2


---

# Preparar aplicativos iOS para gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune
Use a **Ferramenta de Encapsulamento de Aplicativos do Microsoft Intune para iOS** para modificar o comportamento de aplicativos iOS internamente restringindo as funcionalidades do aplicativo sem modificar seu código.

A ferramenta é um aplicativo de linha de comando do Mac OS que cria um "wrapper" em torno de um aplicativo. Depois que um aplicativo for processado, você poderá alterar sua funcionalidade usando as [políticas de gerenciamento de aplicativo móvel](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) do Intune que você configurar.

Para baixar a ferramenta, consulte [Microsoft Intune App Wrapping Tool for iOS - Português (Brasil)](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios).



## Etapa 1. Cumprir os pré-requisitos para usar a ferramenta de encapsulamento de aplicativo
Leia [esta postagem de blog](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) para saber mais sobre os pré-requisitos e como defini-los.

|Requisito|Mais informações|
|---------------|--------------------------------|
|Sistema operacional e conjunto de ferramentas com suporte|Você deve executar a ferramenta de disposição de aplicativo em um computador macOS que execute o OS X 10.8.5 ou posterior e que tenha a versão 5 do conjunto de ferramentas XCode ou posterior instalada.|
|Certificado de autenticação e perfil de provisionamento|Você precisa ter um perfil de provisionamento e um certificado de autenticação da Apple. Consulte sua [Apple developer documentation (Documentação para desenvolvedores da Apple)](https://developer.apple.com/).|
|Processamento de um aplicativo com a Ferramenta de Encapsulamento de Aplicativo|Os aplicativos devem ser desenvolvidos e assinados por sua empresa ou por um ISV (fornecedor de software independente). Você não pode usar essa ferramenta para processar aplicativos da Apple Store. O aplicativo deve ser escrito para iOS 8.0 ou posterior. Aplicativos devem estar no formato PIE (Position Independent Executable). Para obter mais informações sobre o formato PIE, consulte sua documentação para desenvolvedor da Apple. O aplicativo deve ter a extensão de formato **.app**ou **.ipa**.|
|Aplicativos que a ferramenta de encapsulamento não pode processar|Aplicativos criptografados, não assinados e com atributos de arquivo estendido.|
|Direitos de configuração para seu aplicativo|Você deve definir direitos, que concedem ao aplicativo permissões adicionais e recursos além daqueles normalmente concedidos, antes de você encapsular o aplicativo. Consulte [Configurando direitos de aplicativo](#setting-app-entitlements) para obter instruções.|

## Etapa 2. Instalar a ferramenta de encapsulamento de aplicativos

1.  Do **repositório hospedado em GitHub** da [ferramenta de encapsulamento de aplicativo do Microsoft Intune para iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios), baixe os arquivos localmente para a ferramenta de encapsulamento de aplicativo em um computador macOS.

2.  Clique duas vezes no arquivo de instalação **Microsoft Intune App Wrapping Tool for iOS.dmg**. Será exibida uma janela com o EULA (Contrato de Licença de Usuário Final). Leia o documento atentamente.

3. Escolha **Concordo** para aceitar o EULA, que monta o pacote em seu computador.

4.  Abra o pacote **IntuneMAMPackager** e salve os arquivos em uma pasta local no computador macOS. Agora, você está pronto para executar a ferramenta de encapsulamento de aplicativo.

## Etapa 3. Executar a ferramenta de encapsulamento de aplicativo
* No computador macOS, abra uma janela de Terminal e navegue até a pasta em que você salvou os arquivos da ferramenta de encapsulamento de aplicativo. A ferramenta executável se chama **IntuneMAMPackager** e está localizada em **IntuneMAMPackager/conteúdo/MacOS**. Você precisará executar o comando da seguinte maneira:

    ```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]

    ```

    > [!NOTE]
    > Alguns parâmetros são opcionais, conforme mostrado na tabela a seguir.

    **Exemplo:** o comando de exemplo a seguir executa a ferramenta de encapsulamento de aplicativo em um aplicativo chamado **MyApp.ipa**. Um perfil de provisionamento e o hash SHA-1 são especificados. O aplicativo processado é criado, nomeado como **MyApp_Wrapped.ipa** e armazenado na pasta da Área de Trabalho do usuário.

    ```
    ./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB  -v true
    ```
    Você pode usar as seguintes propriedades de linha de comando com a ferramenta de encapsulamento de aplicativo:

    |Propriedade|Como usá-lo|
  |------------|--------------------|
  |**-i**|`<Path of the input native iOS application file>`. O arquivo deve terminar em .app ou .ipa. |
  |**-o**|`<Path of the wrapped output application>` |
  |**-p**|`<Path of your provisioning profile for iOS apps>`|
  |**-c**|`<SHA1 hash of the signing certificate>`|
    |-h|Exibe as informações de uso detalhadas das propriedades de linha de comando disponíveis para a ferramenta de encapsulamento de aplicativo.|
  |-v|(Opcional, mas útil) Produz mensagens detalhadas no console.|
  |-e | (Opcional) O uso desse sinalizador com a ferramenta de encapsulamento de aplicativo remove direitos ausentes conforme ele processa o aplicativo. Confira a seção "Definindo direitos de aplicativo" para obter mais detalhes.|
  |-xe| (Opcional) Imprime informações sobre as extensões do iOS no aplicativo e quais direitos são necessários para usá-los. Confira a seção "Definindo direitos de aplicativo" para obter mais detalhes. |
  |-x| (Opcional) `<An array of paths to extension provisioning profiles>`. Use esta opção se seu aplicativo precisar de perfis de provisionamento de extensão.|
  |-f |(Opcional) `<Path to a plist file specifying arguments.>` Use este sinalizador na frente do arquivo [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) se você optar por usar o modelo plist para especificar o restante das propriedades IntuneMAMPackager: -i, -s, -p, etc. Confira a seção "Usar um plist para argumentos de entrada" para obter mais detalhes. |
  |-b|(Opcional) Use -b sem um argumento se você quiser que o aplicativo de saída encapsulado tenha a mesma versão do pacote que o aplicativo de entrada (não recomendado). <br/><br/> Use `-b <custom bundle version>` se você quiser que o aplicativo encapsulado tenha um CFBundleVersion personalizado. Se você optar por especificar um CFBundleVersion personalizado, recomendamos que incremente o CFBundleVersion do aplicativo nativo pelo componente menos significativo, por exemplo, 1.0.0 -> 1.0.1. |


###Use um plist para argumentos de entrada
Uma maneira fácil de executar a ferramenta de disposição de aplicativo é colocar todos os argumentos de comando em um arquivo [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html). Plist é um formato de arquivo semelhante ao XML que podemos usar para os argumentos de linha de comando usando uma interface de formulário de entrada.

Na pasta **IntuneMAMPackager/Contents/MacOS**, abra `Parameters.plist`, um modelo plist em branco, com um editor de texto ou Xcode. Insira seus argumentos para as chaves a seguir:

| Chave plist |  Valor padrão| Anotações |
|------------------|--------------|-----|
| Caminho do pacote de aplicativos de entrada  |vazio| Mesmo que -i. |
| Caminho do pacote de aplicativos de saída |vazio| Mesmo que -o.|
| Caminho do perfil de provisionamento |vazio| Mesmo que -p. |
| Hash de certificado SHA-1 |vazio| Mesmo que -c. |
| Modo detalhado habilitado |false| Mesmo que -v. |
| Remover direitos ausentes | false| Mesmo que -c.|
| Impedir o build padrão |false | Equivalente a usar -b sem argumentos. |
|Compilar substituição da cadeia de caracteres | vazio| O CFBundleVersion personalizado do aplicativo de saída encapsulado |
|Caminhos do perfil de provisionamento de extensão | vazio| Uma matriz de perfis de provisionamento de extensão para o aplicativo.
  

Por fim, execute o IntuneMAMPackager com o plist como o único argumento:

```
./IntuneMAMPackager –f Parameters.plist
```

* Após a conclusão do processamento, a mensagem “**O aplicativo foi encapsulado com êxito**” será exibida.

    Se ocorrer um erro, consulte [Mensagens de erro](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages) para obter ajuda.

*   O aplicativo encapsulado é salvo na pasta de saída especificada anteriormente. Agora, você pode carregar o aplicativo no [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] e associá-lo a uma política de gerenciamento de aplicativos móveis.

    > [!IMPORTANT]
    > Ao carregar um aplicativo encapsulado, você poderá tentar atualizar uma versão mais antiga do aplicativo se uma versão mais antiga (encapsulada ou nativa) já tiver sido implantada no Intune. Se houver um erro, carregue o aplicativo como um novo aplicativo e exclua a versão mais antiga.

    Agora você pode implantar o aplicativo em seus grupos [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], e o aplicativo será executado no dispositivo usando as restrições de aplicativo que você especificar.

## Mensagens de erro e arquivos de log
Use as seguintes informações para solucionar problemas com a ferramenta de encapsulamento de aplicativo.

### Mensagens de erro
Se a ferramenta de disposição de aplicativos não for concluída com êxito, uma das seguintes mensagens de erro será exibida no console:

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
|Um certificado de autenticação inválido foi especificado. Especifique um certificado de autenticação válido da Apple.|Verifique se que você baixou o certificado de autenticação correto do portal do desenvolvedor da Apple. Seu certificado pode ter expirado ou talvez não tenha uma chave pública ou privada. Se o seu perfil de provisionamento e certificado da Apple puderem ser usados para assinar corretamente um aplicativo no Xcode, eles são válidos para a ferramenta de encapsulamento de aplicativo.|
|O aplicativo de entrada especificado é inválido. Especifique um aplicativo válido.|Verifique se que você tem um aplicativo iOS válido que foi compilado como um arquivo .app ou .ipa.|
|O aplicativo de entrada especificado está criptografado. Especifique um aplicativo não criptografado válido.|A ferramenta de encapsulamento de aplicativo não dá suporte a aplicativos criptografados. Forneça um aplicativo sem criptografia.|
|O aplicativo de entrada especificado não está no formato PIE (Position Independent Executable). Especifique um aplicativo válido no formato PIE.|Aplicativos PIE (Position Independent Executable) podem ser carregados em um endereço de memória aleatório quando executados, o que pode ter benefícios de segurança. Para obter mais informações, consulte sua documentação para desenvolvedores da Apple.|
|O aplicativo de entrada especificado já foi encapsulado. Especifique um aplicativo não encapsulado válido.|Você não pode processar um aplicativo que já foi processado pela ferramenta. Se você quiser processar um aplicativo novamente, execute a ferramenta usando a versão original do aplicativo.|
|O aplicativo de entrada especificado não está assinado. Especifique um aplicativo assinado válido.|A ferramenta de encapsulamento de aplicativo requer que os aplicativos sejam assinados. Consulte a documentação do desenvolvedor para saber como assinar um aplicativo encapsulado.|
|O aplicativo de entrada especificado deve estar no formato .ipa ou .app.|Somente as extensões .app e .ipa são aceitas pela ferramenta de encapsulamento de aplicativo. Verifique se o arquivo de entrada tem uma extensão válida e foi compilado como um arquivo .app ou .ipa.|
|O aplicativo de entrada especificado já foi encapsulado e está na versão mais recente de modelo de política.|A ferramenta de encapsulamento de aplicativo não encapsula novamente aplicativo existente com a versão mais recente do modelo de política.|
|AVISO: você não especificou um hash de certificado SHA1. Certifique-se de que seu aplicativo encapsulado esteja assinado antes da implantação.|Verifique se você especificou um hash SHA1 válido seguindo a propriedade de linha de comando **–c**. |

### Arquivos de log para a ferramenta de encapsulamento de aplicativo
Aplicativos que foram encapsulados usando a ferramenta de encapsulamento de aplicativo geram logs que são gravados no console do dispositivo de cliente do iOS. Essas informações são úteis quando você tiver problemas com o aplicativo e precisar diagnosticar se o problema está relacionado à ferramenta de encapsulamento de aplicativo. Para recuperar as informações, execute as seguintes etapas:

1.  Reproduza o problema executando o aplicativo.

2.  Colete a saída do console seguindo as instruções da Apple para [Depurar aplicativos iOS implantados](https://developer.apple.com/library/ios/qa/qa1747/_index.html).

3.  Filtre os logs salvos para ver a saída de Restrições de aplicativo inserindo o seguinte script no console:

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    Você pode enviar os logs filtrados para a Microsoft.

    > [!NOTE]
    > No arquivo de log, o item "build version" representa a versão da compilação do Xcode.

    Aplicativos de encapsulamento também apresentam aos usuários a opção de enviar logs diretamente do dispositivo por email após o aplicativo falhar. Os usuários podem enviar os logs para você examinar e encaminhar à Microsoft, se necessário.


### Requisitos de autenticação, perfil de provisionamento e certificado

A ferramenta de encapsulamento de aplicativo tem alguns requisitos que devem ser cumpridos para assegurar a funcionalidade completa.

|Requisito|Detalhes|
|---------------|-----------|
|Perfil de provisionamento|**Verifique se o perfil de provisionamento é válido antes de incluí-lo**. A ferramenta de encapsulamento de aplicativo não verifica se o perfil de provisionamento expirou durante o processamento de um aplicativo iOS. Se um perfil de provisionamento expirado for especificado, a ferramenta de encapsulamento do aplicativo incluirá o perfil de provisionamento expirado e você não saberá que há um problema até que o aplicativo não possa ser instalado em um dispositivo iOS.|
|Certificate|**Verifique se certificado é válido antes de especificá-lo**. A ferramenta não verifica se um certificado expirou durante o processamento de aplicativos iOS. Se o hash de um certificado expirado for fornecido, a ferramenta processará e assinará o aplicativo, mas ele não será instalado em dispositivos.<br /><br />**Verifique se o certificado fornecido para assinar o aplicativo empacotado tem uma correspondência no perfil de provisionamento**. A ferramenta não valida se o perfil de provisionamento tiver uma correspondência para o certificado fornecido para assinar o aplicativo encapsulado.|
|Autenticação|Um dispositivo deve ter um PIN definido para a criptografia funcionar. Em dispositivos nos quais você implantou um aplicativo encapsulado, tocar a barra de status no dispositivo exige que o usuário autentique novamente no [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. A política padrão em um aplicativo encapsulado é *autenticação na nova inicialização*. O iOS lida com qualquer notificação externa (por exemplo, uma chamada telefônica) ao encerrar o aplicativo e, em seguida, iniciando-o novamente.


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

-   O certificado de autenticação, o perfil de provisionamento e o aplicativo de linha de negócios que você especificar devem estar no mesmo computador macOS que você usar para executar a ferramenta de encapsulamento de aplicativo. Se os arquivos estiverem em um caminho UNC, verifique se eles são acessíveis no computador macOS. O caminho deve ser protegido por assinatura SMB ou IPsec.

    O aplicativo encapsulado importado no console [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] deve estar no mesmo computador no qual você executa a ferramenta. Se os arquivos estiverem em um caminho UNC, certifique-se de que eles são acessíveis no computador que executa o console [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. O caminho deve ser protegido por assinatura SMB ou IPsec.

-   O ambiente em que a ferramenta de encapsulamento de aplicativo é baixada do repositório GitHub precisa ser protegido por assinatura IPsec ou SMB.

-   O aplicativo que você processar deve vir de uma fonte confiável para garantir a proteção contra ataques.

-   Certifique-se de que a pasta de saída que você especificar na ferramenta de encapsulamento de aplicativo esteja protegida, principalmente se ela for uma pasta remota.

-   Aplicativos iOS que incluem uma caixa de diálogo de upload de arquivos podem permitir que os usuários contornem restrições de recortar, copiar e colar aplicadas ao aplicativo. Por exemplo, um usuário poderia usar a caixa de diálogo de carregamento de arquivo para carregar uma captura de tela dos dados do aplicativo.

-   Quando os usuários monitoram a pasta documentos em seu dispositivo de dentro de um aplicativo encapsulado, eles podem ver uma pasta chamada **.msftintuneapplauncher**. Se essa pasta for alterada ou excluída, isso pode afetar o funcionamento correto dos aplicativos restritos.

### Consulte também
- [Decidir como preparar aplicativos para o gerenciamento de aplicativos móveis com o Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [Use o SDK para habilitar aplicativos para o gerenciamento de aplicativos móveis](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Oct16_HO2-->


