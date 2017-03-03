---
title: "Defina a autoridade de gerenciamento de dispositivo móvel"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como configurar a autoridade de gerenciamento de dispositivo móvel no Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 9d7a1a934188f0a40553d3c6b8b567ba8f6af034
ms.lasthandoff: 02/18/2017

---

# <a name="set-the-mobile-device-management-authority"></a>Defina a autoridade de gerenciamento de dispositivo móvel 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

A configuração de autoridade de gerenciamento de dispositivo móvel determina como você gerenciar seus dispositivos. As configurações possíveis são:

- **Intune Autônomo** – Gerenciamento apenas na nuvem, que você pode definir usando o Portal do Azure. Inclui o conjunto completo de recursos que o Intune oferece.

- **Intune Híbrido** – Integração da solução de nuvem Intune com o System Center Configuration Manager. Você configura o Intune usando o console do Configuration Manager.

- **Gerenciamento de dispositivo móvel para o Office 365** – Integração do Office 365 com a solução de nuvem do Intune. Configure o Intune do seu Centro de Administração do Office 365. Inclui um subconjunto dos recursos que estão disponíveis com o Intune Autônomo.

>[!IMPORTANT]
>Depois de definir a autoridade de gerenciamento de dispositivo móvel, será necessário contatar o [Suporte da Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) para alterá-lo, por isso faça sua escolha com cuidado.

**Para definir a autoridade de gerenciamento de dispositivo móvel:**

1. No portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.

2. Na folha Intune, escolha **Registrar dispositivos** e **Visão Geral**.

3. na folha **Começar a gerenciar dispositivos**, escolha **Definir autoridade MDM Intune**. Uma mensagem indica que você configurou com êxito sua autoridade MDM Intune.

