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
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: ede28a99224b3d0bd94a4300b4b8b85815ae9591


---

# Visão geral do ciclo de vida do aplicativo

O ciclo de vida do aplicativo do Intune começa quando um aplicativo é adicionado e passa pelas fases adicionais até você removê-los.

![O ciclo de vida do aplicativo](./media/app-lifecycle.png "the Intune app lifecycle")

## Adicionar

A primeira etapa na implantação do aplicativo é adicionar os aplicativos que você deseja gerenciar e implantar no Intune. Embora haja muitos tipos de aplicativos diferentes com que você pode trabalhar, os procedimentos básicos são os mesmos. O Intune permite que você adicione aplicativos a [dispositivos registrados](add-apps-for-mobile-devices-in-microsoft-intune.md) ou a [computadores Windows que você gerencia com o software cliente do Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).

## Implantar

Depois de adicionar o aplicativo ao Intune, poderá [implantá-lo em dispositivos que você gerencia](deploy-apps.md). O Intune facilita esse processo e quando o aplicativo é implantado, você pode [Monitorar o sucesso](monitor-apps-in-microsoft-intune.md) da implantação do console de administração do Intune. Além disso, algumas lojas de aplicativos, como as da [Apple](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) e do [Windows](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md) permitem adquirir licenças de aplicativo em massa para sua empresa. O Intune pode sincronizar dados com esses armazenamentos para permitir que você implante e controle o uso de licença para esses tipos de aplicativos diretamente do console de administração do Intune.

## Configurar

Como parte do ciclo de vida do aplicativo, são lançadas novas versões de aplicativos regularmente. O Intune fornece ferramentas para [atualizar aplicativos](update-apps-using-microsoft-intune.md) implantados para uma versão mais recente com facilidade. Além disso, alguns aplicativos permitem que você configure uma funcionalidade adicional, por exemplo:
- As [políticas de configuração de aplicativo do iOS](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md) permitem que você forneça configurações para aplicativos iOS compatíveis que são usadas quando o aplicativo é executado. Por exemplo, um aplicativo pode exigir configurações de identidade visual específicas ou o nome de um servidor para se conectar.
- [Políticas de navegador gerenciado](manage-internet-access-using-managed-browser-policies.md) ajudam s definir as configurações para o navegador gerenciado do Intune que substitui o navegador padrão do dispositivo e permite que você restrinja os sites que os usuários podem visitar.

## Proteger

O Intune oferece várias maneiras para ajudar a proteger os dados em seus aplicativos. Os principais métodos são:
- O [acesso condicional](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) permite que você controle o acesso ao email e outros serviços com base nas condições especificadas como tipos de dispositivo ou conformidade com um [política de conformidade do dispositivo](introduction-to-device-compliance-policies-in-microsoft-intune.md) é implantado.
- O [MAM (Gerenciamento de aplicativos móveis)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) funciona com aplicativos individuais para ajudar a proteger os dados da empresa que eles usam. Por exemplo, você pode restringir a cópia de dados entre os aplicativos gerenciados ou não gerenciados, ou pode impedir que aplicativos sejam executados em dispositivos que foram desbloqueados ou enraizados.

## Desativar

Por fim, é provável que os aplicativos que você implantou fiquem desatualizados e precisem ser removidos. O Intune facilita [desativar aplicativos de serviço](retire-apps-using-microsoft-intune.md).



<!--HONumber=Jul16_HO4-->


