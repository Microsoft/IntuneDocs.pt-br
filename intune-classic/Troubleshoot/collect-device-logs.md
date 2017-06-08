---
title: Coletar logs de dispositivo | Microsoft Docs
description: Saiba como coletar logs de seus dispositivos gerenciados.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: f75719a02e37f6285fb1d7c5de32bb7eb4b3a1ed
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="device-logs"></a>Logs de dispositivo

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Como parte dos esforços de solução de problemas, convém coletar logs de dispositivos de usuário. As instruções para coletar os logs são descritas aqui. Normalmente, você precisará de acesso ao dispositivo para obter esses logs ou solicitar do usuário que ele colete os logs e envie para você.

### <a name="android-logs"></a>Logs do Android
Logs do Android estão localizados em *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.

Ocasionalmente, os arquivos não aparecem, especialmente em dispositivos Android mais novos. Se isso acontecer, os usuários deverão abrir o aplicativo do Portal da Empresa para Android. Em seguida, eles deverão escolher **Configurações**>**Logs de cópia** e reinicializar o dispositivo.

Para obter mais informações sobre como os usuários podem enviar logs de dados, consulte os seguintes artigos:

- [Use o Log Detalhado para ajudar o administrador de TI a corrigir problemas do dispositivo](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android): descreve como ativar o Log Detalhado, que envia todos os logs de dados automaticamente. O Log Detalhado está ativado por padrão.

- [Enviar logs de dados de diagnóstico do Android para o administrador de TI por email](/intune-user-help/send-logs-to-your-it-admin-by-email-android)

- [Enviar logs de dados de diagnóstico para o administrador de TI usando um cabo USB](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>Logs do iOS

Os usuários podem enviar erros de registro, conforme descrito em [Enviar erros de registro do iOS para o administrador de TI](/intune-user-help/send-errors-to-your-it-admin-ios).

Os usuários podem enviar logs de dispositivo, conforme descrito em [Enviar logs de dispositivo iOS](/intune-user-help/send-logs-to-your-it-admin-by-email-ios).

### <a name="mac-os-x-logs"></a>Logs do Mac OS X

1. Abra o aplicativo **Console**.
2. Em **ARQUIVOS**, escolha **system.log**.
3. Na barra de menus na parte superior, escolha **Arquivo** > **Salvar uma Cópia como...**. Em seguida, salve o arquivo.

### <a name="windows-phone"></a>Windows Phone

No aplicativo do Portal da Empresa do Windows Phone, os usuários escolhem três pontos (**...**) para acessar o menu e escolhem **Enviar Logs**. Essa opção está disponível antes e depois de entrar no aplicativo do Portal da Empresa.

### <a name="windows"></a>Windows

Para o Portal da Empresa do Windows, os logs estão localizados em *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.
