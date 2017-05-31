---
title: "Defina a autoridade de gerenciamento de dispositivo móvel"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como configurar a autoridade de gerenciamento de dispositivo móvel no Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c36ddef7e53d6f4f15c82c97dc6d18863e6859f1
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017

---

# <a name="set-the-mobile-device-management-authority"></a>Defina a autoridade de gerenciamento de dispositivo móvel

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

A configuração de autoridade de gerenciamento de dispositivo móvel (MDM) determina como você gerenciar seus dispositivos. Como administrador de TI, você deverá definir uma autoridade MDM antes que os usuários possam registrar dispositivos para gerenciamento.

As configurações possíveis são:

- **Intune Autônomo** – Gerenciamento apenas na nuvem, que você pode definir usando o Portal do Azure. Inclui o conjunto completo de recursos que o Intune oferece. [Definir a autoridade MDM no console do Intune](#mdm-authority-set-to-intune).

- **Intune Híbrido** – Integração da solução de nuvem Intune com o System Center Configuration Manager. Você configura o Intune usando o console do Configuration Manager. [Definir a autoridade do MDM no Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Gerenciamento de dispositivo móvel para o Office 365** – Integração do Office 365 com a solução de nuvem do Intune. Configure o Intune do seu Centro de Administração do Office 365. Inclui um subconjunto dos recursos que estão disponíveis com o Intune Autônomo. Defina a autoridade MDM no Centro de administração do Office 365.

>[!IMPORTANT]
>Depois de definir a autoridade de gerenciamento de dispositivo móvel, será necessário contatar o [Suporte da Microsoft](https://docs.microsoft.com/intune-classic/troubleshoot/get-support) para alterá-lo, por isso faça sua escolha com cuidado.

## <a name="set-mdm-authority-to-intune"></a>Definir a autoridade de MDM como o Intune

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
  ![Captura de tela da carga de trabalho de solução de problema do Intune com o link Selecionar Usuário](media/set-mdm-auth.png)
2. Na folha Intune, escolha **Registro de dispositivo** e escolha **Visão Geral**.

3. na folha **Começar a gerenciar dispositivos**, escolha **Definir autoridade MDM Intune**. Uma mensagem indica que você configurou com êxito sua autoridade MDM Intune.

