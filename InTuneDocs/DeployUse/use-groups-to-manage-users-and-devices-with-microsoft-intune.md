---
title: "Usar grupos para gerenciar usuários e dispositivos | Microsoft Intune"
description: "Crie e gerencie grupos usando o espaço de trabalho Grupos."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab9592c253238fd832f8b48372e5474fcfc5331
ms.openlocfilehash: 96b0cd997544b2013efaca818d614c9802baaa46


---
## Aviso sobre futuras melhorias para a experiência de administração de grupos

Com base nos seus comentários relativos a ter uma experiência de agrupamento e direcionamento no Enterprise Mobility + Security, estamos convertendo os Grupos do Intune para Grupos de segurança baseados no Azure Active Directory. Isso unificará o gerenciamento de grupos no Intune e no Azure Active Directory (Azure AD). Com a nova experiência, você não precisará duplicar grupos entre os serviços e terá extensibilidade usando o PowerShell e o Graph. 

### Como isso afeta me agora?
A alteração não afeta você agora, mas podemos contar quais são as novidades:

-   em setembro, novas contas provisionadas após a versão de serviço mensal usarão os grupos de segurança do Azure AD em vez dos grupos de usuários do Intune.   
-   em outubro, novas contas provisionadas após a versão de serviço mensal gerenciarão grupos baseados em usuários e dispositivos no portal do Azure AD. Não há impacto para os clientes existentes
-   em novembro, a equipe de produto do Intune iniciará a migração de clientes existentes para a nova experiência de gerenciamento de grupos baseada no Azure AD. Todos os grupos de usuários e dispositivos que atualmente estão no Intune serão migrados para os grupos de segurança do Azure AD. A migração será feita em lotes a partir de novembro. Não começaremos as migrações até que possamos minimizar o impacto sobre seu trabalho diário e esperamos não afetar o usuário final. Também o avisaremos antes da migração da sua conta.


### Como e quando eu migrarei para a nova experiência de grupos?
Os clientes atuais serão migrados ao longo de um período. Estamos finalizando o cronograma da migração e atualizaremos este tópico em algumas semanas para fornecer mais detalhes. Você receberá um aviso antes de ser migrado. Se tiver preocupações relacionadas à migração, entre em contato com nossa equipe de migração em [intunegrps@microsoft.com](intunegrps@microsoft.com).

### O que acontece com meus grupos de usuários e dispositivos existentes?
 Os grupos de usuários e dispositivos que você criou serão migrados para os grupos de segurança do Azure AD. Grupos padrão do Intune, como o grupo Todos os Usuários, serão migrados apenas se você os estiver usando em implantações no momento da migração. A migração pode ser mais complexa para alguns grupos; você será notificado se etapas adicionais forem necessárias para a migração.

### Quais novos recursos estarão disponíveis para mim?
Veja as novas funcionalidades que serão introduzidas:

-    os Grupos de segurança do Azure AD terão suporte do Intune para todos os tipos de implantações.
-    os Grupos de segurança do Azure AD darão suporte ao agrupamento de dispositivos com os usuários.
-    os Grupos de segurança do Azure AD darão suporte a grupos dinâmicos com atributos de dispositivos do Intune. Por exemplo, você poderá agrupar dinamicamente os dispositivos com base na plataforma, como iOS. Dessa forma, quando um novo dispositivo iOS for registrado em sua organização, ele será adicionado automaticamente ao grupo dinâmico de dispositivos iOS.
-    experiências de administração compartilhadas para o gerenciamento de grupos no Azure AD e no Intune.
- a *função de Administrador de serviço do Intune* será adicionada ao Azure AD para permitir que os administradores de serviço do Intune executem tarefas de gerenciamento de grupos no Azure AD.




### Quais funcionalidades do Intune não estarão disponíveis?
Embora a experiência de grupo vá melhorar, algumas funcionalidades do Intune não estarão disponíveis após a migração.

#### Funcionalidade de gerenciamento de grupos

-   Você não poderá excluir membros ou grupos quando criar um novo grupo. No entanto, os grupos dinâmicos do Azure AD permitirão que você use atributos para criar regras avançadas para excluir membros com base em critérios.
-   Não haverá suporte para grupos de **Usuários Desagrupados** e **Dispositivos Desagrupados**. Esses grupos não serão migrados.


#### Funcionalidade dependente de grupo

-   A função de Administrador de serviço não terá permissões para **Gerenciar grupos**.
-   Não será possível agrupar dispositivos do Exchange ActiveSync.  O grupo **Todos os Dispositivos Gerenciados pelo EAS** será convertido de um grupo para um modo de exibição de relatório.
-  A dinamização com grupos em relatórios não estará disponível.
-  O direcionamento de grupos personalizados de regras de notificação não estará disponível.

### O que eu devo fazer para me preparar para essa alteração?
 Temos recomendações que facilitarão essa transição para você:

- limpe quaisquer grupos indesejados ou desnecessários do Intune antes da migração.
- avalie seu uso da exclusão em grupos e considere recriar seus grupos de modo que não precisa usar a exclusão.
-  se você tiver administradores que não têm permissões para criar grupos no Azure AD, peça que o administrador do Azure AD os adicione à função **Administrador de serviço do Intune** do Azure AD.


# Criar grupos para gerenciar usuários e dispositivos com o Microsoft Intune

Esta seção descreve como criar grupos do Intune no console de administração do Intune.

Para criar e gerenciar grupos, use o espaço de trabalho **Grupos** no console de administração do Microsoft Intune. A página **Visão Geral dos Grupos** contém resumos de status que o ajudam a identificar e priorizar problemas que exigem a sua atenção para:

-   Alertas
-   Atualizações de software
-   Endpoint Protection
-   Política
-   Gerenciamento de software

Além disso, sua hierarquia de grupo é exibida com resumos de status para ajudar você a identificar e resolver problemas dos membros de um grupo selecionado.


> [!TIP]
> Quando estiver criando seus grupos, considere como você aplicará a política. Por exemplo, você pode ter políticas específicas para sistemas operacionais do dispositivo e políticas específicas para diferentes funções na sua organização, ou para Unidades organizacionais que você já definiu no Active Directory. Algumas pessoas consideram útil ter grupos de dispositivos específicos para iOS, Android e Windows, bem como grupos de usuários para cada função organizacional.
>
> É possível que você queira criar uma política padrão que se aplica a todos os grupos e dispositivos, para estabelecer os requisitos de conformidade básicos da sua empresa. Depois, crie políticas mais específicas para as categorias mais amplas de usuários e dispositivos, como políticas de email para cada um dos sistemas operacionais de dispositivos.
>
> Preste atenção ao nomear suas políticas para que você possa identificá-las facilmente mais tarde. Por exemplo, um bom nome descritivo para uma política é **Política de email do WP para toda a empresa**.
>
> Sempre que criar uma política restritiva, você desejará comunicá-la aos seus usuários. Sendo assim, depois de criar os grupos e políticas mais gerais, fique atento ao criar os grupos menores para reduzir a comunicação desnecessária.


## Criar um grupo de dispositivos

1.  No console de administração do Intune, escolha **Grupos** &gt; **Visão geral** &gt; **Criar Grupo**.

2.  Forneça um nome e uma descrição opcional para o grupo e selecione um grupo de dispositivos como o grupo pai. Escolha **Avançar**.

3.  Na página **Definir Critérios de Associação** , selecione o tipo de dispositivos que o grupo incluirá. Opções adicionais para configurar o grupo dependem do tipo de dispositivos que serão selecionados:

    -   **Computador:** especifique se deseja incluir todos os membros do grupo pai, as OU (Unidades Organizacionais) e os domínios que deseja incluir ou excluir. As informações de domínio e unidade organizacional de um computador são obtidas do inventário.

    -   **Dispositivos Móveis:** especifique para incluir somente os dispositivos móveis que são gerenciados pelo Intune, pelo Exchange ActiveSync ou por ambos.

    -   **Todos os dispositivos:** essa opção inclui todos os dispositivos sem exceções com base em critérios.

4.  Na página **Definir Associação Direta** , inclua ou exclua os dispositivos individuais especificados clicando em **Procurar**. Se for usada a opção para selecionar os dispositivos que não estão no grupo pai especificado, esses dispositivos serão automaticamente adicionados ao grupo pai.


5.  Na página **Resumo**, examine as ações que serão tomadas. Escolha **Concluir**.

O grupo recém-criado pode ser encontrado na lista **Grupos**, no espaço de trabalho **Grupos**, no grupo pai. Nesse local, também é possível editar ou excluir o grupo.

## Criar um grupo de usuários

1.  No console de administração do Intune, escolha **Grupos** &gt; **Visão geral** &gt; **Criar Grupo**.

2.  Forneça um nome e uma descrição opcional para o grupo e selecione um grupo de usuários como o grupo pai. Escolha **Avançar**.

3.  Na página **Definir Critérios de Associação** , especifique se deseja incluir todos os membros do grupo pai ou começar com um grupo vazio.  Você pode, então, incluir ou excluir membros com base nos **Grupos de segurança** de usuários que foram configurados manualmente no [centro de administração do Office 365](http://go.microsoft.com/fwlink/?LinkId=698854) ou que foram sincronizados no Active Directory local. Se a associação de um grupo de segurança for alterada, a associação de grupos de usuários baseada nesse grupo de segurança também poderá mudar.

    > [!IMPORTANT]
    > No momento, se o seu grupo incluir membros de grupos de segurança ou grupos de gerenciamento específicos, e você também excluir membros de grupos específicos, os membros incluídos inicialmente serão removidos. Para criar um grupo que tenha membros incluídos e excluídos, recomendamos que você primeiro crie um grupo pai com os membros incluídos e, em seguida, crie um grupo filho desse grupo, no qual você lista os membros excluídos. Você pode usar esse grupo filho conforme apropriado para a distribuição de aplicativos, perfis e políticas do Intune.

    > [!NOTE]
    > No Portal de Gerenciamento do Azure, você pode criar um grupo com base no gerenciador ao qual os usuários estão subordinados. O grupo será dinâmico, mudando conforme os funcionários são adicionados ou removidos da equipe do gerente no Active Directory do Azure. O procedimento para criar um grupo do Azure baseado em um gerente é descrito em [Usar atributos para criar regras avançadas](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) na seção chamada **Para configurar um grupo como grupo de "Gerente"**.


4.  Na página **Definir Associação Direta** , inclua ou exclua os usuários individuais especificados clicando em **Procurar**. Se for usada a opção para selecionar os usuários que não estão no grupo pai especificado, esses dispositivos serão automaticamente adicionados ao grupo pai. Na parte inferior da caixa de diálogo **Selecionar membros**, você encontrará a opção de adicionar um usuário manualmente. Isso é útil se você quiser adicionar um usuário que ainda não tem um dispositivo registrado.


5.  Na página **Resumo**, examine as ações que serão tomadas. Escolha **Concluir**.

O grupo recém-criado pode ser encontrado na lista **Grupos**, no espaço de trabalho **Grupos**, no grupo pai. Nesse local, também é possível editar ou excluir o grupo.

> [!TIP]
> Grupos de segurança são um ótimo recurso para preencher grupos de usuários. Como os grupos de segurança definem quem tem acesso a quais recursos, eles podem ser bem traduzidos em grupos de usuários do Intune. Os grupos de segurança que são sincronizados do Active Directory para o Azure Active Directory, ou criados diretamente no Azure Active Directory por meio do centro de administração do Office 365 ou do portal de administração do Azure, estão disponíveis para a criação de grupos de usuários no Intune.

## Personalizar exibições para funções administrativas
As exibições de grupo filtrado permitem que você personalize o que os administradores de exibição podem ver com base em suas funções e restringir quais grupos cada administrador de TI pode gerenciar. Isso pode ser útil quando:

-   Seus administradores de TI só devem ser capazes de implantar itens a dispositivos e usuários específicos.

-   Para exibir apenas os grupos relevantes para cada administrador de TI.

Você pode configurar as exibições de grupo filtrado para administradores de serviço no console do administrador do Intune. Para detalhes, confira [What to know before you start Microsoft Intune](/intune/get-started/what-to-know-before-you-start-microsoft-intune) (O que saber antes de iniciar o Microsoft Intune).

Após configurar a exibição de grupo filtrado para um administrador de serviços, esse administrador:

-   Poderá ver e selecione apenas os grupos que você especificou ao implantar softwares e políticas ou usar relatórios

-   Não receberá informações de status nas seguintes páginas do console de administração:

    -   **Visão geral do sistema**

    -   **Visão geral de grupos**

    -   **Visão geral do Endpoint Protection**

    -   **Visão geral de alertas**

    -   **Visão geral de softwares**

    -   **Visão Geral de Políticas**

### Configurar os modos de exibição de grupo filtrado

1.  No console de administração do Intune, escolha **Admin** &gt; **Gerenciamento de Administradores** &gt; **Administradores de Serviço**.

2.  Selecione o administrador de serviços para o qual você deseja filtrar grupos e clique em **Gerenciar grupos**.

3.  Na caixa de diálogo **Selecionar os grupos que serão visíveis para esse administrador de serviços** , adicione os grupos selecionados que o administrador de serviços poderá acessar e clique em **OK**.

Depois de configurar os modos de exibição do grupo filtrado, o administrador de TI será capaz de ver e selecionar apenas os grupos que você selecionou.

## Gerenciar seus grupos
Depois de criar os grupos, você continuará a gerenciá-los de acordo com as necessidades da sua organização.

Você pode editar o grupo para alterar seu nome e descrição e quem pertence ao grupo.

Você pode excluir um grupo que não atenda às necessidades da sua organização. Excluir um grupo não exclui os usuários que pertencem a esse grupo.

## Próximas etapas

### Verificar o design
Depois de configurar seus grupos e políticas, verifique as implicações práticas do seu design, examinando o **Valor pretendido** e o **Status**.

1. Selecione qualquer dispositivo de um grupo de dispositivos e percorra as categorias de informações na parte superior da tela.
2. Selecione **Política** . Você verá algo parecido com esta captura de tela das configurações de política de dispositivo do Android.

![Política de exemplo de configurações do iOS](../media/Intune-Device-Policy-v.2.jpg)

Cada política tem um **Valor Pretendido** e um **Status**. O valor pretendido é o que você quis realizar ao atribuir a política. O status é o que você, de fato, realizou quando todas as politicas que se aplicam ao dispositivo, bem como as restrições e requisitos de hardware e de sistema operacional, são consideradas em conjunto.  Na captura de tela, você pode ver dois exemplos claros:

-   **Permitir senhas simples** é definido como **Sim**, conforme mostrado na coluna **Valor Pretendido** , mas o **Status** é **Não aplicável**. Isso ocorre porque senhas simples não têm suporte para dispositivos Android.

-   Da mesma forma, o item de política expandido **Configurações de email para dispositivos iOS** não é aplicado a esse dispositivo porque se trata de um dispositivo Android.

> [!NOTE]
> Lembre-se de que, quando duas políticas com diferentes níveis de restrição aplicam-se ao mesmo dispositivo ou usuário, a política mais restritiva se aplica na prática.



<!--HONumber=Aug16_HO3-->


