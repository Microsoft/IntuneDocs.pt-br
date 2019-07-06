---
ms.openlocfilehash: 76706fb39c3c5a69cba4fbf3f57c0b58d92e4a27
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67559974"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Requisitos de credencial do Intune e Azure AD

Autenticação e autorização têm base em credenciais do Azure AD e controle de acesso com base em função do Intune (RBAC). Todos os administradores globais e os administradores de serviço do Intune de seu locatário têm acesso ao Data warehouse por padrão. Use funções do Intune para fornecer acesso a mais usuários, concedendo acesso ao recurso **data warehouse do Intune**.

Os requisitos para acessar o Data Warehouse do Intune (incluindo a API) são:

  - O usuário deve ser um destes:
      - Administrador global do Azure AD
      - Um administrador de serviços do Intune
      - Usuário com acesso baseado em função ao recurso **data warehouse do Intune**
      - Autenticação sem usuário por meio da [autenticação somente no aplicativo](../data-warehouse-app-only-auth.md) 
