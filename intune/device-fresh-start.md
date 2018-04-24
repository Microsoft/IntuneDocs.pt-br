---
title: Redefinir dispositivos Windows 10 com o Microsoft Intune – Azure | Microsoft Docs
description: Use Novo Início para remover ou desinstalar aplicativos em computadores Windows 10 usando o Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5658bf2e1ee250ef9fd405b3f7ec1772b166f338
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Usar o Novo Início para redefinir dispositivos Windows 10 com o Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A ação do dispositivo **Novo Início** remove aplicativos instalados em um computador Windows 10 que está executando a Atualização para Criadores. Em seguida, ela atualiza o computador automaticamente para a versão mais recente do Windows.

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