---
title: Políticas de configuração de aplicativo do Microsoft Intune
titleSuffix: ''
description: Saiba como usar políticas de configuração de aplicativo em um dispositivo iOS ou Android no Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 844342d0d21110f46ac9a344edbd7409f7d779cb
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2019
ms.locfileid: "59567212"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>Políticas de configuração de aplicativo do Microsoft Intune

Use políticas de configuração de aplicativo no Microsoft Intune para fornecer definições de configuração para um aplicativo iOS ou Android. Essas definições de configuração permitem que um aplicativo seja personalizado. Você não atribui essas políticas de configuração diretamente a usuários e dispositivos. Em vez disso, você associa uma política de configuração a um aplicativo e, em seguida, atribui o aplicativo. As definições da política de configuração são usadas quando o aplicativo verifica se elas existem, normalmente, na primeira vez em que ele é executado.

Você pode atribuir uma política de configuração de aplicativo a um grupo de usuários e dispositivos usando uma combinação de atribuições de inclusão e exclusão. Depois de adicionar uma política de configuração de aplicativo, você pode definir as atribuições para política de configuração de aplicativo. Ao definir as atribuições para a política, você pode optar por incluir ou excluir os grupos de usuários para os quais a política se aplica. Ao optar por incluir um ou mais grupos, você pode optar por selecionar grupos específicos para incluir ou selecionar grupos internos. Os grupos internos incluem **Todos os Usuários**, **Todos os Dispositivos** e **Todos os Usuários + Todos os Dispositivos**.

Por exemplo, um aplicativo pode exigir que você especifique um dos seguintes detalhes:

- Um número de porta personalizado
- Configurações de idioma
- Configurações de segurança
- Configurações de identidade visual, como um logotipo da empresa

Quando os usuários inserem essas configurações incorretamente, isso pode aumentar a carga do suporte técnico e reduzir a adoção de novos aplicativos.

As políticas de configuração de aplicativo podem ajudar a eliminar esses problemas, permitindo que você atribua essas configurações para os usuários em uma política antes que eles executem o aplicativo. As configurações então são fornecidas automaticamente e os usuários não precisam executar nenhuma ação.

As definições de configuração são usadas sempre que o aplicativo verifica a existência delas. Normalmente, um aplicativo verifica as definições de configuração na primeira vez em que é executado pelo usuário.

Você tem duas opções de como usar as configurações do aplicativo com o Intune:
 - **Dispositivos gerenciados** – o dispositivo é gerenciado pelo Intune como o provedor de MDM (gerenciamento de dispositivo móvel).
 - **Aplicativos gerenciados** – um aplicativo é gerenciado sem registro de dispositivos.

> [!NOTE]
> Como administrador do Microsoft Intune, é possível controlar quais contas de usuário são adicionadas aos aplicativos do Microsoft Office em dispositivos gerenciados. É possível limitar o acesso apenas a contas permitidas de usuários corporativos e bloquear contas pessoais em dispositivos registrados. Os aplicativos de suporte processam a configuração do aplicativo, removem e bloqueiam contas não aprovadas.

## <a name="apps-that-support-app-configuration"></a>Aplicativos que dão suporte à configuração de aplicativo

Você pode usar políticas de configuração de aplicativo para aplicativos que dão suporte a elas. Para dar suporte à configuração de aplicativo no Intune, os aplicativos devem ter sido escritos para dar suporte ao uso de configurações de aplicativo. Consulte o fornecedor do aplicativo para obter mais detalhes.

É possível preparar seus aplicativos de linha de negócios incorporando o SDK de Aplicativo do Intune no aplicativo ou encapsulando o aplicativo ele ser desenvolvido. O SDK do Aplicativo do Intune, disponível para o iOS e o Android, habilita o aplicativo para as políticas de configuração de aplicativo do Intune. Ele se esforça para minimizar a quantidade de alterações de código necessárias do desenvolvedor do aplicativo. Para obter mais informações, consulte a [Visão geral do SDK de Aplicativo do Intune](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Suporte de API do Graph para configuração de aplicativo

Além disso, você pode usar a API do Graph para realizar as tarefas de configuração de aplicativo. Para saber mais, confira [Configuração direcionada do MAM na referência da API do Graph](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="next-steps"></a>Próximas etapas

### <a name="managed-devices"></a>Dispositivos gerenciados

 - Saiba como usar a configuração de aplicativo com seus dispositivos iOS.  Consulte [Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados](app-configuration-policies-use-ios.md).
 - Saiba como usar a configuração de aplicativo com seus dispositivos Android.  Consulte [Adicionar políticas de configuração de aplicativo para dispositivos Android gerenciados](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Aplicativos gerenciados

 - Saiba como usar a configuração de aplicativo com aplicativos gerenciados. Consulte [Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo](app-configuration-policies-managed-app.md).
