---
title: Migrando para grupos do Azure Active Directory | Microsoft Docs
description: "Como os grupos serão migrados do Intune para o Azure AD"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 12/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
translationtype: Human Translation
ms.sourcegitcommit: dd4c8f1d810338912b4926be8419ccf9a52ae722
ms.openlocfilehash: 8d3900da91c89700b97d8774f893d82d3a74ea83


---

# <a name="a-new-way-of-using-groups-in-intune"></a>Uma nova maneira de usar grupos no Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Já ouvimos seus comentários e estamos fazendo algumas alterações no modo de trabalho com grupos no Microsoft Intune.
Estamos migrando todos os grupos do Intune de nossos clientes para grupos de segurança do Azure Active Directory.

A vantagem é que você usará a mesma experiência de grupos em todos os seus aplicativos do Enterprise Mobility + Security e Azure AD. Além disso, você poderá usar o PowerShell e a API do Graph para estender e personalizar essa nova funcionalidade.

Os grupos de segurança do Azure AD dão suporte a todos os tipos de implantações do Intune em usuários e dispositivos. Além disso, é possível usar os grupos dinâmicos do Azure AD que são atualizados automaticamente de acordo com os atributos fornecidos. Por exemplo, você poderá criar um grupo de dispositivos que executa o iOS 9. Sempre que um novo dispositivo que executa o iOS 9 for registrado, ele será adicionado ao grupo dinâmico automaticamente.

## <a name="when-is-this-happening"></a>Quando isso acontecerá?

Atualmente, o processo de migração está em andamento. Você será notificado antes da migração.
Caso já tenha sido migrado, você verá uma mensagem semelhante à seguinte quando tentar acessar os grupos no console do Intune clássico:

![Mensagem para mostrar que os grupos foram migrados.](http://i.imgur.com/72KRaXj.png)

## <a name="what-wont-be-available"></a>O que não estará disponível?

Algumas funcionalidades existentes dos grupos do Intune não estão disponíveis no Azure AD:

- Os grupos **Usuários Desagrupados** e **Dispositivos Desagrupados** do Intune não serão migrados.
- A opção para **Excluir membros específicos** de um grupo atualmente existente no console do Intune não existe no Portal do Azure. No entanto, você poderá usar um grupo de segurança do Azure AD com regras avançadas para replicar esse comportamento. Por exemplo, é possível criar uma regra avançada que inclui todas as pessoas de seu departamento de Vendas em um grupo de segurança, mas não aquelas que têm a palavra “Assistente” no cargo, usando essa regra avançada: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- O grupo **Todos os Dispositivos Gerenciados pelo Exchange ActiveSync** interno do console do Intune não será migrado para o Azure AD. No entanto, você ainda poderá acessar informações sobre dispositivos gerenciados pelo EAS no Portal do Azure.
- Não será possível filtrar relatórios por grupos no console do Intune clássico.
<!--- - Custom group targeting of notification rules will not be available. ROB I took this out as I couldn't replicate the behavior. --->

## <a name="how-to-get-ready"></a>Como se preparar

- Leia os seguintes tópicos sobre o Azure AD para saber mais sobre os grupos de segurança do Azure AD e como eles funcionam:
    -  [Gerenciando o acesso a recursos com grupos do Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
    -  [Gerenciando grupos no Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Usando atributos para criar regras avançadas](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
- Considere a remoção de todos os grupos do Intune que não são mais usados antes da migração.
-  Garanta que todos os administradores que precisam criar grupos são adicionados à função **Administrador de Serviços do Intune** do Azure AD. Observe que a função Administrador de Serviços do Azure AD não tem permissões **Gerenciar Grupo**.
-  Se você usar grupos com a opção **Excluir membros específicos**, considere se é possível recriar esses grupos para que eles não precisem de exclusões ou se é possível usar regras avançadas na consulta do Azure AD para obter o mesmo resultado.


## <a name="what-happens-to-intune-groups"></a>O que acontece com os grupos do Intune?

| Grupos no Intune|Grupo no Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Grupo de usuários estático|Grupo de segurança estático do Azure AD|
|Grupo de usuários dinâmico|Grupos de segurança estáticos do Azure AD com uma hierarquia de grupos de segurança do Azure AD|
|Grupo de dispositivos estático|Grupo de segurança estático do Azure AD|
|Grupo de dispositivos dinâmico|Grupo de segurança dinâmico do Azure AD|
|Um grupo com uma condição de inclusão|Grupo de segurança estático do Azure AD que contém membros estáticos ou dinâmicos da condição de inclusão no Intune.|
|Um grupo com uma condição de exclusão|Não migrado|
|Os grupos internos **Todos os Usuários**, **Usuários Desagrupados**, **Todos os Dispositivos**, **Dispositivos Desagrupados**, **Todos os Computadores**, **Todos os Dispositivos Móveis**, **Todos os dispositivos gerenciados por MDM** e **Todos os dispositivos gerenciados pelo EAS**|Grupos de segurança do Azure AD.|

No Intune, todos os grupos precisam ter um grupo pai. Os grupos podem conter apenas membros do grupo pai. No Azure AD, os grupos filhos podem conter membros que o grupo pai não tem.

Os atributos são propriedades do dispositivo que podem ser usados na definição de grupos. Esta tabela descreve como esses critérios serão migrados para grupos de segurança do Azure AD.

| Atributo no Intune|Atributo no Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Atributo de Unidade Organizacional (OU) para grupos de dispositivos|Atributo OU para grupos dinâmicos.|
|Atributo de nome de domínio para grupos de dispositivos|Atributo de Nome de domínio para grupos dinâmicos.|
|Grupo de segurança como um atributo para grupos de usuários|Grupos não podem ser atributos em consultas dinâmicas do Azure AD. Grupos dinâmicos podem conter somente atributos específicos de dispositivo ou de usuário.|
|Atributo de gerente para grupos de usuários|Regra avançada para atributo de *gerente* em grupos dinâmicos|
|Todos os usuários do grupo de usuário pai|Grupo estático com aquele grupo como membro|
|Todos os dispositivos móveis do grupo de dispositivo pai|Grupo estático com aquele grupo como membro|
|Todos os dispositivos móveis gerenciados pelo Intune|Atributo do Tipo de Gerenciamento com 'MDM' como valor para grupo dinâmico|
|Grupos aninhados dentro de grupos estáticos |Grupos aninhados dentro de grupos estáticos|
|Grupos aninhados dentro de grupos dinâmicos|Grupo dinâmico com um nível de aninhamento|

## <a name="what-happens-to-policies-and-apps-youve-already-deployed"></a>O que acontece com as políticas e os aplicativos que você já implantou?

As políticas e os aplicativos continuam sendo implantados em grupos, exatamente como antes. No entanto, agora você gerenciará esses grupos no Portal do Azure, em vez de no console do Intune clássico.


## <a name="how-to-get-more-information"></a>Como obter mais informações

Contate nossa equipe de migração pelo email [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).  
     




<!--HONumber=Dec16_HO4-->


