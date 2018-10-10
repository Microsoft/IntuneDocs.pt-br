---
title: Funcionalidades do Intune por método de registro para dispositivos Windows
titlesuffix: Microsoft Intune
description: Veja a compatibilidade das funcionalidades de cada método de registro para dispositivos Windows.
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
ms.custom: intune-azure
ms.openlocfilehash: c9e440aef7f434cbe675506fd6f22a9bd26b2c31
ms.sourcegitcommit: 528d2bc70bfd25803a2d9f0fe9372c8a5f5e7dad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2018
ms.locfileid: "47446813"
---
# <a name="capabilities-by-enrollment-method-for-windows-devices"></a>Funcionalidades por método de registro para dispositivos Windows
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Intune permite gerenciar os dispositivos e os aplicativos da sua força de trabalho e como ela acessa os dados da empresa. Os dispositivos precisam primeiro ser registrados no serviço do Intune. Há vários métodos de registrar os dispositivos da sua força de trabalho. Cada método tem diferentes melhores práticas e funcionalidades, conforme mostrado nas tabelas a seguir.

## <a name="best-practices-by-enrollment-method"></a>Melhores práticas por método de registro
| **Práticas recomendadas** | **[Microsoft Azure AD adicionado](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Microsoft Azure AD adicionado com o Autopilot](enrollment-autopilot.md)** |**[Em massa](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **GPO** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Normalmente usado em EDU|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Dispositivos podem ser usados como dispositivos compartilhados|![X](media/xmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Dispositivos pessoais precisam acessar recursos da empresa|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|
|Autoatendimento de aplicativos|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Marca de seleção](media/checkmark.png)|![Marca de seleção](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Funcionalidades por método de registro

| **Funcionalidades** | **[Microsoft Azure AD adicionado](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Microsoft Azure AD adicionado com o Autopilot](enrollment-autopilot.md)** |**[Em massa](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **GPO** |
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

[Opções de registro](enrollment-options.md)

