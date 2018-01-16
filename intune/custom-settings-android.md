---
title: "Configurações personalizadas do Intune para dispositivos Android"
titleSuffix: Azure portal
description: "Conheça as configurações que você pode usar em um perfil personalizado do Android."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b1ccb3b0b7b2ce024ff6a09d7f9d8366896fb67
ms.sourcegitcommit: 5004b9564915712b41860df20324f39fac3dc27d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/03/2018
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Configurações personalizadas para dispositivos Android no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use o perfil **Personalizado** do Android do Microsoft Intune para atribuir configurações OMA-URI, que podem ser usadas para controlar recursos em dispositivos Android. Essas são configurações padrão que muitos fabricantes de dispositivos móveis usam para controlar recursos dos dispositivos.

Essa funcionalidade destina-se a permitir que você atribua as configurações do Android a seguir, que não são configuráveis com as políticas do Intune:

- [Usar um perfil de dispositivo personalizado do Microsoft Intune para criar um perfil de Wi-Fi com uma chave pré-compartilhada](/intune/wi-fi-profile-shared-key)
- [Usar um perfil personalizado do Microsoft Intune para criar um perfil de VPN por aplicativo para dispositivos Android](/intune/android-pulse-secure-per-app-vpn)
- [Usar políticas personalizadas para permitir e bloquear aplicativos para dispositivos Samsung Knox Standard no Microsoft Intune](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
>Somente as configurações listadas acima podem ser configuradas no momento por esse tipo de perfil. Dispositivos Android não expõem uma lista completa das configurações OMA-URI que você pode configurar. Se você quiser ver mais configurações adicionadas, solicite-as no [site Intune Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas).

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

## <a name="next-steps"></a>Próximas etapas

Ao concluir as configurações, o perfil será criado e aparecerá na folha da lista de perfis. Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).




