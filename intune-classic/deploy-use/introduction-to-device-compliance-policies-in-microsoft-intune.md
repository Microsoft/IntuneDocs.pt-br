---
title: Políticas de conformidade do dispositivo
description: Este tópico explica o que são políticas de conformidade do dispositivo e como elas funcionam.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4c9c93d29ddee6d01e057c01a44c81950b857213
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31031746"
---
# <a name="device-compliance-policies-in-microsoft-intune"></a>Políticas de conformidade do dispositivo no Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="what-is-a-compliance-policy"></a>O que é uma política de conformidade?
Para ajudar a proteger dados da empresa, você precisa garantir que os dispositivos usados para acessar dados e aplicativos da empresa estejam em conformidade com determinadas regras. Essas regras podem incluir o uso de um PIN para acessar os dispositivos e criptografar dados armazenados em dispositivos. Um conjunto dessas regras é chamado de política de conformidade.

## <a name="how-should-i-use-compliance-policies"></a>Como devo usar as políticas de conformidade?
Você pode usar políticas de conformidade com políticas de acesso condicional para permitir que somente dispositivos que estão em conformidade com as regras de política de conformidade acessem email ou outros serviços. Para saber mais sobre como as duas políticas podem ser usadas em conjunto, leia o artigo [Restringir o acesso ao email e aos serviços do O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Você também pode usar políticas de conformidade independentemente do acesso condicional. Quando você usa as políticas de conformidade de forma independente, os dispositivos de destino são avaliados e relatados com o status de conformidade. Por exemplo, você talvez deseje um relatório sobre o número de dispositivos que não estão criptografados ou quais dispositivos estão com jailbreak ou com raiz. No entanto, quando você usa as políticas de conformidade de forma independente, não há restrições de acesso aos recursos da empresa em vigor.

Você pode implantar políticas de conformidade para usuários. Quando uma política de conformidade é implantada para um usuário, os dispositivos dos usuários são verificados quanto à conformidade.
Para saber quanto tempo levará para que dispositivos móveis obtenham uma política após a política ser implantada, consulte [Gerenciar configurações e recursos em seus dispositivos](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#frequently-asked-questions-about-intune-policies).

A tabela a seguir lista os tipos de dispositivos que têm suporte das políticas de conformidade. A tabela também descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional.

-----------------------------

|Configuração de política| Windows 8.1 e posterior| Windows Phone 8.1 e posterior| iOS 8.0 e posterior|Android 4.0 e posterior<br/>Samsung KNOX Standard 4.0 e posterior|
|-----|----|----|----|----|
|**Configuração de senha ou PIN** |Corrigida|Corrigida|Corrigida|Em Quarentena|
|**Criptografia de dispositivo**|Não aplicável|Corrigida|Corrigida (pela definição do PIN)|Em Quarentena|
|**Dispositivo desbloqueado ou com raiz**|Não Aplicável|Não Aplicável|Em Quarentena (não é uma configuração)|Em Quarentena (não é uma configuração)|
|**Perfil de email**|Não Aplicável|Não Aplicável|Em Quarentena|Não Aplicável|
|**Versão mínima do SO**|Em Quarentena|Em Quarentena|Em Quarentena|Em Quarentena|
|**Versão máxima do SO**|Em Quarentena|Em Quarentena|Em Quarentena|Em Quarentena|
|**Atestado de integridade do Windows**|Em quarentena: Windows 10 e Windows 10 Mobile<br /><br />Não aplicável: Windows 8.1|Não Aplicável|Não Aplicável|Não Aplicável|

------------------------------

**Remediado** = o sistema operacional do dispositivo impõe a conformidade. (Por exemplo, o usuário é forçado a definir um PIN.)

**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade. (Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo.) Quando os dispositivos não são compatíveis, ocorrem as seguintes ações:

-   O dispositivo será bloqueado se uma política de acesso condicional se aplicar ao usuário.

-   O portal da empresa notificará o usuário sobre qualquer problema de conformidade.

## <a name="next-steps"></a>Próximas etapas
[Criar uma política de conformidade do dispositivo](create-a-device-compliance-policy-in-microsoft-intune.md)

[Implantar e monitorar uma política de conformidade do dispositivo](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a>Consulte também
[Restringir o acesso ao email e aos serviços do O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)
