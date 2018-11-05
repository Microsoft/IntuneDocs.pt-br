---
title: Usar configurações de dispositivo personalizadas no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil para usar configurações personalizadas para dispositivos Windows Phone, Windows 8.1, Windows 10 e posteriores, Android, Android Enterprise, macOS e iOS usando o Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3106f71b59019a1cf71680c51be6dfcb4ce10b0d
ms.sourcegitcommit: c969b596ec0fec227484c50f210ba4e159e2e533
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49983067"
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Criar um perfil com configurações personalizadas no Intune

## <a name="what-are-custom-profiles"></a>O que são perfis personalizados

O Microsoft Intune inclui várias configurações internas para controlar recursos diferentes em um dispositivo. Você também pode criar perfis personalizados. Perfis personalizados são ótimos quando você deseja usar configurações do dispositivo e recursos que não são internos ao Intune. Esses perfis incluem recursos e configurações para que você controlar nos dispositivos em sua organização. Por exemplo, você pode criar um perfil personalizado que define o mesmo recurso para todos os dispositivos iOS.

Para obter mais informações sobre perfis de configuração, veja [O que são perfis de dispositivo do Microsoft Intune?](device-profiles.md). 

Este artigo inclui links para criar perfis personalizados para Android Enterprise, Android, iOS, macOS e Windows.

## <a name="available-platforms"></a>Plataformas disponíveis

As configurações personalizadas são definidas forma diferente para cada plataforma. Por exemplo, para controlar recursos em dispositivos Android e Windows, você pode inserir valores OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Para dispositivos da Apple, você pode importar um arquivo criado com o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) ou com o [Gerenciador de Perfis da Apple](https://support.apple.com/profile-manager).

Perfis personalizados são criados de modo semelhante aos perfis internos e estão disponíveis nas seguintes plataformas:

- [Android](custom-settings-android.md)
- [Android Enterprise](custom-settings-android-for-work.md)
- [iOS](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)

## <a name="next-steps"></a>Próximas etapas

Escolha sua plataforma e comece a trabalhar:

- [Android](custom-settings-android.md)
- [Android Enterprise](custom-settings-android-for-work.md)
- [iOS](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)