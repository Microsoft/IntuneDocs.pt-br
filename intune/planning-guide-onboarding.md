---
title: "Processo de integração do Intune"
description: "Este artigo ajuda você com todos os detalhes que precisam ser considerados ao integrar a solução somente na nuvem do Intune em seu ambiente."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ade7caf544d71c062c0fa251d7a113facb700a36
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="intune-implementation"></a>Implementação do Intune

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Durante a fase de integração, você implementará o Intune no ambiente de produção. O processo de implementação consistirá em configurar o Intune e as dependências externas (se necessário) de acordo com os [requisitos de caso de uso](planning-guide-requirements.md) examinados nas seções anteriores deste guia.

A seção a seguir fornece uma visão geral do processo de implementação do Intune que inclui requisitos e tarefas de alto nível.

>[!TIP]
> Confira [Recursos adicionais](planning-guide-resources.md) para obter mais informações sobre o processo de implementação do Intune.

## <a name="intune-requirements"></a>Requisitos do Intune

Os principais requisitos independentes do Intune são fornecidos abaixo:

-   Assinatura do EMS/Intune

-   Assinatura do Office 365 (para aplicativos do Office e aplicativos gerenciados por política de MAM)

-   Certificado Apple APNs (para habilitar o gerenciamento de plataforma de dispositivo iOS)

-   Azure AD Connect (para sincronização de diretório)

-   Conector Local do Intune para Exchange (para a AC do Exchange no Local, se necessário)

-   Intune Certificate Connector (para a implantação de certificado SCEP, se necessário)

>[!TIP]
> Encontre mais informações sobre os requisitos independentes do Intune [aqui](/intune/supported-devices-browsers).

## <a name="intune-implementation-process"></a>Processo de implementação do Intune

### <a name="overview-of-implementation-tasks"></a>Visão geral das tarefas de implementação

Esta é uma visão geral de cada tarefa durante a implementação do Intune.

#### <a name="task-1-add-intune-subscription"></a>Tarefa 1: Adicionar a assinatura do Intune

Conforme identificado na seção anterior sobre requisitos, é necessária uma assinatura do EMS ou do Intune. Caso sua organização não tenha uma assinatura do EMS nem do Intune, contate a Microsoft ou a Equipe de Contas da Microsoft sobre seu interesse em comprar o EMS (Enterprise Mobility + Security) ou o Intune.

-   Saiba mais sobre [como comprar o Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).

#### <a name="task-2-add-office-365-subscription"></a>Tarefa 2: Adicionar uma assinatura do Office 365

Essa etapa é opcional. Conforme identificado na seção anterior sobre requisitos, é necessária uma assinatura do Office 365 se você planeja usar o Exchange Online e gerenciar aplicativos móveis do Office com uma política de MAM. Caso sua organização não tenha uma assinatura do Office 365, contate a Microsoft ou a equipe de contas da Microsoft sobre seu interesse em comprar o Office 365.

-   Saiba mais sobre [como comprar o Office 365](https://products.office.com/business/compare-office-365-for-business-plans).

#### <a name="task-3-add-users-groups-in-azure-ad"></a>Tarefa 3: Adicionar grupos de usuários no Azure AD

Talvez seja necessário adicionar usuários ou grupos de segurança no AD ou AAD de acordo com seus requisitos e cenários de caso de uso de implantação do Intune. Você deve examinar os usuários e grupos de segurança atuais no Active Directory ou Azure Active Directory e determinar se eles atendem totalmente às suas necessidades. Novos usuários e grupos de segurança geralmente são adicionados no Active Directory e sincronizados no Azure Active Directory por meio do Azure AD Directory Connect.

-   Saiba mais sobre [como adicionar usuários/grupos no Intune](users-permissions-add.md).

#### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>Tarefa 4: Atribuir licenças de usuário do Intune e Office 365

Todos os usuários que serão alvo da distribuição do EMS/Intune e Office 365 precisarão ter uma licença atribuída a eles. A atribuição de licença do EMS/Intune e Office 365 pode ser feita no Portal do Centro de Administração do Office 365.

-   Saiba mais sobre [como atribuir licenças do Intune](licenses-assign.md).

#### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>Tarefa 5: Definir a autoridade de gerenciamento de dispositivo móvel para o Intune

Antes de iniciar a instalação, a configuração, o gerenciamento e o registro de dispositivos usando o Intune, é necessário definir a Autoridade de Gerenciamento de Dispositivo no Intune. A configuração da tarefa da Autoridade de Gerenciamento de Dispositivo é concluída no Portal de Administração do Intune, no espaço de trabalho Administrador.

-   Saiba mais sobre [como definir a Autoridade de Gerenciamento de Dispositivo](/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

#### <a name="task-6-enable-device-platforms"></a>Tarefa 6: Habilitar plataformas de dispositivo

Por padrão, no console de administração do Intune, a maioria das plataformas de dispositivo é habilitada, exceto dispositivos Apple (iOS e Mac). Antes que os dispositivos iOS possam ser registrados e gerenciados no Intune, a plataforma de dispositivo deve ser habilitada. A habilitação da plataforma de dispositivo iOS consiste em um processo de três etapas: criar e baixar o certificado APNs e carregar o certificado APNs no Intune.

-   Saiba mais sobre [como funciona a configuração do gerenciamento de dispositivos iOS e Mac.](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)

#### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>Tarefa 7: Adicionar e implantar políticas de termos e condições

O Microsoft Intune dá suporte à adição e implantação de políticas de termos e condições. A adição e implantação de políticas de termos e condições são concluídas no Portal de Administração do Intune, no espaço de trabalho Política. Adicione políticas de termos e condições conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre [como adicionar e implantar políticas de termos e condições](/intune-classic/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune).

#### <a name="task-8-add-and-deploy-configuration-policies"></a>Tarefa 8: Adicionar e implantar políticas de configuração

O Microsoft Intune dá suporte à adição e à implantação de dois tipos de políticas de Configuração: Geral e Personalizada. A adição e implantação de políticas de Configuração são concluídas no Portal de Administração do Intune, no espaço de trabalho Política. Adicione políticas de Configuração conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre [como adicionar e implantar políticas de configuração](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

#### <a name="task-9-add-and-deploy-resource-profiles"></a>Tarefa 9: Adicionar e implantar perfis de recursos

O Microsoft Intune dá suporte a perfis de Email, Wi-Fi e VPN. A adição e implantação de perfis são concluídas no Portal de Administração do Intune, no espaço de trabalho Política. Adicione perfis de Email/Wi-Fi/VPN conforme apropriado e implante-os em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre como [habilitar o acesso a recursos da empresa com o Intune](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

#### <a name="task-10-add-and-deploy-apps"></a>Tarefa 10: Adicionar e implantar aplicativos

O Microsoft Intune dá suporte à implantação de aplicativos Web, LOB e de Repositório Público. Além disso, há suporte para o gerenciamento de aplicativos que integraram o SDK do Intune pela associação deles a políticas de MAM. A adição e implantação de aplicativos são concluídas no Portal de Administração do Intune, no espaço de trabalho Aplicativo. A adição de políticas de MAM é concluída no Portal de Administração do Intune, no espaço de trabalho Política. Adicione aplicativos conforme apropriado e implante-os em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre como [adicionar e implantar aplicativos](/intune-classic/deploy-use/deploy-apps).

#### <a name="task-11-add-and-deploy-compliance-policies"></a>Tarefa 11: Adicionar e implantar políticas de conformidade

O Microsoft Intune dá suporte a políticas de Conformidade. A adição e implantação de políticas de Conformidade são concluídas no Portal de Administração do Intune, no espaço de trabalho Política. Adicione políticas de Conformidade conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre as [políticas de conformidade](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

#### <a name="task-12-enable-conditional-access-policies"></a>Tarefa 12: Habilitar Políticas de Acesso Condicional

O Microsoft Intune dá suporte ao Acesso Condicional para Exchange Online e no Local, SharePoint Online, Skype for Business Online e Dynamics CRM Online. Habilite políticas de Acesso Condicional no Portal de Administração do Intune, no espaço de trabalho Política. Habilite e configure o Acesso Condicional conforme apropriado, de acordo com seus [requisitos e casos de uso de implantação do Intune](planning-guide-requirements.md).

-   Saiba mais sobre o [acesso condicional](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

#### <a name="task-13-enroll-devices"></a>Tarefa 13: Registrar dispositivos

O Intune dá suporte às plataformas de dispositivo iOS, Mac OS, Android, Windows Desktop e Windows Mobile. Registre as plataformas de dispositivo móvel conforme apropriado, de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre [como registrar dispositivos](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).

>[!TIP]
> Confira este [módulo de sessão sobre o Intune da Microsoft Virtual Academy](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676) para obter mais informações sobre o processo de implementação do Intune.

## <a name="next-section"></a>Próxima seção

A próxima seção fornece diretrizes sobre como [testar e validar sua implantação do Intune](planning-guide-test-validation.md).
