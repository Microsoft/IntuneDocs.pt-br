---
title: Definir as configurações de Wi-Fi para dispositivos Android no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Crie ou adicione um perfil de configuração do dispositivo Wi-Fi para Android. Confira as diferentes configurações, incluindo a adição de certificados, a escolha de um tipo de EAP e a seleção de um método de autenticação no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/24/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: maholdaa
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ea0a60537bb488d3280990747d3e337e73fddc0
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754551"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Adicionar configurações de Wi-Fi para dispositivos que executam o Android no Microsoft Intune

Você pode criar um perfil com configurações de Wi-Fi específicas e implantar esse perfil em seus dispositivos Android. O Microsoft Intune oferece muitos recursos, incluindo autenticação em sua rede, adição de um certificado PKS ou SCEP e muito mais.

Essas configurações de Wi-Fi são separadas em duas categorias: Configurações básicas e configurações de nível empresarial.

Este artigo descreve essas configurações.

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de dispositivo](device-profile-create.md).

## <a name="basic"></a>Básico

- **Tipo de Wi-Fi**: Escolha **básica**.
- **SSID**: insira o **identificador do conjunto de serviços**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.

## <a name="enterprise"></a>Enterprise

- **Tipo de Wi-Fi**: escolha **Corporativo**.
- **SSID**: insira o **identificador do conjunto de serviços**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.
- **Tipo de EAP**: escolha o tipo de protocolo EAP (Extensible Authentication) usado para autenticar conexões sem fio seguras. Suas opções:

  - **EAP-TLS**: Insira também:

    - **Confiança do servidor** - **certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede. Ele autentica a conexão.

    - **Autenticação de cliente** - **certificado do cliente para autenticação de cliente (Certificado de identidade)** : escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

    - **Privacidade de identidade (identidade externa)** : insira o texto enviado na resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

    - **Configurações de proxy**: especifique a configuração de proxy usada pela sua organização. Suas opções:

      - **Nenhum** – você não usa um servidor proxy.
      - **Automático** – selecione esta opção para disponibilizar a configuração de *URL do Servidor Proxy*, que você usa para especificar o servidor proxy ou um arquivo PAC (configuração automática de proxy) que contém uma lista de seus servidores proxy.

    - **URL do servidor proxy**: essa configuração fica disponível quando você define as *Configurações de proxy* como *Automáticas*. Especifique uma das opções a seguir para direcionar os dispositivos para seu servidor proxy:

      - Endereço IP. Por exemplo, `10.0.0.11`
      - Uma URL. Por exemplo, `http://proxyserver.contoso.com`.
      - A URL de um arquivo PAC (configuração automática de proxy). Por exemplo: `http://proxy.contoso.com/proxy.pac`.

      Para obter mais informações sobre os arquivos PAC, confira [Arquivo PAC (configuração automática de proxy)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (abre um site que não é da Microsoft).

  - **EAP-TTLS**: Insira também:

    - **Confiança do servidor** - **certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede. Ele autentica a conexão.

    - **Autenticação do Cliente**: selecione um **Método de autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP (identidade interna)** : escolha como você fará a autenticação da conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi. Suas opções:

          - **Senha não criptografada (PAP)**
          - **Challenge Heshake Authentication Protocol (CHAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado na resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

    - **Configurações de proxy**: especifique a configuração de proxy usada pela sua organização. Suas opções:

      - **Nenhum** – você não usa um servidor proxy.
      - **Automático** – selecione esta opção para disponibilizar a configuração de *URL do Servidor Proxy*, que você usa para especificar o servidor proxy ou um arquivo PAC (configuração automática de proxy) que contém uma lista de seus servidores proxy.

    - **URL do servidor proxy**: essa configuração fica disponível quando você define as *Configurações de proxy* como *Automáticas*. Especifique uma das opções a seguir para direcionar os dispositivos para seu servidor proxy:

      - Endereço IP. Por exemplo, `10.0.0.11`
      - Uma URL. Por exemplo, `http://proxyserver.contoso.com`.
      - A URL de um arquivo PAC (configuração automática de proxy). Por exemplo: `http://proxy.contoso.com/proxy.pac`.

      Para obter mais informações sobre os arquivos PAC, confira [Arquivo PAC (configuração automática de proxy)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (abre um site que não é da Microsoft).

  - **PEAP**: Insira também:

    - **Confiança do servidor** - **certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede. Ele autentica a conexão.

    - **Autenticação do Cliente**: selecione um **Método de autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **método que não seja EAP para autenticação (identidade interna)** : escolha como você fará a autenticação da conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi. Suas opções:

          - **Nenhum**
          - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado na resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

      - **Configurações de proxy**: especifique a configuração de proxy usada pela sua organização. Suas opções:

        - **Nenhum** – você não usa um servidor proxy.
        - **Automático** – selecione esta opção para disponibilizar a configuração de *URL do Servidor Proxy*, que você usa para especificar o servidor proxy ou um arquivo PAC (configuração automática de proxy) que contém uma lista de seus servidores proxy.

      - **URL do servidor proxy**: essa configuração fica disponível quando você define as *Configurações de proxy* como *Automáticas*. Especifique uma das opções a seguir para direcionar os dispositivos para seu servidor proxy:

        - Endereço IP. Por exemplo, `10.0.0.11`
        - Uma URL. Por exemplo, `http://proxyserver.contoso.com`.
        - A URL de um arquivo PAC (configuração automática de proxy). Por exemplo: `http://proxy.contoso.com/proxy.pac`.

        Para obter mais informações sobre os arquivos PAC, confira [Arquivo PAC (configuração automática de proxy)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (abre um site que não é da Microsoft).

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua esse perfil](device-profile-assign.md).

## <a name="more-resources"></a>Mais recursos

- [Visão geral das configurações de Wi-Fi](wi-fi-settings-configure.md), incluindo outras plataformas.

- Você está usando dispositivos Android Enterprise ou Android Kiosk? Se estiver, então confira as [Configurações de Wi-Fi dos dispositivos que executam o Android Empresa e dispositivos dedicados](wi-fi-settings-android-enterprise.md).
