---
title: Habilitar o registro do dispositivo | Microsoft Intune
description: Definir a autoridade do MDM e habilitar o registro para dispositivos iOS, Windows, Android e Mac.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 031cf995da4fa46b244b65a6b1c51b6a1aa00d9f
ms.openlocfilehash: 8c3076b26844669f9927478b5847f88f2265c6c9


---

# <a name="enroll-mobile-devices-and-install-an-app"></a>Registrar dispositivos móveis e instalar um aplicativo
Para configurar o gerenciamento de dispositivo móvel com o Intune, você deve primeiro definir a *autoridade de gerenciamento de dispositivo móvel*, que identifica o serviço que pode gerenciar dispositivos associados à sua conta. Estas diretrizes presumem que você usará o serviço do Intune em vez do System Center Configuration Manager. Depois que a autoridade MDM estiver configurada, você poderá habilitar o gerenciamento de plataformas de dispositivo e registrar seus dispositivos com o aplicativo de Portal da Empresa.

## <a name="enable-device-enrollment"></a>Habilitar registro de dispositivo

1. **Torne o Intune sua autoridade de gerenciamento de dispositivo móvel**
    No [console de administração do Intune](https://manage.microsoft.com/), clique em **Admin** > **Gerenciamento de Dispositivos Móveis** e clique em **Definir Autoridade** de MDM em **Tarefas**.  

2. Selecione **Sim** na caixa de diálogo de Autoridade de MDM.

    ![Console de administração. Defina mdm como Intune](./media/mdmAuthority.png)

## <a name="choose-how-to-enroll-devices"></a>Escolha como registrar dispositivos

O Intune pode gerenciar dispositivos de várias maneiras, dependendo dos requisitos da sua empresa. "Traga seu próprio dispositivo" (BYOD), dispositivos de propriedade corporativa, "escolha seu próprio dispositivo" (CYOD) e os dispositivos de modo de quiosque são apenas alguns cenários de registro disponíveis.

Siga estas etapas para [Escolher como registrar dispositivos](choose-how-to-enroll-devices1.md).

## <a name="enable-mdm-for-your-device-platform"></a>Habilitar o MDM para sua plataforma de dispositivo
O registro deve ser habilitado para iOS, Mac e Android para dispositivos de Trabalho estabelecendo uma relação entre o provedor de plataforma e o seu locatário do Intune. Dispositivos Android e Windows não exigem etapas adicionais, mas em dispositivos Windows, você pode simplificar o registro do dispositivo para seus usuários ao criar uma entrada de Registro DNS especial.

Habilite o registro de dispositivo para a plataforma de dispositivo que deseja gerenciar. Dependendo de sua plataforma, são necessários requisitos diferentes:

-  [iOS e macOS](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune.md)
-  [PC Window](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)
-  [Windows 10 Mobile e Windows Phone](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)

Quando o registro estiver habilitado, os usuários poderão baixar o aplicativo de Portal da Empresa em seu dispositivo e concluir o processo de registro do dispositivo.

### <a name="enable-company-owned-device-enrollment"></a>Habilitar o registro de dispositivo da empresa
Você também pode habilitar uma variedade de situações de [registro de dispositivo da empresa](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices), incluindo:
- [Programa de Registro do Dispositivo da Apple](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Registro do Assistente de Configuração do Apple Configurator](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Registro do Assistente de Configuração do Apple Configurator](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Gerenciador de Registro de Dispositivos](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>Próximas etapas
Parabéns! Você acabou de concluir a última etapa do *Guia de início rápido do Intune*. Agora que sua configuração inicial foi concluída, você pode considerar habilitar funcionalidades adicionais do MDM.

>[!div class="step-by-step"]

>[&larr; **Registrar dispositivos**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Tarefas de pós-configuração** &rarr;](.\post-configuration-tasks.md)  



<!--HONumber=Dec16_HO1-->


