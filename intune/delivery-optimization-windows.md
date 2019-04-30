---
title: Configurações de otimização de entrega para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Configure como os dispositivos Windows 10 que você gerencia com o Intune usam a otimização de entrega. No Intune, crie um perfil de configuração de dispositivo para instalar as atualizações da Internet. Veja também como substituir os anéis de atualização existentes com um perfil de otimização de entrega.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/12/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: 45d91766b3bbdcdd3528afd80d74a56a94e88a2c
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61510190"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Configurações de otimização de entrega no Microsoft Intune

Com o Intune, é possível usar Configurações de otimização de entrega para seus dispositivos Windows 10 reduzirem o consumo de largura de banda quando baixarem aplicativos e atualizações. A otimização de entrega é configurada como parte dos perfis de configuração do dispositivo.  

Este artigo descreve como configurar a otimização de entrega como parte de um perfil de configuração do dispositivo. Após criar um perfil, você atribuirá ou o implantará em seus dispositivos Windows 10. 

Para obter uma lista das configurações de otimização de entrega com suporte pelo Intune, confira [Configurações de otimização de entrega para o Intune](delivery-optimization-settings.md).  

Para conhecer a Otimização de entrega no Windows 10, confira [Atualizações de otimização de entrega](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) na documentação do Windows.  


> [!NOTE]
> **Atualizações de software > Anéis de Atualização do Windows 10** é substituído pelas configurações de **Otimização de entrega**. Seus anéis de atualização existentes podem ser alterados para usar as configurações de **Otimização de entrega**. [Mover os anéis de atualização existentes para otimização da entrega](#move-existing-update-rings-to-delivery-optimization) (neste artigo) 
## <a name="create-the-profile"></a>Criar o perfil

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os Serviços** > filtre por **Intune** > selecione **Intune**.

2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar Perfil**.

3. Insira as seguintes propriedades:

    - **Nome**: insira um nome descritivo para o novo perfil.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Escolha a plataforma:  

        - **Windows 10 e posterior**

    - **Tipo de perfil**: Escolha **Otimização da entrega**.
    - **Configurações**: configure como você deseja que as atualizações e aplicativos sejam baixados. Para saber mais sobre as configurações disponíveis, confira [Configurações de otimização de entrega para o Intune](delivery-optimization-settings.md).

4. Quando terminar, selecione **OK** > **Criar** para salvar as alterações.

O perfil é criado e aparece na lista. Em seguida, [atribua o perfil](device-profile-assign.md) e, em seguida, [monitore seu status](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Mover os anéis de atualização existentes para otimização da entrega

As configurações de **Otimização de entrega** substituem as **Atualizações do software – Anéis de Atualização do Windows 10**. Seus anéis de atualização existentes podem ser facilmente alterados para usar as configurações de **Otimização de entrega**. Para manter as mesmas configurações quando você criar um perfil de otimização de entrega, use o mesmo *Modo de download de otimização de entrega* e defina as mesmas configurações que você já usa. No entanto, é possível optar por definir novamente as configurações de otimização de entrega para aproveitar a gama completa de configurações adicionais que podem ser gerenciadas pelo perfil de Otimização de entrega.

1. Crie um perfil de configuração de otimização de entrega:

    1. No Intune, selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
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
1. Atribua esse perfil novo aos mesmos dispositivos e usuários que o anel de atualização de software existente. [Atribuir o perfil](device-profile-assign.md) lista as etapas.

3. Desconfigure o anel de software existente:
    1. No Intune, acesse **Atualizações de software** > Anéis de atualização do Windows 10.
    2. Na lista, selecione o anel de atualização.
    3. Nas configurações, defina o **Modo de download de otimização da entrega** como **Não configurado**.
    4. **OK** > **Salve** suas alterações.

## <a name="next-steps"></a>Próximas etapas

[Atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).  
Exiba as [configurações de otimização de entrega](delivery-optimization-settings.md) para o Intune.
