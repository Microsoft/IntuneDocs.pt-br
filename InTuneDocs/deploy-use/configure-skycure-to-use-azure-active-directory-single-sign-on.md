---
title: "Configurar o Skycure para usar o Logon único do Azure Active Directory | Microsoft Docs"
description: "Configurar o Skycure para usar o SSO (Logon único) do Azure Active Directory"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 34d5d359-5c7c-4225-a205-8ce890b6f890
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: 228cecad4dc459e18d10e95253118943197bc55d
ms.lasthandoff: 03/22/2017


---

# <a name="configure-skycure-to-use-azure-active-directory-single-sign-on-sso"></a>Configurar o Skycure para usar o SSO (Logon único) do Azure Active Directory

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O SSO do Azure AD é usado quando você integra o Intune com o Skycure. Estes são os principais benefícios:

-   **Administradores** podem usar as mesmas credenciais sem precisar digitá-las novamente sempre que fizerem logon e saírem do Console de gerenciamento do Skycure e dos portais da Microsoft (Intune, Azure).

-   **Os usuários finais** podem usar as mesmas credenciais do Azure AD sem precisar digitá-las novamente sempre que fizerem logon e saírem dos aplicativos do Skycure.

Veja abaixo as etapas para integrar o Skycure ao SSO (Logon único) do Azure Active Directory.

## <a name="to-retrieve-the-azure-active-directory-tenant-id"></a>Para recuperar a ID de locatário do Azure Active Directory

Você precisa recuperar a ID de locatário do Azure AD.

1.  Acesse o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais.

2.  No **Painel,** escolha **Azure Active Directory**.

![Painel do Azure AD](../media/mtp/skycure-sso-1.png)

1.  Na folha **Azure Active Directory** exibida, escolha **Propriedades**.

![Folha Propriedades do Azure AD](../media/mtp/skycure-sso-2.png)

1.  Clique no **ícone Copiar** sob a **ID de Diretório do Locatário** na folha **Propriedades do Azure Active Directory**.

> Cole o valor da ID de Diretório copiado em um arquivo de texto para usá-lo mais tarde. O valor da ID de Diretório será solicitado posteriormente no processo de integração do Skycure e do Intune.

![Painel do Azure AD](../media/mtp/skycure-sso-3.png)

## <a name="allow-skycure-to-communicate-with-azure-active-directory"></a>Permitir a comunicação do Skycure com o Azure Active Directory

1.  Insira a URL abaixo no navegador. Em vez de **DIRECTORY_ID**, insira sua ID de Locatário do Azure Active Directory copiada anteriormente no arquivo de texto.

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  Você precisa fazer logon usando suas credenciais do Azure Active Directory. Clique em **Aceitar** para continuar.

![Página de logon do Azure AD](../media/mtp/skycure-sso-4.png)

## <a name="create-an-azure-ad-security-group-for-skycure-optional"></a>Criar um grupo de Segurança do Azure AD para Skycure (opcional)

Talvez você queira criar um grupo de usuários dedicado que contêm usuários executando o Skycure (por exemplo, usuários do Skycure). Isso pode ser útil ao analisar a atividade do Skycure por meio dos relatórios.

-   Saiba mais sobre [como criar um grupo e adicionar membros no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).

> [!NOTE] 
> Você também pode usar um grupo de segurança existente do Azure AD.

## <a name="configure-the-azure-ad-account-to-integrate-intune-with-skycure"></a>Configurar a conta do Azure AD para integrar o Intune ao Skycure

1.  No [Console de Gerenciamento do Skycure](https://aad.skycure.com/), insira a ID do Locatário do Azure Active Directory salva anteriormente no arquivo de texto.

![Campo ID de Locatário do Azure AD no Console de Gerenciamento do Skycure](../media/mtp/skycure-sso-5.png)

> [!IMPORTANT] 
> O Skycure valida se a ID de Locatário do Azure AD existe consultando o Azure AD. Após o Skycure encontrá-la, o administrador poderá prosseguir para a próxima etapa, que é a configuração Básica.

## <a name="next-steps"></a>Próximas etapas

[Baixar política de configuração de aplicativo iOS do Skycure](https://docs.microsoft.com/intune/deploy-use/download-skycure-ios-app-configuration-policy)

