---
ms.openlocfilehash: 8483ed3d4198e228bdaaf4723b2c9c0dca9cecfc
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71830503"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Requisitos de credencial do Intune e Azure AD

Autenticação e autorização têm base em credenciais do Azure AD e controle de acesso com base em função do Intune (RBAC). Todos os administradores globais e os administradores de serviço do Intune de seu locatário têm acesso ao Data warehouse por padrão. Use funções do Intune para fornecer acesso a mais usuários, concedendo acesso ao recurso **data warehouse do Intune**.

Os requisitos para acessar o Data Warehouse do Intune (incluindo a API) são:

- O usuário deve ser um destes:
  - Administrador global do Azure AD
  - Um administrador de serviços do Intune
  - Usuário com acesso baseado em função ao recurso **data warehouse do Intune**
  - Autenticação sem usuário por meio da [autenticação somente no aplicativo](../developer/data-warehouse-app-only-auth.md) 
