---
title: Configurações de otimização de entrega para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Configure como os dispositivos Windows 10 que você gerencia com o Intune usam a otimização de entrega. No Intune, crie um perfil de configuração de dispositivo para instalar as atualizações da Internet. Veja também como substituir os anéis de atualização existentes com um perfil de otimização de entrega.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/10/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: 9fb4aab6b02c6ad6a5d2f18ca9d15beafc12d58a
ms.sourcegitcommit: e1ff157f692983b49bdd6e20cc9d0f93c3b3733c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124802"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Configurações de otimização de entrega no Microsoft Intune

Com o Intune, use configurações de otimização de entrega para seus dispositivos Windows 10 reduzirem o consumo de largura de banda quando baixarem aplicativos e atualizações. Configure a otimização de entrega como parte dos perfis de configuração do dispositivo.  

Este artigo descreve como configurar a otimização de entrega como parte de um perfil de configuração do dispositivo. Após criar um perfil, você atribuirá ou o implantará em seus dispositivos Windows 10. 

Para ver uma lista das configurações de otimização de entrega compatíveis com o Intune, confira [Configurações de otimização de entrega para o Intune](../delivery-optimization-settings.md).  

Para conhecer a Otimização de entrega no Windows 10, confira [Atualizações de otimização de entrega](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) na documentação do Windows.  

## <a name="create-the-profile"></a>Criar o perfil

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.

3. Insira as seguintes propriedades:

    - **Nome**: insira um nome descritivo para o novo perfil.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Selecione **Windows 10 e posterior**.
    - **Tipo de perfil**: Escolha **Otimização da entrega**.

4. Escolha **Configurações** > **Configurar** e defina como você deseja que as atualizações e aplicativos sejam baixados. Para saber mais sobre as configurações disponíveis, confira [Configurações de otimização de entrega para o Intune](../delivery-optimization-settings.md).

5. Quando terminar, selecione **OK** > **Criar** para salvar as alterações.

O perfil é criado e aparece na lista. Em seguida, [atribua o perfil](device-profile-assign.md) e, em seguida, [monitore seu status](device-profile-monitor.md).

<!-- ## Move existing update rings to delivery optimization

**Delivery optimization** settings replace **Software updates – Windows 10 Update Rings**. Your existing update rings can be easily changed to use the **Delivery optimization** settings. To maintain the same settings when you create a delivery optimization profile, use the same *Delivery optimization download mode* and then set the same settings as you already use. However, you can choose to reconfigure delivery optimization settings to take advantage of the full range of addition settings that the Delivery Optimization profile can manage. 
-->

## <a name="remove-delivery-optimization-from-windows-10-update-rings"></a>Remover a otimização de entrega dos anéis de atualização do Windows 10

A otimização de entrega foi configurada anteriormente como parte dos anéis de atualização de software. A partir de fevereiro de 2019, as configurações de otimização de entrega serão configuradas como parte de um perfil de configuração de dispositivo de otimização de entrega, que inclui configurações adicionais que afetam mais do que a entrega de atualização de software para dispositivos. Se você ainda não fez isso, remova a configuração de otimização de entrega de seus anéis de atualização definindo-a como *Não configurada* e, em seguida, use um perfil de otimização de entrega para gerenciar a maior variedade de opções disponíveis.

1. Crie um perfil de configuração de dispositivo de otimização de entrega:

    1. No centro de administração do Gerenciador de Ponto de Extremidade da Microsoft, selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
    2. Insira as seguintes propriedades:

        - **Nome**: insira um nome descritivo para o novo perfil.
        - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
        - **Plataforma**: Selecione **Windows 10 e posterior**.
        - **Tipo de perfil**: Escolha **Otimização da entrega**.
        - **Configurações**: Para **Modo de download de otimização de entrega**, escolha o mesmo modo usado pelo anel de atualização de software existente, a menos que você deseje alterar as configurações aplicáveis a seus dispositivos. Suas opções:
            - **Não configurado**
            - **HTTP apenas, sem emparelhamento**
            - **HTTP combinado com emparelhamento por trás do mesmo NAT**
            - **HTTP combinado com emparelhamento em um grupo privado**
            - **HTTP combinado com emparelhamento de Internet**
            - **Modo de download simples sem emparelhamento**
            - **Modo bypass**
    3. Defina outras configurações adicionais que você deseja gerenciar.

2. Atribua esse perfil novo aos mesmos dispositivos e usuários que o anel de atualização de software existente. [Atribuir o perfil](device-profile-assign.md) lista as etapas.

3. Desconfigure o anel de software existente:
    1. No centro de administração do Gerenciador de Ponto de Extremidade da Microsoft, acesse **Atualizações de software** > Anéis de atualização do Windows 10.
    2. Na lista, selecione o anel de atualização.
    3. Nas configurações, defina o **Modo de download de otimização da entrega** como **Não configurado**.
    4. **OK** > **Salve** suas alterações.

## <a name="next-steps"></a>Próximas etapas

[Atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).  
Exiba as [configurações de otimização de entrega](../delivery-optimization-settings.md) para o Intune.
