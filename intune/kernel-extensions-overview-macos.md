---
title: Criar perfil de dispositivo de extensões do kernel do macOS com o Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Adicionar ou criar um macOS perfil de dispositivo e, em seguida, configurar as extensões de kernel para permitir a substituição do usuário, adicione o identificador de equipe e um identificador de pacote e a equipe no Microsoft Intune.
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
ms.openlocfilehash: fd2e03c09cb2bed49ee7607283bf63e2c3ae67da
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67403900"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>Adicionar extensões de kernel do macOS no Intune

Em dispositivos macOS, você pode adicionar recursos no nível do kernel. Esses recursos acessar partes do sistema operacional que não é possível acessar a programas normais. Sua organização pode ter necessidades específicas ou requisitos que não estão disponíveis em um aplicativo, um recurso de dispositivo e assim por diante. 

Para adicionar extensões de kernel que sempre têm permissão para carregar em seus dispositivos, adicione "extensões de kernel" (KEXT) no Microsoft Intune e, em seguida, implantar essas extensões em seus dispositivos.

Por exemplo, você tem um programa antivírus que examina o dispositivo quanto a conteúdo malicioso. Você pode adicionar essa extensão de kernel do programa antivírus como uma extensão de kernel permitidos no Intune. Em seguida, "atribua" a extensão para os dispositivos macOS.

Com esse recurso, os administradores podem permitir que os usuários substituam as extensões de kernel, adicione os identificadores de equipe e adicionar extensões específicas de kernel no Intune.

Esse recurso aplica-se a:

- macOS 10.13.2 e posterior

Para usar esse recurso, os dispositivos devem ser:

- Registrado no Intune usando o programa de registro de dispositivo (DEP) da Apple. [Registrar automaticamente dispositivos macOS](device-enrollment-program-enroll-macos.md) tem mais informações.

  OU

- Registrado no Intune com o "registro do usuário aprovado" (termos da Apple). [Preparar-se para a extensões de kernel no macOS High Sierra](https://support.apple.com/en-us/HT208019) (abre o site da Apple) tem mais informações.

O Intune usa "perfis de configuração" para criar e personalizar essas configurações de acordo com as necessidades da sua organização. Depois de adicionar esses recursos em um perfil, você pode enviar por push ou implantar o perfil para dispositivos macOS em sua organização.

Este artigo mostra como criar um perfil de configuração de dispositivo usando extensões de kernel no Intune.

> [!TIP]
> Para obter mais informações sobre extensões de kernel, consulte [visão geral da extensão de kernel](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (abre o site da Apple).

## <a name="what-you-need-to-know"></a>O que você precisa saber

- Extensões de kernel herdado não assinados podem ser adicionadas.
- Certifique-se de inserir o identificador de equipe correta e a ID da extensão do kernel do pacote. Intune não valida os valores inseridos. Se você inserir informações erradas, a extensão não funcionará no dispositivo.

> [!NOTE]
> Apple lançou informações sobre assinatura e a autenticação para todos os softwares. No macOS 10.14.5 e o kernel mais recente, as extensões implantadas por meio do Intune não tem para atender à política de autenticação da Apple.
>
> Para obter informações sobre esta política de autenticação e todas as atualizações ou alterações, consulte os seguintes recursos:
>
>  - [Notarizing seu aplicativo antes da distribuição](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) (abre o site da Apple) 
>  - [Preparar-se para a extensões de kernel no macOS High Sierra](https://support.apple.com/en-us/HT208019) (abre o site da Apple)

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

O perfil é criado e exibido na lista. [Atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

## <a name="next-steps"></a>Próximas etapas

Depois que o perfil é criado, ele está pronto para ser atribuído. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).
