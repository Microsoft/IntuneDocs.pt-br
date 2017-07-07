---
title: Ativar modo perdido do iOS com o Intune
titleSuffix: Intune on Azure
description: Saiba como usar o Intune para ativar o modo perdido em dispositivos iOS perdidos ou roubados.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a34d008ae76355578c6f24a932c9e1e501d5b46b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="activate-lost-mode-on-ios-devices"></a>Ativar modo perdido em dispositivos iOS


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Modo perdido** ajuda você a habilitar o modo perdido em dispositivos iOS perdidos ou roubados. Esse modo permite especificar uma mensagem e um número de telefone que serão exibidos na tela de bloqueio do dispositivo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo iOS e, em seguida, escolha a ação remota **Modo perdido**.
6. Na folha **Modo perdido**, ative o modo perdido, digite a mensagem que será exibida e, opcionalmente, um número de telefone de contato.
7. Clique em **OK**.

Quando você ativa o modo perdido, bloqueia todo o uso do dispositivo. O usuário final não poderá acessar o dispositivo até que você desative o modo perdido. Enquanto o modo perdido estiver habilitado, você poderá usar a ação **Localizar dispositivo** para descobrir onde está o dispositivo.
Para usar o modo perdido, o dispositivo deve ser um dispositivo iOS corporativo, inscrito pelo DEP e estar no modo supervisionado.

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informações sobre segurança e privacidade para o modo perdido e ações para localizar o dispositivo
- Nenhuma informação do local do dispositivo será enviada para o Intune até que você ative esta ação.
- Quando você usa a ação para localizar o dispositivo, as coordenadas da latitude e longitude do dispositivo são enviadas para o Intune e exibidas no portal do Azure.
- Os dados são armazenados por 24 horas, então, removidos. Você não pode remover manualmente os dados de localização.
- Os dados de localização são criptografados, enquanto estão armazenados e enquanto estão sendo transmitidos.
- Ao configurar o modo perdido, recomendamos que a mensagem inserida para exibição na tela de bloqueio inclua informações que ajudam a pessoa que encontrar o dispositivo a devolvê-lo.

