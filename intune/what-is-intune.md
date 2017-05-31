---
title: "Introdução ao Intune na visualização do Portal do Azure"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: conheça as Noções básicas sobre o Intune na versão prévia do Portal do Azure e como ele pode ajudá-lo a gerenciar seus dispositivos."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 04/24/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 16d7ff50eb821e0927c3c6ea21f3cdb1257762a0
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Introdução ao Microsoft Intune na versão prévia do Portal do Azure


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

O Microsoft Intune está migrando para o Portal do Azure e isso significa que os fluxos de trabalho e as funcionalidades usados serão alterados.
O novo portal oferece uma visualização das funcionalidades novas e atualizadas no portal do Azure, em que você pode gerenciar os dispositivos móveis, os computadores e os aplicativos da sua organização.
Com o tempo, todas as funcionalidades do Intune serão movidas para o Azure, mas você já pode executar várias tarefas do Intune no Portal do Azure hoje mesmo. Como esta é uma nova experiência em versão prévia, algumas funcionalidades podem ainda não estar presentes no portal. Examine a seção [Novidades](#whats-new) para obter detalhes.

> [!IMPORTANT]
> **Ainda não consegue ver o novo portal?**<br>
> Já começamos a distribuir a versão prévia para locatários selecionados. Os locatários existentes serão migrados para a nova experiência a partir do ano de 2017. Você receberá uma notificação no Centro de Mensagens do Office antes da migração do locatário.
>
> As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de os fluxos de trabalho de registro da Apple estarem disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.


Você encontrará o novo documentação de produto nesta biblioteca e ele será atualizado continuamente durante a versão prévia. Se você tiver sugestões de elementos que gostaria de ver, deixe sua contribuição no tópico de comentários. Adoraríamos ouvir sua opinião.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Destaques da nova experiência incluem:

- Um console integrado para todos os seus componentes de EMS (Enterprise Mobility + Security)
- Um console baseado em HTML criado nos padrões da Web
- Suporte à API do Microsoft Graph para automatizar diversas ações
- Grupos do Azure Active Directory (AD) para fornecer compatibilidade entre todos os aplicativos do Azure
- Suporte para a maioria dos navegadores da Web modernos

Se você estiver buscando documentação para o console clássico do Intune, consulte a [Biblioteca de documentação do Intune](https://docs.microsoft.com/intune-classic/).

## <a name="before-you-start"></a>Antes de começar

Para usar o Intune no Portal do Azure, você deve ter uma conta de administrador e locatário Intune. [Inscreva-se em uma conta](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) se você ainda não tiver uma.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Navegadores da Web com suporte no Portal do Azure

O Portal do Azure é executado na maioria dos computadores, Macs e tablets. Não há suporte para telefones celulares.
No momento, há suporte para os seguintes navegadores:

- Microsoft Edge (última versão)
- Microsoft Internet Explorer 11
- Safari (última versão, somente Mac)
- Chrome (última versão)
- Firefox (última versão)

Visite o [portal do Azure](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) para obter as informações mais recentes sobre os navegadores com suporte.

## <a name="whats-in-this-library"></a>O que há nesta biblioteca?

A documentação reflete o layout do portal do Intune para tornar mais fácil encontrar as informações necessárias.

![Cargas de trabalho do Portal do Azure](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>Introdução
Esta seção contém informações sobre [novidades](whats-new.md), [problemas conhecidos](known-issues.md), [como obter suporte](get-support.md) e como [começar com uma avaliação gratuita](free-trial-sign-up.md) do Intune.
### <a name="plan-and-design"></a>Plano e design
Informações para ajudá-lo a [planejar e projetar](/intune-classic/plan-and-design/introduction) seu ambiente do Intune.
### <a name="device-enrollment"></a>Registro de dispositivo
[Como fazer o Intune gerenciar seus dispositivos](device-enrollment.md).
### <a name="device-compliance"></a>Conformidade do dispositivo
[Defina um nível de conformidade para seus dispositivos e faça relatórios sobre os dispositivos que não são compatíveis](device-compliance.md).
### <a name="device-configuration"></a>Configuração do dispositivo
[Entenda os perfis que você pode usar para definir as configurações e recursos nos dispositivos gerenciados](device-profiles.md).
### <a name="devices"></a>Dispositivos
[Familiarize-se com os dispositivos gerenciados com relatórios e inventários](device-management.md).
### <a name="mobile-apps"></a>Aplicativos móveis
[Como publicar, gerenciar, configurar e proteger os aplicativos](app-management.md).
### <a name="conditional-access"></a>Acesso condicional
[Restrinja o acesso aos serviços do Exchange com base nas condições que você especificar](conditional-access.md).
### <a name="on-premises-access"></a>Acesso local
[Configurar o acesso ao Exchange ActiveSync e ao Exchange local](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Usuários
[Saiba mais sobre os usuários de dispositivos que você gerencia e classifique os recursos em grupos](user-management.md).
### <a name="groups"></a>Grupos
[Saiba mais sobre como você pode usar grupos do Azure Active Directory com o Intune](groups-get-started.md)
### <a name="intune-roles"></a>Funções do Intune
[Controle quem pode executar várias ações do Intune e a quem essas ações se aplicam](role-based-access-control.md). Você pode usar as funções internas que abordam alguns cenários comuns do Intune ou pode criar suas próprias funções.
### <a name="software-updates"></a>Atualizações de software
[Saiba mais sobre como configurar atualizações de software para dispositivos com Windows 10](windows-update-for-business-configure.md).



## <a name="whats-new"></a>Quais são as novidades?

[Descubra o que há de novo na versão prévia](whats-new.md).

