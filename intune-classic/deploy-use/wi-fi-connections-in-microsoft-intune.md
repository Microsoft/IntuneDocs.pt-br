---
title: "Conexões Wi-Fi"
description: "Use perfis de Wi-Fi para ajudar os usuários a se conectar a redes Wi-Fi."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5d021abec31a38d7135828fbe06acd4a1a10ee42
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2017
---
# <a name="configure-devices-to-connect-to-your-corporate-wi-fi-networks"></a>Configure dispositivos para se conectar às redes Wi-Fi corporativas

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use os perfis de Wi-Fi do Microsoft Intune para implantar configurações de rede sem fio para usuários e dispositivos na organização. Quando você implantar um perfil de Wi-Fi, os usuários terão acesso ao Wi-Fi de sua empresa sem precisar configurá-lo por conta própria.

Por exemplo, você pode instalar uma nova rede Wi-Fi chamada **Wi-Fi Contoso** e configurar todos os dispositivos iOS para se conectarem a essa rede. Este é o processo:

![Resumo do processo de perfil de Wi-Fi](..\media\wi-fi-process-diagram.png)

1.   Crie um perfil de Wi-Fi que contém as configurações necessárias para se conectar à rede sim fio **Wi-Fi Contoso**.

2.   Implante o perfil para o grupo de usuários com dispositivos iOS.

3.   Os usuários encontram a nova rede **Wi-Fi Contoso** na lista de redes sem fio e podem facilmente se conectar a esta rede.


## <a name="create-a-wi-fi-profile"></a>Criar um perfil de Wi-Fi

Você pode implantar perfis de Wi-Fi para as seguintes plataformas:

-   Android 4.0 e posterior

-   Android for Work   

-   iOS 8.0 e posterior

-   Mac OS X 10.9 e posterior

Para dispositivos que executam os sistemas operacionais Windows 8.1 ou Windows 10 Desktop ou Mobile, você pode importar um perfil de configuração de Wi-Fi que já foi exportado em um arquivo. Para obter detalhes, consulte [Exportar ou importar um perfil de configuração de Wi-Fi para dispositivos Windows](#export-or-import-a-wi-fi-configuration-profile-for-windows-devices).

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** &gt; **Adicionar Política**.

2.  Selecione um dos seguintes tipos de política e clique em **Criar Política**:

    -   Perfil de Wi-Fi (Android 4 e posterior)

    -   Perfil de Wi-Fi (Android for Work)

    -   Perfil de Wi-Fi (iOS 8.0 e posterior)

    -   Perfil de Wi-Fi (Mac OS X 10.9 e posterior)


Não há nenhuma configuração recomendada para este tipo de política. Você deve criar uma política personalizada.

3.  Forneça o nome e a descrição do perfil.

4. Especifique os valores de **Conexões de Rede**.
 - **SSID (Identificador do Conjunto de Serviço)**: selecione esta opção se desejar que os usuários vejam o nome da rede e não o SSID.
 - **Conectar quando a rede não estiver transmitindo seu nome (SSID)**|Selecione esta opção para permitir que dispositivos se conectem à rede quando ela não estiver visível na lista de redes (porque esteja oculta e não esteja transmitindo seu nome).

5. Defina as **Configurações de Segurança** para a plataforma selecionada. As configurações disponíveis dependem do tipos de segurança que você selecionar. Eles estão descritos em [Configurações de segurança](#security-settings).

6. Definir **Configurações de Proxy** (somente iOS e MAC OS X).

    |Nome da configuração|Mais informações|Quando usar|
    |----------------|-------------------|-------------|
    |**Configurações do proxy para esta conexão Wi-Fi**|Escolha o tipo de configurações de proxy:<br /><br />-   **Nenhum** (padrão)<br />-   **Manual** – especifique manualmente a URL e o número da porta do servidor proxy.<br />-   **Automático** – use um arquivo de configuração para configurar o servidor proxy.|Sempre|
    |**Endereço do servidor proxy** e **Número da porta**|Especifique a URL e o número da porta do servidor proxy.|Se **Configurações de proxy para esta conexão Wi-Fi** estiverem definidas como **Manual**|
    |**URL do Servidor Proxy**|Especifique a URL do arquivo que contém as configurações do servidor proxy.|Se as **Configurações de proxy para esta conexão Wi-Fi** estiverem definidas como **Automáticas**|

7.  Salvar o perfil de Wi-Fi

A nova política é exibida no nó **Políticas de Configuração** do espaço de trabalho **Política**. Consulte **Próximas etapas** para obter informações sobre como implantar o perfil.

## <a name="export-or-import-a-wi-fi-configuration-profile-for-windows-devices"></a>Exportar ou importar um perfil de configuração de Wi-Fi para dispositivos Windows

Para dispositivos que executam os sistemas operacionais Windows 8.1 ou Windows 10 Desktop ou Mobile, você pode importar um perfil de configuração de Wi-Fi que já foi exportado em um arquivo.

### <a name="export-a-wi-fi-profile"></a>Exportar um perfil de Wi-Fi
No Windows, você pode usar o utilitário **netsh wlan** para exportar um perfil de Wi-Fi existente para um arquivo XML legível pelo Intune. Em um computador Windows que já tenha o perfil Wi-Fi necessário instalado, realize as seguintes etapas:

1.  Crie uma pasta local para os perfis Wi-Fi exportados. Por exemplo, crie uma pasta chamada **c:\WiFi.**

2.  Abra um prompt de comando como administrador.

3.  Execute o comando `netsh wlan show profiles`, e observe o nome do perfil que você deseja exportar.  Neste exemplo, o nome do perfil é **WiFiName**.

4.  Execute este comando: `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Isso criará um arquivo de perfil de Wi-Fi chamado **"Wi-Fi-WiFiName.xml"** na sua pasta de destino.

### <a name="import-a-wi-fi-profile"></a>Importar um perfil de Wi-Fi
Use **Política de importação Wi-Fi do Windows** para importar um conjunto de configurações de Wi-Fi que podem ser implantadas para os grupos de usuário ou dispositivo necessários.


1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Adicionar Política**.

2.  Configure uma política do tipo **Windows** &gt; **Importação de Wi-Fi (Windows 8.1 e posterior)**.

    Essa política pode ser aplicada a dispositivos que executam sistemas operacionais Windows 8.1 e Windows 10 Desktop e Mobile.

    Você só pode criar e implantar uma política *personalizada* de importação de Wi-Fi do Windows. Configurações recomendadas não estão disponíveis.

3.  Especifique os seguintes valores gerais para a Política de importação Wi-Fi do Windows:

    |Nome da configuração|Mais informações|
    |----------------|--------------------|
    |**Nome**|Insira um nome exclusivo para o perfil de Wi-Fi para identificá-lo no console do Intune.|
    |**Descrição**|Forneça uma descrição do perfil de Wi-Fi e outras informações relevantes que o ajudem a localizá-lo.|

4.  Especifique os seguintes valores sob o cabeçalho **Perfil de Wi-Fi Personalizado**:

    |Nome da configuração|Mais informações|
    |----------------|--------------------|
    |**Arquivo de configuração de perfil**|Escolha **Importar** para selecionar o arquivo XML que contém as configurações de perfil de Wi-Fi que você deseja importar para o Intune.|
    |**Nome do perfil de configuração personalizado (exibido a usuários)**|Escolha como exibir o nome do perfil de configuração de Wi-Fi já que ele será mostrado aos usuários em seu dispositivo.|
    |**Detalhes do perfil de configuração**|Escolha como exibir o código XML para o perfil de configuração que você selecionou.|

5.  Quando terminar, selecione **Salvar Política**.

6.  A nova política é exibida no nó **Políticas de configuração** do espaço de trabalho **Política**.

## <a name="deploy-the-profile"></a>Implantar o perfil

Como um perfil é um tipo de política, use o espaço de trabalho **Política** para implantá-lo.

1.  No espaço de trabalho **Política**, selecione a política que deseja implantar e selecione **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar implantação** :

    -   **Para implantar a política**: selecione um ou mais grupos nos quais deseja implantar a política. Em seguida, escolha **Adicionar** &gt; **OK**.

    -   **Para fechar a caixa de diálogo sem implantá-la**: clique em **Cancelar**.


A página de **Visão Geral** do espaço de trabalho **Política** exibe problemas com a política que exigem sua atenção. Além disso, um resumo de status aparece no espaço de trabalho Painel.

## <a name="security-settings"></a>Configurações de segurança
Estas tabelas contêm os detalhes das configurações de segurança disponíveis para os perfis de Wi-Fi do Mac OS X, do iOS e do Android.

### <a name="security-settings-for-android-devices"></a>Configurações de segurança para dispositivos Android

  |Nome da configuração|Mais informações|Quando usar|
|----------------|--------------------|-------------|
|**Tipo de segurança**|Selecione o protocolo de segurança da rede sem fio:<br /><br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **Sem autenticação (aberta)** se a rede não for segura.|Sempre|
|**Tipo de EAP**|Escolha o tipo de protocolo EAP (Extensible Authentication) usado para autenticar conexões sem fio seguras:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|Caso tenha selecionado o tipo de segurança **WPA-Enterprise/WPA2-Enterprise**.|
|**Selecionar certificados raiz para validação do servidor**|Clique em **Selecionar** e escolha o perfil de certificado raiz confiável usado para autenticar a conexão. Para obter mais informações sobre como criar o perfil de certificado raiz confiável, consulte [Proteger o acesso a recursos com perfis de certificado](secure-resource-access-with-certificate-profiles.md).|Caso tenha selecionado qualquer **Tipo de EAP**.|
|**Método de autenticação**|Selecione o método de autenticação usado para a conexão:<br /><br />-   **Certificados** para especificar o certificado do cliente<br />-   **Nome de Usuário e Senha** para especificar um método de autenticação diferente|O **tipo de EAP** é **PEAP** ou **EAP-TTLS**.|
|**Selecione um método que não seja EAP para autenticação (Identidade interna)**|Selecione como você fará a autenticação da conexão:<br /><br />-   **Nenhum**<br />-   **Senha não criptografada (PAP)**<br />-   **Protocolo CHAP**<br />-   **Microsoft CHAP (MS-CHAP)**<br />-   **Microsoft CHAP Versão 2 (MS-CHAP v2)**<br /><br />As opções disponíveis dependem do tipo de EAP selecionado.|O **Método de autenticação** é **Nome de Usuário e Senha**.|
|**Habilitar privacidade de identidade (Identidade Externa)**|Especifique o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor. Durante a autenticação, essa identidade anônima é enviada inicialmente. A identificação real é enviada em um túnel seguro.|O **tipo de EAP** é **PEAP** ou **EAP-TTLS**.|
|**Selecione um certificado de cliente para autenticação de cliente (certificado de identidade)**|Clique em **Selecionar** e escolha o perfil de certificado SCEP usado para autenticar a conexão. Para obter mais informações sobre como criar um perfil de certificado SCEP, consulte [Proteger o acesso a recursos com perfis de certificado](secure-resource-access-with-certificate-profiles.md).|Se o tipo de segurança for **WPA-Enterprise/WPA2-Enterprise** e qualquer **Tipo de EAP** for selecionado.|

### <a name="security-settings-for-ios-and-mac-os-x-devices"></a>Configurações de segurança para dispositivos iOS e Mac OS X

  |Nome da configuração|Mais informações|Quando usar|
|----------------|--------------------|-------------|
|**Tipo de segurança**|Selecione o protocolo de segurança de rede sem fio:<br /><br />-   **WPA-Personal/WPA2-Personal**<br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **WEP**<br />-   **Sem autenticação (aberta)** se a rede não for segura.|Sempre|
|**Tipo de EAP**|Escolha o tipo de protocolo EAP (Extensible Authentication) usado para autenticar conexões sem fio seguras:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|Se você tiver selecionado um tipo de segurança de **WPA-Enterprise/WPA2-Enterprise**.|
|**Nomes de certificado do servidor confiáveis**|Selecione o perfil de certificado raiz confiável usado para autenticar a conexão. Para obter mais informações sobre como criar o perfil de certificado raiz confiável, consulte [Proteger o acesso a recursos com perfis de certificado](secure-resource-access-with-certificate-profiles.md).|Caso tenha selecionado um tipo de EAP **EAP-TLS**, **PEAP**, **EAP-TTLS** ou **EAP-FAST**.|
|**Usar Credencial de Acesso Protegido (PAC)**|Selecione para usar credenciais de acesso protegido para estabelecer um túnel autenticado entre o cliente e o servidor de autenticação. Um arquivo PAC existente será usado se estiver presente.|O **tipo de EAP** é **EAP-FAST**.|
|**Provisionar PAC**|Define o arquivo PAC em seus dispositivos.<br /><br />Quando usado, você também pode selecionar **Provisionar PAC anonimamente** para garantir que o arquivo PAC seja definido sem autenticar o servidor.|Caso **Usar Credencial PAC (Protected Access)** esteja selecionado.|
|**Método de autenticação**|Selecione o método de autenticação usado para a conexão:<br /><br /><ul><li>**Certificados** para especificar o certificado de cliente</li><li>**Nome de Usuário e Senha** para especificar um dos seguintes métodos não EAP para autenticação (também conhecido como identidade interna):<br /><br /><ul><li>**Nenhum**</li><li>**Senha não criptografada (PAP)**</li><li>**Challenge Heshake Authentication Protocol (CHAP)**</li><li>**Microsoft CHAP (MS-CHAP)**</li><li>**Microsoft CHAP Versão 2 (MS-CHAP v2)**</li><li>**EAP-TLS**</li></ul></li></ul>|Caso o **tipo de EAP** seja **PEAP** ou **EAP-TTLS**.|
|**Selecione um certificado de cliente para autenticação de cliente (certificado de identidade)**|Selecione o perfil de certificado SCEP usado para autenticar a conexão. Para obter mais informações sobre como criar um perfil de certificado SCEP, consulte [Proteger o acesso a recursos com perfis de certificado](secure-resource-access-with-certificate-profiles.md).|Caso o tipo de segurança seja **WPA-Enterprise/WPA2-Enterprise** e o **tipo de EAP** seja **EAP-TLS**, **PEAP** ou **EAP-TTLS**.|
|**Habilitar privacidade de identidade (Identidade Externa)**|Especifique o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor.<br /><br />Durante a autenticação, essa identidade anônima é enviada inicialmente. A identificação real é enviada em um túnel seguro.|Quando o **tipo de EAP** é definido como **PEAP**, **EAP-TTLS** ou **EAP-FAST**.|


### <a name="see-also"></a>Consulte também
Saiba como criar um perfil de Wi-Fi com uma chave pré-compartilhada no [Perfil de Wi-Fi de chave pré-compartilhado](pre-shared-key-wi-fi-profile.md).
