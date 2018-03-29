---
title: Redefinir senhas de dispositivos com o Microsoft Intune – Azure | Microsoft Docs
description: Remova ou redefina a senha usando a ação remover senha nos dispositivos que você gerencia ou monitora com o Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4cca5922f036711093469e71489e267af53f05a9
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Redefinir ou remover uma senha de dispositivo no Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Para criar uma nova senha para um dispositivo, use a ação **Remover senha**.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows Phone 8.1 (não ingressado no Azure Active Directory), incluindo versões até a Atualização do Windows 10 para Criadores
- Atualização do Windows 10 para Criadores e posterior
- iOS
- Versões do Android anteriores ao Android 7

Esse recurso não é compatível com os seguintes sistemas:

- Windows
- macOS
- Android for Work

## <a name="reset-a-passcode"></a>Redefinir uma senha

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre pelo **Intune** e, em seguida, selecione **Microsoft Intune**.
3. Selecione **Dispositivos** e, em seguida, **Todos os dispositivos**.
4. Na lista de dispositivos que você gerencia, selecione um dispositivo e escolha **...Mais**. Em seguida, escolha a ação remota de dispositivo **Remover senha**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação realizada, em **Dispositivos**, selecione **Ações do dispositivo**.
