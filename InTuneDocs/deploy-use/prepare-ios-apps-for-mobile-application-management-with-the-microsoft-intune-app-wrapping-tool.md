---
title: "Encapsular aplicativos iOS com a Ferramenta de Disposição do Aplicativo do Intune | Microsoft Intune"
description: "Use as informações neste tópico para aprender a encapsular seus aplicativos iOS sem alterar o código do aplicativo em si. Prepare os aplicativos para que você possa aplicar políticas de gerenciamento de aplicativo móvel."
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
ms.sourcegitcommit: ba4ace8106e83f3579cbaf98dcea8ef240a202a9
ms.openlocfilehash: d150c97197e11d4a81727dca5ddd8eb1310aa193


---

# <a name="prepare-ios-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>Preparar aplicativos iOS para gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune

Use a Ferramenta de Disposição do Aplicativo do Microsoft Intune para iOS para alterar o comportamento de aplicativos iOS internamente ao habilitar os recursos de proteção do aplicativo do Intune sem alterar o código do aplicativo.

A ferramenta é um aplicativo de linha de comando do macOS que cria um wrapper em torno de um aplicativo. Depois que um aplicativo for processado, você poderá alterar sua funcionalidade usando as [políticas de gerenciamento de aplicativo móvel](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) do Intune implantadas pelo administrador de TI.

Para baixar a ferramenta, consulte [Ferramenta de Disposição do Aplicativo do Microsoft Intune para iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) no GitHub.



## <a name="fulfill-the-prerequisites-for-the-app-wrapping-tool"></a>Cumprir os pré-requisitos da Ferramenta de Disposição do Aplicativo
Consulte a postagem de blog [Como obter os pré-requisitos para a Ferramenta de Disposição do Aplicativo do Intune para iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) para saber mais sobre como obter os pré-requisitos.

|Requisito|Mais informações|
|---------------|--------------------------------|
|Sistema operacional e conjunto de ferramentas com suporte | Você precisa executar a Ferramenta de Disposição do Aplicativo em um computador macOS que executa o OS X 10.8.5 ou posterior e que tem a versão 5 do conjunto de ferramentas XCode ou posterior instalada.|
|Certificado de autenticação e perfil de provisionamento | Você precisa ter um perfil de provisionamento e um certificado de autenticação da Apple. Consulte sua [Apple developer documentation (Documentação para desenvolvedores da Apple)](https://developer.apple.com/).|
|Processamento de um aplicativo com a Ferramenta de Encapsulamento de Aplicativo  |Os aplicativos devem ser desenvolvidos e assinados por sua empresa ou por um ISV (fornecedor independente de software). Você não pode usar essa ferramenta para processar aplicativos da Apple Store. O aplicativo deve ser escrito para iOS 8.0 ou posterior. Aplicativos devem estar no formato PIE (Position Independent Executable). Para obter mais informações sobre o formato PIE, consulte a documentação para desenvolvedor da Apple. Por fim, a aplicativo deve ter a extensão **.app**ou **.ipa**.|
|Aplicativos que a ferramenta não pode processar | Aplicativos criptografados, não assinados e com atributos de arquivo estendido.|
|Direitos de configuração para seu aplicativo|Antes de encapsular o aplicativo, você precisa definir direitos, que concedem ao aplicativo permissões e recursos adicionais além daqueles concedidos normalmente. Consulte [Configurando direitos de aplicativo](#setting-app-entitlements) para obter instruções.|

## <a name="install-the-app-wrapping-tool"></a>Instalar a ferramenta de encapsulamento de aplicativos

1.  Baixe os arquivos para a Ferramenta de Disposição do Aplicativo no [GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) para um computador macOS.

2.  Clique duas vezes em **Ferramenta de Disposição do Aplicativo do Microsoft Intune para iOS.dmg**. Será exibida uma janela com o EULA (Contrato de Licença de Usuário Final). Leia o documento atentamente.

3. Escolha **Concordo** para aceitar o EULA, que monta o pacote em seu computador.

4.  Abra a pasta **IntuneMAMPackager** e salve seu conteúdo em seu computador macOS. Agora, você está pronto para executar a Ferramenta de Disposição do Aplicativo.

## <a name="run-the-app-wrapping-tool"></a>Executar a ferramenta de encapsulamento de aplicativos

### <a name="use-terminal"></a>Usar terminal

Abra o programa de Terminal do macOS e navegue até a pasta na qual salvou os arquivos da ferramenta de disposição de aplicativo. A ferramenta executável se chama IntuneMAMPackager e está localizada em IntuneMAMPackager/Conteúdo/MacOS. Execute o comando da seguinte forma:

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]
```

> [!NOTE]
> Alguns parâmetros são opcionais, conforme mostrado na tabela a seguir.

**Exemplo:** o comando de exemplo a seguir executa a Ferramenta de Disposição de Aplicativo em um aplicativo chamado MyApp.ipa. Um perfil de provisionamento e o hash SHA-1 do certificado de autenticação especificado são usados para assinar o aplicativo encapsulado. O aplicativo de saída (MyApp_Wrapped.ipa) é criado e armazenado na sua pasta da Área de Trabalho.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB  -v true
```

### <a name="command-line-parameters"></a>Parâmetros da linha de comando
Você pode usar os seguintes parâmetros de linha de comando com a Ferramenta de Disposição do Aplicativo:

|Propriedade|Como usá-lo|
|---------------|--------------------------------|
|**-i**|`<Path of the input native iOS application file>`. O nome do arquivo deve terminar em .app ou .ipa. |
|**-o**|`<Path of the wrapped output application>` |
|**-p**|`<Path of your provisioning profile for iOS apps>`|
|**-c**|`<SHA1 hash of the signing certificate>`|
|**-h**|Exibe informações de uso detalhadas das propriedades de linha de comando disponíveis para a Ferramenta de Disposição do Aplicativo.|
|**-v**|(Opcional) Produz mensagens detalhadas no console.|
|**-e**| (Opcional) Use esse sinalizador para que a Ferramenta de Disposição do Aplicativo remova direitos ausentes conforme processa o aplicativo. Consulte Configurando direitos de aplicativo para obter detalhes.|
|**-xe**| (Opcional) Imprime informações sobre as extensões do iOS no aplicativo e quais direitos são necessários para usá-las. Consulte Configurando direitos de aplicativo para obter detalhes. |
|**-x**| (Opcional) `<An array of paths to extension provisioning profiles>`. Use esta opção se seu aplicativo precisar de perfis de provisionamento de extensão.|
|**-f**|(Opcional) `<Path to a plist file specifying arguments.>` Use este sinalizador na frente do arquivo [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) se você optar por usar o modelo plist para especificar o restante das propriedades IntuneMAMPackager, como -i, -o e -p. Consulte Usar um plist para argumentos de entrada. |
|**-b**|(Opcional) Use -b sem um argumento se você quiser que o aplicativo de saída encapsulado tenha a mesma versão do pacote que o aplicativo de entrada (não recomendado). <br/><br/> Use `-b <custom bundle version>` se você quiser que o aplicativo encapsulado tenha um CFBundleVersion personalizado. Se você optar por especificar um CFBundleVersion personalizado, recomendamos incrementar o CFBundleVersion do aplicativo nativo pelo componente menos significativo, como 1.0.0 -> 1.0.1. |

### <a name="use-a-plist-to-input-arguments"></a>Use um plist para argumentos de entrada
Uma maneira fácil de executar a ferramenta de disposição de aplicativo é colocar todos os argumentos de comando em um arquivo [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html). Plist é um formato de arquivo semelhante ao XML que você pode usar para inserir os argumentos de linha de comando usando uma interface de formulário.

Na pasta IntuneMAMPackager/Conteúdo/MacOS, abra `Parameters.plist` (um modelo plist em branco) com um editor de texto ou Xcode. Insira seus argumentos para as chaves a seguir:

| Chave plist |  Valor padrão| Observações |
|------------------|--------------|-----|
| Caminho do pacote de aplicativos de entrada  |vazio| Mesmo que -i|
| Caminho do pacote de aplicativos de saída |vazio| Mesmo que -o|
| Caminho do perfil de provisionamento |vazio| Mesmo que -p|
| Hash de certificado SHA-1 |vazio| Mesmo que -c|
| Modo detalhado habilitado |false| Mesmo que -v|
| Remover direitos ausentes | false| Mesmo que -c|
| Impedir o build padrão |false | Equivalente a usar -b sem argumentos|
|Compilar substituição da cadeia de caracteres | vazio| O CFBundleVersion personalizado do aplicativo de saída encapsulado |
|Caminhos do perfil de provisionamento de extensão | vazio| Uma matriz de perfis de provisionamento de extensão para o aplicativo.


Execute o IntuneMAMPackager com plist como o único argumento:

```bash
./IntuneMAMPackager –f Parameters.plist
```

### <a name="post-wrapping"></a>Após a disposição

Após a conclusão do processamento de disposição, a mensagem “O aplicativo foi encapsulado com êxito” será exibida. Se ocorrer um erro, consulte [Mensagens de erro](#error-messages-and-log-files) para obter ajuda.

O aplicativo encapsulado é salvo na pasta de saída especificada anteriormente. Você pode carregar o aplicativo no console de administração do Intune e associá-lo a uma política de gerenciamento de aplicativo móvel.

> [!IMPORTANT]
> Ao carregar um aplicativo encapsulado, você poderá tentar atualizar uma versão mais antiga do aplicativo se uma versão mais antiga (encapsulada ou nativa) já tiver sido implantada no Intune. Se houver um erro, carregue o aplicativo como um novo aplicativo e exclua a versão mais antiga.

Agora você pode implantar o aplicativo em seus grupos de usuários e as políticas de proteção de aplicativo de destino no aplicativo. O aplicativo será executado no dispositivo usando as políticas de proteção de aplicativo que você especificar.

## <a name="error-messages-and-log-files"></a>Mensagens de erro e arquivos de log
Use as seguintes informações para solucionar problemas com a ferramenta de encapsulamento de aplicativo.

### <a name="error-messages"></a>Mensagens de erro
Se a ferramenta de disposição do aplicativo não for concluída com êxito, uma das seguintes mensagens de erro será exibida no console:

|Mensagem de erro|Mais informações|
|-----------------|--------------------|
|Você deve especificar um perfil de provisionamento do iOS válido.|Seu perfil de provisionamento pode não ser válido. Verifique se você tem as permissões corretas para os dispositivos e se o seu perfil está direcionado corretamente para desenvolvimento ou distribuição. Seu perfil de provisionamento também pode estar expirado.|
|Especifique um nome de aplicativo de entrada válido.|Certifique-se de que o nome do aplicativo de entrada especificado está correto.|
|Especifique um caminho válido para o aplicativo de saída.|Certifique-se de que o caminho para o aplicativo de saída especificado existe e está correto.|
|Especifique um perfil de provisionamento de entrada válido.|Verifique se que você forneceu um nome e uma extensão de perfil de provisionamento válidos. Podem estar faltando direitos no seu perfil de provisionamento ou você pode não ter incluído a opção de linha de comando –p.|
|O aplicativo de entrada especificado não foi encontrado. Especifique um nome de aplicativo de entrada e um caminho válido.|Verifique se o caminho do aplicativo de entrada é válido e existe. Verifique se que o aplicativo de entrada existe nesse local.|
|O arquivo de perfil de provisionamento de entrada especificado não foi encontrado. Especifique um arquivo de perfil de provisionamento de entrada válido.|Certifique-se de que o caminho para o arquivo de provisionamento de entrada é válido e de que o arquivo especificado existe.|
|A pasta do aplicativo de saída especificada não foi encontrada. Especifique um caminho válido para o aplicativo de saída.|Certifique-se de que o caminho de saída especificado é válido e existe.|
|O aplicativo de saída não tem a extensão **.ipa**.|Somente aplicativos com as extensões **.app** e **.ipa** são aceitos pela Ferramenta de Disposição do Aplicativo. Verifique se que o arquivo de saída tem uma extensão válida.|
|Um certificado de autenticação inválido foi especificado. Especifique um certificado de autenticação válido da Apple.|Verifique se que você baixou o certificado de autenticação correto do portal do desenvolvedor da Apple. Seu certificado pode ter expirado ou talvez não tenha uma chave pública ou privada. Se o seu perfil de provisionamento e certificado da Apple puderem ser usados para assinar corretamente um aplicativo no Xcode, eles são válidos para a Ferramenta de Disposição do Aplicativo.|
|O aplicativo de entrada especificado é inválido. Especifique um aplicativo válido.|Verifique se que você tem um aplicativo iOS válido que foi compilado como um arquivo .app ou .ipa.|
|O aplicativo de entrada especificado está criptografado. Especifique um aplicativo não criptografado válido.|A Ferramenta de Disposição do Aplicativo não dá suporte a aplicativos criptografados. Forneça um aplicativo sem criptografia.|
|O aplicativo de entrada especificado não está no formato PIE (Position Independent Executable). Especifique um aplicativo válido no formato PIE.|Aplicativos PIE (Position Independent Executable) podem ser carregados em um endereço de memória aleatório quando executados. Isso pode ter benefícios de segurança. Para obter mais informações sobre os benefícios de segurança, consulte a documentação para desenvolvedor da Apple.|
|O aplicativo de entrada especificado já foi encapsulado. Especifique um aplicativo não encapsulado válido.|Você não pode processar um aplicativo que já foi processado pela ferramenta. Se você quiser processar um aplicativo novamente, execute a ferramenta usando a versão original do aplicativo.|
|O aplicativo de entrada especificado não está assinado. Especifique um aplicativo assinado válido.|A ferramenta de encapsulamento de aplicativo requer que os aplicativos sejam assinados. Consulte a documentação do desenvolvedor para saber como assinar um aplicativo encapsulado.|
|O aplicativo de entrada especificado deve estar no formato .ipa ou .app.|Somente as extensões .app e .ipa são aceitas pela ferramenta de encapsulamento de aplicativo. Verifique se o arquivo de entrada tem uma extensão válida e foi compilado como um arquivo .app ou .ipa.|
|O aplicativo de entrada especificado já foi encapsulado e está na versão mais recente de modelo de política.|A Ferramenta de Disposição do Aplicativo não encapsula novamente um aplicativo encapsulado existente com a versão mais recente do modelo de política.|
|AVISO: você não especificou um hash de certificado SHA1. Certifique-se de que seu aplicativo encapsulado esteja assinado antes da implantação.|Especifique um hash SHA1 válido seguindo o sinalizador de linha de comando –c. |

### <a name="log-files-for-the-app-wrapping-tool"></a>Arquivos de log para a Ferramenta de Disposição do Aplicativo
Aplicativos que foram encapsulados usando a Ferramenta de Disposição do Aplicativo geram logs que são gravados no console do dispositivo de cliente do iOS. Essas informações são úteis quando você tem problemas com o aplicativo e precisa determinar se o problema está relacionado à Ferramenta de Disposição do Aplicativo. Para recuperar as informações, execute as seguintes etapas:

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


### <a name="certificate-provisioning-profile-and-authentication-requirements"></a>Requisitos de autenticação, perfil de provisionamento e certificado

A Ferramenta de Disposição do Aplicativo para iOS tem alguns requisitos que precisam ser atendidos para assegurar a funcionalidade completa.

|Requisito|Detalhes|
|---------------|-----------|
|Perfil de provisionamento do iOS|Verifique se o perfil de provisionamento é válido antes de incluí-lo. A Ferramenta de Disposição do Aplicativo não verifica se o perfil de provisionamento expirou durante o processamento de um aplicativo iOS. Se um perfil de provisionamento expirado for especificado, a ferramenta de encapsulamento do aplicativo incluirá o perfil de provisionamento expirado e você não saberá que há um problema até que o aplicativo não possa ser instalado em um dispositivo iOS.|
|Certificado de autenticação do iOS|Verifique se o certificado de autenticação é válido antes de especificá-lo. A ferramenta não verifica se um certificado expirou durante o processamento de aplicativos iOS. Se o hash de um certificado expirado for fornecido, a ferramenta processará e assinará o aplicativo, mas ele não será instalado em dispositivos.<br /><br />Verifique se o certificado fornecido para assinar o aplicativo encapsulado tem uma correspondência no perfil de provisionamento. A ferramenta não valida se o perfil de provisionamento tiver uma correspondência para o certificado fornecido para assinar o aplicativo encapsulado.|
|Autenticação|Um dispositivo deve ter um PIN definido para a criptografia funcionar. Em dispositivos nos quais você implantou um aplicativo encapsulado, tocar a barra de status no dispositivo exige que o usuário efetue o logon novamente com uma conta corporativa ou de estudante. A política padrão em um aplicativo encapsulado é *autenticação na nova inicialização*. O iOS lida com qualquer notificação externa (como uma chamada telefônica) saindo do aplicativo e reiniciando-o.


## <a name="setting-app-entitlements"></a>Definindo direitos de aplicativo
Antes de encapsular seu aplicativo, você pode conceder *direitos* para conceder ao aplicativo permissões e recursos adicionais que excedem o que um aplicativo normalmente pode fazer. Um *arquivo de direito* é usado durante a assinatura de código para especificar permissões especiais dentro de seu aplicativo (por exemplo, acesso a um conjunto de chaves compartilhado). Serviços de aplicativos específicos, chamados *funcionalidades*, são habilitados no Xcode durante o desenvolvimento do aplicativo. Uma vez habilitadas, as funcionalidades são refletidas no arquivo de direitos. Para obter mais informações sobre os recursos e funcionalidades, consulte [Adicionando Funcionalidades](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) na Biblioteca do Desenvolvedor iOS. Para obter uma lista completa de funcionalidades com suporte, consulte [Supported capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html) (Funcionalidades com suporte).

### <a name="supported-capabilities-for-the-app-wrapping-tool-for-ios"></a>Funcionalidades com suporte para a Ferramenta de Encapsulamento de Aplicativos para iOS

|Funcionalidade|Descrição|Diretrizes recomendadas|
|--------------|---------------|------------------------|
|Grupos de aplicativos|Use grupos de aplicativos para permitir que vários aplicativos acessem contêineres compartilhados e permitir comunicação entre processos adicional entre aplicativos.<br /><br />Para habilitar grupos de aplicativos, abra o painel **Funcionalidades** e clique em **LIGAR** em **Grupos de Aplicativos**. Você pode adicionar grupos de aplicativos ou selecionar grupos existentes.|Ao usar Grupos de aplicativos, use a notação inversa de DNS:<br /><br />*group.com.companyName.AppGroup*|
|Modos de segundo plano|Habilitar modos de segundo plano permite que seu aplicativo iOS continue em execução no segundo plano.||
|Proteção de dados|A proteção de dados adiciona um nível de segurança para arquivos armazenados em disco por seu aplicativo iOS. A proteção de dados usa o hardware de criptografia interna presente em dispositivos específicos para armazenar arquivos em um formato criptografado no disco. Seu aplicativo precisa ser provisionado para usar a proteção de dados.||
|Compra no aplicativo|As compras no aplicativo inserem uma loja diretamente em seu aplicativo, permitindo que você se conecte à loja e processe com segurança pagamentos do usuário. Você pode usar a compra no aplicativo para coletar pagamentos por uma funcionalidade avançada ou por conteúdo adicional usado pelo seu aplicativo.||
|Compartilhamento de conjunto de chaves|Habilitar o compartilhamento de conjunto de chaves permite que seu aplicativo compartilhe senhas do conjunto de chaves com outros aplicativos desenvolvidos pela sua equipe.|Ao usar o compartilhamento de conjunto de chaves, use a notação DNS inversa:<br /><br />*com.companyName.KeychainGroup*|
|VPN pessoal|Habilite VPN pessoal para permitir que seu aplicativo crie e controle uma configuração de VPN personalizada do sistema usando a estrutura de extensão de rede.||
|Notificações por push|O APNs (Apple Push Notification Service) permite que um aplicativo que não está em execução em primeiro plano notifique o usuário de que tem informações para ele.|Para que as notificações por push funcionem, você precisa usar um perfil de provisionamento específico ao aplicativo.<br /><br />Siga as etapas na [Apple developer documentation](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) (Documentação para desenvolvedores da Apple).|
|Configuração de acessório sem fio|Habilitar a configuração de acessório sem fio adiciona a estrutura External Accessory ao seu projeto e permite que seu aplicativo configure acessórios MFi Wi-Fi.||

### <a name="steps-to-enable-entitlements"></a>Etapas para habilitar direitos

1.  Habilite as funcionalidades em seu aplicativo:

    a.  No Xcode, vá até o destino do aplicativo e clique em **Funcionalidades**.

    b.  Habilite as funcionalidades apropriadas. Para obter informações detalhadas sobre cada funcionalidade e como determinar os valores corretos, consulte [Adicionando Funcionalidades](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) na Biblioteca do Desenvolvedor iOS.

    c.  Tome nota de quaisquer IDs que você criar durante o processo.

    d.  Compile e assine seu aplicativo a ser encapsulado.

2.  Habilite os direitos no seu perfil de provisionamento:

    a.  Entre na Central de Associados do Desenvolvedor da Apple.

    b.  Crie um perfil de provisionamento para seu aplicativo. Para obter instruções, consulte [How to Obtain the Prerequisites for the Intune App Wrapping Tool for iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) (Como obter os pré-requisitos para a Ferramenta de Disposição do Aplicativo do Intune para iOS).

    c.  No seu perfil de provisionamento, habilite os mesmo direitos que você tem em seu aplicativo. Você precisará fornecer as mesmas IDs que especificou durante o desenvolvimento do seu aplicativo.

    d.  Conclua o assistente de perfil de provisionamento e baixe o arquivo.

3.  Certifique-se de que foram satisfeitos todos os pré-requisitos e encapsule o aplicativo.

### <a name="troubleshoot-common-errors-with-entitlements"></a>Solucione erros comuns com direitos
Se a Ferramenta de Disposição do Aplicativo para iOS exibir um erro de direito, tente as seguintes etapas de solução de problemas.

|Problema|Causa|Resolução|
|---------|---------|--------------|
|Falha ao analisar direitos gerados do aplicativo de entrada.|A Ferramenta de Encapsulamento de Aplicativos não pode ler o arquivo de direitos que foi extraído do aplicativo. O arquivo de direitos pode estar malformado.|Inspecione o arquivo de direitos de seu aplicativo. As instruções a seguir explicam como fazer isso. Ao inspecionar o arquivo de direitos, verifique se há qualquer sintaxe malformada. O arquivo deve estar no formato XML.|
|Direitos estão ausentes no perfil de provisionamento (direitos ausentes são listados). Empacote novamente o aplicativo com um perfil de provisionamento que tenha esses direitos.|Há uma incompatibilidade entre os direitos habilitados no perfil de provisionamento e os recursos habilitados no aplicativo. Essa incompatibilidade também se aplica às IDs associadas a recursos específicos (como grupos de aplicativos e acesso de conjunto de chaves).|Em geral, você pode criar um novo perfil de provisionamento que habilita os mesmos recursos que o aplicativo. Quando as IDs entre o perfil e o aplicativo não coincidirem, a Ferramenta de Encapsulamento de Aplicativos substituirá as IDs se conseguir fazer isso. Se ainda receber o erro depois de criar um novo perfil de provisionamento, você pode tentar remover direitos do aplicativo usando o parâmetro –e (consulte a seção "Usando o parâmetro –e para remover direitos do aplicativo”).|

### <a name="find-the-existing-entitlements-of-a-signed-app"></a>Localize os direitos existentes de um aplicativo assinado
Para examinar as autorizações existentes de um aplicativo assinado e do perfil de provisionamento:

1.  Localize o arquivo .ipa, altere a extensão para .zip.

2.  Expanda o arquivo .zip. Isso produzirá uma pasta de Carga que contém o pacote .app.

3.  Use a ferramenta codesign para verificar os direitos no pacote .app, em que `YourApp.app` é o nome real do seu pacote .app:

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```

4.  Use a ferramenta de segurança para verificar os direitos do perfil de provisionamento inserido no aplicativo, em que `YourApp.app` é o nome real do seu pacote .app.

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```

### <a name="remove-entitlements-from-an-app-by-using-the-e-parameter"></a>Remover direitos de um aplicativo usando o parâmetro –e
Este comando remove quaisquer funcionalidades habilitadas no aplicativo que não estão no arquivo de direitos. Se você remover as funcionalidades que estão sendo usadas pelo aplicativo, elas poderão interromper seu aplicativo. Um exemplo de onde você poderia remover funcionalidades ausentes seria um aplicativo produzido pelo fornecedor que tem todas as funcionalidades por padrão.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## <a name="security-and-privacy-for-the-app-wrapping-tool"></a>Segurança e privacidade da Ferramenta de Disposição do Aplicativo
Use as seguintes melhores práticas de segurança e privacidade ao usar a Ferramenta de Disposição do Aplicativo.

-   O certificado de autenticação, o perfil de provisionamento e o aplicativo de linha de negócios que você especificar devem estar no mesmo computador macOS que você usar para executar a ferramenta de disposição do aplicativo. Se os arquivos estiverem em um caminho UNC, verifique se eles são acessíveis no computador macOS. O caminho deve ser protegido por assinatura SMB ou IPsec.

    O aplicativo encapsulado importado no console de administração deve estar no mesmo computador no qual você executa a ferramenta. Se os arquivos estiverem em um caminho UNC, certifique-se de que serão acessíveis no computador que executa o console de administração. O caminho deve ser protegido por assinatura SMB ou IPsec.

-   O ambiente para o qual a Ferramenta de Disposição do Aplicativo é baixada do repositório do GitHub precisa ser protegido por assinatura IPsec ou SMB.

-   O aplicativo que você processar deve vir de uma fonte confiável para garantir a proteção contra ataques.

-   Certifique-se de que a pasta de saída que você especificar na Ferramenta de Disposição do Aplicativo esteja protegida, principalmente se for uma pasta remota.

-   Aplicativos iOS que incluem uma caixa de diálogo de upload de arquivos podem permitir que os usuários contornem restrições de recortar, copiar e colar aplicadas a eles. Por exemplo, um usuário poderia usar a caixa de diálogo de carregamento de arquivo para carregar uma captura de tela dos dados do aplicativo.

-   Quando monitora a pasta de documentos em seu dispositivo de dentro de um aplicativo encapsulado, você pode ver uma pasta chamada .msftintuneapplauncher. Alterar ou excluir essa pasta pode afetar o funcionamento correto de aplicativos restritos.

### <a name="see-also"></a>Consulte também
- [Decidir como preparar aplicativos para o gerenciamento de aplicativo móvel com o Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [Usar o SDK para habilitar aplicativos para o gerenciamento de aplicativo móvel](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Nov16_HO4-->


