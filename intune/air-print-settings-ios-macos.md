---
title: Configurações do Intune AirPrint para dispositivos iOS e macOS
titlesuffix: Microsoft Intune
description: Saiba como usar o Microsoft Intune para ajudar a conectar automaticamente dispositivos iOS e macOS com impressoras compatíveis com AirPrint.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 850c61868cc5404d1645482a6998856e465b4070
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186283"
---
# <a name="airprint-settings-for-ios-and-macos-devices"></a>Configurações do AirPrint para dispositivos iOS e macOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use essas configurações para configurar os dispositivos iOS ou macOS para se conectarem automaticamente a impressoras compatíveis com AirPrint em sua rede. Você precisará do endereço IP e do caminho de recursos de suas impressoras para continuar.

## <a name="find-airprint-printer-information"></a>Encontrar informações da impressora AirPrint

Use este procedimento para adicionar informações do AirPrint à carga do AirPrint, para que os usuários de dispositivos iOS possam imprimir em impressoras do AirPrint conhecidas.

1. Em um Mac conectado à mesma rede local (sub-rede) que as impressoras AirPrint, abra o Terminal (em **/Applications/Utilities**)
2. No Terminal, digite **ippfind** e pressione enter.
3. Anote qualquer informação sobre a impressora retornada pelo comando, por exemplo: **ipp://myprinter.local.:631/ipp/port1**. A primeira parte das informações é o nome da impressora, e a última parte é o caminho do recurso.
4. No Terminal, digite **ping myprinter.local** e pressione enter.
5. Anote as informações de endereço IP retornadas pelo comando, por exemplo, **myprinter.local de PING (10.50.25.21)**.
6. Por fim, use o caminho de recursos e o endereço IP nas configurações de carga do AirPrint. Um exemplo de endereço IP pode ser **10.50.25.21**, e um exemplo de caminho de recurso pode ser **/ipp port1**.

## <a name="configure-an-airprint-profile"></a>Configurar um perfil de AirPrint

1. Do [Intune no Portal do Azure](https://portal.azure.com), navegue até os [**Recursos do dispositivo** na área de configuração do dispositivo](device-features-configure.md). 
1. No painel **Recursos do dispositivo**, escolha **AirPrint**.
2. No painel **AirPrint**, insira o **Endereço IP** e o **caminho do recurso**, e depois clique em **Adicionar** para adicionar um destino do AirPrint.
3. Adicionar quantos destinos forem necessários. Quando terminar, escolha **OK**.

Você também pode importar uma lista de impressoras de um arquivo de valores separados por vírgulas (.csv) ou exportar a lista.


## <a name="next-steps"></a>Próximas etapas

Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos. Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).