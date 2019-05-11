---
ms.openlocfilehash: 015e50d24149a6b6242eda86d5f3d62489e9955d
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511312"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Requisitos de credencial do Intune e Azure AD

Autenticação e autorização têm base em credenciais do Azure AD e controle de acesso com base em função do Intune (RBAC). Todos os administradores globais e os administradores de serviço do Intune de seu locatário têm acesso ao Data warehouse por padrão. Use funções do Intune para fornecer acesso a mais usuários, concedendo acesso ao recurso **data warehouse do Intune**.

Os requisitos para acessar o Data Warehouse do Intune (incluindo a API) são:

  -  O usuário deve ser um destes:
      -  Administrador global do Azure AD
      -  Um administrador de serviços do Intune
      -  Usuário com acesso baseado em função ao recurso **data warehouse do Intune**
      -  Autenticação sem usuário por meio da [autenticação somente no aplicativo](../data-warehouse-app-only-auth.md) 
