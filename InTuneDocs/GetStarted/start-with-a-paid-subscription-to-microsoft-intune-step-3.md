---
title: "Sincronizar o Active Directory e adicionar usuários ao Intune | Microsoft Intune"
description: "Sincronizar usuários locais com o Azure AD e conceder permissões de administrador para sua assinatura do Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 33534c685ad3a4ddfd4b605e088132f2b8ff2c36


---


# <a name="sync-active-directory-and-add-users-to-intune"></a>Sincronizar o Active Directory e adicionar usuários ao Intune
Você pode configurar a sincronização de diretórios para importar contas de usuários do Active Directory local para o Microsoft Azure Active Directory (Azure AD). Conectar o Active Directory local a todos os seus serviços baseados no Active Directory do Azure simplifica muito o gerenciamento de identidades de usuário. Você também pode configurar recursos de logon único para tornar a experiência de autenticação fácil e familiar para seus usuários.

Para tornar as coisas ainda mais fáceis, quando você usa vários serviços com o mesmo [locatário do Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/), as contas de usuário sincronizadas anteriormente ficam disponíveis para todos os serviços baseados em nuvem que compartilham a mesma assinatura de locatário do Azure AD.

## <a name="synchronize-on-premises-users-with-azure-ad"></a>Sincronizar usuários locais com o Azure AD
A única ferramenta de que você precisa para sincronizar suas contas de usuário com o Azure AD é o [Assistente do Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). O assistente do Azure AD Connect fornece uma experiência simplificada orientada para conexão da sua infraestrutura de identidades local à nuvem.  Escolha sua topologia e necessidades (único ou vários diretórios, sincronização de senha ou federação) e o assistente vai implantar e configurar todos os componentes necessários para deixar sua conexão funcionando. Incluindo: serviços de sincronização, os Serviços de Federação do Active Directory (AD FS) e o módulo do PowerShell do Azure AD.

> [!TIP]
> O Azure AD Connect abrange a funcionalidade que foi lançada anteriormente como Dirsync e Azure AD Sync. Saiba mais sobre a [integração de diretório](http://technet.microsoft.com/library/jj573653.aspx). Para saber sobre os benefícios da sincronização de contas de usuário do seu diretório local para o Azure AD, consulte [Similarities between Active Directory and Azure AD (Similaridades entre Active Directory e Azure AD)](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="grant-administrator-permissions"></a>Conceder permissões de administrador

Para administrar o Intune, você usará:
- Dois tipos de contas de administrador
- Contas de usuário com permissões adicionais
- Dois portais/consoles de administração baseados na Web para conceder aos seus administradores acesso aos itens que eles devem gerenciar.

Depois de acrescentar usuários adicionais à sua assinatura do Intune, é recomendável conceder credenciais administrativas a algumas contas de usuário. O console usado para atribuir credenciais administrativas depende do tipo de administrador que você deseja atribuir:

-   **Administrador de locatários**: use o **portal de conta do Microsoft Intune** para atribuir esse tipo de administrador para gerenciar sua assinatura, incluindo cobrança, armazenamento em nuvem e gerenciamento de usuários que podem usar o Intune.

-   **Administrador de serviços**: use o **console administrador do Microsoft Intune** para atribuir esse tipo de administrador para tarefas diárias, incluindo o gerenciamento de dispositivos móveis ou computadores, implantação de políticas ou software e execução de relatórios.

As seções a seguir explicam essas contas e portais.

## <a name="administrator-accounts-and-user-accounts-with-special-permissions"></a>Contas de administrador e contas de usuário com permissões especiais

Abaixo estão as contas e permissões que você usará para o Intune.

### <a name="tenant-administrator"></a>Administrador de locatários
|Níveis de permissão|Mais informações|
|--------------------------|-------------------------|
|Aos administradores de locatários é atribuída uma função de administrador que define o escopo desse usuário e as tarefas que podem gerenciar.<br /><br />As funções de administrador são comuns entre os diferentes serviços em nuvem da Microsoft, embora alguns serviços possam não dar suporte para algumas funções.<br /><br /> O Microsoft Intune usa as seguintes funções:<br /><br />- Administrador global<br />- Administrador de cobrança<br />- Administrador de senhas<br />- Administrador de suporte de serviço<br />- Administrador de gerenciamento de usuários|Por padrão, a conta usada para criar sua assinatura do Microsoft Intune é de um administrador de locatários com a função de administrador global.<br /></br>  Como um administrador de locatários, você usa o [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] para gerenciar a sua assinatura do Intune e atribuir administradores de locatários do [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Use um administrador de locatários com a função de administração global para acessar o [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] e atribuir seu primeiro administrador de serviços. Como prática recomendada, não use o administrador de locatários para tarefas de gerenciamento cotidianas. Um administrador de locatários não precisa de uma licença do Intune para acessar o [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />O administrador de locatários é um conceito comum entre os serviços em nuvem da Microsoft. Quando você assina o Intune, seu serviço é um locatário do Microsoft Azure AD. Consulte a seção de locatário do Azure AD em [What is an Azure AD directory?](http://technet.microsoft.com/library/jj573650.aspx) (O que é um diretório do Azure AD?).|


### <a name="service-administrator"></a>Administrador de serviços
|Níveis de permissão|Mais informações|
|--------------------------|-------------------------|
|Administradores de serviços recebem uma das seguintes permissões:<br /><br />**Acesso completo**: concede acesso a todas as áreas do [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)], sem restrições. Também é possível adicionar e gerenciar outros administradores de serviço.<br /><br />**Acesso somente leitura**: concede permissão de leitura a todas as áreas do [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Um administrador de serviço somente de leitura não pode modificar os dados, mas pode criar relatórios.<br /><br />**Assistência técnica - Nó Grupos**: concede permissões que permitem que o administrador de serviços execute somente um conjunto de tarefas comumente associadas a cenários de assistência técnica. Para obter informações sobre este conjunto de permissões, consulte [Customize Intune console views according to admin roles](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console) (Personalizar exibições do console do Intune de acordo com as funções de administração).|Por padrão, o Intune não atribui um administrador de serviços. Em vez disso, use um administrador locatário com a função de administrador global para atribuir o primeiro administrador de serviços da sua assinatura. </br></br> Como administrador de serviços, você usa o [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] para gerenciar as tarefas cotidianas do Intune.<br /><br />Você atribui administradores de serviço do console de administração. Um administrador de serviços precisa ter uma licença do Intune antes que a conta possa acessar o console de administração.|



### <a name="device-enrollment-managers"></a>Gerenciadores de registro de dispositivos
|Níveis de permissão|Mais informações|
|--------------------------|-------------------------|
|Os gerenciadores de registro de dispositivos são contas de usuário padrão que têm permissão adicional para registrar mais de cinco dispositivos.|Por padrão, cada usuário do [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] pode registrar até cinco dispositivos. No entanto, você pode conceder a uma conta de usuário a permissão de gerenciador de registro de dispositivos e usar essa conta para registrar grandes grupos de dispositivos corporativos. Isso é útil quando os dispositivos podem ser atribuídos aos usuários em caráter temporário ou podem trabalhar em um modo de quiosque em que não é necessária associação entre usuário e dispositivo.|




>[!div class="step-by-step"]

>[&larr; **Configurações de domínio**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Gerenciar licenças do Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Nov16_HO4-->


