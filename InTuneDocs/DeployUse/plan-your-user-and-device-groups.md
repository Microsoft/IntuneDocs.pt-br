---
title: "Planejar seus grupos de dispositivos e de usuários | Microsoft Intune"
description: 
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 82ab2dbfada6c0745195da149d5f0dc1948ceb92
ms.openlocfilehash: e89d8384532b994d810649fc07c698237e2f3cec


---

# Planejar seus grupos de dispositivos e usuários
Os grupos no Intune oferecem uma grande flexibilidade para o gerenciamento de seus dispositivos e usuários. Você pode configurar grupos para atender às suas necessidades organizacionais de acordo com:

- localização geográfica
- department
- características de hardware
- sistema operacional
- se o dispositivo é de propriedade do usuário ou da empresa


## Como funcionam os grupos do Intune


A exibição padrão do nó Grupos no console de administrador do Intune é:

![Captura de tela da exibição padrão do nó Grupos no console do Intune](/intune/media/Intune_Planning_Groups_Default_small.png)

As políticas são implantadas em grupos, de modo que a hierarquia de grupo é uma das suas principais considerações de design. Também é importante saber que o grupo pai desse grupo não pode ser alterado depois que o grupo é criado, portanto, o design de seus grupos é extremamente importante desde o momento em que você começa a usar o serviço do Intune. Algumas das práticas recomendadas para a criação de uma hierarquia de grupo com base em suas necessidades organizacionais são descritas aqui.

## Regras de associação de grupo

1. Um grupo pode conter usuários ou dispositivos, mas não ambos.

    * **Grupos de dispositivos:** isso inclui computadores e dispositivos móveis. Antes de adicionar um computador a um grupo, é preciso registrá-lo. Antes de adicionar um dispositivo móvel a um grupo, o ambiente deve ser configurado para dar suporte a dispositivos móveis e os dispositivos devem ser registrados ou descobertos a partir do Exchange ActiveSync.

    * **Grupos de usuários:** um grupo pode conter usuários de grupos de segurança, que são sincronizados a partir de seu Active Directory. Se você não usar a sincronização do Active Directory, é possível criar esses grupos manualmente.

2. Um dispositivo ou um usuário pode pertencer a mais de um grupo.

3. Um grupo pode incluir e excluir membros com base nas seguintes regras de associação:

    * **Critérios de Associação:** essas são regras dinâmicas que o Intune executa para incluir ou excluir membros. Esses critérios usam **grupos de segurança** e outras informações sincronizadas no seu AD (Active Directory) local. Quando os dados ou o grupo de segurança mudam, a associação ao grupo muda quando você sincroniza com o AD.

    * **Associação Direta:** essas são regras estáticas que agregam ou excluem membros explicitamente. A lista de membros é estática.

4. Os Serviços de Domínio Active Directory (AD DS) não são necessários para criar grupos de usuários ou grupos de dispositivos que incluam usuários ou computadores. Entretanto, para que os grupos de dispositivos incluam dispositivos móveis, o ambiente tem que estar configurado para dar suporte a dispositivos móveis.

    Além disso, os dispositivos devem ser descobertos e adicionados ao Intune.

## Regras de relação de grupo

1. Cada grupo criado deve ter um grupo pai e não é possível alterá-lo depois de criado.

2. Ao adicionar usuários ou dispositivos a um grupo filho:

    * Grupos filho sempre são subconjuntos do grupo pai.

    * Novos membros adicionados a um grupo filho serão adicionados automaticamente ao seu respectivo grupo pai.

    * Não é possível adicionar um membro a um grupo filho, quando esse membro tiver sido excluído do grupo pai.

3. A associação de um grupo pai define a disponibilidade de associação ao grupo filho.

4. Quando você excluir um grupo pai, todos os grupos filho serão excluídos.

5. É possível implantar o conteúdo e as políticas para um grupo pai e excluir a implantação para grupos filho.

6. Você pode adicionar um usuário ou dispositivo específico a um grupo filho que não seja membro do grupo pai. Se você fizer isso, o novo membro do grupo será adicionado ao grupo pai.

    No entanto, não é possível adicionar um membro a um grupo filho excluído do grupo pai.

7. A associação ao grupo é recursiva. Por exemplo:

    * **Pat** é um membro de apenas um grupo, o grupo de segurança **Usuários de Laptop** .

    * O grupo **Usuários de Laptop** é um membro do grupo de segurança **Usuários Aprovados** .

    * Você cria um grupo no Intune que usa uma consulta de associação dinâmica que inclui os membros do grupo **Usuários Aprovados**. O resultado disso é que o seu grupo de usuários do Intune incluirá **Pat**.

> [!TIP]
> Quando estiver criando seus grupos, reflita como você aplicará a política. Por exemplo, você pode ter políticas específicas para sistemas operacionais do dispositivo e políticas específicas para diferentes funções na sua organização, ou para Unidades organizacionais que você já definiu no Active Directory. Algumas pessoas consideram útil ter grupos de dispositivos específicos para iOS, Android e Windows, bem como grupos de usuários para cada função organizacional.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your company. Then create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful naming your policies so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy you'll want to communicate it to your users, so after you create the more general groups and policies pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## Grupos internos
O Intune fornece nove grupos internos que não podem ser editados nem excluídos: <!--maybe a screen shot would be best?-->

-   **Todos os Usuários**
    -   Usuários Desagrupados
-   **Todos os Dispositivos**
    -   Todos os Computadores
    -   Todos os dispositivos móveis
        -   Todos os dispositivos gerenciados diretos
        -   Todos os dispositivos gerenciados do Exchange ActiveSync
    -   Todos os dispositivos corporativos
    -   Dispositivos Desagrupados

> [!NOTE]
> Seu lema deve ser: *manter as coisas simples*. Se sua organização não tem necessidades específicas como as descritas a seguir, mantenha a simplicidade e use a estrutura de grupo e políticas padrão para tornar o serviço mais gerenciável a longo prazo. A manutenção será mais fácil se for possível tratar os usuários igualmente com pouca diferenciação por grupo, mantendo, assim, menos políticas.


### Todos os usuários e dispositivos na sua organização
Defina um grupo pai para todos os usuários e dispositivos na sua organização, pois, provavelmente, você tem políticas que se aplicam a todos. Você pode usar os grupos **Todos os usuários** e **Todos os dispositivos** padrão no Intune para esta finalidade. Subgrupos que organizam os dispositivos por informações específicas, como um grupo de traga seu próprio dispositivo (BYOD) e outra para dispositivos corporativos (CO), podem ser filhos dos grupos pai **Todos os Usuários** e **Todos os dispositivos**.

## Personalizando grupos da sua organização

### Dispositivos de propriedade corporativa e BYOD
Se sua organização permitir que os funcionários usem seus próprios dispositivos no trabalho (BYOD), fornecer dispositivos da empresa (CO) ou uma combinação de ambos, será recomendável que você aplique políticas com base nessas duas categorias de dispositivos.

No caso de BYOD ou uma mistura de ambos, tenha cuidado em planejar políticas que não venham a infringir os regulamentos de privacidade locais. Crie um grupo pai para todos os usuários que levarão seus próprios dispositivos. Esse grupo pode ser usado para aplicar políticas que se aplicam a todos os usuários nesta categoria.

![Captura de tela da criação de um grupo pai BYOD](/intune/media/Intune_Planning_Groups_BYOD_small.png)

Da mesma forma, você pode criar um grupo para usuários CO em sua organização:

![Captura de tela de grupos de usuário irmãos para a BYOD e CO](/intune/media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### Grupos para regiões geográficas
Se sua organização precisar de políticas para regiões específicas, você poderá criar grupos com base na região geográfica. Você pode baseá-los em grupos regionais que já podem ter sido criados no AD (Active Directory) e sincronizá-los com o Azure AD. Você também pode criá-los diretamente no Azure AD.

Essas capturas de tela mostram como criar grupos do Intune com base em grupos sincronizados do seu AD local. Este exemplo pressupõe que você tem um grupo de segurança do AD chamado **Grupo de usuários dos EUA**.

1. Primeiro, forneça as informações gerais.

![Captura de tela da área Editar Grupo](/intune/media/Intune_Planning_Groups_AD_General_small.png)

Em Critérios de associação, selecione **Grupo de Usuários dos EUA**, sincronizado do AD, como o grupo de segurança para usar em Regras de associação.

![Caixa de diálogo Editar grupo](/intune/media/Intune_Planning_Groups_AD_Criteria_small.png)

Examine e escolha **Concluir** para concluir a criação do grupo.

![Caixa de diálogo Editar grupo](/intune/media/Intune_Planning_Groups_AD_Summary_small.png)

Em nosso exemplo, também criamos um grupo Oriente Médio e Ásia, MEA.

> [!NOTE]
> Se a associação de grupo não for preenchida com base nas associações de grupo de segurança, verifique se você atribuiu licenças do Intune aos membros.

### Grupos de hardware específico
Se sua organização exigir políticas que se aplicam a tipos específicos de hardware, você poderá criar grupos com base nesse critério. Você pode baseá-los em grupos específicos já criados no seu AD local e sincronizá-los com o Azure AD. Você também pode criá-los diretamente no Azure AD. Neste exemplo, usamos o **Grupo de usuários dos EUA** como o pai para o grupo **Usuários de laptop**.

![Caixa de diálogo Selecionar grupo de segurança](/intune/media/Intune_Planning_Groups_Laptop_small.png)

Neste ponto, a hierarquia de grupos deve aparecer como mostrado abaixo. Como você pode ver, agora existem membros no grupo **Usuários de Laptop** do Intune. Todas as políticas aplicadas a esse grupo agora serão aplicadas a usuários de laptop BYOD da região dos EUA.

![Exibição do grupo de Usuários de Laptop](/intune/media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### Grupos para sistemas operacionais específicos
Se sua organização exigir políticas aplicáveis a sistemas operacionais específicos, como Android, iOS ou Windows, você poderá criar grupos com base nessa exigência. Como nos exemplos anteriores, você pode baseá-los em grupos específicos de sistemas operacionais já criados no seu AD local e sincronizá-los com o Azure AD. Você também pode criá-los diretamente no Azure AD.

Seguindo o mesmo método dos exemplos anteriores, podemos criar grupos com base em usuários <!--devices?--> usando plataformas especificas de sistema operacional.

> [!NOTE]
> Se você tiver usuários que usam vários sistemas operacionais/plataformas móveis e não tiver uma forma automatizada para categorizar os usuários como usuários Android, iOS ou Windows, considere a aplicação de políticas no nível do dispositivo, o que lhe dará mais flexibilidade na aplicação de políticas específicas do sistema operacional.
>
> Você não pode provisionar grupos dinamicamente com base no sistema operacional do dispositivo. Faça isso usando os grupos de segurança do AAD ou do AD.

![Exibição do grupo de usuários de laptop](/intune/media/Intune_Planning_Groups_OS_Hierachy_small.png)

Depois que todos os seus grupos de usuários forem preenchidos com base nesses requisitos organizacionais, sua hierarquia de grupo deve ter esta aparência:

![Exibição de hierarquia de grupos](/intune/media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

Essa hierarquia pode ser usada para aplicar as políticas da organização adequadamente.

### Grupos de dispositivos
Você também pode criar grupos semelhantes para dispositivos conforme mostrado abaixo, começando com um amplo grupo que inclui todos os dispositivos dos funcionários para o cenário BYOD:

![Caixa de diálogo Criar Grupo](/intune/media/Intune_Planning_Groups_Device_General_small.png)

Verifique se você selecionou **Todos os dispositivos (computadores e dispositivos móveis)** para que o grupo inclua todos os dispositivos BYO:

![Página Definir critérios de associação](/intune/media/Intune_Planning_Groups_Device_Criteria_small.png)

Examine e clique em **Concluir** para criar o grupo BYOD.

![Caixa de diálogo criar grupo](/intune/media/Intune_Planning_Groups_Device_Summary_small.png)

Continue a criar grupos de dispositivos, até que você tenha uma hierarquia de grupos de dispositivos semelhante à hierarquia de grupos dos usuários. Então, seu nó de grupo no console do Intune deve ser semelhante a este:

![Exibição de hierarquia de grupos do Intune](/intune/media/Intune_Groups_Hierarchy_Final_Small.png)

## Convenções de nomenclatura e hierarquias de grupo
Para facilitar o gerenciamento de políticas, é recomendável nomear cada política de acordo com a finalidade, plataforma e escopo ao qual ela é aplicada. Esse padrão de nomenclatura deve seguir a estrutura do grupo que você criou na preparação para aplicar as políticas.

Por exemplo, para uma política do Android que é aplicada a todos os dispositivos corporativos, Android e dispositivos móveis no nível regional dos EUA, a política pode ser nomeada como **CO_US_Mob_Android_General**.

![Criar política para Android](/intune/media/Intune_planning_policy_android_small.png)

Ao nomear as políticas dessa forma, você poderá identificar rapidamente as políticas e seu uso pretendido, bem como o escopo do nó de políticas do console, conforme mostrado:

![Lista de política do Intune](/intune/media/Intune_planning_policy_view_small.png)

## Próximas etapas
[Criar grupos](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


