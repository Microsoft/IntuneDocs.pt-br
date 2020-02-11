---
title: Adicionar aplicativos do sistema Android Enterprise ao Microsoft Intune
titleSuffix: ''
description: Saiba como adicionar aplicativos do sistema Android Enterprise ao Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
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
ms.openlocfilehash: 613369070d847265f371a7b228a2b6d81bf813fe
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755248"
---
# <a name="add-android-enterprise-system-apps-to-microsoft-intune"></a>Adicionar aplicativos do sistema Android Enterprise ao Microsoft Intune

Antes de atribuir um aplicativo em um dispositivo ou um grupo de usuários, você deve primeiro adicionar o aplicativo ao Microsoft Intune. Os aplicativos do sistema são compatíveis com dispositivos Android Enterprise. Você pode habilitar um aplicativo de sistema para [dispositivos Android Enterprise dedicados](../enrollment/android-kiosk-enroll.md) ou para [dispositivos totalmente gerenciados](../enrollment/android-fully-managed-enroll.md).

## <a name="add-the-app"></a>Adicionar o aplicativo

Para adicionar um aplicativo do sistema Android Enterprise ao Intune no portal do Azure, faça o seguinte:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos** > **Adicionar**.
3. No painel **Selecionar tipo de aplicativo**, sob **Outros** tipos disponíveis, selecione **Aplicativo do sistema Android Enterprise**.
4. Clique em **Selecionar**. As etapas de **Adicionar aplicativo** são exibidas.
No painel **Informações do aplicativo**, adicione os detalhes do aplicativo:
    - **Nome do Aplicativo**: Insira o nome do aplicativo.
    - **Editor**: Insira o nome do editor do aplicativo.  
    - **Nome do Pacote**: Insira o nome do pacote. O Intune determinará se o nome do pacote é válido.
5. Clique em **Avançar** para exibir a página **Marcas de escopo**.
8. Clique em **Selecionar marcas de escopo** para adicionar opcionalmente marcas de escopo no aplicativo. Para saber mais, confira [Usar o RBAC (controle de acesso baseado em função) e marcas de escopo para TI distribuída](~/fundamentals/scope-tags.md).
9. Clique em **Avançar** para exibir a página **Atribuições**.
10. Selecione as atribuições de grupo para o aplicativo. Para saber mais, confira [Adicionar grupos para organizar usuários e dispositivos](~/fundamentals/groups-add.md). 
11. Clique em **Avançar** para exibir a página **Revisar + criar**. Examine os valores e as configurações que você inseriu para o aplicativo.
12. Quando terminar, clique em **Criar** para adicionar o aplicativo ao Intune.

A folha **Visão geral** do aplicativo criado é exibida.

> [!NOTE]
> Você precisará trabalhar com o OEM do dispositivo para localizar o nome do pacote do aplicativo que deseja habilitar/desabilitar.

O aplicativo que você criou é exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que selecionar. 

Os aplicativos do sistema Android Enterprise habilitarão ou desabilitarão os aplicativos que já fazem parte da plataforma. Para habilitar um aplicativo do sistema, atribua-o como **Obrigatório**. Para desabilitar um aplicativo do sistema, atribua-o como **Desinstalar**. Os aplicativos do sistema não podem ser atribuídos como disponíveis para usuários.


## <a name="next-steps"></a>Próximas etapas

- [Atribuir aplicativos a grupos](apps-deploy.md)
