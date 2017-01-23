---
title: "Configurar um nome de domínio personalizado | Microsoft Docs"
description: "Adicionar um nome de domínio personalizado para sua assinatura do Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d05c9d7a78474c19e142bca94e232289fbfba1d9
ms.openlocfilehash: e51746bbd114476e394c44f813fb8cb329879172


---


# <a name="configure-a-custom-domain-name"></a>Configurar um nome de domínio personalizado

[!INCLUDE[classic-portal](../includes/classic-portal.md)]


Quando sua empresa se inscreve em um serviço baseado em nuvem da Microsoft como o Intune, você recebe um nome de domínio inicial hospedado no Azure Active Directory (AD), que é semelhante ao seguinte: **yourdomain.onmicrosoft.com**. Nesse exemplo, **yourdomain** é o nome de domínio que você escolheu quando se inscreveu, e **onmicrosoft.com** é o sufixo atribuído às contas que você adicionar à sua assinatura. Quando a sua organização tem um domínio personalizado, é possível configurar a sua instância do Intune para usar esse domínio em vez do nome de domínio fornecido com a sua assinatura.

Antes de criar contas de usuário ou sincronizar seu Active Directory local, recomendamos fortemente que você decida se usará somente o domínio .onmicrosoft.com ou se adicionará um ou mais nomes de domínios personalizados. Configurar um domínio personalizado antes de adicionar usuários pode simplificar o gerenciamento das identidades de usuário para a sua assinatura, permitindo que os usuários entrem com as credenciais que usam para acessar outros recursos de domínio.

Ao assinar um serviço baseado em nuvem da Microsoft, sua instância desse serviço torna-se um [locatário do Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), que fornece serviços de identidade e diretório para o seu serviço baseado em nuvem. Como as tarefas para configurar o Intune para usar o nome de domínio personalizado das organizações são as mesmas para os outros locatários do Azure AD, use as informações e procedimentos encontrados em [Adicionar seu domínio](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Para obter mais informações sobre o uso do seu domínio personalizado com um serviço baseado em nuvem da Microsoft, consulte [Visão geral conceitual dos nomes de domínio personalizados no Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

Você não pode renomear ou remover esse nome de domínio inicial. No entanto, você pode adicionar, verificar ou remover seus próprios nomes de domínio personalizado para usar com o Intune, que é útil caso você queira manter sua identidade de negócios.

## <a name="to-add-and-verify-your-custom-domain"></a>Para adicionar e verificar seu domínio personalizado

1. Vá para [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx) e entre em sua conta de administrador.

2. No painel de navegação, escolha **Configurações** &gt; **Domínios**.

3. Escolha **Adicionar domínio** e digite o nome de domínio personalizado.

4. A caixa de diálogo **Verificar domínio** é aberta, fornecendo os valores para criar o registro TXT no seu provedor de hospedagem de DNS.
    - **Usuários do GoDaddy**: o Portal de gerenciamento do Office 365 redireciona você para a página de logon do GoDaddy. Após inserir suas credenciais e aceitar o contrato de permissão de alteração de domínio, o registro TXT é criado automaticamente. Como alternativa, [crie o registro TXT](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US).
    - **Usuários do Register.com**: siga as [instruções passo a passo](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify) para criar o registro TXT.

    > [!TIP]
    > Certifique-se de criar um alias DNS (CNAME) para o [registro de dispositivos Windows](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune), enquanto faz alterações no seu provedor de hospedagem de DNS.

As etapas para adicionar e verificar um domínio personalizado também podem ser [executadas no Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

É possível saber mais [Sobre o domínio inicial onmicrosoft.com no Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

>[!div class="step-by-step"]

>[&larr; **Entrar no Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Adicionar usuários ao Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  



<!--HONumber=Jan17_HO2-->


