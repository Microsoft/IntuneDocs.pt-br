---
title: Funcionalidades do método de registro do Intune para dispositivos Windows
titleSuffix: Microsoft Intune
description: As funcionalidades de cada método de registro para dispositivos Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b68ec61496c3c15acc8facc22a6fdfe3c65f06eb
ms.sourcegitcommit: a82d25d98fdf0ba766f8f074871d4f13725e23f9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75547865"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Funcionalidades do método de registro do Intune para dispositivos Windows
[!INCLUDE[azure_portal](../includes/azure_portal.md)]

Há vários métodos de registrar os dispositivos da sua força de trabalho no Intune. Cada método tem diferentes melhores práticas e funcionalidades, conforme mostrado nas tabelas a seguir.

## <a name="best-practices-by-enrollment-method"></a>Melhores práticas por método de registro
| **Práticas recomendadas** | **[Microsoft Azure AD adicionado](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Microsoft Azure AD adicionado com o Autopilot (modo controlado pelo usuário)](enrollment-autopilot.md)** |**[Azure AD adicionado com o Autopilot (modo de autoimplantação)](enrollment-autopilot.md)** |**[Em massa](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Cogerenciamento](https://docs.microsoft.com/configmgr/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Normalmente usado em EDU|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Dispositivos podem ser usados como dispositivos compartilhados|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Dispositivos pessoais precisam acessar recursos da empresa|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Autoatendimento de aplicativos|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Funcionalidades por método de registro

| **Funcionalidades** | **[Microsoft Azure AD adicionado](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Microsoft Azure AD adicionado com o Autopilot (modo controlado pelo usuário)](enrollment-autopilot.md)** |**[Azure AD adicionado com o Autopilot (modo de autoimplantação)](enrollment-autopilot.md)** |**[Em massa](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** | **[Cogerenciamento](https://docs.microsoft.com/configmgr/core/clients/manage/co-management-overview)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Acesso condicional                                      |![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)\*\*|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|
|O usuário é associado ao dispositivo                    |![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|
|Requer o Azure AD Premium                               |![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|
|O dispositivo pode avaliar os recursos protegidos pela AC             |![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|
|Os usuários não podem ser administradores dos seus próprios dispositivos               |![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Capacidade de configurar a experiência de configuração do dispositivo        |![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|
|Capacidade de registrar dispositivos sem interação do usuário      |![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|
|Capacidade de executar scripts do PowerShell                       |![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/checkmark.png)\*| 
|Compatível com registro automático após o ingresso no domínio do AD      |![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|
|Compatível com registro automático após a adição ao Microsoft Azure AD híbrido|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|
|Compatível com registro automático após a adição ao Microsoft Azure AD       |![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![Marca de seleção](./media/enrollment-method-capab/checkmark.png)|![X](./media/enrollment-method-capab/xmark.png)|![X](./media/enrollment-method-capab/xmark.png)|

\* As cargas de trabalho de aplicativos cliente no Configuration Manager devem ser movidas para o Piloto do Intune ou para o Intune.

\** [Os dispositivos estão bloqueados para Acesso Condicional, com exceção do Windows 10 1803 e posterior.](device-enrollment-manager-enroll.md)

## <a name="next-steps"></a>Próximas etapas

[Configurar o registro para Windows](windows-enroll.md)

