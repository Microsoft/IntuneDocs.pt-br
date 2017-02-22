---
title: "Criar perfis de configuração do dispositivo do Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba como criar perfis de configuração de dispositivo do Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: 6c6ac8112a6b6413df635607a24d0d06466c0b88


---

# <a name="how-to-create-device-configuration-profiles"></a>Como criar perfis de configuração de dispositivo 

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
        -  [Configurações de restrição de dispositivo](/intune-azure/configure-devices/how-to-configure-device-restrictions)
        -  [Configurações de email](/intune-azure/configure-devices/how-to-configure-email-settings)
        -  [Configurações de VPN](/intune-azure/configure-devices/how-to-configure-vpn-settings)
        -  [Configurações de Wi-Fi](/intune-azure/configure-devices/how-to-configure-wi-fi-settings)
        -  [Configurações de atualização da edição do Windows 10](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade)
        -  [Configurações do certificado](/intune-azure/configure-devices/how-to-configure-certificates)
        -  [Definir a Proteção de Informações do Windows](/intune-azure/configure-devices/how-to-configure-windows-information-protection)
        -  [Configurações de educação](/intune-azure/configure-devices/education-settings-for-ios.md)
        -  [Configurações personalizadas](/intune-azure/configure-devices/how-to-configure-custom-settings)

    ![Criar perfil de dispositivo](./media/create-device-profile.png)
4. Depois de terminar de definir as configurações, na folha **Criar Perfil**, escolha **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](how-to-assign-device-profiles.md).


### <a name="next-steps"></a>Próximas etapas
Para obter informações sobre como atribuir perfis de dispositivo, consulte [Como atribuir perfis de dispositivos com o Microsoft Intune](/intune-azure/configure-devices/how-to-assign-device-profiles).



<!--HONumber=Feb17_HO1-->


