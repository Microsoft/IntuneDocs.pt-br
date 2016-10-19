---
title: "Como os usuários Android podem obter aplicativos | Microsoft Intune"
description: "Métodos para disponibilizar aplicativos do Android para usuários finais"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 627914b2ac877c1b5ff5bc95f7f2098ab8988250
ms.openlocfilehash: 98e712fb852c89c1d092b87482f30ada33010a33


---


# Como os usuários Android podem obter aplicativos
Use estas informações para entender como e onde os usuários finais do Android obtêm os aplicativos que você distribui por meio do Microsoft Intune. As informações podem variar de acordo com o tipo de dispositivo (dispositivos Android nativos ou Samsung Knox).

## Dispositivos Android (não Samsung Knox) nativos

| Tipo de aplicativo | Aplicativos LOB (Linha de negócios) | Aplicativos da Play Store  |
| ------------- |-------------| -----|
| Aplicativos disponíveis      | Os usuários tocam em **instalar** no Portal da Empresa. É exibida uma notificação, que os usuários tocam para iniciar a instalação. Após a instalação ser bem-sucedida, a notificação desaparece. | Os usuários tocam no aplicativo no Portal da Empresa e são levados para uma página do aplicativo na Play Store, em que podem iniciar a instalação.|
| Required apps      | Os usuários veem uma notificação, que não podem ignorar, indicando que eles precisam instalar um aplicativo. Os usuários tocam a notificação para iniciar a instalação. Após a instalação ser bem-sucedida, a notificação desaparece.    | Os usuários veem uma notificação, que não podem ignorar, indicando que eles precisam instalar um aplicativo. Os usuários tocam na notificação e são levados para uma página do aplicativo na Play Store, em que podem iniciar a instalação. Após a instalação ser bem-sucedida, a notificação desaparece. |

## Dispositivos Android não Samsung Knox

| Tipo de aplicativo | Aplicativos LOB (Linha de negócios) | Aplicativos da Play Store  |
| ------------- |-------------| -----|
| Aplicativos disponíveis      | Os usuários tocam em **instalar** no Portal da Empresa. O aplicativo é instalado sem outras intervenções do usuário. | Os usuários tocam no aplicativo no Portal da Empresa e são levados para uma página do aplicativo na Play Store, em que podem iniciar a instalação.|
| Required apps      | O aplicativo é instalado sem nenhuma outra intervenção do usuário.    | Os usuários veem uma notificação, que não podem ignorar, indicando que eles precisam instalar um aplicativo. Os usuários tocam na notificação e são levados para uma página do aplicativo na Play Store, em que podem iniciar a instalação. Após a instalação ser bem-sucedida, a notificação desaparece. |

Aplicativos podem ser gerenciados ou não gerenciados, conforme descrito abaixo. O processo de criação de aplicativos gerenciados é o mesmo para todos os tipos de dispositivos Android.

**Aplicativos gerenciados** – Aplicativos que podem ser gerenciados por meio de políticas. Eles foram “encapsulados” pelo Intune ou criados com o SDK (Software Development Kit) do MAM (Mobile Application Management) do Intune. Esses aplicativos podem ser gerenciados pelo Intune e é possível aplicar políticas de aplicativo a eles.

**Aplicativos não gerenciados** – Aplicativos que não podem ser gerenciados por meio de políticas. Eles não foram encapsulados pelo Intune ou não incorporam o SDK do MAM do Intune. Políticas de aplicativo que não podem ser aplicadas a esses aplicativos.

### Consulte também
[Adicionar aplicativos com o Microsoft Intune](/intune/deploy-use/add-apps)

[Como os usuários iOS podem obter aplicativos](how-your-ios-users-get-their-apps.md)

[Como os usuários Windows podem obter aplicativos](how-your-windows-users-get-their-apps.md)



<!--HONumber=Oct16_HO2-->


