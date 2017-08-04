---
title: Escolha como registrar dispositivos iOS no Intune
titleSuffix: Intune on Azure
description: Saiba como configurar o registro de dispositivos iOS no Microsoft Intune.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 092f582cf30210858bd8cdd3879edfa873523ccb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="choose-how-to-enroll-ios-and-macos-devices"></a>Escolha como registrar dispositivos iOS e macOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este tópico descreve os métodos que um administrador de TI pode usar para habilitar o registro de dispositivo iOS no Intune.

Use as seguintes informações para decidir qual método usar para registro de dispositivos iOS. Todos os métodos a seguir, exceto BYOD, são para registro de dispositivos corporativos.

**Pré-requisito:** um[certificado do Apple Push Notification Service](apple-mdm-push-certificate-get.md) é obrigatório.

## <a name="user-owned-ios-devices-byod"></a>BYOD (Dispositivos iOS de propriedade do usuário)

Se os usuários desejarem registrar seus dispositivos pessoais BYOD (traga seu próprio dispositivo), eles poderão baixar o aplicativo do Portal da Empresa para iOS na Loja de Aplicativos e seguir as instruções de registro no aplicativo. Depois de registrado, os usuários podem se conectar à rede da empresa, ingressar no domínio ou no Azure Active Directory e obter acesso aos recursos corporativos. Para habilitar o cenário BYOD, o único requisito é ter um [certificado Apple Push Notification Service](apple-mdm-push-certificate-get.md). Você também pode bloquear o registro de dispositivos iOS pessoais. Consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md) para obter instruções.

## <a name="user-owned-macos-devices-byod"></a>Dispositivos macOS de propriedade do usuário (BYOD)

Você pode habilitar o registro de dispositivo macOS. Para habilitar o registro do macOS, o único requisito é ter um [certificado Apple Push Notification Service](apple-mdm-push-certificate-get.md). Para obter mais informações, consulte [Registrar dispositivos macOS](./macos-enroll.md)

## <a name="enrollment-program-with-apple"></a>Programa de registro com a Apple
A Apple oferece programas de compra de dispositivo que incluem o registro de dispositivo e a infraestrutura de gerenciamento. O dispositivo comprado por meio de um desses programas pode ser registrado em massa em um registro “sem fio” com a atribuição de números de série do dispositivo ao gerenciamento do Intune.

- **DEP (Programa de registro de dispositivos)** – programa de registro de dispositivos da Apple para organizações e empresas. Para obter mais informações, consulte [Registrar dispositivos iOS usando o Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).
- **Apple School Manager** – programa de registro de dispositivos da Apple para escolas. Para obter mais informações, consulte [Habilitar o registro de dispositivo iOS com o Apple School Manager](apple-school-manager-set-up-ios.md)

## <a name="apple-configurator"></a>Apple Configurator

Você pode registrar dispositivos iOS exportando um perfil de Registro Corporativo e, em seguida, conectando esses dispositivos móveis a um Mac que esteja executando o Apple Configurator. O Apple Configurator dá suporte a duas formas de registro:

- **Registro no Assistente de Configuração**: redefine o dispositivo para as configurações de fábrica e o prepara para a configuração do novo usuário do dispositivo. Esse método requer que o administrador conecte o dispositivo iOS a um computador Mac via USB executando o Apple Configurator para pré-configurar o registro. Em seguida, os dispositivos são entregues aos usuários, que executam o Assistente de Configuração na primeira inicialização do dispositivo. Esse processo configura o dispositivo dos usuários com suas credenciais corporativas ou de estudante e conclui o processo de registro. Para obter mais informações, confira [Registrar dispositivos iOS usando o Apple Configurator e o Assistente de Configuração](apple-configurator-setup-assistant-enroll-ios.md).

- **Registro direto**: cria um arquivo compatível com Apple Configurator para uso durante a preparação do dispositivo. O dispositivo registrado não é redefinido para os padrões de fábrica nem fica associado a nenhum usuário. Para registrar dispositivos, o administrador precisa conectar o dispositivo iOS por meio de USB em um computador Mac executando o Apple Configurator. Para saber mais, confira [Registrar dispositivos iOS usando o Apple Configurator Device Enrollment](apple-configurator-direct-enroll-ios.md).

## <a name="use-the-device-enrollment-program-dep"></a>Usar o DEP (Device Enrollment Program)

O DEP implanta um perfil de registro "over the air" em dispositivos que são adquiridos por meio do DEP. Quando o usuário executa o Assistente de Configuração no dispositivo na primeira inicialização, o dispositivo é registrado no Intune. Para obter mais informações, consulte [Registrar dispositivos iOS usando o Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).

## <a name="use-the-device-enrollment-manager-dem"></a>Usar o DEM (Gerenciador de Registro de Dispositivos)
O gerenciador de registros de dispositivo é uma conta de usuário genérica que pode registrar e gerenciar até 1.000 dispositivos. Os dispositivos gerenciados pelo DEM não podem ter afinidade de usuário e, portanto, o dispositivo nunca tem um proprietário. Conceda permissões DEM a um usuário do Intune para proporciona essas funcionalidades. Cada dispositivo que o usuário DEM registra usa uma licença do Intune. Para obter mais informações, consulte [Registrar dispositivos usando o Gerenciador de registro de dispositivo](device-enrollment-manager-enroll.md).
