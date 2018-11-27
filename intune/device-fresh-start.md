---
title: Redefinir dispositivos Windows 10 com o Microsoft Intune – Azure | Microsoft Docs
description: Use Novo Início para remover ou desinstalar aplicativos em computadores Windows 10 usando o Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: cd2320e4c3935c4865d785bbb2461bba20afffdb
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188731"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Usar o Novo Início para redefinir dispositivos Windows 10 com o Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A ação do dispositivo **Novo Início** remove todos os aplicativos instalados em um PC executando o Windows 10, versão 1703 ou posterior. O Novo Início ajuda a remover os aplicativos (OEM) pré-instalados que normalmente são instalados em um computador novo.  

1. Entre no [portal do Azure](https://portal.azure.com) e acesse > **Microsoft Intune** > **Dispositivos** > **Todos os Dispositivos**.
2. Na lista de dispositivos que você gerencia, escolha um dispositivo de desktop Windows 10.
3. Clique em **Novo Início**. 
4. Selecione **manter os dados de usuário neste dispositivo** para:
   * Manter o dispositivo do Azure AD conectado
    * Manter o dispositivo inscrito no gerenciamento de dispositivos móveis 
    * Manter o conteúdo da pasta base do usuário e remover aplicativos e configurações  
  > [!IMPORTANT]
 > Se você não mantiver os dados do usuário, o dispositivo será restaurado para seu estado inicial. Ele será retirado do Azure AD e do gerenciamento de dispositivos móveis. 
 
5. Clique em **OK**.   
6. Para ver o status dessa ação, volte para **Dispositivos** e clique em **Ações do dispositivo**.  
