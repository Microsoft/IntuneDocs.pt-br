---
title: Configurações de Wi-Fi para dispositivos Android Enterprise e quiosque – Microsoft Intune | Microsoft Docs
description: Crie ou adicione um perfil de configuração de dispositivo Wi-Fi para o Android Enterprise e o Android Kiosk. Confira as diferentes configurações, incluindo a adição de certificados, a escolha de um tipo de EAP e a seleção de um método de autenticação no Microsoft Intune. Para dispositivos de quiosque, insira também a Chave pré-compartilhada de sua rede.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/08/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: maholdaa
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 266786de3122f8886bb3ed310764459568e1df6a
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585373"
---
# <a name="add-wi-fi-settings-for-devices-running-android-enterprise-and-android-kiosk-in-microsoft-intune"></a>Adicionar configurações de Wi-Fi a dispositivos que executam o Android Enterprise e o Android Kiosk no Microsoft Intune

Você pode criar um perfil com configurações de Wi-Fi específicas e, em seguida, implantar esse perfil nos dispositivos dedicados do Android Empresa e Android. O Microsoft Intune oferece muitos recursos, incluindo autenticação na rede, uso de uma chave pré-compartilhada e muito mais.

Este artigo descreve essas configurações. [Usar o Wi-Fi em dispositivos](wi-fi-settings-configure.md) inclui mais informações sobre o recurso de Wi-Fi no Microsoft Intune.

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de dispositivo](wi-fi-settings-configure.md#create-a-device-profile).

## <a name="device-owner-only"></a>Somente proprietário do dispositivo

Selecione essa opção se estiver usando um dispositivo dedicado Android Empresa como um quiosque.

### <a name="basic"></a>Básico

- **Tipo de Wi-Fi**: escolha **Básico**.
- **Nome da rede**: insira um nome para esta conexão Wi-Fi. Os usuários finais veem esse nome quando navegam nas conexões Wi-Fi disponíveis do dispositivo. Por exemplo, digite **Wi-Fi da Contoso**.
- **SSID**: Insira o **identificador do conjunto de serviços**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.
- **Tipo de Wi-Fi**: selecione o protocolo de segurança para autenticar à rede Wi-Fi. Suas opções:

  - **Abrir (sem autenticação)** : use essa opção somente se a rede não for segura.
  - **Chave WEP pré-compartilhada**: insira a senha em **Chave pré-compartilhada**. Quando a rede da sua organização é definida ou configurada, uma senha ou chave de rede também é configurada. Insira essa senha ou chave de rede para o valor PSK.
  - **Chave WPA pré-compartilhada**: insira a senha em **Chave pré-compartilhada**. Quando a rede da sua organização é definida ou configurada, uma senha ou chave de rede também é configurada. Insira essa senha ou chave de rede para o valor PSK.

### <a name="enterprise"></a>Enterprise

- **Tipo de Wi-Fi**: escolha **Corporativo**.
- **SSID**: Insira o **identificador do conjunto de serviços**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.
- **Tipo de EAP**: escolha o tipo de Protocolo EAP (Extensible Authentication Protocol) usado para autenticar conexões sem fio seguras. Suas opções:

  - **EAP-TLS**: também inserir:

    - **Confiança do Servidor** - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Quando o cliente se conecta à rede, esse certificado é apresentado ao servidor e é usado para autenticar a conexão.

    - **Autenticação de Cliente** - **Certificado do cliente para autenticação de cliente (certificado de identidade)** : escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

    - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **EAP-TTLS**: também inserir:

    - **Confiança do Servidor** - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Quando o cliente se conecta à rede, esse certificado é apresentado ao servidor e é usado para autenticar a conexão.

    - **Autenticação de Cliente**: escolha um **Método de autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP (identidade interna)** : escolha como você autentica a conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi. Suas opções:

          - **Senha não criptografada (PAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **PEAP**: insira também:

    - **Confiança do Servidor** - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Quando o cliente se conecta à rede, esse certificado é apresentado ao servidor e é usado para autenticar a conexão.

    - **Autenticação de Cliente**: escolha um **Método de autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP para autenticação (identidade interna)** : escolha como você autentica a conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi. Suas opções:

          - **Nenhum**
          - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

## <a name="work-profile-only"></a>Somente perfil de trabalho

### <a name="basic"></a>Básico

- **Tipo de Wi-Fi**: escolha **Básico**.
- **SSID**: Insira o **identificador do conjunto de serviços**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.

### <a name="enterprise"></a>Enterprise

- **Tipo de Wi-Fi**: escolha **Corporativo**.
- **SSID**: Insira o **identificador do conjunto de serviços**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.
- **Tipo de EAP**: escolha o tipo de Protocolo EAP (Extensible Authentication Protocol) usado para autenticar conexões sem fio seguras. Suas opções:

  - **EAP-TLS**: também inserir:

    - **Confiança do Servidor** - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Quando o cliente se conecta à rede, esse certificado é apresentado ao servidor e é usado para autenticar a conexão.

    - **Autenticação de Cliente** - **Certificado do cliente para autenticação de cliente (certificado de identidade)** : escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

    - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **EAP-TTLS**: também inserir:

    - **Confiança do Servidor** - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Quando o cliente se conecta à rede, esse certificado é apresentado ao servidor e é usado para autenticar a conexão.

    - **Autenticação de Cliente**: escolha um **Método de autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP (identidade interna)** : escolha como você autentica a conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi. Suas opções:

          - **Senha não criptografada (PAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **PEAP**: insira também:

    - **Confiança do Servidor** - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Quando o cliente se conecta à rede, esse certificado é apresentado ao servidor e é usado para autenticar a conexão.

    - **Autenticação de Cliente**: escolha um **Método de autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP para autenticação (identidade interna)** : escolha como você autentica a conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi. Suas opções:

          - **Nenhum**
          - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua esse perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Também é possível criar perfis de Wi-Fi para dispositivos [Android](wi-fi-settings-android.md), [iOS](wi-fi-settings-ios.md), [macOS](wi-fi-settings-macos.md), [Windows 10](wi-fi-settings-windows.md) e [Windows 8.1](wi-fi-settings-import-windows-8-1.md).
