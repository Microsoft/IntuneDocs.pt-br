---
title: Registrar dispositivos Android no Intune
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como registrar dispositivos Android na versão prévia do Intune Azure."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: b664620f424f9ef612d17beb810564dbdd68ff79
ms.lasthandoff: 03/22/2017


---

# <a name="enroll-android-devices"></a>Registrar dispositivos Android

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

O Intune permite que você gerencie dispositivos Android, incluindo dispositivos Samsung Knox Standard. Para habilitar o gerenciamento de dispositivos, os usuários devem registrar seus dispositivos baixando o aplicativo do Portal da Empresa do Intune, que está disponível no Google Play e, em seguida, abrindo o aplicativo e seguindo as instruções de registro. Quando os dispositivos Android estiverem sob gerenciamento, você pode [criar políticas de conformidade](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android), [gerenciar aplicativos](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-management)e muito mais.

## <a name="prerequisite"></a>Pré-requisito

Você deve definir a autoridade MDM como **Microsoft Intune** para se preparar para gerenciar dispositivos móveis. Consulte [Definir a autoridade MDM](set-mdm-authority.md) para obter instruções. Você define esse item apenas uma vez, na primeira vez que configurar o Intune para gerenciamento de dispositivo móvel, portanto você pode já ter definido isso.

## <a name="set-up-android-enrollment"></a>Configurar registro do Android

Por padrão, o Intune é configurado para permitir o registro de dispositivos Android e Samsung Knox Standard.

Para bloquear o registro de dispositivos Android ou para bloquear o registro somente de dispositivos Android de propriedade pessoal, consulte [Definir restrições de tipo de dispositivo](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions).

Para definir o número máximo de dispositivos que um usuário pode registrar, consulte [Definir restrições de limite de dispositivos](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informe aos usuários como registrar seus dispositivos para acessar os recursos da empresa

Você precisará pedir aos usuários finais que entrem no Google Play para baixar o aplicativo Portal da Empresa do Intune e, em seguida, abram o aplicativo e sigam os prompts para registrar seus dispositivos. O aplicativo orienta os usuários pelo processo de registro, explicando o que os usuários podem esperar e o que os administradores de TI podem e não podem ver em seus dispositivos.

Você também pode enviar a eles um link com as etapas do registro online: [Registrar seu dispositivo Android no Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android).

Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:

- [Recursos sobre a experiência do usuário final com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Usando seu dispositivo Android com o Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)

