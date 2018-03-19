---
title: "Ativar o modo perdido do iOS com o Microsoft Intune – Azure | Microsoft Docs"
description: "Ative ou inicie o Modo perdido para personalizar uma mensagem que será exibida na tela de bloqueio de um dispositivo iOS perdido ou roubado usando o Microsoft Intune. E obtenha detalhes sobre as informações de privacidade e segurança ao usar a ação de Modo perdido."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 47d6314dfaed546e5b4cff7f93a5540ba512bde9
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="enable-lost-mode-on-ios-devices-with-intune"></a>Habilitar o modo perdido em dispositivos iOS com o Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Modo perdido** ajuda você a habilitar o modo perdido em dispositivos iOS perdidos ou roubados. Este modo permite que você insira uma mensagem e um número de telefone que serão exibidos na tela de bloqueio do dispositivo. Para utilizar o modo perdido, é necessário um dispositivo iOS corporativo no modo supervisionado.

## <a name="supported-platforms"></a>Plataformas com Suporte

- iOS 9.3 e posterior

Esse recurso **não** é compatível com os seguintes sistemas: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="enable-lost-mode"></a>Habilitar o modo perdido

1. Entre no [portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre pelo **Intune** e selecione **Microsoft Intune**.
3. Selecione **Dispositivos** e, em seguida, selecione **Todos os dispositivos**.
4. Na lista de dispositivos gerenciados, escolha um dispositivo iOS, escolha **...Mais** e, em seguida, escolha a ação remota **Modo perdido**.
5. Em **Modo perdido**, habilite esse recurso. Em seguida, insira a mensagem a ser exibida e um número de telefone de contato.
6. Selecione **OK** para salvar suas alterações.

Quando você habilita o modo perdido, todo o uso do dispositivo é bloqueado. O usuário final não poderá acessar o dispositivo até que você desative o modo perdido. Enquanto o modo perdido estiver habilitado, use a ação [Localizar dispositivo](device-locate.md) para localizar o dispositivo.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informações sobre segurança e privacidade para o modo perdido e ações para localizar o dispositivo
- Nenhuma informação do local do dispositivo será enviada para o Intune até que essa ação seja ativada.
- Quando você usa a ação para localizar o dispositivo, as coordenadas da latitude e longitude do dispositivo são enviadas para o Intune e exibidas no portal do Azure.
- Os dados são armazenados por 24 horas, então, removidos. Você não pode remover manualmente os dados de localização.
- Os dados de localização são criptografados, enquanto estão armazenados e enquanto estão sendo transmitidos.
- Na mensagem que você inserir para ser exibida na tela de bloqueio, inclua detalhes específicos para que o dispositivo perdido seja devolvido.

## <a name="next-steps"></a>Próximas etapas

Para ver o status de habilitação do modo perdido, abra **Dispositivos** e selecione **Ações do dispositivo**.