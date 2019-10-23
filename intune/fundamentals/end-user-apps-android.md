---
title: Como os usuários Android podem obter aplicativos
description: Métodos para disponibilizar aplicativos do Android para usuários finais
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: fc5362df560d2e93bf5cd7a6cdc32a441d97d05c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505424"
---
# <a name="how-your-android-users-get-their-apps"></a>Como os usuários Android podem obter aplicativos

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Este artigo ajuda você a entender como e onde os usuários finais do Android obtêm os aplicativos que você distribui por meio do Microsoft Intune. As informações podem variar de acordo com o tipo de dispositivo (dispositivos Android nativos ou Samsung Knox Standard).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Dispositivos Android nativos (que não são Samsung Knox Standard)

| Tipo de aplicativo | Aplicativos LOB (Linha de negócios) | Aplicativos da Play Store  |
| ------------- |-------------| -----|
| Aplicativos disponíveis      | Os usuários tocam em **instalar** no Portal da Empresa. É exibida uma notificação, que os usuários tocam para iniciar a instalação. Após a instalação ser bem-sucedida, a notificação desaparece. | Os usuários tocam no aplicativo no Portal da Empresa e são levados para uma página do aplicativo na Play Store. É aqui que eles iniciam a instalação.|
| Required apps      | Os usuários veem uma notificação, que não podem ignorar, indicando que eles precisam instalar um aplicativo. Os usuários tocam a notificação para iniciar a instalação. Após a instalação ser bem-sucedida, a notificação desaparece.    | Os usuários veem uma notificação, que não podem ignorar, indicando que eles precisam instalar um aplicativo. Os usuários tocam na notificação e são levados para uma página do aplicativo na Play Store. É aqui que eles iniciam a instalação. Após a instalação ser bem-sucedida, a notificação desaparece. |

Os usuários finais precisam permitir a instalação de fontes desconhecidas para instalar [Aplicativos LOB](../apps/lob-apps-android.md). Normalmente, essa configuração encontra-se em dois locais diferentes:

* **Android 7.1.2 e anterior**: **Configurações** > **Segurança** > **Fontes desconhecidas**
* **Android 8.0 e posterior**: **Configurações** > **Aplicativos e notificações** > **Acesso a aplicativo especial** > **Instalar aplicativos desconhecidos** > **Portal da Empresa** > **Permitir desta fonte**

Se isso ocorrer, o aplicativo Portal da Empresa informará e orientará o usuário final diretamente para a configuração apropriada. 

## <a name="samsung-knox-standard-android-devices"></a>Dispositivos Samsung Knox Standard Android

| Tipo de aplicativo | Aplicativos LOB (Linha de negócios) | Aplicativos da Play Store  |
| ------------- |-------------| -----|
| Aplicativos disponíveis      | Os usuários tocam em **instalar** no Portal da Empresa. O aplicativo é instalado sem outras intervenções do usuário. | Os usuários tocam no aplicativo no Portal da Empresa e são levados para uma página do aplicativo na Play Store. É aqui que eles iniciam a instalação.|
| Required apps      | O aplicativo é instalado sem nenhuma outra intervenção do usuário.    | Os usuários veem uma notificação, que não podem ignorar, indicando que eles precisam instalar um aplicativo. Os usuários tocam na notificação e são levados para uma página do aplicativo na Play Store. É aqui que eles iniciam a instalação. Após a instalação ser bem-sucedida, a notificação desaparece. |

Aplicativos podem ser gerenciados ou não gerenciados, conforme descrito abaixo. O processo de criação de aplicativos gerenciados é o mesmo para todos os tipos de dispositivos Android.

**Aplicativos gerenciados** – aplicativos gerenciados por meio de políticas. Eles foram “encapsulados” pelo Intune ou criados com o SDK de Aplicativo do Intune. Esses aplicativos podem ser gerenciados pelo Intune e é possível aplicar políticas de aplicativo a eles.

**Aplicativos não gerenciados** – aplicativos não gerenciados por meio de políticas. Eles não foram encapsulados pelo Intune ou não incorporam o SDK de Aplicativo do Intune. Políticas de aplicativo não podem ser aplicadas a esses aplicativos.

## <a name="zebra-devices-with-zebra-mobility-extensions"></a>Dispositivos Zebra com Extensões de Mobilidade Zebra

O Intune usa o kit de ferramentas Extensões de Mobilidade Zebra (MX) para instalar aplicativos silenciosamente em dispositivos Zebra gerenciados pelo administrador do dispositivo. Esse recurso permite implantar e atualizar aplicativos em dispositivos Zebra sem intervenção do usuário. Se a versão MX do seu dispositivo for 4.2 ou anterior, os aplicativos não serão instalados silenciosamente. Para saber mais, confira [Matriz de Recursos MX Completa](http://techdocs.zebra.com/mx/compatibility/) no site da Zebra.

Os aplicativos LOB implantados nos dispositivos Zebra devem ser instalados em um local público no dispositivo. O pacote de aplicativos .apk pode estar acessível a outros aplicativos e serviços que também têm acesso ao armazenamento público no dispositivo. Normalmente, esse acesso consiste em uma pequena janela entre a conclusão do download do aplicativo e o início da instalação. Essa janela pode permitir um ataque. Por exemplo, um pacote .apk pode ser alterado durante esta janela. O Intune minimiza a quantidade de tempo que o .apk gasta no armazenamento público e não permite a instalação de aplicativos não assinados. Para ajudar a minimizar o risco à segurança, verifique se os arquivos .apk enviados não contêm informações confidenciais.

## <a name="see-also"></a>Consulte também

[Adicionar aplicativos com o Microsoft Intune](../apps/apps-add.md)

[Como usuários do iOS podem obter aplicativos](end-user-apps-ios.md)

[Como os usuários do Windows podem obter aplicativos](end-user-apps-windows.md)
