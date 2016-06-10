---
# required metadata

title: Coletar logs de dispositivo| Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 06/01/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Logs de dispositivo

Como parte dos esforços de solução de problemas, convém coletar logs de dispositivos de usuário. As instruções para coletar os logs são descritas aqui. Normalmente, você precisará de acesso ao dispositivo ou solicitará do usuário que ele colete os logs e envie para você. 

### Localização do log do Android
Logs do Android estão localizados em *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. O usuário pode também enviar você arquivos de log por email, conforme descrito em [Enviar logs de dados de diagnóstico do Android para o administrador de TI por email](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android).

### Logs do iOS

O usuário pode enviar erros de registro conforme descrito em [Enviar erros de registro do iOS para o administrador de TI](/intune/enduser/send-errors-to-your-it-admin-ios)

### Dispositivos Mac OS X

1. Abra o aplicativo **Console**.
2. Em **ARQUIVOS** Escolha **system.log**.
3. Na barra de menus na parte superior, escolha **Arquivo** > **Salvar Cópia como...** e salve o arquivo.

### Windows Phone

No **Portal da Empresa do Windows Phone**, o usuário terá que escolher o **...** para acessar o menu e escolher, em seguida, **Enviar Logs**. Essa opção está disponível antes e depois de entrar no portal.

### Windows

Para o Portal da Empresa do Windows, os logs estão localizados em *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.


<!--HONumber=Jun16_HO1-->


