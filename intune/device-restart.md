---
title: Reiniciar dispositivos remotamente com o Intune
titlesuffix: Microsoft Intune
description: Saiba como reiniciar dispositivos remotamente usando a ação de reinicialização do dispositivo no Microsoft Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1bd5a01b8aac91c3bd6ea033d62d41e19aab65f8
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2018
---
# <a name="remotely-restart-devices-with-intune"></a>Reiniciar dispositivos remotamente com o Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Reiniciar** faz com que o dispositivo escolhido seja reiniciado. O proprietário do dispositivo não será notificado automaticamente sobre a reinicialização, portanto ele pode perder trabalho.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Com suporte no Windows 8.1 e versões posteriores
- Windows Phone – Com suporte no Windows 8.1 e versões posteriores
- iOS – Com suporte

    > [!Note]  
    > Este comando requer um dispositivo supervisionado e o direito de acesso de **Bloqueio de Dispositivo**. O dispositivo é reiniciado imediatamente. Dispositivos iOS protegidos por senha não serão reconectados a uma rede Wi-Fi após a reinicialização; Após a reinicialização, é possível que eles não se comuniquem com o servidor.
- macOS – Sem suporte
- Android – Sem suporte

## <a name="how-to-restart-a-device"></a>Como reiniciar um dispositivo

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo, escolha **...Mais** e, em seguida, escolha a ação remota do dispositivo **Reiniciar**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos**, escolha **Ações do dispositivo**.
