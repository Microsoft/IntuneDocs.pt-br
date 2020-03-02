---
title: Aplicativos iOS/iPadOS com políticas de proteção de aplicativo
description: Este tópico descreve o que esperar quando seu aplicativo iOS/iPadOS é gerenciado por políticas de proteção de aplicativo.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/18/2019
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
ms.openlocfilehash: c854811a9deb938613af872f3cf86244ab9121b3
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514652"
---
# <a name="what-to-expect-when-your-iosipados-app-is-managed-by-app-protection-policies"></a>O que esperar quando seu aplicativo iOS/iPadOS é gerenciado por políticas de proteção de aplicativo

As políticas de proteção de aplicativo do Intune aplicam-se a aplicativos usados para trabalho ou escola. Isso significa que, quando seus funcionários e alunos usam os aplicativos deles em um contexto pessoal, podem não notar diferenças na experiência. No entanto, no contexto corporativo ou de estudante, eles podem receber prompts para tomar decisões sobre a conta, atualizar as configurações ou contatar você para obter ajuda. Use este artigo para saber o que os usuários enfrentam ao tentar acessar e usar aplicativos protegidos pelo Intune.  

## <a name="access-apps"></a>Acessar aplicativos

Se o dispositivo **não estiver registrado no Intune**, o usuário será solicitado a reiniciar o aplicativo ao usá-lo pela primeira vez. Uma reinicialização é necessária para que as políticas de proteção de aplicativo possam ser aplicadas ao aplicativo.

<!--- The following screenshot from the Skype app illustrates this restart request: --->

<!---  ![Screenshot of the iOS/iPadOS device showing PIN prompt](./media/end-user-mam-apps-ios/iOS_AppPINPrompt.png) --->

Em dispositivos **registrados para gerenciamento no Intune**, o usuário verá uma mensagem informando que seu aplicativo agora é gerenciado.

## <a name="use-apps-with-multi-identity-support"></a>Usar aplicativos com suporte a várias identidades

Os aplicativos que dão suporte a várias identidades permitem que você use contas pessoais e corporativas diferentes para acessar os mesmos aplicativos. As políticas de proteção de aplicativo, como a inserção de um PIN de dispositivo, são ativadas quando os usuários acessam esses aplicativos em um contexto corporativo ou de estudante.   

Os usuários podem receber o prompt de PIN de forma diferente em todos os aplicativos deles, dependendo de como você configura as políticas.  Por exemplo, você pode configurar suas políticas para que:       
* O Microsoft Outlook solicite ao usuário um PIN ao iniciar o aplicativo. 
* O OneDrive solicite ao usuário um PIN quando ele entrar na conta corporativa.  
* Os aplicativos Microsoft Word, PowerPoint e Excel solicitem ao usuário um PIN ao acessar os documentos armazenados no local do OneDrive for Business da empresa.  

- Saiba mais sobre os aplicativos que dão suporte à [proteção de aplicativo e várias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) com o Intune.  

## <a name="manage-user-accounts-on-the-device"></a>Gerenciar contas de usuário no dispositivo  

As políticas de proteção de aplicativo do Intune limitam os usuários a uma conta corporativa ou de estudante gerenciada por aplicativo. As políticas de proteção de aplicativo não limitam o número de contas não gerenciadas que um usuário pode adicionar.   

- Se um usuário tenta adicionar uma segunda conta gerenciada, ele recebe uma solicitação para selecionar qual conta gerenciada usar. Se o usuário adicionar a segunda conta, a primeira será removida.
- Se você adicionar políticas de proteção a outra das contas do usuário, será solicitado que ele selecione qual conta gerenciada usar. A outra conta é removida. 

Alguns usuários não terão a opção de alternar ou selecionar entre contas gerenciadas. A opção não está disponível em dispositivos que são:
* Gerenciados pelo Intune  
* Gerenciados por soluções de gerenciamento de mobilidade corporativa de terceiros e configurados com IntuneMAMUPN 

O cenário de exemplo a seguir descreve como várias contas de usuário são tratadas:  

O usuário A trabalha para duas empresas – **Empresa X** e **Empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo. A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção do aplicativo primeiro. Se você quiser que a conta de usuário associada à Empresa Y seja gerenciada pelas políticas de proteção do aplicativo, será necessário remover a conta de usuário associada à Empresa X e adicionar a conta de usuário associada à Empresa Y.  

## <a name="next-steps"></a>Próximas etapas

[O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](end-user-mam-apps-android.md)
