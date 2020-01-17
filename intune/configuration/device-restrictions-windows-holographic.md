---
title: Configurações de dispositivo do Windows Holographic Business – Microsoft Intune – Azure | Microsoft Docs
description: Leia sobre e defina configurações de restrição de dispositivo no Microsoft Intune para o Windows Holographic for Business, incluindo cancelamento do registro, geolocalização, senhas, instalação de aplicativos da App Store, cookies e pop-ups no Microsoft Edge, Microsoft Defender, pesquisa, armazenamento e nuvem, conectividade por Bluetooth, hora do sistema e dados de uso no Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: df5fb0ba370bff4f5ec99852484dfb1fd2cc9f60
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206492"
---
# <a name="windows-holographic-for-business-device-settings-to-allow-or-restrict-features-using-intune"></a>Configurações do dispositivo do Windows Holographic for Business para permitir ou restringir os recursos usando o Intune



Este artigo lista e descreve as diferentes configurações que você pode controlar nos dispositivos do Windows Holographic for Business, como o Microsoft Hololens. Como parte de sua solução MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, segurança de controle e muito mais.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Geral

- **Cancelamento de registro manual**: Permite que o usuário exclua manualmente a conta da empresa do dispositivo.
- **Cortana**: Habilite ou desabilite o assistente de voz Cortana.
- **Localização geográfica**: Especifica se o dispositivo pode usar informações de serviços de localização.

## <a name="password"></a>Senha

- **Senha**: Exige que o usuário final insira uma senha para acessar o dispositivo.
- **Exige a senha quando o dispositivo retorna do estado ocioso**: Especifica que o usuário deve inserir uma senha para desbloquear o dispositivo.

## <a name="app-store"></a>Loja de aplicativos

- **Atualização automática de aplicativos da store**: Permite que aplicativos instalados da Microsoft Store sejam atualizados automaticamente.
- **Instalação de aplicativo confiável**: Permite que os aplicativos assinados com um certificado de confiança sejam carregados por sideload.
- **Desbloqueio do desenvolvedor**: Permite que configurações de desenvolvedor do Windows, como a permissão de sideload de aplicativos, sejam modificadas pelo usuário final.

## <a name="microsoft-edge-browser"></a>Navegador Microsoft Edge

- **Cookies**: Permite que o navegador salve cookies da Internet no dispositivo.
- **Pop-ups**: Bloqueia janelas pop-up no navegador (aplica-se a somente ao Windows 10 Desktop).
- **Pesquisar sugestões**: Permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa.
- **Gerenciador de senhas**: Habilite ou desabilite o recurso do Gerenciador de Senhas do Microsoft Edge.
- **Enviar cabeçalhos Do Not Track**: Configura o navegador Microsoft Edge para enviar cabeçalhos Do Not Track para sites visitados pelos usuários.

## <a name="microsoft-defender-smart-screen"></a>Tela inteligente do Microsoft defender

- **SmartScreen para Microsoft Edge**: Habilite o SmartScreen do Microsoft Edge para acessar downloads do site e de arquivos.

## <a name="search"></a>Pesquisar

- **Local de pesquisa** – Especifique se a pesquisa pode usar a localização. informações

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento

- **Conta Microsoft**: Permite que o usuário associe uma conta da Microsoft ao dispositivo.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade

- **Bluetooth**: Controla se o usuário pode habilitar e configurar o Bluetooth no dispositivo.
- **Detectabilidade de Bluetooth**: Permite que o dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth.
- **Anúncios do Bluetooth**: Permite que o dispositivo receba anúncios via Bluetooth.

## <a name="control-panel-and-settings"></a>Painel de controle e configurações

- **Modificação do horário do sistema**: Impede que o usuário final altere a data e hora do dispositivo.

## <a name="kiosk---obsolete"></a>Quiosque – obsoleto

Essas configurações são somente leitura e não podem ser alteradas. Para configurar o modo de quiosque, confira [Configurações de quiosque](kiosk-settings-holographic.md).

Um dispositivo de quiosque normalmente executa um aplicativo específico. Os usuários são impedidos de acessar quaisquer recursos ou funções no dispositivo fora do aplicativo de quiosque.

- **Modo de quiosque**: Identifica o tipo de modo de quiosque compatível com a política. As opções incluem:

  - **Não configurado** (padrão): A política não permite um modo de quiosque. 
  - **Quiosque de aplicativo único**: O perfil habilita o dispositivo a executar somente um aplicativo. Quando o usuário faz logon, um aplicativo específico inicia. Esse modo também impede que o usuário abrir novos aplicativos ou alterar o aplicativo em execução.
  - **Quiosques de vários aplicativos**: O perfil permite que o dispositivo execute vários aplicativos. Somente os aplicativos que você adicionar estão disponíveis ao usuário. O benefício de um quiosque de vários aplicativos ou de um dispositivo com finalidade fixa é proporcionar uma experiência fácil para as pessoas entenderem apenas acessando os aplicativos de que precisam. E removendo os aplicativos que não precisam de sua exibição. 
  
    Ao adicionar aplicativos para uma experiência de quiosque de vários aplicativos, você também adiciona um arquivo de layout do menu Iniciar. [Iniciar o arquivo de layout do menu](/hololens/hololens-kiosk#start-layout-file-for-mdm-intune-and-others) inclui um exemplo de XML que pode ser usado no Intune. 

### <a name="single-app-kiosks"></a>Quiosques de aplicativo único

Insira as seguintes configurações:

- **Conta de usuário**: Insira a conta de usuário local (do dispositivo) ou o logon da conta do Azure AD associado ao aplicativo de quiosque. Para contas ingressadas em domínios do Azure AD, especifique a conta usando o formato `domain\username@tenant.org`. 

    Para quiosques em ambientes de público com logon automático habilitado, um tipo de usuário com o privilégio mínimo (como a conta de usuário padrão local) deve ser usado. Para configurar uma conta do Azure AD (Active Directory) para o modo de quiosque, use o formato `AzureAD\user@contoso.com`.

- **ID de modelo de usuário do aplicativo (AUMID) do aplicativo**: Insira a AUMID do aplicativo de quiosque. Para saber mais, consulte [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (Encontrar a ID do modelo de usuário do aplicativo de um aplicativo instalado).

## <a name="reporting-and-telemetry"></a>Relatório e telemetria

- **Compartilhar dados de uso**: Selecione o nível de envio de dados de diagnóstico.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
