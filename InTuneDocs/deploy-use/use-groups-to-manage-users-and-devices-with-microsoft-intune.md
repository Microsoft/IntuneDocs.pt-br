---
title: "Usar grupos para gerenciar usuários e dispositivos | Microsoft Intune"
description: "Crie e gerencie grupos usando o espaço de trabalho Grupos."
keywords: 
author: Mtillman
ms.author: mtillman
manager: angrobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 46fd83ac8048a313b0fe4f15e01563698bf7995c


---
# <a name="use-groups-to-manage-users-and-devices-in-microsoft-intune"></a>Usar grupos para gerenciar usuários e dispositivos no Microsoft Intune

Este tópico descreve como criar grupos no Intune. Ele também fornece informações sobre como o gerenciamento de grupos será alterado nos próximos meses. 

>[!IMPORTANT]
>
>Se você abrir o espaço de trabalho Grupos no portal do Intune e vir um link para o portal do Azure AD (Azure Active Directory), você já está usando a *nova* abordagem aos grupos de segurança do Azure AD no Intune, descrito em [Aviso de futuras melhorias para a experiência de administração de grupos](#notice-of-upcoming-improvements-to-the-admin-experience-for-groups). Clique no link para o portal do Azure AD para criar e gerenciar seus grupos.
>
>![Captura de tela do link para o gerenciamento de grupo do Azure](../media/groups-link-azure.png) 
>
>Se você não ver o link para o portal do Azure AD, você ainda estará usando a abordagem *atual* ao gerenciamento de grupos, descrita em [Criar grupos para gerenciar usuários e dispositivos no Microsoft Intune](#Create-groups-to-manage-users-and-devices-with-Microsoft-Intune) neste tópico.


## <a name="notice-of-upcoming-improvements-to-the-admin-experience-for-groups"></a>Aviso de futuras melhorias para a experiência de administração de grupos

Vocês nos informaram que gostariam de ter uma experiência de agrupamento e direcionamento no Enterprise Mobility + Security. Nós ouvimos. Com base em seus comentários, em breve converteremos os grupos do Intune em grupos de segurança baseados no Azure Active Directory. Essa mudança unificará o gerenciamento de grupos no Intune e no Azure Active Directory (Azure AD). A nova experiência significa que você não terá que duplicar grupos entre serviços. Ela também fornecerá extensibilidade por meio de opções para usar o Windows PowerShell e o Microsoft Graph.

### <a name="how-does-this-affect-me-right-now"></a>Como isso afeta me agora?
Se você já for cliente do Intune, essa alteração não o afetará. Mas veja o que está por vir:

-   As contas novas usarão grupos de segurança do Azure AD em vez dos grupos de *usuário* do Intune.   
-   Em novembro de 2016, as novas contas que forem provisionadas após a versão de serviço mensal gerenciarão grupos baseados em usuários e dispositivos no portal do Azure AD. Não haverá nenhum efeito sobre clientes existentes.
-   Em dezembro de 2016, a equipe de produtos do Intune iniciará a migração de clientes existentes para a nova experiência de gerenciamento de grupos baseada no Azure AD. Todos os grupos de usuários e dispositivos que existem no Intune serão migrados para os grupos de segurança do Azure AD. Não começaremos as migrações até que possamos minimizar o efeito sobre seu trabalho diário e quando esperarmos que não haja nenhum efeito sobre seus usuários. Também notificaremos você antes de migrar sua conta.


### <a name="how-and-when-will-i-migrate-to-the-new-groups-experience"></a>Como e quando eu migrarei para a nova experiência de grupos?
Nós migraremos clientes atuais do Intune durante um período. Estamos finalizando o cronograma da migração e atualizaremos este tópico em algumas semanas para dar mais detalhes. Você receberá um aviso antes de ser migrado. Se tiver preocupações relacionadas à migração, entre em contato com nossa equipe de migração em [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com). Consulte [Migrando grupos para o Azure Active Directory](migrating-groups-to-azure-active-directory.md) para obter detalhes sobre como os grupos serão migrados.

### <a name="what-happens-to-my-existing-user-and-device-groups"></a>O que acontece com meus grupos de usuários e dispositivos existentes?
 Grupos de usuários e grupos de dispositivos que você criou no Intune serão migrados para grupos de segurança do Azure AD. Grupos padrão do Intune, como o grupo Todos os Usuários, serão migrados apenas se você os estiver usando em implantações no momento da migração. A migração pode ser mais complexa para alguns grupos. Você será notificado se etapas adicionais forem necessárias para a migração em sua organização.

### <a name="what-new-features-will-be-available-to-me"></a>Quais novos recursos estarão disponíveis para mim?
Estas são as novas funcionalidades que introduziremos com essa migração do Intune para o Azure Active Directory:

-    Os grupos de segurança do Azure AD terão suporte do Intune para todos os tipos de implantações.
-    Os grupos de segurança do Azure AD darão suporte ao agrupamento de dispositivos e usuários.
-    Os grupos de segurança do Azure AD darão suporte a grupos dinâmicos que têm atributos de dispositivos do Intune. Por exemplo, você poderá agrupar dinamicamente os dispositivos com base na plataforma, como iOS. Quando um novo dispositivo iOS for registrado em sua organização, ele será adicionado automaticamente ao grupo dinâmico de dispositivos iOS.
-    Você terá uma experiência de administração compartilhada para o gerenciamento de grupos no Azure AD e no Intune.
- A função de Administrador de serviços do Intune será adicionada ao Azure AD para que os administradores de serviço do Intune possam executar tarefas de gerenciamento de grupos no Azure AD.

### <a name="what-intune-functionality-wont-be-available"></a>Quais funcionalidades do Intune não estarão disponíveis?
Embora a experiência de grupos vá melhorar, haverá algumas funcionalidades do Intune que não estarão disponíveis após sua organização migrar dos grupos do Intune para os grupos de segurança do Azure AD.

#### <a name="group-management-functionality"></a>Funcionalidade de gerenciamento de grupos

-   Após a migração, você não poderá excluir membros ou grupos quando criar um novo grupo. No entanto, com os grupos dinâmicos do Azure AD, você pode usar atributos para criar regras avançadas que pode usar para excluir os membros de um grupo com base nos critérios que definir.
-   Não haverá suporte para grupos Usuários Desagrupados e Dispositivos Desagrupados. Nós não migraremos esses grupos do Intune para o Azure AD.


#### <a name="group-dependent-functionality"></a>Funcionalidade dependente de grupo

-   A função de Administrador de serviço não terá permissões para **Gerenciar grupos**.
-   Não será possível agrupar dispositivos do Exchange ActiveSync. O grupo Todos os Dispositivos Gerenciados pelo EAS será convertido de um grupo para um modo de exibição de relatório.
-  A dinamização com grupos em relatórios não estará disponível.
-  O direcionamento de grupos personalizados de regras de notificação não estará disponível.

### <a name="what-should-i-do-to-prepare-for-this-change"></a>O que eu devo fazer para me preparar para essa alteração?
 Temos recomendações que facilitarão essa transição para você:

- Limpe quaisquer grupos indesejados ou desnecessários do Intune antes da migração.
- Avalie seu uso da exclusão em grupos e considere recriar seus grupos de modo que não precisa usar a exclusão.
-  Se você tiver administradores que não têm permissões para criar grupos no Azure AD, peça que o administrador do Azure AD os adicione à função Administrador de serviços do Intune do Azure AD.


## <a name="create-groups-to-manage-users-and-devices-with-microsoft-intune"></a>Criar grupos para gerenciar usuários e dispositivos com o Microsoft Intune

Esta seção descreve como criar grupos do Intune no console de administração do Intune.

Você pode criar e gerenciar grupos no espaço de trabalho **Grupos** no console de administração do Microsoft Intune. A página **Visão Geral dos Grupos** mostra resumos de status que podem ajudar a identificar e priorizar problemas que exigem a sua atenção. Os resumos de status abordam essas áreas:

-   Alertas
-   Atualizações de software
-   Endpoint Protection
-   Política
-   Gerenciamento de software

Sua hierarquia de grupo também exibe resumos de status para ajudar você a identificar e resolver problemas dos membros de um grupo selecionado.

## <a name="create-groups"></a>Criar grupos

> [!TIP]
> Quando criar grupos, pense em como você aplicará políticas. Por exemplo, você pode ter políticas específicas ao sistema operacional de um dispositivo e políticas específicas a diferentes funções em sua organização ou a unidades organizacionais que você já definiu no Active Directory. Pode ser útil ter grupos de dispositivos separados para iOS, Android e Windows, bem como um grupo de usuários para cada função organizacional.
>
> É possível que você também queira criar uma política padrão que se aplica a todos os grupos e dispositivos, para estabelecer os requisitos de conformidade básicos da sua organização. Em seguida, você pode criar políticas mais específicas para as categorias mais amplas de usuários e dispositivos. Por exemplo, você pode criar políticas de email para cada um dos sistemas operacionais do dispositivo.
>
> Preste atenção ao nomear suas políticas para que você possa identificá-las facilmente mais tarde. Por exemplo, um bom nome descritivo para uma política é **Política de email do WP para toda a empresa**.
>
> Sempre que criar uma política restritiva, é recomendável comunicá-la aos seus usuários. Depois de criar os grupos e políticas mais gerais, fique atento ao criar os grupos menores para reduzir a comunicação desnecessária.

### <a name="to-create-a-device-group"></a>Para criar um grupo de dispositivos

1.  No console de administração do Intune, escolha **Grupos** &gt; **Visão geral** &gt; **Criar Grupo**.

2.  Insira um nome e uma descrição (opcional) para o grupo e selecione um grupo de dispositivos como o grupo pai. Escolha **Avançar**.

3.  Na página **Definir Critérios de Associação**, selecione o tipo de dispositivos que serão incluídos no grupo. Você tem opções de configurações de grupo adicionais com base nos tipos de dispositivos que optar por incluir:

    -   **Computador**. Selecione se deseja incluir todos os membros do grupo pai, as unidades organizacionais e os domínios que deseja incluir ou excluir. Você pode obter informações sobre o domínio e a unidade organizacional de um computador do inventário.

    -   **Móvel**. Selecione se deseja incluir somente dispositivos móveis que são gerenciados pelo Intune, dispositivos móveis que são gerenciados pelo Exchange ActiveSync ou ambos.

    -   **Todos os dispositivos**. Esta opção inclui todos os dispositivos, sem exceções com base em critérios.

4.  Na página **Definir Associação Direta**, escolha **Procurar** para selecionar dispositivos individuais a serem incluídos ou excluídos. Se você selecionar dispositivos que não estão no grupo pai especificado, o Intune adicionará automaticamente esses dispositivos ao grupo pai.

5.  Na página **Resumo**, examine suas seleções e escolha **Concluir**.

O grupo recém-criado é mostrado na lista **Grupos**, no espaço de trabalho **Grupos**, no grupo pai. Nesse local, também é possível editar ou excluir o grupo.

### <a name="to-create-a-user-group"></a>Para criar um grupo de usuários

1.  No console de administração do Intune, escolha **Grupos** &gt; **Visão geral** &gt; **Criar Grupo**.

2.  Insira um nome e uma descrição (opcional) para o grupo e selecione um grupo de usuários como o grupo pai. Escolha **Avançar**.

3.  Na página **Definir Critérios de Associação**, escolha se deseja incluir todos os membros do grupo pai ou começar com um grupo vazio. Depois, inclua ou exclua membros com base nos grupos de segurança de usuários que foram configurados manualmente no [centro de administração do Office 365](http://go.microsoft.com/fwlink/?LinkId=698854) ou que foram sincronizados do Active Directory. Se a associação de um grupo de segurança for alterada, a associação de grupos de usuários baseada nesse grupo de segurança também poderá mudar.

    > [!IMPORTANT]
    > No momento, se o seu grupo incluir membros de grupos de segurança ou grupos de gerenciamento específicos, e você excluir membros de alguns grupos, os membros incluídos inicialmente serão removidos. Para criar um grupo que tenha membros incluídos e excluídos, é recomendável que primeiro você crie um grupo pai que tenha os membros incluídos. Em seguida, crie um grupo filho para esse grupo pai. No novo grupo filho, liste os membros excluídos. Então, use esse grupo filho para gerenciar a distribuição de aplicativos, perfis e políticas do Intune.

    > [!NOTE]
    > No portal do Azure, você pode criar grupos com base nos gerentes a que os usuários são subordinados. Esse tipo de grupo é dinâmico e muda conforme os funcionários são adicionados ou removidos da equipe do gerente no Azure Active Directory. O procedimento para criar um grupo do Azure baseado no nome do gerente é descrito em [Usar atributos para criar regras avançadas](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) na seção **Para configurar um grupo como grupo de “Gerente”**.

4.  Na página **Definir Associação Direta**, escolha **Procurar** para selecionar usuários individuais a serem incluídos ou excluídos. Se você selecionar os usuários que não estão no grupo pai especificado, esses dispositivos serão automaticamente adicionados ao grupo pai. A opção de adicionar manualmente um usuário está na parte inferior da caixa de diálogo **Selecionar Membros**. Isso é útil se você quiser adicionar um usuário que ainda não tem um dispositivo registrado.

5.  Na página **Resumo**, examine suas seleções e escolha **Concluir**.

O grupo recém-criado é mostrado na lista **Grupos**, no espaço de trabalho **Grupos**, no grupo pai. Nesse local, também é possível editar ou excluir o grupo.

> [!TIP]
> Grupos de segurança são um bom recurso para usar ao popular grupos de usuários. Como os grupos de segurança definem quem tem acesso a quais recursos, eles podem ser bem traduzidos em grupos de usuários do Intune. Os grupos de segurança que são sincronizados do Active Directory para o Azure Active Directory, criados diretamente no Azure Active Directory por meio do centro de administração do Office 365 ou do portal do Azure, estão disponíveis para serem usados quando você criar grupos de usuários no Intune.

## <a name="filter-admin-views-by-role"></a>Filtrar modos de exibição de administrador por função
Nos modos de exibição de grupo filtrados, você pode ajustar o que um administrador de TI pode ver com base na função do administrador. Você também pode restringir quais grupos cada administrador de TI pode gerenciar. Isso pode ser útil quando:

-   Você quer que seus administradores de TI só possam implantar itens em dispositivos e usuários específicos
-   Você quer que seus administradores de TI vejam apenas os grupos que são relevantes para esse administrador

Você pode configurar as exibições de grupo filtrado para administradores de serviço no console do administrador do Intune. Para detalhes, confira [What to know before you start Microsoft Intune](/intune/get-started/what-to-know-before-you-start-microsoft-intune) (O que saber antes de iniciar o Microsoft Intune).

Depois de definir modos de exibição de grupo filtrados para um administrador de serviço, quando o administrador implantar software ou políticas ou executar relatórios, ele pode exibir e selecionar apenas os grupos que você especificou. O administrador também não ver informações de status nas seguintes páginas do console do administrador:

-   **Visão geral do sistema**
-   **Visão geral dos grupos**
-   **Visão geral do Endpoint Protection**
-   **Visão geral dos alertas**
-   **Visão geral de softwares**
-   **Visão geral das políticas**

### <a name="to-create-a-filtered-group-view"></a>Para criar um modos de exibição de grupo filtrado

1.  No console de administração do Intune, escolha **Admin** &gt; **Gerenciamento de Administradores** &gt; **Administradores de Serviço**.

2.  Selecione o administrador do serviço para o qual você deseja criar um modo de filtrado e escolha **Gerenciar Grupos**.

3.  Na caixa de diálogo **Selecionar os grupos que serão visíveis para esse administrador de serviços**, adicione os grupos que o administrador de serviços poderá acessar e escolha **OK**.

Depois de configurar os modos de exibição do grupo filtrado, o administrador de TI será capaz de exibir e selecionar apenas os grupos que você indicou.

## <a name="manage-your-groups"></a>Gerenciar seus grupos
Depois de criar os grupos, você pode continuar a gerenciá-los de acordo com as necessidades da sua organização.

Você pode editar o grupo para alterar seu nome ou descrição e quem pertence ao grupo.

Você pode excluir um grupo que não atenda às necessidades da sua organização. Excluir um grupo não exclui os usuários que pertencem a esse grupo.

## <a name="next-steps"></a>Próximas etapas
Depois de configurar seus grupos e políticas, verifique as implicações práticas do seu design, examinando o **Valor pretendido** e o **Status**.

### <a name="to-check-your-design"></a>Para verificar o design

1. Selecione qualquer dispositivo de um grupo de dispositivos e percorra as categorias de informações na parte superior da página.
2. Escolha **Política**. Você verá algo parecido com esta captura de tela das configurações de política de dispositivo do Android.

![Exemplo de política de configuração do Android](../media/Intune-Device-Policy-v.2.jpg)

Cada política tem um **Valor Pretendido** e um **Status**. O valor pretendido é o que você quis realizar ao atribuir a política. O status é o que você realizou quando todas as politicas que se aplicam ao dispositivo, bem como as restrições e requisitos de hardware e de sistema operacional, são consideradas em conjunto. Nesta captura de tela, você pode ver dois exemplos claros:

-   **Permitir senhas simples** é definido como **Sim**, conforme mostrado na coluna **Valor Pretendido**, mas o **Status** é **Não aplicável**. Isso ocorre porque senhas simples não têm suporte para dispositivos Android.
-   Da mesma forma, o item de política expandido **Configurações de email para dispositivos iOS** não é aplicado a esse dispositivo porque se trata de um dispositivo Android.

> [!NOTE]
> Lembre-se de que, quando duas políticas com diferentes níveis de restrição aplicam-se ao mesmo dispositivo ou usuário, a política mais restritiva se aplica na prática.



<!--HONumber=Nov16_HO1-->


