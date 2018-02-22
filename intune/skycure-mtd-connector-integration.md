---
title: "Configurar a integração do Skycure com o Intune"
titlesuffix: Azure portal
description: "Configure a integração do Skycure com o Microsoft Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 12/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: beaf027334ce4929e4ca824b2b7e199cea22a832
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2018
---
# <a name="set-up-the-skycure-integration-with-intune"></a>Configurar a integração do Skycure com o Intune

Você precisa adicionar os aplicativos Skycure ao Azure AD com a funcionalidade de Logon único.

## <a name="before-you-begin"></a>Antes de começar

### <a name="azure-ad-account-used-to-integrate-intune-and-skycure"></a>Conta do Azure AD usada para integrar o Intune e o Skycure

-   Configure corretamente a conta do Azure AD no [Console de Gerenciamento do Skycure](https://aad.skycure.com), antes de começar o processo de configuração do Skycure Basic.

### <a name="full-integration-vs-read-only"></a>Integração total versus Somente leitura.

O Skycure dá suporte a dois modos de integração com o Intune:

-   **Integração somente leitura (configuração Básica):** Somente faz o inventário de dispositivos do Azure Active Directory e os preenche no console do Skycure.
<br>
    -   Se as caixas **Relatar a integridade e o risco de dispositivos ao Intune** e **Relatar também incidentes de segurança ao Intune** não estiverem marcadas no Console de Gerenciamento do Skycure, a integração será somente leitura e, portanto, nunca alterará o estado de um dispositivo (compatível ou não compatível) no Intune.
<br></br>
-   **Integração total:** permite que o Skycure reporte dispositivos com detalhes de incidente de risco e segurança ao Intune, que cria uma comunicação bidirecional entre os dois serviços em nuvem.

### <a name="how-the-skycure-apps-are-used-with-azure-ad-and-intune"></a>Como os aplicativos Skycure são usados com o Azure AD e o Intune?

-   **Aplicativo iOS:** permite que os usuários finais entrem no Azure AD usando um aplicativo iOS.

-   **Aplicativo Android:** permite que os usuários finais entrem no Azure AD usando um aplicativo Android.

-   **Aplicativo de gerenciamento:** este é o aplicativo multilocatário do Skycure Azure AD que permite a comunicação entre serviços com o Intune.

## <a name="to-set-up-the-read-only-integration-between-intune-and-skycure"></a>Para configurar a integração somente leitura entre o Intune e o Skycure

> [!IMPORTANT]
> As credenciais de administrador do Skycure são um email que deve pertencer a um usuário válido no Azure Active Directory, caso contrário, o logon falhará. O Skycure usa o Azure Active Directory para autenticar seu administrador usando SSO (Logon único).

1.  Acesse o [Console de Gerenciamento do Skycure](https://aad.skycure.com).

2.  Insira suas **credenciais de administrador do Skycure** e clique em **Continuar**.

3.  Acesse **Configurações**, escolha **Configuração Básica** em **Integração com o Intune**.

4.  No rótulo **Aplicativo iOS**, clique em **Adicionar ao Active Directory**.

    ![Aplicativo iOS no Console de Gerenciamento do Skycure](./media/skycure-setup-1.png)

5.  Na página de logon aberta, insira suas credenciais do Intune e clique em **Aceitar**.

    ![Aviso de logon do Intune no aplicativo iOS](./media/skycure-setup-2.png)

6.  Após a adição do aplicativo ao Azure AD, você pode ver uma indicação de que o aplicativo foi adicionado com êxito ao Azure AD no Console de Gerenciamento do Skycure.

    ![tela de conclusão de aplicativo do iOS](./media/skycure-setup-3.png)

> [!NOTE]
> Repita o mesmo processo para os aplicativos **Skycure Android** e **Gerenciamento**.

### <a name="add-an-azure-ad-security-group-into-skycure"></a>Adicionar um grupo de segurança do Azure AD ao Skycure

Você precisa adicionar um grupo de segurança do Azure AD que contém todos os dispositivos que executam o Skycure.

1.  Insira e selecione todos os grupos de segurança de dispositivos que estão executando o Skycure e clique em **Aplicar alterações**.

    ![Configurar o Console de Gerenciamento do Skycure no grupo de segurança](./media/skycure-setup-4.png)

O Skycure sincroniza os dispositivos que executam seu serviço de Defesa contra Ameaças Móveis com os grupos de segurança do Azure AD.

![Configuração do grupo de segurança concluída no Console de Gerenciamento do Skycure](./media/skycure-setup-5.png)

## <a name="set-up-the-full-integration-between-intune-and-skycure"></a>Configurar a integração total entre o Intune e o Skycure

1.  Acesse o [Console de Gerenciamento do Skycure](https://aad.skycure.com).

2.  Insira suas **credenciais de administrador do Skycure** e clique em **Continuar**.

3.  Acesse **Configurações**, escolha **Integração Total** em **Integração com o Intune**.

4.  Verifique as seguintes configurações:

    a.  Relatar a integridade e o risco do dispositivo ao Intune

    b.  Relatar também incidentes de segurança ao Intune

5.  Clique em **Aplicar Alterações**.

    ![Integração completa do Skycure concluída](./media/skycure-setup-6.png)

## <a name="next-steps"></a>Próximas etapas

[Configurar os aplicativos do Skycure](mtd-apps-ios-app-configuration-policy-add-assign.md)
