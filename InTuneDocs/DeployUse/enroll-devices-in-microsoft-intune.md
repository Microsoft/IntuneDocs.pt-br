---
title: Registrar dispositivos | Microsoft Intune
description: "O MDM (Gerenciamento de Dispositivo Móvel) usa o registro para trazer dispositivos para o gerenciamento e permitir acesso a recursos."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6256b1ed5edb72bf9f623555a4c6e3fddb864b32
ms.openlocfilehash: 71f0637a1cb6fdafb590ca274fcc0f80707ed6ce


---

# Registrar dispositivos para gerenciamento no Intune
O MDM (Gerenciamento de Dispositivo Móvel) do Microsoft Intune usa o registro para trazer dispositivos para o gerenciamento e permitir acesso aos recursos. A maneira como você registra dispositivos depende do tipo de dispositivo, da propriedade e do nível de gerenciamento necessário. Cenários BYOD (Traga seu próprio dispositivo) e COD (Dispositivo de Propriedade da Empresa) exigem um processo de registro. Organizações que usam o Exchange ActiveSync, hospedado na nuvem ou local, podem habilitar gerenciamento mais leve sem requisitos de registro. Computadores Windows também podem ser gerenciados usando o software cliente Intune.

###  Plataformas de dispositivos com suporte

O Intune pode gerenciar as seguintes plataformas de dispositivo:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Visão geral dos métodos de registro do dispositivo

A tabela a seguir mostra os métodos de registro para métodos de registro do dispositivo de propriedade corporativa com seus benefícios.

**Métodos de Registro do iOS**

| **Método** |  **[Apagamento](#Wipe)** | **[Afinidade](#Affinity)**   |   **[Bloqueado](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Não|    Sim |   Não |
|**[DEM](#DEM)**|   Não |Não |Não  |
|**[DEP](#DEP)**|   Sim |   Opt |   Opt|
|**[USB-SA](#USB-SA)**| Sim |   Opt |   Não|
|**[USB-Direct](#USB-Direct)**| Não |    Não  | Não|

**Métodos de Registro do Android e do Windows**

| **Método** |  **[Apagamento](#Wipe)** | **[Afinidade](#Affinity)**   |   **[Bloqueado](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Não|    Sim |   Não |
|**[DEM](#DEM)**|   Não |Não |Não  |

**Métodos de registro para dispositivos de propriedade corporativa**

### BYOD
“Traga seu próprio dispositivo”. Os usuários instalam o aplicativo de Portal da Empresa e registram o dispositivo. Registrar um dispositivo com o Portal da Empresa unirá o dispositivo ao local de trabalho. Registrar os dispositivos iOS com o Portal da Empresa requer uma ID da Apple. O BYOD não requer configuração adicional para dispositivos de propriedade corporativa. Consulte as etapas para [Configurar o gerenciamento de dispositivo](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management). ([Voltar à tabela](#overview-of-device-enrollment-methods))

### DEM
Gerenciador de registro do dispositivo. O administrador cria contas DEM para gerenciar dispositivos corporativos. Os gerentes podem então instalar o Portal da Empresa e registrar vários dispositivos sem usuário. Saiba mais sobre o [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

### DEP
Programa de Registro do Dispositivo da Apple. O administrador cria e implanta a política "por ondas de rádio" para dispositivos iOS corporativos adquiridos e gerenciados com o DEP. O dispositivo é registrado quando o usuário executa o Assistente de Instalação do iOS. Este método dá suporte ao modo **Supervisionado do iOS** que, por sua vez, permite:
  - Registro bloqueado
  - Acesso condicional
  - Detecção de jailbreak
  - Gerenciamento de aplicativos móveis

Saiba mais sobre o [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

### USB-SA
Registro de assistente de configuração conectado com USB. O administrador cria uma política do Intune e a exporta para o Apple Configurator. Dispositivos conectados por USB e corporativos são preparados com a política do Intune. O administrador deve registrar manualmente cada dispositivo. Os usuários recebem seus dispositivos e executam o Assistente de Instalação, registrando seu dispositivo. Este método dá suporte ao modo **Supervisionado do iOS** que, por sua vez, permite:
  - Acesso condicional
  - Detecção de jailbreak
  - Gerenciamento de aplicativos móveis

Saiba mais sobre [Assistente para configuração de registro com Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

### USB-Direct
Registro direto. O administrador cria uma política do Intune e a exporta para o Apple Configurator. Dispositivos conectados por USB e corporativos são registrados diretamente sem a necessidade de uma redefinição de fábrica. O administrador deve registrar manualmente cada dispositivo. Os dispositivos são gerenciados como dispositivos sem usuário. Eles não são bloqueados ou supervisionados e não dão suporte a acesso condicional, detecção de jailbreak, gerenciamento de aplicativos móveis. Saiba mais sobre o [registro direto com o Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

**Comportamento para dispositivos móveis de propriedade corporativa**

### Apagamento
Especifica se o registro do dispositivo exige que o dispositivo seja redefinido de fábrica, removendo todos os dados do dispositivo e retornando-o ao seu estado original.
[Desativar dispositivos](retire-devices-from-microsoft-intune-management.md) ([Voltar à tabela](#overview-of-device-enrollment-methods))

### Afinidade
Especifica se o método de registro dá suporte a "Afinidade de Usuário", que se conecta a um dispositivo com um usuário específico. Dispositivos "Opt" dispositivos podem ser registrados com ou sem afinidade de usuário. Afinidade de usuário é necessária para dar suporte ao seguinte:
  - Aplicativos MAM (Gerenciamento de aplicativos móveis)
  - Acesso condicional para dados de email e da empresa
  - Aplicativo do Portal da Empresa

[Afinidade do usuário](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#user-affinity-for-ios-corporate-owned-devices-using-the-company-portal) ([Voltar à tabela](#overview-of-device-enrollment-methods))

### Bloqueio
Especifica se o dispositivo pode ser bloqueado para impedir que o usuário remova a política do Intune, removendo efetivamente o dispositivo do gerenciamento. Para dispositivos iOS, bloquear o dispositivo requer que ele esteja no modo Supervisionado.
([Voltar à tabela](#overview-of-device-enrollment-methods))

## Habilitar registro de dispositivo  
 O registro permite que os usuários acessem os recursos da empresa em seus dispositivos pessoais e permite que o administrador verifique se esses dispositivos estão em conformidade com as políticas que protegem os recursos da empresa. Essa é a melhor maneira de habilitar cenários "traga seu próprio dispositivo" com o Intune. O administrador deve habilitar o registro no console do Intune, que pode exigir a criação de uma relação de confiança com o dispositivo e atribuição de licenças aos usuários. O dispositivo é então registrado, geralmente quando os usuários inserem suas credenciais corporativas ou de estudante. Em seguida, o dispositivo recebe a política do Intune e obtém acesso aos recursos.

[Preparar-se para registrar dispositivos no Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Registrar dispositivos de propriedade corporativa
COD (Dispositivos de Propriedade Corporativa) podem ser gerenciados com o console do Intune. Os dispositivos iOS podem ser registrados diretamente por meio de ferramentas fornecidas pela Apple. Todos os tipos de dispositivo podem ser registrados por um administrador ou gerente usando o gerenciador de registro do dispositivo. Dispositivos com um número IMEI também podem ser identificados e marcados como propriedade da empresa para habilitar cenários de COD.

[Registrar dispositivos de propriedade corporativa](manage-corporate-owned-devices.md)

## Gerenciamento de dispositivos móveis usando o Exchange ActiveSync e o Intune
Dispositivos móveis que não estão registrados, mas que conectam ao EAS (Exchange ActiveSync) podem ser gerenciados pelo Intune usando a política de MDM do EAS. O Intune usa um Exchange Connector para se comunicar com o EAS, hospedado na nuvem ou local.

[Gerenciamento de dispositivos móveis usando o Exchange ActiveSync e o Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Gerenciar PCs Windows com o Intune  
Você também pode usar o Microsoft Intune para gerenciar computadores Windows usando o software cliente do computador Windows com Intune. Computadores gerenciados com o cliente Intune podem:

 - Informar inventários de hardware e software
 - Instalar aplicativos da área de trabalho (por exemplo arquivos .exe e .msi)
 - Configurações de firewall

Computadores gerenciados com o software cliente Intune não podem ser apagados nem desativados seletivamente e não podem tirar proveito de muitos recursos de gerenciamento do Intune como acesso condicional, configurações de VPN e Wi-Fi ou implantação de certificados e configurações de email.

[Gerenciar PCs Windows com o Intune](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


