---
title: Configuração básica do Microsoft Intune
description: Este artigo fornece as etapas necessárias para configurar o Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7ca0983b7b637b7e85bef97cd77e6c870c4e43eb
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72510020"
---
# <a name="basic-setup"></a>Configuração básica

Depois de avaliar seu ambiente, é hora de configurar o Microsoft Intune.

## <a name="external-dependencies-for-an-intune-deployment"></a>Dependências externas para uma implantação do Intune

### <a name="identity"></a>Identidade

O Intune exige o AAD (Azure Active Directory) como o provedor de identidade e agrupamento de usuário. Saiba mais sobre:

- [Requisitos de identidade](https://docs.microsoft.com/azure/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

- [Requisitos de sincronização de diretórios](https://docs.microsoft.com/azure/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

- [MFA (autenticação multifator)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

- [Planejar seus grupos de dispositivos e de usuários](users-add.md)

- [Como criar grupos de dispositivos e de usuários](groups-get-started.md)

Se sua organização já estiver usando o Office 365, o Intune deverá usar o mesmo ambiente do Azure Active Directory.

### <a name="pki-optional"></a>PKI (opcional)

Se você estiver planejando usar a autenticação com base em certificados para perfis de VPN, Wi-Fi ou email com o Intune, verifique se você tem uma [infraestrutura de PKI em vigor](../protect/certificates-configure.md) com suporte, pronta para criar e implantar perfis de certificado. Saiba mais sobre como configurar certificados no Intune:

- [Como configurar a infraestrutura de certificado para SCEP](/intune/certificates-scep-configure)

- [Configurar a infraestrutura de certificado](/intune/certficates-pfx-configure).


## <a name="task-list-for-an-intune-setup"></a>Lista de tarefas para uma configuração do Intune

### <a name="task-1-intune-subscription"></a>Tarefa 1: Assinatura do Intune

Antes de migrar para o Intune, primeiro você precisa de uma assinatura do Intune.

- Visite [esta página](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), que fornece instruções sobre como:

  - Criar uma nova assinatura do Intune vinculada a um novo locatário do AAD.

  - Vincular a assinatura do Intune entrando em um locatário do AAD existente.

### <a name="task-2-assign-intune-user-licenses"></a>Tarefa 2: Atribuir licenças de usuário do Intune

- Saiba [como atribuir licenças de usuário do Intune](licenses-assign.md).

- Se você tiver criado um novo locatário do Azure Active Directory, saiba [como criar novos usuários ou sincronizar usuários de seu AD (Active Directory) local.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Tarefa 3: Definir sua autoridade de MDM para o Intune

O Intune pode ser gerenciado por meio do portal do Azure ou do console do Branch Atual do Configuration Manager. A menos que você precise integrar o Intune a uma implantação do Branch Atual do Configuration Manager, recomendamos que você gerencie o Intune do [Portal do Azure](https://portal.azure.com).

Defina sua autoridade de MDM como **Intune** para habilitar o Portal do Azure no Intune. O uso de uma autoridade de MDM diferente permite que o Intune transfira o gerenciamento do MDM para consoles de gerenciamento alternativos da Microsoft. Esses casos são incomuns.

> [!IMPORTANT]
> Se você estiver transferindo seu gerenciamento de dispositivos móvel para o Intune pela primeira vez, defina a autoridade de MDM como Intune.

Saiba [como definir a autoridade de gerenciamento móvel](mdm-authority-set.md).

## <a name="next-step"></a>Próxima etapa

Configure [políticas de gerenciamento de dispositivos e aplicativos](../migration-guide-configure-policies.md).
