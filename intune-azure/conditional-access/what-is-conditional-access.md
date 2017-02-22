---
title: "O que é acesso condicional? | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba como definir as condições que usuários e dispositivos devem atender para acessar os recursos da empresa na versão prévia do Microsoft Intune Azure."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 41931f64db969c82f79e007c4be9e68b7caf4ce9
ms.openlocfilehash: 20696fb2dc0126aa224e779738cedb4f95f666e8


---

# <a name="what-is-conditional-access"></a>O que é acesso condicional?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Neste tópico, descreveremos o acesso condicional conforme aplicável ao Enterprise Mobility + Security e seguiremos por essas funcionalidades de acesso condicional no Intune.

O acesso condicional do EMS (Enterprise Mobility + Security) aproveita a potência do Azure Active Directory Premium e do Microsoft Intune para fornecer o controle que você precisa para proteger os dados da empresa, proporcionando aos seus funcionários uma experiência que permite trabalhar melhor de qualquer dispositivo.

Com o acesso condicional, você pode definir condições que limitam o acesso aos dados corporativos com base no local, no estado do usuário e do dispositivo e na sensibilidade do aplicativo.

Da perspectiva do dispositivo, o Intune e o Azure Active Directory trabalham juntos para garantir que somente dispositivos gerenciados e em conformidade tenham permissão para acessar email e serviços do Office 365. Por exemplo, você pode definir uma política no Azure Active Directory para permitir que somente computadores que ingressaram no domínio ou dispositivos móveis registrados em um aplicativo de gerenciamento de dispositivo móvel como Intune possam acessar os serviços do Office 365. É possível usar o Intune para definir um perfil de conformidade do dispositivo que avalia o status de conformidade do dispositivo. O status de conformidade é relatado para o Azure Active Directory para ser usado para impor a política no Azure Active Directory quando o usuário tentar acessar os recursos da empresa. Para saber mais sobre a conformidade do dispositivo no Intune, consulte [O que é a conformidade do dispositivo?](/intune-azure/set-device-compliance/what-is-device-compliance)

É possível configurar acesso condicional para aplicativos de nuvem como o Exchange Online pode ser configurado por meio do Azure Active Directory. Para obter mais informações, consulte este [artigo](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal).

## <a name="on-premises-conditional-access-in-intune"></a>Acesso condicional local no Intune

Acesso condicional no Intune pode ser usado para permitir ou bloquear o acesso ao **Exchange local** com base no registro e gerenciamento de dispositivo.

Configurações de perfil de conformidade do dispositivo são usadas para avaliar a conformidade do dispositivo. O acesso condicional usa a avaliação para permitir ou bloquear o acesso ao Exchange local. Quando o acesso condicional é usado junto com um perfil de conformidade do dispositivo, somente os dispositivos em conformidade podem acessar o Exchange local. É possível definir configurações avançadas de acesso condicional para um controle mais granular, tal como: permitir ou bloquear determinadas plataformas ou bloquear imediatamente dispositivos que não são gerenciados pelo Intune.

O perfil de conformidade do dispositivo e o acesso condicional são atribuídos ao usuário. Qualquer dispositivo que o usuário utiliza para acessar o Exchange local é verificado quanto à conformidade. Lembre-se que o usuário que está usando o dispositivo deve ter um perfil de conformidade atribuído a ele para que o dispositivo seja avaliado quanto à conformidade. Se nenhuma política de conformidade for implantada para o usuário, o dispositivo será tratado como em conformidade e nenhuma restrição de acesso será aplicada.

Quando dispositivos não atendem às condições definidas, o usuário final é guiado pelo processo de registro do dispositivo e correção dos problemas que impedem o dispositivo de estar em conformidade.

## <a name="next-steps"></a>Próximas etapas

[Como criar uma política de acesso condicional para o Exchange Local](create-conditional-access-policy-for-exchange-on-premises.md)

[Como configurar o acesso condicional no Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal)



<!--HONumber=Feb17_HO1-->


