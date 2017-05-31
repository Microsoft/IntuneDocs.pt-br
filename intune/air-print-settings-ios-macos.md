---
title: "Configurações do Intune AirPrint para dispositivos iOS e macOS"
titleSuffix: Intune Azure preview
description: "Visualização do Intune Azure: aprenda a usar o Intune para ajudar a conectar automaticamente os dispositivos iOS e macOS com impressoras compatíveis com AirPrint."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 55486693e2f5678ceeb20dd3a0ef3c52553871d2
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="airprint-settings-for-ios-and-macos-devices"></a>Configurações do AirPrint para dispositivos iOS e macOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Use essas configurações para configurar os dispositivos iOS ou macOS para se conectarem automaticamente a impressoras compatíveis com AirPrint em sua rede. Você precisará do endereço IP e do caminho de recursos de suas impressoras para continuar.

## <a name="find-airprint-printer-information"></a>Encontrar informações da impressora AirPrint

Use este procedimento para adicionar informações do AirPrint à carga do AirPrint, para que os usuários de dispositivos iOS possam imprimir em impressoras do AirPrint conhecidas.

1. Em um Mac conectado à mesma rede local (sub-rede) que as impressoras Airprint, abra o Terminal (em **/aplicativos/utilitários**)
2. No Terminal, digite **ippfind** e pressione enter.
3. Anote qualquer informação sobre a impressora retornada pelo comando, por exemplo: **ipp://myprinter.local.:631/ipp/port1**. A primeira parte das informações é o nome da impressora, e a última parte é o caminho do recurso.
4. No Terminal, digite **ping myprinter.local** e pressione enter.
5. Anote as informações de endereço IP retornadas pelo comando, por exemplo, **myprinter.local de PING (10.50.25.21)**.
6. Por fim, use o caminho de recursos e o endereço IP nas configurações de carga do AirPrint. Um exemplo de endereço IP pode ser **10.50.25.21**, e um exemplo de caminho de recurso pode ser **/ipp port1**.

## <a name="configure-an-airprint-profile"></a>Configurar um perfil de AirPrint

1. Na folha **Recursos do dispositivo**, escolha **AirPrint**.
2. Na folha **AirPrint**, para adicionar um destino de AirPrint, insira seu **Endereço IP** e **caminho do recurso**e depois clique em **Adicionar**.
3. Adicionar quantos destinos forem necessários. Quando terminar, escolha **OK**.

Você também pode importar uma lista de impressoras de um arquivo de valores separados por vírgulas (.csv) ou exportar a lista.

