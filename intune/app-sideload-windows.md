---
title: Aplicativos de sideload do Windows e do Windows Phone para o Intune
description: Saiba como assinar aplicativos de linha de negócios para que você possa usar o Intune para implantá-los.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
ms.custom: intune-classic
ms.openlocfilehash: 617ff6c9c244d4bc38f1ee345f4df39965eaf037
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34223915"
---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Assine aplicativos da linha de negócios para que possam ser implantados em dispositivos Windows com o Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Como administrador do Intune, é possível implantar aplicativos da linha de negócios (LOB) em dispositivos Windows e Windows 10 Mobile, incluindo o aplicativo de Portal da Empresa. Para implantar aplicativos .appx ou. xap em dispositivos Windows 10 Mobile e Windows 10 ou implantar qualquer aplicativo LOB em dispositivos Windows Phone 8.1 ou Windows 8.1, você deve obter um **Certificado de Assinatura de Código Móvel Empresarial da Symantec**. Somente o certificado da Symantec é confiável para esses aplicativos para os respectivos dispositivos Windows. Você pode usar sua própria autoridade de certificação para aplicativos do Windows 10 e "universal". Esse certificado é necessário para:

-   Assinar o aplicativo do Portal da Empresa para implantação em Computadores Windows, dispositivos Windows 10 Mobile e dispositivos Windows Phone

-   Assinar os aplicativos de linha de negócios da empresa para que o Intune possa implantá-los nos dispositivos Windows

As etapas a seguir o ajudarão a obter os certificados necessários e assinar os aplicativos. Você precisará se registrar como um desenvolvedor Microsoft e, em seguida, comprar um certificado da Symantec.


1. **Registrar-se como um desenvolvedor Microsoft**<br>
   [Registre-se como um desenvolvedor Microsoft](http://go.microsoft.com/fwlink/?LinkId=268442) usando as informações da conta corporativa usada durante o logon para comprar sua conta corporativa. Essa solicitação precisará ser autorizada por um executivo da empresa antes que você receba um certificado de assinatura de código.

2. **Obter um certificado corporativo do Symantec**<br>
  Compre um certificado pelo [site do Symantec](http://go.microsoft.com/fwlink/?LinkId=268441) usando sua ID do Symantec. Depois de comprar o certificado, o aprovador corporativo que você designou ao se registrar como um desenvolvedor Microsoft receberá um email solicitando a aprovação da solicitação de certificado. Para obter mais informações sobre o requisito de certificado do Symantec, consulte [Why Windows Phone requires a Symantec certificate? (Por que o Windows Phone exige um certificado da Symantec?)](https://technet.microsoft.com/library/dn764959.aspx#BKMK_Symantec) Perguntas frequentes sobre o registro de dispositivos Windows.

3.  **Importar certificados**<br>
    Assim que a solicitação tiver sido aprovada, você receberá um email com instruções para importar os certificados. Siga as instruções no email para importar os certificados.

4.  **Verificar os certificados importados**<br>
    Para verificar se os certificados foram importados corretamente, acesse o snap-in **Certificados**, clique com o botão direito do mouse em **Certificados** e selecione **Localizar Certificados**. No campo **Contém** , digite “Symantec” e clique em **Encontrar agora**. Os certificados que você importou devem aparecer nos resultados.

    ![Localize o certificado do Symantec](./media/wit.gif)

5. **Exportar um certificado de assinatura**<br>
    Após ter verificado se os certificados estão presentes, você pode exportar o arquivo .pfx para assinar o portal da empresa. Selecione o certificado do Symantec com a “assinatura por código” de **Finalidade** . Clique com o botão direito do mouse no certificado de assinatura por código e selecione **Exportar**.

    ![Exporte o certificado de assinatura](./media/wit-walk-cert2.gif)

    No **Assistente para Exportação de Certificados**, selecione **Sim, exportar a chave privada** e clique em **Avançar**. **Selecione Troca de Informações Pessoais –PKCS #12 (.PFX)** e marque **Incluir todos os certificados no caminho de certificação se possível**. Conclua o assistente. Para obter mais informações, consulte [How to Export a Certificate with the Private Key (Como exportar um certificado com uma chave privada)](http://go.microsoft.com/fwlink/?LinkID=203031).

6.  **Carregar o aplicativo no Intune**<br>
    Carregue o arquivo de aplicativo assinado e seu certificado de assinatura por código para disponibilizar o aplicativo a seus usuários finais.

    1.  No Portal do Azure, clique em **Administração** &gt; **Windows Phone**.

    2.  Clique em **Carregar Arquivo do Aplicativo Assinado** e entre com sua ID do administrador do Intune.

    3.  Adicione o arquivo de certificado (.pfx) que você exportou para **Certificado de assinatura por código** e crie uma senha para o certificado.

    4.  Conclua o assistente.

## <a name="example-download-sign-and-deploy-the-company-portal-app-for-windows-devices"></a>Exemplo: baixar, assinar e implantar o aplicativo do Portal da Empresa em dispositivos Windows

É possível implantar o aplicativo do Portal da Empresa em dispositivos Windows (incluindo dispositivos Windows Phone e Windows 10 Mobile) com o Intune em vez de instalar da Microsoft Store. Você deve baixar o aplicativo de Portal da Empresa e assiná-lo com seu certificado.  Isso só é necessário se os usuários não usam o Armazenamento da Empresa e você deseja implantar o Portal da Empresa em dispositivos Windows Phone 8.1.


1.  **Baixe o aplicativo do Portal da Empresa**

    Para implantar o aplicativo do Portal da Empresa usando o Intune, é possível baixar o [Aplicativo do Portal da Empresa do Microsoft Intune para Windows Phone 8.1](http://go.microsoft.com/fwlink/?LinkId=615799) no Centro de Download e executar o arquivo de extração automática (.exe). Esse arquivo contém dois arquivos:

    -   CompanyPortal.appx – Aplicativo de instalação do Portal da Empresa para Windows Phone 8.1

    -   WinPhoneCompanyPortal.ps1 – Um script do PowerShell que você pode usar para assinar o arquivo do aplicativo do Portal da Empresa para que ele pode ser implantado em dispositivos Windows Phone 8.1

    Como alternativa, é possível baixar o Portal da Empresa para Windows Phone 8.1 (pacote licenciado offline) ou o Portal da Empresa para Windows 10 (pacote licenciado offline) da [Microsoft Store para Empresas](http://businessstore.microsoft.com/). O aplicativo de Portal da Empresa precisará ser adquirido com uma licença offline e o pacote apropriado baixado para uso offline. As listagens de plataforma Windows 8 e Windows Phone 8 na seleção fazem referência às suas contrapartes 8.1. Para obter mais detalhes sobre como fazer isso com o Intune, consulte [Gerenciar aplicativos adquiridos na Microsoft Store para Empresas](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).

2.  **Baixar o SDK do Windows Phone** Baixe o SDK do Windows Phone 8.0](http://go.microsoft.com/fwlink/?LinkId=615570) e instale o SDK no seu computador. O SDK é necessário para gerar um token de registro do aplicativo.

3.  **Gerar um arquivo AETX** Gere um arquivo de token de registro do aplicativo (.aetx) por meio do arquivo Symantec PFX usando o AETGenerator.exe, parte do SDK do Windows Phone 8.0. Para obter instruções de como criar um arquivo AETX, consulte [Como gerar um token de registro de aplicativo para o Windows Phone](https://msdn.microsoft.com/library/windows/apps/jj735576.aspx)

4.  **Baixar o SDK do Windows para o Windows 8.1** Baixe e instale o [SDK do Windows Phone](http://go.microsoft.com/fwlink/?LinkId=613525) (http://go.microsoft.com/fwlink/?LinkId=613525). Observe que o script do PowerShell incluído com o aplicativo do Portal da Empresa usa o local de instalação padrão, `${env:ProgramFiles(x86)}\Windows Kits\8.1`. Se instalar em outro lugar, você deve incluir o local em um parâmetro de cmdlet.

5.  **Assinar código do aplicativo usando o PowerShell** Como administrador, abra o **Windows PowerShell** no computador host instalado com o SDK do Windows, o Symantec Enterprise Mobile Code Signing Certificate, navegue até o arquivo Sign-WinPhoneCompanyPortal.ps1 e execute o script.

    **Exemplo 1**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -AetxPath 'C:\signing\cert.aetx'
    ```
    Este exemplo assina CompanyPortal.appx em C:\temp\ e produz o CompanyPortalEnterpriseSigned.appx. Ele usaria a senha de PFX 1234 e leria a ID do editor do arquivo PFX. Ele lê também a ID da empresa do arquivo cert.aetx.

    **Exemplo 2**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -PublisherId 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1' -EnterpriseId 1000000001
    ```
    Este exemplo assina CompanyPortal.appx em C:\temp\ e produz o CompanyPortalEnterpriseSigned.appx. Ele usaria a senha de PFX 1234 e usaria a ID do editor especificada.

    **Parâmetros:**

    -   `-InputAppx` – O caminho local para o arquivo CompanyPortal.appx entre aspas simples. Por exemplo, 'C:\temp\CompanyPortal.appx'

    -   `-OutputAppx` – O nome de arquivo e caminho local para o aplicativo do Portal da Empresa assinado entre aspas simples. Por exemplo, 'C:\temp\CompanyPortalEnterpriseSigned.appx'

    -   `-PfxFilePath` – O nome do arquivo e o caminho local para o arquivo PFX exportado do certificado Symantec. Por exemplo, 'C:\signing\cert.pfx'

    -   `-PfxPassword` – A senha usada para assinar o arquivo PFX entre aspas simples. Por exemplo, '1234'

    -   `-AetxPath` – O caminho local para o arquivo .aetx que é usado para ler a ID da empresa, se o argumento 'EnterpriseId' não estiver definido. Este argumento ou EnterpriseId deve ser fornecido. Por exemplo, 'C:\signing\cert.aetx'

    -   `-PublisherId` - a ID do Editor da empresa. Se ausente, o campo 'Assunto' da Symantec Enterprise Mobile Code Signing Certificate será usado. Por exemplo, 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1'

    -   `-SdkPath` - o caminho para a pasta raiz do SDK do Windows para Windows 8.1. Esse argumento é opcional e o padrão é ${env:ProgramFiles(x86)}\Windows Kits\8.1.

    -   `-EnterpriseId` - a ID da empresa. Este argumento ou 'AetxPath' deve ser fornecido. Se esse argumento não for fornecido, a ID da empresa será lida do arquivo AETX. Por exemplo, 1000000001

6.  Implante o aplicativo do Portal da Empresa do Windows Phone 8.1 (SSP.appx). Para obter diretrizes, veja [Como adicionar aplicativos LOB (linha de negócios) do Windows Phone](lob-apps-windows-phone.md) ([Portal Clássico](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune)).

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>Como renovar o certificado corporativo de autenticação de código Symantec

O certificado da Symantec usado para implantar aplicativos móveis do Windows e do Windows Phone deve ser renovado periodicamente.

1.  Procure um email de renovação enviado da Symantec aproximadamente 14 dias antes da expiração do certificado. O email contém instruções da Symantec sobre como renovar o certificado corporativo.

    Para obter informações adicionais sobre certificados Symantec, visite [www.symantec.com](http://www.symantec.com) ou ligue para 1-877-438-8776 ou 1-650-426-3400.

2.  Vá para o site (exemplo: [ https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do ](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) e faça logon com a ID do Publicador Symantec e email endereçado associado ao certificado. Lembre-se de usar o mesmo computador para iniciar a renovação que você usará para baixar o certificado.

3.  Após a renovação ser aprovada e paga, baixe o certificado.

### <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>Como instalar o certificado atualizado para aplicativos de linhas de negócios (LOB)

1.  Assine a versão mais recente do seu aplicativo de linha de negócios.

2.  Abra o Portal do Azure e acesse **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Windows Phone** e clique em **Carregar Aplicativo Assinado**.

3.  Carregue o Portal da Empresa assinado. Você precisará de SSP.xap recentemente assinado e o novo arquivo .PFX que recebeu da Symantec ou o token de registro de aplicativo que foi criado com esse novo arquivo .PFX.

4.  Quando o upload for concluído, remova a versão antiga do Portal da Empresa no espaço de trabalho **Software**  .

5.  Assine todos aplicativos de linha de negócios de empresa novos e atualizados usando o novo certificado. Os aplicativos existentes não precisam ser assinados e reimplantados.

## <a name="manually-deploy-windows-10-company-portal-app"></a>Implantar manualmente o aplicativo Portal da Empresa para Windows 10
É possível pode implantar manualmente o aplicativo Portal da Empresa para Windows 10 diretamente do Intune, mesmo que ele ainda não esteja integrado com a Microsoft Store para Empresas.

 > [!NOTE]
 > Essa opção exigirá a implantação manual das atualizações sempre que uma atualização do aplicativo for lançada.

1. Faça logon na sua conta da [Microsoft Store para Empresas](https://www.microsoft.com/business-store) e adquira a versão do aplicativo Portal da Empresa com **licença offline**.  
2. Assim que o aplicativo for adquirido, selecione-o na página **Inventário**.  
3. Selecione **Todos os dispositivos do Windows 10** como a **Plataforma**, em seguida, a devida **Arquitetura** e baixe. Um arquivo de licença do aplicativo não é necessário para este aplicativo.
![Imagem de todos os dispositivos do Windows 10 e detalhes do Pacote de Arquitetura do X86 para Download](./media/Win10CP-all-devices.png)
4. Baixe todos os pacotes em "Estruturas Necessárias". Isto deve ser feito para as arquiteturas do x86, x64 e ARM – resultando em um total de nove pacotes, como mostrado abaixo.

![Imagem dos arquivos de dependência para Download ](./media/Win10CP-dependent-files.png)
5. Antes de carregar o aplicativo Portal da Empresa no Intune, crie uma pasta (por exemplo, C:&#92;Portal da Empresa) com os pacotes estruturados da seguinte maneira:
   1. Coloque o pacote Portal da Empresa em C:\Portal da Empresa. Crie uma subpasta Dependências nesse local também.  
   ![Imagem da pasta Dependências salva com o arquivo APPXBUN](./media/Win10CP-Dependencies-save.png)
   2. Coloque os nove pacotes de dependências na pasta Dependências.  
   Se as dependências não forem colocadas nesse formato, o Intune não conseguirá reconhecê-las e carregá-las durante o carregamento do pacote, fazendo com que o carregamento falhe com o seguinte erro.  
   ![A dependência de aplicativo do Windows para este instalador do software não foi encontrada na pasta do aplicativo. Você pode continuar a criar e implantar esse aplicativo, mas ele não será executado até que a dependência ausente do aplicativo do Windows seja fornecida.](./media/Win10CP-error-message.png)
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
