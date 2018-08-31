---
title: Registrar dispositivos de perfil de trabalho Android no Intune
titlesuffix: Microsoft Intune
description: Saiba como registrar dispositivos de perfil de trabalho Android no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fc1943781dcf95209b575cdb6e36d5065275626f
ms.sourcegitcommit: 40b1d82df99f09a75a17065cdd0e84d8038f460a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "40255077"
---
# <a name="set-up-enrollment-of-android-work-profile-devices"></a>Configurar o registro de dispositivos de perfil de trabalho Android

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Intune ajuda você a implantar aplicativos e configurações em dispositivos de perfil de trabalho Android para garantir que suas informações pessoais e de trabalho fiquem separadas. Para obter detalhes específicos sobre o Android Enterprise, confira [Requisitos do Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Para configurar o gerenciamento do perfil de trabalho Android, siga estas etapas:

1. [Conecte sua conta de locatário do Intune à sua conta do Android Enterprise](connect-intune-android-enterprise.md).
2. Especifique as configurações de registro de perfil de trabalho Android. Há suporte para os perfis de trabalho Android [somente em determinados dispositivos Android](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Todo dispositivo que dá suporte aos perfis de trabalho Android também dá suporte ao gerenciamento do Android convencional. O Intune permite que você especifique como os dispositivos que dão suporte para os perfis de trabalho Android devem ser gerenciados nas [Restrições de Registro](enrollment-restrictions-set.md).
    - **Bloquear (definido por padrão)**: todos os dispositivos Android, incluindo dispositivos que dão suporte a perfis de trabalho Android, serão registrados como dispositivos Android convencionais.
    - **Permitir**: todos os dispositivos que dão suporte a perfis de trabalho Android são registrados como dispositivos de perfil de trabalho Android. Os dispositivos Android que não dão suporte aos perfis de trabalho Android são registrados como dispositivos Android convencionais.
3. [Informe aos usuários como registrar seus dispositivos](/intune-user-help/enroll-your-device-in-intune-android).


Se você deseja registrar perfis de trabalho Android em dispositivos que já foram registrados como dispositivos Android regulares, primeiro você deve cancelar o registro desses dispositivos e registrá-los novamente.

Quando você estiver registrando dispositivos de perfil de trabalho Android usando uma conta de [Gerente de Registros de Dispositivo](device-enrollment-manager-enroll.md), há um limite de 10 dispositivos que podem ser registrados por conta.

Para obter mais informações, consulte [Dados que o Intune envia ao Google](data-intune-sends-to-google.md).

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Aprovar o aplicativo Portal da Empresa na Google Play Store gerenciada

Para garantir que os usuários sempre tenham acesso à versão mais atualizada do aplicativo Portal da Empresa, aprove o aplicativo Portal da Empresa para Android na Google Play Store gerenciada. Aprovando-o, você assegura que cada usuário obtenha as atualizações automáticas. Se você não aprová-lo, o Portal da Empresa acabará ficando desatualizado e não poderá receber a correções de bugs importantes ou novos recursos quando lançados pela Microsoft.

Siga estas etapas para aprovar o Portal da Empresa do Intune:

1.  Navegue para o aplicativo do Portal da Empresa na [Google Play Store gerenciada](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Entre na Google Play Store gerenciada com a mesma conta do Google que você usou para configurar a associação ao Android Enterprise.
3.  Clique em **Aprovar** e uma nova caixa de diálogo será aberta.
4.  Examine as permissões nessa caixa de diálogo e clique em **Aprovar**. É necessário aceitar essas permissões para que o aplicativo Portal da Empresa gerencie o perfil de trabalho no dispositivo.
5.  Selecione **Manter aprovada quando o aplicativo solicitar novas permissões** e clique em **Salvar.**

## <a name="next-steps-for-android-work-profiles"></a>Próximas etapas dos perfis de trabalho Android
- [Implantar aplicativos de perfil de trabalho Android](store-apps-android.md)
- [Adicionar políticas de configuração de perfil de trabalho Android](device-profiles.md)
