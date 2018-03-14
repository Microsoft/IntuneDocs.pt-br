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
ms.openlocfilehash: c45d3e47c90ca7739b3aa6eee1bf31d787a82264
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Usar o Novo Início para redefinir dispositivos Windows 10 com o Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Novo Início** remove todos os aplicativos que foram instalados em um computador Windows 10 que executa a Atualização para Criadores e, em seguida, atualiza automaticamente o computador para a versão mais recente do Windows.
Essa ação pode ser usada para ajudar a remover aplicativos pré-instalados (OEM) que geralmente são fornecidos com um novo computador. Você pode configurar se os dados do usuário são mantidos quando essa ação do dispositivo é realizada. Nesse caso, os aplicativos e as configurações são removidas, mas o conteúdo da pasta base dos usuários é mantido.

## <a name="how-to-use-fresh-start"></a>Como usar o Novo Início

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Dispositivos**.
4. No painel **Dispositivos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo do Windows 10 Desktop e, em seguida, escolha a ação remota de dispositivo **Novo Início**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, no painel **Dispositivos**, escolha **Ações do dispositivo**.

