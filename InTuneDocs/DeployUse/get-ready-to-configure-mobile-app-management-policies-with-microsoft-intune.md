---
# required metadata

title: Preparar-se para configurar políticas de gerenciamento de aplicativos móveis | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Preparar-se para configurar as políticas de gerenciamento de aplicativos móveis com o Microsoft Intune
Este tópico descreve o que você precisa fazer para começar a criar políticas de MAM (Gerenciamento de Aplicativo Móvel) no Portal do Azure.
Se no momento você estiver usando o **console de administração do Intune** para gerenciar seus dispositivos, poderá criar uma política de MAM que dê suporte a aplicativos para dispositivos registrados no Intune usando o [console de administração do Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).
>[!IMPORTANT]
> Você não poderá ver todas as configurações de política de MAM no console de administração do Intune. O portal do Azure é o novo console de administração para criar políticas de MAM.

##  Plataformas com suporte
- iOS 8.1 ou posterior

- Android 4 ou posterior

##  Aplicativos com suporte
Para ver a lista completa de aplicativos com suporte, vá para a [Galeria de aplicativos móveis do Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) na página de parceiros de aplicativos do Microsoft Intune.
Clique no aplicativo para ver os cenários e plataformas com suporte e se o aplicativo dá suporte várias identidades.

**Antes** de configurar políticas de MAM, você precisará do seguinte:

-   **Uma assinatura do Microsoft Intune**.    Os usuários finais precisam de licenças do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] para obter aplicativos com políticas de MAM.

-   A **autoridade de gerenciamento de dispositivo móvel** deverá ser definida como o **Intune** ou **Configuration manager**, caso você esteja usando apenas o Intune ou o Configuration Manager integrado com o Intune para gerenciar dispositivos. Se você estiver usando o gerenciamento de dispositivo móvel interno do O365, deverá adquirir uma assinatura do Intune e [definir a autoridade de gerenciamento de dispositivos móveis como Intune](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority).
-   Uma assinatura do **Office 365 (O365)** é necessária para o seguinte:
  - Para aplicar políticas de MAM a aplicativos com suporte a várias identidade.
  - Para criar contas corporativas do SharePoint Online e Exchange Online. Não há suporte para o Exchange e SharePoint local.


- **Azure Active Directory (Azure AD)** para criar usuários. O Azure AD autentica o usuário quando o usuário final inicia o aplicativo e insere suas credenciais de trabalho.

    > [!NOTE]
    > Se você estiver configurando usuários usando o console do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], lembre-se de que a configuração da política de MAM migrará para o Portal do Azure no futuro e, para usar esse portal, você terá de configurar grupos de usuários do Azure AD usando o portal do Office 365.


## Criar usuários e atribuir licenças do Microsoft Intune

1. Você precisa de uma assinatura do Intune: você já terá uma assinatura do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] se estiver usando o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] para gerenciar dispositivos.  Você também terá uma assinatura do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] se tiver adquirido uma licença do EMS. Se estiver experimentando o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] para conferir os recursos de MAM, poderá obter uma conta de avaliação [aqui](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/).

    Para verificar se você tem uma assinatura do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], no portal do Office, vá para a página de Cobrança.  Você deve ver [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] como **Ativo** em assinaturas.

2.  Entre no   [portal do Office](http://portal.office.com) com suas credenciais de administrador.

3.  Navegue até a página **Usuários Ativos** para adicionar usuários e atribuir licenças [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Página Adicionar usuários do Portal do Office](../media/AppManagement/OfficePortal_AddUsers.png)

4.  Para conceder a um usuário a capacidade de acessar o portal do Office, o portal do Azure AD e o portal do Azure, atribua a **função de Administrador Global** ao usuário.

    ![Captura de tela do portal do office mostrando a página Usuários Ativos ](../media/AppManagement/OfficePortal_AddRoletoUser.png)

5.  Políticas de MAM são implantadas para grupos de usuários no Active Directory do Azure. Para criar grupos de usuários que você deseja usar para as políticas de MAM, navegue até a página **Grupos** no **portal do Office** e clique no ícone **+** para criar um novo grupo de segurança.  Digite um nome, uma descrição e clique em **Criar**. Quando o grupo é criado, você pode adicionar o usuário ao grupo clicando em **Editar membros** no grupo de segurança recém-criado. O grupo de segurança é criado no Active Directory do Azure.

    ![Captura de tela da página mostrando seleção de função de administrador global na página Editar funções de usuário](../media/AppManagement/OfficePortal_CreateGroups.png)

A tabela a seguir lista a função e as permissões que você pode atribuir a usuários administrativos.

|||
|--|----|
|**Função**|**Permissões**|
|Administrador global (portal do O365)|Acesso ao portal do O365 e ao portal do Azure AD<br /><br />Acesso ao portal do Azure (pode realizar tarefas de gerenciamento de função e de aplicativo móvel).|
|Função de proprietário (portal do Azure)|Acesso ao portal do Azure (pode realizar tarefas de gerenciamento de função e de aplicativo móvel).|
|Função de contribuinte (portal do Azure)|Acesso ao portal do Azure (pode realizar apenas tarefas de gerenciamento de aplicativo móvel).|

## Atribuir a função de colaborador a um usuário

**Administradores globais** têm acesso ao Portal do Azure.  Se desejar que outros usuários administradores possam configurar políticas e realizar outras tarefas de gerenciamento de aplicativos móveis, você pode atribuir a **função de Colaborador** ao usuário conforme descrito a seguir:


1.  Na folha **Configurações** da seção **Gerenciamento de recursos**, clique em **Usuários**.

    ![Captura de tela da folha Usuários no portal do Azure](../media/AppManagement/AzurePortal_MAM_AddUsers.png)

2.  Clique em **Adicionar** para abrir a folha **Adicionar acesso** .

3.  Clique em **Selecionar uma função** e em **Função Colaborador**.

    ![Captura de tela da folha Selecionar uma função no portal do Azure](../media/AppManagement/AzurePortal_MAM_AddRole.png)

4.  Depois que você tiver selecionado a função, clique em **Adicionar usuário**e procure o usuário pelo nome de usuário ou endereço de email. Os usuários que você vê nessa lista são os primeiros 1.000 usuários criados previamente no AD do Azure usando o Portal do Office. Clique em **Ok** na folha **Adicionar acesso** para salvar e atribuir a função ao usuário.

    ![Captura de tela da folha Adicionar usuários no portal do Azure](../media/AppManagement/AzurePortal_MAM_AddusertoRole.png)

    > [!IMPORTANT]
    > Se você selecionar um usuário que não tem uma licença [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] atribuída, ele não poderá acessar o portal.

## Próximas etapas
[Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


