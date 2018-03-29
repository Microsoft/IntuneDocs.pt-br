---
title: Criar perfis de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou configure um perfil de dispositivo no Microsoft Intune, incluindo a seleção do tipo de plataforma e a definição das configurações no Portal do Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e5070052c0d4cce3cfd81a7bae259bc7dfb22e7f
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/20/2018
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Criar um perfil de dispositivo no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Criar o perfil
1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços** e pesquise o **Microsoft Intune**.

2. No **Microsoft Intune**, selecione **Configuração do dispositivo** e selecione **Perfis**. Em seguida, selecione **Criar Perfil**.

3. Digite as seguintes propriedades:

    - **Nome**: insira um nome descritivo para o novo perfil.
    - **Descrição:** insira uma descrição para o perfil. (Isso é opcional, mas recomendado.)
    - **Plataforma**: selecione o tipo de plataforma:  

        - **Android**
        - **Android for Work**
        - **iOS**
        - **macOS**
        - **Windows Phone 8.1**
        - **Windows 8.1 e posterior**
        - **Windows 10 e posterior**

    - **Tipo de perfil**: selecione o tipo que você deseja criar. A lista dependerá da plataforma que você escolher.
    - **Configurações**: os tópicos a seguir descrevem as configurações para cada tipo de perfil:

        -  [Configurações de recurso do dispositivo](device-features-configure.md)
        -  [Configurações de restrição de dispositivo](device-restrictions-configure.md)
        -  [Configurações de email](email-settings-configure.md)
        -  [Configurações de VPN](vpn-settings-configure.md)
        -  [Configurações de Wi-Fi](wi-fi-settings-configure.md)
        -  [Configurações de atualização da edição do Windows 10](edition-upgrade-configure-windows-10.md)
        -  [Configurações do certificado](certificates-configure.md)
        -  [Definir a Proteção de Informações do Windows](windows-information-protection-configure.md)
        -  [Configurações de educação](education-settings-configure.md)
        -  [Configurações personalizadas](custom-settings-configure.md)

    ![Captura de tela de criação de perfil](./media/create-device-profile.png)

4. Selecione **Criar** quando terminar.

O perfil será criado e aparecerá na lista.


## <a name="next-steps"></a>Próximas etapas
Para atribuir perfis de dispositivo, consulte [Como atribuir perfis de dispositivo com o Microsoft Intune](device-profile-assign.md).
