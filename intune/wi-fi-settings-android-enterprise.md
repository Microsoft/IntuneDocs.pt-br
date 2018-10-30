---
title: Definir configurações de Wi-Fi para dispositivos Android Enterprise e quiosque – Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Crie ou adicione um perfil de configuração de dispositivo Wi-Fi para o Android Enterprise e o Android Kiosk. Confira as diferentes configurações, incluindo a adição de certificados, a escolha de um tipo de EAP e a seleção de um método de autenticação no Microsoft Intune. Para dispositivos de quiosque, insira também a Chave pré-compartilhada de sua rede.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c2983f2f7b7079f73c857bf7caafe4236373c5dc
ms.sourcegitcommit: cff65435df070940da390609d6376af6ccdf0140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2018
ms.locfileid: "49431906"
---
# <a name="add-wi-fi-settings-for-devices-running-android-enterprise-and-android-kiosk-in-microsoft-intune"></a>Adicionar configurações de Wi-Fi a dispositivos que executam o Android Enterprise e o Android Kiosk no Microsoft Intune

Você pode criar um perfil com configurações de Wi-Fi específicas e, em seguida, implantar esse perfil nos dispositivos Android Enterprise e Android Kiosk. O Microsoft Intune oferece muitos recursos, incluindo autenticação na rede, uso de uma chave pré-compartilhada e muito mais.

Este artigo descreve essas configurações.

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de dispositivo](device-profile-create.md).

## <a name="device-owner-only---kiosk"></a>Somente proprietário do dispositivo — quiosque

Selecione essa opção se estiver usando um dispositivo Android Enterprise como um quiosque.

- **Nome da rede**: insira um nome para esta conexão Wi-Fi. Esse valor é o nome que os usuários verão ao navegarem pela lista de conexões disponíveis no dispositivo.
- **SSID**: abreviação de **service set identifier** (identificador de conjunto de serviço). Essa configuração é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o **nome de rede** configurado ao escolherem a conexão.
- **Conectar-se automaticamente**: escolha **Habilitar** para se conectar automaticamente a essa rede quando o dispositivo estiver ao alcance. Escolha **Desabilitar** para impedir que dispositivos se conectem automaticamente.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.
- **Tipo de Wi-Fi**: selecione o protocolo de segurança para autenticar à rede Wi-Fi. Suas opções:

  - **Abrir (sem autenticação)**: use essa opção somente se a rede não for segura.
  - **Chave WEP pré-compartilhada**: insira a senha em **Chave pré-compartilhada**. Quando a rede da sua organização é definida ou configurada, uma senha ou chave de rede também é configurada. Insira essa senha ou chave de rede para o valor PSK.
  - **Chave WPA pré-compartilhada**: insira a senha em **Chave pré-compartilhada**. Quando a rede da sua organização é definida ou configurada, uma senha ou chave de rede também é configurada. Insira essa senha ou chave de rede para o valor PSK.

Selecione **OK** para salvar suas alterações.

## <a name="work-profile-only"></a>Somente perfil de trabalho

### <a name="basic-settings"></a>Configurações básicas

- **Tipo de Wi-Fi**: escolha **Básico**.
- **SSID**: abreviação de **service set identifier** (identificador de conjunto de serviço). Essa configuração é o nome real da rede sem fio à qual os dispositivos se conectam.
- **Conectar-se automaticamente**: escolha **Habilitar** para se conectar automaticamente a essa rede quando o dispositivo estiver ao alcance. Escolha **Desabilitar** para impedir que dispositivos se conectem automaticamente.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.

## <a name="enterprise-profile"></a>Perfil corporativo

- **Tipo de Wi-Fi**: escolha **Corporativo**.
- **SSID**: abreviação de **service set identifier** (identificador de conjunto de serviço). Essa configuração é o nome real da rede sem fio à qual os dispositivos se conectam.
- **Conectar-se automaticamente**: escolha **Habilitar** para se conectar automaticamente a essa rede quando o dispositivo estiver ao alcance. Escolha **Desabilitar** para impedir que dispositivos se conectem automaticamente.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.
- **Tipo de EAP**: escolha o tipo de Protocolo EAP (Extensible Authentication Protocol) usado para autenticar conexões sem fio seguras. Suas opções: 

  - **EAP-TLS**: também inserir:

    - **Confiança do Servidor** - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede e é usado para autenticar a conexão.

      Selecione **OK** para salvar suas alterações.

    - **Autenticação de Cliente** - **Certificado do cliente para autenticação de cliente (certificado de identidade)**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      Selecione **OK** para salvar suas alterações.

  - **EAP-TTLS**: também inserir:

    - **Confiança do Servidor** - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede e é usado para autenticar a conexão.

      Selecione **OK** para salvar suas alterações.

    - **Autenticação de Cliente** — escolha um **método de Autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP (identidade interna)**: escolha como você autentica a conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi.

          Suas opções: **Senha não criptografada (PAP)**, **Protocolo CHAP (CHAP)**, **Microsoft CHAP (MS-CHAP)**, ou **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

        Selecione **OK** para salvar suas alterações.

      - **Privacidade de identidade (identidade externa)**: insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **PEAP**: insira também:

    - **Confiança do Servidor** - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede e é usado para autenticar a conexão.

      Selecione **OK** para salvar suas alterações.

    - **Autenticação de Cliente** — escolha um **método de Autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP para autenticação (identidade interna)**: escolha como você autentica a conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi.

          Suas opções: **Nenhum** ou **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

        Selecione **OK** para salvar suas alterações.

      - **Privacidade de identidade (identidade externa)**: insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

Selecione **OK** > **Criar** para salvar suas alterações. O perfil será criado e exibido na lista de perfis.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua esse perfil](device-profile-assign.md).

## <a name="more-resources"></a>Mais recursos

- Confira as configurações disponíveis para dispositivos Android em [Configurações de Wi-Fi para dispositivos que executam o Android](wi-fi-settings-android.md).
- [Visão geral das configurações de Wi-Fi](wi-fi-settings-configure.md), incluindo outras plataformas.