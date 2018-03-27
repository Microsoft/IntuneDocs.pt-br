---
title: Acesso condicional ao O365 baseado em aplicativo
description: Entenda como o AC para MAM pode ajudar a controlar os aplicativos que têm acesso aos serviços do O365.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/05/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b0b0fbfce086729551b211dd4bc4b83348aa4787
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services"></a>Permitir que apenas aplicativos móveis que dão suporte às políticas de proteção de aplicativo do Intune acessem os serviços do Office 365

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As [Políticas de proteção de aplicativo do Intune](protect-apps-and-data-with-microsoft-intune.md) ajudam a proteger os dados de sua empresa nos dispositivos registrados para gerenciamento no Intune. É possível usar as políticas de proteção de aplicativo em **dispositivos do funcionário que não estão registrados para gerenciamento no Intune**.  Nesse caso, mesmo que você não gerencie o dispositivo, ainda é necessário se certificar de que os dados e recursos da empresa estão protegidos. Usando o acesso condicional baseado em aplicativo com MAM, você pode criar uma política que permite que apenas aplicativos móveis que dão suporte às políticas de proteção de aplicativo do Intune acessem os serviços do O365, como o Exchange Online.

Por exemplo, ao permitir que apenas o **aplicativo do Microsoft Outlook** acesse o Exchange Online você pode **bloquear os aplicativos de email interno no iOS e no Android**, que não têm a proteção de dados das políticas de MAM do Intune, para receber email do **Exchange Online**. Ou você pode bloquear o acesso dos aplicativos móveis que não têm suporte do Intune MAM ao **SharePoint Online**.

O diagrama a seguir ilustra o fluxo usado pelas políticas de acesso condicional baseados em aplicativo para determinar quando permitir ou bloquear o acesso: ![Diagrama que mostra os vários critérios incluídos para determinar se o acesso é permitido ou bloqueado](../media/mam-ca-decision-flow_simple.png).

Descrição das abreviações usadas nos diagramas:
* **CP**: aplicativo de Portal da Empresa
* **AA**: aplicativo Microsoft Authenticator
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## <a name="prerequisites"></a>Pré-requisitos
**Antes** de criar uma política de acesso condicional baseado em aplicativo, você deve ter uma **assinatura premium do Enterprise Mobility + Security ou do Azure Active Directory** e os usuários devem ser licenciados para o EMS ou Azure AD. Para obter mais detalhes, veja a [página de preços do Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou a [página de preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).


## <a name="supported-apps"></a>Aplicativos com suporte
**Exchange Online**:
* **Microsoft Outlook** para Android e iOS.

**SharePoint Online**
* Microsoft Word para iOS e Android
* Microsoft Excel para iOS e Android
* Microsoft PowerPoint para iOS e Android
* Microsoft OneDrive para Empresas para iOS e Android
* Microsoft OneNote para iOS

>[!IMPORTANT]
>Para dispositivos Android, o registro de dispositivo inicial deve ser feito por meio do logon no aplicativo OneDrive ou no aplicativo do Outlook. O aplicativo OneNote para Android ainda não tem suporte para MAM sem registro.

Para saber mais sobre a experiência do usuário com um aplicativo que tem políticas de acesso condicional baseado em aplicativo, veja [O que esperar ao usar um aplicativo com AC do MAM](use-apps-with-mam-ca.md).


## <a name="next-steps"></a>Próximas etapas
[Criar uma política do Exchange Online para aplicativos MAM](mam-ca-for-exchange-online.md)

[Criar uma política do SharePoint Online para aplicativos MAM](mam-ca-for-sharepoint-online.md)

[Bloquear aplicativos que não têm autenticação moderna](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Consulte também

[Proteger dados de aplicativo com as políticas de proteção de aplicativo](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
