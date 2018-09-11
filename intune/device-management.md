---
title: Gerenciar dispositivos com o Microsoft Intune – Azure | Microsoft Docs
description: Examine os dispositivos gerenciados com o Microsoft Intune, incluindo a exportação de uma lista de dispositivos em formato CSV, exibir seus dispositivos ingressados no Azure Active Directory, examine um log de alterações de ações no dispositivo, use o Conector do TeamViewer para permitir que os administradores de TI solucionem problemas de dispositivos Android remotamente e exiba todas as ações que você pode executar em seus dispositivos.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/02/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: 8ae7a15f623b82cabed5314c4770c2edef902414
ms.sourcegitcommit: 18f51ae8291b57562921e40fc364a5a60a59b139
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253554"
---
# <a name="what-is-microsoft-intune-device-management"></a>O que é o gerenciamento de dispositivo do Microsoft Intune?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Como um administrador de TI, você deve garantir que os dispositivos gerenciados estejam fornecendo os recursos de que os usuários precisam para trabalhar, protegendo os dados contra riscos.

A carga de trabalho **Dispositivos** fornece ideias sobre os dispositivos gerenciados e permite que você execute tarefas remotas neles.

## <a name="get-to-your-devices"></a>Obter seus dispositivos

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Dispositivos**. Essa exibição mostra informações detalhadas sobre os dispositivos individuais, e o que você pode fazer com eles, incluindo:

   - **Visão geral** mostra um instantâneo visual dos dispositivos registrados e também quantos dispositivos estão usando diferentes plataformas, incluindo Android, iOS e muito mais.
   - **Todos os dispositivos** mostra uma lista dos dispositivos registrados que você gerencia.

     Use o recurso **Exportar** para criar uma lista .csv de todos os dispositivos, em incrementos de 10.000 (Internet Explorer) ou 30.000 (Edge, Chrome).

     Selecione qualquer dispositivo para [exibir detalhes adicionais sobre o dispositivo](device-inventory.md), incluindo detalhes de hardware, aplicativos instalados, status da política de conformidade e muito mais.

   - **Dispositivos do Azure AD** mostra uma lista de dispositivos registrados ou adicionados ao Azure AD (Active Directory). Saiba mais sobre o [gerenciamento de dispositivos do Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
   - **Ações do dispositivo**: inclui um histórico das ações remotas executadas em diferentes dispositivos, incluindo a ação, o status, quem a iniciou e o horário.

     ![Captura de tela da monitoração das ações do dispositivo](./media/monitor-device-actions.png)

   - **Logs de auditoria** são um registro das atividades que geram uma alteração no Intune. [Logs de auditoria](monitor-audit-logs.md) fornecem mais detalhes.
   - O **Conector do TeamViewer** é um serviço do TeamViewer que permite aos usuários de dispositivos Android gerenciados pelo Intune obter assistência remota do administrador de TI. Saiba mais sobre o [TeamViewer](device-profile-android-teamviewer.md).
   - **Ajuda e suporte** oferece um atalho nas dicas de solução de problemas, solicitando suporte ou verificando o status do Intune.

## <a name="available-device-actions"></a>Ações do dispositivo disponíveis
As ações disponíveis dependem da plataforma e da configuração do dispositivo.

- [Exibir inventário de dispositivo](device-inventory.md)
- Execute as ações do dispositivo remoto:
    - [Desativar](devices-wipe.md#retire)
    - [Apagamento](devices-wipe.md#wipe)
    - [Bloqueio remoto](device-remote-lock.md)
    - [Redefinir senha](device-passcode-reset.md)
    - [Bypass do bloqueio de ativação](device-activation-lock-bypass.md) (somente iOS)
    - [Novo Início](device-fresh-start.md) (somente Windows)
    - [Modo perdido](device-lost-mode.md) (somente iOS)
    - [Localizar dispositivo](device-locate.md) (somente iOS)
    - [Reiniciar](device-restart.md) (somente Windows)
    - [Redefinir o PIN do Windows 10](device-windows-pin-reset.md)
    - [Controle remoto para Android](device-profile-android-teamviewer.md)
    - [Sincronizar dispositivo](device-sync.md)

## <a name="next-steps"></a>Próximas etapas

- Em **Todos os dispositivos**, selecione um dispositivo para exibir mais detalhes sobre o dispositivo específico.
- Escolha **Ações do dispositivo** para ver o status das ações executadas nos dispositivos que você gerencia.
