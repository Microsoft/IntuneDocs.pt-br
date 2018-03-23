---
title: Grupos clássicos do Intune no Portal do Azure
titleSuffix: Microsoft Intune
description: Conheça as novidades dos grupos no portal do Microsoft Intune no Azure.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
ms.custom: intune-azure
ms.openlocfilehash: 026f7e4177553c8aa7fdb86fd8b24514b1ca64c9
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2018
---
# <a name="microsoft-intune-classic-groups-in-the-azure-portal"></a>Grupos clássicos do Microsoft Intune no Portal do Azure

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ouvimos seus comentários e fizemos mudanças da maneira de trabalhar com grupos no Microsoft Intune.
Se você estiver usando o Intune no Portal do Azure, seus grupos do Intune serão migrados para os grupos de segurança do Azure Active Directory.

A vantagem é que você usará a mesma experiência de grupos em todos os seus aplicativos do Enterprise Mobility + Security e Azure AD. Além disso, você pode usar o PowerShell e a API do Graph para estender e personalizar essa nova funcionalidade.

Os grupos de segurança do Azure AD dão suporte a todos os tipos de implantações do Intune em usuários e dispositivos. Além disso, é possível usar os grupos dinâmicos do Azure AD que são atualizados automaticamente de acordo com os atributos fornecidos. Por exemplo, você poderá criar um grupo de dispositivos que executa o iOS 9. Sempre que um dispositivo com iOS 9 é registrado, ele é exibido automaticamente no grupo dinâmico.

## <a name="what-is-not-available"></a>O que não está disponível?

Alguns dos recursos de grupos do Intune que você talvez pode ter usado anteriormente não estão disponíveis no Azure AD:

- Os grupos **Usuários Desagrupados** e **Dispositivos Desagrupados** do Intune não estão mais disponíveis.
- A opção para **Excluir membros específicos** de um grupo atualmente não existe no Portal do Azure. No entanto, você poderá usar um grupo de segurança do Azure AD com regras avançadas para replicar esse comportamento. Por exemplo, é possível criar uma regra avançada que inclui todas as pessoas do seu departamento de vendas em um grupo de segurança e exclui os grupos que têm a palavra “Assistente” em seu título, com essa regra avançada:

  `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- O grupo **Todos os Dispositivos Gerenciados pelo Exchange ActiveSync** no console clássico do Intune não foi migrado para o Azure AD. No entanto, você ainda poderá acessar informações sobre dispositivos gerenciados pelo EAS no Portal do Azure.

## <a name="how-to-get-started"></a>Como começar?

- Leia os tópicos a seguir para saber mais sobre grupos de segurança do Azure AD e como eles funcionam:
    -  [Gerenciando o acesso a recursos com grupos do Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-manage-groups/).
    -  [Gerenciando grupos no Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Usando atributos para criar regras avançadas](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-  Garanta que todos os administradores que precisam criar grupos são adicionados à função **Administrador de Serviços do Intune** do Azure AD. Observe que a função Administrador de Serviços do Azure AD não tem permissões para **Gerenciar Grupos**.
-  Se os grupos do Intune usaram a opção **Excluir membros específicos**, decida se você pode recriar esses grupos sem exclusões ou se precisa de regras avançadas para atender às necessidades corporativas.


## <a name="what-happened-to-intune-groups"></a>O que aconteceu com os grupos do Intune?
Quando os grupos são migrados do Portal Clássico do Intune para o Portal do Azure, as seguintes regras são aplicadas:

| Grupos no Intune|Grupos no Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Grupo de usuários estático|Grupo de segurança estático do Azure AD|
|Grupo de usuários dinâmico|Grupos de segurança estáticos do Azure AD com uma hierarquia de grupos de segurança do Azure AD|
|Grupo de dispositivos estático|Grupo de segurança estático do Azure AD|
|Grupo de dispositivos dinâmico|Grupo de segurança dinâmico do Azure AD|
|Um grupo com uma condição de inclusão|Grupo de segurança estático do Azure AD que contém membros estáticos ou dinâmicos da condição de inclusão no Intune|
|Um grupo com uma condição de exclusão|Não migrado|
|Grupos internos:<br>- **Todos os usuários**<br>- **Usuários desagrupados**<br>- **Todos os dispositivos**<br>- **Dispositivos desagrupados**<br>- **Todos os computadores**<br>- **Todos os dispositivos móveis**<br>- **Todos os dispositivos gerenciados do MDM**<br>- **Todos os dispositivos gerenciados do EAS**|Grupos de segurança do Azure AD|

## <a name="group-hierarchy"></a>Hierarquia de grupos

No console do Intune, todos os grupos tinham um grupo pai. Os grupos podem conter apenas membros do grupo pai. No Azure AD, os grupos filhos podem conter membros que não fazem parte do grupo pai.

## <a name="group-attributes"></a>Atributos do grupo
Os atributos são propriedades do dispositivo que podem ser usados na definição de grupos. Esta tabela descreve como esses critérios são migrados para grupos de segurança do Azure AD.

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

## <a name="what-happens-to-policies-and-apps-you-previously-deployed"></a>O que acontece com as políticas e os aplicativos já implantados?

As políticas e os aplicativos continuam sendo implantados em grupos, exatamente como antes. No entanto, agora você gerenciará esses grupos no Portal do Azure, em vez de no console do Intune.
