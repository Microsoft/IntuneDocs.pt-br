---
title: Integrar o MTD Zimperium com o Microsoft Intune
titleSuffix: ''
description: Como configurar a solução de MTD (Defesa contra Ameaças Móveis) Zimperium com o Microsoft Intune para controlar o acesso de dispositivos móveis aos recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 68896a363cab37aabe9a597872da0fe75c44c473
ms.sourcegitcommit: 3903f20cb5686532ccd8c36aa43c5150cee7cca2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2018
ms.locfileid: "52267230"
---
# <a name="integrate-zimperium-with-intune"></a>Integrar o Zimperium ao Intune

Execute as etapas a seguir para integrar a solução Zimperium Mobile Threat Defense ao Intune.

## <a name="before-you-begin"></a>Antes de começar

> [!NOTE]
> As etapas a seguir devem ser concluídas no  [console do Zimperium MTD](https://sso.zimperium.com/signon/aad/).

Antes de iniciar o processo de integração do Zimperium com o Intune, verifique se você tem a assinatura e as credenciais a seguir:

-   Assinatura do Microsoft Intune

-   Credenciais de administrador do Azure Active Directory para conceder as seguintes permissões:

    -   Entrada e leitura de perfil do usuário

    -   Acessar diretório como o usuário conectado

    -   Ler dados do diretório

    -   Enviar informações do dispositivo para o Intune

-   Credenciais de administrador para acessar o console do Zimperium MTD.

### <a name="zimperium-app-authorization"></a>Autorização do aplicativo Zimperium

O processo de autorização de aplicativo Zimperium é o seguinte:

-   Permitir que o serviço do Zimperium comunique informações relacionadas ao estado de integridade do dispositivo de volta para o Intune.

-   O Zimperium sincroniza-se com a associação do Grupo de Registro do Azure AD (Active Directory) para popular o banco de dados de dispositivos.

-   Permitir que o console do administrador do Zimperium use o SSO (logon único) do Azure AD.

-   Permitir que o aplicativo Zimperium conecte-se usando o SSO do Azure AD.

## <a name="to-set-up-zimperium-integration"></a>Para configurar a integração ao Zimperium

1.  Acesse o  [console do Zimperium MTD](https://sso.zimperium.com/signon/aad/)  e entre com suas credenciais.

2.  Escolha **Management** (Gerenciamento) no menu à esquerda.

3.  Escolha a guia **MDM settings** (Configurações de MDM).

4.  Escolha **Add MDM** (Adicionar MDM), selecione **Microsoft Intune** na lista **MDM provider** (Provedor de MDM).

5.  Depois de configurar o Microsoft Intune como o serviço de MDM, a janela  **Configuração do Microsoft Intune**  aparecerá, escolha  **Adicionar Azure Active Directory**  para cada opção: **Zimperium zConsole**, **Aplicativos zIPS iOS e Android** para autorizar o Zimperium a comunicar-se com o Intune e com o Azure AD por meio do logon único do Azure AD.

    > [!IMPORTANT]
    > Você deve adicionar os aplicativos Zimperium zConsole, zIPS iOS e Android para concluir o processo de integração ao Intune.

6.  Escolha  **Aceitar**  para autorizar o aplicativo Zimperium a comunicar-se com o Intune e com o Azure Active Directory.

7.  Após adicionar o **Zimperium zConsole** e os aplicativos **zIPS iOS e Android** ao Azure AD, adicione os grupos de segurança do Azure AD. Essa adição permite a sincronização do grupo de segurança do Azure AD com o serviço do Zimperium.

8.  Escolha  **Concluir** para salvar a configuração e iniciar a primeira sincronização do grupo de segurança do Azure AD.

## <a name="next-steps"></a>Próximas etapas

-   [Configurar os aplicativos do Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
