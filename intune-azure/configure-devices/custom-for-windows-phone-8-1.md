---
title: "Configurações personalizadas do Intune para dispositivos Windows Phone 8.1 | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: aprenda sobre as configurações que você pode usar em um perfil personalizado do Windows Phone 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: 3656db2d9828dcc16c479ba072de691848fdd23b


---

# <a name="custom-settings-for-windows-phone-81-devices-in-intune-azure-preview"></a>Configurações personalizadas para dispositivos Windows Phone 8.1 na versão prévia do Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Use o perfil **Personalizado** do Microsoft Intune no Windows Phone 8.1 para implantar configurações OMA-URI, que podem ser usadas para controlar recursos em dispositivos Windows Phone 8.1. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade vida permitir que você implante definições não configuráveis com outras políticas do Intune.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Configurações de política personalizadas para dispositivos Windows Phone 8.1

1. Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](how-to-configure-custom-settings.md) para começar.
2. Na folha **Criar Perfil**, escolha **Configurações** para adicionar uma ou mais configurações OMA-URI.
3. Na folha **Adicionar Linha**, defina os seguintes valores para cada configuração:
    - **Nome** – Insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.
    - **Descrição** – Forneça uma descrição que proporciona uma visão geral da configuração e outras informações relevantes que ajudarão a localizá-la.
    - **OMA-URI** – Especifique o OMA-URI para o qual você deseja fornecer uma configuração.
    - **Tipo de dados** – Selecione o tipo de dados em que você especificará essa configuração de OMA-URI. Escolha entre **Cadeia de caracteres**, **Data e hora**, **Inteiro**, **Ponto flutuante** ou **Booliano**.
    - **Valor** – Especifique o valor que você deseja associar ao OMA-URI inserido.

4. Clique em **OK** quando terminar e continue a adicionar mais configurações conforme necessário.



<!--HONumber=Feb17_HO1-->


