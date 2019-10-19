---
title: Solucionar problemas de perfis de email no Microsoft Intune – Azure | Microsoft Docs
description: Consulte os problemas comuns e soluções para perfis de email no Microsoft Intune, incluindo perfis de email duplicados e erros em dispositivos Android Samsung KNOX Standard.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/17/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 101f414955a3b60d22003f61678854fecc16910d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506590"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Problemas comuns e soluções para perfis de dispositivo no Microsoft Intune

Analise alguns problemas comuns relacionados ao perfil de email e como resolvê-los.

## <a name="what-you-need-to-know"></a>O que você precisa saber

- Os perfis de email são implantados para o usuário que registrou o dispositivo. Para configurar o perfil de email, o Intune usa as propriedades Azure Active Directory (AD) no perfil de email do usuário durante o registro. [Adicionar configurações de email a dispositivos](email-settings-configure.md) pode ser um bom recurso.
- Depois de migrar do Configuration Manager híbrido para o Intune autônomo, o perfil de email do Configuration Manager híbrido permanece no dispositivo por 7 dias. Esse comportamento é esperado. Se você precisar do perfil de email removido mais cedo, entre em contato com o [suporte do Intune](../fundamentals/get-support.md).
- Para Android Enterprise, implante o Gmail ou nove para trabalho usando o Google Play Store gerenciado. [Adicionar aplicativos Google Play gerenciados](../apps/apps-add-android-for-work.md) lista as etapas.
- O Microsoft Outlook para iOS e Android não dá suporte a perfis de email. Em vez disso, implante uma política de configuração de aplicativo. Para obter mais informações, consulte [definição de configuração do Outlook](../apps/app-configuration-policies-outlook.md).
- Os perfis de email destinados a grupos de dispositivos (não grupos de usuários) podem não ser entregues ao dispositivo. Quando o dispositivo tiver um usuário primário, o direcionamento de dispositivo deverá funcionar. Se o perfil de email incluir certificados de usuário, não se esqueça de direcionar grupos de usuários.
- Os usuários podem ser solicitados repetidamente a inserir sua senha para o perfil de email. Nesse cenário, verifique todos os certificados referenciados no perfil de email. Se um dos certificados não for direcionado a um usuário, o Intune tentará implantar o perfil de email novamente.

## <a name="device-already-has-an-email-profile-installed"></a>O dispositivo já tem um perfil de email instalado

Se os usuários criarem um perfil de email antes de registrarem no Intune ou no Office 365 MDM, o perfil de email implantado pelo Intune poderá não funcionar conforme o esperado:

- **iOS**: o Intune detecta um perfil de email existente e duplicado com base no nome do host e endereço de email. O perfil de email criado pelo usuário bloqueia a implantação do perfil criado pelo Intune. Esse é um problema comum, pois usuários do iOS normalmente criam um perfil de email e, depois, se registram. O aplicativo Portal da Empresa informa que o usuário não está em conformidade e pode solicitar que o usuário remova o perfil de email.

  O usuário deve remover seu perfil de email para que seja possível implantar o perfil do Intune. Para evitar esse problema, instrua os usuários a registrar e permitir que o Intune implante o perfil. Depois os usuários podem criar seu perfil de email.

- **Windows**: o Intune detecta um perfil de email existente e duplicado com base no nome do host e endereço de email. O Intune substitui o perfil de email existente criado pelo usuário.

- **Samsung KNOX Standard**: o Intune identifica uma conta de email duplicada com base no endereço de email e depois a substitui pelo perfil do Intune. Se o usuário configurar essa conta, ela será substituída novamente pelo perfil do Intune. Isso pode causar alguma confusão ao usuário cuja configuração de conta for substituída.

O Samsung KNOX não usa o nome do host para identificar o perfil. É recomendável que você não crie vários perfis de email para implantar no mesmo endereço de email em diferentes hosts, pois eles substituirão uns aos outros.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>Erro 0x87D1FDE8 para dispositivo KNOX Standard

**Problema**: depois de criar e implantar um perfil de email do Exchange Active Sync para Samsung KNOX Standard em diferentes dispositivos Android, os erros **0x87D1FDE8** ou **falha na correção** surgem na guia de propriedades do dispositivo > política.

Examine a configuração do seu perfil de EAS para Samsung KNOX e a política de origem. Não há suporte para a opção de sincronização das Samsung Notes e essa opção não deve estar selecionada em seu perfil. Certifique-se de que os dispositivos tenham tempo suficiente para processar a política, até 24 horas.

## <a name="unable-to-send-images-from--email-account"></a>Não é possível enviar imagens da conta de email

Os usuários que têm contas de email configuradas automaticamente não podem enviar imagens de seus dispositivos. Esse cenário pode ocorrer se a opção **Permitir que o email seja enviado de aplicativos de terceiros** não estiver habilitada.

### <a name="intune-solution"></a>Solução do Intune

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do Dispositivo** > **Perfis**.
3. Selecione seu perfil de email > **Propriedades** de  > **configurações**.
4. Defina a configuração **permitir que o email seja enviado de aplicativos de** terceiros para **habilitar**o.

### <a name="configuration-manager-hybrid"></a>Híbrido do Configuration Manager

1. Abra o console do Configuration Manager > **Ativos e Conformidade**.

2. Expanda **Visão geral** > **Configurações de Conformidade** > **Acesso aos Recursos da Empresa** e selecione **Perfis de Email**.

3. Clique com o botão direito do mouse no perfil de email e abra as **Propriedades**.

4. Na guia **Configurações de Sincronização**, selecione **Permitir que o email seja enviado de aplicativos de terceiros**.

## <a name="next-steps"></a>Próximas etapas

Obtenha [ajuda do suporte da Microsoft](../fundamentals/get-support.md) ou use os [fóruns da comunidade](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
