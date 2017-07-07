---
title: "Visão geral do ciclo de vida do aplicativo"
description: "Saiba mais sobre o ciclo de vida de aplicativos gerenciados pelo Intune, desde sua adição até sua eventual aposentadoria."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cf505bec8a07923db78a870e4d7bfd64660e681c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="overview-of-the-app-lifecycle"></a>Visão geral do ciclo de vida do aplicativo

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

O ciclo de vida de aplicativo do Intune começa quando um aplicativo é adicionado e passa por outras fases até você removê-lo.

![O ciclo de vida do aplicativo](./media/app-lifecycle.png "o ciclo de vida do aplicativo do Intune")

## <a name="add"></a>Adicionar

A primeira etapa na implantação do aplicativo é adicionar ao Intune os aplicativos que você deseja gerenciar e atribuir. Embora você possa trabalhar com vários tipos de aplicativos diferentes, os procedimentos básicos são os mesmos. Com o Intune, é possível adicionar aplicativos a [dispositivos registrados](apps-add.md) ([portal Clássico](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)) ou a [computadores Windows gerenciados com o software cliente do Intune](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune).

## <a name="deploy"></a>Implantar

Depois de adicionar o aplicativo ao Intune, você poderá [atribuí-lo aos usuários e dispositivos gerenciados](apps-deploy.md) ([portal Clássico](/intune-classic/deploy-use/deploy-apps)). O Intune facilita esse processo e, após a implantação do aplicativo, você poderá [monitorar o sucesso](apps-monitor.md) ([portal Clássico](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)) da implantação no console de administração do Intune. Além disso, em algumas lojas de aplicativos, como as da [Apple](vpp-apps-ios.md) ([portal Clássico](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)) e do [Windows](windows-store-for-business.md) ([portal Clássico](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)), você pode comprar licenças de aplicativo em massa para sua empresa. O Intune pode sincronizar dados com essas lojas, para que você possa implantar e acompanhar o uso da licença para esses tipos de aplicativos, diretamente no console de administração do Intune.

## <a name="configure"></a>Configurar

Como parte do ciclo de vida do aplicativo, são lançadas novas versões de aplicativos regularmente. O Intune fornece ferramentas para [atualizar aplicativos](apps-add.md) com facilidade ([portal Clássico](/intune-classic/deploy-use/update-apps-using-microsoft-intune)) que foram implantados em uma versão mais recente. Além disso, é possível configurar funcionalidade extra em alguns aplicativos, por exemplo:
- As [políticas de configuração de aplicativo do iOS](app-configuration-policies-use-ios.md) ([portal Clássico](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)) fornecem configurações para aplicativos iOS em conformidade que são usadas quando o aplicativo é executado. Por exemplo, um aplicativo pode exigir configurações de identidade visual específicas ou o nome de um servidor para se conectar.
- As [políticas de navegador gerenciado](app-configuration-managed-browser.md) ([portal Clássico](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)) ajudam a definir as configurações do navegador gerenciado do Intune, que substitui o navegador padrão do dispositivo e permite restringir os sites que os usuários podem visitar.

## <a name="protect"></a>Proteger

O Intune oferece várias maneiras para ajudar a proteger os dados em seus aplicativos. Os principais métodos são:
- O [acesso condicional](conditional-access.md) ([portal Clássico](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)) controla o acesso a email e a outros serviços de acordo com as condições especificadas. As condições incluem tipos de dispositivo ou conformidade com uma [política de conformidade do dispositivo](device-compliance.md) ([portal Clássico](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)) implantada.
- As [políticas de proteção de aplicativo](app-protection-policy.md) ([portal Clássico](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)) funcionam com aplicativos individuais para ajudar a proteger os dados da empresa usados por eles. Por exemplo, você pode restringir a cópia de dados entre os aplicativos gerenciados e não gerenciados, ou impedir que aplicativos sejam executados em dispositivos com jailbreak ou raiz.

## <a name="retire"></a>Desativar

Por fim, é provável que os aplicativos implantados fiquem desatualizados e precisem ser removidos. O Intune facilita a [desativação de aplicativos do serviço](device-management.md) ([portal Clássico](/intune-classic/deploy-use/retire-apps-using-microsoft-intune)).
