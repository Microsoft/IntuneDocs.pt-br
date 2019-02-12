---
title: Configurações de otimização de entrega para Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Configure o modo como as atualizações de software são entregues para seus dispositivos usando os serviços de nuvem de otimização de entrega disponíveis nos dispositivos com Windows 10 e posteriores. No Intune, crie um perfil de configuração de dispositivo para instalar as atualizações da Internet. Veja também como substituir os anéis de atualização existentes com um perfil de otimização de entrega.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f335c8acf9e979366fe75d1a3da2318b7ec46400
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55836686"
---
# <a name="windows-10-and-newer-delivery-optimization-settings-in-microsoft-intune"></a>Configurações de otimização de entrega do Windows 10 (e mais recentes) no Microsoft Intune

> [!NOTE]
> **Atualizações de software > Anéis de Atualização do Windows 10** é substituído pelas configurações de **Otimização de entrega**. Seus anéis de atualização existentes podem ser alterados para usar as configurações de **Otimização de entrega**. [Mover os anéis de atualização existentes para otimização da entrega](#move-existing-update-rings-to-delivery-optimization) (neste artigo) lista as etapas. 


Esse recurso se aplica às seguintes plataformas:

- Windows 10 e posterior

Este artigo lista e descreve todas as configurações de otimização de entrega que é possível configurar para dispositivos com Windows 10. Essas configurações são adicionadas a um perfil de configuração do dispositivo e, em seguida, atribuídas ou implantadas em seus dispositivos usando o Microsoft Intune.

[Atualizações de otimização de entrega](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) é um excelente recurso para saber mais sobre a otimização de entrega no Windows 10.

## <a name="create-the-profile"></a>Criar o perfil

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os Serviços** > filtre por **Intune** > selecione **Intune**.

2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar Perfil**.

3. Insira as seguintes propriedades:

    - **Nome**: insira um nome descritivo para o novo perfil.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Escolha a plataforma:  

        - **Windows 10 e posterior**

    - **Tipo de perfil**: Escolha **Otimização da entrega**.
    - **Configurações**: Escolha como você deseja que as atualizações sejam baixadas. Suas opções: 

        - **Não configurado**: Os usuários finais atualizam seus dispositivos usando seus próprios métodos, que podem ser pelas configurações do **Windows Update** ou de **Otimização de Entrega** que acompanham o sistema operacional.
        - **HTTP apenas, sem emparelhamento**: Obtenha atualizações somente pela Internet. Não receber atualizações de outros computadores na sua rede (chamado de emparelhamento ou ponto a ponto).
        - **HTTP combinado com emparelhamento por trás do mesmo NAT**: Obtenha as atualizações pela Internet e por outros computadores na sua rede. 
        - **HTTP combinado com emparelhamento em um grupo privado**: O emparelhamento ocorre em dispositivos no mesmo Site do Active Directory (se houver) ou no mesmo domínio. Quando essa opção está selecionada, o emparelhamento cruza seus endereços IP de conversão de endereços de rede (NATs).
        - **HTTP combinado com emparelhamento de Internet**: Obtenha as atualizações pela Internet e por outros computadores na sua rede.
        - **Modo de download simples sem emparelhamento**: Obtém atualizações pela Internet, diretamente do proprietário da atualização, como a Microsoft. Não entra em contato com os serviços de nuvem de otimização de entrega.
        - **Modo bypass**: Use a otimização do BITS (Serviço de Transferência Inteligente em Segundo Plano) para receber atualizações. Não use a otimização de entrega.

4. Quando terminar, selecione **OK** > **Criar** para salvar as alterações.

O perfil será criado e exibido na lista. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Mover os anéis de atualização existentes para otimização da entrega

**Atualizações de software > Anéis de Atualização do Windows 10** é substituído pelas configurações de **Otimização de entrega**. Seus anéis de atualização existentes podem ser facilmente alterados para usar as configurações de **Otimização de entrega**. Etapas:

1. Crie um perfil de configuração de otimização de entrega:

    1. No Intune, selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
    2. Insira as seguintes propriedades:

        - **Nome**: insira um nome descritivo para o novo perfil.
        - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
        - **Plataforma**: Selecione **Windows 10 e posterior**.
        - **Tipo de perfil**: Escolha **Otimização da entrega**.
        - **Configurações**: Para **Modo de download de otimização de entrega**, escolha o mesmo modo usado pelo anel de atualização de software existente. Suas opções:
            - **Não configurado**
            - **HTTP apenas, sem emparelhamento**
            - **HTTP combinado com emparelhamento por trás do mesmo NAT**
            - **HTTP combinado com emparelhamento em um grupo privado**
            - **HTTP combinado com emparelhamento de Internet**
            - **Modo de download simples sem emparelhamento**
            - **Modo bypass**

2. Atribua esse perfil novo aos mesmos dispositivos e usuários que o anel de atualização de software existente. [Atribuir o perfil](device-profile-assign.md) lista as etapas.

3. Desconfigure o anel de software existente:
    1. No Intune, acesse **Atualizações de software** > Anéis de atualização do Windows 10.
    2. Na lista, selecione o anel de atualização.
    3. Nas configurações, defina o **Modo de download de otimização da entrega** como **Não configurado**.
    4. **OK** > **Salve** suas alterações.

## <a name="next-steps"></a>Próximas etapas

[Atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).
