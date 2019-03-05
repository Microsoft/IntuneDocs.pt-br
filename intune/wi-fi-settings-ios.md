---
title: Definir as configurações de Wi-Fi para dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Crie ou adicione um perfil de configuração de dispositivo Wi-Fi para dispositivos iOS. Confira as diferentes configurações, incluindo a adição de certificados, a escolha de um tipo de EAP e a seleção de um método de autenticação no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1b2640a28fde07a69da3cb154e198e0ebbbd73ea
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57234640"
---
# <a name="add-wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>Adicionar configurações de Wi-Fi para dispositivos iOS no Microsoft Intune

Você pode criar um perfil com configurações de Wi-Fi específicas e implantar esse perfil em seus dispositivos iOS. O Microsoft Intune oferece muitos recursos, incluindo autenticação em sua rede, adição de um certificado PKS ou SCEP e muito mais.

Essas configurações de Wi-Fi são separadas em duas categorias: Configurações básicas e configurações de nível empresarial.

Este artigo descreve essas configurações.

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de dispositivo](device-profile-create.md).

## <a name="basic-profiles"></a>Perfis básicos

- **Tipo de Wi-Fi**: Escolha **básica**.
- **Nome da rede**: insira um nome para esta conexão Wi-Fi. Esse valor é o nome que os usuários verão ao navegarem pela lista de conexões disponíveis no dispositivo.
- **SSID**: abreviação de **service set identifier** (identificador de conjunto de serviço). Essa propriedade é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o nome de rede configurado ao escolher a conexão.
- **Conectar-se automaticamente**: escolha **Habilitar** para se conectar automaticamente a essa rede quando o dispositivo estiver ao alcance. Escolha **Desabilitar** para impedir que dispositivos se conectem automaticamente.
- **Rede oculta**: Escolher **Habilitar** se o SSID da rede não é transmitido. Escolher **Desabilitar** se o SSID da rede é transmitido e visível.
- **Tipo de segurança**: selecione o protocolo de segurança para autenticar à rede Wi-Fi. Suas opções:

  - **Abrir (sem autenticação)**: use essa opção somente se a rede não for segura.
  - **WPA/WPA2 – Pessoal**: insira a senha em **Chave pré-compartilhada**. Quando a rede da sua organização é definida ou configurada, uma senha ou chave de rede também é configurada. Insira essa senha ou chave de rede para o valor PSK.
  - **WEP**

- **Configurações de proxy**: Suas opções:
  - **Nenhum**: Nenhuma configuração de proxy está definida.
  - **Manual**: Insira o **Endereço do servidor proxy** como um endereço IP e seu **Número da porta**.
  - **Automática**: Use um arquivo para configurar o servidor proxy. Digite a **URL do servidor proxy** (por exemplo, `http://proxy.contoso.com`) que contém o arquivo de configuração.

## <a name="enterprise-profiles"></a>Perfis corporativos

- **Tipo de Wi-Fi**: escolha **Corporativo**.
- **SSID**: abreviação de **service set identifier** (identificador de conjunto de serviço). Essa propriedade é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o nome de rede configurado ao escolher a conexão.
- **Conectar-se automaticamente**: escolha **Habilitar** para se conectar automaticamente a essa rede quando o dispositivo estiver ao alcance. Escolha **Desabilitar** para impedir que dispositivos se conectem automaticamente.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.

- **Tipo de EAP**: escolha o tipo de protocolo EAP (Extensible Authentication) usado para autenticar conexões sem fio seguras. Suas opções:

  - **EAP-FAST**: Insira as **Configurações de PAC (Protected Access Credential)**. Essa opção usa credenciais de acesso protegido para criar um túnel autenticado entre o cliente e o servidor de autenticação. Suas opções:
    - **Não usar (PAC)**
    - **Usar (PAC)**: Se houver um arquivo PAC, use-o.
    - **Usar e Provisionar PAC**: Crie e adicione o arquivo PAC aos seus dispositivos.
    - **Usar e Provisionar PAC anonimamente**: Crie e adicione o arquivo PAC aos seus dispositivos sem se autenticar no servidor.

  - **EAP-SIM**

  - **EAP-TLS**: Insira também:

    - **Servidor de confiabilidade** - **Nomes de certificado do servidor**: **Adicione** um ou mais nomes comuns usados nos certificados emitidos pela AC (autoridade de certificação) confiável. Quando você inserir essas informações, poderá ignorar a janela de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.
    - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede e é usado para autenticar a conexão.

      Selecione **OK** para salvar suas alterações.

    - **Autenticação de cliente** - **certificado do cliente para autenticação de cliente (Certificado de identidade)**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      Selecione **OK** para salvar suas alterações.

  - **EAP-TTLS**: Insira também:

    - **Servidor de confiabilidade** - **Nomes de certificado do servidor**: **Adicione** um ou mais nomes comuns usados nos certificados emitidos pela AC (autoridade de certificação) confiável. Quando você inserir essas informações, poderá ignorar a janela de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.
    - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede e é usado para autenticar a conexão.

      Selecione **OK** para salvar suas alterações.

    - **Autenticação de Cliente** — escolha um **método de Autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP (identidade interna)**: escolha como você fará a autenticação da conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi.

          Suas opções: **Senha não criptografada (PAP)**, **Protocolo CHAP (CHAP)**, **Microsoft CHAP (MS-CHAP)** ou **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

        Selecione **OK** para salvar suas alterações.

      - **Privacidade de identidade (identidade externa)**: insira o texto enviado na resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **LEAP**

  - **PEAP**: Insira também:

    - **Servidor de confiabilidade** - **Nomes de certificado do servidor**: **Adicione** um ou mais nomes comuns usados nos certificados emitidos pela AC (autoridade de certificação) confiável. Quando você inserir essas informações, poderá ignorar a janela de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.
    - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede e é usado para autenticar a conexão.

      Selecione **OK** para salvar suas alterações.

    - **Autenticação de Cliente** — escolha um **método de Autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. 

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

        Selecione **OK** para salvar suas alterações.

      - **Privacidade de identidade (identidade externa)**: insira o texto enviado na resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

- **Configurações de proxy**: Suas opções:
  - **Nenhum**: Nenhuma configuração de proxy está definida.
  - **Manual**: Insira o **Endereço do servidor proxy** como um endereço IP e seu **Número da porta**.
  - **Automática**: Use um arquivo para configurar o servidor proxy. Digite a **URL do servidor proxy** (por exemplo, `http://proxy.contoso.com`) que contém o arquivo de configuração.

Selecione **OK** > **Criar** para salvar suas alterações. O perfil será criado e exibido na lista de perfis.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua esse perfil](device-profile-assign.md).

## <a name="more-resources"></a>Mais recursos

[Visão geral das configurações de Wi-Fi](wi-fi-settings-configure.md), incluindo outras plataformas disponíveis.
