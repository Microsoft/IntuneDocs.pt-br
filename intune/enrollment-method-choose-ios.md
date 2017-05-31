---
title: Escolha como registrar dispositivos iOS no Intune
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como configurar o registro de dispositivos iOS no Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ee0ecf26a333ec441eb95e79473a9bf405e4120c
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="choose-how-to-enroll-ios-devices"></a>Escolha como registrar dispositivos iOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Este tópico descreve os métodos que você pode usar para registrar dispositivos iOS e os pré-requisitos para registro.

Use as seguintes informações para decidir qual método usar para registro de dispositivos iOS. Todos os métodos a seguir, exceto BYOD, são para registro de dispositivos corporativos.

**Pré-requisito:** um[certificado do Apple Push Notification Service](apple-mdm-push-certificate-get.md) é obrigatório.

## <a name="user-owned-ios-devices-byod"></a>BYOD (Dispositivos iOS de propriedade do usuário)

Se quiserem que os usuários registrem dispositivos pessoais BYOD (traga seu próprio dispositivo), o único método de registro disponível será os usuários baixarem o aplicativo Portal da Empresa para iOS da App Store e seguir as instruções de registro no aplicativo. Depois de registrado, os usuários podem se conectar à rede da empresa, ingressar no domínio ou no Azure Active Directory e obter acesso aos recursos corporativos. Você pode bloquear o registro de dispositivos iOS de propriedade pessoal. Consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md#set-device-type-restrictions) para obter instruções.

## <a name="apple-configurator"></a>Apple Configurator

Você pode registrar dispositivos iOS exportando um perfil de Registro Corporativo e, em seguida, conectando esses dispositivos móveis a um Mac que esteja executando o [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017). O Apple Configurator dá suporte a duas formas de registro:

- **Registro no Assistente de Configuração**: redefine o dispositivo para as configurações de fábrica e o prepara para a configuração do novo usuário do dispositivo. Esse método requer que o administrador conecte o dispositivo iOS a um computador Mac via USB executando o Apple Configurator para pré-configurar o registro. Em seguida, os dispositivos são entregues aos usuários, que executam o processo do Assistente de Configuração. Esse processo configura o dispositivo dos usuários com suas credenciais corporativas ou de estudante e conclui o processo de registro. Para obter mais informações, confira [Registrar dispositivos iOS usando o Apple Configurator e o Assistente de Configuração](apple-configurator-setup-assistant-enroll-ios.md).

- **Registro direto**: cria um arquivo compatível com Apple Configurator para uso durante a preparação do dispositivo. O dispositivo registrado não é redefinido para os padrões de fábrica nem fica associado a nenhum usuário. Para registrar dispositivos, o administrador precisa conectar o dispositivo iOS por meio de USB em um computador Mac executando o Apple Configurator. Para saber mais, confira [Registrar dispositivos iOS usando o Apple Configurator Device Enrollment](apple-configurator-direct-enroll-ios.md).

## <a name="use-the-device-enrollment-program-dep"></a>Usar o DEP (Device Enrollment Program)

O DEP implanta um perfil de registro "over the air" em dispositivos que são adquiridos por meio do DEP. Quando o usuário executa o Assistente de Configuração no dispositivo, o dispositivo é registrado no Intune. O registro dos dispositivos feito pelo DEP não pode ser desfeito pelos usuários. Para obter mais informações, consulte [Registrar dispositivos iOS usando o Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).

## <a name="use-the-device-enrollment-manager-dem"></a>Usar o DEM (Gerenciador de Registro de Dispositivos)
O Gerenciador de registro do dispositivo é um tipo de conta de usuário que pode registrar e gerenciar até 1.000 dispositivos. Adicione usuários existentes à conta do DEM para fornecer recursos especiais. Cada dispositivo que o usuário DEM registra usa uma única licença Intune. Para obter mais informações, consulte [Registrar dispositivos usando o Gerenciador de registro de dispositivo](device-enrollment-manager-enroll.md).

