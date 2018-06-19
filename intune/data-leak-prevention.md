---
title: Impedir vazamento de dados em dispositivos não gerenciados
titlesuffix: Microsoft Intune
description: Permita o acesso aos dados corporativos em dispositivos e proteja os dados contra vazamentos usando o Microsoft Intune.
keywords: proteção de dados impedir vazamentos dispositivo O365 Office 365
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b1512c3a-3bbd-4111-a0df-c874a0a335df
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b8f0f038a1f093ec93182fa0ee590d83e6ebea29
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31024950"
---
# <a name="prevent-data-leaks-on-non-managed-devices-using-microsoft-intune"></a>Impedir vazamentos de dados em dispositivos não gerenciados usando o Microsoft Intune

Se você permite acesso aos dados da empresa hospedados pelo Office 365, é possível controlar como os usuários compartilham e salvam os dados sem o risco de vazamentos acidentais ou intencionais. O Microsoft Intune fornece políticas de proteção de aplicativo que você define para proteger os dados da empresa em dispositivos pertencentes ao usuário. Os dispositivos não precisam ser registrados no serviço Intune. 

As políticas de proteção de aplicativo configuradas com o Intune também funcionam em dispositivos gerenciados com soluções de gerenciamento de dispositivo que não são da Microsoft. Os dados pessoais nos dispositivos permanecem intocados; somente os dados da empresa são gerenciados pelo departamento de TI. 

Você pode definir políticas de proteção de aplicativo para aplicativos móveis do Office em dispositivos que executam o Windows, o iOS ou o Android para proteger os dados da empresa. Essas políticas permitem definir políticas, como PIN baseado no aplicativo ou criptografia de dados da empresa, ou configurações mais avançadas para restringir como os recursos recortar, copiar, colar e salvar como são usados pelos usuários entre os aplicativos gerenciados e não gerenciados. Você também pode apagar remotamente os dados da empresa sem precisar que os usuários registrem os dispositivos. 

As políticas de proteção de aplicativo do Intune são independentes do gerenciamento de dispositivo. As políticas de proteção de aplicativo permitem o gerenciamento de aplicativos móveis do Office em dispositivos gerenciados e não gerenciados pelo Intune, bem como em dispositivos gerenciados por soluções de MDM que não são da Microsoft. 

## <a name="before-you-begin"></a>Antes de começar

O plano de ação a seguir poderá ser usado quando os requisitos abaixo forem atendidos:
* Sua empresa está pronta para fazer a transição com segurança para a nuvem.
* Sua empresa usa o Office 365 Exchange Online, o SharePoint Online, o OneDrive for Business ou o Yammer.
* Sua empresa tem licenças do Microsoft 365, do EMS (Enterprise Mobility + Security) ou da Proteção de Informações do Azure.
* Sua empresa permite que os usuários acessem dados da empresa de dispositivos Android, iOS ou Windows de propriedade pessoal ou da empresa. 
* Sua empresa não deseja exigir o registro de dispositivos pessoais em um serviço de gerenciamento de dispositivo. 

## <a name="action-plan"></a>Plano de ação

Para dispositivos iOS e Android: 

1. Saiba como as [políticas de proteção de aplicativo](app-protection-policy.md) funcionam.
2. Saiba como [criar e implantar políticas de proteção de aplicativo](app-protection-policies.md) para aplicativos móveis do Office. 
3. [Monitore as políticas de proteção de aplicativo](app-protection-policies-monitor.md) que você criar e implantar. 

Para dispositivos Windows 10: 

1. Saiba [como funciona a WIP (Proteção de Informações do Windows)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip). 
2. Prepare-se para configurar [políticas de proteção de aplicativo para Windows 10](app-protection-policies-configure-windows-10.md).
3. [Crie e implante políticas de proteção de aplicativo da WIP com o Intune](windows-information-protection-policy-create.md).

## <a name="what-to-tell-employees-and-students"></a>O que dizer aos funcionários e alunos

Conforme apropriado, compartilhe os links a seguir para fornecer informações adicionais: 
* [O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-ios.md)
* [O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo](app-protection-enabled-apps-android.md) 

## <a name="next-steps"></a>Próximas etapas

Deseja obter ajuda para habilitar este ou outros cenários do EMS ou do Office 365? Se você tiver, pelo menos, 150 licenças do Microsoft 365, do Enterprise Mobility + Security ou do Azure Active Directory Premium, use seus [Benefícios do FastTrack](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program). 