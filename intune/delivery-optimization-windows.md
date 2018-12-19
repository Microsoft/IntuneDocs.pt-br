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
ms.openlocfilehash: 1b83a380620704e9e3f616cee77b33d577c86c0d
ms.sourcegitcommit: 88f760abcea7348a0c6d00b533b54a6ff68d3985
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2018
ms.locfileid: "52977262"
---
# <a name="windows-10-and-newer-delivery-optimization-settings-in-microsoft-intune"></a>Configurações de otimização de entrega do Windows 10 (e mais recentes) no Microsoft Intune

Este artigo lista e descreve todas as configurações de otimização de entrega que é possível configurar para dispositivos com Windows 10. Essas configurações são adicionadas a um perfil de configuração do dispositivo e, em seguida, atribuídas ou implantadas em seus dispositivos usando o Microsoft Intune. 

[Atualizações de otimização de entrega](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) é um excelente recurso para saber mais sobre a otimização de entrega no Windows 10.

## <a name="settings"></a>Configurações

**Modo de download de otimização de entrega**: Escolha como as atualizações são entregues aos seus dispositivos. Suas opções:

- **Não configurado**: Os usuários finais atualizam seus dispositivos usando seus próprios métodos, que podem ser pelas configurações do **Windows Update** ou de **Otimização de Entrega** que acompanham o sistema operacional.
- **HTTP apenas, sem emparelhamento**: Obtenha atualizações somente pela Internet. Não receber atualizações de outros computadores na sua rede (chamado de emparelhamento ou ponto a ponto).
- **HTTP combinado com emparelhamento por trás do mesmo NAT HTTP combinado com emparelhamento em um grupo privado**: Obtenha as atualizações pela Internet e por outros computadores na sua rede. O emparelhamento ocorre em dispositivos no mesmo Site do Active Directory (se houver) ou no mesmo domínio. Quando essa opção está selecionada, o emparelhamento cruza seus endereços IP de conversão de endereços de rede (NATs).
- **HTTP combinado com emparelhamento de Internet**: Obtenha as atualizações pela Internet e por outros computadores na sua rede.
- **Modo de download simples sem emparelhamento**: Obtém atualizações pela Internet, diretamente do proprietário da atualização, como a Microsoft. Não entra em contato com os serviços de nuvem de otimização de entrega.
- **Modo bypass**: Use a otimização do BITS (Serviço de Transferência Inteligente em Segundo Plano) para receber atualizações. Não use a otimização de entrega.

## <a name="move-from-existing-update-rings-to-delivery-optimization"></a>Mover de anéis de atualização existentes para otimização de entrega

**Atualizações de software > Anéis de Atualização do Windows 10** é substituído pelas configurações de **Otimização de entrega**. Seus anéis de atualização existentes podem ser facilmente alterados para usar as configurações de **Otimização de entrega**. Etapas:

1. Crie um perfil de configuração de otimização de entrega:

    1. No Intune, selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
    2. Digite um **Nome** e uma **Descrição** para o perfil.
    3. Para **Plataforma**, escolha **Windows 10 e posterior**. Para **Tipo de perfil**, escolha **Otimização de entrega**.
    4. Selecione **Configurações**. Para **Modo de download de otimização de entrega**, escolha o mesmo modo usado pelo anel de atualização de software existente. Suas opções:
        - **Não configurado**
        - **HTTP apenas, sem emparelhamento**
        - **HTTP combinado com emparelhamento por trás do mesmo NAT HTTP combinado com emparelhamento em um grupo privado**
        - **HTTP combinado com emparelhamento de Internet**
        - **Modo de download simples sem emparelhamento**
        - **Modo bypass**

2. Atribua esse perfil novo aos mesmos dispositivos e usuários que o anel de atualização de software existente. [Atribuir o perfil](device-profile-assign.md) lista as etapas.

3. Desconfigure o anel de software existente:
    1. No Intune, acesse **Atualizações de software** > Anéis de atualização do Windows 10.
    2. Na lista, selecione o anel de atualização.
    3. Nas configurações, defina o **Modo de download de otimização de entrega** como **Não configurado**.
    4. **OK** > **Salve** suas alterações.

## <a name="next-steps"></a>Próximas etapas

[Atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).
