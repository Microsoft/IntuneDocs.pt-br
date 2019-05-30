---
title: RBAC (controle de acesso baseado em função) com o Microsoft Intune
description: Saiba como o RBAC permite controlar quem pode executar ações e fazer alterações no Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7419a316018ed5c883f89a51090a852680cd9e38
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66040674"
---
# <a name="role-based-access-control-rbac-with-microsoft-intune"></a>RBAC (controle de acesso baseado em função) com o Microsoft Intune

O RBAC (controle de acesso baseado em função) ajuda a gerenciar quem tem acesso aos recursos da sua organização e o que eles podem fazer com esses recursos.  Ao [atribuir funções](assign-role.md) aos usuários do Intune, é possível limitar o que eles podem ver e alterar. Cada função tem um conjunto de permissões que determinam o que os usuários com essa função podem acessar e alterar dentro de sua organização.

Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões no Azure AD:
- **Administrador Global**
- **Administrador de Serviços do Intune** (também conhecido como **Administrador do Intune**)

## <a name="roles"></a>Funções
Uma função define o conjunto de permissões concedido aos usuários atribuídos a essa função.
É possível usar as funções internas e personalizadas. As funções internas abordam alguns cenários comuns do Intune. É possível [criar suas próprias funções personalizadas](create-custom-role.md) com o conjunto exato de permissões necessárias. Várias funções do Azure Active Directory têm permissões para o Intune.
Para ver uma função, escolha **Intune** > **Funções** > **Todas as funções** > escolha uma função. Você verá as seguintes páginas:

-   **Propriedades**: o nome, a descrição, o tipo, as atribuições e as marcas de escopo para a função. 
-   **Permissões**: lista um grande conjunto de alternâncias que definem quais permissões a função tem.
-   **Atribuições**: uma lista das [atribuições de função]( assign-role.md) que define quais usuários têm acesso a quais usuários/dispositivos. Uma função pode ter várias atribuições e um usuário pode estar em várias atribuições.

### <a name="built-in-roles"></a>Funções internas
Você pode atribuir funções internas a grupos sem configuração adicional. Não é possível excluir nem editar o nome, a descrição, o tipo ou as permissões de uma função interna. Para obter uma lista completa das permissões de cada função interna, confira a [Tabela do RBAC do Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

- **Operador de suporte técnico**: realiza tarefas remotas em usuários e dispositivos e pode atribuir aplicativos ou políticas a usuários ou dispositivos.
- **Política e Gerenciador de Perfis**: gerencia a política de conformidade, os perfis de configuração, o registro da Apple, os identificadores de dispositivo corporativo e as linhas de base de segurança.
- **Operador somente leitura**: exibe informações de usuário, dispositivo, registro, configuração e aplicativo. Não é possível fazer alterações no Intune.
- **Gerenciador de Aplicativos**: gerencia os aplicativos móveis e gerenciados, pode ler as informações do dispositivo e pode exibir os perfis de configuração do dispositivo.
- **Administrador de Função do Intune**: gerencia funções personalizadas do Intune e adiciona atribuições a funções internas do Intune. É a única função do Intune que pode atribuir permissões a Administradores.
- **Administrador de Escola**: Gerencia dispositivos Windows 10 no [Intune para Educação](introduction-intune-education.md).

### <a name="custom-roles"></a>Funções personalizadas
É possível criar suas próprias funções com permissões personalizadas. Para saber mais informações sobre funções personalizadas, confira [Criar uma função personalizada](create-custom-role.md).

### <a name="azure-active-directory-roles-with-intune-access"></a>Funções do Azure Active Directory com o acesso do Intune
| Função do Azure Active Directory | Todos os dados do Intune | Dados de auditoria do Intune |
| --- | :---: | :---: |
| Administrador Global | Leitura/gravação | Leitura/gravação |
| Administrador de Serviços do Intune | Leitura/gravação | Leitura/gravação |
| Administrador de Acesso Condicional | Nenhum | Nenhum |
| Administrador de Segurança | Somente leitura | Somente leitura |
| Operador de segurança | Somente leitura | Somente leitura |
| Leitor de segurança | Somente leitura | Somente leitura |
| Administrador de conformidade | Nenhum | Somente leitura |
| Administrador de dados de conformidade | Nenhum | Somente leitura |

> [!TIP]
> O Intune também mostra três extensões do Azure AD: **Usuários**, **Grupos** e **Acesso condicional**, que são controlados com o uso do RBAC do Azure AD. Além disso, o **Administrador de Contas de Usuário** apenas realiza as atividades do usuário/grupo do AAD e não tem permissões totais para realizar todas as atividades no Intune. Para saber mais, confira [RBAC com o Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).
### <a name="roles-created-in-the-intune-classic-portal"></a>Funções criadas no Portal Clássico do Intune
Somente os usuários **Administradores de Serviços** do Intune com permissões "Totais" são migrados do Portal Clássico do Intune para o Portal do Azure. Você deve reatribuir o acesso "Somente Leitura" ou "Assistência técnica" aos usuários **Administradores de Serviços** do Intune nas funções do Intune no portal do Azure e removê-los do portal clássico.
> [!IMPORTANT]
> Talvez seja necessário manter o acesso de Administrador de Serviços do Intune no Portal Clássico, caso os administradores ainda precisem ter acesso para gerenciar computadores usando o Intune.

## <a name="role-assignments"></a>Atribuições de função
Uma atribuição de função define:

- quais usuários são atribuídos à função
- quais recursos eles podem ver
- quais recursos eles podem alterar.

É possível atribuir funções internas e personalizadas a seus usuários. Para receber uma função do Intune, o usuário deve ter uma licença do Intune.
Para ver uma atribuição de função, escolha **Intune** > **Funções** > **Todas as funções** > escolha uma atribuição. Você verá as seguintes páginas:

-   **Propriedades**: o nome, a descrição, a função, os membros, os escopos e as marcas da atribuição.
-   **Membros**: todos os usuários em grupos listados têm permissão para gerenciar os usuários/dispositivos listados no Escopo (Grupos).
-   **Escopo (Grupos)**: todos os usuários/dispositivos nesses grupos podem ser gerenciados pelos usuários em Membros.
-   **[Escopo (Marcas)](scope-tags.md)**: os usuários em Membros podem ver os recursos que têm as mesmas marcas de escopo.

### <a name="multiple-role-assignments"></a>Várias atribuições de função
Se um usuário tiver várias atribuições de função, as permissões nelas se estenderão a diferentes objetos, da seguinte maneira:

- permissões para atribuir aplicam-se somente aos objetos (como políticas ou aplicativos) no Escopo (grupos) de atribuição dessa função. permissões para atribuir não se aplicam a objetos em outras atribuições de função, a menos que outra atribuição especificamente os conceda.
- outras permissões (como de criação e leitura), que se aplicam a todos os objetos do mesmo tipo (como todas as políticas ou todos os aplicativos) em qualquer uma das atribuições do usuário.
- permissões para objetos de tipos diferentes (como políticas ou aplicativos) não se aplicam umas às outras. uma permissão de leitura para uma política, por exemplo, não fornece uma permissão de leitura a aplicativos nas atribuições do usuário.

## <a name="next-steps"></a>Próximas etapas
- [Atribuir uma função a um usuário](assign-role.md)
- [Criar uma função personalizada](create-custom-role.md)
