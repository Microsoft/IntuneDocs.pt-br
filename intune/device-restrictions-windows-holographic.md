---
title: Configurações de restrição de dispositivo do Microsoft Intune para Windows Holographic for Business
titleSuffix: ''
description: Conheça as definições do Intune que você pode usar para controlar as configurações e as funcionalidades do dispositivo em dispositivos que executam Windows Holographic for Business.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 694b81434a95f48abc98f5012460523420df58cc
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="microsoft-intune-windows-holographic-for-business-device-restriction-settings"></a>Configurações de restrição de dispositivo Windows Holographic for Business no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

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

-   **Navegador Microsoft Edge** – Permitir o uso do navegador da Web Edge no dispositivo.
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

## <a name="reporting-and-telemetry"></a>Relatório e telemetria

- **Compartilhar dados de uso** – selecione o nível de envio de dados de diagnóstico.