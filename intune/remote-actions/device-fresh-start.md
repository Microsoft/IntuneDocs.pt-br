---
title: Redefinir dispositivos Windows 10 com o Microsoft Intune – Azure | Microsoft Docs
description: Use Novo Início para remover ou desinstalar aplicativos em computadores Windows 10 usando o Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8e48b7dac5064f9daeb62e141a4c1b2a4adf11b7
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782188"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Usar o Novo Início para redefinir dispositivos Windows 10 com o Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

A ação do dispositivo **Novo Início** remove todos os aplicativos instalados em um PC executando o Windows 10, versão 1703 ou posterior. O Novo Início ajuda a remover os aplicativos (OEM) pré-instalados que normalmente são instalados em um computador novo. 

1. Entre no [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) e selecione **Dispositivos** > **Todos os dispositivos**.
2. Na lista de dispositivos que você gerencia, escolha um dispositivo de desktop Windows 10.
3. Clique em **Novo Início**. 
4. Selecione **manter os dados de usuário neste dispositivo** para:
   * Manter o dispositivo do Azure AD conectado
   * O dispositivo é registrado novamente no gerenciamento de dispositivo móvel quando um usuário habilitado do Azure Active Directory entra no dispositivo.
   * Manter o conteúdo da pasta base do usuário e remover aplicativos e configurações

  > [!IMPORTANT]
 > Se você não mantiver dados de usuário, o dispositivo será restaurado para o estado OOBE (configuração inicial pelo usuário) padrão e concluído, mantendo a conta de administrador interna.
 > Os dispositivos BYOD terão seus registros do Azure AD e do gerenciamento de dispositivos móveis cancelados.
 > Os dispositivos ingressados no Azure AD serão registrados no gerenciamento de dispositivo móvel novamente quando um usuário habilitado do Azure Active Directory entrar no dispositivo.
 
5. Clique em **OK**.   
6. Para ver o status dessa ação, volte para **Dispositivos** e clique em **Ações do dispositivo**.  
7. O dispositivo voltará à tela de entrada inicial.
