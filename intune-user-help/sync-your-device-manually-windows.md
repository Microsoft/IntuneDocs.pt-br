---
title: Sincronizar o dispositivo Windows manualmente | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: aa556b2939986759aa92e63750fd161c05afbc38
ms.sourcegitcommit: 6a9830de768dd97a0e95b366fd5d2f93980cee05
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
---
# <a name="sync-your-windows-device-manually"></a>Sincronizar o dispositivo Windows manualmente

Quando a velocidade de instalação do aplicativo é inferior ao ideal, inicie uma sincronização manual do dispositivo. Sincronizações manuais forçam o dispositivo a se conectar com o Intune para receber as atualizações e comunicações mais recentes. A velocidade da instalação pode aumentar após a conclusão da sincronização do dispositivo.

O Intune dá suporte à sincronização manual no aplicativo Portal da Empresa e no aplicativo Configurações do dispositivo. 

A funcionalidade do aplicativo Portal da Empresa tem suporte em dispositivos com Windows 10 que executam a Atualização do Criador (1703) ou posterior. 
* [Sincronizar no aplicativo Portal da Empresa](#Sync-from-Company-Portal-app-for-Windows)  

Todos os dispositivos com Windows podem ser sincronizados a partir do aplicativo Configurações do dispositivo, incluindo:

* [Windows 10 desktop](#windows-10-desktop)  
* [Microsoft HoloLens](#microsoft-hololens)   
* [Windows 10 Mobile](#windows-10-mobile)  
* [Windows Phone 8.1](#windows-phone-81)    

## <a name="sync-from-company-portal-app-for-windows"></a>Sincronizar do aplicativo Portal da Empresa para Windows
Conclua estas etapas para sincronizar manualmente qualquer dispositivo com Windows 10 que esteja executando a Atualização do Criador (versão 1703) ou posterior.

1.  Abra o aplicativo Portal da Empresa no dispositivo.

2.  Selecione **Configurações** > **Sincronização**.

    ![Captura de tela da home page do aplicativo Portal da Empresa, Configurações realçada](./media/RS1_homePage_settings_04.png)  
    
    ![Captura de tela da página Configurações do aplicativo Portal da Empresa, botão Sincronização realçado](./media/RS1_settingspage_sync05.png)    

## <a name="sync-from-settings-app"></a>Sincronização no aplicativo Configurações 
Conclua estas etapas para sincronizar manualmente seu Microsoft HoloLens, sua área de trabalho do Windows 10, Windows 10 Mobile ou dispositivos com Windows Phone 8.1 pelo aplicativo Configurações.

### <a name="windows-10-desktop"></a>Windows 10 Desktop
1. Em seu dispositivo, selecione **Iniciar** > **Configurações**.

2. Selecione **Contas**.

    ![Escolha Contas na página Configurações](./media/win10pc-sync-2-settings-accounts.png)  

3. Há várias versões do Windows 10 para desktops. Compare sua tela com as capturas de tela a seguir para determinar qual conjunto de etapas seguir. 

    * Se a sua tela mostrar **Acesso corporativo ou de estudante**, confira as etapas em [Acesso corporativo ou de estudante](#access-work-or-school).

    ![Opção de Acesso corporativo ou de estudante no aplicativo Configurações](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

    * Se sua tela mostrar **Acesso corporativo**, confira as etapas em [Acesso corporativo](#work-access).  

    ![Escolha acesso corporativo como tipo de conta](./media/win10pc-sync-3-work-access.png)

#### <a name="access-work-or-school-steps"></a>Etapas do Acesso corporativo ou de estudante

1. Clique em **Acesso corporativo ou de estudante**.

    ![Captura de tela mostrando opção de Acesso corporativo ou de estudante](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

2. Selecione a conta que tem um ícone de maleta ao lado. Se você não vir essa conta, talvez sua empresa tenha definido suas configurações de forma diferente. Em vez disso, clique na conta que tem um logotipo da Microsoft ao lado.

     ![Escolha o nome da sua conta ao lado da pasta ou do logotipo da Microsoft](./media/win10pc-rs1-sync-info-button.png)

3. Clique em **Informações**. 

4. Clique em **Sincronizar**. 

#### <a name="work-access-steps"></a>Etapas do acesso corporativo

1.  Clique em **Acesso corporativo**.

    ![Escolha acesso corporativo como tipo de conta](./media/win10pc-sync-3-work-access.png)

2. Em **Registrar-se no gerenciamento de dispositivo**, selecione no nome da sua empresa.

    ![Escolha o nome da empresa para o gerenciamento de dispositivos](./media/win10pc-sync-4-tap-com-name.png)

3. Clique em **Sincronizar**. O botão permanece desativado até que a sincronização seja concluída.

    ![Escolha o botão Sincronizar](./media/win10pc-sync-5-tap-sync.png)  


### <a name="windows-10-mobile"></a>Windows 10 Mobile

   1. Em seu dispositivo, acesse **Todos os aplicativos** > **Configurações** > **Contas**.

       ![Escolha Contas na tela Configurações](./media/win10m-sync-1-settings-accounts.png)

   2. Selecione **Acesso corporativo**.

       ![Escolha acesso corporativo como tipo de conta](./media/win10m-sync-2-work-access.png)

   3. Em **Inscrever-se no gerenciamento de dispositivo**, selecione o nome da sua empresa.

       ![Escolha o nome da empresa para o gerenciamento de dispositivos](./media/win10m-sync-3-tap-comp-name.png)

   4. Selecione o ícone **Sincronizar**. O botão permanece desativado até que a sincronização seja concluída.

       ![Escolha o ícone Sincronizar](./media/win10m-sync-4-tap-sync.png)  
### <a name="microsoft-hololens"></a>Microsoft HoloLens  
Essas instruções se aplicam a dispositivos HoloLens que estão executando a Atualização de Aniversário do Windows 10 (também conhecida como RS1). 
1.  Abra o aplicativo Configurações em seu dispositivo.  

2.  Selecione **Contas** > **Acesso Corporativo**.  
    ![Captura de tela do aplicativo Configurações do HoloLens, link de contas realçado](./media/RS1_holoLens_SettingsRS1_Accounts_06.png)  

3.  Selecione a conta conectada > **Sincronizar**. ![Captura de tela do aplicativo Configurações do HoloLens, botão de sincronização realçado](./media/RS1_holoLens_SyncRS1_Sync_08.png)  

### <a name="windows-phone-81"></a>Windows Phone 8.1

1. Vá para **Todos os aplicativos** > **Configurações** > **Local de trabalho**.

    ![Lista de configurações](./media/wp81-1-sync-settings-workplace.png)

2. Selecione o nome da sua empresa.

    ![Escolha o nome da empresa para a conta de local de trabalho](./media/wp81-2-sync-tap-compname.png)

3. Selecione o ícone **Sincronizar**.

    ![Escolha o ícone Sincronizar](./media/wp81-3-sync-tap-sync-button.png)

Ainda precisa de ajuda? Contate o suporte da sua empresa. Para obter as informações de contato, consulte o [site do Portal da Empresa](https://portal.manage.microsoft.com#HelpDeskDialog).
