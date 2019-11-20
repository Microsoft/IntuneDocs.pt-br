---
title: Definir as configurações de Wi-Fi para dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Crie ou adicione um perfil de configuração de dispositivo Wi-Fi para dispositivos iOS. Confira as diferentes configurações, incluindo a adição de certificados, a escolha de um tipo de EAP e a seleção de um método de autenticação no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dd37813e5ea0b6a64d7fae22cada06cccb01a942
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059211"
---
# <a name="add-wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>Adicionar configurações de Wi-Fi para dispositivos iOS no Microsoft Intune

Você pode criar um perfil com configurações de Wi-Fi específicas e implantar esse perfil em seus dispositivos iOS. O Microsoft Intune oferece muitos recursos, incluindo autenticação em sua rede, adição de um certificado PKCS ou SCEP e muito mais.

Essas configurações de Wi-Fi são separadas em duas categorias: Configurações básicas e Configurações no nível da empresa.

Este artigo descreve essas configurações.

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de dispositivo](../device-profile-create.md).

> [!NOTE]
> Essas configurações estão disponíveis para todos os tipos de registro. Para obter mais informações sobre os tipos de registro, consulte [registro do IOS](../enrollment/ios-enroll.md).

## <a name="basic-profiles"></a>Perfis básicos

- **Tipo de Wi-Fi**: escolha **Básico**.
- **Nome da rede**: insira um nome para esta conexão Wi-Fi. Esse valor é o nome que os usuários verão ao navegarem pela lista de conexões disponíveis no dispositivo.
- **SSID**: abreviação de **service set identifier** (identificador de conjunto de serviço). Essa propriedade é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o nome de rede configurado ao escolher a conexão.
- **Conectar-se automaticamente**: escolha **Habilitar** para se conectar automaticamente a essa rede quando o dispositivo estiver ao alcance. Escolha **Desabilitar** para impedir que dispositivos se conectem automaticamente.
- **Rede oculta**: escolha **Habilitar** se o SSID da rede não é transmitido. Escolher **Desabilitar** se o SSID da rede é transmitido e visível.
- **Tipo de segurança**: selecione o protocolo de segurança para autenticar à rede Wi-Fi. Suas opções:

  - **Abrir (sem autenticação)** : use essa opção somente se a rede não for segura.
  - **WPA/WPA2 - Pessoal**: insira a senha em **Chave pré-compartilhada**. Quando a rede da sua organização é definida ou configurada, uma senha ou chave de rede também é configurada. Insira essa senha ou chave de rede para o valor PSK.
  - **WEP**

- **Configurações de proxy**: suas opções:
  - **Nenhum**: nenhuma configuração de proxy é definida.
  - **Manual**: insira o **Endereço do servidor proxy** como um endereço IP e seu **Número da porta**.
  - **Automático**: use um arquivo para configurar o servidor proxy. Digite a **URL do servidor proxy** (por exemplo, `http://proxy.contoso.com`) que contém o arquivo de configuração.

## <a name="enterprise-profiles"></a>Perfis corporativos

- **Tipo de Wi-Fi**: escolha **Corporativo**.
- **SSID**: abreviação de **service set identifier** (identificador de conjunto de serviço). Essa propriedade é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o nome de rede configurado ao escolher a conexão.
- **Conectar-se automaticamente**: escolha **Habilitar** para se conectar automaticamente a essa rede quando o dispositivo estiver ao alcance. Escolha **Desabilitar** para impedir que dispositivos se conectem automaticamente.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.

- **Tipo de EAP**: escolha o tipo de Protocolo EAP (Extensible Authentication Protocol) usado para autenticar conexões sem fio seguras. Suas opções:

  - **EAP-FAST**: insira as **Configurações de PAC (Protected Access Credential)** . Essa opção usa credenciais de acesso protegido para criar um túnel autenticado entre o cliente e o servidor de autenticação. Suas opções:
    - **Não usar (PAC)**
    - **Usar (PAC)** : se houver um arquivo PAC, use-o.
    - **Usar e provisionar PAC**: crie e adicione o arquivo PAC aos seus dispositivos.
    - **Usar e provisionar PAC anonimamente**: crie e adicione o arquivo PAC aos seus dispositivos sem se autenticar no servidor.

  - **EAP-SIM**

  - **EAP-TLS**: também inserir:

    - **Confiança do Servidor** - **Nomes de servidores de certificados**: **adicione** um ou mais nomes comuns usados nos certificados emitidos pela autoridade de certificação confiável ao seus servidores de acesso de rede sem fio. Por exemplo, adicione `mywirelessserver.contoso.com` ou `mywirelessserver`. Quando você inserir essas informações, poderá ignorar a janela de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.
    - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado permite que o cliente confie no certificado do servidor de acesso à rede sem fio.

    - **Autenticação de Cliente**: escolha um **Método de autenticação**. Suas opções:

      - **Credencial derivada**: Use um certificado derivado do cartão inteligente de um usuário. Se nenhum emissor de credencial derivado estiver configurado, o Intune solicitará que você adicione um. Para obter mais informações, consulte [usar credenciais derivadas no Microsoft Intune](../protect/derived-credentials.md).

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

    - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **EAP-TTLS**: também inserir:

    - **Confiança do Servidor** - **Nomes de servidores de certificados**: **adicione** um ou mais nomes comuns usados nos certificados emitidos pela autoridade de certificação confiável ao seus servidores de acesso de rede sem fio. Por exemplo, adicione `mywirelessserver.contoso.com` ou `mywirelessserver`. Quando você inserir essas informações, poderá ignorar a janela de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.
    - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado permite que o cliente confie no certificado do servidor de acesso à rede sem fio.

    - **Autenticação de Cliente** — escolha um **método de Autenticação**. Suas opções:

      - **Credencial derivada**: Use um certificado derivado do cartão inteligente de um usuário. Se nenhum emissor de credencial derivado estiver configurado, o Intune solicitará que você adicione um. Para obter mais informações, consulte [usar credenciais derivadas no Microsoft Intune](../protect/derived-credentials.md).

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP (identidade interna)** : escolha como você autentica a conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi.

          Suas opções: **Senha não criptografada (PAP)** , **Protocolo CHAP (CHAP)** , **Microsoft CHAP (MS-CHAP)** , ou **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **LEAP**

  - **PEAP**: insira também:

    - **Confiança do Servidor** - **Nomes de servidores de certificados**: **adicione** um ou mais nomes comuns usados nos certificados emitidos pela autoridade de certificação confiável ao seus servidores de acesso de rede sem fio. Por exemplo, adicione `mywirelessserver.contoso.com` ou `mywirelessserver`. Quando você inserir essas informações, poderá ignorar a janela de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.
    - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado permite que o cliente confie no certificado do servidor de acesso à rede sem fio.

    - **Autenticação de Cliente** — escolha um **método de Autenticação**. Suas opções:

      - **Credencial derivada**: Use um certificado derivado do cartão inteligente de um usuário. Se nenhum emissor de credencial derivado estiver configurado, o Intune solicitará que você adicione um. Para obter mais informações, consulte [usar credenciais derivadas no Microsoft Intune](../protect/derived-credentials.md).

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. 

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

- **Configurações de proxy**: suas opções:
  - **Nenhum**: nenhuma configuração de proxy é definida.
  - **Manual**: insira o **Endereço do servidor proxy** como um endereço IP e seu **Número da porta**.
  - **Automático**: use um arquivo para configurar o servidor proxy. Digite a **URL do servidor proxy** (por exemplo, `http://proxy.contoso.com`) que contém o arquivo de configuração.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua esse perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Defina as configurações de Wi-Fi em dispositivos [Android](wi-fi-settings-android.md), [Android Enterprise](wi-fi-settings-android-enterprise.md), [MacOS](wi-fi-settings-macos.md)e [Windows 10](wi-fi-settings-windows.md) .
