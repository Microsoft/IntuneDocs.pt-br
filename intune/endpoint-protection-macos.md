---
title: Adicionar proteção de ponto de extremidade no macOS no Microsoft Intune – Azure | Microsoft Docs
description: Em dispositivos macOS, use o gatekeeper para determinar quais aplicativos podem ser instalados, incluindo a Mac App Store. Também habilite ou configure um firewall para permitir que aplicativos específicos, aplicativos de especificações de blocos, usem o modo oculto e até mesmo bloqueiem determinados tipos de conexões de entrada usando o Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c2c3a33b996a68263550fc05d3af853c263c930a
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565921"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>configurações de proteção de ponto de extremidade do macOS no Intune

Este artigo mostra as configurações de proteção de ponto de extremidade que você pode configurar para dispositivos que executam macOS. Essas configurações incluem as configurações de firewall e gatekeeper nesses dispositivos e podem ser configuradas usando um perfil de dispositivo no Microsoft Intune.

## <a name="gatekeeper"></a>Gatekeeper

- **Permitir aplicativos baixados destes locais**: limitar aplicativos dependendo do local do qual eles são baixados. A intenção é proteger dispositivos contra malware e permitir somente aplicativos de fontes confiáveis. Suas opções para permitir: 
  - **Mac App Store**
  - **Mac App Store e desenvolvedores identificados**
  - **Qualquer lugar**

- **O usuário pode substituir o Gatekeeper**: impede os usuários de ignorar a configuração do Gatekeeper e impede que os usuários cliquem em CTRL para instalar um aplicativo. Quando habilitado, os usuários podem clicar em CTRL em qualquer aplicativo e instalá-lo.

## <a name="firewall"></a>Firewall

Use o firewall para controlar conexões por aplicativo, em vez de por porta. Usar as configurações por aplicativo torna mais fácil aproveitar os benefícios da proteção de firewall. Também ajuda a impedir que aplicativos indesejáveis assumam o controle de portas de rede abertas para aplicativos legítimos.

- **Use o firewall para proteger os dispositivos contra acesso à rede não autorizado controlando conexões por aplicativo.**
  - **Firewall**: habilite o Firewall para configurar como as conexões de entrada são tratadas em seu ambiente.
  - **Conexões de entrada**: bloqueie todas as conexões de entrada, exceto as conexões necessárias para serviços básicos da Internet, como DHCP, Bonjour e IPsec. Esse recurso também bloqueia todos os serviços de compartilhamento, como Compartilhamento de Arquivos e Compartilhamento de Tela. Se você estiver usando serviços de compartilhamento, mantenha essa configuração como **Não configurada**.

- **Permitir ou bloquear conexões de entrada para aplicativos específicos**
  - **Aplicativos permitidos**: selecione os aplicativos que explicitamente têm permissão para receber conexões de entrada.
  - **Aplicativos bloqueados**: selecione os aplicativos que devem bloquear conexões de entrada.
  - **Modo oculto**: para impedir que o computador responda a solicitações de investigação, habilite o modo oculto. O dispositivo continua a responder a solicitações de entrada para aplicativos autorizados. Solicitações inesperadas, como o ICMP (ping), são ignoradas.
