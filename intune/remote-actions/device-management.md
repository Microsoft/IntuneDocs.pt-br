---
title: Gerenciar dispositivos com o Microsoft Intune – Azure | Microsoft Docs
description: Examine os dispositivos gerenciados com o Microsoft Intune, incluindo a exportação de uma lista de dispositivos em formato CSV, exibir seus dispositivos ingressados no Azure Active Directory, examine um log de alterações de ações no dispositivo, use o Conector do TeamViewer para permitir que os administradores de TI solucionem problemas de dispositivos Android remotamente e exiba todas as ações que você pode executar em seus dispositivos.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/19/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: a3ee6240d9efb0d09c41a6a9b1260cd4189927a8
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509423"
---
# <a name="what-is-microsoft-intune-device-management"></a>O que é o gerenciamento de dispositivo do Microsoft Intune?

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Como um administrador de TI, você deve garantir que os dispositivos gerenciados estejam fornecendo os recursos de que os usuários precisam para trabalhar, protegendo os dados contra riscos.

A carga de trabalho **Dispositivos** fornece ideias sobre os dispositivos gerenciados e permite que você execute tarefas remotas neles.

## <a name="get-to-your-devices"></a>Obter seus dispositivos

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecione **Dispositivos**. Essa exibição mostra informações detalhadas sobre os dispositivos individuais, e o que você pode fazer com eles, incluindo:

   - **Visão geral** mostra um instantâneo visual dos dispositivos registrados e também quantos dispositivos estão usando diferentes plataformas, incluindo Android, iOS e muito mais.
   - **Todos os dispositivos** mostra uma lista dos dispositivos registrados que você gerencia.

     Use o recurso **Exportar** para criar uma lista .csv de todos os dispositivos, em incrementos de 10.000 (Internet Explorer) ou 30.000 (Microsoft Edge, Chrome).

     Escolha algum dispositivo para [exibir detalhes adicionais sobre ele](device-inventory.md), incluindo detalhes de hardware, aplicativos instalados, status da política de conformidade e muito mais.

   - **Dispositivos do Azure AD** mostra uma lista de dispositivos registrados ou adicionados ao Azure AD (Active Directory). Saiba mais sobre o [gerenciamento de dispositivos do Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
   - **Ações do dispositivo**: inclui um histórico das ações remotas executadas em diferentes dispositivos, incluindo a ação, o status, quem a iniciou e o horário.

     ![Captura de tela da monitoração das ações do dispositivo](./media/device-management/monitor-device-actions.png)

   - **Logs de auditoria** são um registro das atividades que geram uma alteração no Intune. [Logs de auditoria](../fundamentals/monitor-audit-logs.md) fornecem mais detalhes.
   - O **Conector do TeamViewer** é um serviço do TeamViewer que permite aos usuários de dispositivos Android gerenciados pelo Intune obter assistência remota do administrador de TI. Saiba mais sobre o [TeamViewer](teamviewer-support.md).
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
  - [Controle remoto para Android](teamviewer-support.md)
  - [Sincronizar dispositivo](device-sync.md)
  - [Enviar notificações personalizadas](custom-notifications.md#send-a-custom-notification-to-a-single-device) (Android, iOS)

## <a name="next-steps"></a>Próximas etapas

- Em **Todos os dispositivos**, selecione um dispositivo para exibir mais detalhes sobre o dispositivo específico.
- Escolha **Ações do dispositivo** para ver o status das ações executadas nos dispositivos que você gerencia.
