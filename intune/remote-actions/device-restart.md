---
title: Reiniciar dispositivos com o Microsoft Intune – Azure | Microsoft Docs
description: Reinicie os dispositivos Windows e iOS usando o Microsoft Intune no Portal do Azure usando a ação remota Reiniciar.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 18cf8e3aec0c7ed7d8869c0f5b13b6e39df23d77
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73713417"
---
# <a name="remotely-restart-devices-with-intune"></a>Reiniciar dispositivos remotamente com o Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

A ação de dispositivo **Reiniciar** faz com que o dispositivo escolhido seja reiniciado. O proprietário do dispositivo não é notificado automaticamente sobre a reinicialização e pode perder trabalho.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Com suporte no Windows 8.1 e versões posteriores
- Windows Phone – Com suporte no Windows 8.1 e versões posteriores
- Dispositivos de quiosque Android – com suporte no Android 7.0 e posterior
- iOS – Com suporte

    > [!Note]  
    > Este comando requer um dispositivo supervisionado e o direito de acesso do **Bloqueio de dispositivo**. O dispositivo é reiniciado imediatamente. Os dispositivos iOS bloqueados por senha não ingressam novamente em uma rede Wi-Fi após a reinicialização. Após a reinicialização, talvez o dispositivo não seja capaz de se comunicar com o servidor.
- macOS – Sem suporte
- Dispositivos Android e de perfil de trabalho Android – não há suporte

## <a name="restart-a-device"></a>Reiniciar um dispositivo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecione **Dispositivos** > **Todos os dispositivos**.
4. Na lista de dispositivos gerenciados, selecione um dispositivo, selecione **Mais** e, em seguida, a ação remota do dispositivo **Reiniciar**.

## <a name="next-steps"></a>Próximas etapas

- Para ver o status da ação do dispositivo **Reiniciar**, selecione **Dispositivos** > **Ações do dispositivo**.
