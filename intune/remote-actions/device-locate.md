---
title: Localizar dispositivos iOS perdidos com Microsoft Intune – Azure | Microsoft Docs
description: Localize dispositivos iOS perdidos ou roubados usando o recurso de localizar dispositivo no Microsoft Intune. Obtenha detalhes sobre as informações de privacidade e de segurança ao usar a ação do dispositivo localizar.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/24/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 817f46558932c074abc37b45d2885496419a0db0
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "73712418"
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Localizar dispositivos iOS perdidos ou roubados com o Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Para obter a localização de um dispositivo iOS perdido ou roubado em um mapa, use a ação **Localizar dispositivo**. O dispositivo deve estar no modo supervisionado. Antes de usar essa ação, verifique se o dispositivo está no [modo perdido](device-lost-mode.md).

## <a name="supported-platforms"></a>Plataformas com Suporte

- iOS 9.3 e posterior

Esse recurso não é compatível com os seguintes sistemas: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="locate-a-lost-or-stolen-device"></a>Localizar um dispositivo perdido ou roubado

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecione **Dispositivos** e, em seguida, **Todos os dispositivos**.
4. Na lista de dispositivos gerenciados, escolha um dispositivo iOS e **...Mais**. Em seguida, escolha a ação remota **Localizar dispositivo**.
5. Depois que o dispositivo for localizado, a localização será mostrada em **Localizar dispositivo**.
    ![Captura de tela de Localizar dispositivo usando o Intune no Azure](./media/device-locate/locate-device.png)


## <a name="activate-lost-mode-sound-alert-on-an-ios-device"></a>Ativar alerta sonoro de modo perdido em um dispositivo iOS

Se alguém tiver perdido um dispositivo iOS 9.3 ou posterior, você poderá disparar remotamente o dispositivo para tocar um som de alerta para que o usuário possa localizá-lo. O dispositivo deve estar no [modo perdido](device-lost-mode.md).

No [Intune no portal do Azure](https://aka.ms/intuneportal), escolha **Dispositivos** > **Todos os dispositivos** > selecione um dispositivo iOS > **Visão Geral**  >  **Mais** > **Tocar som do modo Perdido (somente supervisionar)** .

O som continuará a ser executado até que o usuário o desabilite no dispositivo ou o dispositivo seja removido do modo perdido.


## <a name="security-and-privacy-information-for-lost-mode-and-locate-device-actions"></a>Informações de segurança e privacidade para as ações de modo perdido e de localização do dispositivo
- Nenhuma informação do local do dispositivo será enviada para o Intune até que essa ação seja ativada.
- Quando você usa a ação de localização do dispositivo, as coordenadas de latitude e longitude do dispositivo podem ser recuperadas com a API do Graph.
- Os dados são armazenados por 24 horas, então, removidos. Você não pode remover manualmente os dados de localização.
- Os dados de localização são criptografados, enquanto estão armazenados e enquanto estão sendo transmitidos.
- Ao configurar o modo perdido, é possível personalizar uma mensagem que aparecerá na tela de bloqueio. Para ajudar a pessoa que encontrar o dispositivo, inclua nessa mensagem detalhes específicos para que o dispositivo perdido seja devolvido.

## <a name="next-steps"></a>Próximas etapas

Para ver o status de habilitação de localizar dispositivo, abra **Dispositivos** e selecione **Ações do dispositivo**.
