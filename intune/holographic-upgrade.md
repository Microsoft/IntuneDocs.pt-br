---
title: Atualizar o Windows Holographic para o Windows Holographic for Business
titleSuffix: Azure portal
description: Saiba como atualizar dispositivos que executam o Windows Holographic para o Windows Holographic for Business
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/30/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c467d2d4e02785bfac48afe2b39c50300eb4be40
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2018
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Atualizar dispositivos que executam o Windows Holographic para o Windows Holographic for Business


Para gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune, você deve criar um perfil de Atualização de Edição para atualizar os dispositivos do Windows Holographic para o Windows Holographic for Business. Para o Microsoft HoloLens, você pode adquirir o Commercial Suite para obter a licença necessária para a atualização. Para obter mais informações, consulte [Desbloquear recursos do Windows Holographic for Business](https://docs.microsoft.com/en-us/hololens/hololens-upgrade-enterprise).

## <a name="to-set-up-an-edition-upgrade-device-configuration-profile"></a>Para configurar um perfil de configuração de dispositivo de Atualização de Edição

1. Entre no [Portal do Azure](https://portal.azure.com) com sua conta de administrador.


2.  Clique em **Configuração de dispositivo**, **Perfis** e, em seguida, clique em **+Criar perfil**.

    ![Criar perfil](media/Holographic-create-profile.png)

3.  Na folha **Criar perfil**, digite um nome para o perfil, selecione **Windows 10 e posterior** para a plataforma e selecione **Atualização de edição** para o tipo de perfil. Clique em **Configurar definições**.

5. Na folha **Atualização de Edição**, em **Edição para a qual atualizar**, selecione **Windows 10 Holographic for Business**. Em **Arquivo de Licença**, navegue e selecione o arquivo de licença XML que foi fornecido para você.

    ![Inserir o nome do arquivo XML](media/Holographic-edition-upgrade.png)
 
5.  Clique em **OK** e, em seguida, clique em **Criar** para criar o perfil.


## <a name="deploy-the-edition-upgrade-policy"></a>Implantar a política de Atualização de Edição

Agora, você atribui o perfil de Atualização de Edição a dispositivos ou grupos selecionados.

1. No perfil que você criou nas etapas anteriores, clique em **Atribuições**.

2. Na folha **Atribuições**, selecione os grupos de usuários e os dispositivos que você deseja incluir e excluir com a política.

![Incluir e excluir grupos](media/Holographic-groups.PNG)

Quando esses usuários ou dispositivos estiverem registrados no Intune, o perfil de Atualização de Edição será aplicado. 

## <a name="next-steps"></a>Próximas etapas

Para obter mais informações sobre grupos, consulte [Introdução aos grupos](get-started-groups.md).


