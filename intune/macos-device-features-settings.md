---
title: Configurações de recurso de dispositivo macOS no Microsoft Intune – Azure | Microsoft Docs
description: Confira todas as definições para configurar dispositivos macOS para AirPrint no Microsoft Intune. Confira também as etapas para obter o endereço IP, caminho e as configurações de porta de um servidor AirPrint em sua rede. Use essas configurações em um perfil de configuração de dispositivos para configurar dispositivos macOS para usar servidores AirPrint em sua rede.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.openlocfilehash: cdc5f5fe2c94dee2349cab777c7671c2673f52b2
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831949"
---
# <a name="macos-device-feature-settings-in-intune"></a>Configurações de recursos do dispositivo macOS no Intune

O Intune inclui algumas configurações internas para permitir que os usuários do macOS imprimam em impressoras AirPrint em sua rede. Este artigo lista essas configurações e descreve o que cada uma faz. Ele também lista as etapas para obter o endereço IP, o caminho e a porta das impressoras AirPrint usando o aplicativo Terminal (emulador).

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo macOS](device-features-configure.md).

## <a name="airprint-settings"></a>Configurações de AirPrint

1. Em **Configurações**, escolha **AirPrint**. Insira as seguintes propriedades do servidor AirPrint:

    - **Endereço IP**: Insira o endereço IPv4 ou IPv6 da impressora. Se você usar nomes de host para identificar as impressoras, obtenha o endereço IP ao executar o ping da impressora no aplicativo Terminal. [Obter o endereço IP e o caminho](#get-the-ip-address-and-path) (neste artigo) fornece mais detalhes.
    - **Caminho**: Insira o caminho da impressora. Geralmente, o caminho é `ipp/print` para impressoras na rede. [Obter o endereço IP e o caminho](#get-the-ip-address-and-path) (neste artigo) fornece mais detalhes.
    - **Porta**: Insira a porta de escuta do destino do AirPrint. Se você deixar essa propriedade em branco, o AirPrint usará a porta padrão. Disponível no iOS 11.0 e posterior.
    - **TLS**: Escolha **Habilitar** para proteger as conexões do AirPrint com o protocolo TLS. Disponível no iOS 11.0 e posterior.

2. Selecione **Adicionar**. O servidor AirPrint é adicionado à lista. Você pode adicionar vários servidores AirPrint.

    Você também pode **Importar** um arquivo .csv (separado por vírgula) que inclui uma lista de impressoras AirPrint. Além disso, depois de adicionar impressoras AirPrint no Intune, você pode **Exportar** essa lista.

3. Quando terminar, escolha **OK** para salvar sua lista.

## <a name="get-the-ip-address-and-path"></a>Obter o endereço IP e o caminho

Para adicionar servidores AirPrinter, você precisa ter o endereço IP da impressora, o caminho do recurso e a porta. As etapas a seguir mostram como obter essas informações.

1. Em um Mac conectado à mesma rede local (sub-rede) que as impressoras AirPrint, abra o **Terminal** (em **/Applications/Utilities**).
2. No aplicativo Terminal, digite `ippfind` e escolha Enter.

    Observe as informações da impressora. Por exemplo, pode retornar algo semelhante a `ipp://myprinter.local.:631/ipp/port1`. A primeira parte é o nome da impressora. A última parte (`ipp/port1`) é o caminho do recurso.

3. No Terminal, digite `ping myprinter.local` e escolha Enter.

   Observe o endereço IP. Por exemplo, pode retornar algo semelhante a `PING myprinter.local (10.50.25.21)`.

4. Use os valores do endereço IP e do caminho de recursos. Neste exemplo, o endereço IP é `10.50.25.21` e o caminho do recurso é `/ipp/port1`.

## <a name="next-steps"></a>Próximas etapas

- Exiba todas as configurações para dispositivos [iOS](ios-device-features-settings.md).
- Atribua esse perfil a grupos. Confira [atribuir perfis de dispositivos](device-profile-assign.md).