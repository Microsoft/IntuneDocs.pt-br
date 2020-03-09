---
title: Criar um perfil de dispositivo de extensões de kernel do macOS com o Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Adicione ou crie um perfil de dispositivo macOS e, em seguida, configure extensões de kernel para permitir a substituição de usuário, adicionar um identificador de equipe e um pacote e um identificador de equipe no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/25/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f8a516ce9dda525d5c7a48fcbc2c799471489d0d
ms.sourcegitcommit: ff254acb94df88afc3e3e7b878084052adf40745
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77600239"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>Adicionar extensões de kernel macOS no Intune

> [!NOTE]
> As extensões de kernel macOS estão sendo substituídas pelas extensões do sistema. Para obter mais informações, confira [Dica de suporte: como usar extensões de sistema em vez de extensões de kernel para macOS Catalina 10.15 no Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/support-tip-using-system-extensions-instead-of-kernel-extensions/ba-p/1191413).

Em dispositivos macOS, você pode adicionar recursos no nível do kernel. Esses recursos acessam partes do sistema operacional que os programas normais não podem acessar. Sua organização pode ter necessidades ou requisitos específicos que não estejam disponíveis em um aplicativo, um recurso de dispositivo etc. 

Para adicionar extensões de kernel que sempre podem ser carregadas em seus dispositivos, adicione "extensões de kernel" (KEXT) no Microsoft Intune e, em seguida, implante essas extensões nos dispositivos.

Por exemplo, você tem um programa de verificação de vírus que examina o dispositivo em busca de conteúdo mal-intencionado. Você pode adicionar a extensão de kernel do programa de verificação de vírus como uma extensão de kernel permitida no Intune. Em seguida, "atribua" a extensão aos dispositivos macOS.

Com esse recurso, os administradores podem permitir que os usuários substituam as extensões do kernel, adicionem identificadores de equipe e adicionem extensões de kernel específicas no Intune.

Esse recurso aplica-se a:

- macOS 10.13.2 e posterior

Para usar esse recurso, os dispositivos precisam ser:

- Registrados no Intune usando o DEP (Programa de registro de dispositivos) da Apple. O artigo [Registrar dispositivos macOS automaticamente](../enrollment/device-enrollment-program-enroll-macos.md) traz mais informações.

  OU

- Registrados no Intune com o "registro aprovado pelo usuário" (termo da Apple). O artigo [Preparar-se para as alterações nas extensões de kernel no macOS High Sierra](https://support.apple.com/en-us/HT208019) (abre o site da Apple) traz mais informações.

O Intune usa "perfis de configuração" para criar e personalizar essas configurações de acordo com as necessidades da sua organização. Depois de adicionar esses recursos em um perfil, você pode enviar por push ou implantar o perfil para dispositivos macOS em sua organização.

Este artigo mostra como criar um perfil de configuração de dispositivo usando extensões de kernel no Intune.

> [!TIP]
> Para obter mais informações sobre extensões de kernel, confira [Visão geral da extensão de kernel](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (abre o site da Apple).

## <a name="what-you-need-to-know"></a>O que você precisa saber

- As extensões de kernel herdadas não assinadas podem ser adicionadas.
- Lembre-se de inserir o identificador de equipe correto e a ID do pacote da extensão de kernel. O Intune não confirma os valores inseridos. Se você inserir informações incorretas, a extensão não funcionará no dispositivo. Um identificador de equipe tem exatamente 10 caracteres alfanuméricos. 

> [!NOTE]
> A Apple lançou informações sobre assinatura e autenticação para todos os programas de software. No macOS 10.14.5 e mais recente, as extensões de kernel implantadas por meio do Intune não precisam atender à política de autenticação da Apple.
>
> Para obter informações sobre essa política de autenticação e as atualizações ou as alterações, confira os seguintes recursos:
>
> - [Como autenticar seu aplicativo antes da distribuição](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) (abre o site da Apple) 
> - [Preparar-se para as alterações nas extensões de kernel no macOS High Sierra](https://support.apple.com/en-us/HT208019) (abre o site da Apple)

## <a name="create-the-profile"></a>Criar o perfil

1. Entre no [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: insira um nome descritivo para o novo perfil.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Selecione **macOS**
    - **Tipo de perfil**: Selecione **Extensões**.
    - **Configurações**: Insira as configurações que você deseja definir. Para obter uma lista de todas as configurações e o que elas fazem, confira:

        - [macOS](kernel-extensions-settings-macos.md)

4. Quando terminar, selecione **OK** > **Criar** para salvar suas alterações.

O perfil é criado e exibido na lista. [Atribua o perfil](../device-profile-assign.md) e [monitore seu status](../device-profile-monitor.md).

## <a name="next-steps"></a>Próximas etapas

Depois que o perfil é criado, ele está pronto para ser atribuído. Em seguida, [atribua o perfil](../device-profile-assign.md) e [monitore seu status](../device-profile-monitor.md).
