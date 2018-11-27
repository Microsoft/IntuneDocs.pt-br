---
title: Configuração básica do Microsoft Intune
description: Este artigo fornece as etapas necessárias para configurar o Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.openlocfilehash: 4cec5c593fd4191a9d73e77b13fd38df81a7fe8b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179738"
---
# <a name="basic-setup"></a>Configuração básica

Depois de avaliar seu ambiente, é hora de configurar o Microsoft Intune.

## <a name="external-dependencies-for-an-intune-deployment"></a>Dependências externas para uma implantação do Intune

### <a name="identity"></a>Identidade

O Intune exige o AAD (Azure Active Directory) como o provedor de identidade e agrupamento de usuário. Saiba mais sobre:

-  [Requisitos de identidade](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

-   [Requisitos de sincronização de diretórios](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

-   [Requisitos de MFA (autenticação multifator)](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

-   [Planejar seus grupos de dispositivos e de usuários](users-add.md)

-   [Como criar grupos de dispositivos e de usuários](groups-get-started.md)

Se sua organização já estiver usando o Office 365, o Intune deverá usar o mesmo ambiente do Azure Active Directory.

### <a name="pki-optional"></a>PKI (opcional)

Se você estiver planejando usar a autenticação com base em certificados para perfis de VPN, Wi-Fi ou email com o Intune, verifique se você tem uma [infraestrutura de PKI em vigor](certificates-configure.md) com suporte, pronta para criar e implantar perfis de certificado. Saiba mais sobre como configurar certificados no Intune:

-   [Como configurar a infraestrutura de certificado para SCEP](/intune/certificates-scep-configure)

-   [Configurar a infraestrutura de certificado](/intune/certficates-pfx-configure).


## <a name="task-list-for-an-intune-setup"></a>Lista de tarefas para uma configuração do Intune

### <a name="task-1-intune-subscription"></a>Tarefa 1: Assinatura do Intune

Antes de migrar para o Intune, primeiro você precisa de uma assinatura do Intune.

-   Visite [esta página](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), que fornece instruções sobre como:

    -   Criar uma nova assinatura do Intune vinculada a um novo locatário do AAD.

    -   Vincular a assinatura do Intune entrando em um locatário do AAD existente.

### <a name="task-2-assign-intune-user-licenses"></a>Etapa 2: Atribuir licenças de usuário do Intune

-   Saiba [como atribuir licenças de usuário do Intune](licenses-assign.md).

-   Se você tiver criado um novo locatário do Azure Active Directory, saiba [como criar novos usuários ou sincronizar usuários de seu AD (Active Directory) local.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Tarefa 3: Definir sua autoridade de MDM para o Intune

O Intune pode ser gerenciado por meio do portal do Azure ou do console do Branch Atual do Configuration Manager. A menos que você precise integrar o Intune a uma implantação do Branch Atual do Configuration Manager, recomendamos que você gerencie o Intune do [Portal do Azure](https://portal.azure.com).

Defina sua autoridade de MDM como **Intune** para habilitar o Portal do Azure no Intune. O uso de uma autoridade de MDM diferente permite que o Intune transfira o gerenciamento do MDM para consoles de gerenciamento alternativos da Microsoft. Esses casos são incomuns.

> [!IMPORTANT]
> Se você estiver transferindo seu gerenciamento de dispositivos móvel para o Intune pela primeira vez, defina a autoridade de MDM como Intune.

Saiba [como definir a autoridade de gerenciamento móvel](mdm-authority-set.md).

## <a name="next-step"></a>Próxima etapa

Configure [políticas de gerenciamento de dispositivos e aplicativos](migration-guide-configure-policies.md).
