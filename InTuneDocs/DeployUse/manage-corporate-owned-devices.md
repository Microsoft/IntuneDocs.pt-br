---
# required metadata

title: Registrar dispositivos de propriedade corporativa | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrar dispositivos corporativos com o Microsoft Intune
Organização ou COD (dispositivos de propriedade corporativa) podem ser colocados no gerenciamento do Intune de várias formas, dependendo do dispositivo, como ele foi adquirido e as necessidades da organização.

## Dispositivos iOS corporativos
Esses métodos de registro são bons para cenários CYOD ("Escolha seu próprio dispositivo") em que a organização adquire os dispositivos para usuários, mas deseja manter o gerenciamento do dispositivo. Se a sua organização tiver adquirido dispositivos iOS, você poderá pré-configurar o registro para que o dispositivo seja gerenciado desde a primeira vez que o usuário o ativar. O Intune dá suporte ao registro via [DEP (programa de registro de dispositivo) da Apple](ios-device-enrollment-program-in-microsoft-intune.md) ou usando a ferramenta Apple Configurator em execução em um computador Mac para registro [direto](ios-direct-enrollment-in-microsoft-intune.md) ou [Assistente de Configuração](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[Registrar dispositivos iOS corporativos](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Gerenciador de registro de dispositivos
As organizações podem usar o Intune para gerenciar grandes números de dispositivos móveis com uma única conta de usuário chamada de uma conta de gerenciador de registro do dispositivo. Depois de criar uma conta de Gerenciador de registro do dispositivo, essa conta poderá ser usada por um gerente para registrar mais de cinco dispositivos padrão permitidos por padrão para usuários normais. O registro de dispositivos com um Gerenciador de registro do dispositivo funciona somente para dispositivos que não são usados por um usuário específico. Esses dispositivos são bons para aplicativos de ponto de venda ou utilitários, por exemplo, mas ruins para usuários que precisam acessar os recursos da empresa ou email.

[Registrar dispositivos corporativos com o gerenciador de registro de dispositivo](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## IMEI (Identidade de equipamentos móveis internacional)
IMEI (identidade de equipamentos móveis internacional) exclusivo são uma propriedade de dispositivo de comum para muitos fabricantes de dispositivos móveis. Os administradores do Intune podem importar números IMEI para os dispositivos da empresa. Quando o dispositivo se torna gerenciado pelo Intune, ele pode ser marcado como um dispositivo corporativo e receber a política apropriada.

[Especificar dispositivos corporativos com números IMEI (Identidade de Equipamentos Móveis Internacional)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

## Visão geral dos métodos de registro do dispositivo de propriedade corporativa

A tabela a seguir mostra os métodos de registro para métodos de registro do dispositivo de propriedade corporativa com seus benefícios.

**Métodos de Registro do iOS**

| **Método** |  **[Redefinir](#Reset)** |   **[Afinidade](#Affinity)**   |   **[Bloqueado](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Não|    Sim |   Não |
|**[DEM](#DEM)**|   Não |Não |Não  |
|**[DEP](#DEP)**|   Sim |   Opt |   Opt|
|**[USB-SA](#USB-SA)**| Sim |   Opt |   Não|
|**[USB-Direct](#USB-Direct)**| Não |    Não  | Não|

**Métodos de Registro do Android e do Windows**

| **Método** |  **[Apagamento](#Wipe)** | **[Usuário](#User)**   |   **[Bloqueado](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Não|    Sim |   Não |
|**[DEM](#DEM)**|   Não |Não |Não  |

**Métodos de registro para dispositivos de propriedade corporativa**

### BYOD
“Traga seu próprio dispositivo”. Os usuários instalam o aplicativo de Portal da Empresa e registram o dispositivo. Registrar um dispositivo com o Portal da Empresa unirá o dispositivo ao local de trabalho. Registrar os dispositivos iOS com o Portal da Empresa requer uma ID da Apple. O BYOD não requer configuração adicional para dispositivos de propriedade corporativa. Consulte as etapas para [Configurar o gerenciamento de dispositivo](get-ready-to-enroll-devices-in-microsoft-intune#set-up-device-management.md).

### DEM
Gerenciador de registro do dispositivo. O administrador cria contas DEM. Os gerentes podem então instalar o Portal da Empresa e registrar vários dispositivos sem usuário. Saiba mais sobre o [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Voltar à tabela](#overview-of corporate-owned-device-enrollment-methods))

### DEP
Programa de Registro do Dispositivo da Apple. Administrador cria e implanta a política por ondas de rádio para dispositivos iOS adquiridos e gerenciados com o DEP. O dispositivo é registrado quando o usuário executa o Assistente de Instalação do iOS. Este método dá suporte ao modo **Supervisionado do iOS** que, por sua vez, permite:
  - Registro bloqueado
  - Acesso condicional
  - Detecção de jailbreak
  - Gerenciamento de aplicativos móveis

Saiba mais sobre o [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Voltar à tabela](#overview-of corporate-owned-device-enrollment-methods))

### USB-SA
Registro de assistente de configuração conectado com USB. O administrador cria uma política do Intune e a exporta para o Apple Configurator. Dispositivos conectados por USB são preparados com a política do Intune. O administrador deve registrar manualmente cada dispositivo. Os usuários recebem seus dispositivos e executam o Assistente de Instalação, registrando seu dispositivo. Este método dá suporte ao modo **Supervisionado do iOS** que, por sua vez, permite:
  - Registro bloqueado
  - Acesso condicional
  - Detecção de jailbreak
  - Gerenciamento de aplicativos móveis

Saiba mais sobre [Assistente para configuração de registro com Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Voltar à tabela](#overview-of corporate-owned-device-enrollment-methods))

### USB-Direct
Registro direto. O administrador cria uma política do Intune e a exporta para o Apple Configurator. Dispositivos conectados por USB são registrados diretamente sem a necessidade de uma redefinição de fábrica. O administrador deve registrar manualmente cada dispositivo. Os dispositivos são gerenciados como dispositivos sem usuário. Eles não são bloqueados ou supervisionados e não dão suporte a acesso condicional, detecção de jailbreak, gerenciamento de aplicativos móveis. Saiba mais sobre o [registro direto com o Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Voltar à tabela](#overview-of corporate-owned-device-enrollment-methods))

**Comportamento para dispositivos móveis de propriedade corporativa**

### Redefinir
Especifica se o registro do dispositivo exige que o dispositivo seja redefinido de fábrica, removendo todos os dados do dispositivo e retornando-o ao seu estado original.
([Voltar à tabela](#overview-of corporate-owned-device-enrollment-methods))

### Afinidade
Especifica se o método de registro dá suporte a "Afinidade de Usuário", que se conecta a um dispositivo com um usuário específico. Dispositivos "Opt" dispositivos podem ser registrados com ou sem afinidade de usuário. Afinidade de usuário é necessária para dar suporte ao seguinte:
  - Aplicativos MAM (Gerenciamento de aplicativos móveis)
  - Acesso condicional para dados de email e da empresa
  - Aplicativo do Portal da Empresa

([Voltar à tabela](#overview-of corporate-owned-device-enrollment-methods))([Voltar à tabela](#overview-of corporate-owned-device-enrollment-methods))

### Bloqueio
Especifica se o dispositivo pode ser bloqueado para impedir que o usuário remova a política do Intune, removendo efetivamente o dispositivo do gerenciamento. Para dispositivos iOS, bloquear o dispositivo requer que ele esteja no modo Supervisionado.
([Voltar à tabela](#overview-of corporate-owned-device-enrollment-methods))([Voltar à tabela](#overview-of corporate-owned-device-enrollment-methods))


<!--HONumber=Jun16_HO1-->


