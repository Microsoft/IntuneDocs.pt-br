---
title: Registrar dispositivos | Microsoft Intune
description: "O MDM (Gerenciamento de Dispositivo Móvel) usa o registro para trazer dispositivos para o gerenciamento e permitir acesso a recursos."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 92e40930c0ccbeb3d98bef43b115fd92f24beaef
ms.openlocfilehash: 136f91e26a367ab107a80673930e735c85008ac7


---

# Registrar dispositivos para gerenciamento no Intune
Você pode registrar dispositivos, incluindo computadores Windows, para habilitar o MDM (gerenciamento de dispositivo móvel) com o Microsoft Intune. Este tópico descreve diferentes maneiras de registrar dispositivos móveis no gerenciamento do Intune. A maneira como você registra seus dispositivos depende do tipo de dispositivo, da propriedade e do nível de gerenciamento necessário. O registro de BYOD (Traga seu próprio dispositivo) permite que os usuários registrem seus telefones, tablets ou computadores pessoais. O registro de COD (Dispositivo de propriedade corporativa) permite cenários de gerenciamento como apagamento remoto, dispositivos compartilhados ou afinidade do usuário para um dispositivo.

Caso utilize o [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune), hospedado na nuvem ou local, você pode habilitar o gerenciamento simples do Intune sem registro. Computadores Windows também podem ser gerenciados usando o [software cliente do Intune](#manage-windows-pcs-with-intune).

## Visão geral dos métodos de registro do dispositivo

A tabela a seguir mostra os métodos de registro do Intune e seus recursos com suporte. Os recursos incluem:
- **Apagar** – redefinição de fábrica do dispositivo, removendo todos os dados. Para obter mais informações, consulte [Desativar dispositivos](retire-devices-from-microsoft-intune-management.md).
- **Afinidade** – associa dispositivos a usuários. Necessário para MAM (gerenciamento de dispositivo móvel) e acesso condicional a dados da empresa. Para obter mais informações, consulte [Afinidade do usuário](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices).
- **Bloqueio** – impede que os usuários removam o dispositivo do gerenciamento. Dispositivos iOS exigem o modo Supervisionado para o Bloqueio. Para obter mais informações, consulte [Bloqueio remoto](retire-devices-from-microsoft-intune-management.md#block-access-a-device).

**Métodos de registro do iOS**

| **Método** |  **Apagamento** |  **Afinidade**    |   **Bloqueio** | **Detalhes** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Não|    Sim |   Não | [Mais informações](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   Não |Não |Não  | [Mais informações](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   Sim |   Opcional |  Opcional|[Mais informações](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| Sim |   Opcional |  Não| [Mais informações](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**| Não |    Não  | Não|[Mais informações](ios-direct-enrollment-in-microsoft-intune.md)|

**Métodos de registro do Windows**

| **Método** |  **Apagamento** |  **Afinidade**    |   **Bloqueio** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Sim|   Sim |   Não | [Mais informações](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   Não |Não |Não  |[Mais informações](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Métodos de registro do Android**

| **Método** |  **Apagamento** |  **Afinidade**    |   **Bloqueio** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Não|    Sim |   Não | [Mais informações](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   Não |Não |Não  |[Mais informações](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

Para ver uma série de perguntas que o ajudarão a encontrar o método certo, consulte [Escolher como registrar dispositivos](/intune/get-started/choose-how-to-enroll-devices1).

## BYOD
Usuários de “Traga seu próprio dispositivo” instalam o aplicativo de Portal da Empresa e registram o dispositivo. Isso permite que os usuários se conectem à rede da empresa e ingressem no domínio ou no Azure Active Directory. Para a maioria das plataformas, você precisa habilitar o registro de BYOD para muitos cenários de COD. Para obter mais informações, consulte [Pré-requisitos para o registro de dispositivos](prerequisites-for-enrollment.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

## Dispositivos de propriedade corporativa
CODs (dispositivos de propriedade corporativa) podem ser gerenciados com o console do Intune. Dispositivos iOS podem ser registrados diretamente por meio das ferramentas fornecidas pela Apple. Todos os tipos de dispositivo podem ser registrados por um administrador ou gerente usando o gerenciador de registro do dispositivo. Dispositivos com um número IMEI também podem ser identificados e marcados como propriedade da empresa para habilitar cenários de COD.

Para obter mais informações, consulte [Registrar dispositivos corporativos](manage-corporate-owned-devices.md).

### DEM
O Gerenciador de registro do dispositivo é um conta especial do Intune usada para registrar e gerenciar vários dispositivos corporativos. Os gerentes podem instalar o Portal da Empresa e registrar vários dispositivos sem usuário. Saiba mais sobre o [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

### DEP
O DEP (Programa de registro de dispositivos) da Apple permite criar e implantar políticas "por ondas de rádio" em dispositivos iOS adquiridos e gerenciados com o DEP. O dispositivo é registrado quando os usuários liga o dispositivo pela primeira vez e executa o Assistente de Configuração do iOS. Este método dá suporte ao modo **Supervisionado do iOS** que, por sua vez, permite:
  - Registro bloqueado
  - Acesso condicional
  - Detecção de jailbreak
  - Gerenciamento de aplicativos móveis

Saiba mais sobre o [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

### USB-SA
Dispositivos conectados por USB e corporativos são preparados com a política do Intune. Para o registro do Assistente de Configuração, o administrador cria uma política do Intune e a exporta para o Apple Configurator. O administrador deve registrar manualmente cada dispositivo. Os usuários recebem seus dispositivos e executam o Assistente de Instalação, registrando seu dispositivo. Este método dá suporte ao modo **Supervisionado do iOS** que, por sua vez, permite:
  - Acesso condicional
  - Detecção de jailbreak
  - Gerenciamento de aplicativos móveis

Saiba mais sobre [Assistente para configuração de registro com Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

### USB-Direct
Para o registro direto, o administrador cria uma política do Intune e a exporta para o Apple Configurator. Dispositivos conectados por USB e corporativos são registrados diretamente sem a necessidade de uma redefinição de fábrica. O administrador deve registrar manualmente cada dispositivo. Os dispositivos são gerenciados como dispositivos sem usuário. Eles não são bloqueados ou supervisionados e não dão suporte a acesso condicional, detecção de jailbreak ou gerenciamento de aplicativo móvel. Saiba mais sobre o [registro direto com o Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

## Gerenciamento de dispositivos móveis usando o Exchange ActiveSync e o Intune
Dispositivos móveis que não estão registrados, mas que conectam ao EAS (Exchange ActiveSync) podem ser gerenciados pelo Intune usando a política de MDM do EAS. O Intune usa um Exchange Connector para se comunicar com o EAS, hospedado na nuvem ou local.

Para obter mais informações, consulte [Gerenciamento de dispositivo móvel usando o Exchange ActiveSync e o Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md).


## Gerenciamento de computador Windows com o Intune  
Você também pode usar o Microsoft Intune para gerenciar computadores Windows com o software cliente do Intune. Computadores gerenciados com o cliente Intune podem:

 - Informar inventários de hardware e software
 - Instalar aplicativos da área de trabalho (por exemplo arquivos .exe e .msi)
 - Configurações de firewall

Computadores que são gerenciados com o software cliente do Intune não podem ser totalmente apagados, embora o apagamento seletivo esteja disponível. Computadores gerenciados com o cliente de software do Intune não podem tirar proveito de muitos recursos de gerenciamento do Intune como acesso condicional, configurações de VPN e Wi-Fi ou implantação de certificados e configurações de email.

Para obter mais informações, consulte [Gerenciar computadores Windows com o Intune](manage-windows-pcs-with-microsoft-intune.md).

## Plataformas de dispositivos com suporte

O Intune pode gerenciar as seguintes plataformas de dispositivo:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Próximas etapas
- [Pré-requisitos para registro de dispositivo](prerequisites-for-enrollment.md)
- [Gerenciar dispositivos corporativos](manage-corporate-owned-devices.md)
- [Dispositivos móveis e computadores com suporte](../get-started/supported-mobile-devices-and-computers.md)



<!--HONumber=Oct16_HO3-->


