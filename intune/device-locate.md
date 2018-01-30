---
title: Localizar dispositivos iOS perdidos com o Intune
titlesuffix: Azure portal
description: Saiba como localizar dispositivos iOS perdidos ou roubados com o Intune.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 90b1321c0df49f446bfdeccbacdfd5642396dacd
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Localizar dispositivos iOS perdidos ou roubados com o Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Localizar Dispositivo** exibe a localização de um dispositivo iOS perdido ou roubado em um mapa. O dispositivo deve ser um dispositivo iOS corporativo, inscrito pelo DEP e estar no modo supervisionado. Antes de usar essa ação, o dispositivo deve ter sido colocado no [modo perdido](/intune-azure/manage-devices/lost-mode.md).

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Sem suporte
- Windows Phone – Sem suporte
- iOS – Com suporte no iOS 9.3 e versões posteriores (no modo perdido), supervisionado e corporativo
- macOS – Sem suporte
- Android – Sem suporte

## <a name="how-to-locate-a-lost-or-stolen-device"></a>Como localizar um dispositivo perdido ou roubado

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo iOS e, em seguida, escolha a ação remota **Localizar Dispositivo**.
6. Depois do dispositivo ser localizado, o local será exibido na folha **Localizar dispositivo**.
    ![Folha Localizar dispositivo](./media/locate-device.png)

>[!NOTE]
>Para fins de privacidade, a distância de ampliação do zoom do mapa é limitada.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informações sobre segurança e privacidade para o modo perdido e ações para localizar o dispositivo
- Nenhuma informação do local do dispositivo será enviada para o Intune até que você ative esta ação.
- Quando você usa a ação para localizar o dispositivo, as coordenadas da latitude e longitude do dispositivo são enviadas para o Intune e exibidas no portal do Azure.
- Os dados são armazenados por 24 horas, então, removidos. Você não pode remover manualmente os dados de localização.
- Os dados de localização são criptografados, enquanto estão armazenados e enquanto estão sendo transmitidos.
- Ao configurar o modo perdido, recomendamos que a mensagem inserida para exibição na tela de bloqueio inclua informações que ajudam a pessoa que encontrar o dispositivo a devolvê-lo.


## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.