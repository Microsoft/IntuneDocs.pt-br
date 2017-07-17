---
title: "Configurações do Intune AirPrint para dispositivos iOS e macOS"
titleSuffix: Intune on Azure
description: "Saiba como você pode usar o Intune para ajudar a conectar automaticamente dispositivos iOS e macOS com impressoras compatíveis com AirPrint."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 743eb9a71efe1a5ea18b15312fdd4fe684f0ff07
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
# Configurações do AirPrint para dispositivos iOS e macOS
<a id="airprint-settings-for-ios-and-macos-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use essas configurações para configurar os dispositivos iOS ou macOS para se conectarem automaticamente a impressoras compatíveis com AirPrint em sua rede. Você precisará do endereço IP e do caminho de recursos de suas impressoras para continuar.

## Encontrar informações da impressora AirPrint
<a id="find-airprint-printer-information" class="xliff"></a>

Use este procedimento para adicionar informações do AirPrint à carga do AirPrint, para que os usuários de dispositivos iOS possam imprimir em impressoras do AirPrint conhecidas.

1. Em um Mac conectado à mesma rede local (sub-rede) que as impressoras AirPrint, abra o Terminal (em **/Applications/Utilities**)
2. No Terminal, digite **ippfind** e pressione enter.
3. Anote qualquer informação sobre a impressora retornada pelo comando, por exemplo: **ipp://myprinter.local.:631/ipp/port1**. A primeira parte das informações é o nome da impressora, e a última parte é o caminho do recurso.
4. No Terminal, digite **ping myprinter.local** e pressione enter.
5. Anote as informações de endereço IP retornadas pelo comando, por exemplo, **myprinter.local de PING (10.50.25.21)**.
6. Por fim, use o caminho de recursos e o endereço IP nas configurações de carga do AirPrint. Um exemplo de endereço IP pode ser **10.50.25.21**, e um exemplo de caminho de recurso pode ser **/ipp port1**.

## Configurar um perfil de AirPrint
<a id="configure-an-airprint-profile" class="xliff"></a>

1. Na folha **Recursos do dispositivo**, escolha **AirPrint**.
2. Na folha **AirPrint**, para adicionar um destino de AirPrint, insira seu **Endereço IP** e **caminho do recurso**e depois clique em **Adicionar**.
3. Adicionar quantos destinos forem necessários. Quando terminar, escolha **OK**.

Você também pode importar uma lista de impressoras de um arquivo de valores separados por vírgulas (.csv) ou exportar a lista.


## Próximas etapas
<a id="next-steps" class="xliff"></a>

Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos. Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).