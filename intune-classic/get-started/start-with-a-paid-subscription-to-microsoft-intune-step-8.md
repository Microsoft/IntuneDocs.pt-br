---
title: Habilitar registro de dispositivo
description: Definir a autoridade do MDM e habilitar o registro para dispositivos iOS, Windows, Android e Mac.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 64c6eb58246ac3ad232c1b8ee89d12a83e7e1784
ms.contentlocale: pt-br
ms.lasthandoff: 06/08/2017


---

# <a name="enable-enrollment-for-mobile-devices"></a>Habilitar registro para dispositivos móveis

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico descreve como um administrador do Intune pode habilitar o registro de dispositivo móvel. Para obter ajuda sobre como usar o Intune em seu telefone, consulte [usando dispositivos gerenciados para realizar seu trabalho](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions).

Para configurar o gerenciamento de dispositivo móvel com o Intune, você deve primeiro definir a *autoridade de gerenciamento de dispositivo móvel*, que identifica o serviço que pode gerenciar dispositivos associados à sua conta. Estas diretrizes presumem que você usará o serviço do Intune em vez do System Center Configuration Manager. Depois que a autoridade MDM estiver configurada, você poderá habilitar o gerenciamento de plataformas de dispositivo e registrar seus dispositivos com o aplicativo de Portal da Empresa.

## <a name="enable-device-enrollment"></a>Habilitar registro de dispositivo

1. **Torne o Intune sua autoridade de gerenciamento de dispositivo móvel**
    No [console de administração do Intune](https://manage.microsoft.com/), clique em **Admin** > **Gerenciamento de Dispositivos Móveis** e clique em **Definir Autoridade** de MDM em **Tarefas**.  

2. Selecione **Sim** na caixa de diálogo de Autoridade de MDM.

    ![Console de administração. Defina mdm como Intune](../media/intune-mdm-authority.png)

## <a name="choose-how-to-enroll-devices"></a>Escolha como registrar dispositivos

O Intune pode gerenciar dispositivos de várias maneiras, dependendo dos requisitos da sua empresa. "Traga seu próprio dispositivo" (BYOD), dispositivos de propriedade corporativa, "escolha seu próprio dispositivo" (CYOD) e os dispositivos de modo de quiosque são apenas alguns cenários de registro disponíveis.

Siga estas etapas para [Escolher como registrar dispositivos](choose-how-to-enroll-devices1.md).

## <a name="enable-mdm-for-your-device-platform"></a>Habilitar o MDM para sua plataforma de dispositivo
O registro deve ser habilitado para iOS, Mac e Android para dispositivos de Trabalho estabelecendo uma relação entre o provedor de plataforma e o seu locatário do Intune. Dispositivos Android e Windows não exigem etapas adicionais, mas em dispositivos Windows, você pode simplificar o registro do dispositivo para seus usuários ao criar uma entrada de Registro DNS especial.

Habilite o registro de dispositivo para a plataforma de dispositivo que deseja gerenciar. Dependendo de sua plataforma, são necessários requisitos diferentes:

- [iOS e macOS](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Windows 10 e Windows Phone](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
- [PC com Windows](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) (cliente de software do Intune)
- [Android for Work](/intune-classic/deploy-use/set-up-android-for-work)

Quando o registro estiver habilitado, os usuários poderão baixar o aplicativo de Portal da Empresa em seu dispositivo e concluir o processo de registro do dispositivo.

### <a name="enable-company-owned-device-enrollment"></a>Habilitar o registro de dispositivo da empresa
Você também pode habilitar uma variedade de situações de [registro de dispositivo da empresa](/intune-classic/deploy-use/manage-corporate-owned-devices), incluindo:
- [Programa de Registro do Dispositivo da Apple](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Registro do Assistente de Configuração do Apple Configurator](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Registro direto do Apple Configurator](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Gerenciador de Registro de Dispositivos](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>Próximas etapas
Parabéns! Você acabou de concluir a última etapa do *Guia de início rápido do Intune*. Agora que sua configuração inicial foi concluída, você pode considerar habilitar funcionalidades adicionais do MDM.

>[!div class="step-by-step"]
>[&larr; **Registrar dispositivos**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Tarefas de pós-configuração** &rarr;](.\post-configuration-tasks.md)  

