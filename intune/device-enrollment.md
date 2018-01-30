---
title: "O que é o registro do dispositivo do Microsoft Intune"
titlesuffix: Azure portal
description: Saiba mais sobre o registro de dispositivos iOS, Android e Windows.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/29/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a94703ecc1d7fd464f565855bb9b8dd9ee3c3bfb
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="what-is-device-enrollment"></a>O que é o registro de dispositivo?
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Intune permite gerenciar os dispositivos e os aplicativos da sua força de trabalho e como ela acessa os dados da empresa. Para usar esse gerenciamento de dispositivo móvel (MDM), os dispositivos devem primeiro ser registrados no serviço do Intune. Quando um dispositivo é registrado, ele recebe um certificado de MDM. Esse certificado é usado para se comunicar com o serviço do Intune.

Como é possível ver nas tabelas a seguir, há vários métodos de registrar os dispositivos da sua força de trabalho. Cada método depende da propriedade do dispositivo (pessoal ou corporativo), tipo de dispositivo (iOS, Windows, Android) e requisitos de gerenciamento (redefinições, afinidade, bloqueio).

## <a name="ios-enrollment-methods"></a>Métodos de registro do iOS

| **Método** |  **Redefinição Necessária** |    [**Afinidade do Usuário**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) |   **Bloqueado** | **Detalhes** |
|:---:|:---:|:---:|:---:|:---:|
| | Os dispositivos são redefinidos para as configurações de fábrica durante o registro. |  Associa cada usuário a um usuário.| Os usuários não podem cancelar o registro de dispositivos.  | |
|**[BYOD](#bring-your-own-device)** | Não|   Sim |   Não | [Mais informações](./apple-mdm-push-certificate-get.md)|
|**[DEM](#device-enrollment-manager)**| Não |Não |Não  | [Mais informações](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#apple-device-enrollment-program)**|   Sim |   Opcional |  Opcional|[Mais informações](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Sim |   Opcional |  Não| [Mais informações](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| Não |    Não  | Não|[Mais informações](./apple-configurator-direct-enroll-ios.md)|

## <a name="windows-enrollment-methods"></a>Métodos de registro do Windows

| **Método** |  **Redefinição Necessária** |    **Afinidade do usuário**   |   **Bloqueado** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Não |  Sim |   Não | [Mais informações](windows-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Não |Não |Não  |[Mais informações](device-enrollment-manager-enroll.md)|
|**Registrar automaticamente** | Não |Sim |Não | [Mais informações](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Registrar em massa** |Não |Não |Não | [Mais informações](./windows-bulk-enroll.md) |

## <a name="android-enrollment-methods"></a>Métodos de registro do Android

| **Método** |  **Redefinição Necessária** |    **Afinidade do usuário**   |   **Bloqueado** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Não|   Sim |   Não | [Mais informações](./android-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Não |Não |Não  |[Mais informações](./device-enrollment-manager-enroll.md)|
|**Android for Work**| Não | Sim | Não| [Mais informações](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## <a name="bring-your-own-device"></a>Traga seu próprio dispositivo
Traga seus próprios dispositivos (BYOD) inclui telefones pessoais, tablets e computadores. Os usuários instalam e executam o aplicativo do Portal da Empresa para registrar BYODs. Esse programa permite que os usuários acessem os recursos da empresa como email.

## <a name="corporate-owned-device"></a>Dispositivo corporativo
Os dispositivos corporativos (COD) incluem telefones, tablets, e computadores pertencentes à organização e distribuídos para a força de trabalho. O registro de COD é compatível com cenários de gerenciamento como registro automático, dispositivos compartilhados ou requisitos de registro pré-autorizados. Uma maneira comum de registrar CODs é um administrador ou gerente usar o gerenciador de registros de dispositivo (DEM). Os dispositivos iOS podem ser registrados diretamente por meio das ferramentas do Programa de Registro de Dispositivos (DEP) fornecidas pela Apple. Os dispositivos com um número IMEI também podem ser identificados e marcados como propriedade da empresa.

### <a name="device-enrollment-manager"></a>Gerenciador de registro de dispositivos
O DEM (gerenciador de registro de dispositivos) é uma conta de usuário especial usada para registrar e gerenciar vários dispositivos corporativos. Os gerentes podem instalar o Portal da Empresa e registrar vários dispositivos sem usuário. Saiba mais sobre o [DEM](./device-enrollment-manager-enroll.md).

### <a name="apple-device-enrollment-program"></a>Programa de Registro do Dispositivo da Apple
O DEP (Programa de registro de dispositivos) da Apple permite criar e implantar políticas "por ondas de rádio" em dispositivos iOS adquiridos e gerenciados com o DEP. O dispositivo é registrado quando os usuários liga o dispositivo pela primeira vez e executa o Assistente de Configuração do iOS. Esse método dá suporte ao modo supervisionado do iOS, que permite que um dispositivo seja configurado com uma funcionalidade específica.

Saiba mais sobre o registro DEP do iOS:

- [Escolha como registrar dispositivos iOS](ios-enroll.md)
- [Registrar dispositivos iOS usando o Programa de registro de dispositivos](https://docs.microsoft.com/intune/device-restrictions-ios#device-enrollment-program)

### <a name="usb-sa"></a>USB-SA
Os administradores de TI usam o Apple Configurator, por USB, para preparar manualmente todos os dispositivos de propriedade corporativa para o registro usando o Assistente de Configuração. O administrador de TI cria um perfil de registro e exporta-o para o Apple Configurator. Quando os usuários recebem seus dispositivos, eles devem executar o Assistente de Instalação para registrá-los. Esse método dá suporte ao modo **Supervisionado do iOS**, que, por sua vez, habilita os seguintes recursos:
  - Registro bloqueado
  - Modo de quiosque e outras restrições e configurações avançadas

Saiba mais sobre o registro do Apple Configurator no iOS com o Assistente de Configuração:

- [Decidir como registrar dispositivos iOS](enrollment-method-choose-ios.md)
- [Registrar dispositivos iOS com o Configurator e o Assistente de Configuração](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
Para o registro direto, o administrador deve registrar todos os dispositivos manualmente criando uma política de registro e exportando-a para o Apple Configurator. Dispositivos conectados por USB e corporativos são registrados diretamente sem a necessidade de uma redefinição de fábrica. Os dispositivos são gerenciados como dispositivos sem usuário. Eles não são bloqueados ou supervisionados e não dão suporte a acesso condicional, detecção de jailbreak ou gerenciamento de aplicativo móvel.

Para saber mais sobre o registro de iOS, consulte:

- [Decidir como registrar dispositivos iOS](enrollment-method-choose-ios.md)
- [Registrar dispositivos iOS com o Configurator e registro direto](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Gerenciamento de dispositivos móveis usando o Exchange ActiveSync e o Intune
Os dispositivos móveis que não estão registrados, mas que se conectam ao EAS (Exchange ActiveSync), podem ser gerenciados pelo Intune usando a política de MDM do EAS. O Intune usa um Exchange Connector para se comunicar com o EAS, hospedado na nuvem ou local. Mais informações em breve.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Limpeza de dispositivo móvel após a expiração do certificado MDM

O certificado do MDM é renovado automaticamente quando os dispositivos móveis estão se comunicando com o serviço Intune. Se os dispositivos móveis forem apagados ou se eles não conseguirem se comunicar com o serviço Intune por um certo período, o certificado do MDM não será renovado. O dispositivo é removido do Portal do Azure 180 dias após a expiração do certificado do MDM.
