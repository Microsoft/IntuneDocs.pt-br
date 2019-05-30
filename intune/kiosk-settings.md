---
title: Configurações de quiosque para dispositivos com Windows e Holographic no Microsoft Intune – Azure | Microsoft Docs
description: Configure dispositivos com Windows 10 (e posterior) e Windows Holographic for Business como quiosques de aplicativo único e de vários aplicativos, personalize o menu Iniciar, adicione aplicativos, mostre a barra de tarefas e configure um navegador da Web no Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: fbd545d13d9241edd55c01e4353a28b3851d2ac2
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66046897"
---
# <a name="windows-10-and-windows-holographic-for-business-device-settings-to-run-as-a-dedicated-kiosk-using-intune"></a>Configurações de dispositivos com Windows 10 (e posterior) e Windows Holographic for Business para execução como um quiosque dedicado usando o Intune

Em dispositivos Windows 10, use o Intune para executar dispositivos como um quiosque, às vezes conhecido como um dispositivo dedicado. Um dispositivo no modo de quiosque pode executar um ou muitos aplicativos. Você pode mostrar e personalizar um menu Iniciar, adicionar aplicativos diferentes, incluindo aplicativos Win32, adicionar uma home page específica a um navegador da Web, entre outros. 

Esse recurso se aplica a dispositivos que executam:

- Windows 10 e posterior
- Windows Holographic for Business

O Intune oferece suporte a um único perfil de quiosque por dispositivo. Se você precisar de vários perfis de quiosque em um único dispositivo, poderá usar um [OMA-URI personalizado](custom-settings-windows-10.md).

O Intune usa "perfis de configuração" para criar e personalizar essas configurações de acordo com as necessidades da sua organização. Depois de adicionar esses recursos em um perfil, envie por push ou implante essas configurações em grupos de sua organização.

Este artigo mostra como criar um perfil de configuração de dispositivos. Para obter uma lista com todas as configurações e suas funções, consulte [Configurações de quiosque do Windows 10](kiosk-settings-windows.md) e [Configurações de quiosque do Windows Holographic for Business](kiosk-settings-holographic.md).

## <a name="create-the-profile"></a>Criar o perfil

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os Serviços** > filtre por **Intune** > selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar Perfil**.
3. Insira as seguintes propriedades:

   - **Nome**: insira um nome descritivo para o novo perfil.
   - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
   - **Plataforma**: Selecione **Windows 10 e posterior**
   - **Tipo de perfil**: Selecione **Quiosque**

4. Em **Configurações**, selecione um **modo de quiosque**. O **Modo de quiosque** identifica o tipo de modo de quiosque compatível com a política. As opções incluem:

    - **Não configurado** (padrão): A política não habilita o modo de quiosque.
    - **Quiosque de tela inteira e aplicativo único**: O dispositivo é executado como uma única conta de usuário e fica bloqueado com um único aplicativo da Loja. Assim, quando o usuário faz logon, um aplicativo específico inicia. Esse modo também impede que o usuário abrir novos aplicativos ou alterar o aplicativo em execução.
    - **Quiosque de vários aplicativos**: O dispositivo executa vários aplicativos da Loja, aplicativos Win32 ou aplicativos da caixa de entrada do Windows usando a AUMID (ID do modelo de usuário do aplicativo). Somente os aplicativos que você adiciona ficam disponíveis no dispositivo.

        O benefício de um quiosque de vários aplicativos ou de um dispositivo com finalidade fixa é proporcionar uma experiência fácil para os usuários ao possibilitar acesso somente aos aplicativos de que eles precisam. E também removendo da exibição os aplicativos de que eles não precisam.

    Para obter uma lista de todas as configurações e o que elas fazem, confira:
      - [Configurações de quiosque do Windows 10](kiosk-settings-windows.md)
      - [Configurações de quiosque do Windows Holographic for Business](kiosk-settings-holographic.md)

5. Quando terminar, selecione **OK** > **Criar** para salvar suas alterações. 

O perfil é criado e exibido na lista de perfis. Em seguida, [atribua](device-profile-assign.md) o perfil.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

Você pode criar perfis de quiosque para dispositivos que executam as seguintes plataformas:
- [Android](device-restrictions-android.md#kiosk)
- [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings)
- [Windows 10 e posterior](kiosk-settings-windows.md)
- [Windows Holographic for Business](kiosk-settings-holographic.md)
