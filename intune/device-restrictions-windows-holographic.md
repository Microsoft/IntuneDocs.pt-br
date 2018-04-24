---
title: Restrições de dispositivo para o Windows Holographic for Business no Microsoft Intune – Azure | Microsoft Docs
description: Leia sobre e defina configurações de restrição de dispositivo no Microsoft Intune para o Windows Holographic for Business, incluindo cancelamento do registro, geolocalização, senhas, instalação de aplicativos da App Store, cookies e pop-ups no Edge, Windows Defender, pesquisa, armazenamento e nuvem, conectividade por Bluetooth, hora do sistema e dados de uso no Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/9/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5b0784aeb1dc1022b4be824c2f858f9525d03918
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="device-restriction-settings-for-windows-holographic-for-business-in-intune"></a>Configurações de restrição de dispositivo para o Windows Holographic for Business no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

As seguintes configurações de restrição de dispositivo são compatíveis com dispositivos que executam o Windows Holographic for Business, como o Microsoft Hololens.

## <a name="general"></a>Geral

- **Cancelamento de registro manual** – Permite que o usuário exclua manualmente a conta de trabalho do dispositivo.
- **Cortana** – Habilitar ou desabilitar a assistente de voz Cortana.
- **Geolocalização** – Especifica se o dispositivo pode usar informações de serviços de localização.

## <a name="password"></a>Senha
-   **Senha** – Exige que o usuário final insira uma senha para acessar o dispositivo.
    -   **Exigir senha quando o dispositivo retorna do estado ocioso** – Especifica que o usuário deverá inserir uma senha para desbloquear o dispositivo.

## <a name="app-store"></a>Loja de aplicativos

-   **Atualizar aplicativos automaticamente da loja** – Permite que os aplicativos instalados da Microsoft Store sejam atualizados automaticamente.
-   **Instalação de aplicativo confiável** - permite que os aplicativos assinados com um certificado de confiança sejam carregados por sideload.
-   **Desbloqueio do desenvolvedor** - permite que configurações de desenvolvedor do Windows, como a permissão de sideload de aplicativos, sejam modificadas pelo usuário final.

## <a name="edge-browser"></a>Navegador Edge

-   **Cookies** – Permite que o navegador salve cookies da Internet no dispositivo.
-   **Pop-ups** – Bloqueia janelas pop-up no navegador (aplica-se a somente ao Windows 10 Desktop).
-   **Sugestões de Pesquisa** – Permite que seu mecanismo de pesquisa sugira sites à medida que você digita frases de pesquisa.
-   **Gerenciador de Senhas** – Habilitar ou desabilitar o recurso de Gerenciador de Senhas do Edge.
- **Enviar cabeçalhos Do Not Track** – Configura o navegador Edge para enviar cabeçalhos Do Not Track para sites visitados pelos usuários.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **SmartScreen para Microsoft Edge** – habilite o SmartScreen do Edge para acessar downloads do site e de arquivos.

## <a name="search"></a>Pesquisar
- **Local de pesquisa** – Especifique se a pesquisa pode usar a localização. Informações do

## <a name="cloud-and-storage"></a>Nuvem e Armazenamento
-   **Conta da Microsoft** – Permite que o usuário associe uma conta da Microsoft ao dispositivo.

## <a name="cellular-and-connectivity"></a>Rede Celular e Conectividade

-   **Bluetooth** – Controla se o usuário pode habilitar e configurar o Bluetooth no dispositivo.
-   **Descoberta de Bluetooth** – Permite que o dispositivo seja descoberto por outros dispositivos habilitados para Bluetooth.
-   **Anúncios por Bluetooth** – Permite que o dispositivo receba anúncios via Bluetooth.

## <a name="control-panel-and-settings"></a>Painel de controle e configurações

- **Modificação do horário do sistema** - impede que o usuário final altere a data e hora do dispositivo.

## <a name="kiosk-preview"></a>Quiosque (Versão prévia)

Um dispositivo de quiosque normalmente executa um aplicativo específico. Os usuários são impedidos de acessar quaisquer recursos ou funções no dispositivo fora do aplicativo de quiosque.

- **Modo de quiosque** – identifica o tipo de modo de quiosque compatível com a política. As opções incluem:

  - **Não configurado** (padrão) – A política não habilita um modo de quiosque. 
  - **Quiosque de aplicativo único** – o perfil habilita o dispositivo a executar somente um aplicativo. Quando o usuário faz logon, um aplicativo específico inicia. Esse modo também impede que o usuário abrir novos aplicativos ou alterar o aplicativo em execução.

#### <a name="single-app-kiosks"></a>Quiosques de aplicativo único
Insira as seguintes configurações:

- **Conta de usuário** – insira a conta de usuário local (para o dispositivo) ou o logon da conta do Azure AD associado ao aplicativo de quiosque. Para contas ingressadas em domínios do Azure AD, especifique a conta usando o formato `domain\username@tenant.org`. 

    Para quiosques em ambientes de público com logon automático habilitado, um tipo de usuário com o privilégio mínimo (como a conta de usuário padrão local) deve ser usado. Para configurar uma conta do Azure AD (Active Directory) para o modo de quiosque, use o formato `AzureAD\user@contoso.com`.

- **AUMID (ID do modelo de usuário do aplicativo)** – insira a AUMID do aplicativo de quiosque. Para saber mais, consulte [Find the Application User Model ID of an installed app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (Encontrar a ID do modelo de usuário do aplicativo de um aplicativo instalado).

## <a name="reporting-and-telemetry"></a>Relatório e telemetria

- **Compartilhar dados de uso** – selecione o nível de envio de dados de diagnóstico.