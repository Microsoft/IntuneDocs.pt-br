---
title: Como configurar certificados com o Intune
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: aprenda a usar o Intune para criar e atribuir certificados que ajudarão a proteger Wi-Fi, VPN e outras conexões."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: d1c1833ea7fe9e794a70b2b2536f44801b68fa7e
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Como configurar certificados no Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ao conceder aos usuários acesso a recursos corporativos por meio de VPN, Wi-Fi ou perfis de email, você pode proteger o acesso usando um certificado instalado em cada dispositivo de usuário. O fluxo de trabalho de alto nível é o seguinte:

1. Verifique se você tem a infraestrutura de certificado correta em vigor. Você pode usar os [Certificados SCEP](configure-certificate-infrastructure-for-scep.md) e os [Certificados PKCS](configure-certificate-infrastructure-for-pfx.md).
2. Instale um certificado raiz ou um certificado de CA (Autoridade de Certificação) intermediário em cada dispositivo para que o dispositivo reconheça a legitimidade da autoridade de certificação. Para fazer isso, crie e atribua um **perfil de certificado confiável**. Quando você atribui esse perfil, os dispositivos que você gerencia com o Intune solicitarão e receberão o certificado raiz. Você precisa criar um perfil separado para cada plataforma. Perfis de certificado confiável estão disponíveis para as seguintes plataformas:
    - iOS 8.0 e posterior
    - macOS 10.9 e posterior
    - Android 4.0 e posterior <!--Android for Work --->
    - Windows 8.1 e posterior
    - Windows Phone 8.1 e posterior
    - Windows 10 e posterior
3. Crie perfis de certificado para que os dispositivos solicitem um certificado a ser usado para autenticação de VPN, Wi-Fi e acesso por email. Você pode criar e implantar um perfil de certificado **PKCS** ou **SCEP** para dispositivos em execução nestas plataformas:
    - iOS 8.0 e posterior
    - Android 4.0 e posterior
    - Android for Work
    - Windows 10 (Desktop e Mobile) e posterior

    Somente é possível usar um perfil de certificado SCEP nestas plataformas:

-     macOS 10.9 e posterior
-     Windows Phone 8.1 e posterior

Você deve criar um perfil separado para cada plataforma de dispositivo. Ao criar o perfil, associe-o ao perfil de certificado raiz confiável já criado.

### <a name="further-considerations"></a>Considerações adicionais

- Se não tiver uma Autoridade de Certificação Corporativa, você precisará criar uma.
- Com base em suas plataformas de dispositivo, se decidir usar o perfil de SCEP (Protocolo de Registro de Certificado Simplificado), você também precisará configurar um NDES (Serviço de Registro de Dispositivo de Rede).
- Se você planeja usar perfis SCEP ou PKCS, precisará baixar e configurar o Microsoft Intune Certificate Connector.

## <a name="before-you-start"></a>Antes de começar


### <a name="if-you-want-to-use-scep-certificates"></a>Se você quiser usar certificados SCEP

Cumpra os pré-requisitos necessários em [Infraestrutura de certificado para SCEP](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep).

### <a name="if-you-want-to-use-pkcs-certificates"></a>Se você quiser usar certificados PKCS

Cumpra os pré-requisitos necessários em [Infraestrutura de certificado para PKCS](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx).

## <a name="task-1-export-the-trusted-root-ca-certificate"></a>Tarefa 1: exportar o certificado de AC raiz confiável
Exporte o certificado de AC (Autoridade de Certificação) Raiz Confiável como um arquivo **.cer** da autoridade de certificação emissora ou de qualquer dispositivo que confie em sua autoridade de certificação emissora. Não exporte a chave privada.

Ao configurar um perfil de certificado confiável, você importará esse certificado.

## <a name="task-2-create-trusted-certificate-profiles"></a>Tarefa 2: criar perfis de certificado confiável
Você deverá criar um perfil de certificado confiável antes de criar um perfil de certificado SCEP ou PKCS. Você precisa de um perfil de certificado confiável e um perfil SCEP ou PKCS para cada plataforma de dispositivo.

### <a name="to-create-a-trusted-certificate-profile"></a>Para criar um perfil de certificado Confiável

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de certificado confiável.
5. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado confiável. No momento, é possível escolher uma das seguintes plataformas para as configurações de certificado:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**
6. Na lista suspensa de **Tipo de perfil**, escolha **Certificado confiável**.
7. Navegue até o certificado salvo na tarefa 1 e clique em **OK**.
8. Somente para dispositivos Windows 8.1 e Windows 10, selecione o **Repositório de Destino** para o certificado confiável de:
    - **Repositório de certificados do computador – Raiz**
    - **Repositório de certificados do computador – Intermediário**
    - **Repositório de certificados do usuário – Intermediário**
8. Após terminar, escolha **OK**, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](how-to-assign-device-profiles.md).


> [!Note]
> Dispositivos Android exibirão um aviso de que terceiros instalaram um certificado confiável.

## <a name="task-3-create-scep-or-pkcs-certificate-profiles"></a>Tarefa 3: criar perfis de certificado SCEP ou PKCS
Depois de criar um perfil de certificado confiável, crie perfis de certificado SCEP ou PKCS para cada plataforma que você deseja usar. Quando você cria um perfil de certificado SCEP, deverá especificar um perfil de certificado confiável para essa mesma plataforma. Isso vincula os dois perfis de certificado, mas você ainda deve atribuir cada perfil separadamente.

### <a name="to-create-an-scep-certificate-profile"></a>Para criar um perfil de certificado SCEP

1. No Portal do Azure, selecione a carga de trabalho **Configurar dispositivos**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de certificado SCEP.
5. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado SCEP. No momento, é possível escolher uma das seguintes plataformas para as configurações de restrição de dispositivo:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **Certificado SCEP**.
7. Na folha **Certificado SCEP**, defina as seguintes configurações:
    - **Período de validade do certificado** – Se você executar o comando **certutil – setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** na AC emissora, o que permite usar um período de validade personalizado, poderá especificar a quantidade de tempo restante antes que o certificado expire.<br>Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também tem que ser inferior ao período de validade restante do certificado da AC emissora. 
    - **KSP (provedor de armazenamento de chaves)** (Windows Phone 8.1, Windows 8.1 e Windows 10) – Especifique o local em que a chave do certificado será armazenada. Escolha um destes valores:
        - **Registrar no KSP do TPM (Trusted Platform Module) se existir; caso contrário, no KSP de Software**
        - **Registrar no KSP do TPM (Trusted Platform Module); caso contrário, falha**
        - **Registrar no Passport; caso contrário, falha (Windows 10 e posterior)**
        - **Registrar no Software KSP**
    - **Formato de nome da entidade** – Na lista, selecione como o Intune cria automaticamente o nome da entidade na solicitação de certificado. Se o certificado for para um usuário, você também pode incluir o endereço de email do usuário no nome da entidade. Escolha:
        - **Não configurado**
        - **Nome comum**
        - **Nome comum incluindo email**
        - **Nome comum como email**
    - **Nome alternativo da entidade** – Especifique como o Intune criará automaticamente os valores para o SAN (nome alternativo da entidade) na solicitação de certificado. Se tiver selecionado um tipo de certificado de usuário, por exemplo, você pode incluir o UPN no nome alternativo da entidade. Se o certificado do cliente for usado para autenticar em um Servidor de Políticas de Rede, você deve definir o nome alternativo da entidade como o UPN. 
    - **Uso de chave** – Especifique as opções de uso de chave para o certificado. Você pode escolher entre as seguintes opções: 
        - **Codificação de chave:** permitir a troca de chaves apenas quando a chave for criptografada. 
        - **Assinatura digital:** permitir a troca de chaves apenas quando uma assinatura digital ajudar a proteger a chave. 
    - **Tamanho da chave (bits)** – Selecione o número de bits que estão contidos na chave. 
    - **Algoritmo de hash:** (Android, Windows Phone 8.1, Windows 8.1 e Windows 10) – Selecione um dos tipos de algoritmo de hash disponíveis para ser usado com esse certificado. Selecione o nível mais alto de segurança que dá suporte aos dispositivos de conexão. 
    - **Certificado Raiz** – Escolha um perfil de certificado de AC raiz configurado anteriormente e atribuído ao usuário ou dispositivo. Esse certificado AC deve ser o certificado raiz da AC que emite o certificado que você está configurando nesse perfil de certificado. 
    - **Uso estendido da chave** – Escolha **Adicionar** para adicionar valores para a finalidade desejada do certificado. Na maioria dos casos, o certificado exigirá **Autenticação de cliente** para que o usuário ou dispositivo possa autenticar-se em um servidor. No entanto, você pode adicionar outros usos da chave conforme necessário. 
    - **Configurações de Registro**
        - **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
        - **URLs de servidor SCEP** – Especifique uma ou mais URLs para os servidores de NDES que emitirão certificados por meio do protocolo SCEP. 
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.

Siga as instruções na página de configuração do perfil para definir as configurações de perfil de certificado SCEP.
>[!Note]
> Somente para dispositivos iOS: em Formato de nome da entidade, selecione Personalizado para inserir um formato de nome da entidade personalizado.
> As duas variáveis que atualmente têm suporte para o formato personalizado são **Nome Comum (CN)** e **Email (E)**. Usando uma combinação dessas cadeias de caracteres variáveis e estáticas, é possível criar um formato de nome de entidade personalizado, como este: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** Nesse exemplo, você criou um formato de nome de entidade que, além das variáveis CN e E, usa cadeias de caracteres para os valores de Unidade Organizacional, Organização, Local, Estado e País. [Este tópico](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) mostra a função **CertStrToName** função e suas cadeias de caracteres com suporte.


### <a name="to-create-a-pkcs-certificate-profile"></a>Para criar um perfil de certificado PKCS

No Portal do Azure, selecione a carga de trabalho **Configurar dispositivos**.
2. Na folha **Configurações do dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, clique em **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de certificado PKCS.
5. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado PKCS de:
    - **Android**
    - **iOS**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **Certificado PKCS**.
7. Na folha **Certificado PKCS**, defina as seguintes configurações:
    - **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
    - **Período de validade do certificado** – Se você executar o comando **certutil – setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** na AC emissora, o que permite usar um período de validade personalizado, poderá especificar a quantidade de tempo restante antes que o certificado expire.<br>Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também tem que ser inferior ao período de validade restante do certificado da AC emissora.
    - **KSP (provedor de armazenamento de chaves)** (Windows 10) –
    - **Autoridade de certificação** -
    - **Nome da autoridade de certificação** -
    - **Nome do modelo de certificado** – Insira o nome de um modelo de certificado que o Serviço de Registro de Dispositivo de Rede está configurado para usar e que foi adicionado a uma AC emissora.
    Verifique se o nome corresponde exatamente a um dos modelos de certificado relacionados no registro do servidor que executa o Serviço de Registro de Dispositivo de Rede. Certifique-se de especificar o nome do modelo de certificado e não o nome para exibição do modelo de certificado. 
    Para localizar os nomes dos modelos de certificado, navegue até a seguinte chave: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP. Você verá os modelos de certificado listados como os valores para **EncryptionTemplate**, **GeneralPurposeTemplate**e **SignatureTemplate**. Por padrão, o valor para todos os modelos de certificado é IPSECIntermediateOffline, que mapeia até o nome de exibição do modelo do **IPsec (solicitação offline)**. 
    - **Formato de nome da entidade** – Na lista, selecione como o Intune cria automaticamente o nome da entidade na solicitação de certificado. Se o certificado for para um usuário, você também pode incluir o endereço de email do usuário no nome da entidade. Escolha:
        - **Não configurado**
        - **Nome comum**
        - **Nome comum incluindo email**
        - **Nome comum como email**
    - **Nome alternativo da entidade** – Especifique como o Intune criará automaticamente os valores para o SAN (nome alternativo da entidade) na solicitação de certificado. Se tiver selecionado um tipo de certificado de usuário, por exemplo, você pode incluir o UPN no nome alternativo da entidade. Se o certificado do cliente for usado para autenticar em um Servidor de Políticas de Rede, você deve definir o nome alternativo da entidade como o UPN.
    - **Uso estendido da chave** (Android) – Escolha **Adicionar** para adicionar valores para a finalidade desejada do certificado. Na maioria dos casos, o certificado exigirá **Autenticação de cliente** para que o usuário ou dispositivo possa autenticar-se em um servidor. No entanto, você pode adicionar outros usos da chave conforme necessário. 
    - **Certificado Raiz** (Android) – Escolha um perfil de certificado de AC raiz configurado anteriormente e atribuído ao usuário ou dispositivo. Esse certificado AC deve ser o certificado raiz da AC que emite o certificado que você está configurando nesse perfil de certificado.
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.

## <a name="task-4-assign-certificate-profiles"></a>Tarefa 4: atribuir perfis de certificado

Antes de atribuir perfis de certificado a grupos, considere o seguinte:

- Quando você atribui perfis de certificado a grupos, o arquivo de certificado do perfil do Certificado de Autoridade de Certificação Confiável é instalado no dispositivo. O dispositivo usa o perfil de certificado SCEP ou PKCS para criar uma solicitação de certificado pelo dispositivo.
- Os perfis de certificado são instalados somente em dispositivos que executam a plataforma que você usa ao criar o perfil.
- Você pode implantar perfis de certificado para coleções de usuários ou coleções de dispositivos.
- Para publicar um certificado em um dispositivo rapidamente depois que o dispositivo for registrado, implante o perfil de certificado para um grupo de usuários em vez de um grupo de dispositivos. Se você implantar um grupo de dispositivos, um registro de dispositivo completo será necessário para que o dispositivo receba políticas.
- Embora você implante cada perfil separadamente, também precisará implantar a AC Raiz Confiável e o perfil SCEP ou PKCS. Caso contrário, a política de certificação SCEP ou PKCS falhará.

## <a name="next-steps"></a>Próximas etapas
Consulte [Como atribuir perfis de dispositivo](how-to-assign-device-profiles.md) para obter informações gerais sobre como atribuir perfis de dispositivo.

