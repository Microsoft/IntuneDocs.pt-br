---
title: Configurações de dispositivo do Windows Holographic Business – Microsoft Intune – Azure | Microsoft Docs
description: Leia sobre e defina configurações de restrição de dispositivo no Microsoft Intune para o Windows Holographic for Business, incluindo cancelamento do registro, geolocalização, senhas, instalação de aplicativos da App Store, cookies e pop-ups no Microsoft Edge, Windows Defender, pesquisa, armazenamento e nuvem, conectividade por Bluetooth, hora do sistema e dados de uso no Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: fed8c33bbf4ff302d08576dc5e34ce1257425090
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565240"
---
# <a name="windows-holographic-for-business-device-settings-to-allow-or-restrict-features-using-intune"></a>Configurações do dispositivo do Windows Holographic for Business para permitir ou restringir os recursos usando o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo lista e descreve as diferentes configurações que você pode controlar nos dispositivos do Windows Holographic for Business, como o Microsoft Hololens. Como parte de sua solução MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, segurança de controle e muito mais.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Geral

- **Cancelamento de registro manual**: permite que o usuário exclua manualmente a conta de trabalho do dispositivo.
- **Cortana**: habilitar ou desabilitar a assistente de voz Cortana.
- **Geolocalização**: especifica se o dispositivo pode usar informações dos serviços de localização.

## <a name="password"></a>Senha

- **Senha**: exige que o usuário final insira uma senha para acessar o dispositivo.
- **Exigir senha quando o dispositivo retorna do estado ocioso**: especifica que o usuário deverá inserir uma senha para desbloquear o dispositivo.

## <a name="app-store"></a>Loja de aplicativos

- **Atualizar aplicativos automaticamente do repositório**: permite que os aplicativos instalados da Microsoft Store sejam atualizados automaticamente.
- **Instalação de aplicativo confiável**: permite que os aplicativos assinados com um certificado de confiança sejam carregados por sideload.
- **Desbloqueio do desenvolvedor**: permite que configurações de desenvolvedor do Windows, como a permissão de sideload de aplicativos, sejam modificadas pelo usuário final.

## <a name="microsoft-edge-browser"></a>Navegador Microsoft Edge

- **Cookies**: permite que o navegador salve cookies da Internet no dispositivo.
- **Pop-ups**: bloqueia janelas pop-up no navegador (aplica-se a somente ao Windows 10 Desktop).
- **Sugestões de Pesquisa**: permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa.
- **Gerenciador de Senhas**: habilite ou desabilite o recurso do Gerenciador de Senhas do Microsoft Edge.
- **Enviar cabeçalhos Do Not Track**: configura o navegador Microsoft Edge para enviar cabeçalhos Do Not Track para sites visitados pelos usuários.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **SmartScreen para Microsoft Edge**: habilite o SmartScreen do Microsoft Edge para acessar downloads de site e de arquivos.

## <a name="search"></a>Pesquisar

- **Local de pesquisa** – Especifique se a pesquisa pode usar a localização. Informações do

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento

- **Conta da Microsoft**: permite que o usuário associe uma conta da Microsoft ao dispositivo.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade

- **Bluetooth**: controla se o usuário pode habilitar e configurar o Bluetooth no dispositivo.
- **Detectabilidade de Bluetooth**: permite que o dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth.
- **Anúncio de Bluetooth**: permite que o dispositivo receba anúncios via Bluetooth.

## <a name="control-panel-and-settings"></a>Painel de controle e configurações

- **Modificação do Horário do Sistema**: impede que o usuário final altere a data e a hora do dispositivo.

## <a name="kiosk---obsolete"></a>Quiosque – obsoleto

Essas configurações são somente leitura e não podem ser alteradas. Para configurar o modo de quiosque, confira [Configurações de quiosque](kiosk-settings-holographic.md).

Um dispositivo de quiosque normalmente executa um aplicativo específico. Os usuários são impedidos de acessar quaisquer recursos ou funções no dispositivo fora do aplicativo de quiosque.

- **Modo de quiosque**: identifica o tipo de modo de quiosque compatível com a política. As opções incluem:

  - **Não Configurado** (padrão): a política não habilita um modo de quiosque. 
  - **Quiosque de aplicativo único**: o perfil habilita o dispositivo a executar somente um aplicativo. Quando o usuário faz logon, um aplicativo específico inicia. Esse modo também impede que o usuário abrir novos aplicativos ou alterar o aplicativo em execução.
  - **Quiosque de vários aplicativos**: o perfil permite que o dispositivo execute vários aplicativos. Somente os aplicativos que você adicionar estão disponíveis ao usuário. O benefício de um quiosque de vários aplicativos ou de um dispositivo com finalidade fixa é proporcionar uma experiência fácil para as pessoas entenderem apenas acessando os aplicativos de que precisam. E removendo os aplicativos que não precisam de sua exibição. 
  
    Ao adicionar aplicativos para uma experiência de quiosque de vários aplicativos, você também adiciona um arquivo de layout do menu Iniciar. [Iniciar o arquivo de layout do menu](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-file-for-intune) inclui um exemplo de XML que pode ser usado no Intune. 

#### <a name="single-app-kiosks"></a>Quiosques de aplicativo único

Insira as seguintes configurações:

- **Conta de usuário**: insira a conta de usuário local (para o dispositivo) ou o logon da conta do Azure AD associado ao aplicativo de quiosque. Para contas ingressadas em domínios do Azure AD, especifique a conta usando o formato `domain\username@tenant.org`. 

    Para quiosques em ambientes de público com logon automático habilitado, um tipo de usuário com o privilégio mínimo (como a conta de usuário padrão local) deve ser usado. Para configurar uma conta do Azure AD (Active Directory) para o modo de quiosque, use o formato `AzureAD\user@contoso.com`.

- **ID do modelo do usuário do aplicativo (AUMID)**: insira a AUMID do aplicativo de quiosque. Para saber mais, consulte [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (Encontrar a ID do modelo de usuário do aplicativo de um aplicativo instalado).

## <a name="reporting-and-telemetry"></a>Relatório e telemetria

- **Compartilhar dados de uso**: selecione o nível de envio de dados de diagnóstico.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
