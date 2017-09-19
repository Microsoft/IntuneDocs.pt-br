---
title: "Configurações personalizadas do Intune para dispositivos Windows Phone 8.1"
titleSuffix: Azure portal
description: "Conheça as configurações que você pode usar em um perfil personalizado do Windows Phone 8.1."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2fa0a944c70e9749a9ac1c7e2b3341660000072c
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
---
# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Configurações personalizadas para dispositivos Windows Phone 8.1 no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use o perfil **Personalizado** do Microsoft Intune no Windows Phone 8.1 para atribuir configurações OMA-URI, que podem ser usadas para controlar recursos em dispositivos Windows Phone 8.1. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade vida permitir que você atribua definições não configuráveis com outras políticas do Intune.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Configurações de política personalizadas para dispositivos Windows Phone 8.1

1. Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.
2. Na folha **Criar Perfil**, escolha **Configurações** para adicionar uma ou mais configurações OMA-URI.
3. Na folha **Adicionar Linha**, defina os seguintes valores para cada configuração:
    - **Nome** – Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.
    - **Descrição** – Forneça uma descrição que proporciona uma visão geral da configuração e outras informações relevantes que ajudarão a localizá-la.
    - **OMA-URI** – Especifique o OMA-URI para o qual você deseja fornecer uma configuração.
    - **Tipo de dados** – Selecione o tipo de dados em que você especificará essa configuração de OMA-URI. Escolha entre **Cadeia de caracteres**, **Data e hora**, **Inteiro**, **Ponto flutuante** ou **Booliano**.
    - **Valor** – Especifique o valor que você deseja associar ao OMA-URI inserido.

4. Clique em **OK** quando terminar e continue a adicionar mais configurações conforme necessário.
