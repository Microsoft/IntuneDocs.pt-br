---
title: Integrar o MTD Zimperium com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Como configurar a solução de MTD (Defesa contra Ameaças Móveis) Zimperium com o Microsoft Intune para controlar o acesso de dispositivos móveis aos recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/04/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5ce1950c81a1327ede14fc5885eaf12f33614097
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59569669"
---
# <a name="integrate-zimperium-with-intune"></a>Integrar o Zimperium ao Intune

Execute as etapas a seguir para integrar a solução Zimperium Mobile Threat Defense ao Intune.

## <a name="before-you-begin"></a>Antes de começar

> [!NOTE]
> As etapas a seguir devem ser concluídas no  [console do Zimperium MTD](https://sso.zimperium.com/signon/aad/).

Antes de iniciar o processo de integração do Zimperium com o Intune, verifique se você tem a assinatura e as credenciais a seguir:

-   Assinatura do Microsoft Intune

-   Credenciais de administrador do Administrador Global do Azure Active Directory para conceder as seguintes permissões:

    -   Entrada e leitura de perfil do usuário

    -   Acessar diretório como o usuário conectado

    -   Ler dados do diretório

    -   Enviar informações do dispositivo para o Intune

-   Credenciais de administrador para acessar o console do Zimperium MTD.

### <a name="zimperium-app-authorization"></a>Autorização do aplicativo Zimperium

O processo de autorização de aplicativo Zimperium é o seguinte:

-   Conceda permissões para que o serviço do Zimperium comunique informações relacionadas ao estado de integridade do dispositivo de volta para o Intune. Para conceder essas permissões, você deve usar credenciais de Administrador Global. Conceder permissões é uma operação única. Depois que as permissões são concedidas, as credenciais de Administrador Global não são necessárias para a operação diária.

-   O Zimperium sincroniza-se com a associação do Grupo de Registro do Azure AD (Active Directory) para popular o banco de dados de dispositivos.

-   Permitir que o console do administrador do Zimperium use o SSO (logon único) do Azure AD.

-   Permitir que o aplicativo Zimperium conecte-se usando o SSO do Azure AD.

Para saber mais sobre o consentimento e os aplicativos do Azure Active Directory, confira [Solicitar as permissões de um administrador de diretório](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#request-the-permissions-from-a-directory-admin) no artigo do Azure Active Directory *Permissões e consentimento no ponto de extremidade do Azure Active Directory v2.0*.


## <a name="to-set-up-zimperium-integration"></a>Para configurar a integração ao Zimperium

1.  Acesse o [console do Zimperium MTD](https://sso.zimperium.com/signon/aad/) e entre com suas credenciais. Para executar o processo de instalação de integração do Zimperium, você deve entrar com um usuário do Azure Active Directory que tenha a função de Administrador Global. Essa operação de configuração única usa os direitos de Administrador Global para conceder permissão em sua organização para os aplicativos do Zimperium se comunicarem com o Intune. 

2.  Escolha **Management** (Gerenciamento) no menu à esquerda.

3.  Escolha a guia **MDM settings** (Configurações de MDM).

4.  Escolha **Add MDM** (Adicionar MDM), selecione **Microsoft Intune** na lista **MDM provider** (Provedor de MDM).

5.  Depois que você definir o Microsoft Intune como o serviço MDM, a janela **Configuração do Microsoft Intune** será exibida e você deverá escolher **Adicionar Azure Active Directory** para cada opção: aplicativos **Zimperium zConsole**, **zIPS iOS e Android** para autorizar o Zimperium para se comunicar com o Intune e o Azure AD por meio do logon único do Azure AD.

    > [!IMPORTANT]  
    > Você deve adicionar os aplicativos Zimperium zConsole, zIPS iOS e Android para concluir o processo de integração ao Intune.

6.  Escolha **Accept** (Aceitar) para autorizar o aplicativo Zimperium a comunicar-se com o Intune e com o Azure Active Directory.

7.  Após adicionar o **Zimperium zConsole** e os aplicativos **zIPS iOS e Android** ao Azure AD, adicione os grupos de segurança do Azure AD. Essa adição permite a sincronização do grupo de segurança do Azure AD com o serviço do Zimperium.

8.  Escolha **Finish** (Concluir) para salvar a configuração e iniciar a primeira sincronização do grupo de segurança do Azure AD.

9.  Saia do console do Zimperium MTD.

## <a name="next-steps"></a>Próximas etapas

-   [Configurar os aplicativos do Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
