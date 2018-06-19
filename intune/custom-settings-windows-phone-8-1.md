---
title: Configurações personalizadas do Microsoft Intune para dispositivos que executam o Windows Phone 8.1
titleSuffix: ''
description: Conheça as configurações que você pode usar em um perfil personalizado do Windows Phone 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b21464016dff3396b25861af568fa90d8b7a260f
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31834746"
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-phone-81"></a>Configurações personalizadas de dispositivo do Microsoft Intune para dispositivos que executam o Windows Phone 8.1

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use o perfil **Personalizado** do Microsoft Intune no Windows Phone 8.1 para atribuir configurações OMA-URI, que podem ser usadas para controlar recursos em dispositivos Windows Phone 8.1. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade vida permitir que você atribua definições não configuráveis com outras políticas do Intune.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Configurações de política personalizadas para dispositivos Windows Phone 8.1

1. Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.
2. No painel **Configurações personalizadas de OMA-URI**, escolha **Adicionar** para adicionar uma ou mais configurações de OMA-URI.
3. No painel **Adicionar Linha**, defina os seguintes valores para cada configuração:
    - **Nome** – Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.
    - **Descrição** – Forneça uma descrição que proporciona uma visão geral da configuração e outras informações relevantes que ajudarão a localizá-la.
    - **OMA-URI** – Especifique o OMA-URI para o qual você deseja fornecer uma configuração.
    - **Tipo de dados** – Selecione o tipo de dados no qual você especificará essa configuração de OMA-URI. Escolha entre **Cadeia de caracteres**, **Cadeia de caracteres (XML)**, **Data e hora**, **Inteiro**, **Ponto flutuante**, **Booliano** ou **Base64**.
    - **Valor** – Insira o valor ou arquivo que você deseja associar ao OMA-URI inserido.

4. Clique em **OK** quando terminar e continue a adicionar mais configurações conforme necessário.
