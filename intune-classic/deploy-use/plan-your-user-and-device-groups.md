---
title: Planejar seus grupos de dispositivos e usuários
description: Planeje grupos para atender às necessidades da organização.
keywords: ''
author: sanchusa
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 679399f306f3837a010cc01799c7567c1e5b5b39
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31025307"
---
# <a name="plan-your-user-and-device-groups"></a>Planejar seus grupos de dispositivos e usuários

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Os grupos no Intune oferecem grande flexibilidade quando você está gerenciando dispositivos e usuários. Você pode configurar grupos para atender às suas necessidades organizacionais de acordo com:

- localização geográfica
- department
- características de hardware
- sistema operacional
- se o dispositivo é de propriedade do usuário ou da empresa


## <a name="how-intune-groups-work"></a>Como funcionam os grupos do Intune


Esta é a exibição padrão do nó **Grupos** no console de administrador do Intune:

![Captura de tela da exibição padrão do nó Grupos no console do Intune](../media/Intune_Planning_Groups_Default_small.png)

As políticas são implantadas em grupos, de modo que a hierarquia de grupo é uma das suas principais considerações de design. É importante saber que você não pode alterar o grupo pai de um grupo depois de ter criado o grupo. A forma como você projeta seus grupos é extremamente importante desde o momento em que começa a usar o serviço Intune. Algumas das práticas recomendadas para a criação de uma hierarquia de grupo com base em suas necessidades organizacionais são descritas aqui.

## <a name="group-membership-rules"></a>Regras de associação de grupo

- Um grupo pode conter usuários ou dispositivos, mas não ambos.

    * **Grupos de dispositivos**. Inclui computadores e dispositivos móveis. Antes de adicionar um computador a um grupo, é preciso registrá-lo. Antes de adicionar um dispositivo móvel a um grupo, o ambiente deve ser configurado para dar suporte a dispositivos móveis, e os dispositivos devem ser registrados ou descobertos no Exchange ActiveSync.

    * **Grupos de usuários**. Um grupo pode ter usuários de grupos de segurança. Sincronização de grupos de segurança com sua instância do Active Directory. Se não sincronizar com o Active Directory, você poderá criar esses grupos manualmente.

- Um dispositivo ou um usuário pode pertencer a mais de um grupo.

- Um grupo pode incluir e excluir membros com base nas seguintes regras de associação:

    * **Critérios de Associação**. Essas são regras dinâmicas que o Intune executa para incluir ou excluir membros. Esses critérios usam grupos de segurança e outras informações sincronizadas com sua instância local do Active Directory. Quando os dados ou o grupo de segurança mudam, a associação ao grupo muda quando você sincroniza com o Active Directory.

    * **Associação Direta**. Essas são regras estáticas que agregam ou excluem membros explicitamente. A lista de membros é estática.

-   Os AD DS (Serviços de Domínio do Active Directory) não são necessários quando você cria grupos de usuários ou grupos de dispositivos que incluem usuários ou computadores. Mas, para que os grupos de dispositivos incluam dispositivos móveis, seu ambiente deve ser configurado para dar suporte a dispositivos móveis.

    Além disso, os dispositivos devem ser descobertos e adicionados ao Intune.

## <a name="group-relationship-rules"></a>Regras de relação de grupo

- Cada grupo criado deve ter um grupo pai. Você não pode alterar o grupo pai de um grupo depois de ter criado o grupo.

- Ao adicionar usuários ou dispositivos a um grupo filho:

    * O grupo filho sempre é um subconjunto do grupo pai.

    * Novos membros adicionados a um grupo filho serão adicionados automaticamente ao seu respectivo grupo pai.

    * Não é possível adicionar um membro a um grupo filho, quando esse membro tiver sido excluído do grupo pai.

- A associação de um grupo pai define a disponibilidade de associação ao grupo filho.

- Quando você excluir um grupo pai, todos os grupos filho serão excluídos.

- É possível implantar o conteúdo e as políticas para um grupo pai e excluir a implantação em grupos filho.

- Você poderá adicionar um usuário ou dispositivo específico a um grupo filho se o usuário ou dispositivo já não for membro do grupo pai. Se você fizer isso, o novo membro do grupo filho será adicionado ao grupo pai.

    No entanto, não será possível adicionar um membro a um grupo filho se o membro for excluído do grupo pai.

- A associação ao grupo é recursiva. Por exemplo:

    * **Pat** é um membro de apenas um grupo, o grupo de segurança **Usuários de Laptop** .

    * O grupo **Usuários de Laptop** é um membro do grupo de segurança **Usuários Aprovados** .

    * Você cria um grupo no Intune que usa uma consulta de associação dinâmica que inclui os membros do grupo **Usuários Aprovados**. O resultado disso é que o seu grupo de usuários do Intune incluirá **Pat**.

> [!TIP]
> Quando criar grupos, reflita sobre como você aplicará políticas. Por exemplo, você pode ter políticas específicas para sistemas operacionais do dispositivo ou políticas específicas para diferentes funções ou unidades organizacionais que você já definiu no serviço do Active Directory. Alguns administradores consideram útil criar grupos de dispositivos específicos para iOS, Android e Windows. Isso vai além da criação de grupos de usuários para cada função organizacional.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your organization. Then, you create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful when you name your policies, so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy, you'll want to communicate it to your users. After you create the more general groups and policies, pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## <a name="built-in-groups"></a>Grupos internos
O Intune tem nove grupos internos que não podem ser editados nem excluídos: <!--maybe a screen shot would be best?-->

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
> Seu lema deve ser: *manter as coisas simples*. Se sua organização não tiver necessidades específicas como as descritas a seguir, mantenha a simplicidade e use a estrutura de grupo e políticas padrão. Isso tornará o serviço mais gerenciável no longo prazo. A manutenção será mais fácil se você puder tratar seus usuários uniformemente. Com pouca diferenciação por grupo, você terá menos políticas para manter.


### <a name="all-users-and-devices-in-your-organization"></a>Todos os usuários e dispositivos na sua organização
Defina um grupo pai para todos os usuários e dispositivos na sua organização. É provável que você tenha políticas que se aplicam a todos. Você pode usar os grupos padrão do Intune **Todos os Usuários** e **Todos os Dispositivos** para esta finalidade. Subgrupos que organizam os dispositivos por informações específicas, como o grupo de BYOD (traga seu próprio dispositivo) e o de dispositivos CO (corporativos), podem ser grupos filho dos grupos pai **Todos os Usuários** e **Todos os Dispositivos**.

## <a name="customize-groups-for-your-organization"></a>Personalizar grupos para sua organização

### <a name="byod-and-corporate-owned-devices"></a>Dispositivos de propriedade corporativa e BYOD
Se a sua organização permite que os funcionários usem os próprios dispositivos, fornece dispositivos da empresa ou trabalha com uma combinação de ambos, recomenda-se que você aplique políticas distintas a essas duas categorias de dispositivos.

No caso de BYOD ou uma mistura de ambos, tenha cuidado em planejar políticas que não venham a infringir os regulamentos de privacidade locais. Crie um grupo pai para todos os usuários que levarão seus próprios dispositivos. Você pode usar esse grupo para aplicar políticas que se aplicam a todos os usuários nesta categoria.

![Criar um grupo pai de BYOD](../media/Intune_Planning_Groups_BYOD_small.png)

Da mesma forma, você pode criar um grupo para usuários de dispositivos CO em sua organização:

![Grupos de usuário irmãos para dispositivos BYOD e CO](../media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### <a name="groups-for-geographic-regions"></a>Grupos para regiões geográficas
Se sua organização precisar de políticas para regiões específicas, você poderá criar grupos com base na região geográfica. Você pode baseá-los em grupos regionais que já tenha sido criados em sua instância do Active Directory e sincronizá-los com o serviço do Azure Active Directory. Você também pode criar grupos regionais diretamente no Azure Active Directory.

As próximas capturas de tela mostram como criar grupos do Intune com base em grupos sincronizados com sua instância local do Active Directory. Esses exemplos pressupõem que você tenha um grupo de segurança do AD chamado **Grupo de Usuários dos EUA**.

Primeiro, forneça as informações gerais.

![Captura de tela da área Editar Grupo](../media/Intune_Planning_Groups_AD_General_small.png)

Em **Critérios de Associação**, selecione o **Grupo de Usuários dos EUA**, sincronizado com o Active Directory, como o grupo de segurança a ser usado nas regras de associação.

![Captura de tela da caixa de diálogo Editar Grupo](../media/Intune_Planning_Groups_AD_Criteria_small.png)

Examine suas entradas e escolha **Concluir** para criar o grupo.

![Captura de tela da caixa de diálogo Editar Grupo](../media/Intune_Planning_Groups_AD_Summary_small.png)

Em nosso exemplo, também criamos um grupo chamado **MEA** para o Oriente Médio e a Ásia.

> [!NOTE]
> Se a associação de grupo não for preenchida com base nas associações de grupo de segurança, verifique se você atribuiu licenças do Intune aos membros do grupo.

### <a name="groups-for-specific-hardware"></a>Grupos de hardware específico
Se sua organização exigir políticas que se aplicam a tipos específicos de hardware, você poderá criar grupos com base nesse critério. Você pode basear as políticas em grupos específicos já criados em sua instância local do Active Directory e sincronizá-los com o serviço do Azure Active Directory. Você também pode criar grupos diretamente no Azure Active Directory. Neste exemplo, usamos o **Grupo de Usuários dos EUA** como o grupo pai para o grupo **Usuários de Laptop**.

![Caixa de diálogo Selecionar Grupo de Segurança](../media/Intune_Planning_Groups_Laptop_small.png)

Neste ponto, a hierarquia do grupo deve ser semelhante à seguinte captura de tela. Como você pode ver, agora existem membros no grupo **Usuários de Laptop** do Intune. Todas as políticas aplicadas a esse grupo serão aplicadas a usuários de laptop BYOD da região dos EUA.

![Exibição do grupo de Usuários de Laptop](../media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### <a name="groups-for-specific-operating-systems"></a>Grupos para sistemas operacionais específicos
Se sua organização exigir políticas aplicáveis a sistemas operacionais específicos, como Android, iOS ou Windows, você poderá criar grupos com base nessa exigência. Assim como em exemplos anteriores, você pode baseá-las em grupos específicos já criados em sua instância local do Active Directory e sincronizá-los com o serviço do Azure Active Directory. Você também pode criá-las diretamente na sua instância do Azure Active Directory.

Usando o mesmo método dos exemplos anteriores, você pode criar grupos com base em usuários <!--devices?--> que usam plataformas de sistema operacional específicas.

> [!NOTE]
> Se você tiver usuários que usam vários sistemas operacionais/plataformas móveis e não tiver uma forma automatizada para categorizar os usuários como usuários Android, iOS ou Windows, considere a aplicação de políticas no nível do dispositivo. Isso lhe dará mais flexibilidade para aplicar políticas específicas a um sistema operacional.
>
> Você não pode provisionar grupos dinamicamente com base no sistema operacional do dispositivo. Em vez disso, use grupos de segurança do Active Directory ou do Azure Active Directory.

![Grupo de Usuários de Laptop](../media/Intune_Planning_Groups_OS_Hierachy_small.png)

Depois que todos os seus grupos de usuários forem preenchidos com base nesses requisitos organizacionais, sua hierarquia de grupo deve ter esta aparência:

![Exibição de hierarquia de grupos](../media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

Você pode usar essa hierarquia para aplicar as políticas da organização.

### <a name="device-groups"></a>Grupos de dispositivos
Você também pode criar grupos semelhantes para dispositivos conforme mostrado abaixo, começando com um amplo grupo que inclui todos os dispositivos dos funcionários para o cenário de BYOD.

![Caixa de diálogo Criar Grupo](../media/Intune_Planning_Groups_Device_General_small.png)

Verifique se você selecionou **Todos os dispositivos (computadores e dispositivos móveis)** para que o grupo inclua todos os dispositivos BYO:

![Página Definir critérios de associação](../media/Intune_Planning_Groups_Device_Criteria_small.png)

Examine suas entradas e escolha **Concluir** para criar o grupo de BYOD.

![Caixa de diálogo Criar Grupo](../media/Intune_Planning_Groups_Device_Summary_small.png)

Continue a criar grupos de dispositivos, até que você tenha uma hierarquia de grupos de dispositivos semelhante à hierarquia de grupos dos usuários. Seu nó de grupo no console do Intune será semelhante a este:

![Exibição de hierarquia de grupos do Intune](../media/Intune_Groups_Hierarchy_Final_Small.png)

## <a name="group-hierarchies-and-naming-conventions"></a>Convenções de nomenclatura e hierarquias de grupo
Para facilitar o gerenciamento de políticas, é recomendável nomear cada política de acordo com a finalidade, a plataforma e o escopo ao qual ela é aplicada. Use um padrão de nomenclatura que siga a estrutura de grupos que você criou quando se preparou para aplicar as políticas.

Por exemplo, para uma política do Android que é aplicada a todos os dispositivos corporativos, Android e dispositivos móveis no nível regional dos EUA, a política pode ser nomeada como **CO_US_Mob_Android_General**.

![Criar política para Android](../media/Intune_planning_policy_android_small.png)

Ao nomear as políticas dessa forma, você poderá identificar rapidamente as políticas e seu uso pretendido, bem como o escopo do nó **Políticas** do console, da seguinte forma:

![Lista de política do Intune](../media/Intune_planning_policy_view_small.png)

## <a name="next-steps"></a>Próximas etapas
[Criar grupos](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)
