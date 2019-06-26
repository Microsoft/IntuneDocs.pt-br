---
title: Definir configurações de proteção de ponto de extremidade no Microsoft Intune – Azure | Microsoft Docs
description: Crie configurações de proteção de ponto de extremidade ao criar um perfil do dispositivo Windows 10 ou macOS no Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 5/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: 2bebdf712ccf325c6742e6bb326a8fb2768023b7
ms.sourcegitcommit: 14f4e97de5699394684939e6f681062b5d4c1671
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2019
ms.locfileid: "67251178"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Adicionar configurações de proteção de ponto de extremidade no Intune

Com o Intune, é possível usar perfis de configuração de dispositivo para gerenciar recursos comuns de proteção de ponto de extremidade nos dispositivos, incluindo:
- Firewall 
- BitLocker
- Permitir ou bloquear aplicativos  
- Criptografia e Windows Defender

Por exemplo, você pode criar um perfil de proteção de ponto de extremidade que permita apenas a usuários do macOS instalar aplicativos da Mac App Store. Ou habilite a Windows SmartScreen durante a execução de aplicativos em dispositivos Windows 10.

Antes de criar um perfil, consulte os seguintes artigos que detalham as configurações de proteção de ponto de extremidade que o Intune pode gerenciar para cada plataforma compatível: 
   - [Configurações do macOS](endpoint-protection-macos.md)
   - [Configurações do Windows 10](endpoint-protection-windows-10.md)

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Criar um perfil de dispositivo contendo configurações de proteção de ponto de extremidade

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
4. Insira um **Nome** e uma **Descrição** para o perfil de proteção de ponto de extremidade.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações personalizadas. No momento, é possível escolher uma das seguintes plataformas para as configurações de restrição de dispositivo:
   - **macOS**
   - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Tipo de perfil**, escolha **Endpoint Protection**. 
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Consulte:
   - [Configurações do macOS](endpoint-protection-macos.md)
   - [Configurações do Windows 10](endpoint-protection-windows-10.md)  

8. Depois de definir as configurações aplicáveis, selecione **Criar** na página **Criar perfil**.

   O perfil é criado e exibido na página da lista de perfis. Para atribuir esse perfil a grupos, consulte [atribuir perfis de dispositivo](device-profile-assign.md).


## <a name="next-steps"></a>Próximas etapas  

Para atribuir um perfil a grupos, consulte [atribuir perfis de dispositivo](device-profile-assign.md).
