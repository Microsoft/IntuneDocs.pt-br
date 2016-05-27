---
# required metadata

title: Registrar dispositivos móveis de avaliação | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrar dispositivos móveis de avaliação e instalar um aplicativo
Para configurar o gerenciamento de dispositivo móvel com o Intune, você deve primeiro definir a autoridade de gerenciamento de dispositivos móveis, habilitar o gerenciamento de plataformas de dispositivo e registrar seus dispositivos com o aplicativo do Portal da Empresa. Em seguida, você pode implantar o aplicativo Microsoft Skype que publicou.

## Preparar o serviço de gerenciamento de dispositivo

1.  **Torne o Intune sua autoridade de gerenciamento de dispositivos móveis**

    No [console de administração do Intune](https://manage.microsoft.com/), clique em **Admin** &gt; **Gerenciamento de Dispositivo Móvel**. Escolha **Tarefas** > **Definir autoridade MDM**, e, em seguida, escolha **Sim** na caixa de diálogo **Autoridade MDM**.

2.  **Habilitar o MDM para sua plataforma de dispositivo**

    Habilite o gerenciamento de dispositivos móveis para a plataforma de dispositivo que você deseja gerenciar. Dependendo de sua plataforma, são necessários requisitos diferentes:

    -   **iOS e Mac OS X**: consulte [Set up iOS and Mac management with Microsoft Intune (Configurar gerenciamento de iOS e Mac com o Microsoft Intune)](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Android**: dispositivos móveis Android permitem que usuários realizem seu registro usando o aplicativo do Portal da Empresa disponível no Google Play. Nenhuma configuração adicional no Intune é necessária.

    -   **Windows Phone**: consulte [Set up Windows Phone management with Microsoft Intune (Configurar o gerenciamento do Windows Phone com o Microsoft Intune)](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune).

## Registrar dispositivos de teste

### iOS e Mac OS X
Instale o aplicativo do **Portal da Empresa do Microsoft Intune** da Microsoft Corporation, disponível na App Store, e entre com as credenciais de usuário do Intune adicionadas acima. Exiba os **Dispositivos registrados** para adicionar seu dispositivo.

### Android
Instale o aplicativo do **Portal da Empresa do Intune** da Microsoft Corporation, disponível no [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612), e entre com as credenciais de usuário do Intune adicionadas acima.

### Windows Phone 8.1
Os usuários instalam o aplicativo do **Portal da Empresa** da Microsoft Corporation, disponível na loja do Windows Phone, e entram com as credenciais de usuário do Intune adicionadas acima.  Exiba os **Dispositivos registrados** para adicionar seu dispositivo.

 ### Windows Phone 8.0
 Os usuários clicam em **configurações do sistema** &gt; **aplicativos da empresa** e entram com as credenciais de usuário do Intune adicionadas acima. O aplicativo Portal da Empresa é implantado em seu telefone.

Se for solicitado um **Endereço do servidor**, digite “manage.microsoft.com”.


## Instalar o aplicativo implantado anteriormente
Abra o Portal da Empresa no dispositivo móvel, escolha **Aplicativos**e, em seguida, instale o **Microsoft Skype**.

Para saber mais sobre o gerenciamento de dispositivo móvel usando o Intune, consulte [Get ready to enroll devices in Microsoft Intune (Preparar-se para registrar dispositivos no Microsoft Intune)](/Intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune).

### Próximas etapas
Parabéns! Você concluiu a etapa 5 do passo a passo da *avaliação do Microsoft Intune*.

>[!div class="step-by-step"]

>[&larr; **Criar Políticas**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)     [**Opções e extras** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)  


<!--HONumber=May16_HO1-->


