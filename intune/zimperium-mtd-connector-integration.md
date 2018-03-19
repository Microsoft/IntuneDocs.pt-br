---
title: Integrar o MTD Zimperium com o Microsoft Intune
titleSuffix: 
description: "Como configurar a solução de MTD (Defesa contra Ameaças Móveis) Zimperium com o Microsoft Intune para controlar o acesso de dispositivos móveis aos recursos corporativos."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fada315aad9bce47a3a04286d84e1c7dbdd2ce61
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="integrate-zimperium-with-intune"></a>Integrar o Zimperium ao Intune

Execute as etapas a seguir para integrar a solução Zimperium Mobile Threat Defense ao Intune.

## <a name="before-you-begin"></a>Antes de começar

> [!NOTE]
> As etapas a seguir devem ser concluídas no [console do Zimperium MTD](https://staging2-console.zimperium.com).

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

1.  Acesse o [console do Zimperium MTD](https://staging2-console.zimperium.com) e entre com suas credenciais.

2.  Escolha **Management** (Gerenciamento) no menu à esquerda.

3.  Escolha a guia **MDM settings** (Configurações de MDM).

4.  Escolha **Add MDM** (Adicionar MDM), selecione **Microsoft Intune** na lista **MDM provider** (Provedor de MDM).

5.  Depois de configurar o Microsoft Intune como o serviço de MDM, a janela **Microsoft Intune Configuration** (Configuração do Microsoft Intune) aparecerá, escolha **Add Azure Active Directory** (Adicionar Azure Active Directory) para cada opção: **Zimperium zConsole**, **aplicativos zIPS iOS e Android** para autorizar o Zimperium a comunicar-se com o Intune e com o Azure AD por meio do logon único do Azure AD.

    > [!IMPORTANT]
    > Você deve adicionar os aplicativos Zimperium zConsole, zIPS iOS e Android para concluir o processo de integração ao Intune.

6.  Escolha **Accept** (Aceitar) para autorizar o aplicativo Zimperium a comunicar-se com o Intune e com o Azure Active Directory.

7.  Após adicionar o **Zimperium zConsole** e os aplicativos **zIPS iOS e Android** ao Azure AD, adicione os grupos de segurança do Azure AD. Essa adição permite a sincronização do grupo de segurança do Azure AD com o serviço do Zimperium.

8.  Escolha **Finish** (Concluir) para salvar a configuração e iniciar a primeira sincronização do grupo de segurança do Azure AD.

## <a name="next-steps"></a>Próximas etapas

-   [Configurar os aplicativos do Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
