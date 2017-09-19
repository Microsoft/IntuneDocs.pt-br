---
title: "Criar perfis de configuração de dispositivo do Intune"
titlesuffix: Azure portal
description: "Saiba como criar perfis de configuração de dispositivo do Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 05/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ab7a2f905a7eec33204516e07f0a5d2cda4e1d95
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Como criar perfis de configuração do dispositivo no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
2. Na folha que mostra a lista de perfis, escolha **Criar Perfil**.
3. Na folha **Criar Perfil**, especifique os seguintes itens:
    - **Nome** – Insira um nome descritivo para o novo perfil.
    - **Descrição** – Insira uma descrição opcional para o perfil.
    - **Plataforma** – Selecione o tipo de plataforma para o perfil que você deseja criar.
    - **Tipo de perfil** – Selecione o tipo de perfil que você deseja criar. A lista de tipos disponíveis varia dependendo da plataforma escolhida.
    - **Configurações** – Consulte os seguintes tópicos para obter informações sobre as configurações para cada tipo de perfil:
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

    ![Criar perfil de dispositivo](./media/create-device-profile.png)
4. Depois de terminar de definir as configurações, na folha **Criar Perfil**, escolha **Criar**.

O perfil é criado e exibido na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).


### <a name="next-steps"></a>Próximas etapas
Para obter informações sobre como atribuir perfis de dispositivo, consulte [Como atribuir perfis de dispositivos com o Microsoft Intune](device-profile-assign.md).
