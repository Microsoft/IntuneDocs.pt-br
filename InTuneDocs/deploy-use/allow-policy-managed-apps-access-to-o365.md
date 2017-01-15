---
title: Acesso condicional ao O365 baseado em aplicativo | Microsoft Docs
description: "Entenda como o AC para MAM pode ajudar a controlar os aplicativos que têm acesso aos serviços do O365."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2babdeaaf10e9a58716d299cbde0babe45967fb1


---

# <a name="allow-only-mobile-apps-that-support-intune-mam-policies-to-access-office-365-services"></a>Permitir que apenas aplicativos móveis que dão suporte às políticas de MAM do Intune acessem os serviços do Office 365

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As [Políticas de gerenciamento de aplicativos móveis (MAM) do Intune](protect-apps-and-data-with-microsoft-intune.md) ajudam a proteger os dados da empresa em dispositivos registrados para gerenciamento no Intune. É possível usar as políticas MAM em **dispositivos do funcionário que não estão registrados para gerenciamento no Intune**.  Nesse caso, mesmo que você não gerencie o dispositivo, ainda é necessário se certificar de que os dados e recursos da empresa estão protegidos. Ao usar o acesso condicional para MAM (MAM CA), você pode criar uma política que permita aos aplicativos móveis que dão suporte às políticas de MAM do Intune acessar serviços do O365, como o Exchange Online.

Por exemplo, ao permitir que apenas o **aplicativo do Microsoft Outlook** acesse o Exchange Online você pode **bloquear os aplicativos de email interno no iOS e no Android**, que não têm a proteção de dados das políticas de MAM do Intune, para receber email do **Exchange Online**.

O diagrama a seguir ilustra o fluxo usado pelas políticas de AC de MAM para determinar quando permitir ou bloquear o acesso: ![Diagrama que mostra os vários critérios incluídos para determinar se o acesso é permitido ou bloqueado ](../media/mam-ca-decision-flow_simple.png).

Descrição das abreviações usadas nos diagramas:
* **CP**: aplicativo de Portal da Empresa
* **AA**: aplicativo Microsoft Authenticator
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## <a name="prerequisites"></a>Pré-requisitos
**Antes** de configurar uma política de AC de MAM, você deve ter uma **assinatura premium do Enterprise Mobility + Security ou do Azure Active Directory** e os usuários devem ser licenciados para o EMS ou Azure AD. Para obter mais detalhes, veja a [página de preços do Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) ou a [página de preços do Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


## <a name="supported-apps"></a>Aplicativos com suporte
**Exchange Online**: **Microsoft Outlook** para Android e iOS.

Para saber mais sobre a experiência do usuário com um aplicativo que tem políticas de AC de MAM, consulte [O que esperar ao usar um aplicativo com AC do MAM](use-apps-with-mam-ca.md).


## <a name="next-steps"></a>Próximas etapas
[Criar uma política do Exchange Online para aplicativos MAM](mam-ca-for-exchange-online.md)

[Bloquear aplicativos que não têm autenticação moderna](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Consulte também

[Proteger dados de aplicativos com políticas de MAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


