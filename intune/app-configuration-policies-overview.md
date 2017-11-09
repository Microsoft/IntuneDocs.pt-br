---
title: "Políticas de configuração de aplicativo do Intune | Microsoft Docs"
titlesuffix: Azure portal
description: "Saiba como usar políticas de configuração de aplicativo para o Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b690f691278d0cc708ed7e586e30aee4ed6e807a
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2017
---
# <a name="app-configuration-policies-for-intune"></a>Políticas de configuração de aplicativo para o Intune

Forneça configurações quando os usuários executarem um aplicativo iOS ou Android com as políticas de configuração de aplicativo no Microsoft Intune. Por exemplo, um aplicativo pode exigir que os usuários especifiquem:

- Um número de porta personalizado
- Configurações de idioma
- Configurações de segurança
- Configurações de identidade visual, como um logotipo da empresa

Quando os usuários inserem essas configurações incorretamente, isso pode aumentar a carga do suporte técnico e reduzir a adoção de novos aplicativos.

As políticas de configuração de aplicativo podem ajudar a eliminar esses problemas, permitindo que você atribua essas configurações para os usuários em uma política antes que eles executem o aplicativo. As configurações então são fornecidas automaticamente e os usuários não precisam executar nenhuma ação.

Você não atribui essas políticas diretamente para usuários e dispositivos. Em vez disso, você associa uma política a um aplicativo e atribui o aplicativo. As configurações de política serão usadas sempre que o aplicativo verificá-las, normalmente na primeira vez em que é executado.

Você tem duas opções de como usar as configurações do aplicativo com o Intune:
 - **Dispositivos gerenciados**  
   O dispositivo é gerenciado pelo Intune como o provedor de MDM.
 - **Aplicativos gerenciados**  
   Um aplicativo é gerenciado sem registro de dispositivo.

## <a name="apps-that-support-app-configuration"></a>Aplicativos que dão suporte à configuração de aplicativo

Você pode usar políticas de configuração de aplicativo para aplicativos que dão suporte a elas. Para dar suporte à configuração de aplicativo no Intune, os aplicativos devem ter sido escritos para dar suporte ao uso de configurações de aplicativo. Consulte o fornecedor do aplicativo para obter mais detalhes.

Você pode preparar seus aplicativos de linha de negócios incorporando o SDK de Aplicativo do Intune no aplicativo ou encapsulando o aplicativo após ele ter sido desenvolvido. O SDK do Aplicativo do Intune, disponível para iOS e Android, habilita o aplicativo para as políticas de proteção do aplicativo do Intune. Ele se esforça para minimizar a quantidade de alterações de código necessárias do desenvolvedor do aplicativo. Para obter mais informações, consulte a [Visão geral do SDK de Aplicativo do Intune](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Suporte de API do Graph para configuração de aplicativo

Além disso, você pode usar a API do Graph para realizar as tarefas de configuração de aplicativo. Para saber mais, confira [Configuração direcionada do MAM na referência da API do Graph](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="next-steps"></a>Próximas etapas

### <a name="managed-devices"></a>Dispositivos gerenciados

 - Saiba como usar a configuração de aplicativo com seus dispositivos iOS.  Consulte [Adicionar políticas de configuração de aplicativos para dispositivos iOS gerenciados](app-configuration-policies-use-ios.md).
 - Saiba como usar a configuração de aplicativo com seus dispositivos Android.  Consulte [Adicionar políticas de configuração de aplicativo para dispositivos Android gerenciados](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Aplicativos gerenciados

 - Saiba como usar a configuração de aplicativo com aplicativos gerenciados. Consulte [Adicionar políticas de configuração de aplicativo para aplicativos gerenciados sem registro de dispositivo](app-configuration-policies-managed-app.md).