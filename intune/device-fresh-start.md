---
title: "Redefinir dispositivos Windows 10 com o Microsoft Intune – Azure | Microsoft Docs"
description: "Use Novo Início para remover ou desinstalar aplicativos em computadores Windows 10 usando o Microsoft Intune, incluindo aplicativos pré-instalados de OEMs (fabricantes de equipamento originais). Também é possível manter o conteúdo da pasta base usando a configuração “se os dados do usuário são mantidos”."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d17c9dc11791f32f0c2c1e7faa88966c112fc6a5
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Usar o Novo Início para redefinir dispositivos Windows 10 com o Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação do dispositivo **Novo Início** remove todos os aplicativos instalados em um computador Windows 10 que executa a Atualização para Criadores. Em seguida, ela atualiza o computador automaticamente para a versão mais recente do Windows.

Essa ação ajuda a remover os aplicativos (OEM) pré-instalados que normalmente são instalados em um computador novo. Para manter o conteúdo da pasta base do usuário e remover apenas os aplicativos e as configurações, use a configuração `if user data is retained`.

> [!IMPORTANT]
> Novo Início cancela o registro do dispositivo no Intune, mas o dispositivo ainda permanece ingressado no Azure Active Directory.

## <a name="use-fresh-start"></a>Usar o Novo Início

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços**, filtre pelo **Intune** e selecione **Microsoft Intune**.
3. Selecione **Dispositivos** e, em seguida, selecione **Todos os dispositivos**.
4. Na lista de dispositivos que você gerencia, escolha um dispositivo de desktop Windows 10 e, em seguida, selecione **Novo Início**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status dessa ação, selecione **Ações do dispositivo** (**Microsoft Intune** > **Dispositivos**).