---
title: Gerenciar dispositivos com o Microsoft Intune
titleSuffix: ''
description: Examine os dispositivos gerenciados com o Intune e execute várias operações neles.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/21/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 436eeb306bf4ba343ae4d88a824aeed2077a3426
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>O que é o gerenciamento de dispositivo do Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Como um administrador de TI, você deve garantir que os dispositivos gerenciados estejam fornecendo os recursos de que os usuários finais precisam para fazer seu trabalho, protegendo simultaneamente esses dados de riscos.

A carga de trabalho **Dispositivos** fornece ideias sobre os dispositivos gerenciados e permite que você execute tarefas remotas neles. Para acessar a carga de trabalho:

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Em **Intune**, escolha **Dispositivos**.
4. Você pode exibir informações sobre dispositivos e executar as ações de dispositivo remoto conforme demonstrado a seguir:
    - **Visão geral** – um instantâneo dos dispositivos registrados que você pode gerenciar.
    - **Todos os dispositivos** – uma lista dos dispositivos registrados que você gerencia. Escolha **Filtro** ou **Colunas** para refinar as informações exibidas. Selecione um dispositivo para [exibir o inventário de dispositivo](device-inventory.md).
    - **Dispositivos do Azure AD** – uma lista de dispositivos registrados ou associados com o Azure AD (Active Directory). Saiba mais sobre o [gerenciamento de dispositivos do Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
    - **Ações de dispositivo** – um histórico das ações remotas executadas em dispositivos, incluindo a ação, o status dela, quem iniciou a ação e o horário.

        ![Captura de tela da monitoração das ações do dispositivo](./media/monitor-device-actions.png)

    - **logs de auditoria** – Os logs de auditoria fornecem um registro das atividades que geram uma alteração no Microsoft Intune. Saiba mais sobre [Logs de auditoria](monitor-audit-logs.md).
    - **Conector do TeamViewer** – Serviço do TeamViewer que permite que usuários de dispositivos Android gerenciados pelo Intune obtenham assistência remota de seu administrador de TI. Saiba mais sobre o [TeamViewer](device-profile-android-teamviewer.md).
    - **Ajuda e Suporte** – Solucione problemas, solicite suporte ou exiba o status do Intune.  
    
## <a name="available-device-actions"></a>Ações do dispositivo disponíveis
As ações disponíveis dependem da plataforma e da configuração do dispositivo.

- [Exibir inventário de dispositivo](device-inventory.md)
- Executar ações remotas de dispositivo:
    - [Remover os dados da empresa](devices-wipe.md#remove-company-data)
    - [Redefinição de fábrica](devices-wipe.md#factory-reset)
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

- Escolha **Ações do dispositivo** para ver o status das ações executadas nos dispositivos que você gerencia.
