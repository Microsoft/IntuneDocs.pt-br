---
title: Renomear um dispositivo com o Microsoft Intune – Azure | Microsoft Docs
description: Renomeie um dispositivo usando o Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 11b339a3e94e60db43e8237d9f3d2c729b48a57d
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77413605"
---
# <a name="rename-a-device-in-intune"></a>Renomear um dispositivo no Intune

A ação **Renomear dispositivo** possibilita renomear um dispositivo registrado no Intune. O nome do dispositivo é alterado no Intune e no dispositivo.

É possível renomear os seguintes tipos de dispositivos:
- Windows de propriedade corporativa 
- iOS/iPadOS supervisionado
- MacOS 10 de propriedade corporativa

No momento, esse recurso não dá suporte à renomeação de dispositivos Windows do Azure AD híbrido.

## <a name="rename-a-device"></a>Renomear um dispositivo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Escolha **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Mais** > **Renomear dispositivo**.
4. Na folha **Renomear dispositivo**, digite o novo nome na caixa de texto. Use letras, números e hifens. O nome deve conter pelo menos uma letra ou um hífen.
5. Se você quiser reiniciar o dispositivo após renomeá-lo, escolha **Sim** ao lado de **Reinicializar após a renomeação**.
6. Escolha **Renomear**.

## <a name="windows-device-rename-rules"></a>Regras de renomeação de dispositivo Windows
Ao renomear um dispositivo Windows, o novo nome deve seguir estas regras:
- 15 caracteres ou menos (deve ser menor ou igual a 63 bytes, não incluindo NULL à direita)
- Não nulo ou uma cadeia de caracteres vazia
- ASCII permitidos: Letras (a-z, A-Z), números (0-9) e hifens
- Unicode permitidos: caracteres >= 0x80, deve ser UTF8 válido, deve ser mapeável para IDN (ou seja, RtlIdnToNameprepUnicode é bem-sucedido; confira RFC 3492)
- Os nomes não devem conter apenas números
- Sem espaços no nome
- Caracteres não permitidos: { | } ~ [ \ ] ^ ' : ; < = > ? & @ ! " # $ % ` ( ) + / , . _ *)


## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação **Renomear** dispositivo, verifique a página **Visão geral** do dispositivo.
