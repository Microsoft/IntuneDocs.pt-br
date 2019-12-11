---
title: Dados enviados pelo Intune à Apple
titleSuffix: Microsoft Intune
description: Lista de dados que o Intune envia para a Apple.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b204a956-18ec-11e8-accf-0ed5f89f718b
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a2f1be7a2457cca7da62883370c9e273168c6a29
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502435"
---
# <a name="data-intune-sends-to-apple"></a>Dados enviados pelo Intune à Apple

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Quando qualquer um dos seguintes serviços da Apple está habilitado em um dispositivo, o Microsoft Intune estabelece uma conexão com a Apple e compartilha informações do usuário e do dispositivo com a Apple: 

- [DEP (Programa de registro de dispositivos) da Apple](../enrollment/device-enrollment-program-enroll-ios.md)
- [APNS (Apple MDM Push Certificate)](../enrollment/apple-mdm-push-certificate-get.md)
- [ASM (Apple School Manager)](https://docs.microsoft.com/schooldatasync/apple-school-manager-integration-with-intune-for-education-and-school-data-sync)
- [VPP (Apple Volume Purchase Program)](../apps/vpp-apps-ios.md)

Antes que o Microsoft Intune estabeleça uma conexão, você deve criar uma conta da Apple para cada um dos serviços de Apple.

A tabela a seguir lista os dados que o Microsoft Intune envia de um dispositivo para os serviços da Apple habilitados. 

| Serviço | Dados enviados à Apple | Usada para |
|---|---| ---|
| [APNS](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token, PushMagic | Se o servidor aceita o dispositivo, o dispositivo fornece o token de dispositivo de notificação por push para o servidor. O servidor deve usar esse token para enviar mensagens por push para o dispositivo. Essa mensagem de check-in também contém uma cadeia de caracteres PushMagic. O servidor deve se lembrar dessa cadeia de caracteres e incluí-la em qualquer mensagem enviada por push para o dispositivo. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do servidor | Token de dispositivo de notificação por push usado para autenticar no serviço da Apple. |
| ASM/DEP | nome_do_servidor | Um nome de identificação do servidor MDM. |
| ASM/DEP | server_uuid | Um identificador de servidor gerado pelo sistema. |
| ASM/DEP | admin_id | ID da Apple da pessoa que gerou os tokens atuais que estão em uso. |
| ASM/DEP | org_name | O nome da organização. |
| ASM/DEP | org_email | Endereço de email da organização. |
| ASM/DEP | org_phone | O telefone da organização. |
| ASM/DEP | org_address | O endereço da organização. |
| ASM/DEP | org_id | ID do cliente da DEP. Essa chave está disponível somente na versão de protocolo 3 e posterior. |
| ASM/DEP | serial_number | Número de série do dispositivo (cadeia de caracteres). |
| ASM/DEP | modelo | O nome do modelo (cadeia de caracteres). |
| ASM/DEP | descrição | Uma descrição do dispositivo (cadeia de caracteres). |
| ASM/DEP | asset_tag | A marca de ativo do dispositivo (cadeia de caracteres). |
| ASM/DEP | profile_status | O status da instalação do perfil. Os valores possíveis: **vazio**, **atribuído**, **enviado por push** ou **removido**. |
| ASM/DEP | profile_uuid | A ID exclusiva do perfil atribuído. |
| ASM/DEP | device_assigned_by | O email da pessoa que atribuiu o dispositivo. |
| ASM/DEP | os | O sistema operacional do dispositivo: iOS, OSX ou tvOS. Essa chave é válido em X-Server-Protocol-Version 2 e posterior. |
| ASM/DEP | device_family | A família de produtos do dispositivo Apple: iPad, iPhone, iPod, Mac ou AppleTV. Essa chave é válido em X-Server-Protocol-Version 2 e posterior. |
| ASM/DEP | profile_name | Cadeia de caracteres. Um nome legível para o perfil. |
| ASM/DEP | support_phone_number | Opcional. Cadeia de caracteres. Um número de telefone de suporte para a organização. |
| ASM/DEP | support_email_address | Opcional. Cadeia de caracteres. Um endereço de email de suporte para a organização. Essa chave é válido em X-Server-Protocol-Version 2 e posterior. |
| ASM/DEP | department | Opcional. Cadeia de caracteres. O nome do departamento ou local definido pelo usuário. |
| ASM/DEP | dispositivos | Matriz de cadeias de caracteres que contém os números de série do dispositivo. (Pode estar vazia). |
| VPP | GUID de UserId do Intune | GUID gerado pelo Intune. |
| VPP | UPN de AppleId gerenciada | ID da Apple que foi especificado pelo administrador ao configurar a conexão de token de VPP com a Apple. |
| VPP | Número de Série | Número de série do dispositivo gerenciado. |

Para parar de usar serviços da Apple com o Microsoft Intune e excluir os dados, você deve desabilitar o token da Apple do Microsoft Intune e também excluir a sua conta da Apple. Consulte a conta da Apple para saber como executar o gerenciamento de contas.


