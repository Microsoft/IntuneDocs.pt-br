---
title: RBAC com o Intune
titleSuffix: Azure portal
description: "Versão prévia do Intune Azure: saiba como o RBAC permite controlar quem pode executar ações e fazer alterações."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e9dc65389485d2a77e351b5e781824eed0612054
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="role-based-administration-control-rbac-with-intune"></a>RBAC (controle de administração baseada em funções) com o Intune

O RBAC ajuda você a controlar quem pode realizar as várias tarefas do Intune em sua organização e a quem essas tarefas se aplicam. Você pode usar as funções internas que abordam alguns cenários comuns do Intune ou pode criar suas próprias funções. Uma função é definida por:

- **Definição de função**: o nome de uma função, os recursos gerenciados por ela e as permissões concedidas a cada recurso.
- **Membros**: os grupos de usuários que recebem as permissões.
- **Escopo**: os grupos de usuários ou dispositivos que podem ser gerenciados pelos membros.
- **Atribuição**: após a configuração da definição, dos membros e do escopo, a função é atribuída.

![Exemplo de RBAC do Intune](./media/intune-rbac-1.PNG)

Começando no novo Portal do Azure, o **Azure AD (Azure Active Directory)** fornece duas Funções do Diretório que podem ser usadas com o Intune. Essas funções recebem permissão total para realizar todas as atividades no Intune:

- **Administrador Global:** os usuários com essa função têm acesso a todos os recursos administrativos do Azure AD, bem como a serviços federados ao Azure AD, como o Exchange Online, SharePoint Online e Skype for Business Online. A pessoa que se inscreve no locatário do Azure AD se torna um administrador global. Somente os administradores globais podem atribuir outras funções de administrador do Azure AD. Pode haver mais de um administrador global na sua organização. Os administradores globais podem redefinir a senha de qualquer usuário e de todos os outros administradores.

- **Administrador de Serviços do Intune:** os usuários com essa função têm permissões globais no Intune quando o serviço está presente. Além disso, essa função fornece a capacidade de gerenciar usuários, dispositivos e criar e gerenciar grupos.

- **Administrador de Acesso Condicional:** os usuários com essa função só têm permissões para exibir, criar, modificar e excluir as políticas de acesso condicional.

    > [!IMPORTANT]
    > A função Administrador de Serviços do Intune não fornece a capacidade de gerenciar as configurações de acesso condicional do Azure AD.

    > [!TIP]
    > O Intune também mostra três extensões do Azure AD: **Usuários**, **Grupos** e **Acesso condicional**, que são controlados com o uso do RBAC do Azure AD. Além disso, o **Administrador de Contas de Usuário** apenas realiza as atividades do usuário/grupo do AAD e não tem permissões totais para realizar todas as atividades no Intune. Consulte [RBAC com o Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles) para obter mais detalhes.

## <a name="roles-created-in-the-intune-classic-portal"></a>Funções criadas no Portal Clássico do Intune

Somente os usuários **Administradores de Serviços** do Intune com permissões "Totais" são migrados do Portal Clássico do Intune para o Portal do Azure. Você precisa reatribuir o acesso “Somente Leitura” ou “Assistência técnica” aos usuários **Administradores de Serviços** do Intune nas funções do Intune no portal do Azure e removê-los do portal clássico.

> [!IMPORTANT]
> Talvez seja necessário manter o acesso de Administrador de Serviços do Intune no Portal Clássico, caso os administradores ainda precisem ter acesso para gerenciar computadores usando o Intune.

## <a name="built-in-roles"></a>Funções internas

As seguintes funções são internas do Intune e você pode atribuí-las a grupos sem nenhuma outra configuração:

- **Operador do Suporte Técnico**: realiza tarefas remotas em usuários e dispositivos e pode atribuir aplicativos ou políticas a usuários ou dispositivos.
- **Gerente de Política e Perfil**: gerencia a política de conformidade, os perfis de configuração, o registro da Apple e os identificadores de dispositivo corporativo.
- **Operador Somente Leitura**: exibe informações de usuário, dispositivo, registro, configuração e aplicativo. Não é possível fazer alterações no Intune.
- **Gerente de Aplicativo**: gerencia aplicativos móveis e gerenciados e pode ler informações do dispositivo.

### <a name="to-assign-a-built-in-role"></a>Para atribuir uma função interna

1. Nas **funções do Intune**, escolha a função interna que você deseja atribuir.

2. Na folha <*nome da função*> – **Propriedades**, escolha **Gerenciar** e, em seguida, **Atribuições**.

    > [!NOTE]
    > Não é possível excluir nem editar as funções internas

3. Na folha da função personalizada, escolha **Atribuir**.

4. Na folha **Atribuições de Função**, insira um **Nome** e uma **Descrição** opcional para a atribuição e, em seguida, escolha o seguinte:
    - **Membros** – Selecione um grupo que contém o usuário para o qual você deseja conceder permissões.
    - **Escopo** – Selecione um grupo que contém os usuários que o membro acima terá permissão para gerenciar.
<br></br>
5. Quando terminar, clique em **OK**. A nova atribuição é exibida na lista de atribuições.

### <a name="intune-rbac-table"></a>Tabela do RBAC do Intune

- Baixe a [tabela do RBAC do Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) para ver mais detalhes sobre o que cada função pode fazer.

## <a name="custom-roles"></a>Funções personalizadas

Você pode criar uma função personalizada que inclui as permissões necessárias para uma função de trabalho específica. Por exemplo, se um grupo do departamento de TI gerencia aplicativos, políticas e perfis de configuração, você pode adicionar todas essas permissões juntas em uma única função personalizada.

> [!IMPORTANT]
> Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões no Azure AD:
> - **Administrador Global**
> - **Administrador de Serviços do Intune**

### <a name="to-create-a-custom-role"></a>Para criar uma função personalizada

1. Entre no [portal do Azure](https://portal.azure.com) com suas credenciais do Intune.

2. Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3. Escolha **Intune**. O Painel do Intune é aberto. Escolha **Funções do Intune**.

4. Na folha **Funções do Intune**, escolha **Funções do Intune** e, depois, **Adicionar personalizada**.

5. Na folha **Adicionar Função Personalizada**, insira um nome e uma descrição para a nova função e clique em **Permissões**.

3. Na folha **Permissões**, escolha as permissões que você deseja usar com essa função. Use a [tabela do RBAC do Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) para ajudá-lo a decidir quais permissões você deseja aplicar.

4. Quando terminar, escolha **OK**.

5. Na folha **Adicionar Função Personalizada**, clique em **Criar**. A nova função é exibida na lista da folha **Funções do Intune**.

### <a name="to-assign-a-custom-role"></a>Para atribuir uma função personalizada

1. Nas **funções do Intune**, escolha a função personalizada que você deseja atribuir.

2. Na folha <*nome da função*> – **Propriedades**, escolha **Gerenciar** e, em seguida, **Atribuições**. Nessa folha, também é possível editar ou excluir funções existentes.

3. Na folha da função personalizada, escolha **Atribuir**.

4. Na folha **Atribuições de Função**, insira um **Nome** e uma **Descrição** opcional para a atribuição e, em seguida, escolha o seguinte:
    - **Membros** – Selecione um grupo que contém o usuário para o qual você deseja conceder permissões.
    - **Escopo** – Selecione um grupo que contém os usuários que o membro acima terá permissão para gerenciar.
<br></br>
5. Quando terminar, clique em **OK**. A nova atribuição é exibida na lista de atribuições.

## <a name="next-steps"></a>Próximas etapas

[Usar a função de operador de assistência técnica do Intune com o portal de solução de problemas](help-desk-operators.md)

## <a name="see-also"></a>Consulte também

[Atribuir funções usando o Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
