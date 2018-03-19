---
title: "Localizar dispositivos iOS perdidos com Microsoft Intune – Azure | Microsoft Docs"
description: "Encontre ou localize dispositivos iOS perdidos ou roubados usando o recurso Localizar Dispositivo no Microsoft Intune, além disso, obtenha detalhes sobre as informações de privacidade e segurança ao usar a ação Localizar Dispositivo."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4bc51ef7f9af9cc97fd4c11408a1857679aee665
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Localizar dispositivos iOS perdidos ou roubados com o Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Para obter a localização de um dispositivo iOS perdido ou roubado em um mapa, use a ação **Localizar Dispositivo**. O dispositivo precisa ser um dispositivo iOS corporativo, registrado por meio do DEP (Programa de registro de dispositivos) e estar no modo supervisionado. Antes de usar essa ação, verifique se o dispositivo está no [modo perdido](device-lost-mode.md).

## <a name="supported-platforms"></a>Plataformas com Suporte

- iOS 9.3 e posterior

Esse recurso **não** é compatível com os seguintes sistemas: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="locate-a-lost-or-stolen-device"></a>Localizar um dispositivo perdido ou roubado

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre pelo **Intune** e selecione **Microsoft Intune**.
3. Selecione **Dispositivos** e, em seguida, selecione **Todos os dispositivos**.
4. Na lista de dispositivos gerenciados, escolha um dispositivo iOS, escolha **...Mais** e, em seguida, escolha a ação remota **Localizar dispositivo**.
5. Depois que o dispositivo for localizado, a localização será exibida em **Localizar dispositivo**.
    ![Localizar o dispositivo usando o Intune no Azure](./media/locate-device.png)

>[!NOTE]
>Para fins de privacidade, a distância de ampliação do zoom do mapa é limitada.

## <a name="security-and-privacy-information-for-lost-mode-and-locate-device-actions"></a>Informações de segurança e privacidade para as ações de modo perdido e de localização do dispositivo
- Nenhuma informação do local do dispositivo será enviada para o Intune até que essa ação seja ativada.
- Quando você usa a ação para localizar o dispositivo, as coordenadas da latitude e longitude do dispositivo são enviadas para o Intune e exibidas no portal do Azure.
- Os dados são armazenados por 24 horas, então, removidos. Você não pode remover manualmente os dados de localização.
- Os dados de localização são criptografados, enquanto estão armazenados e enquanto estão sendo transmitidos.
- Ao configurar o modo perdido, é possível personalizar uma mensagem que será exibida na tela de bloqueio. Para ajudar a pessoa que encontrar o dispositivo, inclua nessa mensagem detalhes específicos para que o dispositivo perdido seja devolvido.

## <a name="next-steps"></a>Próximas etapas

Para ver o status de habilitação de Localizar Dispositivo, abra **Dispositivos** e selecione **Ações do dispositivo**.
