---
title: Integrar o Zimperium ao Intune
titleSuffix: Intune on Azure
description: Integrar o Intune ao Zimperium
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 515f99f694a9125d60bb9210becc6722bfb9e24f
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/30/2017
---
# <a name="integrate-zimperium-with-intune"></a>Integrar o Zimperium ao Intune

Execute as etapas a seguir para integrar a solução Zimperium Mobile Threat Defense ao Intune.

## <a name="before-you-begin"></a>Antes de começar

> [!NOTE]
> As etapas a seguir devem ser concluídas no [console do Zimperium MTD](https://staging2-console.zimperium.com).

Antes de iniciar o processo de integração do Zimperium ao Intune, verifique se você tem o seguinte:

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

-   Sincronizar o Zimperium com a associação ao Grupo de Registro do Azure AD para popular o banco de dados do dispositivo.

-   Permitir que o console do administrador do Zimperium use o SSO (logon único) do Azure AD.

-   Permitir que o aplicativo Zimperium conecte-se usando o SSO do Azure AD.

## <a name="to-set-up-zimperium-integration"></a>Para configurar a integração ao Zimperium

1.  Acesse o [console do Zimperium MTD](https://staging2-console.zimperium.com) e entre com suas credenciais.

2.  Escolha **Management** (Gerenciamento) no menu à esquerda.

3.  Escolha a guia **MDM settings** (Configurações de MDM).

4.  Escolha **Add MDM** (Adicionar MDM), selecione **Microsoft Intune** na lista **MDM provider** (Provedor de MDM).

5.  Depois de configurar o Microsoft Intune como o serviço de MDM, a janela **Microsoft Intune Configuration** (Configuração do Microsoft Intune) aparecerá, escolha **Add Azure Active Directory** (Adicionar Azure Active Directory) para cada opção: **Zimperium zConsole**, **aplicativos zIPS iOS e Android** para autorizar o Zimperium a comunicar-se com o Intune e com o Azure AD por meio do logon único do Azure AD.

    > [!IMPORTANT]
    > Você deve adicionar os aplicativos Zimperium zConsole, zIPS iOS e Android para concluir o processo de integração ao Intune.

6.  Escolha **Accept** (Aceitar) para autorizar o aplicativo Zimperium a comunicar-se com o Intune e com o Azure Active Directory.

7.  Após adicionar o **Zimperium zConsole** e os aplicativos **zIPS iOS e Android** ao Azure AD, adicione os grupos de segurança do Azure AD para que o Zimperium possa sincronizar o grupo de segurança do Azure AD com seu serviço.

8.  Escolha **Finish** (Concluir) para salvar a configuração e iniciar a primeira sincronização do grupo de segurança do Azure AD.

## <a name="next-steps"></a>Próximas etapas

-   [Configurar os aplicativos do Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
