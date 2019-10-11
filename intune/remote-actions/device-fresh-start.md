---
title: Redefinir dispositivos Windows 10 com o Microsoft Intune – Azure | Microsoft Docs
description: Use Novo Início para remover ou desinstalar aplicativos em computadores Windows 10 usando o Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/09/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 01ecfda5b173b2fc9dcef893789614bfbcc7c90b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728241"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Usar o Novo Início para redefinir dispositivos Windows 10 com o Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

A ação do dispositivo **Novo Início** remove todos os aplicativos instalados em um PC executando o Windows 10, versão 1703 ou posterior. O Novo Início ajuda a remover os aplicativos (OEM) pré-instalados que normalmente são instalados em um computador novo. 

1. Entre no [portal do Azure](https://portal.azure.com) e acesse > **Microsoft Intune** > **Dispositivos** > **Todos os Dispositivos**.
2. Na lista de dispositivos que você gerencia, escolha um dispositivo de desktop Windows 10.
3. Clique em **Novo Início**. 
4. Selecione **manter os dados de usuário neste dispositivo** para:
   * Manter o dispositivo do Azure AD conectado
   * O dispositivo é registrado no gerenciamento de dispositivo móvel novamente quando um usuário habilitado do Azure Active Directory entra no dispositivo.
   * Manter o conteúdo da pasta base do usuário e remover aplicativos e configurações

  > [!IMPORTANT]
 > Se você não mantém dados de usuário, o dispositivo será restaurado para o estado padrão concluído OOBE (configuração inicial pelo usuário) retendo a conta de administrador interna.
 > Os dispositivos BYOD terão seus registros do Azure AD e do gerenciamento de dispositivos móveis cancelados.
 > Os dispositivos ingressados no Azure AD serão registrados no gerenciamento de dispositivo móvel novamente quando um usuário habilitado do Azure Active Directory entrar no dispositivo.
 
5. Clique em **OK**.   
6. Para ver o status dessa ação, volte para **Dispositivos** e clique em **Ações do dispositivo**.  
7. O dispositivo será restaurado para a tela de entrada inicial.
