---
title: "Criar perfis de configuração do dispositivo do Intune | Visualização do Intune Azure"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como criar perfis de configuração de dispositivo do Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 17c5649e7ece5becd17e8ef9a74d748b6202693f
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Como criar perfis de configuração do dispositivo no Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
2. Na folha que mostra a lista de perfis, escolha **Criar Perfil**.
3. Na folha **Criar Perfil**, especifique o seguinte:
    - **Nome** – Insira um nome descritivo para o novo perfil.
    - **Descrição** – Insira uma descrição opcional para o perfil.
    - **Plataforma** – Selecione o tipo de plataforma para o perfil que você deseja criar.
    - **Tipo de perfil** – Selecione o tipo de perfil que você deseja criar. A lista de tipos disponíveis varia dependendo da plataforma que você escolheu.
    - **Configurações** – Consulte os seguintes tópicos para obter informações sobre as configurações para cada tipo de perfil:
        -  [Configurações de recurso do dispositivo](/intune-azure/configure-devices/how-to-configure-device-features)
        -  [Configurações de restrição de dispositivo](/intune-azure/configure-devices/how-to-configure-device-restrictions)
        -  [Configurações de email](/intune-azure/configure-devices/how-to-configure-email-settings)
        -  [Configurações de VPN](/intune-azure/configure-devices/how-to-configure-vpn-settings)
        -  [Configurações de Wi-Fi](/intune-azure/configure-devices/how-to-configure-wi-fi-settings)
        -  [Configurações de atualização da edição do Windows 10](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade)
        -  [Configurações do certificado](/intune-azure/configure-devices/how-to-configure-certificates)
        -  [Definir a Proteção de Informações do Windows](/intune-azure/configure-devices/how-to-configure-windows-information-protection)
        -  [Configurações de educação](/intune-azure/configure-devices/how-to-configure-education-settings)
        -  [Configurações personalizadas](/intune-azure/configure-devices/how-to-configure-custom-settings)

    ![Criar perfil de dispositivo](./media/create-device-profile.png)
4. Depois de terminar de definir as configurações, na folha **Criar Perfil**, escolha **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](how-to-assign-device-profiles.md).


### <a name="next-steps"></a>Próximas etapas
Para obter informações sobre como atribuir perfis de dispositivo, consulte [Como atribuir perfis de dispositivos com o Microsoft Intune](/intune-azure/configure-devices/how-to-assign-device-profiles).

