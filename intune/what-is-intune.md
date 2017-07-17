---
title: "Introdução ao Intune no portal do Azure"
titleSuffix: Intune on Azure
description: "Conheça os conceitos básicos do Intune no portal do Azure e como ele pode ajudar você a gerenciar seus dispositivos."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 06/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7549f3277c23c3951090502f2babfe7c47b0a201
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Introdução ao Microsoft Intune no portal do Azure
<a id="introduction-to-microsoft-intune-in-the-azure-portal" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Microsoft Intune agora está no portal do Azure, o que significa que a funcionalidade e os fluxos de trabalho conhecidos agora são diferentes.
O novo portal oferece uma funcionalidade nova e atualizada no portal do Azure, em que você pode gerenciar os dispositivos móveis, computadores e aplicativos de sua organização.

> [!IMPORTANT]
> **Ainda não consegue ver o novo portal?**<br>
> Os locatários existentes estão sendo migrados para a nova experiência. Uma notificação é mostrada no Centro de Mensagens do Office antes da migração do locatário.
>
> As contas do Intune criadas antes de janeiro de 2017 precisam de uma migração única antes que os fluxos de trabalho do Registro da Apple estejam disponíveis no Azure. O agendamento para a migração ainda não foi anunciado. Caso sua conta existente não possa acessar o portal do Azure, recomendamos criar uma conta de avaliação.
>
> Examine a lista de possíveis bloqueadores (em inglês) em https://blogs.technet.microsoft.com/intunesupport/2017/05/17/intune-migration-blockers-for-grouping-targeting/


Encontre informações sobre o novo portal nesta biblioteca, que está sempre sendo atualizada. Caso tenha sugestões que gostaria de ver, deixe seus comentários nos comentários do tópico. Adoraríamos ouvir sua opinião.

Destaques da nova experiência incluem:

- Um console integrado para todos os seus componentes de EMS (Enterprise Mobility + Security)
- Um console baseado em HTML criado nos padrões da Web
- Suporte à API do Microsoft Graph para automatizar diversas ações
- Grupos do Azure Active Directory (AD) para fornecer compatibilidade entre todos os aplicativos do Azure
- Suporte para a maioria dos navegadores da Web modernos

Se você estiver buscando documentação para o console clássico do Intune, consulte a [Biblioteca de documentação do Intune](https://docs.microsoft.com/intune-classic/).

## Antes de começar
<a id="before-you-start" class="xliff"></a>

Para usar o Intune no Portal do Azure, você deve ter uma conta de administrador e locatário Intune. [Inscreva-se em uma conta](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) se você ainda não tiver uma.

## Navegadores da Web com suporte no Portal do Azure
<a id="supported-web-browsers-for-the-azure-portal" class="xliff"></a>

O Portal do Azure é executado na maioria dos computadores, Macs e tablets. Não há suporte para telefones celulares.
No momento, há suporte para os seguintes navegadores:

- Microsoft Edge (última versão)
- Microsoft Internet Explorer 11
- Safari (última versão, somente Mac)
- Chrome (última versão)
- Firefox (última versão)

Visite o [portal do Azure](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) para obter as informações mais recentes sobre os navegadores com suporte.

## O que há nesta biblioteca?
<a id="whats-in-this-library" class="xliff"></a>

A documentação reflete o layout do portal do Intune para tornar mais fácil encontrar as informações necessárias.

![Cargas de trabalho do Portal do Azure](./media/azure-portal-workloads.png)

### Introdução
<a id="introduction-and-get-started" class="xliff"></a>
Esta seção contém [informações de introdução](introduction-intune.md) que ajudam você a começar a usar o Intune.
### Plano e design
<a id="plan-and-design" class="xliff"></a>
Informações para ajudá-lo a [planejar e projetar](/intune-classic/plan-design/introduction) seu ambiente do Intune.
### Registro de dispositivo
<a id="device-enrollment" class="xliff"></a>
[Como fazer o Intune gerenciar seus dispositivos](device-enrollment.md).
### Conformidade do dispositivo
<a id="device-compliance" class="xliff"></a>
[Defina um nível de conformidade para seus dispositivos e, depois, relate os dispositivos que não estão em conformidade](device-compliance.md).
### Configuração do dispositivo
<a id="device-configuration" class="xliff"></a>
[Entenda os perfis que você pode usar para definir as configurações e recursos nos dispositivos gerenciados](device-profiles.md).
### Dispositivos
<a id="devices" class="xliff"></a>
[Familiarize-se com os dispositivos gerenciados com relatórios e inventários](device-management.md).
### Aplicativos móveis
<a id="mobile-apps" class="xliff"></a>
[Como publicar, gerenciar, configurar e proteger os aplicativos](app-management.md).
### Acesso condicional
<a id="conditional-access" class="xliff"></a>
[Restrinja o acesso aos serviços do Exchange com base nas condições que você especificar](conditional-access.md).
### Acesso local
<a id="on-premises-access" class="xliff"></a>
[Configurar o acesso ao Exchange ActiveSync e ao Exchange local](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### Usuários
<a id="users" class="xliff"></a>
[Saiba mais sobre os usuários de dispositivos que você gerencia e classifique os recursos em grupos](user-management.md).
### Grupos
<a id="groups" class="xliff"></a>
[Saiba mais sobre como você pode usar grupos do Azure Active Directory com o Intune](groups-get-started.md)
### Funções do Intune
<a id="intune-roles" class="xliff"></a>
[Controle quem pode executar várias ações do Intune e a quem essas ações se aplicam](role-based-access-control.md). Você pode usar as funções internas que abordam alguns cenários comuns do Intune ou pode criar suas próprias funções.
### Atualizações de software
<a id="software-updates" class="xliff"></a>
[Saiba mais sobre como configurar atualizações de software para dispositivos com Windows 10](windows-update-for-business-configure.md).



## Quais são as novidades?
<a id="whats-new" class="xliff"></a>

[Conheça as novidades do Intune](whats-new.md).
