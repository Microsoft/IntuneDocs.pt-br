---
title: RBAC com o Microsoft Intune
description: Saiba como o RBAC (Controle de Acesso Baseado em Função) permite controlar quem executa ações e faz alterações no Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/27/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2a0c230e89944b4330582fe4c6933ca1fe717aec
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329983"
---
# <a name="role-based-administration-control-rbac-with-microsoft-intune"></a>RBAC (Controle de administração baseada em funções) com o Microsoft Intune

O RBAC ajuda você a controlar quem pode realizar as várias tarefas do Intune em sua organização e a quem essas tarefas se aplicam. Você pode usar as funções internas que abordam alguns cenários comuns do Intune ou pode criar suas próprias funções. Uma função é definida por:

- **Definição de função**: o nome de uma função, os recursos gerenciados por ela e as permissões concedidas a cada recurso.
- **Membros**: os grupos de usuários que recebem as permissões.
- **Escopo**: os grupos de usuários ou dispositivos que podem ser gerenciados pelos membros.
- **Atribuição**: após a configuração da definição, dos membros e do escopo, a função é atribuída.

![Exemplo de RBAC do Intune](./media/intune-rbac-1.PNG)

Começando no novo Portal do Azure, o **Azure AD (Azure Active Directory)** fornece duas Funções do Diretório que podem ser usadas com o Intune. Essas funções recebem permissão total para realizar todas as atividades no Intune:

- **Administrador Global:** os usuários com essa função têm acesso a todos os recursos administrativos do Azure AD, bem como a serviços federados ao Azure AD, como o Exchange Online, SharePoint Online e Skype for Business Online. A pessoa que se inscreve no locatário do Azure AD se torna um administrador global. Somente os administradores globais podem atribuir outras funções de administrador do Azure AD. Pode haver mais de um administrador global na sua organização. Os administradores globais podem redefinir a senha de qualquer usuário e de todos os outros administradores.

- **Administrador de Serviços do Intune:** os usuários com essa função têm permissões globais no Intune quando o serviço está presente. Ainda, além de quaisquer restrições substitutas do Azure, essa função permite de gerenciar usuários, dispositivos e criar e gerenciar grupos do Intune.

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
- **Gerenciador de Aplicativos**: gerencia os aplicativos móveis e gerenciados, pode ler as informações do dispositivo e pode exibir os perfis de configuração do dispositivo.
- **Administrador de Funções do Intune**: gerencia funções personalizadas do Intune e adiciona atribuições a funções internas do Intune. É a única função do Intune que pode atribuir permissões a Administradores.
- **Administrador de Escola**: gerencia dispositivos Windows 10 no [Intune para Educação](introduction-intune-education.md) e pode executar as seguintes ações: 

|Permissão|Operação|
|---|---|
|Dados de Auditoria|Ler|
|DeviceConfigurations|Atribuir, criar, excluir, ler, atualizar|
|Gerenciadores de Registro de Dispositivos|Ler, atualizar|
|Dispositivos Gerenciados|Ler, atualizar<!--, Delete [To be added in 1803]-->|
|Aplicativos móveis|Atribuir, criar, excluir, ler, atualizar|
|Relatórios|Ler|
|Ações remotas|Limpar computador, reinicializar, bloqueio remoto, desativar, sincronizar dispositivos, apagar|
|Organização|Ler|

### <a name="to-assign-a-built-in-role"></a>Para atribuir uma função interna

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Funções** > **Todas as funções**.
1. No painel **Funções do Intune – Todas as funções**, escolha a função interna que você deseja atribuir.

2. No painel <*nome da função*> – **Visão Geral**, escolha **Gerenciar** e **Atribuições**.

    > [!NOTE]
    > Não é possível excluir nem editar as funções internas

3. No painel da função personalizada, escolha **Atribuir**.

4. No painel **Atribuições de Função**, insira um **Nome** e uma **Descrição** opcional para a atribuição e escolha o seguinte:
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

2. Escolha **Todos os serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3. Escolha **Intune** > **Funções** > **Todas as funções** > **Adicionar personalizada**.

4. No painel **Adicionar Função Personalizada**, insira um nome e uma descrição para a nova função e clique em **Permissões**.

5. No painel **Permissões**, escolha as permissões que você deseja usar com essa função. Use a [tabela do RBAC do Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) para ajudá-lo a decidir quais permissões você deseja aplicar.

6. Quando terminar, escolha **OK**.

7. No painel **Adicionar Função Personalizada**, clique em **Criar**. A nova função é exibida na lista no painel **Funções do Intune – Todas as funções**.

### <a name="to-assign-a-custom-role"></a>Para atribuir uma função personalizada

1. No painel **Funções do Intune – Todas as funções**, escolha a função personalizada que você deseja atribuir.

2. No painel <*nome da função*> – **Visão Geral**, escolha **Gerenciar** e **Atribuições**. Nesse painel, também é possível editar ou excluir as funções existentes.

3. No painel da função personalizada, escolha **Atribuir**.

4. No painel **Atribuições de Função**, insira um **Nome** e uma **Descrição** opcional para a atribuição e escolha o seguinte:
    - **Membros** – Selecione um grupo que contém o usuário para o qual você deseja conceder permissões.
    - **Escopo** – Selecione um grupo que contém os usuários que o membro acima terá permissão para gerenciar.
<br></br>
5. Quando terminar, clique em **OK**. A nova atribuição é exibida na lista de atribuições.

## <a name="next-steps"></a>Próximas etapas

[Usar a função de operador de assistência técnica do Intune com o portal de solução de problemas](help-desk-operators.md)

## <a name="see-also"></a>Consulte também

[Atribuir funções usando o Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
