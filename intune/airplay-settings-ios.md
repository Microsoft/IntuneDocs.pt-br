---
title: "Configurações do Intune AirPlay para dispositivos iOS"
titleSuffix: Intune Azure preview
description: "Saiba como você pode usar o Intune para ajudar com a conexão automática dos dispositivos iOS para dispositivos compatíveis com AirPlay."
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
ms.openlocfilehash: ad2f20603261ec0eac4156facd3fd23b2982f517
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="intune-airplay-settings-for-ios-devices"></a>Configurações do Intune AirPlay para dispositivos iOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Use essas configurações para ajudar a conectar dispositivos iOS que você gerencia aos dispositivos compatíveis com AirPlay (como a Apple TV) em sua rede.
Com esse recurso, você pode:

- **Configurar uma lista de dispositivos e senha** - provisione os dispositivos com o nome e a senha de dispositivos AirPlay para conectá-los automaticamente quando estiverem dentro do alcance. Se você fornecer uma senha, os usuários finais não precisarão fornecê-la durante a conexão.
- **Configurar destinos permitidos** - configure uma lista de dispositivos AirPlay (por ID de dispositivo). Os usuários finais só poderão ver e se conectar aos dispositivos que você listar (somente para dispositivos supervisionados).

## <a name="get-started"></a>Introdução

1. Na folha **Recursos do dispositivo**, escolha **AirPlay**.
2. Na folha **AirPlay**, escolha uma ou ambas as seguintes ações:

## <a name="configure-a-device-and-password-list"></a>Configurar uma lista de dispositivos e senha

1. Na folha **Senhas**, insira o **Nome do dispositivo** e a **Senha** de um dispositivo Airplay, por exemplo, **Contoso Apple TV**.
2. Depois de inserir os detalhes do dispositivo, clique em **Adicionar**. O dispositivo aparecerá na lista **Nome do Dispositivo**.
3. Continue adicionando itens. Quando terminar, escolha **OK**.


## <a name="configure-allowed-destinations"></a>Configurar destinos permitidos

1. Na folha **Destinos permitidos (somente supervisionado)*, insira a **ID do dispositivo** de um dispositivo Airplay, por exemplo, 52:46:CD:51:83:4C.
2. Depois de inserir a ID do dispositivo, clique em **Adicionar**. A ID aparecerá na lista **D do dispositivo**.
3. Continue adicionando itens. Quando terminar, escolha **OK**.

Você também pode importar o dispositivo e as senhas, e os destinos permitidos, de um arquivo csv (valores separados por vírgula).



