---
title: Em desenvolvimento – Microsoft Intune
titleSuffix: ''
description: Recursos do Microsoft Intune em desenvolvimento
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3645d07fe9a703f182e05bc9a7f9fbb93c413ddc
ms.sourcegitcommit: dfcf80a91792715404dc021c8684866c8b0a27e1
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65816237"
---
# <a name="in-development-for-microsoft-intune---may-2019"></a>Em desenvolvimento para o Microsoft Intune – maio de 2019

Para ajudá-lo em sua preparação e planejamento, esta página listas atualizações e recursos da interface do usuário do Intune que estão em desenvolvimento, mas ainda não foram liberados. Além disso:

- Se prevermos que você precisará agir antes de uma alteração, publicaremos uma postagem complementar do Centro de Mensagens do Office.
- Quando um recurso é lançado em produção, seja como versão prévia ou em disponibilidade geral, a descrição do recurso sairá dessa página, indo para a [página Novidades](whats-new.md).
- Esta página e a [página Novidades](whats-new.md) são atualizadas periodicamente. Volte a ela para verificar se há atualizações adicionais.
- Consulte o [Roteiro M365](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) para entregas estratégicas e linhas do tempo.

> [!Note]
> Esses itens refletem a expectativas atuais da Microsoft sobre as funcionalidades do Intune que estarão presentes em uma versão futura. As datas e os recursos individuais podem mudar. Nem todos os itens em desenvolvimento têm uma descrição de recurso nesta página.

**RSS feed**: receba uma notificação quando esta página for atualizada copiando e colando a seguinte URL em seu leitor de feed: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune no portal do Azure


<!-- 1905 start-->


### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Suporte de linha de base para pesquisa de palavra-chave  <!-- 3082036         -->
Em breve, ao criar ou editar um perfil de linha de base de segurança, você poderá usar a *pesquisa* para filtrar as configurações exibidas no console.   

### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Redefinir e apagar dispositivos em massa usando a API do Graph <!-- 3295288 -->
Você poderá redefinir e apagar até 100 dispositivos em massa, usando a API do Graph.

<!-- 1904 start-->

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Os usuários de dispositivos podem exibir todos os aplicativos gerenciados que você instalou ou tentou instalar <!-- 2352913 -->
O Portal da Empresa para Windows listará todos os aplicativos gerenciados&ndash; necessários e disponíveis&ndash; instalados em um dispositivo do usuário. Os usuários poderão exibir tentativas e instalações de aplicativos pendentes e o status atual. Se a sua organização não torna aplicativos obrigatórios ou disponíveis, os usuários veem uma mensagem explicando que nenhum aplicativo da empresa foi instalado. Os usuários também poderão classificar ou filtrar seus aplicativos por status de instalação.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Usar "regras de aplicabilidade" ao criar perfis de configuração de dispositivo do Windows 10 <!-- 2549910 -->
Você cria perfis de configuração de dispositivo do Windows 10 (**Configuração do dispositivo** > **Perfis** > **Criar perfil** > **Windows 10** para plataforma). Você poderá criar uma **regra de aplicabilidade** para que o perfil apenas se aplique a uma edição ou versão específica. Por exemplo, você pode criar um perfil que permita algumas configurações do BitLocker. Depois de adicionar o perfil, use uma regra de aplicabilidade para que o perfil só se aplique a dispositivos que executem o Windows 10 Enterprise.

Aplica-se a: 
- Windows 10 e posterior



## <a name="notices"></a>Avisos

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Consulte também
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.


