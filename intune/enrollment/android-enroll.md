---
title: Registrar dispositivos Android no Intune
titleSuffix: Microsoft Intune
description: Saiba como registrar dispositivos Android no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 7/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a9de31ce7a08edcb7dddc6a65a061c1883021e4
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723587"
---
# <a name="enroll-android-devices"></a>Registrar dispositivos Android

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Como administrador do Intune, você pode registrar dispositivos Android das seguintes maneiras:
- Android Enterprise (oferecendo um conjunto de opções de registro que proporciona aos usuários os recursos mais seguros e atualizados):
    - [**Perfil de trabalho do Android Enterprise**](android-work-profile-enroll.md): para dispositivos pessoais que receberam permissão para acessar dados corporativos. Administradores podem gerenciar contas de trabalho, aplicativos e dados. Dados pessoais no dispositivo são mantidos separados de dados de trabalho e os administradores não controlam as configurações ou dados pessoais. 
    - [**Android Enterprise dedicado**](android-kiosk-enroll.md): para dispositivos de propriedade corporativa com uso único, como a sinalização digital, impressão de tíquete ou gerenciamento de estoque. Os administradores bloqueiam o uso de um dispositivo a um conjunto limitado de aplicativos e links da Web. Isso também impede que os usuários adicionem outros aplicativos ou executem outras ações no dispositivo.
    - [**Android Enterprise totalmente gerenciado**](android-fully-managed-enroll.md): para dispositivos de propriedade corporativa com usuário único, usados exclusivamente para trabalho e não para uso pessoal. Os administradores podem gerenciar todo o dispositivo e impor controles de política não disponíveis para perfis de trabalho. 
- [**Administrador do dispositivo Android**](android-enroll-device-administrator.md), incluindo dispositivos Samsung Knox Standard e [dispositivos Zebra](../configuration/android-zebra-mx-overview.md). 

## <a name="prerequisites"></a>Pré-requisitos

Para se preparar para gerenciar dispositivos móveis, é necessário definir a autoridade MDM (gerenciamento de dispositivo móvel) como **Microsoft Intune**. Consulte [Definir a autoridade MDM](../fundamentals/mdm-authority-set.md) para obter instruções. Você define esse item apenas uma vez, na primeira vez que configurar o Intune para gerenciamento de dispositivo móvel.

Para dispositivos fabricados pela Zebra Technologies, talvez você precise conceder permissões adicionais ao Portal da Empresa, dependendo dos recursos do dispositivo específico. Para saber mais, confira [Extensões de mobilidade em dispositivos Zebra](../configuration/android-zebra-mx-overview.md).

Para dispositivos Samsung Knox Standard, há [mais pré-requisitos](android-samsung-knox-mobile-enroll.md).

## <a name="next-steps"></a>Próximas etapas

- [Configurar registros de perfil de trabalho Android Enterprise](android-work-profile-enroll.md)
- [Configurar registros de dispositivo dedicados Android Enterprise](android-kiosk-enroll.md)
- [Configurar registro de dispositivos totalmente gerenciados Android Enterprise](android-fully-managed-enroll.md)
- [Configurar o registro de administrador de dispositivos Android](android-enroll-device-administrator.md)

