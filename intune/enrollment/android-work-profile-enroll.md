---
title: Registrar dispositivos de perfil de trabalho Android Enterprise no Intune
titleSuffix: Microsoft Intune
description: Saiba como registrar dispositivos de perfil de trabalho Android Enterprise no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4339f98ed133c3426faee8bd4b18024fd2648606
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72503360"
---
# <a name="set-up-enrollment-of-android-enterprise-work-profile-devices"></a>Configurar o registro de dispositivos de perfil de trabalho Android Enterprise

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Intune ajuda você a implantar aplicativos e configurações em dispositivos de perfil corporativo do Android Enterprise, de modo a garantir que suas informações pessoais e de trabalho fiquem separadas. Para obter detalhes específicos sobre o Android Enterprise, confira [Requisitos do Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Para configurar o gerenciamento do perfil de trabalho Android Enterprise, siga estas etapas:

1. [Conecte sua conta de locatário do Intune à sua conta do Android Enterprise](connect-intune-android-enterprise.md).
2. Especifique as configurações de registro de perfil de trabalho Android Enterprise. Há suporte para os perfis de trabalho Android Enterprise [somente em determinados dispositivos Android](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Todos os dispositivos compatíveis com perfis corporativos do Android Enterprise também permitem o gerenciamento de administrador do dispositivo Android. O Intune permite que você especifique como os dispositivos que dão suporte aos perfis de trabalho Android Enterprise devem ser gerenciados nas [Restrições de Registro](enrollment-restrictions-set.md).
    - **Bloquear**:  Todos os dispositivos Android, incluindo dispositivos que aceitam perfis corporativos do Android Enterprise, serão registrados como dispositivos de administrador de Android, a menos que esse tipo de registro também esteja bloqueado. 
    - **Permitir (definido por padrão)** : todos os dispositivos que dão suporte aos perfis de trabalho Android Enterprise são registrados como dispositivos de perfil de trabalho Android Enterprise. Qualquer dispositivo Android que não aceite perfis corporativos do Android Enterprise é registrado como um dispositivo de administrador de Android, a menos que o registro de administrador do dispositivo Android esteja bloqueado. 
> [!NOTE]
> O padrão definido como **Permitir** é verdadeiro para novos locatários a partir de julho de 2019. Nenhum locatário anterior terá alterações nas Restrições de Registro, nem verá as políticas definidas nessas restrições. Para locatários anteriores que nunca tiveram alterações nas Restrições de Registro, **Bloquear** ainda será o padrão para os perfis corporativos do Android Enterprise.

3. [Informe aos usuários como registrar seus dispositivos](/intune-user-help/create-a-work-profile-and-enroll-your-device-in-intune-android).  

Se você deseja registrar dispositivos usando perfis corporativos do Android Enterprise, mas esses dispositivos já foram registrados com o administrador de dispositivos Android, primeiramente, cancele o registro desses dispositivos e registre-os novamente.
> [!NOTE]
> Como administrador, você pode fazer isso de forma remota usando a função **Desativar**. Essa função pode ser encontrada no menu Ações depois de selecionar o dispositivo na folha **Todos os Dispositivos**.

Quando você estiver registrando dispositivos de perfil de trabalho Android Enterprise usando uma conta de [Gerenciador de Registros do Dispositivo](device-enrollment-manager-enroll.md), há um limite de 10 dispositivos que podem ser registrados por conta.

Para obter mais informações, consulte [Dados que o Intune envia ao Google](../protect/data-intune-sends-to-google.md).

## <a name="next-steps-for-android-enterprise-work-profiles"></a>Próximas etapas para perfis de trabalho Android Enterprise
- [Implantar aplicativos do perfil de trabalho Android Enterprise](../apps/apps-add-android-for-work.md)
- [Adicionar políticas de configuração de perfis de trabalho Android Enterprise](../configuration/device-profiles.md)

## <a name="see-also"></a>Consulte também

[Configurar e solucionar problemas de dispositivos Android Enterprise no Microsoft Intune](https://support.microsoft.com/help/4476974)
