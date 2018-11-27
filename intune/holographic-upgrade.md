---
title: Atualizar o Windows Holographic para o Windows Holographic for Business
titleSuffix: Microsoft Intune
description: Saiba como atualizar dispositivos que executam o Windows Holographic para o Windows Holographic for Business
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 735cd658e78a68156957d54be02f32b41812495e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179194"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Atualizar dispositivos que executam o Windows Holographic para o Windows Holographic for Business


Para gerenciar dispositivos que executam o Windows Holographic com o Microsoft Intune, será necessário fazer upgrade do Windows Holographic para o Windows Holographic for Business. É possível criar um perfil de Atualização de Edição para fazer a atualização. Para o Microsoft HoloLens, você pode adquirir o Commercial Suite para obter a licença necessária para a atualização. Para obter mais informações, consulte [Desbloquear recursos do Windows Holographic for Business](https://docs.microsoft.com/hololens/hololens-upgrade-enterprise).

## <a name="to-set-up-an-edition-upgrade-device-configuration-profile"></a>Para configurar um perfil de configuração de dispositivo de Atualização de Edição

1. Entre no [Portal do Azure](https://portal.azure.com) com sua conta de administrador.


2.  Clique em **Configuração de dispositivo**, **Perfis** e, em seguida, clique em **+Criar perfil**.

    ![Criar perfil](media/Holographic-create-profile.png)

3.  Na página **Criar perfil**, digite um nome para o perfil, selecione **Windows 10 e posterior** para a plataforma e selecione **Atualização de edição** para o tipo de perfil. Clique em **Configurar definições**.

5. Na página **Atualização de Edição**, em **Edição para a qual atualizar**, selecione **Windows 10 Holographic for Business**. Em **Arquivo de Licença**, navegue e selecione o arquivo de licença XML que foi fornecido para você.

    ![Inserir o nome do arquivo XML](media/Holographic-edition-upgrade.png)
 
5.  Clique em **OK** e, em seguida, clique em **Criar** para criar o perfil.


## <a name="deploy-the-edition-upgrade-policy"></a>Implantar a política de Atualização de Edição

Agora, você atribui o perfil de Atualização de Edição a dispositivos ou grupos selecionados.

1. No perfil que você criou nas etapas anteriores, clique em **Atribuições**.

2. No painel **Atribuições**, selecione os grupos de usuários e os dispositivos que você deseja incluir e excluir da política.

![Incluir e excluir grupos](media/Holographic-groups.PNG)

Quando esses usuários ou dispositivos estiverem registrados no Intune, o perfil de Atualização de Edição será aplicado. 

## <a name="next-steps"></a>Próximas etapas

Para obter mais informações sobre grupos, consulte [Introdução aos grupos](get-started-groups.md).


