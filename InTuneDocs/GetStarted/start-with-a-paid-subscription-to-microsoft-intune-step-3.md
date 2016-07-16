---
title: "Sincronizar o Active Directory e adicionar usuários ao Intune | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed26d65b98a0ae1bbc4fbac682fb53fddd50b4e5
ms.openlocfilehash: 70a2d32de67f0a69bbc29ca68a1c831c9cf38796


---


# Sincronizar o Active Directory e adicionar usuários ao Intune
Você pode configurar a sincronização de diretórios para importar contas de usuários do Active Directory local para o Microsoft Azure Active Directory (Azure AD). Conectar o Active Directory local a todos os seus serviços baseados no Active Directory do Azure simplifica muito o gerenciamento de identidades de usuário. Você também pode configurar recursos de logon único para tornar a experiência de autenticação fácil e familiar para seus usuários.

Para tornar as coisas ainda mais fáceis, quando você usa vários serviços com o mesmo [locatário do Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), as contas de usuário sincronizadas anteriormente ficam disponíveis para todos os serviços baseados em nuvem que compartilham a mesma assinatura de locatário do Azure AD.

## Sincronizar usuários locais com o Azure AD
A única ferramenta de que você precisa para sincronizar suas contas de usuário com o Azure AD é o [Assistente do Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). O assistente do Azure AD Connect fornece uma experiência simplificada orientada para conexão da sua infraestrutura de identidades local à nuvem.  Escolha sua topologia e necessidades (único ou vários diretórios, sincronização de senha ou federação) e o assistente vai implantar e configurar todos os componentes necessários para deixar sua conexão funcionando. Incluindo: serviços de sincronização, os Serviços de Federação do Active Directory (AD FS) e o módulo do PowerShell do Azure AD.

> [!TIP]
> O Azure AD Connect abrange a funcionalidade que foi lançada anteriormente como Dirsync e Azure AD Sync. Saiba mais sobre a [integração de diretório](http://technet.microsoft.com/library/jj573653.aspx). Para saber sobre os benefícios da sincronização de contas de usuário do seu diretório local para o Azure AD, consulte [Similarities between Active Directory and Azure AD (Similaridades entre Active Directory e Azure AD)](http://technet.microsoft.com/library/dn518177.aspx).

## Conceder permissões de administrador
Depois de acrescentar usuários adicionais à sua assinatura do Intune, é recomendável conceder [credenciais administrativas](administrative-accounts-websites-perms.md) a algumas contas de usuário. O console usado para atribuir credenciais administrativas depende do tipo de administrador que você deseja atribuir:

-   **Administrador de locatários**: use o **[!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]** para atribuir esse tipo de administrador para gerenciar sua assinatura, incluindo cobrança, armazenamento em nuvem e gerenciamento de usuários que podem usar [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

-   **Administrador de serviços**: use o **[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]** para atribuir esse tipo de administrador para tarefas diárias, incluindo o gerenciamento de dispositivos móveis ou computadores, implantação de políticas ou software e execução de relatórios.


### Próximas etapas
Parabéns! Você acabou de concluir a etapa 3 do *Guia de início rápido do Intune*.

>[!div class="step-by-step"]

>[&larr; **Configurações de domínio**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Gerenciar licenças do Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Jun16_HO4-->


