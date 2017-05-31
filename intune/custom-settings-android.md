---
title: "Configurações personalizadas do Intune para dispositivos Android"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba as configurações que você pode usar em um perfil personalizado do Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ff3d3b1596f58213bed2509b1bfd5ae81c63f440
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Configurações personalizadas para dispositivos Android no Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Use o perfil **Personalizado** do Android do Microsoft Intune para atribuir configurações OMA-URI, que podem ser usadas para controlar recursos em dispositivos Android. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade destina-se a permitir que você atribua configurações do Android que não são configuráveis com as políticas do Intune.

## <a name="custom-profile-settings-for-android-devices"></a>Configurações de perfil personalizadas para dispositivos Android

1. Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.
2. Na folha **Criar Perfil**, escolha **Configurações** para adicionar uma ou mais configurações OMA-URI.
3. Na folha **Editar Linha**, defina os seguintes valores para cada configuração:
    - **Nome** – Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.
    - **Descrição** – Forneça uma descrição que proporciona uma visão geral da configuração e outras informações relevantes que ajudarão a localizá-la.
    - **Tipo de dados** – Selecione o tipo de dados em que você especificará essa configuração de OMA-URI. Escolha dentre **Cadeia de caracteres**, **Cadeia de caracteres (XML)**, **Data e hora**, **Inteiro**, **Ponto flutuante** ou **Booliano**.
    - **OMA-URI** – Especifique o OMA-URI para o qual você deseja fornecer uma configuração.
    - **Valor** – Especifique o valor que você deseja associar ao OMA-URI inserido.
4. Clique em **OK** quando terminar e continue a adicionar mais configurações conforme necessário.

