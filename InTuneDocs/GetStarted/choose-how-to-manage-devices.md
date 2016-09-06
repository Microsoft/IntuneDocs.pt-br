---
title: Escolher como gerenciar dispositivos | Microsoft Intune
description: Saiba mais sobre as diferentes maneiras de registrar e gerenciar dispositivos.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c329bd08aaf72ae2acaa03dcb12c911d84b46b4e
ms.openlocfilehash: cfd9df3814d0d306a254a5566155a91ce5d0ca16


---

# Escolha como gerenciar dispositivos
O Intune permite que você gerencie uma variedade de dispositivos *registrando-os* no serviço. Os usuários podem usar um *portal da empresa* para executar uma variedade de operações como registrar seu dispositivo, procurar e instalar aplicativos, certificar-se de seu dispositivo é compatível com as políticas da empresa e entrar em contato com seu suporte de TI.

## Maneiras de gerenciar dispositivos móveis
O Intune pode gerenciar as seguintes plataformas de dispositivo:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

> [!NOTE]
> Se você tiver registrado anteriormente dispositivos que executam uma versão anterior do iOS que a versão com suporte, os dispositivos permanecerão registrados. Consulte a documentação para confirmar se o recurso dá suporte a essa versão do iOS.

O Intune pode gerenciar os dispositivos dos usuários, popularmente conhecidos como “BYOD” (traga seu próprio dispositivo). Ele também pode gerenciar dispositivos da empresa, incluindo cenários em que a empresa oferece uma lista de dispositivos entre os quais os usuários podem escolher, conhecido como "escolha o seu próprio dispositivo" (CYOD).

### Registrando dispositivos no gerenciamento
Para sistemas operacionais de dispositivos móveis, incluindo iOS, Android e Windows Phone, você sempre deve registrar dispositivos. A forma como você registra os dispositivos depende das necessidades da sua organização:

|Tipo de registro|BYOD|CYOD|Dispositivo compartilhado com conta do gerente|Dispositivo compartilhado sem conta de usuário|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Descrição**|Dispositivo pessoal registrado usando o Microsoft Intune|Dispositivo corporativo para usuário único|Dispositivo corporativo gerenciado usando uma conta de gerente compartilhada por vários usuários|Dispositivo corporativo sem usuário usado por muitos usuários.|
|**Usuário do dispositivo**|Proprietário|Usuário atribuído|Nenhuma conta de usuário específica|Nenhum usuário específico|
|**Quem registra?**|Proprietário|Administrador|Gerenciador de Dispositivos|Qualquer pessoa|
|**Quem cancela o registro?**|Proprietário ou administrador|Plataforma |Administrador ou usuário|Administrador ou usuário|
|**Quem pode redefinir?**|Proprietário ou administrador|Administrador|Administrador|Administrador|

Para obter mais orientações, consulte [escolher como registrar dispositivos móveis](/intune/get-started/choose-how-to-enroll-devices1).

> [!NOTE]
> Consulte [Mobile device management capabilities](mobile-device-management-capabilities-in-microsoft-intune.md) (Funcionalidades de gerenciamento de dispositivos móveis) para obter uma lista completa das funcionalidades que o registro dos dispositivos fornece.

## Maneiras de gerenciar computadores Windows
O Intune pode gerenciar computadores Windows Vista e computadores Windows posteriores usando o cliente de computador do Intune. No entanto, para computadores Windows, você pode escolher entre registrá-los ou instalar software cliente do computador do Intune, que oferece algumas funcionalidades indisponíveis ao registrar dispositivos. Na maioria dos cenários, você registrará o dispositivo Windows no Intune, o que proporciona um conjunto maior de funcionalidades que o cliente do computador.

Considere usar o cliente do computador do Intune quando desejar:

- usar qualquer uma das funcionalidades habilitadas do cliente do computador do Microsoft Intune para gerenciar seus computadores Windows
- gerenciar um computador Windows que executa um sistema operacional que não tem suporte para registro

> [!NOTE]
> Consulte [Windows PC management capabilities](windows-pc-management-capabilities-in-microsoft-intune.md) (Funcionalidades de gerenciamento do computador Windows) encontrar uma lista completa das funcionalidades que a instalação do cliente do computador do Intune em computadores Windows com suporte fornece.

## Gerenciamento do Exchange ActiveSync
Você também pode gerenciar dispositivos usando o Exchange ActiveSync. Isso requer que você instale o On-Premises Connector ou use o Service to Service Connector interno para se conectar ao seu Exchange Server.

Para saber mais sobre os requisitos de hardware e software para instalar o On-Premises Connector, consulte [Requirements for the On-Premises Connector](/intune/deploy-use/intune-on-premises-exchange-connector#requirements-for-the-on-premises-connector) (Requisitos para o On-Premises Connector).

Para saber mais sobre como usar o On-Premises Connector ou o Service to Service Connector com o Exchange, consulte [Mobile device management with Exchange ActiveSync and Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) (Gerenciamento de dispositivo móvel com o Exchange ActiveSync e o Microsoft Intune).



## Próximas etapas
Agora, você descobriu algumas das funcionalidades que podem ser usadas ao registrar seus dispositivos com [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Em seguida, você precisará [registrar seus dispositivos](/intune/deploy-use/enroll-devices-in-microsoft-intune). Após ter registrado seus dispositivos, você pode aproveitar todas as funcionalidades sobre as quais leu nesse tópico. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->



<!--HONumber=Aug16_HO3-->


