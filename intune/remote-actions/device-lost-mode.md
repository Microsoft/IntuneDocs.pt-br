---
title: Ativar o modo perdido do iOS com o Microsoft Intune – Azure | Microsoft Docs
description: Ative ou inicie o modo perdido para personalizar uma mensagem exibida na tela de bloqueio de um dispositivo iOS perdido ou roubado usando o Microsoft Intune. E obtenha detalhes sobre as informações de privacidade e de segurança ao usar a ação de modo perdido.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 34a4c8adeef7e8b28c90ad38579f0f9ac7c4784d
ms.sourcegitcommit: 807ab3e35f4d9ffa18655410b7d61e5e772ab348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73057535"
---
# <a name="enable-lost-mode-on-ios-devices-with-intune"></a>Habilitar o modo perdido em dispositivos iOS com o Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

A ação de dispositivo **Modo perdido** ajuda você a habilitar o modo perdido em dispositivos iOS perdidos ou roubados. Esse modo permite que você insira uma mensagem e um número de telefone que aparecerão na tela de bloqueio do dispositivo. Para utilizar o modo perdido, é necessário um dispositivo iOS corporativo no modo supervisionado.

## <a name="supported-platforms"></a>Plataformas com Suporte

- iOS 9.3 e posterior

Esse recurso não é compatível com os seguintes: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="enable-lost-mode"></a>Habilitar o modo perdido

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecione **Dispositivos** e, em seguida, **Todos os dispositivos**.
4. Na lista de dispositivos gerenciados, escolha um dispositivo iOS e o **Modo perdido (somente supervisionado)** .
5. Em **Modo perdido**, selecione **Habilitar**.
6. Em **Mensagem a ser exibida na tela de bloqueio**, digite a mensagem que será exibida na tela de bloqueio do dispositivo.
7. Como opção, insira um número de telefone na caixa **Número de telefone a ser exibido**.
6. Selecione **OK** para salvar suas alterações.

Quando você habilita o modo perdido, todo o uso do dispositivo é bloqueado. O usuário final não poderá acessar o dispositivo até que você desative o modo perdido. Enquanto o modo perdido estiver habilitado, use a ação [Localizar dispositivo](device-locate.md) para localizar o dispositivo.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informações sobre segurança e privacidade para o modo perdido e ações para localizar o dispositivo
- Nenhuma informação do local do dispositivo será enviada para o Intune até que essa ação seja ativada.
- Quando você usa a ação do dispositivo localizar, as coordenadas da latitude e de longitude do dispositivo são enviadas para o Intune e mostradas no portal do Azure.
- Os dados são armazenados por 24 horas, então, removidos. Você não pode remover manualmente os dados de localização.
- Os dados de localização são criptografados, enquanto estão armazenados e enquanto estão sendo transmitidos.
- Na mensagem que você inserir para ser mostrada na tela de bloqueio, inclua detalhes específicos para que o dispositivo perdido seja devolvido.

## <a name="next-steps"></a>Próximas etapas

Para ver o status de habilitação do modo perdido, abra **Dispositivos** e selecione **Ações do dispositivo**.
