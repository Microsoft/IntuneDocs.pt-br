---
title: Usar certificados PFX importados no Microsoft Intune – Azure | Microsoft Docs
description: Use certificados PKCS (Public Key Cryptography Standards) importados com o Microsoft Intune, o que inclui a importação de certificados, a configuração do modelo de certificado, a instalação do Conector de Certificado PFX Importado do Intune e a criação de um perfil de Certificado PKCS Importado.
keywords: ''
author: ralms
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
ms.openlocfilehash: d54c58523fdb44080b6c4210d639f9ad0ce476e2
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "73801537"
---
# <a name="configure-and-use-imported-pkcs-certificates-with-intune"></a>Configurar e usar certificados PKCS importados com o Intune

O Microsoft Intune dá suporte ao uso de certificados de par de chaves públicas (PKCS) importados, normalmente usados na criptografia S/MIME com perfis de email. Determinados perfis de email no Intune dão suporte a uma opção para habilitar o S/MIME, em que é possível definir um certificado de autenticação S/MIME e um certificado de criptografia S/MIME.

A criptografia S/MIME é desafiadora porque o email é criptografado com um certificado específico. Você precisa ter a chave privada do certificado que criptografou o email no dispositivo em que está lendo o email para que ele seja descriptografado. Os certificados de criptografia são renovados regularmente, o que significa que você pode precisar do seu histórico de criptografia em todos os seus dispositivos para garantir que possa ler emails mais antigos.  Como o mesmo certificado precisa ser usado em todos os dispositivos, não é possível usar perfis de certificados [SCEP](certificates-scep-configure.md) ou [PKCS](certficates-pfx-configure.md) para essa finalidade, pois esses mecanismos de entrega de certificados fornecem certificados exclusivos por dispositivo.

Para obter mais informações sobre como usar S/MIME com o Intune, confira [Usar S/MIMEpara criptografar email](certificates-s-mime-encryption-sign.md).

## <a name="requirements"></a>Requisitos

Para usar certificados PKCS importados com o Intune, a seguinte infraestrutura será necessária:

- **Conector do Certificado PFX do Microsoft Intune**:

  Cada locatário do Intune tem suporte para uma única instância desse conector. É possível instalar esse conector no mesmo servidor de uma instância do Microsoft Intune Certificate Connector.

  Este conector manipula as solicitações para arquivos PFX importados para o Intune para criptografia de email S/MIME de um usuário específico.

  Este conector poderá atualizar-se automaticamente quando novas versões forem disponibilizadas. Para usar a capacidade de atualização, verifique se estão abertos os firewalls que permitem que o conector contate **autoupdate.msappproxy.net** na porta **443**.

  Para obter mais informações sobre todos os pontos de extremidade de rede que o conector acessa, confira [Largura de banda e requisitos de configuração de rede do Intune](../fundamentals/network-bandwidth-use.md).

- **Windows Server**:  
  Use um Windows Server para hospedar o Conector de Certificado PFX do Microsoft Intune.  O conector é usado para processar solicitações de certificados importados para o Intune.

  O Intune dá suporte à instalação do *Microsoft Intune Certificate Connector* no mesmo servidor do *Conector de Certificado PFX do Microsoft Intune*.

  Para dar suporte ao conector, o servidor deve executar o .NET 4.6 Framework ou posterior. A instalação do conector instalará automaticamente o .NET 4.6 Framework, caso não esteja instalado.

- **Visual Studio 2015 ou posterior** (opcional): Use o Visual Studio para criar o módulo auxiliar do PowerShell com cmdlets para importar certificados PFX ao Microsoft Intune. Para obter os cmdlets auxiliares do PowerShell, confira o [Projeto PFXImport do PowerShell no GitHub](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).

## <a name="how-it-works"></a>Como funciona

Ao usar o Intune para implantar um **certificado PFX importado** em um usuário, há dois componentes em jogo, além do dispositivo:

- **Serviço do Intune**: armazena os certificados PFX em um estado criptografado e manipula a implantação do certificado no dispositivo do usuário.  As senhas que protegem as chaves privadas dos certificados são criptografadas antes de serem carregadas, usando um HSM (módulo de segurança de hardware) ou a criptografia do Windows, o que garante que o Intune não possa acessar a chave privada a qualquer momento.

- **Conector do Certificado PFX do Microsoft Intune**: quando um dispositivo solicita um certificado PFX que foi importado para o Intune, a senha criptografada, o certificado e a chave pública do dispositivo são enviados para o conector.  O conector descriptografa a senha usando a chave privada local e, em seguida, criptografa novamente a senha (e quaisquer perfis do plist, se usar o iOS) com a chave do dispositivo antes de enviar o certificado de volta para o Intune.  Depois, o Intune entrega o certificado ao dispositivo, que consegue descriptografá-lo com a chave privada do dispositivo e instalar o certificado.

## <a name="download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune"></a>Baixar, instalar e configurar o Conector de Certificado PFX do Microsoft Intune

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Administração de locatários** > **Conectores e tokens** > **Conectores de certificado** > **Adicionar**.

   ![Baixar o Conector de Certificado PFX do Microsoft Intune](./media/certificates-imported-pfx-configure/download-imported-pfxconnector.png)

3. Siga as orientações para baixar o *Conector de Certificado PFX do Microsoft Intune* em um local acessível do servidor no qual você instalará o conector.

4. Após a conclusão do download, entre no servidor e execute o instalador (PfxCertificateConnectorBootstrapper.exe).  
   - Quando você aceita o local de instalação padrão, o conector é instalado em `Program Files\Microsoft Intune\PFXCertificateConnector`.
   - O serviço do conector é executado na conta Sistema Local. Se for necessário usar um proxy para acesso à Internet, confirme se a conta de serviço local pode acessar as configurações de proxy no servidor.

5. O Conector do Certificado PFX do Microsoft Intune abre a guia **Registro** após a instalação. Para habilitar a conexão com o Intune, **Entre** e insira uma conta com permissões de administrador do Intune ou administrador global do Azure.

   > [!WARNING]
   > Por padrão, a **Configuração de Segurança Aprimorada do IE** do Windows Server é definida como **Ativada**, o que pode causar problemas ao entrar no Office 365.

6. Feche a janela.

7. No Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft, volte para **Administração de locatários** > **Conectores e tokens** > **Conectores de certificado**. Depois de alguns instantes, uma marca de seleção verde é exibida e o status da conexão é atualizado. O servidor do conector agora pode se comunicar com o Intune.

## <a name="import-pfx-certificates-to-intune"></a>Importar Certificados PFX para o Intune

Use o [Microsoft Graph](https://docs.microsoft.com/graph) para importar os certificados PFX de seus usuários no Intune. O [Projeto PFXImport do PowerShell no GitHub](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell) proporciona cmdlets para executar as operações com facilidade.

Se você preferir usar sua própria solução personalizada no Graph, use o [tipo de recurso userPFXCertificate](https://docs.microsoft.com/graph/api/resources/intune-raimportcerts-userpfxcertificate?view=graph-rest-beta).

### <a name="build-pfximport-powershell-project-cmdlets"></a>Criar cmdlets do “Projeto PFXImport do PowerShell”

Para usar os cmdlets do PowerShell, crie seu próprio projeto usando o Visual Studio. O processo é muito direto e, embora possa ser executado no servidor, é recomendável executá-lo em sua estação de trabalho.  

1. Vá para a raiz do repositório [Intune-Resource-Access](https://github.com/microsoft/Intune-Resource-Access) no GitHub e baixe ou clone o repositório do Git para o seu computador.

   ![Botão de download do GitHub](./media/certificates-imported-pfx-configure/github-download.png)

2. Vá para `.\Intune-Resource-Access-develop\src\PFXImportPowershell\` e abra o projeto com o Visual Studio usando o arquivo **PFXImportPS.sln**.

3. Na parte superior, altere de **Depurar** para **Versão**.

4. Vá para **Compilar** e selecione **Compilar PFXImportPS**. Após alguns instantes, você verá a confirmação **Compilação Bem-sucedida** na parte inferior esquerda do Visual Studio.

   ![Opção de Compilação do Visual Studio](./media/certificates-imported-pfx-configure/vs-build-release.png)

5. O processo de compilação cria uma nova pasta com o Módulo do PowerShell em `.\Intune-Resource-Access-develop\src\PFXImportPowershell\PFXImportPS\bin\Release`.

   Use essa pasta de **Versão** nas próximas etapas.

### <a name="create-the-encryption-public-key"></a>Criar uma Chave Pública de criptografia

Importe os Certificados PFX e suas chaves privadas para o Intune. A senha que protege a chave privada é criptografada com uma chave pública armazenada localmente. É possível usar a criptografia do Windows, um módulo de segurança de hardware ou outro tipo de criptografia para gerar e armazenar os pares de chaves públicas e privadas.  Dependendo do tipo de criptografia usado, o par de chave pública ou privada pode ser exportado em um formato de arquivo para fins de backup.

O módulo do PowerShell fornece métodos para criar uma chave usando a criptografia do Windows. Também é possível usar outras ferramentas para criar uma chave.  

#### <a name="to-create-the-encryption-key-using-windows-cryptography"></a>Para criar a chave de criptografia usando a criptografia do Windows

1. Copie a pasta *Versão* criada pelo Visual Studio no servidor em que você instalou o **Conector de Certificado PFX do Microsoft Intune**. Essa pasta contém o módulo do PowerShell.

2. No servidor, abra o *PowerShell* como Administrador e navegue até a pasta *Versão* que contém o módulo do PowerShell.

3. Para importar o módulo, execute `Import-Module .\IntunePfxImport.psd1`.

4. Em seguida, execute `Add-IntuneKspKey "Microsoft Software Key Storage Provider" "PFXEncryptionKey"`

   > [!TIP]
   > O provedor que você usa deve ser selecionado novamente ao importar os Certificados PFX. É possível usar o **Provedor de Armazenamento de Chaves de Software Microsoft**, embora haja suporte para o uso de um provedor diferente. O nome da chave também é fornecido como exemplo, e é possível usar um nome de chave diferente à sua escolha.

   Se você planeja importar o certificado de sua estação de trabalho, pode exportar essa chave para um arquivo com o seguinte comando:  `Export-IntunePublicKey -ProviderName "<ProviderName>" -KeyName "<KeyName>" -FilePath "<File path to write to>"`

   A chave privada deve ser importada no servidor que hospeda o Conector de Certificado PFX do Microsoft Intune para que os certificados PFX importados possam ser processados com êxito.

#### <a name="to-use-a-hardware-security-module-hsm"></a>Para usar um HSM (módulo de segurança de hardware)

Você pode usar um HSM (módulo de segurança de hardware) para gerar e armazenar o par de chaves públicas e privadas. Para obter mais informações, confira a documentação do fornecedor do HSM.

### <a name="import-pfx-certificates"></a>Importar certificados PFX

O processo a seguir usa os cmdlets do PowerShell como exemplo de importação dos certificados PFX. Você pode escolher diferentes opções, dependendo de seus requisitos.

As opções incluem:  
- Finalidade pretendida (agrupa os certificados com base em uma marcação):  
  - não atribuído
  - smimeEncryption
  - smimeSigning

- Esquema de Preenchimento:  
  - pkcs1
  - oaepSha1
  - oaepSha256
  - oaepSha384
  - oaepSha512

Selecione o Provedor de Armazenamento de Chaves que corresponde ao provedor usado para criar a chave.

#### <a name="to-import-the-pfx-certificate"></a>Para importar o certificado PFX  

1. Exporte os certificados da CA (Autoridade de Certificação) seguindo a documentação do provedor.  Para os Serviços de Certificados do Active Directory, você pode usar [este script de exemplo](https://gallery.technet.microsoft.com/Export-CMPfxCertificatesFro-d55f687b).

2. No servidor, abra o *PowerShell* como Administrador e navegue até a pasta *Versão* que contém o módulo do PowerShell.

3. Para importar o módulo, execute `Import-Module .\IntunePfxImport.psd1`

4. Para autenticar no Intune Graph, execute `$authResult = Get-IntuneAuthenticationToken -AdminUserName "<Admin-UPN>"`

   > [!NOTE]
   > Conforme a autenticação é executada no Graph, você deve fornecer permissões à AppID. Caso seja a primeira vez que você utiliza esse utilitário, é necessário ser um *Administrador global*. Os cmdlets do PowerShell usam a mesma AppID das [Amostras do PowerShell do Intune](https://github.com/microsoftgraph/powershell-intune-samples).

5. Converta a senha de cada arquivo PFX importado para uma cadeia de caracteres segura, executando `$SecureFilePassword = ConvertTo-SecureString -String "<PFXPassword>" -AsPlainText -Force`.

6. Para criar um objeto **UserPFXCertificate**, execute `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "<FullPathPFXToCert>" $SecureFilePassword "<UserUPN>" "<ProviderName>" "<KeyName>" "<IntendedPurpose>" "<PaddingScheme>"`

   Por exemplo: `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "C:\temp\userA.pfx" $SecureFilePassword "userA@contoso.com" "Microsoft Software Key Storage Provider" "PFXEncryptionKey" "smimeEncryption" "pkcs1"`

   > [!NOTE]
   > Ao importar o certificado de um sistema diferente do servidor onde o conector está instalado, o usuário deve usar o comando a seguir, que inclui o caminho do arquivo da chave: `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "<FullPathPFXToCert>" $SecureFilePassword "<UserUPN>" "<ProviderName>" "<KeyName>" "<IntendedPurpose>" "<PaddingScheme>" "<File path to public key file>"`

7. Importe o objeto **UserPFXCertificate** para o Intune executando `Import-IntuneUserPfxCertificate -AuthenticationResult $authResult -CertificateList $userPFXObject`

8. Para validar o certificado importado, execute `Get-IntuneUserPfxCertificate -AuthenticationResult $authResult -UserList "<UserUPN>"`

Para mais informações sobre outros comandos disponíveis, confira o arquivo Leiame no [Projeto PFXImport do PowerShell no GitHub](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).

## <a name="create-a-pkcs-imported-certificate-profile"></a>Criar um perfil de certificado PKCS importado

Depois de importar os certificados para o Intune, crie um perfil de **certificado importado PKCS** e atribua-o aos grupos do Azure Active Directory.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.

3. Insira as seguintes propriedades:

   - **Nome** do perfil
   - Opcionalmente, defina uma descrição
   - **Plataforma** na qual implantar o perfil
   - Defina **Tipo de perfil** como **Certificado PKCS importado**

4. Selecione **Configurações** e digite as seguintes propriedades:

   - **Finalidade pretendida**: especifique a finalidade pretendida dos certificados importados para esse perfil. Os administradores podem importar certificados com finalidades pretendidas diferentes (como autenticação S/MIME ou criptografia S/MIME). A finalidade pretendida selecionada no perfil de certificado corresponde ao perfil de certificado com os certificados corretos importados. A finalidade pretendida é uma marcação para agrupar certificados importados, mas não garante que os certificados importados com essa marcação atenderão à finalidade pretendida.  
   - **Período de validade do certificado**: a menos que o período de validade seja alterado no modelo de certificado, a opção padrão é de um ano.
   - **KSP (provedor de armazenamento de chaves)** : Para o Windows, selecione o local em que as chaves serão armazenadas no dispositivo.

5. Selecione **OK** > **Criar** para salvar seu perfil.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. [Atribua](../configuration/device-profile-assign.md) o novo perfil de dispositivo.
