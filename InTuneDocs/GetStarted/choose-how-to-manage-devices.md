---
title: Escolher como gerenciar dispositivos | Microsoft Intune
description: Saiba mais sobre as diferentes maneiras de registrar e gerenciar dispositivos.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: fccdf689868dbb181a171328fb7a8d186b9cb309


---

# <a name="choose-how-to-manage-devices"></a>Escolha como gerenciar dispositivos

Para tirar proveito dos muitos recursos que o Intune oferece, como a implantação de aplicativo e o controle de configurações de dispositivo, os dispositivos devem ser *gerenciados*. A maneira como você gerencia os dispositivos depende dos recursos do Intune que deseja usar.
Este tópico o ajudará a escolher qual método atende às suas necessidades.

Para gerenciar dispositivos que executam o iOS, o Mac OS X, o Android ou o Windows Phone, você deve *registrá-los*.

Para gerenciar computadores Windows, você tem duas opções:

1. Registrar o dispositivo **ou**
2. Instalar o *cliente de software do Intune*.

## <a name="decide-which-method-to-use"></a>Decidir qual método usar
Use este fluxo de decisão para decidir como registrar seus dispositivos gerenciados.

![Fluxo de decisão para registrar seus dispositivos gerenciados.](./media/choose-manage-method.png)

Inscrever os computadores Windows para obter o máximo de funcionalidade. No entanto, o cliente de software do Intune pode ser mais adequado às suas necessidades quando:

- O computador executa o Windows 7
- Você deseja gerenciar atualizações de software do Windows e o uso de licenças
- Você deseja gerenciar malware com o Endpoint Protection e o Firewall do Windows
- Para oferecer assistência remota aos usuários usando o software TeamViewer


Para obter uma lista detalhada dos recursos de gerenciamento que você obterá com cada método, veja [Recursos de gerenciamento de dispositivo móvel](mobile-device-management-capabilities-in-microsoft-intune.md) e [Recursos do cliente de software PC Intune](windows-pc-management-capabilities-in-microsoft-intune.md).
Para obter informações sobre os dispositivos e os computadores aos quais o Intune dá suporte, veja [Suporte para dispositivos móveis e computadores](/intune/get-started/supported-mobile-devices-and-computers)


## <a name="exchange-activesync-management"></a>Gerenciamento do Exchange ActiveSync
Além de registrar um dispositivo ou instalar o software cliente do Intune, você também pode gerenciar dispositivos [usando o Exchange ActiveSync](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune). Esse método requer que você instale o Conector Local ou use o Service to Service Connector interno para se conectar ao seu Exchange Server.
Embora essa seja uma terceira opção para gerenciar dispositivos, ela fornece um conjunto limitado de recursos de gerenciamento quando comparada aos outros métodos.


## <a name="next-steps"></a>Próximas etapas

- [Escolher como registrar dispositivos móveis](/intune/get-started/choose-how-to-enroll-devices1)
- [Gerenciar computadores Windows com o software cliente de computador do Intune](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune)



- [Gerenciamento de dispositivos móveis do Exchange ActiveSync com o Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).



<!--HONumber=Nov16_HO4-->


