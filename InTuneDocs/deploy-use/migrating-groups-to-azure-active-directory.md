---
title: "Migração para grupos do Azure Active Directory| Microsoft Intune"
description: "Como os grupos serão migrados do Intune para o Azure AD"
keywords: 
author: Mtillman
ms.author: mtillman
manager: angerobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: e14bbadc4293b7b963197b35704a7170e4fc29e8


---

## <a name="the-new-admin-experience-for-groups"></a>A nova experiência de administração para grupos
    
Com base nos seus comentários sobre ter uma experiência de agrupamento e direcionamento no Enterprise Mobility & Security, estamos convertendo os Grupos do Intune para Grupos de Segurança baseados no Azure Active Directory. Isso unificará o gerenciamento de grupos no Intune e no Azure Active Directory (Azure AD). Com a nova experiência, você não precisará duplicar grupos entre os serviços e terá extensibilidade usando o PowerShell e o Graph. 

### <a name="how-and-when-will-i-migrate-to-the-new-groups-experience"></a>Como e quando eu migrarei para a nova experiência de grupos?
Os clientes atuais serão migrados ao longo de um período, que começará a partir de dezembro de 2016. Você receberá um aviso antes de os grupos serem migrados. Se tiver preocupações relacionadas à migração, entre em contato com nossa equipe de migração em [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="what-new-features-will-be-available-to-me"></a>Quais novos recursos estarão disponíveis para mim?
Veja as novas funcionalidades que serão introduzidas: 
 
-    Os Grupos de segurança do Azure AD terão suporte do Intune para todos os tipos de implantações. 
-    Os Grupos de segurança do Azure AD darão suporte ao agrupamento de dispositivos com os usuários.
-    Os Grupos de segurança do Azure AD darão suporte a grupos dinâmicos com atributos de dispositivos do Intune. Por exemplo, você poderá agrupar dinamicamente os dispositivos com base na plataforma, como iOS. Dessa forma, quando um novo dispositivo iOS for registrado em sua organização, ele será adicionado automaticamente ao grupo dinâmico de dispositivos iOS.
-    Experiências de administração compartilhadas para o gerenciamento de grupos no Azure AD e no Intune.
- A *função de Administrador de serviço do Intune* será adicionada ao Azure AD para permitir que os administradores de serviço do Intune executem tarefas de gerenciamento de grupos no Azure AD.

 
### <a name="what-intune-functionality-wont-be-available"></a>Quais funcionalidades do Intune não estarão disponíveis?
Embora a experiência de grupo vá melhorar, algumas funcionalidades do Intune não estarão disponíveis após a migração.

#### <a name="group-management-functionality"></a>Funcionalidade de gerenciamento de grupos

-   Você não poderá excluir membros ou grupos quando criar um novo grupo. No entanto, os grupos dinâmicos do Azure AD permitirão que você utilize atributos para criar regras avançadas para excluir membros com base em critérios. Por exemplo, é possível criar uma regra avançada que inclui todas as pessoas do seu departamento de vendas em um grupo de segurança, mas não aqueles que têm a palavra “Assistente” em seu título, com essa regra avançada: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`. Para obter mais informações, consulte [Usar atributos para criar regras avançadas](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-   Não haverá suporte para grupos de **Usuários Desagrupados** e **Dispositivos Desagrupados**. Esses grupos não serão migrados.

#### <a name="group-dependent-functionality"></a>Funcionalidade dependente de grupo

-   A função de Administrador de serviço não terá permissões para **Gerenciar grupos**.
-   Não será possível agrupar dispositivos do Exchange ActiveSync.  O grupo **Todos os Dispositivos Gerenciados pelo EAS** será convertido de um grupo para um modo de exibição de relatório.
-  A dinamização com grupos em relatórios não estará disponível.
-  O direcionamento de grupos personalizados de regras de notificação não estará disponível.

### <a name="what-should-i-do-to-prepare-for-this-change"></a>O que eu devo fazer para me preparar para essa alteração?
 Temos recomendações que facilitarão essa transição para você:
 
- Limpe quaisquer grupos indesejados ou desnecessários do Intune antes da migração.
- Avaliar o uso de exclusão em grupos e considerar como recriar seus grupos para que você não precise usar a exclusão ou para que você possa usar regras avançadas para atingir o mesmo objetivo.
-  Se você tiver administradores que não têm permissões para criar grupos no Azure AD, peça que o administrador do Azure AD os adicione à função **Administrador de serviço do Intune** do Azure AD.

Você também pode aprender mais sobre grupos de segurança do Azure AD:
-  Para obter uma visão geral, leia [Gerenciando acesso a recursos com grupos do Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
-  Para obter informações sobre como criar e gerenciar grupos do Azure AD, consulte [Gerenciar grupos no Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
-  Para obter mais informações sobre regras avançadas para grupos de segurança, [Usando atributos para criar regras avançadas](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).

> [!NOTE]
Você pode observar que a documentação do grupo de segurança do Azure AD não aborda a criação de grupos de dispositivos. Esta funcionalidade será habilitada no Azure AD antes da migração de grupo Intune começar.

## <a name="migration-details"></a>Detalhes da migração
Aqui estão os detalhes de como os grupos do Intune serão migrados para os grupos de segurança do Azure AD.

### <a name="migration-of-existing-groups"></a>Migração de grupos existentes

| Grupo do Intune torna-se...|... grupo de segurança do Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Grupos de usuários estáticos direcionados pela política do Intune|Grupos de segurança estáticos do Azure AD que contêm os mesmos usuários|
|Grupos de usuários dinâmicos direcionados pela política do Intune|Grupos de segurança estáticos do Azure AD com uma hierarquia de grupos de segurança do Azure AD|
|Grupos de dispositivos estáticos direcionados pela política do Intune|Grupos de segurança estáticos do Azure AD com dispositivos|
|Grupos de dispositivos dinâmicos com atributos de dispositivo, que são afetados pela política do Intune|Grupos de segurança dinâmicos do Azure AD com atributos de dispositivos|
|Um grupo com uma condição de inclusão|Um grupo de segurança estático separado do Azure AD que terá um grupo + qualquer membro dinâmico/estático que a condição inclusa tenha permissão no Intune|
|Um grupo com uma condição de exclusão|... não será migrado. As condições de exclusão não têm suporte durante a criação de grupos estáticos no Azure AD. Uma condição de exclusão pode ser usada ao criar um grupo dinâmico no Azure AD.|
|Os grupos padrão **Todos os Usuários**, **Usuários Desagrupados**, **Todos os Dispositivos**, **Dispositivos Desagrupados**, **Todos os Computadores**, **Todos os Dispositivos Móveis**, **Todos os dispositivos gerenciados MDM** e **Todos os dispositivos gerenciados EAS**, que você usa na política do Intune  |Grupos de segurança do Azure AD. Os grupos padrão que não estão sendo usados teriam que ser criados pelo cliente quando necessário, usando grupos dinâmicos.|

### <a name="changes-in-hierarchical-views"></a>Alterações em exibições hierárquicas
A exibição hierárquica de grupos em uma relação pai-filho no Intune era uma relação de subconjunto-superconjunto, enquanto no Azure AD, este não é o caso. O filho pode ter membros que o pai não tinha. Os grupos também podem ser cíclicos na natureza no Azure AD: um grupo pai pode ser filho do grupo filho.

### <a name="attribute-conversion-during-migration"></a>Conversão de atributo durante a migração
Os atributos são propriedades do dispositivo que podem ser usados na definição de grupos. Esta tabela descreve como esses critérios serão migrados para grupos de segurança do Azure AD.

| Atributo do Intune|Atributo do Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Atributo de Unidade Organizacional (OU) para grupos de dispositivos|Atributo OU para grupos dinâmicos. Valores de atributo disponibilizados para o administrador referente a cada locatário ao adicioná-lo como um dos componentes do locatário para exibição.|
|Atributo de nome de domínio para grupos de dispositivos|Atributo de Nome de domínio para grupos dinâmicos. Valores de atributo disponibilizados para o administrador referente a cada locatário ao adicioná-lo como um dos componentes do locatário para exibição|
|Grupo de segurança como um atributo para grupos de usuários|Grupos não podem ser atributos em consultas dinâmicas do Azure AD. Grupos dinâmicos podem conter somente atributos específicos de dispositivo ou de usuário.|
|Atributo de gerente para grupos de usuários|Regra avançada para atributo de *gerente* em grupos dinâmicos|
|Todos os usuários do grupo de usuário pai|Grupo estático com aquele grupo como membro|
|Todos os dispositivos móveis do grupo de dispositivo pai|Grupo estático com aquele grupo como membro|
|Todos os dispositivos móveis administrados pelo Gerenciamento Direto do Microsoft Intune|Atributo do Tipo de Gerenciamento com 'MDM' como valor para grupo dinâmico|
|Todos os dispositivos móveis gerenciados pelo EAS|Dispositivos EAS não podem ser agrupados no Azure AD. O grupo **Todos os Dispositivos Gerenciados pelo EAS** será convertido de um grupo para um modo de exibição de relatório.|
|Grupos aninhados dentro de grupos estáticos |Grupos aninhados dentro de grupos estáticos|
|Grupos aninhados dentro de grupos dinâmicos|Grupo dinâmico com um nível de aninhamento|


## <a name="migration-of-policies"></a>Migração de políticas
Durante a migração de grupos, você continuará a gerenciar as políticas no console do Intune. Haverá um link no console do Intune para o console de gerenciamento do Azure, no qual você gerenciará seus grupos. Suas políticas continuarão a ser implantadas nos grupos de segurança migrados do Azure AD, que são paralelos aos grupos do Intune antigos.

Quando toda a funcionalidade do Intune for migrada para o portal de gerenciamento do Azure (em torno do primeiro trimestre de 2017), você gerenciará políticas e grupos.

     
### <a name="see-also"></a>Consulte também
[Gerenciando acesso a recursos com grupos do Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)

[Gerenciando grupos no Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)

[Usando atributos para criar regras avançadas](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)



<!--HONumber=Nov16_HO1-->


