---
title: Desativar aplicativos
description: Saiba como desativar ou desinstalar aplicativos usando o Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 1851fa03d36ffe42a49fd557cdd0c2c6250726f4
ms.contentlocale: pt-br
ms.lasthandoff: 06/08/2017


---

# <a name="retire-apps-using-microsoft-intune"></a>Desativar aplicativos usando o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Para desativar um aplicativo, basta desinstalá-lo. Quando você implanta e gerencia aplicativos com o Intune, o processo de desinstalação do aplicativo é o mesmo para computadores Windows e dispositivos móveis. O aplicativo deve dar suporte ao processo de desinstalação para que o procedimento tenha êxito.

## <a name="uninstall-an-app"></a>Desinstalar um aplicativo

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Aplicativos** &gt; **Aplicativos**.

2.  Selecione o aplicativo que você deseja desinstalar (que já foi implantado anteriormente) e selecione **Gerenciar Implantação**.

3.  Na página **Ação de Implantação** , selecione **Desinstalar** na coluna **Aprovação** .

Quando o dispositivo ou computador verificar se existem aplicativos em seguida, o aplicativo será desinstalado.

### <a name="see-also"></a>Consulte também
[Adicionar aplicativos no Microsoft Intune](add-apps.md)

