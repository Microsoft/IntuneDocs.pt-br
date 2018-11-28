---
title: Solucionar problemas de perfis de email no Microsoft Intune – Azure | Microsoft Docs
description: Problemas com o perfil de email e como resolvê-los.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 480b453aa4f08f8d2a2460e26bfdb5f05466df6e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52190070"
---
# <a name="troubleshoot-email-profiles-in-microsoft-intune"></a>Solucionar problemas de perfis de email no Microsoft Intune

Analise alguns problemas comuns relacionados ao perfil de email e como resolvê-los.

Caso essas informações não ajudem, [obtenha também o suporte para o Microsoft Intune](get-support.md).

## <a name="unable-to-send-images-from--email-account"></a>Não é possível enviar imagens da conta de email
Aplica-se ao Intune no portal clássico do Azure.

Os usuários que têm contas de email configuradas automaticamente não podem enviar imagens de seus dispositivos. Esse cenário pode ocorrer se a opção **Permitir que o email seja enviado de aplicativos de terceiros** não estiver habilitada.

### <a name="intune-solution"></a>Solução do Intune

1. Abra o Console de administração do Microsoft Intune, selecione **Política** Carga de trabalho > **Política de configuração**.

2. Selecione o perfil de email e clique em **Editar**.

3. Selecione a opção **Permitir que o email seja enviado de aplicativos de terceiros.**

### <a name="configuration-manager-integrated-with-intune-solution"></a>Configuration Manager integrado à solução Intune

1. Abra o console do Configuration Manager > **Ativos e Conformidade**.

2. Expanda **Visão geral** > **Configurações de Conformidade** > **Acesso aos Recursos da Empresa** e selecione **Perfis de Email**.

3. Clique com o botão direito do mouse no perfil de email e abra as **Propriedades**.

4. Na guia **Configurações de Sincronização**, selecione **Permitir que o email seja enviado de aplicativos de terceiros**.

## <a name="device-already-has-an-email-profile-installed"></a>O dispositivo já tem um perfil de email instalado

Se o usuário instalou um perfil de email antes de provisionar um perfil do Intune, o resultado da implantação do perfil de email do Intune dependerá da plataforma do dispositivo:

- **iOS**: o Intune detecta um perfil de email existente e duplicado com base no nome do host e endereço de email. O perfil de email duplicado criado pelo usuário bloqueia a implantação de um perfil criado pelo administrador do Intune. Esse é um problema comum, pois usuários do iOS normalmente criam um perfil de email e, depois, se registram. O portal da empresa atualiza o usuário de que ele não está em conformidade devido ao seu perfil de email configurado manualmente e solicita que o usuário remova esse perfil. O usuário deve remover seu perfil de email para que o perfil do Intune possa ser implantado. Para evitar esse problema, instrua os usuários a registrar e permitir que o Intune implante o perfil. Em seguida, instale o perfil de email criado pelo usuário.

- **Windows**: o Intune detecta um perfil de email existente e duplicado com base no nome do host e endereço de email. O Intune substitui o perfil de email existente criado pelo usuário.

- **Samsung KNOX Standard**: o Intune identifica uma conta de email duplicada com base no endereço de email e depois a substitui pelo perfil do Intune. Se o usuário configurar essa conta, ela será substituída novamente pelo perfil do Intune. Isso pode causar alguma confusão ao usuário cuja configuração de conta for substituída.

O Samsung KNOX não usa o nome do host para identificar o perfil. É recomendável que você não crie vários perfis de email para implantar no mesmo endereço de email em hosts diferentes, pois eles substituirão uns aos outros.

## <a name="error--0x87d1fde8-for-knox-standard-device"></a>Erro 0x87D1FDE8 para dispositivo KNOX Standard
**Problema**: depois de criar e implantar um perfil de email do Exchange Active Sync para Samsung KNOX Standard para vários dispositivos Android, o erro **0x87D1FDE8** ou **falha na correção** é reportado na guia da política > das propriedades do dispositivo.

Examine a configuração do seu perfil de EAS para Samsung KNOX e a política de origem. Não há suporte para a opção de sincronização das Samsung Notes e essa opção não deve estar selecionada em seu perfil. Certifique-se de que os dispositivos tenham tempo suficiente para processar a política, até 24 horas.

## <a name="next-steps"></a>Próximas etapas
Caso essas informações não ajudem, [obtenha também o suporte para o Microsoft Intune](get-support.md).