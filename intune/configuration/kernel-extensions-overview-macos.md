---
title: Criar perfil de dispositivo de extensões de kernel macOS com o Microsoft Intune-Azure | Microsoft Docs
titleSuffix: ''
description: Adicione ou crie um perfil de dispositivo macOS e, em seguida, configure extensões de kernel para permitir substituição do usuário, adicionar identificador de equipe e um grupo e um identificador de equipe em Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9832089cf73405a9e39795b076e9ead84bc7d7cd
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734447"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>Adicionar extensões de kernel macOS no Intune

Em dispositivos macOS, você pode adicionar recursos no nível do kernel. Esses recursos acessam partes do sistema operacional que programas regulares não podem acessar. Sua organização pode ter necessidades ou requisitos específicos que não estão disponíveis em um aplicativo, um recurso de dispositivo e assim por diante. 

Para adicionar extensões de kernel que sempre têm permissão para carregar em seus dispositivos, adicione "extensões de kernel" (KEXT) em Microsoft Intune e, em seguida, implante essas extensões em seus dispositivos.

Por exemplo, você tem um programa de verificação de vírus que verifica o seu dispositivo em busca de conteúdo mal-intencionado. Você pode adicionar a extensão do kernel do programa de verificação de vírus como uma extensão de kernel permitida no Intune. Em seguida, "atribua" a extensão aos dispositivos macOS.

Com esse recurso, os administradores podem permitir que os usuários substituam as extensões do kernel, adicionem identificadores de equipe e adicionem extensões de kernel específicas no Intune.

Esse recurso aplica-se a:

- macOS 10.13.2 e posterior

Para usar esse recurso, os dispositivos devem ser:

- Registrado no Intune usando a DEP (Programa de registro de dispositivos da Apple). [Registrar dispositivos MacOS automaticamente](../enrollment/device-enrollment-program-enroll-macos.md) tem mais informações.

  OU

- Registrado no Intune com "registro aprovado pelo usuário" (termo da Apple). [Preparar para alterações em extensões de kernel no MacOS High Sierra](https://support.apple.com/en-us/HT208019) (abre o site da Apple) tem mais informações.

O Intune usa "perfis de configuração" para criar e personalizar essas configurações de acordo com as necessidades da sua organização. Depois de adicionar esses recursos em um perfil, você pode enviar por push ou implantar o perfil para dispositivos macOS em sua organização.

Este artigo mostra como criar um perfil de configuração de dispositivo usando extensões de kernel no Intune.

> [!TIP]
> Para obter mais informações sobre extensões de kernel, consulte [visão geral da extensão do kernel](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (abre o site da Apple).

## <a name="what-you-need-to-know"></a>O que você precisa saber

- Extensões de kernel herdadas não assinadas podem ser adicionadas.
- Certifique-se de inserir o identificador de equipe correto e a ID do pacote da extensão do kernel. O Intune não valida os valores inseridos. Se você inserir informações erradas, a extensão não funcionará no dispositivo.

> [!NOTE]
> A Apple lançou informações sobre assinatura e notarization para todos os softwares. No macOS 10.14.5 e mais recentes, as extensões de kernel implantadas por meio do Intune não precisam atender à política de notarization da Apple.
>
> Para obter informações sobre essa política de notarization e quaisquer atualizações ou alterações, consulte os seguintes recursos:
>
> - [Notarizing seu aplicativo antes da distribuição](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) (abre o site da Apple) 
> - [Preparar-se para alterações nas extensões de kernel no MacOS High Sierra](https://support.apple.com/en-us/HT208019) (abre o site da Apple)

## <a name="create-the-profile"></a>Criar o perfil

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: insira um nome descritivo para o novo perfil.
    - **Descrição:** insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: selecione **macOS**
    - **Tipo de perfil**: selecione **extensões**.
    - **Configurações**: insira as configurações que você deseja definir. Para obter uma lista de todas as configurações e o que elas fazem, confira:

        - [macOS](kernel-extensions-settings-macos.md)

4. Quando terminar, selecione **OK** > **Criar** para salvar suas alterações.

O perfil é criado e exibido na lista. [Atribua o perfil](../device-profile-assign.md) e [monitore seu status](../device-profile-monitor.md).

## <a name="next-steps"></a>Próximas etapas

Depois que o perfil é criado, ele está pronto para ser atribuído. Em seguida, [atribua o perfil](../device-profile-assign.md) e [monitore seu status](../device-profile-monitor.md).