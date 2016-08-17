---
title: "Visão geral do ciclo de vida do aplicativo | Microsoft Intune"
description: "Saiba mais sobre o ciclo de vida de aplicativos gerenciados pelo Intune, desde sua adição até sua eventual aposentadoria."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f3b4b01844c9ab8a5de38e9a33f595cfc87b42a0
ms.openlocfilehash: 650c06072cdcf19cf3fd1b93454e5373772f0e14


---

# Visão geral do ciclo de vida do aplicativo

O ciclo de vida de aplicativo do Intune começa quando um aplicativo é adicionado e passa por outras fases até você removê-lo.

![O ciclo de vida do aplicativo](./media/app-lifecycle.png "the Intune app lifecycle")

## Adicionar

A primeira etapa na implantação do aplicativo é adicionar os aplicativos que você deseja gerenciar e implantar no Intune. Embora você possa trabalhar com vários tipos de aplicativos diferentes, os procedimentos básicos são os mesmos. Com o Intune, é possível adicionar aplicativos a [dispositivos registrados](add-apps-for-mobile-devices-in-microsoft-intune.md) ou a [computadores Windows gerenciados com o software cliente do Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).

## Implantar

Depois de adicionar o aplicativo ao Intune, você poderá [implantá-lo nos dispositivos gerenciados](deploy-apps.md). O Intune facilita esse processo e, após a implantação do aplicativo, você pode [monitorar o êxito](monitor-apps-in-microsoft-intune.md) da implantação por meio do console de administração do Intune. Além disso, em algumas lojas de aplicativos, como as da [Apple](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) e do [Windows](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md), é possível comprar licenças de aplicativo em massa para sua empresa. O Intune pode sincronizar dados com essas lojas, para que você possa implantar e acompanhar o uso da licença para esses tipos de aplicativos, diretamente no console de administração do Intune.

## Configurar

Como parte do ciclo de vida do aplicativo, são lançadas novas versões de aplicativos regularmente. O Intune fornece ferramentas para [atualizar aplicativos](update-apps-using-microsoft-intune.md) implantados para uma versão mais recente com facilidade. Além disso, é possível configurar funcionalidade extra em alguns aplicativos, por exemplo:
- As [políticas de configuração de aplicativo iOS](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md) fornecem configurações para aplicativos iOS compatíveis que são usadas quando o aplicativo é executado. Por exemplo, um aplicativo pode exigir configurações de identidade visual específicas ou o nome de um servidor para se conectar.
- As [políticas de navegador gerenciado](manage-internet-access-using-managed-browser-policies.md) ajudam a definir as configurações para o navegador gerenciado do Intune, que substitui o navegador padrão do dispositivo e permite restringir os sites que os usuários podem visitar.

## Proteger

O Intune oferece várias maneiras para ajudar a proteger os dados em seus aplicativos. Os principais métodos são:
- O [acesso condicional](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) controla o acesso ao email e outros serviços com base nas condições que você especificar. As condições incluem tipos de dispositivo ou conformidade com uma [política de conformidade do dispositivo](introduction-to-device-compliance-policies-in-microsoft-intune.md) implantada.
- O [MAM (gerenciamento de aplicativo móvel)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) funciona com aplicativos individuais para ajudar a proteger os dados da empresa utilizados por eles. Por exemplo, você pode restringir a cópia de dados entre os aplicativos gerenciados e não gerenciados, ou impedir que aplicativos sejam executados em dispositivos com jailbreak ou raiz.

## Desativar

Por fim, é provável que os aplicativos implantados fiquem desatualizados e precisem ser removidos. O Intune facilita [desativar aplicativos de serviço](retire-apps-using-microsoft-intune.md).



<!--HONumber=Aug16_HO2-->


