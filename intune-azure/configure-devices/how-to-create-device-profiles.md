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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 74a905ed2ba9ec04ae14df96fcd3f6b6caf1241c
ms.contentlocale: pt-br
ms.lasthandoff: 05/10/2017


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
        -  [Configurações de recurso do dispositivo](how-to-configure-device-features.md)
        -  [Configurações de restrição de dispositivo](how-to-configure-device-restrictions.md)
        -  [Configurações de email](how-to-configure-email-settings.md)
        -  [Configurações de VPN](how-to-configure-vpn-settings.md)
        -  [Configurações de Wi-Fi](how-to-configure-wi-fi-settings.md)
        -  [Configurações de atualização da edição do Windows 10](how-to-configure-windows-10-edition-upgrade.md)
        -  [Configurações do certificado](how-to-configure-certificates.md)
        -  [Definir a Proteção de Informações do Windows](how-to-configure-windows-information-protection.md)
        -  [Configurações de educação](how-to-configure-education-settings.md)
        -  [Configurações personalizadas](how-to-configure-custom-settings.md)

    ![Criar perfil de dispositivo](./media/create-device-profile.png)
4. Depois de terminar de definir as configurações, na folha **Criar Perfil**, escolha **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](how-to-assign-device-profiles.md).


### <a name="next-steps"></a>Próximas etapas
Para obter informações sobre como atribuir perfis de dispositivo, consulte [Como atribuir perfis de dispositivos com o Microsoft Intune](how-to-assign-device-profiles.md).

