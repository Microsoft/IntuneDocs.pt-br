---
title: Ativar modo perdido do iOS com o Intune
titlesuffix: Azure portal
description: Saiba como usar o Intune para ativar o modo perdido em dispositivos iOS perdidos ou roubados.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fcdd5e6fa844d4c475462cd0b2a4883f8ff9ba90
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2018
---
# <a name="activate-lost-mode-on-ios-devices"></a>Ativar modo perdido em dispositivos iOS


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Modo perdido** ajuda você a habilitar o modo perdido em dispositivos iOS perdidos ou roubados. Esse modo permite especificar uma mensagem e um número de telefone exibidos na tela de bloqueio do dispositivo.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Sem suporte
- Windows Phone – Sem suporte
- iOS – Com suporte no iOS 9.3 e versões posteriores, supervisionado e corporativo
- macOS – Sem suporte
- Android – Sem suporte

## <a name="how-to-activate-lost-mode"></a>Como ativar o modo perdido

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo iOS, escolha **...Mais** e, em seguida, escolha a ação remota **Modo perdido**.
6. Na folha **Modo perdido**, habilite o modo perdido. Em seguida, insira a mensagem a ser exibida e, como alternativa, um número de telefone de contato.
7. Clique em **OK**.

Quando você ativa o modo perdido, bloqueia todo o uso do dispositivo. O usuário final não poderá acessar o dispositivo até que você desative o modo perdido. Enquanto o modo perdido estiver habilitado, você poderá usar a ação **Localizar dispositivo** para descobrir onde está o dispositivo.
Para utilizar o modo perdido, é necessário um dispositivo iOS corporativo no modo supervisionado.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informações sobre segurança e privacidade para o modo perdido e ações para localizar o dispositivo
- Nenhuma informação do local do dispositivo será enviada para o Intune até que essa ação seja ativada.
- Quando você usa a ação para localizar o dispositivo, as coordenadas da latitude e longitude do dispositivo são enviadas para o Intune e exibidas no portal do Azure.
- Os dados são armazenados por 24 horas, então, removidos. Você não pode remover manualmente os dados de localização.
- Os dados de localização são criptografados, enquanto estão armazenados e enquanto estão sendo transmitidos.
- Recomendamos que a mensagem inserida para exibição na tela de bloqueio inclua informações que ajudem a pessoa que encontrar o dispositivo a devolvê-lo.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos**, escolha **Ações do dispositivo**.

