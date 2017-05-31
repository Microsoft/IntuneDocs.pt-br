---
title: Desativar aplicativos | Microsoft Docs
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
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 670e108fc4f672b4900f7cfb4e0127e16a377fa7
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


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

