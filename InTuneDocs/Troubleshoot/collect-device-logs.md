---
title: Coletar logs de dispositivo| Microsoft Intune
description: Saiba como coletar logs de seus dispositivos gerenciados.
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 19b0b502d2c8c261947c461f27a0e8153df5b186
ms.openlocfilehash: 1e65c1fa25e273ba03218f79ebeff611138e8013


---

# <a name="device-logs"></a>Logs de dispositivo

Como parte dos esforços de solução de problemas, convém coletar logs de dispositivos de usuário. As instruções para coletar os logs são descritas aqui. Normalmente, você precisará de acesso ao dispositivo ou solicitará do usuário que ele colete os logs e envie para você.

### <a name="android-logs"></a>Logs do Android
Logs do Android estão localizados em *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. 

Ocasionalmente, os arquivos não aparecem, especialmente em dispositivos Android mais novos. Se isso acontecer, os usuários finais deverão abrir o aplicativo Portal da Empresa para o Android e, em seguida, ir para **Configurações**, escolher **Copiar Logs** e reinicializar o dispositivo. 

Para obter mais informações sobre como os usuários podem enviar logs de dados, consulte os seguintes artigos:

- [Use o Log Detalhado para ajudar o administrador de TI a corrigir problemas do dispositivo](/intune/enduser/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android) – Descreve como ativar o Log Detalhado, que envia todos os logs de dados automaticamente. O Log Detalhado está ativado por padrão.

- [Enviar logs de dados de diagnóstico do Android para o administrador de TI por email](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android) 

- [Enviar logs de dados de diagnóstico para o administrador de TI usando um cabo USB](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>Logs do iOS

Os usuários podem enviar erros de registro, conforme descrito em [Enviar erros de registro do iOS para o administrador de TI](/intune/enduser/send-errors-to-your-it-admin-ios).

### <a name="mac-os-x-logs"></a>Logs do Mac OS X

1. Abra o aplicativo **Console**.
2. Em **ARQUIVOS** Escolha **system.log**.
3. Na barra de menus na parte superior, escolha **Arquivo** > **Salvar Cópia como...** e salve o arquivo.

### <a name="windows-phone"></a>Windows Phone

No aplicativo do Portal da Empresa do Windows Phone, os usuários terão que escolher o **...** para acessar o menu e escolher, em seguida, **Enviar Logs**. Essa opção está disponível antes e depois de entrar no aplicativo do Portal da Empresa.

### <a name="windows"></a>Windows

Para o Portal da Empresa do Windows, os logs estão localizados em *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Nov16_HO2-->


