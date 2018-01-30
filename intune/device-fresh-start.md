---
title: Redefinir dispositivos Windows 10 com o Intune
titlesuffix: Azure portal
description: "Saiba como usar o Novo Início para redefinir computadores Windows 10 que executam o Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dce888c1985ff4761100d15d898b654d77318b65
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Usar o Novo Início para redefinir dispositivos Windows 10 com o Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Novo Início** remove todos os aplicativos que foram instalados em um computador Windows 10 que executa a Atualização para Criadores e, em seguida, atualiza automaticamente o computador para a versão mais recente do Windows.
Isso pode ser usado para ajudar a remover aplicativos pré-instalados (OEM) que geralmente são fornecidos com um novo computador. Você pode configurar se os dados do usuário são mantidos quando essa ação do dispositivo é realizada. Nesse caso, os aplicativos e as configurações são removidas, mas o conteúdo da pasta base dos usuários é mantido.

## <a name="how-to-use-fresh-start"></a>Como usar o Novo Início

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo do Windows 10 Desktop e, em seguida, escolha a ação remota de dispositivo **Novo Início**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.

