---
title: O que é o registro do dispositivo do Microsoft Intune
titleSuffix: Microsoft Intune
description: Saiba mais sobre o registro de dispositivos iOS/iPadOS, Android e Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 4/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7955c91a33edef37b86f5bd8f29dfb681d28030e
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415341"
---
# <a name="what-is-device-enrollment"></a>O que é o registro de dispositivo?
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Intune permite gerenciar os dispositivos e os aplicativos da sua força de trabalho e como ela acessa os dados da empresa. Para usar esse gerenciamento de dispositivo móvel (MDM), os dispositivos devem primeiro ser registrados no serviço do Intune. Ao registrar um dispositivo, este recebe um certificado de MDM. Esse certificado é usado para se comunicar com o serviço do Intune.

Como é possível ver nas tabelas a seguir, há vários métodos de registrar os dispositivos da sua força de trabalho. Cada método depende da propriedade do dispositivo (pessoal ou corporativo), tipo de dispositivo (iOS, Windows, Android) e requisitos de gerenciamento (redefinições, afinidade, bloqueio).

Por padrão, dispositivos para todas as plataformas têm permissão para se registrarem no Intune. No entanto, você pode [restringir os dispositivos pela plataforma](enrollment-restrictions-set.md#create-a-device-type-restriction).

## <a name="iosipados-enrollment-methods"></a>Métodos de registro do iOS/iPadOS

| **Método** | **Redefinição Necessária** | [**Afinidade do Usuário**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) | **Locked** | **Detalhes** |
|:---:|:---:|:---:|:---:|:---:|
| | Os dispositivos são apagados durante o registro. | Associa cada usuário a um usuário.| Se sim, os usuários não podem cancelar o registro dos dispositivos. | |
|**[BYOD](#bring-your-own-device)** | Não| Sim | Não | [Mais informações](apple-mdm-push-certificate-get.md)|
|**[DEM](#device-enrollment-manager)**| Não |Não |Não | [Mais informações](device-enrollment-program-enroll-ios.md)|
|**[DEP](#apple-device-enrollment-program)**| Sim | Opcional | Opcional|[Mais informações](device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Sim | Opcional | Não| [Mais informações](apple-configurator-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| Não | Não | Não|[Mais informações](apple-configurator-enroll-ios.md)|

## <a name="macos-enrollment-methods"></a>Métodos de registro do macOS
| **Método** |  **Redefinição Necessária** |  **Afinidade do usuário** | **Bloqueado** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Não| Sim | Não | [Mais informações](macos-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Não |Não |Não  | [Mais informações](device-enrollment-manager-enroll.md)|
|**[DEP](#apple-device-enrollment-program)**| Sim | Opcional | Opcional|[Mais informações](device-enrollment-program-enroll-macos.md)|

## <a name="windows-enrollment-methods"></a>Métodos de registro do Windows

| **Método** | **Redefinição Necessária** | **Afinidade do usuário** | **Bloqueado** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Não | Sim | Não | [Mais informações](windows-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Não |Não |Não |[Mais informações](device-enrollment-manager-enroll.md)|
|**Registrar automaticamente** | Não |Sim |Não | [Mais informações](windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Autopilot** |Sim |Sim |Não | [Mais informações](enrollment-autopilot.md)
|**Registrar em massa** |Não |Não |Não | [Mais informações](windows-bulk-enroll.md) |
|**Cogerenciamento** |Não |Sim |Não | [Mais informações](https://docs.microsoft.com/configmgr/core/clients/manage/co-management-overview)
|**GPO** |Não |Sim |Não | [Mais informações](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)

## <a name="android-enrollment-methods"></a>Métodos de registro do Android

| **Pessoal** | **Métodos de registro** | **Redefinição Necessária** | **Afinidade do usuário** | **Bloqueado** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Administrador de dispositivo Android**|**Usuário iniciado por meio do Portal da Empresa** | Não | Sim | Não | [Mais informações](https://docs.microsoft.com/intune-user-help/enroll-device-android-company-portal)|
|**Perfil de trabalho do Android Enterprise**|**Usuário iniciado por meio do Portal da Empresa**| Não | Sim | Não | [Mais informações](android-work-profile-enroll.md)|


| **Corporativo** | **Métodos de registro** | **Redefinição Necessária** | **Afinidade do usuário** | **Bloqueado** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**Administrador de dispositivo Android**|**[DEM](#device-enrollment-manager) iniciado por meio do Portal da Empresa**| Não | Não | Não |[Mais informações](device-enrollment-manager-enroll.md)|
|**Administrador de dispositivo Android**|**Usuário (IMEI ou número de série pré-declarado) iniciado por meio do Portal da Empresa**| Não | Sim | Não | [Mais informações](./../corporate-identifiers-add.md)|
|**Administrador de dispositivo Android com extensões de mobilidade Zebra**|**Usuário ou [DEM](#device-enrollment-manager) iniciado por meio do Portal da Empresa**| Não | Sim se iniciado pelo usuário, Não se iniciado pelo [DEM](#device-enrollment-manager) | Não | [Mais informações](../configuration/android-zebra-mx-overview.md)|
|**Android Enterprise dedicado**|**NFC, Token, código QR, Zero Touch**| Sim | Não | Configurável por meio de política | [Mais informações](android-kiosk-enroll.md)|
|**Android Enterprise totalmente gerenciado**|**NFC, Token, código QR, Zero Touch**| Sim | Sim | Configurável por meio de política | [Mais informações](android-dedicated-devices-fully-managed-enroll.md)|


## <a name="bring-your-own-device"></a>Traga seu próprio dispositivo
A abordagem BYOD (Traga seu próprio dispositivo) inclui telefones, tablets e computadores de propriedade pessoal. Os usuários instalam e executam o aplicativo do Portal da Empresa para registrar BYODs. Esse programa permite que os usuários acessem os recursos da empresa como email.

## <a name="corporate-owned-device"></a>Dispositivo corporativo
[Os COD (dispositivos corporativos)](corporate-identifiers-add.md) incluem telefones, tablets e computadores que pertencem à organização e são distribuídos para a força de trabalho. O registro de COD é compatível com cenários de gerenciamento como registro automático, dispositivos compartilhados ou requisitos de registro pré-autorizados. Uma maneira comum de registrar CODs é um administrador ou gerente usar o gerenciador de registros de dispositivo (DEM). Os dispositivos iOS/iPadOS podem ser registrados diretamente por meio das ferramentas do DEP (Programa de registro de dispositivos) fornecidas pela Apple. Os dispositivos com um número IMEI também podem ser identificados e marcados como propriedade da empresa.

### <a name="device-enrollment-manager"></a>Gerenciador de registro de dispositivos
O DEM (gerenciador de registro de dispositivos) é uma conta de usuário especial usada para registrar e gerenciar vários dispositivos corporativos. Os gerentes podem instalar o Portal da Empresa e registrar vários dispositivos sem usuário. Esses tipos de dispositivos são bons, por exemplo, para aplicativos de ponto de venda ou utilitários, mas não para usuários que precisam acessar os recursos ou o email da empresa. Saiba mais sobre o [DEM](device-enrollment-manager-enroll.md).

### <a name="apple-device-enrollment-program"></a>Programa de Registro do Dispositivo da Apple
O DEP da Apple permite criar e implantar políticas "over-the-air" em dispositivos iOS/iPadOS e macOS adquiridos e gerenciados com o DEP. O dispositivo é registrado quando os usuários liga o dispositivo pela primeira vez e executa o Assistente de Configuração. Esse método dá suporte ao modo supervisionado do iOS/iPadOS, que permite a configuração de dispositivo com uma funcionalidade específica.

Saiba mais sobre o registro DEP do iOS/iPadOS:

- [Escolha como registrar dispositivos iOS/iPadOS](ios-enroll.md)
- [Registrar dispositivos iOS/iPadOS usando o Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md)

### <a name="usb-sa"></a>USB-SA
Os administradores de TI usam o Apple Configurator, por USB, para preparar manualmente todos os dispositivos de propriedade corporativa para o registro usando o Assistente de Configuração. O administrador de TI cria um perfil de registro e exporta-o para o Apple Configurator. Quando os usuários recebem seus dispositivos, devem executar o Assistente de Instalação para registrá-los. Esse método dá suporte ao modo **Supervisionado do iOS**, que, por sua vez, habilita os seguintes recursos:
- Registro bloqueado
- Modo de quiosque e outras restrições e configurações avançadas

Saiba mais sobre o registro do Apple Configurator no iOS/iPadOS com o Assistente de Configuração:

- [Decidir como registrar dispositivos iOS/iPadOS](ios-enroll.md)
- [Registrar dispositivos iOS/iPadOS com o Configurator e o Assistente de Configuração](apple-configurator-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
Para o registro direto, o administrador deve registrar todos os dispositivos manualmente criando uma política de registro e exportando-a para o Apple Configurator. Os dispositivos de propriedade da empresa conectados por USB são registrados diretamente, sem precisar de apagamento. Os dispositivos são gerenciados como dispositivos sem usuário. Eles não são bloqueados nem supervisionados e não dão suporte ao Acesso Condicional, detecção de jailbreak ou gerenciamento de aplicativo móvel.

Para saber mais sobre o registro de iOS/iPadOS, confira:

- [Decidir como registrar dispositivos iOS/iPadOS](ios-enroll.md)
- [Registrar dispositivos iOS/iPadOS com o Configurator e registro direto](apple-configurator-enroll-ios.md)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Limpeza de dispositivo móvel após a expiração do certificado MDM

O certificado do MDM é renovado automaticamente quando os dispositivos móveis estão se comunicando com o serviço Intune. Se os dispositivos móveis são apagados ou se eles não conseguem se comunicar com o serviço do Intune por algum tempo, o certificado do MDM não é renovado. O dispositivo é removido do Portal do Azure 180 dias após a expiração do certificado do MDM.
