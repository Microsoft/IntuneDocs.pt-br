---
title: Registrar dispositivos | Microsoft Docs
description: "O MDM (Gerenciamento de Dispositivo Móvel) usa o registro para trazer dispositivos para o gerenciamento e permitir acesso a recursos."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 911d2887791cf16d4290c3ac5189aa44086f4603
ms.openlocfilehash: 8f18f9ff2c32bb24b68fa987a8aad990b911a549
ms.lasthandoff: 03/11/2017


---

# <a name="enroll-devices-for-management-in-intune"></a>Registrar dispositivos para gerenciamento no Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Você pode registrar dispositivos, incluindo computadores Windows, para habilitar o MDM (gerenciamento de dispositivo móvel) com o Microsoft Intune. Este tópico descreve diferentes maneiras de registrar dispositivos móveis no gerenciamento do Intune. A maneira como você registra seus dispositivos depende do tipo de dispositivo, da propriedade e do nível de gerenciamento necessário. O registro de BYOD (Traga seu próprio dispositivo) permite que os usuários registrem seus telefones, tablets ou computadores pessoais. O registro de CODs (dispositivos de propriedade corporativa) permite cenários de gerenciamento como registro automático, dispositivos compartilhados ou requisitos de registro pré-autorizados.

Caso utilize o [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune), hospedado na nuvem ou local, você pode habilitar o gerenciamento simples do Intune sem registro. Computadores Windows também podem ser gerenciados usando o [software cliente do Intune](#manage-windows-pcs-with-intune).

Por padrão, dispositivos para todas as plataformas têm permissão para se registrarem no Intune. Para bloquear o registro de dispositivos, entre no [Portal de administração do Microsoft Intune](http://manage.microsoft.com) com suas credenciais de administrador. Escolha **Admin** > **Gerenciamento de Dispositivo Móvel** > **Regras de Registro** e desmarque as caixas de seleção aplicáveis para as plataformas que deseja bloquear.

## <a name="overview-of-device-enrollment-methods"></a>Visão geral dos métodos de registro do dispositivo

A tabela a seguir mostra os métodos de registro do Intune e os requisitos e recursos com suporte de cada método. Os requisitos e recursos são descritos abaixo.

- **Apagar** – indica se o dispositivo precisa ser apagado antes que os usuários possam registrá-lo. O termo "apagar" significa uma redefinição de fábrica do dispositivo, que remove todos os dados. Para obter mais informações, consulte [Desativar dispositivos](retire-devices-from-microsoft-intune-management.md).
- **Afinidade** – associa dispositivos a usuários. Necessário para MAM (gerenciamento de dispositivo móvel) e acesso condicional a dados da empresa. Para obter mais informações, consulte [Afinidade do usuário](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices).
- **Bloqueio** – indica se os usuários são impedidos de cancelar o registro dos dispositivos usando menus do sistema operacional nativo. Os usuários podem cancelar o registro de seus dispositivos em todas as plataformas usando o aplicativo Portal da Empresa.

**Métodos de registro do iOS**

| **Método** |    **Apagamento necessário?** |    **Afinidade**    |    **Bloqueio** | **Detalhes** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Não|    Sim |    Não | [Mais informações](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|    Não |Não |Não    | [Mais informações](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|    Sim |    Opcional |    Opcional|[Mais informações](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**|    Sim |    Opcional |    Não| [Mais informações](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**|    Não |    Não    | Não|[Mais informações](ios-direct-enrollment-in-microsoft-intune.md)|

**Métodos de registro do Windows**

| **Método** |    **Apagamento necessário?** |    **Afinidade**    |    **Bloqueio** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Não|    Sim |    Não | [Mais informações](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|    Não |Não |Não    |[Mais informações](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Métodos de registro do Android**

| **Método** |    **Apagamento necessário?** |    **Afinidade**    |    **Bloqueio** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Não|    Sim |    Não | [Mais informações](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|    Não |Não |Não    |[Mais informações](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Métodos de registro do Android para Trabalho**

| **Método** |    **Apagamento necessário?** |    **Afinidade**    |    **Bloqueio** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Não|    Sim |    Não | [Mais informações](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|    Não |Não |Não    |[Mais informações](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Métodos de registro do macOS**

| **Método** |    **Apagamento necessário?** |    **Afinidade**    |    **Bloqueio** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Não|    Sim |    Não | [Mais informações](prerequisites-for-enrollment.md)|


Para ver uma série de perguntas que o ajudarão a encontrar o método certo, consulte [Escolher como registrar dispositivos](/intune/get-started/choose-how-to-enroll-devices1).

## <a name="byod"></a>BYOD
Usuários de “Traga seu próprio dispositivo” instalam o aplicativo de Portal da Empresa e registram o dispositivo. Isso permite que os usuários se conectem à rede da empresa e ingressem no domínio ou no Azure Active Directory. Para a maioria das plataformas, você precisa habilitar o registro de BYOD para muitos cenários de COD. Para obter mais informações, consulte [Pré-requisitos para o registro de dispositivos](prerequisites-for-enrollment.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

## <a name="corporate-owned-devices"></a>Dispositivos de propriedade corporativa
CODs (dispositivos de propriedade corporativa) podem ser gerenciados com o console do Intune. Dispositivos iOS podem ser registrados diretamente por meio das ferramentas fornecidas pela Apple. Todos os tipos de dispositivo podem ser registrados por um administrador ou gerente usando o gerenciador de registro do dispositivo. Dispositivos com um número IMEI também podem ser identificados e marcados como propriedade da empresa para habilitar cenários de COD.

Para obter mais informações, consulte [Registrar dispositivos corporativos](manage-corporate-owned-devices.md).

### <a name="dem"></a>DEM
O Gerenciador de registro do dispositivo é um conta especial do Intune usada para registrar e gerenciar vários dispositivos corporativos. Os gerentes podem instalar o Portal da Empresa e registrar vários dispositivos sem usuário. Saiba mais sobre o [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
O DEP (Programa de registro de dispositivos) da Apple permite criar e implantar políticas "por ondas de rádio" em dispositivos iOS adquiridos e gerenciados com o DEP. O dispositivo é registrado quando os usuários liga o dispositivo pela primeira vez e executa o Assistente de Configuração do iOS. Este método dá suporte ao modo **Supervisionado do iOS** que, por sua vez, permite:
  -    Registro bloqueado
  -    Modo de quiosque e outras restrições e configurações avançadas

Saiba mais sobre o [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

### <a name="usb-sa"></a>USB-SA
Os administradores de TI usam o Apple Configurator, por USB, para preparar manualmente todos os dispositivos de propriedade corporativa para o registro usando o Assistente de Configuração. O administrador de TI cria um perfil de registro e exporta-o para o Apple Configurator. Quando os usuários recebem seus dispositivos, eles devem executar o Assistente de Instalação para registrá-los. Este método dá suporte ao modo **Supervisionado do iOS** que, por sua vez, permite:
  -    Registro bloqueado
  -    Modo de quiosque e outras restrições e configurações avançadas

Saiba mais sobre [Assistente para configuração de registro com Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

### <a name="usb-direct"></a>USB-Direct
Para o registro direto, o administrador deve registrar todos os dispositivos manualmente criando uma política de registro e exportando-a para o Apple Configurator. Dispositivos conectados por USB e corporativos são registrados diretamente sem a necessidade de uma redefinição de fábrica. Os dispositivos são gerenciados como dispositivos sem usuário. Eles não são bloqueados ou supervisionados e não dão suporte a acesso condicional, detecção de jailbreak ou gerenciamento de aplicativo móvel.  Saiba mais sobre o [registro direto com o Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Gerenciamento de dispositivos móveis usando o Exchange ActiveSync e o Intune
Dispositivos móveis que não estão registrados, mas que conectam ao EAS (Exchange ActiveSync) podem ser gerenciados pelo Intune usando a política de MDM do EAS. O Intune usa um Exchange Connector para se comunicar com o EAS, hospedado na nuvem ou local. Para obter mais informações, consulte [Gerenciamento de dispositivo móvel usando o Exchange ActiveSync e o Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md).


## <a name="windows-pc-management-with-intune"></a>Gerenciamento de computador Windows com o Intune  
Você também pode usar o Microsoft Intune para gerenciar computadores Windows com o software cliente do Intune. Computadores gerenciados com o cliente Intune podem:

 - Informar inventários de hardware e software
 - Instalar aplicativos da área de trabalho (por exemplo arquivos .exe e .msi)
 - Gerenciar as configurações do firewall

Computadores que são gerenciados com o software cliente do Intune não podem ser totalmente apagados, embora o apagamento seletivo esteja disponível. Computadores gerenciados com o cliente de software do Intune não podem tirar proveito de muitos recursos de gerenciamento do Intune como acesso condicional, configurações de VPN e Wi-Fi ou implantação de certificados e configurações de email. Para obter mais informações, consulte [Gerenciar computadores Windows com o Intune](manage-windows-pcs-with-microsoft-intune.md).

## <a name="supported-device-platforms"></a>Plataformas de dispositivos com suporte

O Intune pode gerenciar as seguintes plataformas de dispositivo:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## <a name="next-steps"></a>Próximas etapas
- [Pré-requisitos para registro de dispositivo](prerequisites-for-enrollment.md)
- [Gerenciar dispositivos corporativos](manage-corporate-owned-devices.md)
- [Dispositivos móveis e computadores com suporte](../get-started/supported-mobile-devices-and-computers.md)

