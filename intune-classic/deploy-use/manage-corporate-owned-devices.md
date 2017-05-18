---
title: Gerenciar dispositivos de propriedade corporativa | Microsoft Docs
description: "Registre dispositivos corporativos de diversas formas, com base no tipo de dispositivo, em como ele foi comprado e nas necessidades da organização."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 8ef5f26eced99dac547be727fc96e41c11d3a0e7
ms.lasthandoff: 04/24/2017


---

# <a name="enroll-corporate-owned-devices-by-using-intune"></a>Registrar dispositivos corporativos usando o Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Registre dispositivos corporativos ou da organização para registrá-los com o Intune de diversas formas, dependendo do tipo do dispositivo, de como ele foi adquirido e das necessidades da organização. Você também pode instalar o aplicativo de Portal da Empresa para registrar e gerenciar dispositivos corporativos, como em cenários de BYOD ("traga seu próprio dispositivo").

Por padrão, dispositivos para todas as plataformas têm permissão para se registrarem no Intune. Para bloquear o registro de dispositivos, entre no [Portal de administração do Microsoft Intune](https://manage.microsoft.com) com suas credenciais de administrador. Escolha **Admin** > **Gerenciamento de Dispositivo Móvel** > **Regras de Registro** e desmarque as caixas de seleção aplicáveis para as plataformas que deseja bloquear.

## <a name="enroll-corporate-owned-ios-devices"></a>Registrar dispositivos iOS corporativos

O métodos de registro de dispositivos corporativos são uma boa opção para cenários de CYOD "escolha seu próprio dispositivo". Em um ambiente de CYOD, a organização paga para um dispositivo que o usuário seleciona e a organização gerencia o dispositivo.

Se o usuário tiver dispositivos iOS entre os quais escolher, você pode pré-configurar registro para que o dispositivo seja gerenciado com o Intune desde a primeira vez em que o usuário o ativar. O Intune dá suporte ao registro por meio do [DEP (programa de registro de dispositivo) da Apple](ios-device-enrollment-program-in-microsoft-intune.md) ou usando a ferramenta Apple Configurator em um computador Mac para registro [direto](ios-direct-enrollment-in-microsoft-intune.md) ou com o [Assistente de Configuração](ios-setup-assistant-enrollment-in-microsoft-intune.md).

Saiba como [registrar dispositivos iOS corporativos](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

## <a name="create-a-device-enrollment-manager-account"></a>Criar uma conta de gerenciador de registro de dispositivo

Você pode criar uma conta de DEM (gerenciador de registro de dispositivo) de usuário único no Intune para gerenciar um grande número de dispositivos móveis na sua organização. Depois de criar uma conta de DEM, o gerente da conta designada pode registrar mais do que os 15 dispositivos que um usuário padrão pode registrar.

Você pode usar uma conta de DEM para registrar apenas dispositivos que não são usados por um usuário único específico. Esses tipos de dispositivos são bons para aplicativos de ponto de venda ou utilitários, por exemplo, mas não para usuários que precisam acessar os recursos da empresa ou o email.

Saiba como [registrar dispositivos corporativos usando uma conta de DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).

## <a name="enroll-corporate-owned-windows-10-enterprise-devices"></a>Registrar dispositivos Windows 10 Enterprise corporativos

Caso utilize o Azure Active Directory Premium ou a Microsoft Enterprise Mobility Suite em sua organização, você pode [registrar dispositivos Windows 10 Enterprise](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Quando um usuário adiciona uma conta corporativa ou de estudante a um dispositivo, o dispositivo é marcado automaticamente como "corporativo".

## <a name="import-imei-numbers"></a>Importar números IMEI

Muitos fabricantes de dispositivos móveis usam um número exclusivo chamado IMEI (identidade de equipamentos móveis internacional) em seus dispositivos. Você pode importar números IMEI para dispositivos de propriedade da sua organização. Quando o dispositivo passa a ser gerenciado pelo Intune, ele é marcado como um dispositivo corporativo.

Saiba como [marcar dispositivos corporativos usando números IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).

## <a name="identify-a-device-as-corporate-owned"></a>Identificar uma dispositivo como corporativo

O Intune reconhece um dispositivo como "corporativo" quando qualquer uma das seguintes condições forem verdadeiras:

 - O dispositivo foi [registrado usando uma conta de DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) (todas as plataformas).
 - O dispositivo foi registrado usando o [DEP da Apple](ios-device-enrollment-program-in-microsoft-intune.md) ou o [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) (somente iOS).
 - O fabricante do dispositivo [declarou o dispositivo previamente usando números IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) (todas as plataformas com números IMEI).
 - O dispositivo está registrado no [Azure Active Directory ou no Enterprise Mobility Suite como um dispositivo Windows 10 Enterprise](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) (somente Windows 10).

Quando um dispositivo é marcado como corporativo, você verá **Corporativo** na coluna **Propriedade** para esse registro de dispositivo no console do administrador. 

