---
title: Adicionar aplicativos do sistema Android Enterprise ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar aplicativos do sistema Android Enterprise ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d45455a97f8016527dce49839b5493f16b173d43
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563652"
---
# <a name="add-android-enterprise-system-apps-to-microsoft-intune"></a>Adicionar aplicativos do sistema Android Enterprise ao Microsoft Intune

Antes de atribuir um aplicativo em um dispositivo ou um grupo de usuários, você deve primeiro adicionar o aplicativo ao Microsoft Intune. Os aplicativos do sistema são compatíveis com dispositivos Android Enterprise. Você pode habilitar um aplicativo de sistema para [dispositivos Android Enterprise dedicados](../enrollment/android-kiosk-enroll.md) ou para [dispositivos totalmente gerenciados](../enrollment/android-fully-managed-enroll.md).

## <a name="add-the-app"></a>Adicionar o aplicativo

Para adicionar um aplicativo do sistema Android Enterprise ao Intune no portal do Azure, faça o seguinte:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. No painel **Adicionar aplicativo**, sob **Outros** tipos disponíveis, selecione **Aplicativo do sistema Android Enterprise**.
4. Para configurar as informações do aplicativo, selecione **Configurar** e forneça as informações a seguir:
    - **Nome do Aplicativo**: Insira o nome do aplicativo.
    - **Editor**: Insira o nome do editor do aplicativo.  
    - **Nome do Pacote**: Insira o nome do pacote. O Intune determinará se o nome do pacote é válido.
5. Selecione **OK**.
6. Selecione **Adicionar**.

> [!NOTE]
> Você precisará trabalhar com o OEM do dispositivo para localizar o nome do pacote do aplicativo que deseja habilitar/desabilitar.

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que selecionar. 

Os aplicativos do sistema Android Enterprise habilitarão ou desabilitarão os aplicativos que já fazem parte da plataforma. Para habilitar um aplicativo do sistema, atribua-o como **Obrigatório**. Para desabilitar um aplicativo do sistema, atribua-o como **Desinstalar**. Os aplicativos do sistema não podem ser atribuídos como disponíveis para usuários.


## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos](apps-deploy.md)
