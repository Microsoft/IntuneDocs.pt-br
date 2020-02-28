---
title: Configurações de Wi-Fi para dispositivos Android Enterprise e quiosque – Microsoft Intune | Microsoft Docs
description: Crie ou adicione um perfil de configuração de dispositivo Wi-Fi para o Android Enterprise e o Android Kiosk. Confira as diferentes configurações, incluindo a adição de certificados, a escolha de um tipo de EAP e a seleção de um método de autenticação no Microsoft Intune. Para dispositivos de quiosque, insira também a Chave pré-compartilhada de sua rede.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
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
ms.openlocfilehash: aef1747fdbb3118db82f6e99c2838632c8a9d369
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512442"
---
# <a name="add-wi-fi-settings-for-android-enterprise-dedicated-and-fully-managed-devices-in-microsoft-intune"></a>Adicionar configurações de Wi-Fi para dispositivos Android Enterprise dedicados e totalmente gerenciados no Microsoft Intune

Você pode criar um perfil com configurações de Wi-Fi específicas e, em seguida, implantar esse perfil nos dispositivos dedicados e totalmente gerenciados do Android Enterprise. O Microsoft Intune oferece muitos recursos, incluindo autenticação na rede, uso de uma chave pré-compartilhada e muito mais.

Este artigo descreve essas configurações. [Usar o Wi-Fi em dispositivos](wi-fi-settings-configure.md) inclui mais informações sobre o recurso de Wi-Fi no Microsoft Intune.

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de dispositivo](wi-fi-settings-configure.md#create-a-device-profile).

## <a name="device-owner-only"></a>Somente proprietário do dispositivo

Selecione esta opção se você estiver implantando em um dispositivo Android Enterprise dedicado ou totalmente gerenciado.  No momento, os dispositivos Android Enterprise dedicados e totalmente gerenciados dão suporte à implantação de certificado SCEP, mas não PKCS.

### <a name="basic"></a>Básico

- **Tipo de Wi-Fi**: Escolha **básica**.
- **Nome da rede**: insira um nome para esta conexão Wi-Fi. Os usuários finais veem esse nome quando navegam nas conexões Wi-Fi disponíveis do dispositivo. Por exemplo, digite **Wi-Fi da Contoso**.
- **SSID**: insira o **identificador SSID**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.
- **Tipo de Wi-Fi**: selecione o protocolo de segurança para autenticar à rede Wi-Fi. Suas opções:

  - **Abrir (sem autenticação)** : use essa opção somente se a rede não for segura.
  - **WEP–chave pré-compartilhada**: insira a senha em **Chave pré-compartilhada**. Quando a rede da sua organização é definida ou configurada, uma senha ou chave de rede também é configurada. Insira essa senha ou chave de rede para o valor PSK.
  - **WPA–chave pré-compartilhada**: insira a senha em **Chave pré-compartilhada**. Quando a rede da sua organização é definida ou configurada, uma senha ou chave de rede também é configurada. Insira essa senha ou chave de rede para o valor PSK.

### <a name="enterprise"></a>Enterprise

- **Tipo de Wi-Fi**: escolha **Corporativo**.
- **SSID**: insira o **identificador SSID**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.
- **Tipo de EAP**: escolha o tipo de protocolo EAP (Extensible Authentication) usado para autenticar conexões sem fio seguras. Suas opções:

  - **EAP-TLS**: Insira também:

    - **Confiança do servidor** - **certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Quando o cliente se conecta à rede, esse certificado é apresentado ao servidor e é usado para autenticar a conexão.

    - **Autenticação de cliente** - **certificado do cliente para autenticação de cliente (Certificado de identidade)** : escolha o perfil de certificado do cliente SCEP que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

    - **Privacidade de identidade (identidade externa)** : insira o texto enviado na resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **EAP-TTLS**: Insira também:

    - **Confiança do servidor** - **certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Quando o cliente se conecta à rede, esse certificado é apresentado ao servidor e é usado para autenticar a conexão.

    - **Autenticação do Cliente**: selecione um **Método de autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP (identidade interna)** : escolha como você fará a autenticação da conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi. Suas opções:

          - **Senha não criptografada (PAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado na resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **PEAP**: Insira também:

    - **Confiança do servidor** - **certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Quando o cliente se conecta à rede, esse certificado é apresentado ao servidor e é usado para autenticar a conexão.

    - **Autenticação do Cliente**: selecione um **Método de autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **método que não seja EAP para autenticação (identidade interna)** : escolha como você fará a autenticação da conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi. Suas opções:

          - **Nenhum**
          - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado na resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

## <a name="work-profile-only"></a>Somente perfil de trabalho

### <a name="basic"></a>Básico

- **Tipo de Wi-Fi**: Escolha **básica**.
- **SSID**: insira o **identificador SSID**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.

### <a name="enterprise"></a>Enterprise

- **Tipo de Wi-Fi**: escolha **Corporativo**.
- **SSID**: insira o **identificador SSID**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.
- **Tipo de EAP**: escolha o tipo de protocolo EAP (Extensible Authentication) usado para autenticar conexões sem fio seguras. Suas opções:

  - **EAP-TLS**: Insira também:

    - **Confiança do servidor** - **certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Quando o cliente se conecta à rede, esse certificado é apresentado ao servidor e é usado para autenticar a conexão.

    - **Autenticação de cliente** - **certificado do cliente para autenticação de cliente (Certificado de identidade)** : escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

    - **Privacidade de identidade (identidade externa)** : insira o texto enviado na resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **EAP-TTLS**: Insira também:

    - **Confiança do servidor** - **certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Quando o cliente se conecta à rede, esse certificado é apresentado ao servidor e é usado para autenticar a conexão.

    - **Autenticação do Cliente**: selecione um **Método de autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP (identidade interna)** : escolha como você fará a autenticação da conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi. Suas opções:

          - **Senha não criptografada (PAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado na resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **PEAP**: Insira também:

    - **Confiança do servidor** - **certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Quando o cliente se conecta à rede, esse certificado é apresentado ao servidor e é usado para autenticar a conexão.

    - **Autenticação do Cliente**: selecione um **Método de autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **método que não seja EAP para autenticação (identidade interna)** : escolha como você fará a autenticação da conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi. Suas opções:

          - **Nenhum**
          - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado na resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua esse perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Também é possível criar perfis de Wi-Fi para dispositivos [Android](wi-fi-settings-android.md), [iOS/iPadOS](wi-fi-settings-ios.md), [macOS](wi-fi-settings-macos.md), [Windows 10](wi-fi-settings-windows.md) e [Windows 8.1](wi-fi-settings-import-windows-8-1.md).
