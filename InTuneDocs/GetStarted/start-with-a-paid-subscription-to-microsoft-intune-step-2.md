---
title: "Configurar um nome de domínio personalizado | Microsoft Intune"
description: "Descreve o processo de adicionar um nome de domínio personalizado para sua assinatura do Intune"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bf2122afc7f86d81b9d072147b19f75be2a55b51
ms.openlocfilehash: 63c0b3340a6f69e20c85abf7947c25ce88f5d826


---


# Configurar um nome de domínio personalizado

Por padrão, o Intune usa o nome de domínio **<domain>.onmicrosoft.com** que foi criado quando você assinou pela primeira vez o serviço. Quando a sua organização tem um domínio personalizado, é possível configurar a sua instância do Intune para usar esse domínio em vez do nome de domínio fornecido com a sua assinatura.

Antes de criar novas contas de usuário ou sincronizar contas por meio do seu Active Directory local, recomendamos fortemente que você decida se usará somente o domínio .onmicrosoft.com ou se adicionará um ou mais nomes de domínios personalizados. Configurar um domínio personalizado antes de adicionar usuários pode simplificar o gerenciamento das identidades de usuário para a sua assinatura, permitindo que os usuários entrem com as credenciais que usam para acessar outros recursos de domínio.

Ao assinar um serviço baseado em nuvem da Microsoft, sua instância desse serviço torna-se um [locatário do Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), que fornece serviços de identidade e diretório para o seu serviço baseado em nuvem. Como as tarefas para configurar o Intune para usar o nome de domínio personalizado das organizações são as mesmas para os outros locatários do Azure AD, use as informações e procedimentos encontrados em [Adicionar seu domínio](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Para obter mais informações sobre o uso do seu domínio personalizado com um serviço baseado em nuvem da Microsoft, consulte [Visão geral conceitual dos nomes de domínio personalizados no Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

### Próximas etapas
Parabéns! Você acabou de concluir a etapa 2 do *Guia de início rápido do Intune*.

>[!div class="step-by-step"]

>[&larr; **Entrar no Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Adicionar usuários ao Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  



<!--HONumber=Aug16_HO5-->


