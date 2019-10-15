---
title: Definir as configurações de Wi-Fi para dispositivos Android no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Crie ou adicione um perfil de configuração do dispositivo Wi-Fi para Android. Confira as diferentes configurações, incluindo a adição de certificados, a escolha de um tipo de EAP e a seleção de um método de autenticação no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1d341aeace950f62ae699aa7760a65c0fd2f74fa
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734031"
---
# <a name="add-wi-fi-settings-for-devices-running-android-in-microsoft-intune"></a>Adicionar configurações de Wi-Fi para dispositivos que executam o Android no Microsoft Intune

Você pode criar um perfil com configurações de Wi-Fi específicas e implantar esse perfil em seus dispositivos Android. O Microsoft Intune oferece muitos recursos, incluindo autenticação em sua rede, adição de um certificado PKS ou SCEP e muito mais.

Essas configurações de Wi-Fi são separadas em duas categorias: Configurações básicas e Configurações no nível da empresa.

Este artigo descreve essas configurações.

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de dispositivo](device-profile-create.md).

## <a name="basic"></a>Básico

- **Tipo de Wi-Fi**: escolha **Básico**.
- **SSID**: Insira o **identificador do conjunto de serviços**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Conectar-se automaticamente**: escolha **Habilitar** para se conectar automaticamente a essa rede quando o dispositivo estiver ao alcance. Escolha **Desabilitar** para impedir que dispositivos se conectem automaticamente.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.

## <a name="enterprise"></a>Enterprise

- **Tipo de Wi-Fi**: escolha **Corporativo**.
- **SSID**: Insira o **identificador do conjunto de serviços**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Conectar-se automaticamente**: escolha **Habilitar** para se conectar automaticamente a essa rede quando o dispositivo estiver ao alcance. Escolha **Desabilitar** para impedir que dispositivos se conectem automaticamente.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.
- **Tipo de EAP**: escolha o tipo de Protocolo EAP (Extensible Authentication Protocol) usado para autenticar conexões sem fio seguras. Suas opções: 

  - **EAP-TLS**: também inserir:

    - **Confiança do Servidor** - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede. Ele autentica a conexão.

    - **Autenticação de Cliente** - **Certificado do cliente para autenticação de cliente (certificado de identidade)** : escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

    - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **EAP-TTLS**: também inserir:

    - **Confiança do Servidor** - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede. Ele autentica a conexão.

    - **Autenticação de Cliente**: escolha um **Método de autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP (identidade interna)** : escolha como você autentica a conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi. Suas opções:

          - **Senha não criptografada (PAP)**
          - **Challenge Heshake Authentication Protocol (CHAP)**
          - **Microsoft CHAP (MS-CHAP)**
          - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **PEAP**: insira também:

    - **Confiança do Servidor** - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede. Ele autentica a conexão.

    - **Autenticação de Cliente**: escolha um **Método de autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP para autenticação (identidade interna)** : escolha como você autentica a conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi. Suas opções:

          - **Nenhum**
          - **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua esse perfil](device-profile-assign.md).

## <a name="more-resources"></a>Mais recursos

- [Visão geral das configurações de Wi-Fi](wi-fi-settings-configure.md), incluindo outras plataformas.

- Você está usando dispositivos Android Enterprise ou Android Kiosk? Se estiver, então confira as [Configurações de Wi-Fi dos dispositivos que executam o Android Empresa e dispositivos dedicados](wi-fi-settings-android-enterprise.md).