---
title: "Registrar dispositivos móveis de avaliação | Microsoft Intune"
description: "Como registrar dispositivos móveis e instalar um aplicativo quando você se inscrever para uma avaliação gratuita de 30 dias do Intune"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 08/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 581e880fa4308ec627f5b2c1242fb5b30b713743
ms.openlocfilehash: 7bd5f5d8f4931133a8ef1e697b2fec4cccd07b83


---

# Registrar dispositivos móveis de avaliação e instalar um aplicativo
Para configurar o gerenciamento de dispositivo móvel com o Intune, você deve primeiro definir a autoridade de gerenciamento de dispositivos móveis, habilitar o gerenciamento de plataformas de dispositivo e registrar seus dispositivos com o aplicativo do Portal da Empresa. Em seguida, você pode implantar o aplicativo Microsoft Skype que publicou.

## Preparar o serviço de gerenciamento de dispositivo

1.  **Torne o Intune sua autoridade de gerenciamento de dispositivos móveis**

    No [console de administração do Intune](https://manage.microsoft.com/), clique em **Admin** &gt; **Gerenciamento de Dispositivo Móvel**. Escolha **Tarefas** > **Definir autoridade MDM**, e, em seguida, escolha **Sim** na caixa de diálogo **Autoridade MDM**.

2.  **Habilitar o MDM para sua plataforma de dispositivo**

    Habilite o gerenciamento de dispositivos móveis para a plataforma de dispositivo que você deseja gerenciar. Dependendo de sua plataforma, são necessários requisitos diferentes:

    -   **iOS e Mac OS X**: consulte [Set up iOS and Mac management with Microsoft Intune](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune) (Configurar gerenciamento de iOS e Mac com o Microsoft Intune).

    -   **Android**: dispositivos móveis Android permitem que usuários realizem seu registro usando o aplicativo do Portal da Empresa disponível no Google Play. Nenhuma configuração adicional no Intune é necessária.

    -   **Windows Phone**: consulte [Set up Windows Phone management with Microsoft Intune](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune) (Configurar o gerenciamento do Windows Phone com o Microsoft Intune).

## Registrar dispositivos de teste

### iOS e Mac OS X
Instale o aplicativo do **Portal da Empresa do Microsoft Intune** da Microsoft Corporation, disponível na App Store, e entre com as credenciais de usuário do Intune adicionadas acima. Exiba os **Dispositivos registrados** para adicionar seu dispositivo.

### Android
Instale o aplicativo do **Portal da Empresa do Intune** da Microsoft Corporation, disponível no [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612), e entre com as credenciais de usuário do Intune adicionadas acima.

### Windows Phone 8.1
Os usuários instalam o aplicativo do **Portal da Empresa** da Microsoft Corporation, disponível na loja do Windows Phone, e entram com as credenciais de usuário do Intune adicionadas acima.  Exiba os **Dispositivos registrados** para adicionar seu dispositivo.

## Instalar o aplicativo implantado anteriormente
Abra o Portal da Empresa no dispositivo móvel, escolha **Aplicativos**e, em seguida, instale o **Microsoft Skype**.

Para saber mais sobre o gerenciamento de dispositivo móvel usando o Intune, consulte [Get ready to enroll devices in Microsoft Intune](/Intune/deploy-use/prerequisites-for-enrollment) (Prepare-se para registrar dispositivos no Microsoft Intune).

### Próximas etapas
Parabéns! Você concluiu a etapa 5 do passo a passo da *avaliação do Microsoft Intune*.

>[!div class="step-by-step"]

>[&larr; **Criar políticas**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)     [**Opções e extras** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)  



<!--HONumber=Oct16_HO2-->


