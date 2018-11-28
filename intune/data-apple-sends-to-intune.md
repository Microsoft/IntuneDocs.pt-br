---
title: Dados enviados pela Apple ao Intune
titleSuffix: Microsoft Intune
description: Lista de dados que a Apple envia para o Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cf27fdb8-f408-425c-9a7c-146de1534425
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 12f9b6aa5fb9a7b1f31b43dc7faf3e36cdd49157
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186538"
---
# <a name="data-apple-sends-to-intune"></a>Dados enviados pela Apple ao Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Quando qualquer um dos seguintes serviços da Apple está habilitado em um dispositivo, o Microsoft Intune estabelece uma conexão com a Apple para compartilhar informações do usuário e do dispositivo:

- [DEP (Programa de registro de dispositivos) da Apple](device-enrollment-program-enroll-ios.md)
- [Apple MDM Push Certificate (APNs)](apple-mdm-push-certificate-get.md)
- [ASM (Apple School Manager)](https://docs.microsoft.com/schooldatasync/apple-school-manager-integration-with-intune-for-education-and-school-data-sync)
- [VPP (Apple Volume Purchase Program)](vpp-apps-ios.md)

Antes que o Microsoft Intune estabeleça uma conexão, você deve criar uma conta da Apple para cada um dos serviços de Apple.

A tabela a seguir lista os dados que um dispositivo da Apple envia ao Intune. [O Intune também envia dados à Apple](data-intune-sends-to-apple.md). 

| Serviço | Mensagem | Dados enviados ao Intune | Usada para |
|:---:|:---:|:---:| ---|
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Autenticar | MessageType | O tipo de mensagem: autenticar. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Autenticar | Tópico | O tópico que o dispositivo escutará. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Autenticar | MesUDID | A UDID dos dispositivos. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Autenticar | OSVersion | Versão do sistema operacional do dispositivo. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Autenticar | BuildVersion | Versão da compilação do dispositivo. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Autenticar | ProductName | Nome do produto do dispositivo. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Autenticar | SerialNumber | Número de série do dispositivo. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Autenticar | IMEI | A identidade da estação internacional do equipamento móvel. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Autenticar | MEID | O identificador de equipamentos móveis do dispositivo |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | Tópico | O tópico que o dispositivo escutará. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | UDID | A UDID do dispositivo. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | Token | O token de push para o dispositivo. O servidor deve usar esse token atualizado ao enviar notificações por push ao dispositivo. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | PushMagic | A cadeia de caracteres mágica que deve ser incluída na mensagem de notificação por push.  |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | UnlockToken | Um blob de dados que pode ser usado para se desbloquear o dispositivo. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | AwaitingConfiguration | Se definido como verdadeiro, o dispositivo está aguardando um comando de MDM de DeviceConfigured antes de continuar por meio do Assistente de configuração.  |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Check-out | MessageType | O tipo de mensagem: check-out. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Check-out | Tópico | O tópico que o dispositivo escutará. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Check-out | UDID | A UDID do dispositivo |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Protocolo de MDM | Status | Status.  |
| [APNS](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Protocolo de MDM | UDID |A UDID do dispositivo.  |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Protocolo de MDM | CommandUUID | UUID do comando ao qual se destina essa resposta. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Protocolo de MDM | ErrorChain | Matriz de dicionários que representam a cadeia de erros ocorridos.  |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | Número de série | Número de série do dispositivo. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | modelo | Nome do modelo do dispositivo. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | Descrição | Uma descrição do dispositivo. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | Cor | A cor do dispositivo. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | Marca de ativo | A marca de ativo do dispositivo. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | Status do perfil | O status da instalação do perfil. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | UUID do perfil | A UUID do perfil atribuído. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | Hora de atribuição do perfil | Um carimbo de data/hora no formato ISO 8601 que indica quando um perfil foi atribuído ao dispositivo. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | Hora de envio do perfil | Um carimbo de data/hora no formato ISO 8601 que indica quando um perfil foi enviado ao dispositivo.|
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | Data de atribuição do dispositivo | Um carimbo de data/hora no formato ISO 8601 que indica quando o dispositivo foi registrado no programa de registro de dispositivos. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | Data de atribuição do dispositivo | O email da pessoa que atribuiu o dispositivo. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | SO | O sistema operacional do dispositivo. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token do Programa de Registro | Família de dispositivos | Família de produtos de Apple do dispositivo. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | ID de usuário da Apple | Uma ID de usuário gerada pela Apple. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | descrição do aplicativo | A descrição de um aplicativo VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | ícone do aplicativo | A URL de um ícone hospedado pela Apple para um aplicativo VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | ID do Aplicativo | ID do aplicativo da Apple, também conhecido como adamsId. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | nome do aplicativo | O nome de um aplicativo VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | assignedCount | O número de licenças atribuídas para um aplicativo. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | availableCount | O número de licenças não atribuídas para um aplicativo. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | bundleId | A bundleId de um aplicativo. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | direitos autorais | As informações de direitos autorais de um aplicativo. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | CountryCode | O código do país de um programa VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | deviceAssignable | A Apple retorna verdadeiro se o administrador puder atribuir uma licença de dispositivo para um aplicativo. Por fim, é retornado falso. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | facilitatorMemberId | A ID de membro de um facilitador de conta VPP.  |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | gêneros | Os gêneros de um aplicativo. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | GUID de UserId do Intune | A GUID gerada pelo Intune. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | isIrrevocable | A Apple retorna verdadeiro se a licença não puder ser revogada. Se for possível revogá-la, retornar-se-á falso. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | ID da licença | A ID gerada pela Apple para identificar uma licença específica. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | Local | Local armazenado em dados de configuração VPP da Apple. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | UPN de AppleId gerenciada | O email da AppleID para membro facilitador, administrador e usuário. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | OrganizationId | A ID da organização atribuída à Apple. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | pricingParam | O tipo de preço da Apple para um aplicativo. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | productType | O tipo de produto de um aplicativo VPP. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | retiredCount | O número de licenças desativadas para um aplicativo. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | totalCount | O número total de licenças adquiridas para um aplicativo. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | url | A URL de armazenamento do iTunes de um aplicativo.|
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Token VPP da Apple | Status do usuário | O status do usuário em programas VPP da Apple. |


Para parar de usar serviços da Apple com o Microsoft Intune e excluir os dados, você deve desabilitar o token da Apple do Microsoft Intune e também excluir a sua conta da Apple. Consulte a conta da Apple para saber como executar o gerenciamento de contas.


