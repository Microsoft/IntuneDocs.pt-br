---
title: Funcionalidades do método de registro do Intune para dispositivos Windows
titlesuffix: Microsoft Intune
description: As funcionalidades de cada método de registro para dispositivos Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa71461b136243262146502adc0f7b925b345a0b
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55839321"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Funcionalidades do método de registro do Intune para dispositivos Windows
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Há vários métodos de registrar os dispositivos da sua força de trabalho no Intune. Cada método tem diferentes melhores práticas e funcionalidades, conforme mostrado nas tabelas a seguir.

## <a name="best-practices-by-enrollment-method"></a>Melhores práticas por método de registro
| **Práticas recomendadas** | **[Microsoft Azure AD adicionado](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Microsoft Azure AD adicionado com o Autopilot](enrollment-autopilot.md)** |**[Em massa](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Normalmente usado em EDU|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Dispositivos podem ser usados como dispositivos compartilhados|![X](media/xmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Dispositivos pessoais precisam acessar recursos da empresa|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|
|Autoatendimento de aplicativos|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Funcionalidades por método de registro

| **Funcionalidades** | **[Microsoft Azure AD adicionado](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Microsoft Azure AD adicionado com o Autopilot](enrollment-autopilot.md)** |**[Em massa](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Acesso condicional                                      |![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|
|O usuário é associado ao dispositivo                    |![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|
|Requer o Azure AD Premium                               |![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|
|O dispositivo pode avaliar os recursos protegidos pela AC             |![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|
|Os usuários não podem ser administradores dos seus próprios dispositivos               |![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Capacidade de configurar a experiência de configuração do dispositivo        |![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Capacidade de registrar dispositivos sem interação do usuário      |![X](media/xmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|
|Capacidade de executar scripts do PowerShell                       |![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|Compatível com registro automático após o ingresso no domínio do AD      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|
|Compatível com registro automático após a adição ao Microsoft Azure AD híbrido|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|
|Compatível com registro automático após a adição ao Microsoft Azure AD       |![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|

## <a name="next-steps"></a>Próximas etapas

[Configurar o registro para Windows](windows-enroll.md)

