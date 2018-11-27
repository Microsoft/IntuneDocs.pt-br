---
title: Definir configurações de Wi-Fi para dispositivos macOS no Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Crie ou adicione um perfil de configuração do dispositivo Wi-Fi para dispositivos macOS. Confira as diferentes configurações, incluindo a adição de certificados, a escolha de um tipo de EAP e a seleção de um método de autenticação no Microsoft Intune.
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
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6602a5507e4357899259722a7a8d095d540e2826
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181132"
---
# <a name="add-wi-fi-settings-for-macos-devices-in-microsoft-intune"></a>Adicionar configurações de Wi-Fi para dispositivos macOS no Microsoft Intune

Você pode criar um perfil com configurações de Wi-Fi específicas e implantar esse perfil em seus dispositivos macOS. O Microsoft Intune oferece muitos recursos, incluindo autenticação em sua rede, adição de um certificado PKS ou SCEP e muito mais.

Essas configurações de Wi-Fi são separadas em duas categorias: Configurações básicas e Configurações no nível da empresa.

Este artigo descreve essas configurações.

## <a name="before-you-begin"></a>Antes de começar

[Criar um perfil de dispositivo](device-profile-create.md).

## <a name="basic-profiles"></a>Perfis básicos

- **Tipo de Wi-Fi**: escolha **Básico**.
- **Nome da rede**: insira um nome para esta conexão Wi-Fi. Esse valor é o nome que os usuários verão ao navegarem pela lista de conexões disponíveis no dispositivo.
- **SSID**: abreviação de **service set identifier** (identificador de conjunto de serviço). Essa propriedade é o nome real da rede sem fio à qual os dispositivos se conectam. No entanto, os usuários veem apenas o nome de rede configurado ao escolher a conexão.
- **Conectar-se automaticamente**: escolha **Habilitar** para se conectar automaticamente a essa rede quando o dispositivo estiver ao alcance. Escolha **Desabilitar** para impedir que dispositivos se conectem automaticamente.
- **Rede oculta**: escolha **Habilitar** para ocultar esta rede da lista de redes disponíveis no dispositivo. O SSID não é transmitido. Escolha **Desabilitar** para exibir esta rede na lista de redes disponíveis no dispositivo.
- **Tipo de segurança**: selecione o protocolo de segurança para autenticar à rede Wi-Fi. Suas opções:

  - **Abrir (sem autenticação)**: use essa opção somente se a rede não for segura.
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

  - **EAP-FAST**: insira as **Configurações de PAC (Protected Access Credential)**. Essa opção usa credenciais de acesso protegido para criar um túnel autenticado entre o cliente e o servidor de autenticação. Suas opções:
    - **Não usar (PAC)**
    - **Usar (PAC)**: se houver um arquivo PAC, use-o.
    - **Usar e provisionar PAC**: crie e adicione o arquivo PAC aos seus dispositivos.
    - **Usar e provisionar PAC anonimamente**: crie e adicione o arquivo PAC aos seus dispositivos sem se autenticar no servidor.

  - **EAP-SIM**

  - **EAP-TLS**: também inserir:

    - **Confiança do Servidor** - **Nomes de servidores de certificados**: **adicione** um ou mais nomes comuns usados nos certificados emitidos pela autoridade de certificação confiável. Quando você inserir essas informações, poderá ignorar a janela de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.
    - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede e é usado para autenticar a conexão.

      Selecione **OK** para salvar suas alterações.

    - **Autenticação de Cliente** - **Certificado do cliente para autenticação de cliente (certificado de identidade)**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

      Selecione **OK** para salvar suas alterações.

  - **EAP-TTLS**: também inserir:

    - **Confiança do Servidor** - **Nomes de servidores de certificados**: **adicione** um ou mais nomes comuns usados nos certificados emitidos pela autoridade de certificação confiável. Quando você inserir essas informações, poderá ignorar a janela de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.
    - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede e é usado para autenticar a conexão.

      Selecione **OK** para salvar suas alterações.

    - **Autenticação de Cliente** — escolha um **método de Autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. Insira também:
        - **Método não EAP (identidade interna)**: escolha como você autentica a conexão. Certifique-se de escolher o mesmo protocolo configurado em sua rede Wi-Fi.

          Suas opções: **Senha não criptografada (PAP)**, **Protocolo CHAP (CHAP)**, **Microsoft CHAP (MS-CHAP)**, ou **Microsoft CHAP Versão 2 (MS-CHAP v2)**

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

        Selecione **OK** para salvar suas alterações.

      - **Privacidade de identidade (identidade externa)**: insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

  - **LEAP**

  - **PEAP**: insira também:

    - **Confiança do Servidor** - **Nomes de servidores de certificados**: **adicione** um ou mais nomes comuns usados nos certificados emitidos pela autoridade de certificação confiável. Quando você inserir essas informações, poderá ignorar a janela de confiança dinâmica mostrada em dispositivos de usuário quando eles se conectam à rede Wi-Fi.
    - **Certificado raiz para validação do servidor**: escolha um perfil de certificado raiz confiável existente. Esse certificado é apresentado ao servidor quando o cliente se conecta à rede e é usado para autenticar a conexão.

      Selecione **OK** para salvar suas alterações.

    - **Autenticação de Cliente** — escolha um **método de Autenticação**. Suas opções:

      - **Nome de usuário e senha**: solicita ao usuário um nome de usuário e uma senha para autenticar a conexão. 

      - **Certificados**: escolha o perfil de certificado do cliente SCEP ou PKCS que também é implantado no dispositivo. Esse certificado é a identidade apresentada pelo dispositivo ao servidor para autenticar a conexão.

        Selecione **OK** para salvar suas alterações.

      - **Privacidade de identidade (identidade externa)**: insira o texto enviado em resposta a uma solicitação de identidade de EAP. Esse texto pode ser qualquer valor, como `anonymous`. Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.

- **Configurações de proxy**: suas opções:
  - **Nenhum**: nenhuma configuração de proxy é definida.
  - **Manual**: insira o **Endereço do servidor proxy** como um endereço IP e seu **Número da porta**.
  - **Automático**: use um arquivo para configurar o servidor proxy. Digite a **URL do servidor proxy** (por exemplo, `http://proxy.contoso.com`) que contém o arquivo de configuração.

Selecione **OK** > **Criar** para salvar suas alterações. O perfil será criado e exibido na lista de perfis.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua esse perfil](device-profile-assign.md).

## <a name="more-resources"></a>Mais recursos

[Visão geral das configurações de Wi-Fi](wi-fi-settings-configure.md), incluindo outras plataformas disponíveis.