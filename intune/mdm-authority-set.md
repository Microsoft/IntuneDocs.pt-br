---
title: "Defina a autoridade de gerenciamento de dispositivo móvel"
titleSuffix: Intune on Azure
description: "Saiba como definir a autoridade de gerenciamento de dispositivo móvel no Intune. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 449c45e0edcc0d0a33352ba154ad68fa6c4725c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="set-the-mobile-device-management-authority"></a>Defina a autoridade de gerenciamento de dispositivo móvel

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A configuração de autoridade de gerenciamento de dispositivo móvel (MDM) determina como você gerenciar seus dispositivos. Como administrador de TI, você deverá definir uma autoridade MDM antes que os usuários possam registrar dispositivos para gerenciamento.

As configurações possíveis são:

- **Intune Autônomo** – Gerenciamento apenas na nuvem, que você pode definir usando o Portal do Azure. Inclui o conjunto completo de recursos que o Intune oferece. [Definir a autoridade MDM no console do Intune](#mdm-authority-set-to-intune).

- **Intune Híbrido** – Integração da solução de nuvem Intune com o System Center Configuration Manager. Você configura o Intune usando o console do Configuration Manager. [Definir a autoridade do MDM no Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Gerenciamento de dispositivo móvel para o Office 365** – Integração do Office 365 com a solução de nuvem do Intune. Configure o Intune do seu Centro de Administração do Office 365. Inclui um subconjunto dos recursos que estão disponíveis com o Intune Autônomo. Defina a autoridade MDM no Centro de administração do Office 365.

>[!IMPORTANT]    
No Configuration Manager versão 1610 ou posterior e no Microsoft Intune versão 1705, você altera a autoridade de MDM sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes. Para obter detalhes, consulte [O que fazer se você escolher a configuração incorreta de autoridade de MDM](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>Definir a autoridade de MDM como o Intune

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
  ![Captura de tela da carga de trabalho de solução de problema do Intune com o link Selecionar Usuário](media/set-mdm-auth.png)
2. Na folha Intune, escolha **Registro de dispositivo** e escolha **Visão Geral**.

3. na folha **Começar a gerenciar dispositivos**, escolha **Definir autoridade MDM Intune**. Uma mensagem indica que você configurou com êxito sua autoridade MDM Intune.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Limpeza de dispositivo móvel após a expiração do certificado MDM

O certificado do MDM é renovado automaticamente quando os dispositivos móveis estão se comunicando com o serviço Intune. Se os dispositivos móveis forem apagados ou se eles não conseguirem se comunicar com o serviço Intune por um certo período, o certificado do MDM não será renovado. O dispositivo é removido do Portal do Azure 180 dias após a expiração do certificado do MDM.
