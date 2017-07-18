---
title: "Adicionar usuários e conceder permissões"
description: "Sincronizar usuários locais com o Azure AD e conceder permissões de administrador para sua assinatura do Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4289fdbdadbef34f06514b62722f84354534ae65
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2017
---
# <a name="add-users-and-give-administrative-permission-to-intune"></a>Adicionar usuários e conceder permissão administrativa para o Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Este tópico informa os administradores como adicionar usuários ao Intune e quais permissões administrativas estão disponíveis no serviço Intune.

Como administrador, é possível adicionar usuários diretamente ou sincronizar os usuários do seu Active Directory local. Depois de adicionados, os usuários podem registrar dispositivos e acessar os recursos da empresa. Também é possível conceder aos usuários permissões adicionais, incluindo as de *administrador global* e *administrador de serviços*.

## <a name="add-users-to-intune"></a>Adicionar usuários ao Intune
É possível adicionar manualmente os usuários à assinatura do Intune usando o [portal do Office 365](https://www.office.com/signin) ou o [portal do Intune no Azure](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview). Um administrador pode editar contas de usuário para atribuir licenças do Intune. Você pode atribuir licenças no portal do Office 365 ou no portal do Intune no Azure. Para obter mais informações sobre como usar o portal do Office 365, consulte [Adicionar usuários individualmente ou em massa ao portal do Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="add-intune-users-in-the-office-365-admin-center"></a>Adicionar usuários do Intune no Centro de administração do Office 365
1. Entre no [portal do Office 365](https://www.office.com/signin).
2. No menu do Office 365, selecione **Administrador**.
3. No Centro de administração, selecione **Adicionar um usuário**.

  ![Captura de tela da Administração do Office 365](media/office-add-user.png)

4. Especifique os seguintes detalhes do usuário:
  - **Nome**
  - **Sobrenome**
  - **Nome de exibição** – exibido no portal do Intune
  - **Nome de usuário** – nome UPN no portal do Intune
  - **Local**
  - **Informações de contato** (opcional)
  - **Senha** – gerar automaticamente ou especificar

     ![Captura de tela da Administração do Office 365](media/office-add-user-details.png)

5. Atribua uma licença do Intune. Selecione **Licenças de produto** e escolha a licença do produto.
6. Escolha **Adicionar** para criar um novo usuário.

### <a name="add-intune-users-in-the-azure-intune-portal"></a>Adicionar usuários do Intune no portal do Azure Intune
1. Entre no [Portal do Azure](https://portal.azure.com). e vá até **Monitoramento + Gerenciamento** > **Intune**. Você também pode *pesquisar recursos* para o **Intune**.
2. Selecione **Usuários**.
3. No Centro de administração, selecione **Adicionar um usuário**.
  ![Captura de tela da Administração do Office 365](media/intune-add-user.png)
4. Especifique os seguintes detalhes do usuário:
  - **Nome**
  - **Nome de usuário** – o novo nome no Portal do Azure Active Directory ![Captura de tela da Administração do Office 365](media/intune-add-user-info.png) Escolha **OK** para continuar.
5. Opcionalmente, você pode especificar as seguintes propriedades de usuário:
  - **Perfil** – informações de trabalho incluindo **Cargo** e **Departamento**
  -  **Grupos** – selecione grupos a adicionar para o usuário
  - **Função do diretório** – dar ao usuário permissões administrativas para o Intune

  Selecione **Criar** para adicionar o novo usuário ao Intune.
6. Selecione **Perfil** e, em seguida, escolha um **Local de uso** para o novo usuário. O local de uso é necessário antes que você possa atribuir uma licença do Intune ao novo usuário. Escolha **Salvar** para continuar.
    ![Captura de tela da Administração do Office 365](media/intune-add-user-loc.png)
7. Selecione **Licenças** e, em seguida, escolha **Atribuir** para atribuir uma licença do Intune a este usuário. Uma licença do Intune é necessária para registrar dispositivos ou acessar recursos da empresa. Selecione **Produtos**, escolha o tipo de licença, escolha **Selecionar** e, em seguida, escolha **Atribuir**.

## <a name="grant-admin-permissions"></a>Conceder permissões de administrador

Depois de acrescentar usuários à sua assinatura do Intune, é recomendável conceder permissões administrativas a alguns usuários:
-   [Administrador global](#tenant-administrator): use o portal do Office 365 para atribuir esse tipo de administrador. O administrador global pode gerenciar sua assinatura, incluindo cobrança, armazenamento em nuvem e gerenciamento de usuários que podem usar o Intune.
-   [Administrador limitado ou personalizado](#service-administrator): use o console do Intune no Azure ou do Office 365 para atribuir a esse tipo de administrador para tarefas diárias, incluindo o gerenciamento de dispositivos móveis e computadores, a implantação de políticas e de aplicativos e a execução de relatórios.

![Imagem da atribuição de funções no portal do Office 365.](./media/office-assign-roles.png)

### <a name="types-of-administrators"></a>Tipos de administradores

Atribua uma ou mais permissões de administrador aos usuários. Essas permissões definem o escopo administrativo para os usuários e as tarefas que eles podem gerenciar. As permissões de administrador são comuns entre os diferentes serviços em nuvem da Microsoft, embora alguns serviços possam não dar suporte a algumas permissões. O Intune usa as seguintes permissões de administrador:

- **Administrador global** (Office 365 e Intune) – tem acesso a todos os recursos administrativos do Intune. Por padrão, a pessoa que se inscreve no Intune se torna um administrador global. Os administradores globais são os únicos que podem atribuir outras funções de administrador. É possível ter mais de um administrador global na sua organização. Recomendamos como melhor prática que apenas algumas pessoas da empresa tenham essa função, a fim de reduzir os riscos para o seu negócio.
- **Administrador de cobranças** (Office 365 e Intune) – faz compras, gerencia assinaturas, gerencia tíquetes de suporte e monitora a integridade do serviço.
- **Administrador de senhas** (Office 365 e Intune) – redefine senhas, gerencia solicitações de serviço e monitora a integridade do serviço. Administradores de senha são limitados a redefinição de senhas de usuários.
- **Administrador de serviços** (Office 365) – abre solicitações de suporte com a Microsoft e observa o painel de serviços e a central de mensagens. Eles têm permissões “somente leitura”, exceto para a abertura e leitura de tíquetes de suporte.
- **Administrador de gerenciamento de usuários** (Office 365 e Intune) – Redefine senhas, monitora a integridade do serviço, adiciona e exclui contas de usuário e gerencia solicitações de serviço. O administrador de gerenciamento de usuários não pode excluir um administrador global, criar outras funções de administrador ou redefinir senhas para outros administradores.

Por padrão, a conta usada para criar sua assinatura do Microsoft Intune é de um administrador global. Como prática recomendada, não use o administrador global para tarefas de gerenciamento cotidianas. Um administrador não precisa de uma licença do Intune para acessar o console do administrador do Intune. Consulte a seção de locatário do Azure AD em [O que é um diretório do Azure AD?](http://technet.microsoft.com/library/jj573650.aspx).

Para acessar o portal do Office 365, sua conta deve ter um status de **Entrada permitida** configurado. No portal do Intune, em **Perfil**, defina **Bloquear entrada** para **Não** para permitir o acesso. Esse status é diferente de ter uma licença para a assinatura. Por padrão, todas as contas de usuário são **Permitidas**. Usuários sem permissões de administrador podem usar o portal do Office 365 para redefinir as senhas do Intune.

## <a name="sync-active-directory-and-add-users-to-intune"></a>Sincronizar o Active Directory e adicionar usuários ao Intune
É possível configurar a sincronização de diretórios para importar contas de usuários do Active Directory local para o Microsoft Azure Active Directory (Azure AD), o que inclui os usuários do Intune. Conectar o Active Directory local a todos os seus serviços baseados no Active Directory do Azure simplifica muito o gerenciamento de identidades de usuário. Você também pode configurar recursos de logon único para tornar a experiência de autenticação fácil e familiar para seus usuários. Ao vincular o mesmo [locatário do Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) a vários serviços, as contas de usuário sincronizadas anteriormente estarão disponíveis para todos os serviços baseados em nuvem.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Como sincronizar usuários locais com o Azure AD
A única ferramenta de que você precisa para sincronizar suas contas de usuário com o Azure AD é o [Assistente do Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). O assistente do Azure AD Connect fornece uma experiência simplificada orientada para conexão da sua infraestrutura de identidades local à nuvem.  Escolha sua topologia e necessidades (único ou vários diretórios, sincronização de senha ou federação). O assistente implanta e configura todos os componentes necessários para deixar sua conexão funcionando. Incluindo: serviços de sincronização, os Serviços de Federação do Active Directory (AD FS) e o módulo do PowerShell do Azure AD.

> [!TIP]
> O Azure AD Connect abrange a funcionalidade que foi lançada anteriormente como Dirsync e Azure AD Sync. Saiba mais sobre a [integração de diretório](http://technet.microsoft.com/library/jj573653.aspx). Para saber sobre a sincronização de contas de usuário do seu diretório local para o Azure AD, consulte [Similarities between Active Directory and Azure AD (Similaridades entre Active Directory e Azure AD)](http://technet.microsoft.com/library/dn518177.aspx).
