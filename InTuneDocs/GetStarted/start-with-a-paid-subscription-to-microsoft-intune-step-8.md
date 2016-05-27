---
# required metadata

title: Registrar dispositivos móveis e instalar um aplicativo | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrar dispositivos móveis e instalar um aplicativo
Para configurar o gerenciamento de dispositivo móvel com o Intune, você deve primeiro definir a autoridade de gerenciamento de dispositivo móvel, habilitar o gerenciamento de plataformas de dispositivo e registrar seus dispositivos com o aplicativo de portal da empresa. Em seguida, você pode implantar o aplicativo Microsoft Skype que publicou na etapa 6.

## Habilitar o gerenciamento de dispositivos e registrá-los

1.  **Torne o Intune sua autoridade de gerenciamento de dispositivos móveis**
    No [Console de administração do Intune](https://manage.microsoft.com/), clique em **Administração** > **Gerenciamento de Dispositivos Móveis** e clique em **Definir Autoridade de MDM** em **Tarefas**.  Selecione **Sim** na caixa de diálogo de Autoridade de MDM.
    ![Console de administração. Defina mdm como Intune](./media/mdmAuthority.png)

2.  **Habilitar o MDM para sua plataforma de dispositivo**
    Habilite o gerenciamento de dispositivos móveis para a plataforma de dispositivo que você deseja gerenciar. Dependendo de sua plataforma, são necessários requisitos diferentes:

    -   **iOS e Mac OS X**: consulte [Set up iOS and Mac management with Microsoft Intune (Configurar gerenciamento de iOS e Mac com o Microsoft Intune)](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Windows Phone**: consulte [Set up Windows Phone management with Microsoft Intune (Configurar o gerenciamento do Windows Phone com o Microsoft Intune)](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

    -   **Android**: dispositivos móveis Android permitem que usuários realizem seu registro usando o aplicativo do portal da empresa disponível no [Google Play](https://play.google.com/store/apps/details?id=com.skype.raider). Nenhuma configuração adicional no Intune é necessária.

3.  **Registrar dispositivos**:

    -   **Android** - instale o aplicativo **Portal da Empresa do Intune** da Microsoft Corporation, disponível no [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) e entre com as credenciais de usuário do Intune adicionadas acima.

    -   **iOS e Mac OS X** - instale o aplicativo **Portal da empresa do Microsoft Intune** da Microsoft Corporation disponível na Windows Store e entre com as credenciais de usuário do Intune adicionadas acima. Exiba os **Dispositivos registrados** para adicionar seu dispositivo.

    -   **Windows Phone 8.1** - os usuários instalam o aplicativo **Portal da Empresa** da Microsoft Corporation, disponível na loja do Windows Phone, e entram com as credenciais de usuário do Intune adicionadas acima.  Exiba os **Dispositivos registrados** para adicionar seu dispositivo.

    -   **Windows Phone 8.0** - os usuários selecionam **configurações do sistema** &gt; **aplicativos da empresa** e entram com as credenciais de usuário do Intune adicionadas acima. O aplicativo portal da empresa é implantado em seu telefone.

    Se for solicitado um **Endereço do servidor**, digite “manage.microsoft.com”.

## Instalar um aplicativo em um dispositivo registrado
Na [etapa 6](start-with-a-paid-subscription-to-microsoft-intune-step-6.md) deste guia de início rápido, você publicou o aplicativo do Skype no seu grupo de usuários personalizado do Intune. Agora, você instalará esse aplicativo em um dispositivo registrado recentemente.

Abra o portal da empresa no dispositivo móvel registrado, escolha **Aplicativos** e, então, instale o **Microsoft Skype**.

Para saber mais sobre o gerenciamento de dispositivo móvel usando [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], consulte [Preparar-se para registrar dispositivos no Microsoft Intune](/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune).


### Próximas etapas
Parabéns! Você acabou de concluir a última etapa do *Guia de início rápido do Intune*. Agora que sua configuração inicial foi concluída, você pode considerar habilitar funcionalidades adicionais do MDM.

>[!div class="step-by-step"]

>[&larr; **Registrar dispositivos**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Tarefas de pós-configuração** &rarr;](.\post-configuration-tasks.md)  


<!--HONumber=May16_HO1-->


