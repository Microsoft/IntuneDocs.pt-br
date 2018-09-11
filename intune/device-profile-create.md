---
title: Criar perfis de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou configure um perfil de dispositivo no Microsoft Intune, incluindo a seleção do tipo de plataforma e a definição das configurações no Portal do Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7195b9d2d64c2282f2380624a209ad45220d3a4f
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313931"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Criar um perfil de dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Criar o perfil
1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços** e pesquise o **Microsoft Intune**.

2. No **Microsoft Intune**, selecione **Configuração do dispositivo** e selecione **Perfis**. Em seguida, selecione **Criar Perfil**.

3. Digite as seguintes propriedades:

   - **Nome**: insira um nome descritivo para o novo perfil.
   - **Descrição:** insira uma descrição para o perfil. (Isso é opcional, mas recomendado.)
   - **Plataforma**: selecione o tipo de plataforma:  

       - **Android**
       - **Perfis de trabalho Android**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 e posterior**
       - **Windows 10 e posterior**

   - **Tipo de perfil**: selecione o tipo que você deseja criar. A lista dependerá da plataforma que você escolher.
   - **Configurações**: os tópicos a seguir descrevem as configurações para cada tipo de perfil:

       -  [Recursos de dispositivo](device-features-configure.md)
       -  [Restrições de dispositivo](device-restrictions-configure.md)
       -  [Endpoint protection](endpoint-protection-configure.md)
       -  [Proteção de identidade](identity-protection-configure.md)  
       -  [Quiosque](kiosk-settings.md)
       -  [Email](email-settings-configure.md)
       -  [VPN](vpn-settings-configure.md)
       -  [Wi-Fi](wi-fi-settings-configure.md)
       -  Educação para [Windows 10](education-settings-configure.md) e [iOS](wi-fi-settings-ios.md)
       -  [Atualização de edição do Windows 10](edition-upgrade-configure-windows-10.md)
       -  [Políticas de atualização do iOS](software-updates-ios.md)
       -  [Certificados](certificates-configure.md)
       -  [Proteção de Informações do Windows](windows-information-protection-configure.md)
       -  [Personalizado](custom-settings-configure.md)

     ![Captura de tela de criação de perfil](./media/create-device-profile.png)

4. Selecione **Criar** quando terminar.

O perfil será criado e aparecerá na lista.

## <a name="next-steps"></a>Próximas etapas
[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
