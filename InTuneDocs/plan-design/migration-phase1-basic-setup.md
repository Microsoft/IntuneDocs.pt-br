---
title: "Configuração básica do Intune | Microsoft Docs"
description: "A finalidade deste artigo é fornecer as etapas necessárias para configurar o Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: b01b68b7587cb91f24285cdffafeab43296886e6
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-basic-setup"></a>Fase 1: Configuração básica

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Depois de avaliar seu ambiente, é hora de configurar o Intune.

## <a name="external-dependencies-for-an-intune-deployment"></a>Dependências externas para uma implantação do Intune

### <a name="identity"></a>Identidade

O Intune exige o AAD (Azure Active Directory) como o provedor de identidade e agrupamento de usuário.

-   Saiba mais sobre os [requisitos de identidade](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Saiba mais sobre os [requisitos de sincronização de diretório](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Saiba mais sobre os [requisitos de autenticação multifator](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

-   Saiba mais sobre como [planejar os grupos de usuários e de dispositivos](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups).

-   Saiba [como criar grupos de usuários e de dispositivos](https://docs.microsoft.com/en-us/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

Caso sua organização já esteja usando o Office 365, é importante que o Intune use o mesmo ambiente do Azure Active Directory.

### <a name="pki-optional"></a>PKI (opcional)

Se você estiver planejando usar a autenticação com base em certificados para perfis de VPN, Wi-Fi ou email com o Intune, verifique se você tem uma [infraestrutura de PKI em vigor](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles) com suporte, pronta para criar e implantar perfis de certificado.

Confira abaixo mais informações sobre como configurar certificados no Intune.

-   [Configurar a infraestrutura de certificado para SCEP](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep).

-   [Configurar a infraestrutura de certificado](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx).

-   [Como configurar perfis de certificado do Intune](file:///C:/intune/deploy-use/https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles).

-   [Como configurar políticas de acesso a recursos](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

## <a name="task-list-for-an-intune-setup"></a>Lista de tarefas para uma configuração do Intune

### <a name="task-1-intune-subscription"></a>Tarefa 1: Assinatura do Intune

Antes de migrar para o Intune, primeiro você precisa de uma assinatura do Intune.

-   Visite [esta página](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), que fornece instruções sobre como:

    -   Criar uma nova assinatura do Intune vinculada a um novo locatário do AAD.

    -   Vincular a assinatura do Intune entrando em um locatário do AAD existente.

### <a name="task-2-assign-intune-user-licenses"></a>Etapa 2: Atribuir licenças de usuário do Intune

-   Saiba [como atribuir licenças de usuário do Intune](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

-   Se você tiver criado um novo locatário do Azure Active Directory, saiba [como criar novos usuários ou sincronizar usuários de seu AD (Active Directory) local.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Tarefa 3: Definir sua autoridade de MDM para o Intune

O Intune pode ser gerenciado por meio do Portal do Azure ou do console do Branch Atual do Configuration Manager. A menos que você precise integrar o Intune a uma implantação do Branch Atual do Configuration Manager, recomendamos o gerenciamento do Intune no [Portal do Azure](https://portal.azure.com).

Defina sua autoridade de MDM como **Intune** para habilitar o Portal do Azure no Intune. O uso de uma autoridade de MDM diferente permite que o Intune transfira o gerenciamento do MDM para consoles de gerenciamento alternativos da Microsoft. Esses casos são incomuns.

> [!IMPORTANT]
> Se você estiver transferindo seu gerenciamento de dispositivos móvel para o Intune pela primeira vez, defina a autoridade de MDM como Intune.

-   Saiba [como definir a autoridade de gerenciamento móvel](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

## <a name="next-step"></a>Próximas etapas

[Fase 1: Configurar políticas de gerenciamento de dispositivos e aplicativos](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

