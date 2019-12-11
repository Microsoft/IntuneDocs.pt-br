---
title: Definir as configurações de Wi-Fi para dispositivos Android no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Crie ou adicione um perfil de configuração do dispositivo Wi-Fi para Android. Confira as diferentes configurações, incluindo a adição de certificados, a escolha de um tipo de EAP e a seleção de um método de autenticação no Microsoft Intune.
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
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a9bd1691b7943f02c9577e962fb1bcd5d9cf40a
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72585325"
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
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.

## <a name="enterprise"></a>Enterprise

- **Tipo de Wi-Fi**: escolha **Corporativo**.
- **SSID**: Insira o **identificador do conjunto de serviços**, que é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
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
