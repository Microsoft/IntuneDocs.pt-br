---
title: Aplicativos iOS com políticas de proteção de aplicativo
description: Este tópico descreve o que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a1a3dcd7068a004f94b97b5ec6c43c609662a76d
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "73414569"
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo

 Este tópico descreve a experiência do usuário ao usar aplicativos com políticas de proteção de aplicativo aplicadas. As políticas do aplicativo são aplicadas somente quando aplicativos são usados no contexto de trabalho: por exemplo, para acessar aplicativos com uma conta corporativa ou acessar arquivos armazenados no OneDrive para Empresas.

## <a name="access-apps"></a>Acessar aplicativos

Se o dispositivo **não estiver registrado no Intune**, o usuário será solicitado a reiniciar o aplicativo ao usá-lo pela primeira vez. Uma reinicialização é necessária para que essas políticas de proteção de aplicativo possam ser aplicadas ao aplicativo.

<!--- The following screenshot from the Skype app illustrates this restart request: --->

<!---  ![Screenshot of the iOS device showing PIN prompt](./media/end-user-mam-apps-ios/iOS_AppPINPrompt.png) --->

Em dispositivos **registrados para gerenciamento no Intune**, o usuário verá uma mensagem informando que seu aplicativo agora é gerenciado.

## <a name="use-apps-with-multi-identity-support"></a>Usar aplicativos com suporte a várias identidades

Aplicativos que dão suporte a várias identidades permitem usar contas diferentes (pessoal e corporativa) para acessar os mesmos aplicativos quando políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho.  

Por exemplo, o usuário receberá uma solicitação para fornecer o PIN ao acessar dados de trabalho. No **aplicativo Outlook**, o usuário será solicitado a fornecer um PIN ao iniciar o aplicativo. No **aplicativo OneDrive**, o usuário será solicitado a fornecer um PIN ao digitar a conta corporativa.  No Microsoft **Word**, **PowerPoint** e **Excel**, o usuário será solicitado a fornecer um PIN ao acessar os documentos armazenados no local do OneDrive for Business da empresa.

- Saiba mais sobre os aplicativos que dão suporte à [proteção de aplicativo e várias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) com o Intune.

As políticas de proteção do aplicativo são aplicadas apenas em contextos corporativos. Desse modo, o aplicativo pode se comportar de forma diferente, de acordo com o contexto – de trabalho ou pessoal.

## <a name="manage-user-accounts-on-the-device"></a>Gerenciar contas de usuário no dispositivo

Aplicativos de várias identidades permitem aos usuários adicionar várias contas.  O aplicativo do Intune permite apenas uma conta de gerenciamento.  Aplicativo do Intune não limita o número de contas não gerenciados.

Quando há uma conta gerenciada em um aplicativo:

- Se um usuário tenta adicionar uma segunda conta gerenciada, ele recebe uma solicitação para selecionar qual conta gerenciada usar.  A outra conta é removida.
- Se o administrador de TI adicionar uma política à segunda conta existente, o usuário receberá uma solicitação para selecionar qual conta gerenciada usar.  A outra conta é removida.

Leia o cenário de exemplo a seguir para entender melhor como várias contas de usuário são tratadas.

O usuário A trabalha para duas empresas – **Empresa X** e **Empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo. A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção do aplicativo primeiro. Se você quiser que a conta de usuário associada à Empresa Y seja gerenciada pelas políticas de proteção do aplicativo, será necessário remover a conta de usuário associada à Empresa X e adicionar a conta de usuário associada à Empresa Y.

### <a name="add-a-second-account"></a>Adicionar uma segunda conta

Se estiver usando um dispositivo iOS, ao tentar adicionar uma segunda conta corporativa ao mesmo dispositivo, você poderá ver uma mensagem de bloqueio. As contas serão exibidas e você poderá escolher a conta que deseja remover.

## <a name="next-steps"></a>Próximas etapas

[O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](end-user-mam-apps-android.md)
