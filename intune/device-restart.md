---
title: Reiniciar dispositivos com o Microsoft Intune – Azure | Microsoft Docs
description: Reinicie os dispositivos Windows e iOS usando o Microsoft Intune no Portal do Azure usando a ação remota Reiniciar.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b68d7eda57d50c3a1cb55979590e8b07d9daf50
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37904941"
---
# <a name="remotely-restart-devices-with-intune"></a>Reiniciar dispositivos remotamente com o Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Reiniciar** faz com que o dispositivo escolhido seja reiniciado. O proprietário do dispositivo não é notificado automaticamente sobre a reinicialização e pode perder trabalho.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Com suporte no Windows 8.1 e versões posteriores
- Windows Phone – Com suporte no Windows 8.1 e versões posteriores
- Dispositivos de quiosque Android – com suporte
- iOS – Com suporte

    > [!Note]  
    > Este comando requer um dispositivo supervisionado e o direito de acesso do **Bloqueio de dispositivo**. O dispositivo é reiniciado imediatamente. Os dispositivos iOS bloqueados por senha não ingressam novamente em uma rede Wi-Fi após a reinicialização. Após a reinicialização, talvez o dispositivo não seja capaz de se comunicar com o servidor.
- macOS – Sem suporte
- Dispositivos Android e de perfil de trabalho Android – não há suporte

## <a name="restart-a-device"></a>Reiniciar um dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Dispositivos** > **Todos os dispositivos**.
4. Na lista de dispositivos gerenciados, selecione um dispositivo, selecione **Mais** e, em seguida, a ação remota do dispositivo **Reiniciar**.

## <a name="next-steps"></a>Próximas etapas

- Para ver o status da ação do dispositivo **Reiniciar**, selecione **Dispositivos** > **Ações do dispositivo**.
