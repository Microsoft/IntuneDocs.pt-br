---
title: Definir configurações de rede com fios para dispositivos macOS no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Crie ou adicione um perfil de configuração do dispositivo de rede com fios para dispositivos macOS. Confira as diferentes configurações, incluindo a adição de certificados, a escolha de um tipo de EAP e a seleção de um método de autenticação no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/4/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7dba36d03489bcdeee3c3c1f69a4995823dd21ee
ms.sourcegitcommit: df8e2c052fafb2d5d4e9b4fcd831ae0ecf7f8d16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74994326"
---
# <a name="add-wired-network-settings-for-macos-devices-in-microsoft-intune"></a>Adicionar configurações de rede com fio para dispositivos macOS no Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Você pode criar um perfil com configurações de rede com fios específicas e implantar esse perfil em seus dispositivos macOS. O Microsoft Intune oferece muitos recursos, incluindo autenticação em sua rede, adição de um certificado PKS ou SCEP e muito mais. 

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de dispositivo](device-profile-create.md).

> [!NOTE]
> Essas configurações estão disponíveis para todos os tipos de registro. Para obter mais informações sobre os tipos de registro, consulte [registro do MacOS](../enrollment/macos-enroll.md).

## <a name="profiles"></a>Perfis

- **Tipo de perfil**: escolha **rede com fio**.
- **Interface de rede**: 
- **Tipo de EAP**: escolha o tipo de Protocolo EAP (Extensible Authentication Protocol) usado para autenticar conexões sem fio seguras. Suas opções:
  - **EAP-FAST**: insira as **Configurações de PAC (Protected Access Credential)** . Essa opção usa credenciais de acesso protegido para criar um túnel autenticado entre o cliente e o servidor de autenticação. Suas opções:
    - **Não usar (PAC)**
    - **Usar (PAC)** : se houver um arquivo PAC, use-o.
    - **Usar e provisionar PAC**: crie e adicione o arquivo PAC aos seus dispositivos.
    - **Usar e provisionar PAC anonimamente**: crie e adicione o arquivo PAC aos seus dispositivos sem se autenticar no servidor.
  - **EAP-TLS**: também inserir:
    - **Confiança do Servidor** - **Nomes de servidores de certificados**: **adicione** um ou mais nomes comuns usados nos certificados emitidos pela autoridade de certificação confiável. Quando você inserir essas informações, poderá ignorar a janela de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.
    - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede e é usado para autenticar a conexão.
    - **Autenticação de Cliente** - **Certificado do cliente para autenticação de cliente (certificado de identidade)** : escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.
  - **EAP-TTLS**: também inserir:
    - **Confiança do Servidor** - **Nomes de servidores de certificados**: **adicione** um ou mais nomes comuns usados nos certificados emitidos pela autoridade de certificação confiável. Quando você inserir essas informações, poderá ignorar a janela de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.
    - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede e é usado para autenticar a conexão.
    - **Autenticação de Cliente** — escolha um **método de Autenticação**. Suas opções:
      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP (identidade interna)** : escolha como você autentica a conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi.
          Suas opções: **Senha não criptografada (PAP)** , **Protocolo CHAP (CHAP)** , **Microsoft CHAP (MS-CHAP)** , ou **Microsoft CHAP Versão 2 (MS-CHAP v2)**
      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.
      - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.
  - **LEAP**
  - **PEAP**: insira também:
    - **Confiança do Servidor** - **Nomes de servidores de certificados**: **adicione** um ou mais nomes comuns usados nos certificados emitidos pela autoridade de certificação confiável. Quando você inserir essas informações, poderá ignorar a janela de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.
    - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede e é usado para autenticar a conexão.
    - **Autenticação de Cliente** — escolha um **método de Autenticação**. Suas opções:
      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. 
      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.
      - **Privacidade de identidade (identidade externa)** : insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua este perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Defina as configurações de Wi-Fi em dispositivos [Android](wi-fi-settings-android.md), [Android Enterprise](wi-fi-settings-android-enterprise.md), [Ios](wi-fi-settings-ios.md)e [Windows 10](wi-fi-settings-windows.md) .
