---
title: "O que é o registro do dispositivo do Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba mais sobre o registro de dispositivos iOS, Android e Windows."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 57bad4be991b61fe5212d340ab8d89cb6af3b0f7
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-device-enrollment"></a>O que é o registro de dispositivo?
[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Este tópico descreve o registro e as diferentes maneiras de registrar dispositivos móveis no gerenciamento do Intune.

Os dispositivos são registrados no Intune, para que você possa gerenciá-los. Chamamos essa funcionalidade na documentação do Intune de MDM (gerenciamento de dispositivo móvel). Quando dispositivos são registrados no Intune, eles recebem um certificado do MDM, que os dispositivos usam para se comunicar com o serviço Intune.

A maneira como você registra seus dispositivos depende do tipo de dispositivo, da propriedade e do nível de gerenciamento necessário. O registro de BYOD (Traga seu próprio dispositivo) permite que os usuários registrem seus telefones, tablets ou computadores pessoais. O registro de CODs (dispositivos de propriedade corporativa) permite cenários de gerenciamento como registro automático, dispositivos compartilhados ou requisitos de registro pré-autorizados.

Caso use o Exchange ActiveSync, hospedado na nuvem ou local, você pode habilitar o gerenciamento simples do Intune sem registro (mais informações em breve). Você pode gerenciar computadores Windows como dispositivos móveis, que é o método recomendado descrito abaixo.


## <a name="overview-of-device-enrollment-methods"></a>Visão geral dos métodos de registro do dispositivo

A tabela a seguir mostra os métodos de registro do Intune e os requisitos e recursos com suporte de cada método. Os requisitos e recursos são descritos abaixo. Os seguintes termos são usados na tabela:

- **Apagar** – indica se o dispositivo precisa ser apagado antes que os usuários possam registrá-lo. O termo "apagar" significa uma redefinição de fábrica do dispositivo, que remove todos os dados. Para obter mais informações, consulte [Usar apagamento completo ou seletivo em dispositivos](devices-wipe.md).
- **Afinidade** – associa dispositivos a usuários. Necessário para MAM (gerenciamento de dispositivo móvel) e acesso condicional a dados da empresa. Para obter mais informações, consulte [Afinidade do usuário](device-enrollment-program-enroll-ios.md).
- **Bloqueio** – indica se os usuários são impedidos de cancelar o registro de seus dispositivos no gerenciamento. Os usuários podem cancelar o registro de seus dispositivos em todas as plataformas usando o aplicativo Portal da Empresa. Eles não podem usar os menus do sistema operacional nativo para cancelar o registro.


**Métodos de registro do iOS**

| **Método** |    **Apagamento necessário?** |    **Afinidade**    |    **Bloqueio** | **Detalhes** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Não|    Sim |    Não | Mais informações em breve|
|**[DEM](#dem)**|    Não |Não |Não    | [Mais informações](device-enrollment-program-enroll-ios.md)|
|**[DEP](#dep)**|    Sim |    Opcional |    Opcional|[Mais informações](device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**|    Sim |    Opcional |    Não| [Mais informações](apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**|    Não |    Não    | Não|[Mais informações](apple-configurator-direct-enroll-ios.md)|

**Métodos de registro do Windows**

| **Método** |    **Apagamento necessário?** |    **Afinidade**    |    **Bloqueio** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Não |    Sim |    Não | [Mais informações](windows-enroll.md)|
|**[DEM](#dem)**|    Não |Não |Não    |[Mais informações](device-enrollment-manager-enroll.md)|

**Métodos de registro do Android**

| **Método** |    **Apagamento necessário?** |    **Afinidade**    |    **Bloqueio** | **Detalhes**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Não|    Sim |    Não | [Mais informações](android-enroll.md)|
|**[DEM](#dem)**|    Não |Não |Não    |[Mais informações](device-enrollment-program-enroll-ios.md)|
|**Android for Work**| Não | Sim | Não| [Mais informações](android-enroll.md) |


## <a name="byod"></a>BYOD
Usuários de “Traga seu próprio dispositivo” instalam o aplicativo de Portal da Empresa e registram o dispositivo. Isso permite que os usuários se conectem à rede da empresa e ingressem no domínio ou no Azure Active Directory. Para a maioria das plataformas, você precisa habilitar o registro de BYOD para muitos cenários de COD. Você pode bloquear o registro de dispositivos Android e iOS de propriedade pessoal. Consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md#set-device-type-restrictions) para obter instruções.

## <a name="corporate-owned-devices"></a>Dispositivos de propriedade corporativa
CODs (dispositivos de propriedade corporativa) podem ser gerenciados com o Portal do Azure. Dispositivos iOS podem ser registrados diretamente por meio das ferramentas fornecidas pela Apple. Todos os tipos de dispositivo podem ser registrados por um administrador ou gerente usando o gerenciador de registro do dispositivo. Dispositivos com um número IMEI também podem ser identificados e marcados como propriedade da empresa para habilitar cenários de COD.

### <a name="dem"></a>DEM
O DEM (gerenciador de registro de dispositivos) é uma conta de usuário especial usada para registrar e gerenciar vários dispositivos corporativos. Os gerentes podem instalar o Portal da Empresa e registrar vários dispositivos sem usuário. Saiba mais sobre o [DEM](device-enrollment-manager-enroll.md). ([Voltar à tabela](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
O DEP (Programa de registro de dispositivos) da Apple permite criar e implantar políticas "por ondas de rádio" em dispositivos iOS adquiridos e gerenciados com o DEP. O dispositivo é registrado quando os usuários liga o dispositivo pela primeira vez e executa o Assistente de Configuração do iOS. Este método dá suporte ao modo **Supervisionado do iOS** que, por sua vez, permite:

  -    Registro bloqueado
  -    Modo de quiosque e outras restrições e configurações avançadas

Para saber mais sobre o registro de iOS, consulte:

- [Escolha como registrar dispositivos iOS](enrollment-method-choose-ios.md)
- [Registrar dispositivos iOS usando o Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md)
- [Voltar à tabela acima](#overview-of-device-enrollment-methods)

### <a name="usb-sa"></a>USB-SA
Os administradores de TI usam o Apple Configurator, por USB, para preparar manualmente todos os dispositivos de propriedade corporativa para o registro usando o Assistente de Configuração. O administrador de TI cria um perfil de registro e exporta-o para o Apple Configurator. Quando os usuários recebem seus dispositivos, eles devem executar o Assistente de Instalação para registrá-los. Este método dá suporte ao modo **Supervisionado do iOS** que, por sua vez, permite:
  -    Registro bloqueado
  -    Modo de quiosque e outras restrições e configurações avançadas

Para saber mais sobre o registro de iOS, consulte:

- [Decidir como registrar dispositivos iOS](enrollment-method-choose-ios.md)
- [Registrar dispositivos iOS com o Configurator e o Assistente de Configuração](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
Para o registro direto, o administrador deve registrar todos os dispositivos manualmente criando uma política de registro e exportando-a para o Apple Configurator. Dispositivos conectados por USB e corporativos são registrados diretamente sem a necessidade de uma redefinição de fábrica. Os dispositivos são gerenciados como dispositivos sem usuário. Eles não são bloqueados ou supervisionados e não dão suporte a acesso condicional, detecção de jailbreak ou gerenciamento de aplicativo móvel.

Para saber mais sobre o registro de iOS, consulte:

- [Decidir como registrar dispositivos iOS](enrollment-method-choose-ios.md)
- [Registrar dispositivos iOS com o Configurator e registro direto](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Gerenciamento de dispositivos móveis usando o Exchange ActiveSync e o Intune
Dispositivos móveis que não estão registrados, mas que conectam ao EAS (Exchange ActiveSync) podem ser gerenciados pelo Intune usando a política de MDM do EAS. O Intune usa um Exchange Connector para se comunicar com o EAS, hospedado na nuvem ou local. Mais informações em breve.

## <a name="supported-device-platforms-and-browsers"></a>Plataformas de dispositivo e navegadores com suporte

Consulte [Dispositivos e navegadores com suporte no Intune](https://docs.microsoft.com/intune-classic/get-started/supported-mobile-devices-and-computers)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Limpeza de dispositivo móvel após a expiração do certificado MDM

O certificado do MDM é renovado automaticamente quando os dispositivos móveis estão se comunicando com o serviço Intune. Se os dispositivos móveis forem apagados ou se eles não conseguirem se comunicar com o serviço Intune por um certo período, o certificado do MDM não será renovado. O dispositivo é removido do Portal do Azure 180 dias após a expiração do certificado do MDM.
