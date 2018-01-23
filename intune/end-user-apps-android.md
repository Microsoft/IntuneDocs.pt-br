---
title: "Como os usuários Android podem obter aplicativos"
description: "Métodos para disponibilizar aplicativos do Android para usuários finais"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ad05e4eac40a6d3b8c522e893d8aea51de34c67a
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2018
---
# <a name="how-your-android-users-get-their-apps"></a>Como os usuários Android podem obter aplicativos

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Use estas informações para entender como e onde os usuários finais do Android obtêm os aplicativos que você distribui por meio do Microsoft Intune. As informações podem variar de acordo com o tipo de dispositivo (dispositivos Android nativos ou Samsung Knox Standard).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Dispositivos Android nativos (que não são Samsung Knox Standard)

| Tipo de aplicativo | Aplicativos LOB (Linha de negócios) | Aplicativos da Play Store  |
| ------------- |-------------| -----|
| Aplicativos disponíveis      | Os usuários tocam em **instalar** no Portal da Empresa. É exibida uma notificação, que os usuários tocam para iniciar a instalação. Após a instalação ser bem-sucedida, a notificação desaparece. | Os usuários tocam no aplicativo no Portal da Empresa e são levados para uma página do aplicativo na Play Store, em que podem iniciar a instalação.|
| Required apps      | Os usuários veem uma notificação, que não podem ignorar, indicando que eles precisam instalar um aplicativo. Os usuários tocam a notificação para iniciar a instalação. Após a instalação ser bem-sucedida, a notificação desaparece.    | Os usuários veem uma notificação, que não podem ignorar, indicando que eles precisam instalar um aplicativo. Os usuários tocam na notificação e são levados para uma página do aplicativo na Play Store, em que podem iniciar a instalação. Após a instalação ser bem-sucedida, a notificação desaparece. |

Os usuários finais precisam permitir a instalação de fontes desconhecidas para instalar [Aplicativos LOB](lob-apps-android.md). Normalmente, essa opção encontra-se em dois locais diferentes:

* **Android 7.1.2 e inferior**: **Configurações** > **Segurança** > **Fontes desconhecidas**
* **Android 8.0 e posterior**: **Configurações** > **Aplicativos e notificações** > **Acesso a aplicativo especial** > **Instalar aplicativos desconhecidos** > **Portal da Empresa** > **Permitir desta fonte**

Se isso ocorrer, o aplicativo Portal da Empresa informará e orientará o usuário final diretamente para a configuração apropriada. 


## <a name="samsung-knox-standard-android-devices"></a>Dispositivos Samsung Knox Standard Android

| Tipo de aplicativo | Aplicativos LOB (Linha de negócios) | Aplicativos da Play Store  |
| ------------- |-------------| -----|
| Aplicativos disponíveis      | Os usuários tocam em **instalar** no Portal da Empresa. O aplicativo é instalado sem outras intervenções do usuário. | Os usuários tocam no aplicativo no Portal da Empresa e são levados para uma página do aplicativo na Play Store, em que podem iniciar a instalação.|
| Required apps      | O aplicativo é instalado sem nenhuma outra intervenção do usuário.    | Os usuários veem uma notificação, que não podem ignorar, indicando que eles precisam instalar um aplicativo. Os usuários tocam na notificação e são levados para uma página do aplicativo na Play Store, em que podem iniciar a instalação. Após a instalação ser bem-sucedida, a notificação desaparece. |

Aplicativos podem ser gerenciados ou não gerenciados, conforme descrito abaixo. O processo de criação de aplicativos gerenciados é o mesmo para todos os tipos de dispositivos Android.

**Aplicativos gerenciados** – Aplicativos que podem ser gerenciados por meio de políticas. Eles foram “encapsulados” pelo Intune ou criados com o SDK de Aplicativo do Intune. Esses aplicativos podem ser gerenciados pelo Intune e é possível aplicar políticas de aplicativo a eles.

**Aplicativos não gerenciados** – Aplicativos que não podem ser gerenciados por meio de políticas. Eles não foram encapsulados pelo Intune ou não incorporam o SDK de Aplicativo do Intune. Políticas de aplicativo que não podem ser aplicadas a esses aplicativos.

### <a name="see-also"></a>Consulte também
[Adicionar aplicativos com o Microsoft Intune](apps-add.md)

[Como usuários do iOS podem obter aplicativos](end-user-apps-ios.md)

[Como os usuários do Windows podem obter aplicativos](end-user-apps-windows.md)
