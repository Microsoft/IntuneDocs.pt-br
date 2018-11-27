---
title: Configurações do Intune AirPlay para dispositivos iOS
titlesuffix: Microsoft Intune
description: Saiba como usar o Microsoft Intune para ajudar com a conexão automática dos dispositivos iOS para dispositivos compatíveis com AirPlay.
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
ms.openlocfilehash: efeb7895bcd83883e7fcaaca93c3d19d19a0bb5c
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184124"
---
# <a name="intune-airplay-settings-for-ios-devices"></a>Configurações do Intune AirPlay para dispositivos iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use essas configurações para ajudar a conectar os dispositivos iOS gerenciados a dispositivos compatíveis com AirPlay (como Apple TVs) em sua rede.
Com esse recurso, você pode:

- **Configurar uma lista de dispositivos e senhas** – permita que os usuários se conectem automaticamente aos dispositivos AirPlay que estão no alcance. Provisione-os com o nome e a senha dos dispositivos AirPlay, de forma que eles não precisem fornecê-los quando se conectarem.
- **Configurar destinos permitidos** - configure uma lista de dispositivos AirPlay (por ID de dispositivo). Os usuários finais somente podem ver e se conectar aos dispositivos listados (apenas para dispositivos supervisionados).

## <a name="get-started"></a>Introdução

1. Do [Intune no Portal do Azure](https://portal.azure.com), navegue até os [**Recursos do dispositivo** na área de configuração do dispositivo](device-features-configure.md). 
1. No painel **Recursos do dispositivo**, escolha **AirPlay**.
2. No painel **AirPlay**, escolha uma ou ambas as ações a seguir:

## <a name="configure-a-device-and-password-list"></a>Configurar uma lista de dispositivos e senha

1. No painel **Senhas**, insira o **Nome do Dispositivo** e a **Senha** de um dispositivo AirPlay, por exemplo, **Contoso Apple TV**.
2. Depois de inserir os detalhes do dispositivo, clique em **Adicionar**. O dispositivo é exibido na lista **Nome do Dispositivo**.
3. Continue adicionando itens. Quando terminar, escolha **OK**.


## <a name="configure-allowed-destinations"></a>Configurar destinos permitidos

1. No painel **Destinos permitidos (somente supervisionados)**, insira a **ID do Dispositivo** de um dispositivo AirPlay, por exemplo, 52:46:CD:51:83:4C.
2. Depois de inserir a ID do dispositivo, clique em **Adicionar**. A ID é exibida na lista **ID do Dispositivo**.
3. Continue adicionando itens. Quando terminar, escolha **OK**.

Você também pode importar o dispositivo e as senhas, bem como os destinos permitidos, de um arquivo csv (valores separados por vírgula).


## <a name="next-steps"></a>Próximas etapas

Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos. Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).

