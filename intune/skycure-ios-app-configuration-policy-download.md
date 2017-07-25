---
title: "Baixar a política de configuração de aplicativo do iOS para Skycure a ser usada com o Intune"
titleSuffix: Intune on Azure
description: "Baixe a política de configuração de aplicativo do iOS para Skycure a ser usada com o Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1bdc2ecf-32d0-4b6a-80b4-dbcdb9909010
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ffe1027e90203d4e300a2446f15e72cc5bf53973
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Baixar política de configuração de aplicativo iOS do Skycure
<a id="download-skycure-ios-app-configuration-policy" class="xliff"></a>

## Antes de começar
<a id="before-you-begin" class="xliff"></a>

Você precisa fazer logon no Console de Gerenciamento do Skycure para executar as próximas etapas.

> [!TIP] 
> Se estiver usando o Microsoft Internet Explorer 11 ou o Edge, talvez seja necessário abrir o Console de gerenciamento do Skycure usando o modo privado.

## Para baixar a política de configuração de aplicativo do iOS
<a id="to-download-the-ios-app-configuration-policy" class="xliff"></a>

1.  Acesse o [Console de Gerenciamento do Skycure](https://aad.skycure.com).

2.  Insira suas **credenciais de administrador do Skycure** e clique em **Continuar**.

    ![Logon no Console de Gerenciamento do Skycure](./media/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > O nome de usuário de administrador do Skycure é uma conta de email que deve ser uma conta de usuário válida no Azure Active Directory, caso contrário, o logon falhará. O Skycure usa o Azure Active Directory para autenticar seu nome de usuário de administrador usando SSO (Logon único).

3.  Acesse **Configurações** &gt; **Integrações de Gerenciamento de Dispositivo** &gt; **Seleção de Integração EMM**, escolha **Microsoft Intune** e salve sua seleção.

4.  Clique no link **Arquivos de configuração da integração** e salve o arquivo \*.zip gerado. O arquivo .zip contém o arquivo **skycure\_configuration.plist**, que será usado para criar a política de configuração de aplicativo do iOS no console clássico do Intune.

![Arquivos de configuração de integração do Skycure](./media/skycure-ios-app-2.png)

## Próximas etapas
<a id="next-steps" class="xliff"></a>

[Adicionar e atribuir aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)
