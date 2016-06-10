---
# required metadata

title: Conexões Wi-Fi | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Conexões Wi-Fi no Microsoft Intune
Use os perfis de Wi-Fi do Microsoft Intune para implantar configurações de rede sem fio para usuários e dispositivos na organização. Essas configurações simplificam as conexões de usuário a redes sem fio.

Por exemplo, você pode instalar uma nova rede Wi-Fi chamada **Wi-Fi Contoso** e configurar todos os dispositivos iOS para se conectarem a essa rede. Este é o processo:

1.   Crie um perfil de Wi-Fi contendo as configurações necessárias para conectar à rede sim fio **Wi-Fi Contoso**.

2. Implante o perfil para o grupo de usuários com dispositivos iOS.

3.   Os usuários encontram a nova rede **Wi-Fi Contoso** na lista de redes sem fio e podem facilmente se conectar a esta rede.

Você pode implantar perfis de Wi-Fi para as seguintes plataformas:

-   Android 4.0 e posterior

-   iOS 7.1 e posterior

-   Mac OS X 10.9 e posterior

Para dispositivos que executam o Windows 8.1 e posterior, você pode importar um perfil de configuração de Wi-Fi que já foi exportado em um arquivo. Para saber detalhes, consulte Importar um perfil de Wi-Fi, mais adiante neste tópico.

## Como criar um perfil de Wi-Fi

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Adicionar Política**.

2.  Selecione um dos seguintes tipos de política e clique em **Criar Política**:

    -   **Perfil de Wi-Fi (Android 4 e posterior)**

    -   **Perfil de Wi-Fi (iOS 7.1 e posterior)**

    -   **Perfil de Wi-Fi (Mac OS X 10.9 e posterior)**

    Não há nenhuma configuração recomendada para este tipo de política. Você deve criar uma política personalizada.

3.  Forneça o nome e a descrição do perfil.

4. Especifique os valores de **Conexões de Rede** :

  |Configuração|Mais informações| |-----------|--------------------|
|**Nome da rede**|Especifique um nome descritivo para a rede sem fio. Esse é o nome exibido no dispositivo do usuário quando ele escolher uma rede sem fio.| |**SSID (Identificador do Conjunto de Serviços)**| Especifique o SSID da rede sem fio no qual você deseja que os dispositivos se conectem. O SSID diferencia maiúsculas de minúsculas e não é exibido aos usuários. | |**Conectar automaticamente quando esta rede estiver no intervalo**| Selecione esta opção para conectar automaticamente os dispositivos na rede sem fio quando ela estiver no intervalo. | |**Conectar quando a rede não estiver transmitindo seu nome (SSID)**| Selecione esta opção para permitir que dispositivos conectem-se à rede quando ela não está visível na lista de redes (porque está oculta e não está transmitindo seu nome). |

5. Defina as **Configurações de Segurança** para a plataforma selecionada. As configurações disponíveis dependem do tipos de segurança que você selecionar.

  #### Para dispositivos Android

  |Nome da configuração|Mais informações|Usar quando:| |----------------|--------------------|-------------|
|**Tipo de segurança**|Selecione o protocolo de segurança para a rede sem fio:<br /><br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **Nenhuma autenticação (aberta)** se a rede não for segura.|Sempre| |**Tipo de EAP**|Escolha o tipo de EAP (Protocolo de Autenticação Extensível) usado para autenticar conexões sem fio seguras:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|Você selecionou o tipo de segurança **WPA-Enterprise/WPA2-Enterprise**.| |**Selecionar certificados raiz para validação do servidor**|Clique em **Selecionar**, em seguida, escolha o perfil de certificado raiz confiável usado para autenticar a conexão. **Importante:** para criar o perfil de certificado raiz confiável, consulte [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Proteger o acesso a recursos com perfis de certificado).|Qualquer **tipo de EAP** é selecionado.| |**Método de autenticação**|Selecione o método de autenticação da conexão:<br /><br />-   **Certificados** para especificar o certificado de cliente<br />-   **Nome de Usuário e Senha** para especificar um método diferente de autenticação| O **tipo de EAP** é **PEAP** ou **EAP-TTLS**. | |**Selecione um método não EAP para autenticação (identidade interna)**| Selecione como você fará a autenticação da conexão:<br /><br />-   **Nenhum**<br />-   **Senha não criptografada (PAP)**<br />-   **Challenge Handshake Authentication Protocol (CHAP)**<br />-   **Microsoft CHAP (MS-CHAP)**<br />-   **Microsoft CHAP versão 2 (MS-CHAP v2)**<br /><br />As opções disponíveis dependem do tipo EAP selecionado. | O **Método de autenticação** é **Nome de Usuário e Senha**. | |**Habilitar privacidade de identidade (identidade externa)**| Especifique o texto enviado em resposta a uma solicitação de identidade EAP. Esse texto pode ser qualquer valor. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro. | O **tipo de EAP** é **PEAP** ou **EAP-TTLS**. | |**Selecione um certificado de cliente para autenticação de cliente (certificado de identidade)**| Clique em **Selecionar**, em seguida, escolha o perfil de certificado SCEP usado para autenticar a conexão. **Importante:** para criar um perfil de certificado SCEP, consulte [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Proteger o acesso a recursos com perfis de certificado).|O tipo de segurança é **WPA-Enterprise/WPA2-Enterprise**, e qualquer **tipo de EAP** é selecionado.|

  #### Para dispositivos iOS e Mac OS X

  |Nome da configuração|Mais informações|Usar quando:| |----------------|--------------------|-------------|
|**Tipo de segurança**|Selecione o protocolo de segurança da rede sem fio:<br /><br />-   **WPA-Personal/WPA2-Personal**<br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **WEP**<br />-   **Nenhuma autenticação (aberta)** se a rede não for segura.|Sempre| |**Tipo de EAP**|Escolha o tipo de EAP (Protocolo de Autenticação Extensível) usado para autenticar conexões sem fio seguras:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|Você selecionou um tipo de segurança de **WPA-Enterprise/WPA2-Enterprise**.| |**Nomes de certificado do servidor confiável**|Selecione o perfil de certificado raiz confiável usado para autenticar a conexão. **Importante:** para criar o perfil de certificado raiz confiável, consulte [Proteger o acesso a recursos com perfis de certificado](secure-resource-access-with-certificate-profiles.md). |Você selecionou um tipo de EAP de **EAP-TLS**, **PEAP**, **EAP-TTLS** ou **EAP-FAST**. | |**Usar PAC (Protected Access Credential)**| Selecione para usar credenciais de acesso protegido para estabelecer um túnel autenticado entre o cliente e o servidor de autenticação. Um arquivo PAC existente será usado se estiver presente. | O **tipo de EAP** é **EAP-FAST**. | |**Provisionar PAC**| Provisiona o arquivo PAC para seus dispositivos.<br /><br />Quando usado, você também pode selecionar **Provisionar PAC Anonimamente** para garantir que o arquivo PAC seja provisionado sem autenticar o servidor.|**Usar PAC (Protected Access Credential)** é selecionado.| |**Método de autenticação**|Selecione o método de autenticação usado para a conexão:<br /><br /><ul><li>**Certificados** para especificar o certificado de cliente</li><li>**Nome de Usuário e Senha** para especificar um dos seguintes métodos não EAP para autenticação (também conhecido como identidade interna):<br /><br /><ul><li>**Nenhum**</li><li>**Senha não criptografada (PAP)**</li><li>**Challenge Handshake Authentication Protocol (CHAP)**</li><li>**Microsoft CHAP (MS-CHAP)**</li><li>**Microsoft CHAP versão 2 (MS-CHAP v2)**</li><li>**EAP-TLS**</li></ul></li></ul>|O **tipo EAP** é **PEAP** ou **EAP-TTLS**.| |**Selecione um certificado de cliente para autenticação de cliente (Certificado de Identidade)**|Selecione o perfil de certificado SCEP usado para autenticar a conexão. **Importante:** para criar um perfil de certificado SCEP, consulte [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Proteger o acesso a recursos com perfis de certificado).|Quando o tipo de segurança é **WPA-Enterprise/WPA2-Enterprise** e o **tipo de EAP** é **EAP-TLS**, **PEAP** ou **EAP-TTLS**| |**Habilitar privacidade de identidade (identidade exterior)**|Especifique o texto que é enviado para uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor.<br /><br />Durante a autenticação, essa identidade anônima é enviada inicialmente, seguida pela identificação real enviada em um túnel seguro.|Quando o **tipo de EAP** é definido como **PEAP**, **EAP-TTLS** ou **EAP-FAST**.|

6. (Somente iOS e MAC OS X) Definir **Configurações de Proxy**

    |Nome da configuração|Mais informações|Use quando:|
    |----------------|-------------------|-------------|
    |**Configurações de proxy para esta conexão Wi-Fi**|Escolha o tipo de configurações de proxy:<br /><br />-   **Nenhum** (padrão)<br />-   **Manual** - Especifique manualmente a URL e o número da porta do servidor proxy.<br />-   **Automático** – Use um arquivo de configuração para configurar o servidor proxy.|Sempre|
    |**Endereço do servidor proxy** e **Número da porta**|Especifique a URL e o número da porta do servidor proxy.|**Configurações de proxy para esta conexão Wi-Fi** é definido como **Manual**|
    |**URL do servidor proxy**|Especifique a URL do arquivo que contém as configurações do servidor proxy.|**Configurações de proxy para esta conexão Wi-Fi** é definido como **Automático**|

7.  Salvar o perfil de Wi-Fi

A nova política é exibida no nó **Políticas de Configuração** do espaço de trabalho **Política**. Consulte **Próximas etapas** para obter informações sobre como implantar o perfil.

## Exportar ou importar um perfil de configuração de Wi-Fi (somente Windows 8.1 e posterior)

### Exportar um perfil de Wi-Fi
No Windows, você pode usar o utilitário **netsh wlan** para exportar um perfil de Wi-Fi existente para um arquivo XML legível pelo Intune. Em um computador Windows que já tenha o perfil de WiFi necessário instalado, siga o procedimento a seguir.

1.  Crie uma pasta local para os perfis Wi-Fi exportados, como c:\WiFi

2.  Abra um Prompt de Comando como Administrador.

3.  Execute o comando `netsh wlan show profiles`, e observe o nome do perfil que você deseja exportar.  Neste exemplo, o nome do perfil é *WiFiName*.

4.  Execute este comando: `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Isso criará um arquivo de perfil de Wi-Fi chamado "Wi-Fi-WiFiName.xml” na sua pasta de destino.

## Importar um perfil de Wi-Fi
Use **Política de importação Wi-Fi do Windows** para importar um conjunto de configurações de Wi-Fi que podem ser implantadas para os grupos de usuário ou dispositivo necessários. O procedimento para exportar um perfil Wi-Fi é descrito em

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Adicionar Política**.

2.  Configure uma política do tipo **Windows** &gt; **Política de Importação de Wi-Fi do Windows**.

    Você só pode criar e implantar uma política personalizada do perfil de Wi-Fi do Windows. Configurações recomendadas não estão disponíveis.

3.  Especifique os seguintes valores gerais para a Política de importação Wi-Fi do Windows:

    |Nome da configuração|Mais informações|
    |----------------|--------------------|
    |**Nome**|Insira um nome exclusivo para o perfil de Wi-Fi para identificá-lo no console do Intune.|
    |**Descrição**|Forneça uma descrição do perfil de Wi-Fi e outras informações relevantes que o ajudem a localizá-lo.|

4.  Especifique os seguintes valores sob o cabeçalho **Perfil de Wi-Fi Personalizado**:

    |Nome da configuração|Mais informações|
    |----------------|--------------------|
    |**Arquivo de configuração de perfil**|Clique em **Importar** para selecionar o arquivo XML que contém as configurações de perfil de Wi-Fi que você deseja importar para o Intune.|
    |**Nome do perfil de configuração personalizada (exibido aos usuários)**|Exibe o nome do perfil de configuração de Wi-Fi como ele será mostrado aos usuários em seu dispositivo.|
    |**Detalhes da configuração do perfil**|Exibe o código XML para o perfil de configuração selecionado.|

5.  Quando tiver terminado, clique em **Salvar política**.

6.  A nova política é exibida no nó **Políticas de configuração** do espaço de trabalho **Política** .

## Implantar a política

1.  No espaço de trabalho **Política** , selecione a política que deseja implantar e clique em **Gerenciar Implantação**.

2.  Na caixa de diálogo **Gerenciar implantação** :

    -   **Para implantar a política** - Selecione um ou mais grupos ao qual você deseja implantar a política, clique **Adicionar** &gt; **OK**.

    -   **Para fechar a caixa de diálogo sem implantá-la** - clique em **Cancelar**.


Um resumo de status e alertas na página **Visão geral** do espaço de trabalho **Política** identifica problemas com a política que exigem atenção. Além disso, um resumo de status aparece no espaço de trabalho Painel.

### Consulte também
Saiba como criar um perfil de Wi-Fi com uma chave pré-compartilhada no [Perfil de Wi-Fi de chave pré-compartilhado](pre-shared-key-wi-fi-profile.md)


<!--HONumber=May16_HO3-->


