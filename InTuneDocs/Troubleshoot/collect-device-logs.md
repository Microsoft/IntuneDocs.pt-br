---
title: Coletar logs de dispositivo| Microsoft Intune
description: Saiba como coletar logs de seus dispositivos gerenciados.
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3a081109cd499d3bdda75cb6c8a4dab9d9d28fab
ms.openlocfilehash: ec7d522e8dcff66d1b84fed3c4c0cc708e555e67


---

# <a name="device-logs"></a>Logs de dispositivo

Como parte dos esforços de solução de problemas, convém coletar logs de dispositivos de usuário. As instruções para coletar os logs são descritas aqui. Normalmente, você precisará de acesso ao dispositivo ou solicitará do usuário que ele colete os logs e envie para você.

### <a name="android-log-location"></a>Localização do log do Android
Logs do Android estão localizados em *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. O usuário pode também enviar você arquivos de log por email, conforme descrito em [Enviar logs de dados de diagnóstico do Android para o administrador de TI por email](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android).

### <a name="ios-logs"></a>Logs do iOS

O usuário pode enviar erros de registro conforme descrito em [Enviar erros de registro do iOS para o administrador de TI](/intune/enduser/send-errors-to-your-it-admin-ios)

### <a name="mac-os-x-devices"></a>Dispositivos Mac OS X

1. Abra o aplicativo **Console**.
2. Em **ARQUIVOS** Escolha **system.log**.
3. Na barra de menus na parte superior, escolha **Arquivo** > **Salvar Cópia como...** e salve o arquivo.

### <a name="windows-phone"></a>Windows Phone

No **Portal da Empresa do Windows Phone**, o usuário terá que escolher o **...** para acessar o menu e escolher, em seguida, **Enviar Logs**. Essa opção está disponível antes e depois de entrar no portal.

### <a name="windows"></a>Windows

Para o Portal da Empresa do Windows, os logs estão localizados em *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Oct16_HO3-->


