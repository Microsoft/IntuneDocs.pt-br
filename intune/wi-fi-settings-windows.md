---
title: Configurações de Wi-Fi para dispositivos Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil de configuração de Wi-Fi usando as configurações de Wi-Fi para dispositivos Windows 10 e posterior no Microsoft Intune. Defina configurações Básicas ou configurações de nível empresarial.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f6532c63612b806f9824f5b9ca98f1ebbbc943f
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321590"
---
## <a name="wi-fi-settings-for-windows-10-and-later-devices-in-intune"></a>Configurações de Wi-Fi para dispositivos Windows 10 e posterior no Intune

As configurações de Wi-Fi são usadas em um perfil de configuração que se aplica a dispositivos que executam o Windows 10 e posterior. As opções são:

- Básico
- Enterprise

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de dispositivo](device-profile-create.md).

## <a name="settings-for-basic-and-enterprise-profiles"></a>Configurações para perfis básico e empresarial

- **Nome de Wi-Fi (SSID)**: abreviação de identificador SSID. Esse valor é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **Nome da conexão** definido ao escolher a conexão.
- **Nome da conexão**: insira um nome amigável para essa conexão Wi-Fi. O texto inserido é o nome que os usuários veem ao navegarem pelas conexões disponíveis no dispositivo.
- **Conectar automaticamente quando estiver no intervalo**: quando essa opção estiver marcada como **Sim**, os dispositivos se conectarão automaticamente quando estiverem no intervalo dessa rede. Quando ela estiver marcada como **Não**, os dispositivos não se conectarão automaticamente.
  - **Conectar-se à rede preferencial, se disponível**: se os dispositivos estiverem no intervalo de uma rede preferencial, escolha **Sim** para usar a rede preferencial. Escolha **Não** para usar a rede Wi-Fi nesse perfil de configuração.

    Por exemplo, crie uma rede Wi-Fi **ContosoCorp** e use **ContosoCorp** dentro desse perfil de configuração. Você também tem uma rede Wi-Fi **ContosoGuest** dentro do intervalo. Quando os dispositivos corporativos estão dentro do intervalo, você deseja que eles se conectem automaticamente a **ContosoCorp**. Nesse cenário, defina a propriedade **Conectar-se à rede preferencial se disponível** como **Não**.

  - **Conectar-se a esta rede, mesmo quando ela não difundir seu SSID**: escolha **Sim** para que o perfil de configuração se conecte automaticamente à rede, mesmo quando a rede estiver oculta (ou seja, seu SSID não for difundido publicamente). Escolha **Não** se você não deseja que esse perfil de configuração se conecte à rede oculta.

- **Configurações de Proxy da Empresa**: opte por usar as configurações de proxy em sua organização. Suas opções:
  - **Nenhum**: nenhuma configuração de proxy é definida.
  - **Configurar manualmente**: insira o **Endereço de IP do servidor proxy** e o **Número da porta**.
  - **Configurar automaticamente**: insira a URL que aponta para um script PAC (configuração automática de proxy). Por exemplo, insira `http://proxy.contoso.com/proxy.pac`.

## <a name="settings-for-basic-profiles-only"></a>Configurações apenas para perfis básicos

- **Tipo de Segurança Sem Fio**: insira o protocolo de segurança usado para autenticar dispositivos na rede. As opções são:
  - **Abrir (sem autenticação)**: use essa opção somente se a rede não for segura.
  - **WPA/WPA2-Personal**

## <a name="settings-for-enterprise-profiles-only"></a>Configurações apenas para perfis empresariais

- **SSO (logon único)**: permite que você configure o SSO (logon único), em que as credenciais são compartilhadas para a conexão do computador e da rede Wi-Fi. As opções são:
  - **Desabilitar**: desabilita o comportamento do SSO. O usuário precisa autenticar à rede separadamente.
  - **Habilitar antes de o usuário se autenticar no dispositivo**: use o SSO para se autenticar à rede logo antes do processo de entrada do usuário.
  - **Habilitar depois que o usuário entrar no dispositivo**: use o SSO para se autenticar à rede imediatamente após a conclusão do processo de entrada do usuário.
  - **Tempo máximo de autenticação antes do tempo limite**: insira o número máximo de segundos a aguardar antes da autenticação com a rede, de 1 a 120 segundos.
  - **Permitir que o Windows solicite ao usuário credenciais de autenticação adicionais**: a escolha da opção **Sim** permitirá que o sistema Windows solicite ao usuário credenciais adicionais se for exigido pelo método de autenticação. Escolha **Não** para ocultar esses prompts.

- **Habilitar o cache da Chave PMK**: selecione **Sim** para armazenar em cache o PMK usado na autenticação. Esse cache normalmente permite que a autenticação na rede seja concluída mais rapidamente. Escolha **Não** para forçar o handshake de autenticação ao se conectar à rede Wi-Fi todas as vezes.

  - **Tempo máximo que um PMK é armazenado em cache**: insira o número de minutos que uma Chave PMK é armazenada no cache, de 5 a 1.440 minutos.
  - **Número máximo de PMKs armazenados em cache**: insira o número de chaves armazenadas em cache, de 1 a 255.

- **Habilitar pré-autenticação**: a pré-autenticação permite que o perfil seja autenticado em todos os pontos de acesso da rede no perfil antes da conexão. Ao mover entre pontos de acesso, a pré-autenticação reconecta o usuário ou os dispositivos mais rapidamente. Escolha **Sim** para que o perfil se autentique em todos os pontos de acesso nessa rede que estão dentro do intervalo. Escolha **Não** para exigir que o usuário ou o dispositivo se autentique em cada ponto de acesso separadamente.

  - **Número máximo de tentativas de pré-autenticação**: insira o número de tentativas de pré-autenticação, de 1 a 16.

- **Tipo de EAP**: escolha o tipo de protocolo EAP usado para autenticar conexões sem fio seguras. Suas opções:

  - **EAP-SIM**
  - **EAP-TLS**
  - **EAP-TTLS**
  - **PEAP Protegido** (PEAP)

### <a name="more-options-when-you-choose-the-eap-type"></a>Mais opções ao escolher o tipo de EAP

> [!NOTE]
> Atualmente, apenas há suporte para perfis de certificado SCEP com o uso de um tipo de EAP. Não há suporte para perfis de certificado PKCS. Sempre que um usuário precisar inserir um certificado, lembre-se de escolher um certificado SCEP.

#### <a name="server-trust"></a>Confiança do Servidor

|Nome da configuração|Mais informações|Usar quando|
|--------------|-------------|----------|
|**Nomes de servidor de certificados**|Insira um ou mais nomes comuns usados nos certificados emitidos pela AC (autoridade de certificação) confiável. Se você inserir essas informações, poderá ignorar a caixa de diálogo de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.|O tipo de EAP é **EAP-TLS**, **EAP-TTLS** ou **PEAP**|
|**Certificado raiz para validação do servidor**|Escolha o perfil de certificado raiz confiável usado para autenticar a conexão. |O tipo de EAP é **EAP-TLS**, **EAP-TTLS** ou **PEAP**|
|**Privacidade de identidade (identidade externa)**|Insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.|O tipo de EAP é **PEAP**|

#### <a name="client-authentication"></a>Autenticação do Cliente

| Nome da configuração | Mais informações | Usar quando |
|---|---|---|
| **Certificado de cliente para autenticação de cliente (Certificado de identidade)** |  Escolha o perfil de certificado SCEP usado para autenticar a conexão. | O tipo de EAP é **EAP-TLS** |
| **Método de autenticação** | Selecione o método de autenticação para a conexão:<br><br>- **Certificados**: selecione o certificado do cliente SCEP que é o certificado de identidade apresentado ao servidor.<br><br>- **Nome de usuário e senha**: insira um **método não EAP (identidade interna)** de autenticação. Suas opções:<br><br>- **Senha não criptografada (PAP)**<br>- **Challenge Handshake (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP Versão 2 (MS-CHAP v2)**<br><br>- **Privacidade de identidade (identidade externa)**: insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro. | O tipo de EAP é **EAP-TTLS** |

## <a name="use-an-imported-settings-file"></a>Usar um arquivo de configurações importadas

Para as configurações que não estão disponíveis no Intune, você pode exportar as configurações de Wi-Fi de outro dispositivo Windows. Essa exportação cria um arquivo XML com todas as configurações. Em seguida, importe esse arquivo no Intune e use-o como o perfil de Wi-Fi. Confira [Exportar e importar configurações de Wi-Fi para dispositivos Windows](wi-fi-settings-import-windows-8-1.md).

## <a name="next-steps"></a>Próximas etapas
[Definir configurações de Wi-Fi no Intune](wi-fi-settings-configure.md)
