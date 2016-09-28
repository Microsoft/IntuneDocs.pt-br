---
title:
- "Solucionar problemas do gerenciamento de aplicativos móveis | Microsoft Intune"
description: 
keywords: 
author: karaman
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: 9cfb3694b2fae919fd0554a6e21b497cdcf19c72
ms.openlocfilehash: f33e8de82ee07bb4571a5bfaff63af72f9086376


---

# Solucionar problemas do gerenciamento de aplicativos móveis

Se você estiver tendo problemas com o gerenciamento de aplicativos móveis, comece por aqui. Este tópico contém alguns problemas comuns que podem ocorrer, juntamente com as soluções.


**Problema:** o MAM sem a política de Registro do console do Azure não está sendo aplicado ao aplicativo Skype for Business em dispositivos iOS e Android.

Resolução: o Skype for Business deve ser configurado para autenticação moderna.  Siga as instruções em [Habilitar o locatário para autenticação moderna](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) para configurar a autenticação moderna para o Skype.

**Problema:** o MAM sem a política de Registro do console do Azure não está sendo aplicado a nenhum (aplicativo do Office com suporte) [https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners] para nenhum usuário.
 
Solução: Confirme se o usuário está licenciado para o Intune.  

**Problema:** o usuário do administrador de TI não consegue configurar políticas de MAM no Portal do Azure

Resolução: as funções a seguir têm acesso ao Portal do Azure:

- Administrador global, que pode ser configurada no [Portal do Office](http://portal.office.com/)
- Proprietário, que pode ser configurada no [Portal do Azure](https://portal.azure.com/).
- Colaborador, que pode ser configurada no [Portal do Azure](https://portal.azure.com/).

Consulte [Preparar-se para configurar as políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) para obter ajuda para configurar essas funções. 

**Problema:** o relatório do aplicativo não mostra os usuários a que direcionamos a política de MAM recentemente.

Resolução: se uma política de MAM tiver sido direcionada a um usuário recentemente, pode levar até 24 horas para que esse usuário apareça nos relatórios como um usuário de destino. 

**Problema:** alterações/atualizações de política podem levar até 8 horas para serem aplicadas.  

Resolução: o usuário final pode fazer logoff do aplicativo e fazer logon novamente para forçar a sincronização com o serviço.  

**Problema:** a política de MAM não está sendo aplicada a dispositivos do DEP da Apple

Resolução: verifique se você está usando a afinidade de usuário com o DEP (Programa de registro de dispositivo) da Apple. A afinidade de usuário é necessária para qualquer aplicativo que exigir a autenticação do usuário no DEP.
Consulte [Registrar dispositivos iOS de propriedade corporativa usando o DEP](https://docs.microsoft.com/en-us/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) para obter mais informações sobre o registro de dispositivos iOS com o DEP.


### Consulte também
- [Validar a configuração do gerenciamento de aplicativo móvel](https://docs.microsoft.com/en-us/intune/deploy-use/validate-mobile-application-management)
- [Preparar-se para configurar as políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 





<!--HONumber=Sep16_HO2-->


