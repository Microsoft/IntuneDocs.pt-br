---
title: Processo de integração do Intune
titleSuffix: Microsoft Intune
description: Este artigo o ajuda com todos os detalhes que precisam ser considerados ao integrar a solução somente na nuvem do Microsoft Intune ao seu ambiente.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e21eb6169acf8ae69ace94fd54007eaa4f7f90f
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66046750"
---
# <a name="implement-your-microsoft-intune-plan"></a>Implementar seu plano do Microsoft Intune

Durante a fase de integração, você implantará o Intune no ambiente de produção. O processo de implementação consiste em configurar o Intune e as dependências externas (se necessário) de acordo com os [requisitos de caso de uso](planning-guide-requirements.md).

A seção a seguir fornece uma visão geral do processo de implementação do Intune que inclui requisitos e tarefas de alto nível.

## <a name="intune-requirements"></a>Requisitos do Intune

Os principais requisitos independentes do Intune são:

-   EMS (Enterprise Mobility + Security)/assinatura do Intune

-   Assinatura do Office 365 (para aplicativos do Office e aplicativos gerenciados por política de proteção do aplicativo)

-   Certificado Apple APNs (para habilitar o gerenciamento de plataforma de dispositivo iOS)

-   Azure AD Connect (para sincronização de diretório)

-   On-Premises Connector do Intune para Exchange (para a acesso condicional para o Exchange Local, se necessário)

-   Intune Certificate Connector (para a implantação de certificado SCEP, se necessário)

>[!TIP]
> Consulte a lista de [dispositivos com suporte](supported-devices-browsers.md) para obter uma lista de dispositivos que você pode gerenciar com o Intune.

## <a name="intune-implementation-process"></a>Processo de implementação do Intune

Nós identificamos 13 tarefas discretas para implementar uma implantação do Intune. Dependendo dos requisitos de negócios, da infraestrutura existente e da estratégia de gerenciamento de dispositivo, algumas dessas tarefas talvez já tenham sido concluídas. Outras podem não se aplicar ao seu plano.

### <a name="task-1-get-an-intune-subscription"></a>Tarefa 1: Obter uma assinatura do Intune

Conforme indicado na seção de requisitos do Intune acima, você precisa de uma assinatura do EMS ou do Intune. Caso sua organização não tenha uma, contate a Microsoft ou a equipe de contas da Microsoft sobre seu interesse em comprar o EMS (Enterprise Mobility + Security) ou o Intune.

-   Saiba mais sobre [como comprar o Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).

### <a name="task-2-add-office-365-subscription"></a>Tarefa 2: Adicionar assinatura do Office 365

Essa etapa é opcional. Você precisa de uma assinatura do Office 365 se você planeja usar o Exchange Online e gerenciar aplicativos móveis do Office com as políticas de proteção do aplicativo. Caso sua organização não tenha uma assinatura do Office 365, contate a Microsoft ou a equipe de contas da Microsoft sobre seu interesse em comprar o Office 365.

-   Saiba mais sobre [como comprar o Office 365](https://products.office.com/business/compare-office-365-for-business-plans).

### <a name="task-3-add-users-groups-in-azure-ad"></a>Tarefa 3: Adicionar grupos de usuários no Azure AD

Talvez seja necessário adicionar usuários ou grupos de segurança no Active Directory ou Azure Active Directory de acordo com seus requisitos e cenários de caso de uso de implantação do Intune. Examine os usuários e grupos de segurança atuais no Active Directory ou Azure Active Directory e determine se eles atendem totalmente às suas necessidades. Ao adicionar novos usuários e grupos de segurança, recomendamos adicioná-los no Active Directory e sincronizar com o Azure Active Directory usando o Azure AD Connect.


-   Saiba mais sobre [como adicionar usuários/grupos no Intune](users-permissions-add.md).
<!---why not send them to the AAD connect topic? Question out to Andre: https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect--->



### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>Tarefa 4: Atribuir licenças de usuário do Intune e do Office 365

Todos os usuários que serão alvo da distribuição do EMS/Intune e Office 365 precisarão ter uma licença atribuída a eles. É possível atribuir licenças do EMS/Intune e do Office 365 no centro de administração do Microsoft 365.

-   Saiba mais sobre [como atribuir licenças do Intune](licenses-assign.md).

### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>Tarefa 5: Definir a autoridade de gerenciamento de dispositivo móvel para o Intune

Antes de iniciar a instalação, a configuração, o gerenciamento e o registro de dispositivos usando o Intune, é necessário definir a autoridade de gerenciamento de dispositivo para o Intune.

-   Saiba mais sobre [como definir a autoridade de gerenciamento de dispositivo](mdm-authority-set.md).

### <a name="task-6-enable-device-platforms"></a>Tarefa 6: Habilitar plataformas de dispositivo

Por padrão, a maioria das plataformas de dispositivo é habilitada, exceto dispositivos Apple (iOS e Mac). Antes que os dispositivos iOS possam ser registrados e gerenciados no Intune, a plataforma de dispositivo deve ser habilitada. Para fazer isso, você precisa criar um MDM Push Certificate e adicioná-lo ao Intune.

-   Saiba mais sobre [como habilitar dispositivos da Apple para registro](apple-mdm-push-certificate-get.md).

### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>Tarefa 7: Adicionar e implantar políticas de termos e condições

O Intune dá suporte a políticas de termos e condições. Adicione políticas de termos e condições conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre [como adicionar e implantar políticas de termos e condições](terms-and-conditions-create.md).

### <a name="task-8-add-and-deploy-configuration-policies"></a>Tarefa 8: Adicionar e implantar políticas de configuração

O Intune dá suporte a dois tipos de políticas de configuração, geral e personalizada. Adicione políticas de configuração conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre [como adicionar e implantar políticas de configuração](device-profiles.md).

### <a name="task-9-add-and-deploy-resource-profiles"></a>Tarefa 9: Adicionar e implantar perfis de recursos

O Intune dá suporte a perfis de Email, de Wi-Fi e de VPN. Adicione esses perfis conforme apropriado e implante-os em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre [como habilitar o acesso a recursos da empresa com o Intune](device-profiles.md).

### <a name="task-10-add-and-deploy-apps"></a>Tarefa 10: Adicione e implante aplicativos

O Intune dá suporte à implantação de aplicativos Web, LOB e de repositório público. Você também pode gerenciar aplicativos que integraram o SDK do Intune, associando-os a políticas de proteção do aplicativo. Adicione aplicativos conforme apropriado e implante-os em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre [adição e implantação de aplicativos](app-management.md).

### <a name="task-11-add-and-deploy-compliance-policies"></a>Tarefa 11: Adicionar e implantar políticas de conformidade

O Intune dá suporte a políticas de conformidade. Adicione políticas de conformidade conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre as [políticas de conformidade](device-compliance.md).

### <a name="task-12-enable-conditional-access-policies"></a>Tarefa 12: Habilitar políticas de acesso condicional

O Intune dá suporte ao acesso condicional para Exchange Online, Exchange Local, SharePoint Online, Skype for Business Online e Dynamics CRM Online. Habilite e configure o acesso condicional conforme apropriado, de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre o [acesso condicional](conditional-access.md).

### <a name="task-13-enroll-devices"></a>Tarefa 13: Registrar dispositivos

O Intune dá suporte às plataformas de dispositivo iOS, Mac OS, Android, Windows Desktop e Windows Mobile. Registre as plataformas de dispositivo móvel conforme apropriado, de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre [como registrar dispositivos](device-enrollment.md).


## <a name="next-steps"></a>Próximas etapas

Confira este [módulo de sessão sobre o Intune da Microsoft Virtual Academy](https://mva.microsoft.com/en-US/training-courses/deploying-microsoft-enterprise-mobility-suite-16408) para obter mais informações sobre o processo de implementação do Intune.


Veja diretrizes de como [testar e validar sua implantação do Intune](planning-guide-test-validation.md).
