---
title: Configurar Intune
description: "Requisitos e pré-requisitos para começar a usar sua assinatura do Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fba27041fb55cfbef1cbba39e3679ce6884cd5f0
ms.sourcegitcommit: 0b164f806165d312acfc88815a60e325e3d02672
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2017
---
# <a name="set-up-intune"></a>Configurar Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Essas etapas de configuração ajudam a habilitar o MDM (gerenciamento de dispositivo móvel). Os dispositivos devem ser gerenciados antes que você possa fornecer aos usuários o acesso aos recursos da empresa ou gerenciar as configurações nesses dispositivos.

Algumas etapas, como configurar uma assinatura do Intune e configurar a autoridade de MDM, são necessárias para a maioria dos cenários. Outras etapas, como configurar um domínio personalizado ou adicionar aplicativos, são opcionais, dependendo das necessidades da sua empresa.

Caso esteja usando o Microsoft System Center Configuration Manager para gerenciar computadores e servidores, é possível [estender o Configuration Manager para gerenciar dispositivos móveis](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

>[!TIP]
>Você pode usar o *Benefício do FastTrack Center* ao comprar no mínimo 150 licenças para o Intune em um plano qualificado. Com esse serviço, os especialistas da Microsoft trabalharão junto a você para deixar o ambiente pronto para o Intune. Consulte [Benefício do FastTrack Center para o EMS (Enterprise Mobility + Security)](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program).



| Etapas | Status  |
| ------------- |-------------|
| 1  | [Pré-requisitos](supported-devices-browsers.md) – informações importantes antes de começar. Isso inclui configurações com suporte e requisitos de rede.|
| 2 |  [Entrar no Intune](account-sign-up.md) – entre na sua assinatura de avaliação ou crie uma nova assinatura do Intune. |  
| 3 | [Configurar nome de domínio](custom-domain-name-configure.md) – defina o registro de DNS para conectar o nome de domínio da sua empresa ao Intune. Essa opção fornece aos usuários um domínio familiar ao se conectar com o Intune e usar recursos.  |
| 4 | [Adicionar usuários](users-add.md) – adicione usuários manualmente ou conecte o Active Directory para sincronizar usuários com o Intune. Obrigatório, a menos que os dispositivos sejam de quiosque "sem usuário", por exemplo. |
| 5 | [Atribuir licenças](licenses-assign.md) – forneça aos usuários a permissão para usar o Intune. Cada usuário ou dispositivo sem usuário requer uma licença do Intune para acessar o serviço.|
| 6 |  [Adicionar grupos](groups-add.md) – use grupos de usuários e de dispositivos para simplificar as tarefas de gerenciamento. Os grupos são usados para atribuir aplicativos, configurações e outros recursos. |
| 7 | [Adicionar aplicativos](apps-add.md) – os aplicativos podem ser atribuídos a grupos e instalados automaticamente ou opcionalmente. |
| 8 | [Configurar dispositivos](device-profiles.md) – configure os perfis que gerenciarão as configurações de dispositivos. Os perfis de dispositivo podem predefinir as configurações de email, VPN, Wi-Fi e recursos do dispositivo. Eles também podem restringir os dispositivos para ajudar a proteger os dados e dispositivos.  |
| 9 | [Personalizar o Portal da Empresa](company-portal-app.md) –personalize o Portal da Empresa do Intune que os usuários usam para registrar dispositivos e instalar aplicativos. Essas configurações são exibidas no aplicativo Portal da Empresa e no site Portal da Empresa do Intune. |
| 10 | [Habilitar registro de dispositivo](mdm-authority-set.md) – Habilite o gerenciamento do Intune de dispositivos iOS, Windows, Mac e Android, definindo a autoridade de MDM e habilitando as plataformas específicas. |
