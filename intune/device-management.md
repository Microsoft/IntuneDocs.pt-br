---
title: Gerenciar dispositivos com o Intune
titleSuffix: Intune on Azure
description: "Saiba como ver os dispositivos gerenciados com o Intune e executar várias operações neles."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b034e144aa43d239874b484acb2a40be12aff7c
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>O que é o gerenciamento de dispositivo do Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Como um administrador de TI, você deve garantir que os dispositivos gerenciados estejam fornecendo os recursos de que os usuários finais precisam para fazer seu trabalho, protegendo simultaneamente esses dados de riscos.

A carga de trabalho **Dispositivos** fornece ideias sobre os dispositivos gerenciados e permite que você execute tarefas remotas neles. Para acessar a carga de trabalho:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Em **Intune**, escolha **Dispositivos**.
4. Você pode exibir informações sobre dispositivos e executar as ações de dispositivo remoto conforme demonstrado a seguir:
    - **Visão geral** – um instantâneo dos dispositivos registrados que você pode gerenciar.
    - **Todos os dispositivos** – uma lista dos dispositivos registrados que você gerencia. Escolha **Filtro** ou **Colunas** para refinar as informações exibidas. Selecione um dispositivo para [exibir o inventário de dispositivo](device-inventory.md).
    - **Dispositivos do Azure AD** – uma lista de dispositivos registrados ou associados com o Azure AD (Active Directory). Saiba mais sobre o [gerenciamento de dispositivos do Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
    - **Ações de dispositivo** – um histórico das ações remotas executadas em dispositivos, incluindo a ação, o status dela, quem iniciou a ação e o horário.

    ![Monitorar ações do dispositivo](./media/monitor-device-actions.png)

    - **TeamViewer** – o serviço do TeamViewer permite que usuários de dispositivos Android gerenciados pelo Intune obtenham assistência remota de seu administrador de TI. Saiba mais sobre o [TeamViewer](device-profile-android-teamviewer.md).

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

- Escolha **Ações do Dispositivo** para ver o status das ações executadas nos dispositivos gerenciados.
