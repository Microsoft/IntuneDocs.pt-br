---
title: Fazer sideload de aplicativos do Windows e do Windows Phone
titleSuffix: Microsoft Intune
description: Saiba como assinar aplicativos de linha de negócios para que você possa usar o Intune para implantá-los.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 09/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a89392dabe695cf49e989351cef822852676916
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507387"
---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Assine aplicativos da linha de negócios para que possam ser implantados em dispositivos Windows com o Intune

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Como administrador do Intune, é possível implantar aplicativos da linha de negócios (LOB) Universal em dispositivos Windows 8.1 Desktop ou Windows 10 Desktop e Mobile, incluindo o aplicativo de Portal da Empresa. Para implantar aplicativos .appx em dispositivos Windows 8.1 Desktop ou Windows 10 Desktop e Mobile você pode usar o certificado de assinatura de código de uma autoridade de certificação pública já confiável por seus dispositivos Windows ou pode usar sua própria autoridade de certificação.

 > [!NOTE]
 > O Windows 8.1 Desktop requer uma política corporativa para habilitar o carregamento lateral ou o uso de Chaves de Sideload (habilitadas automaticamente para dispositivos ingressados no domínio). Para saber mais, confira [Sideload do Windows 8](https://blogs.technet.microsoft.com/scd-odtsp/2012/09/27/windows-8-sideloading-requirements-from-technet/).

## <a name="windows-10-sideloading"></a>Sideload do Windows 10

No Windows 10, o sideload é diferente de versões anteriores do Windows:

- Você pode desbloquear um dispositivo para sideload usando uma política corporativa. O Intune fornece uma política de configuração de dispositivo chamada "Instalação de aplicativo confiável". Definir isso como <allow> é tudo o que é necessário para dispositivos que já confiam no certificado usado para assinar o aplicativo appx.

- Os certificados Symantec Phone e as Chaves de Licença de Sideload não são necessários. No entanto, se uma autoridade de certificação local não estiver disponível, poderá ser necessário obter um certificado de assinatura de código de uma autoridade de certificação pública. Para saber mais, confira [Introdução à Assinatura de Código](https://docs.microsoft.com/windows/desktop/SecCrypto/cryptography-tools#introduction-to-code-signing).

### <a name="code-sign-your-app"></a>Assinatura de código para o seu aplicativo

A primeira etapa consiste em assinar o código do pacote appx. Para saber mais, confira [Assinar um pacote de aplicativos usando o SignTool](https://docs.microsoft.com/windows/uwp/packaging/sign-app-package-using-signtool).

### <a name="upload-your-app"></a>Carregar seu aplicativo

Em seguida, carregue o arquivo appx assinado. Para saber mais, confira [Adicionar um aplicativo de linha de negócios do Windows ao Microsoft Intune](lob-apps-windows.md).

Se você implantar o aplicativo conforme necessário para usuários ou dispositivos, não precisará do aplicativo do Portal da Empresa do Intune. No entanto, se você implantar o aplicativo conforme disponível para os usuários, eles poderão usar o aplicativo Portal da Empresa da Microsoft Store Pública, usar o aplicativo Portal da Empresa da Microsoft Store para Empresas Privada, ou será necessário assinar e implantar manualmente o Portal da Empresa do Intune.

### <a name="upload-the-code-signing-certificate"></a>Carregar um certificado de assinatura de código

Se o seu dispositivo Windows 10 ainda não confiar na autoridade de certificação, depois de assinar o pacote appx e carregá-lo no serviço Intune, será necessário carregar o certificado de assinatura de código no portal do Intune:
1. Clique em Aplicativos Cliente
2. Clique em Certificados do Windows Enterprise
3. Selecione 'Selecionar um arquivo' em certificado de assinatura de código
4. Selecione seu arquivo .cer e clique em carregar

Agora, qualquer dispositivo Windows 10 Desktop & Mobile com uma implantação de appx pelo serviço Intune fará o download automático do certificado corporativo correspondente e o aplicativo poderá ser iniciado após a instalação.

O Intune implanta apenas o arquivo .cer mais recente que foi carregado. Se você tiver vários arquivos appx criados por diferentes desenvolvedores que não estão associados à sua organização, será necessário fornecer arquivos appx não assinados para assinar com seu certificado ou fornecer o certificado de assinatura de código usado por sua organização.

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>Como renovar o certificado corporativo de autenticação de código Symantec

O certificado usado para implantar aplicativos móveis do Windows Phone 8.1 foi descontinuado em 28 de fevereiro de 2019 e não está mais disponível para renovação da Symantec. Se você estiver implantando no Windows 10 Mobile, poderá continuar usando os certificados de assinatura de código do Symantec Desktop Enterprise seguindo as instruções em [Sideload do Windows 10](app-sideload-windows.md#windows-10-sideloading).

## <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>Como instalar o certificado atualizado para aplicativos de linhas de negócios (LOB)

Windows Phone 8.1

O serviço Intune não pode mais implantar aplicativos de LOB para esta plataforma depois que o certificado de assinatura de código existente do Symantec Mobile Enterprise expirar. Ainda será possível carregar arquivos XAP/APPX não assinados usando um cartão SD ou baixando o arquivo no dispositivo. Para saber mais, confira [Como instalar arquivos XAP no Windows Phone](https://answers.microsoft.com/en-us/mobiledevices/forum/mdlumia-mdapps/how-to-install-xap-file-in-windows-phone-8/da09ee72-51ae-407c-9b85-bc148df89280).

Windows 8.1 Desktop/Windows 10 Desktop & Mobile

Se o período de certificação expirar, os arquivos appx poderão parar de iniciar. Você deve obter um novo arquivo .cer e seguir as instruções para assinar com código cada arquivo appx implantado e recarregar todos os arquivos appx e o arquivo .cer atualizado na seção Certificados do Windows Enterprise do portal do Intune

## <a name="manually-deploy-windows-10-company-portal-app"></a>Implantar manualmente o aplicativo Portal da Empresa para Windows 10
Se você não deseja fornecer acesso à Microsoft Store, pode implantar manualmente o aplicativo Windows 10 Company Portal diretamente do Intune, mesmo que não tenha integrado o Intune ao Microsoft Store for Business (MSFB). Como alternativa, se você se integrou, poderá implantar o aplicativo Portal da Empresa usando [implantar aplicativos usando o MSFB](store-apps-windows.md).

 > [!NOTE]
 > Essa opção exigirá a implantação manual das atualizações sempre que uma atualização do aplicativo for lançada.

1. Faça logon na sua conta da [Microsoft Store para Empresas](https://www.microsoft.com/business-store) e adquira a versão do aplicativo Portal da Empresa com **licença offline**.  
2. Assim que o aplicativo for adquirido, selecione-o na página **Inventário**.  
3. Selecione **Todos os dispositivos do Windows 10** como a **Plataforma**, em seguida, a devida **Arquitetura** e baixe. Um arquivo de licença do aplicativo não é necessário para este aplicativo.
   ![Imagem dos detalhes do pacote do Windows 10 X86 para Download](./media/app-sideload-windows/Win10CP-all-devices.png)
4. Baixe todos os pacotes em "Estruturas Necessárias". Isto deve ser feito para as arquiteturas do x86, x64 e ARM – resultando em um total de nove pacotes, como mostrado abaixo.

   ![Imagem dos arquivos de dependência para Download ](./media/app-sideload-windows/Win10CP-dependent-files.png)
5. Antes de carregar o aplicativo Portal da Empresa no Intune, crie uma pasta (por exemplo, C:&#92;Portal da Empresa) com os pacotes estruturados da seguinte maneira:
   1. Coloque o pacote Portal da Empresa em C:\Portal da Empresa. Crie uma subpasta Dependências nesse local também.  
      ![Imagem da pasta Dependências salva com o arquivo APPXBUN](./media/app-sideload-windows/Win10CP-Dependencies-save.png)
   2. Coloque os nove pacotes de dependências na pasta Dependências.  
      Se as dependências não forem colocadas nesse formato, o Intune não conseguirá reconhecê-las e carregá-las durante o carregamento do pacote, fazendo com que o carregamento falhe com o seguinte erro.  
      ![Mensagem de erro – a dependência de aplicativo do Windows deve ser fornecida.](./media/app-sideload-windows/Win10CP-error-message.png)
6. Retorne ao Intune, em seguida, carregue o aplicativo Portal da Empresa como um novo aplicativo. Implante-o como um aplicativo necessário para o conjunto de usuários de destino desejado.  

Consulte [Implantando um appxbundle com dependências via MDM do Microsoft Intune ](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) para obter mais informações sobre como o Intune lida com as dependências para os aplicativos Universal.  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Como atualizo o Portal da Empresa nos dispositivos de meus usuários se eles já instalaram os aplicativos mais antigos na loja?
Se os usuários já instalaram os aplicativos Portal da Empresa para Windows 8.1 ou Windows Phone 8.1 na Store, então, eles deverão ser atualizados automaticamente para a nova versão sem nenhuma ação necessária tomada por você ou seu usuário. Se a atualização não acontecer, peça aos usuários que verifiquem se eles ativaram as atualizações automáticas dos aplicativos da Store em seus dispositivos.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Como atualizo meu aplicativo Portal da Empresa para Windows 8.1 carregado para o aplicativo Portal da Empresa para Windows 10?
Nosso caminho de migração recomendado é excluir a implantação do aplicativo Portal da Empresa para Windows 8.1 definindo a ação de implantação para "Desinstalar". Depois que isso for feito, o aplicativo Portal da Empresa para Windows 10 poderá ser implantado usando qualquer uma das opções acima.  

Se você precisar carregar o aplicativo e implantou o Portal da Empresa para Windows 8.1 sem assiná-lo com o Certificado da Symantec, siga as etapas em Implantar diretamente por meio da seção Intune acima para concluir a atualização.

Se você precisar carregar o aplicativo, assinou e implantou o Portal da Empresa para Windows 8.1 com o certificado de assinatura de código da Symantec, siga as etapas na seção abaixo.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Como atualizo meu aplicativo Portal da Empresa para Windows Phone 8.1 ou o aplicativo Portal da Empresa para Windows 8.1 carregado para o aplicativo Portal da Empresa para Windows 10?
Nosso caminho de migração recomendado é excluir a implantação existente do aplicativo Portal da Empresa para Windows Phone 8.1 ou do aplicativo Portal da Empresa para Windows 8.1 definindo a ação de implantação para "Desinstalar". Depois que isso for feito, o aplicativo Portal da Empresa para Windows 10 poderá ser implantado normalmente.  

Caso contrário, o aplicativo Portal da Empresa para Windows 10 precisará ser atualizado e assinado devidamente para garantir que o caminho de atualização seja respeitado.  

Se o aplicativo Portal da Empresa para Windows 10 for assinado e implantado dessa forma, você precisará repetir o processo para cada nova atualização do aplicativo quando ela ficar disponível na loja. O aplicativo não será atualizado automaticamente quando a loja for atualizada.  

Aqui está como assinar e implantar o aplicativo desta forma:

1. Baixe o aplicativo Portal da Empresa para Windows 10 do Microsoft Intune assinando o script em [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript).  Esse script requer o SDK do Windows para o Windows 10 ser instalado no computador host. Para baixar o SDK do Windows para Windows 10, acesse [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Baixe o aplicativo Portal da Empresa para Windows 10 na Microsoft Store para Empresas, como descrito acima.  
3. Execute o script com os parâmetros de entrada detalhados no cabeçalho do script para assinar o aplicativo Portal da Empresa para Windows 10 (extraído abaixo). As dependências não precisam ser passada para o script. Só são necessárias quando o aplicativo está sendo carregado para o Console de Administração do Intune.

|       Parâmetro       |                                                                    Descrição                                                                    |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| InputWin10AppxBundle  |                                             O caminho para onde está localizado o arquivo appxbundle de origem.                                              |
| OutputWin10AppxBundle |                                                  O caminho de saída para o arquivo assinado appxbundle.                                                  |
|       Win81Appx       |                          O caminho para onde o arquivo do Portal da Empresa para Windows 8.1 ou Windows Phone 8.1 (.APPX) está localizado.                           |
|      PfxFilePath      |                                   O caminho para o arquivo do Certificado de Autenticação do Código do Symantec Enterprise Mobile (.PFX).                                    |
|      PfxPassword      |                                     A senha do Certificado de Autenticação do Código do Symantec Enterprise Mobile.                                      |
|      PublisherId      |      A ID do Editor da empresa. Se ausente, o campo 'Assunto' da Symantec Enterprise Mobile Code Signing Certificate será usado.       |
|        SdkPath        | O caminho para a pasta-raiz do SDK do Windows para o Windows 10. Esse argumento é opcional e o padrão é ${env:ProgramFiles(x86)}\Windows Kits\10 |

O script produzirá a versão assinada do aplicativo Portal da Empresa para Windows 10 quando terminar a execução. Você pode implantar a versão assinada do aplicativo como um aplicativo LOB via Intune, que atualizará as versões atualmente implantadas para esse novo aplicativo.  
