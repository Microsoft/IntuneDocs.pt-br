---
title: Integrar o Zimperium ao Intune
titleSuffix: Intune on Azure
description: Integrar o Intune ao Zimperium
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b4adb2db14c2e1c83be8e7b3644944c1910cb97
ms.sourcegitcommit: d434dfab7ef7a6c4082d675717fa22d5581b4f51
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2017
---
# <a name="integrate-zimperium-with-intune"></a>Integrar o Zimperium ao Intune

Você precisa seguir as etapas abaixo para integrar a solução Zimperium Mobile Threat Defense ao Intune.

## <a name="before-you-begin"></a>Antes de começar

> [!NOTE]
> As etapas abaixo precisam ser realizadas no [console do Zimperium MTD](https://staging2-console.zimperium.com).

Antes de iniciar o processo de integração do Zimperium ao Intune, verifique se você tem o seguinte:

-   Assinatura do Microsoft Intune

-   Credenciais de administrador do Azure Active Directory para conceder as seguintes permissões:

    -   Entrada e leitura de perfil do usuário

    -   Acessar diretório como o usuário conectado

    -   Ler dados do diretório

    -   Enviar informações do dispositivo para o Intune

-   Credenciais de administrador para acessar o console do Zimperium MTD.

### <a name="zimperium-app-authorization"></a>Autorização do aplicativo Zimperium

O processo de autorização do aplicativo Zimperium consiste no seguinte:

-   Permitir que o serviço do Zimperium comunique informações relacionadas ao estado de integridade do dispositivo de volta para o Intune.

-   Sincronizar o Zimperium com a associação ao Grupo de Registro do Azure AD para popular o banco de dados do dispositivo.

-   Permitir que o console do administrador do Zimperium use o SSO (logon único) do Azure AD.

-   Permitir que o aplicativo Zimperium conecte-se usando o SSO do Azure AD.

## <a name="to-set-up-zimperium-integration"></a>Para configurar a integração ao Zimperium

1.  Acesse o [console do Zimperium MTD](https://staging2-console.zimperium.com) e entre com suas credenciais.

2.  Escolha **Management** (Gerenciamento) no menu à esquerda.

3.  Escolha a guia **MDM settings** (Configurações de MDM).

4.  Escolha **Add MDM** (Adicionar MDM), selecione **Microsoft Intune** na lista **MDM provider** (Provedor de MDM).

5.  Depois de configurar o Microsoft Intune como o serviço de MDM, a janela **Microsoft Intune Configuration** (Configuração do Microsoft Intune) aparecerá, escolha **Add Azure Active Directory** (Adicionar Azure Active Directory) para cada opção: **Zimperium zConsole**, **zIPS iOS and Android apps** (Aplicativos zIPS iOS e Android ) para autorizar o Zimperium a comunicar-se com o Intune e com o Azure AD por meio do logon único do Azure AD.

    > [!IMPORTANT]
    > Você deve adicionar os aplicativos Zimperium zConsole, zIPS iOS e Android para concluir o processo de integração ao Intune.

6.  Escolha **Accept** (Aceitar) para autorizar o aplicativo Zimperium a comunicar-se com o Intune e com o Azure Active Directory.

7.  Após adicionar o **Zimperium zConsole** e os aplicativos **zIPS iOS e Android** ao Azure AD, será preciso adicionar os grupos de segurança do Azure AD para que o Zimperium possa sincronizar o grupo de segurança do Azure AD com seu serviço.

8.  Escolha **Finish** (Concluir) para salvar a configuração e iniciar a primeira sincronização do grupo de segurança do Azure AD.

## <a name="next-steps"></a>Próximas etapas

-   [Configurar os aplicativos do Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)