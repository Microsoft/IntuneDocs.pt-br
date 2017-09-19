---
title: "Configurações do Intune AirPlay para dispositivos iOS"
titlesuffix: Azure portal
description: "Saiba como você pode usar o Intune para ajudar com a conexão automática dos dispositivos iOS para dispositivos compatíveis com AirPlay."
keywords: 
author: lleonard-msft
ms.author: alleonar
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
ms.openlocfilehash: ff64e8657d65ea8e233cde8d3e3219d2bdab6ce7
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
---
# <a name="intune-airplay-settings-for-ios-devices"></a>Configurações do Intune AirPlay para dispositivos iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use essas configurações para ajudar a conectar os dispositivos iOS gerenciados a dispositivos compatíveis com AirPlay (como Apple TVs) em sua rede.
Com esse recurso, você pode:

- **Configurar uma lista de dispositivos e senhas** – permita que os usuários se conectem automaticamente aos dispositivos AirPlay que estão no alcance. Provisione-os com o nome e a senha dos dispositivos AirPlay, de forma que eles não precisem fornecê-los quando se conectarem.
- **Configurar destinos permitidos** - configure uma lista de dispositivos AirPlay (por ID de dispositivo). Os usuários finais somente podem ver e se conectar aos dispositivos listados (apenas para dispositivos supervisionados).

## <a name="get-started"></a>Introdução

1. Na folha **Recursos do dispositivo**, escolha **AirPlay**.
2. Na folha **AirPlay**, escolha uma ou ambas as seguintes ações:

## <a name="configure-a-device-and-password-list"></a>Configurar uma lista de dispositivos e senha

1. Na folha **Senhas**, insira o **Nome do Dispositivo** e a **Senha** de um dispositivo AirPlay, por exemplo, **Contoso Apple TV**.
2. Depois de inserir os detalhes do dispositivo, clique em **Adicionar**. O dispositivo é exibido na lista **Nome do Dispositivo**.
3. Continue adicionando itens. Quando terminar, escolha **OK**.


## <a name="configure-allowed-destinations"></a>Configurar destinos permitidos

1. Na folha **Destinos permitidos (somente supervisionados)**, insira a **ID do Dispositivo** de um dispositivo AirPlay, por exemplo, 52:46:CD:51:83:4C.
2. Depois de inserir a ID do dispositivo, clique em **Adicionar**. A ID é exibida na lista **ID do Dispositivo**.
3. Continue adicionando itens. Quando terminar, escolha **OK**.

Você também pode importar o dispositivo e as senhas, bem como os destinos permitidos, de um arquivo csv (valores separados por vírgula).


## <a name="next-steps"></a>Próximas etapas

Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos. Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).

