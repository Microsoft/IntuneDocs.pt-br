---
title: Localizar dispositivos iOS perdidos com Microsoft Intune – Azure | Microsoft Docs
description: Localize dispositivos iOS perdidos ou roubados usando o recurso de localizar dispositivo no Microsoft Intune. Obtenha detalhes sobre as informações de privacidade e de segurança ao usar a ação do dispositivo localizar.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da8bb19db8c2da2d5854c3f991ccce4d124d594c
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Localizar dispositivos iOS perdidos ou roubados com o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Para obter a localização de um dispositivo iOS perdido ou roubado em um mapa, use a ação **Localizar dispositivo**. O dispositivo precisa ser um dispositivo iOS corporativo, registrado por meio do programa de registro de dispositivos e estar no modo supervisionado. Antes de usar essa ação, verifique se o dispositivo está no [modo perdido](device-lost-mode.md).

## <a name="supported-platforms"></a>Plataformas com Suporte

- iOS 9.3 e posterior

Esse recurso não é compatível com os seguintes sistemas: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="locate-a-lost-or-stolen-device"></a>Localizar um dispositivo perdido ou roubado

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Dispositivos** e, em seguida, **Todos os dispositivos**.
4. Na lista de dispositivos gerenciados, escolha um dispositivo iOS e **...Mais**. Em seguida, escolha a ação remota **Localizar dispositivo**.
5. Depois que o dispositivo for localizado, a localização será mostrada em **Localizar dispositivo**.
    ![Captura de tela de Localizar dispositivo usando o Intune no Azure](./media/locate-device.png)

>[!NOTE]
>Por motivos de privacidade, a distância de ampliação do zoom do mapa é limitada.

## <a name="security-and-privacy-information-for-lost-mode-and-locate-device-actions"></a>Informações de segurança e privacidade para as ações de modo perdido e de localização do dispositivo
- Nenhuma informação do local do dispositivo será enviada para o Intune até que essa ação seja ativada.
- Quando você usa a ação do dispositivo localizar, as coordenadas da latitude e de longitude do dispositivo são enviadas para o Intune e mostradas no portal do Azure.
- Os dados são armazenados por 24 horas, então, removidos. Você não pode remover manualmente os dados de localização.
- Os dados de localização são criptografados, enquanto estão armazenados e enquanto estão sendo transmitidos.
- Ao configurar o modo perdido, é possível personalizar uma mensagem que aparecerá na tela de bloqueio. Para ajudar a pessoa que encontrar o dispositivo, inclua nessa mensagem detalhes específicos para que o dispositivo perdido seja devolvido.

## <a name="next-steps"></a>Próximas etapas

Para ver o status de habilitação de localizar dispositivo, abra **Dispositivos** e selecione **Ações do dispositivo**.
