---
title: Definir configurações de proteção de ponto de extremidade no Microsoft Intune – Azure | Microsoft Docs
description: Crie configurações de proteção de ponto de extremidade ao criar um perfil do dispositivo Windows 10 ou macOS no Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 3/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8cda293fb337730c936a7fab9b7eadf4816beb67
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57237946"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Adicionar configurações de proteção de ponto de extremidade no Intune

A proteção de ponto de extremidade permite controlar diferentes recursos de segurança em seus dispositivos, incluindo firewall, bitLocker, permitir e bloquear aplicativos, Windows Defender, criptografia e muito mais. Você pode definir essas configurações no Microsoft Intune usando perfis de dispositivo.

Por exemplo, você pode criar um perfil de proteção de ponto de extremidade que permita apenas a usuários do macOS instalar aplicativos da Mac App Store. Ou habilite a Windows SmartScreen durante a execução de aplicativos em dispositivos Windows 10.

Este artigo mostra como criar um perfil. Em seguida, selecione a plataforma de dispositivo para obter mais detalhes sobre as configurações disponíveis.

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Criar um perfil de dispositivo contendo configurações de proteção de ponto de extremidade

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
4. Insira um **Nome** e uma **Descrição** para o perfil de proteção de ponto de extremidade.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações personalizadas. No momento, é possível escolher uma das seguintes plataformas para as configurações de restrição de dispositivo:
   - **macOS**
   - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Tipo de perfil**, escolha **Endpoint Protection**. 
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:
   - [Configurações do macOS](endpoint-protection-macos.md)
   - [Configurações do Windows 10](endpoint-protection-windows-10.md)
8. Quando terminar, volte para a página **Criar Perfil** e clique em **Criar**.

O perfil é criado e exibido na página da lista de perfis. Para atribuir esse perfil a grupos, consulte [atribuir perfis de dispositivo](device-profile-assign.md).

## <a name="next-steps"></a>Próximas etapas
Para atribuir um perfil a grupos, consulte [atribuir perfis de dispositivo](device-profile-assign.md).
