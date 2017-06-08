---
title: "Baixar política de configuração de aplicativo iOS do Skycure | Microsoft Docs"
description: "Baixe a política de configuração de aplicativo iOS do Skycure para usar com o aplicativo Skycure para iOS implantado para os usuários finais."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d211b876-4d3a-473c-999f-843c0a16cd22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a8e46960a5d469093052148eb457140b3c235d3a
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="download-skycure-ios-app-configuration-policy"></a>Baixar política de configuração de aplicativo iOS do Skycure

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

##<a name="before-you-begin"></a>Antes de começar

Você precisa fazer logon no Console de Gerenciamento do Skycure para executar as próximas etapas.

> [!TIP] 
> Se estiver usando o Microsoft Internet Explorer 11 ou o Edge, talvez seja necessário abrir o Console de gerenciamento do Skycure usando o modo privado.

## <a name="to-download-the-ios-app-configuration-policy"></a>Para baixar a política de configuração de aplicativo do iOS

1.  Acesse o [Console de Gerenciamento do Skycure](https://aad.skycure.com).

2.  Insira suas **credenciais de administrador do Skycure** e clique em **Continuar**.

    ![Logon no Console de Gerenciamento do Skycure](../media/mtp/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > O nome de usuário de administrador do Skycure é uma conta de email que deve ser uma conta de usuário válida no Azure Active Directory, caso contrário, o logon falhará. O Skycure usa o Azure Active Directory para autenticar seu nome de usuário de administrador usando SSO (Logon único).

3.  Acesse **Configurações** &gt; **Integrações de Gerenciamento de Dispositivo** &gt; **Seleção de Integração EMM**, escolha **Microsoft Intune** e salve sua seleção.

2.  Clique no link **Arquivos de configuração da integração** e salve o arquivo \*.zip gerado. O arquivo .zip contém o arquivo **skycure\_configuration.plist**, que será usado para criar a política de configuração de aplicativo do iOS no console clássico do Intune.

![Arquivos de configuração de integração do Skycure](../media/mtp/skycure-ios-app-2.png)

## <a name="next-steps"></a>Próximas etapas

[Adicionar aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)
