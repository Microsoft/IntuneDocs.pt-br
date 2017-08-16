---
title: "Definir restrições de registro no Intune"
titleSuffix: Intune on Azure
description: Restrinja o registro pela plataforma e defina um limite de registro de dispositivo no Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 47dc35e5b50670027a85f395f674345b934d377b
ms.sourcegitcommit: 7674efb7de5ad54390801165364f5d9c58ccaf84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2017
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
- Versão do sistema operacional da plataforma (apenas iOS e Android)
  - Versão mínima
  - Versão máxima
- Restringir dispositivos pessoais (apenas Android, iOS e macOS)

>[!NOTE]
>Restrições de registro não são um recurso de segurança. Dispositivos comprometidos podem falsificar a identidade. Tais restrições são uma barreira de melhor esforço para usuários que não são mal-intencionados.

## <a name="set-device-type-restrictions"></a>Definir restrições de tipo de dispositivo
As restrições de registro padrão se aplicam a todos os usuários e registros sem usuários.
1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Escolha **Registro de dispositivos** > **Restrições de registro**.
4. Em **Restrições de registro** > **Restrições de Tipo de Dispositivo**, selecione **Padrão**.
5. Em **Todos os Usuários**, selecione **Plataformas**. Escolha **Permitir** ou **Bloquear** para cada plataforma:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Clique em **Salvar**.
6. Em **Todos os Usuários**, selecione **Configurações de Plataforma** e selecione as seguintes configurações. Para cada plataforma permitida, é possível configurar as seguintes opções:
  - **Versões** – Especifique as versões **Mín** e **Máx** do sistema operacional da plataforma para dispositivos Android e iOS. As versões do sistema operacional não se aplicam a dispositivos registrados por meio do Programa de Registro de Dispositivos, do Apple School Manager ou do aplicativo do Apple Configurator.
  - **Propriedade Pessoal** – Especifique se deseja **Permitir** ou **Bloquear** para dispositivos Android, iOS e macOS.
  ![Captura de tela de espaço de trabalho de restrições de dispositivo com as configurações de plataforma de dispositivo padrão mostrando as configurações de propriedade pessoal definidas.](media/device-restrictions-platform-configurations.png)
  Clique em **Salvar**.

>[!NOTE]
>Se você impedir o registro de dispositivos pessoais Android, os dispositivos pessoais Android for Work ainda poderão ser registrados.

## <a name="set-device-limit-restrictions"></a>Definir restrições de limite de dispositivos
As restrições de registro padrão se aplicam a todos os usuários.
1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Escolha **Registro de dispositivos** > **Restrições de registro**.
4. No Portal do Intune, escolha **Registro de dispositivo** e **Restrições de registro**.
5. Escolha **Restrições de registro** > **Restrições de limite de dispositivo**.
6. Em **Todos os Usuários**, selecione **Limite de Dispositivo**. Especifique o número máximo de dispositivos registrados por usuário.  
![Captura de tela da folha de restrições de limite de dispositivo com as restrições de limite de dispositivo.](./media/device-restrictions-limit.png)

  Clique em **Salvar**.
