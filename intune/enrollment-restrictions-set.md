---
title: "Definir restrições de registro no Intune"
titleSuffix: Intune on Azure
description: Restrinja o registro pela plataforma e defina um limite de registro de dispositivo no Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2dfcba8c788f262ce816dcd23dc2921fd57f331b
ms.sourcegitcommit: d1ad84edf4f03cb4c11fe55131556b43fc3a4500
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
# <a name="set-enrollment-restrictions"></a>Definir restrições de registro

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Como um administrador do Intune, você pode determinar quais dispositivos podem ser registrados para gerenciamento com o Intune. Use o Portal do Intune para definir as seguintes restrições para o registro de dispositivo:

- Número máximo de dispositivos registrados
- Plataformas de dispositivo que podem ser registradas:
  - Android
  - iOS
  - macOS
  - Windows
- Restringir dispositivos pessoais (somente Android e iOS)

>[!NOTE]
>Restrições de registro não são um recurso de segurança. Dispositivos comprometidos podem falsificar a identidade. Tais restrições são uma barreira de melhor esforço para usuários que não são mal-intencionados.

## <a name="set-device-type-restrictions"></a>Definir restrições de tipo de dispositivo
As restrições de registro padrão se aplicam a todos os usuários que não receberam restrições de registro de prioridade mais altas.  
1. No Portal do Intune, escolha **Registro de dispositivo** e **Restrições de registro**.
![Captura de tela do espaço de trabalho de restrições de dispositivo com as restrições de tipo de dispositivo padrão e restrições de limite de dispositivo.](media/device-restrictions-set-default.png)
2. Em **Restrições de registro** > **Restrições de Tipo de Dispositivo**, selecione **Padrão**.
3. Em **Todos os Usuários**, selecione **Plataformas**. Escolha **Permitir** ou **Bloquear** para cada plataforma:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Clique em **Salvar**.
4. Em **Todos os Usuários**, selecione **Configurações de Plataforma** e selecione as seguintes configurações:
  - **Propriedade Pessoal** – Especifique se deseja **Permitir** ou **Bloquear** para dispositivos Android e iOS.
  ![Captura de tela de espaço de trabalho de restrições de dispositivo com as configurações de plataforma de dispositivo padrão mostrando as configurações de propriedade pessoal definidas.](media/device-restrictions-platform-configurations.png)
  Clique em **Salvar**.

>[!NOTE]
>Se você impedir o registro de dispositivos pessoais Android, dispositivos Android for Work ainda poderão ser registrados.

## <a name="set-device-limit-restrictions"></a>Definir restrições de limite de dispositivos
As restrições de registro padrão se aplicam a todos os usuários que não receberam restrições de registro de prioridade mais altas.  
1. No Portal do Intune, escolha **Registro de dispositivo** e **Restrições de registro**.
2. Escolha **Restrições de registro** > **Restrições de limite de dispositivo**.
3. Em **Todos os Usuários**, selecione **Limite de Dispositivo**. Especifique o número máximo de dispositivos registrados por usuário.  
![Captura de tela da folha de restrições de limite de dispositivo com as restrições de limite de dispositivo.](./media/device-restrictions-limit.png)

  Clique em **Salvar**.
