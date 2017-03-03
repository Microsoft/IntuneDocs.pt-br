---
title: "Adicionar usuários e conceder permissões | Microsoft Docs"
description: "Sincronizar usuários locais com o Azure AD e conceder permissões de administrador para sua assinatura do Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ad13897fe7bbe4fe13167bb4ce7f558b436a7a90
ms.openlocfilehash: b1f16df329c01aeb45885f3981e2d9d7ef854e8b


---

# <a name="add-users-and-give-administrative-permission-to-intune"></a>Adicionar usuários e conceder permissão administrativa para o Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico informa os administradores como adicionar usuários ao Intune e quais permissões administrativas estão disponíveis no serviço Intune.

Como administrador, é possível adicionar usuários diretamente ou sincronizar os usuários do seu Active Directory local. Depois de adicionados, os usuários podem registrar dispositivos e acessar os recursos da empresa. Também é possível conceder aos usuários permissões adicionais, incluindo *administrador de locatários*, *administrador de serviços* e *permissões de gerenciador de registro de dispositivo*.

Este tópico ajuda a:

- [Adicionar usuários ao Intune](#add-users-to-intune)
- [Conceder permissões adicionais do Intune](#grant-intune-permissions), incluindo:
  - [Administrador de locatários](#tenant-administrator)
  - [Administrador de serviços](#service-administrator)
  - [Gerenciadores de registro de dispositivos](#device-enrollment-managers)

## <a name="add-users-to-intune"></a>Adicionar usuários ao Intune
É possível adicionar manualmente os usuários à assinatura do Intune usando o [portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), mas eles não são atribuídos automaticamente a uma licença do Intune. Em vez disso, posteriormente, um administrador de locatários do Intune precisa editar a conta do usuário para atribuir uma licença ao usuário do portal do Office 365. Para obter diretrizes, consulte [Adicionar usuários individualmente ou em massa ao portal do Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="sync-active-directory-and-add-users-to-intune"></a>Sincronizar o Active Directory e adicionar usuários ao Intune
É possível configurar a sincronização de diretórios para importar contas de usuários do Active Directory local para o Microsoft Azure Active Directory (Azure AD), o que inclui os usuários do Intune. Conectar o Active Directory local a todos os seus serviços baseados no Active Directory do Azure simplifica muito o gerenciamento de identidades de usuário. Você também pode configurar recursos de logon único para tornar a experiência de autenticação fácil e familiar para seus usuários. Ao vincular o mesmo [locatário do Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) a vários serviços, as contas de usuário sincronizadas anteriormente estarão disponíveis para todos os serviços baseados em nuvem.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Como sincronizar usuários locais com o Azure AD
A única ferramenta de que você precisa para sincronizar suas contas de usuário com o Azure AD é o [Assistente do Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). O assistente do Azure AD Connect fornece uma experiência simplificada orientada para conexão da sua infraestrutura de identidades local à nuvem.  Escolha sua topologia e necessidades (único ou vários diretórios, sincronização de senha ou federação) e o assistente vai implantar e configurar todos os componentes necessários para deixar sua conexão funcionando. Incluindo: serviços de sincronização, os Serviços de Federação do Active Directory (AD FS) e o módulo do PowerShell do Azure AD.

> [!TIP]
> O Azure AD Connect abrange a funcionalidade que foi lançada anteriormente como Dirsync e Azure AD Sync. Saiba mais sobre a [integração de diretório](http://technet.microsoft.com/library/jj573653.aspx). Para saber sobre os benefícios da sincronização de contas de usuário do seu diretório local para o Azure AD, consulte [Similarities between Active Directory and Azure AD (Similaridades entre Active Directory e Azure AD)](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="grant-intune-permissions"></a>Conceder permissões do Intune

Depois de acrescentar usuários à sua assinatura do Intune, é recomendável conceder permissões administrativas a algumas contas de usuário. Para administrar o Intune, você pode conceder aos usuários três tipos de permissão do Intune
-   **Administrador de locatários**: use o portal do Office 365 para atribuir a esse tipo de administrador o gerenciamento da sua assinatura, incluindo cobrança, armazenamento em nuvem e gerenciamento de usuários que podem usar o Intune.
-   **Administrador de serviços**: use o console de administração do Microsoft Intune para atribuir a esse tipo de administrador tarefas diárias, incluindo o gerenciamento de dispositivos móveis ou computadores, a implantação de políticas e aplicativos e execução de relatórios.
-   **Gerenciador de registro de dispositivos**: use o console de administração do Microsoft Intune para atribuir a esse tipo de administrador tarefas diárias, incluindo o gerenciamento de dispositivos e computadores, a implantação de políticas e aplicativos e execução de relatórios.


### <a name="tenant-administrator"></a>Administrador de locatários


Aos administradores de locatários é atribuída uma função de administrador que define o escopo desse usuário e as tarefas que podem gerenciar. As funções de administrador são comuns entre os diferentes serviços em nuvem da Microsoft, embora alguns serviços possam não dar suporte para algumas funções. O Intune usa as seguintes funções:
- **Administrador global** – Tem acesso a todos os recursos administrativos do Intune. Por padrão, a pessoa que se inscreve no Intune se torna um administrador global. Os administradores globais são os únicos que podem atribuir outras funções de administrador. É possível ter mais de um administrador global na sua organização. Recomendamos como melhor prática que apenas algumas pessoas da empresa tenham essa função, a fim de reduzir os riscos para o seu negócio.
- **Administrador de cobranças** – Faz compras, gerencia assinaturas, gerencia tíquetes de suporte e monitora a integridade do serviço.
- **Administrador de senhas** – Redefine senhas, gerencia solicitações de serviço e monitora a integridade do serviço. Administradores de senha são limitados a redefinição de senhas de usuários.
- **Administrador de suporte de serviço** – Abre solicitações de suporte com a Microsoft e observa o painel de serviços e a central de mensagens. Eles têm permissões “somente leitura”, exceto para a abertura e leitura de tíquetes de suporte.
- **Administrador de gerenciamento de usuários** – Redefine senhas, monitora a integridade do serviço, adiciona e exclui contas de usuário e gerencia solicitações de serviço. O administrador de gerenciamento de usuários não pode excluir um administrador global, criar outras funções de administrador ou redefinir senhas para administradores globais, de cobrança e de serviço.

Por padrão, a conta usada para criar sua assinatura do Microsoft Intune é de um administrador de locatários com a função de administrador global. Como administrador de locatários, use o console de administração do Intune para gerenciar a sua assinatura do Intune e atribuir administradores de locatários do [portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854). Use um administrador de locatários com a função de administração global para acessar o portal e atribuir seu primeiro administrador de serviços. Como prática recomendada, não use o administrador de locatários para tarefas de gerenciamento cotidianas. Um administrador de locatários não precisa de uma licença do Intune para acessar o console de administração do Intune. O administrador de locatários é um conceito comum entre os serviços em nuvem da Microsoft. Quando você assina o Intune, seu serviço é um locatário do Azure AD. Consulte a seção de locatário do Azure AD em [O que é um diretório do Azure AD?](http://technet.microsoft.com/library/jj573650.aspx).

Como administrador de locatários, use o [portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) para gerenciar a sua assinatura, incluindo as tarefas a seguir, quando permitido pela sua função de administrador:

- Gerenciar contas de usuário e configurar a sincronização de diretório do seu Active Directory local
- Gerenciar grupos de usuários, chamados grupos de segurança
- Atribuir licenças de usuários para o Intune
- Configurar o nome de domínio para sua assinatura usada quando o usuário entra (por exemplo, contoso.com)
- Gerenciar cobrança e compras, incluindo licenças e espaço de armazenamento em nuvem
- Encontrar links para exibir a integridade do serviço do Intune

Para acessar o portal do Office 365, sua conta deve ter um status de entrada de **Permitido**. Esse status é diferente de ter uma licença para a assinatura. Por padrão, todas as contas de usuário são **Permitidas**. Usuários sem permissões de administrador podem usar o portal do Office 365 para redefinir as senhas do Intune.

### <a name="service-administrator"></a>Administrador de serviços

Por padrão, o Intune não atribui um administrador de serviços. Em vez disso, use um administrador locatário com a função de administrador global para atribuir o primeiro administrador de serviços da sua assinatura. Como administrador de serviços, use o [console de administração do Intune](https://manage.microsoft.com/) para gerenciar as tarefas cotidianas do Intune. Você atribui administradores de serviço do console de administração. Um administrador de serviços precisa ter uma licença do Intune para acessar o console de administração.

Administradores de serviços recebem uma das seguintes permissões:
- **Acesso completo**: acesso irrestrito a todas as áreas do console de administração do Intune, adicionar e gerenciar outros administradores de serviço
- **Acesso “somente leitura”**: permissão de leitura para todas as áreas do console de administração do Intune, não pode modificar dados, mas pode executar relatórios
- **Assistência técnica – Nós dos grupos**: permite que o administrador de serviços execute somente as tarefas associadas a cenários de assistência técnica, consulte [Personalizar exibições do console do Intune de acordo com funções do administrador](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console)

Como administrador de serviços, use este portal para gerenciar as tarefas do dia a dia, incluindo:

- Criar e gerenciar políticas para computadores e dispositivos móveis
- Carregar e implantar atualizações de software e aplicativos
- Gerenciar a Endpoint Protection em computadores
- Exibir status do dispositivo e executar relatórios

### <a name="device-enrollment-managers"></a>Gerenciadores de registro de dispositivos

Os gerenciadores de registro de dispositivos são contas de usuário padrão que têm permissão adicional para registrar mais dispositivos sem usuário. Por padrão, cada usuário do Intune pode registrar até&15; dispositivos. Como administrador, é possível conceder a uma conta de usuário uma permissão de gerenciador de registro do dispositivo. Essa conta pode registrar um grande número de dispositivos corporativos. Isso é útil quando os dispositivos podem ser atribuídos aos usuários em caráter temporário ou podem trabalhar em um modo de quiosque em que não é necessária associação entre usuário e dispositivo. Para obter mais informações, consulte [Gerenciador de registro de dispositivo](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Configurações de domínio**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Gerenciar licenças do Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Feb17_HO3-->


