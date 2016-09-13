---
title: "Contas administrativas, sites e permissões | Microsoft Intune"
description: "contas administrativas permissões sites"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db3075e7-38fd-4dfe-b266-26aed10ac8ea
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0c1e08cc49d75303f6793894e3c8a040f6e7a8b1
ms.openlocfilehash: 29d6f9cd31e6fbf287ae30fb2171bf752ff71157


---

# Contas administrativas, sites e permissões no Microsoft Intune

Antes de configurar o Microsoft Intune, examine este tópico e outros requisitos listados em [What to know before you start Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md) (O que saber antes de começar a usar o Microsoft Intune).

Para administrar o Intune, você usará:
- Dois tipos de contas de administrador
- Contas de usuário com permissões adicionais
- Dois portais/consoles de administração baseados na Web para conceder aos seus administradores acesso aos itens que eles devem gerenciar.

As seções a seguir explicam essas contas e portais.

## Contas de administrador e contas de usuário com permissões especiais

Abaixo estão as contas e permissões que você usará para o Intune.

### Administrador de locatários
|Níveis de permissão|Mais informações|
|--------------------------|-------------------------|
|Aos administradores de locatários é atribuída uma função de administrador que define o escopo desse usuário e as tarefas que podem gerenciar.<br /><br />As funções de administrador são comuns entre os diferentes serviços em nuvem da Microsoft, embora alguns serviços possam não dar suporte para algumas funções.<br /><br /> O Microsoft Intune usa as seguintes funções:<br /><br />- Administrador global<br />- Administrador de cobrança<br />- Administrador de senhas<br />- Administrador de suporte de serviço<br />- Administrador de gerenciamento de usuários|Por padrão, a conta usada para criar sua assinatura do Microsoft Intune é de um administrador de locatários com a função de administrador global.<br /></br>  Como um administrador de locatários, você usa o [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] para gerenciar a sua assinatura do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] e atribui administradores de locatários do [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Use um administrador de locatários com a função de administração global para acessar o [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] e atribuir seu primeiro administrador de serviços. Como prática recomendada, não use o administrador de locatários para tarefas de gerenciamento cotidianas. Um administrador de locatários não precisa de uma licença para que o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] acesse o [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />O administrador de locatários é um conceito comum entre os serviços em nuvem da Microsoft. Quando você assina o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], seu serviço é um locatário do Microsoft Azure AD. Consulte a seção de locatário do Azure AD em [What is an Azure AD directory?](http://technet.microsoft.com/library/jj573650.aspx) (O que é um diretório do Azure AD?).|


### Administrador de serviços
|Níveis de permissão|Mais informações|
|--------------------------|-------------------------|
|Administradores de serviços recebem uma das seguintes permissões:<br /><br />**Acesso completo**: concede acesso a todas as áreas do [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)], sem restrições. Também é possível adicionar e gerenciar outros administradores de serviço.<br /><br />**Acesso somente leitura**: concede permissão de leitura a todas as áreas do [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Um administrador de serviço somente de leitura não pode modificar os dados, mas pode criar relatórios.<br /><br />**Assistência técnica - Nó Grupos**: concede permissões que permitem que o administrador de serviços execute somente um conjunto de tarefas comumente associadas a cenários de assistência técnica. Para obter informações sobre este conjunto de permissões, consulte [Customize Intune console views according to admin roles](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console) (Personalizar exibições do console do Intune de acordo com as funções de administração).|Por padrão, o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] não atribui um administrador de serviços. Em vez disso, use um administrador locatário com a função de administrador global para atribuir o primeiro administrador de serviços da sua assinatura. </br></br> Como administrador de serviços, você usa o [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] para gerenciar as tarefas cotidianas do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].<br /><br />Você atribui administradores de serviço do console de administração. Um administrador de serviços precisa ter uma licença para o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] antes que a conta possa acessar o console de administração.|



### Gerenciadores de registro de dispositivos
|Níveis de permissão|Mais informações|
|--------------------------|-------------------------|
|Os gerenciadores de registro de dispositivos são contas de usuário padrão que têm permissão adicional para registrar mais de cinco dispositivos.|Por padrão, cada usuário do [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] pode registrar até cinco dispositivos. No entanto, você pode conceder a uma conta de usuário a permissão de gerenciador de registro de dispositivos e usar essa conta para registrar grandes grupos de dispositivos corporativos. Isso é útil quando os dispositivos podem ser atribuídos aos usuários em caráter temporário ou podem trabalhar em um modo de quiosque em que não é necessária associação entre usuário e dispositivo.|


## Sites administrativos do Intune
 Diferentes tarefas administrativas exigem que você use um site administrativo a seguir, que você pode acessar usando um [navegador da Web com suporte](supported-web-browsers.md).

- [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Console do administrador do Microsoft Intune](https://admin.manage.microsoft.com/)

### [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Como administrador de locatários, use este portal para gerenciar a sua assinatura**, incluindo as tarefas a seguir, quando permitido pela sua função de administrador:

- Gerenciar contas de usuário da assinatura e configurar a sincronização de diretório do seu Active Directory local.
- Gerenciar grupos de usuários, chamados grupos de segurança.
- Atribuir licenças aos usuários para usar o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Configurar o nome de domínio que você usa com sua assinatura. O nome de domínio define a conta com a qual os usuários entram.
- Gerenciar detalhes de cobrança e compra da sua assinatura, incluindo o número de licenças que possui ou a quantidade de espaço de armazenamento na nuvem que você pode usar.
- Encontrar links para exibir a integridade do serviço do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Como administrador de locatários, você pode entrar no portal do Office 365 para gerenciar a assinatura, mesmo que sua conta não tenha recebido a atribuição de uma licença para usar [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Qualquer usuário que tenha uma licença para o Intune, mas que não seja um administrador, pode usar este portal para redefinir sua senha da conta e editar seu perfil.
- Para acessar o portal do Office 365, sua conta deve ter um status de entrada de **Permitido**. Esse status é diferente de ter uma licença para a assinatura. Por padrão, todas as contas de usuário são **Permitidas**.


### [Console do administrador do Microsoft Intune](https://admin.manage.microsoft.com/)

**Como administrador de serviços, use este portal para gerenciar as tarefas do dia a dia**, incluindo:

- Definir políticas para computadores e dispositivos móveis.
- Carregar e implantar software, como atualizações de software e aplicativos.
- Gerenciar a Endpoint Protection do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] em computadores.
- Exibir status do dispositivo e executar relatórios.
- Entrar neste portal. Você deve ter permissões de administrador de serviços ou ser um administrador de locatários com a função de administrador global para entrar neste portal.


Apenas usuários com permissões de administrador de serviços ou administradores de locatários com a função de administrador global podem entrar nesse portal. Para acessar o console de administração, sua conta deve ter uma licença para usar o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] e um status de entrada de **Permitido**.

Saiba mais sobre como [adicionar usuários à sua assinatura](start-with-a-paid-subscription-to-microsoft-intune-step-3.md) e [atribuir licenças à sua assinatura](start-with-a-paid-subscription-to-microsoft-intune-step-4.md).

 ### Consulte também
 [O que saber antes de começar a usar o Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


