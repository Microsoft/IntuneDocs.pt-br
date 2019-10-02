---
title: Configurar um nome de domínio personalizado
titleSuffix: Microsoft Intune
description: Adicionar um nome de domínio personalizado para sua assinatura do Microsoft Intune
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: b1087082400b321c07ea5993ca0280bf0ce455b1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726083"
---
# <a name="configure-a-custom-domain-name"></a>Configurar um nome de domínio personalizado

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Este tópico informa os administradores como eles podem criar um DNS CNAME para simplificar e personalizar sua experiência de logon usando o Microsoft Intune.

Quando sua empresa se inscreve em um serviço baseado em nuvem da Microsoft como o Intune, você recebe um nome de domínio inicial hospedado no Azure Active Directory (AD), que é semelhante a **seudomínio.onmicrosoft.com**. Nesse exemplo, **seudomínio** é o nome de domínio que você escolheu ao se inscrever. **onmicrosoft.com** é o sufixo atribuído às contas que você adiciona à sua assinatura. Você pode configurar o domínio personalizado da organização para acessar o Intune, em vez de usar o nome de domínio fornecido com a sua assinatura.

Antes de criar contas de usuário ou sincronizar seu Active Directory local, recomendamos fortemente que você decida se usará somente o domínio .onmicrosoft.com ou se adicionará um ou mais nomes de domínios personalizados. Configure um domínio personalizado antes de adicionar usuários para simplificar o gerenciamento de usuários. A configuração de um domínio do cliente permite que os usuários entrem com as credenciais usadas para acessar outros recursos do domínio.

Ao assinar um serviço baseado em nuvem da Microsoft, sua instância desse serviço torna-se um [locatário do Microsoft Azure AD](https://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), que fornece serviços de identidade e diretório para o seu serviço baseado em nuvem. Como as tarefas para configurar o Intune para usar o nome de domínio personalizado das organizações são as mesmas para os outros locatários do Azure AD, use as informações e procedimentos encontrados em [Adicionar seu domínio](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Para saber mais sobre os domínios personalizados, consulte [Visão geral conceitual dos nomes de domínio personalizados no Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

Você não pode renomear nem remover o nome de domínio inicial onmicrosoft.com. Você pode adicionar, verificar ou remover os nomes de domínio personalizados usados com o Intune para manter sua identidade de empresa limpa.

## <a name="to-add-and-verify-your-custom-domain"></a>Para adicionar e verificar seu domínio personalizado

1. Acesse o [Centro de administração do Microsoft 365](https://admin.microsoft.com/) e entre em sua conta de administrador.

2. No painel de navegação, escolha **Configuração** &gt; **Domínios**.

3. Escolha **Adicionar domínio** e digite o nome de domínio personalizado. Selecione **Avançar**.
   ![Captura de tela do Centro de administração do Microsoft 365 com a opção Configurações > Domínios selecionada e um novo nome de domínio sendo adicionado](./media/custom-domain-name-configure/domain-custom-add.png)
4. A caixa de diálogo **Verificar domínio** é aberta, fornecendo os valores para criar o registro TXT no seu provedor de hospedagem de DNS.
    - **Usuários da GoDaddy**: o Centro de administração do Microsoft 365 redireciona você à página de logon da GoDaddy. Após inserir suas credenciais e aceitar o contrato de permissão de alteração de domínio, o registro TXT é criado automaticamente. Como alternativa, [crie o registro TXT](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).
    - **Usuários do Register.com**: siga as [instruções passo a passo](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) para criar o registro TXT.
5. [Talvez seja necessário criar registros DNS adicionais para registros no Intune](../enrollment/windows-enroll.md#simplify-windows-enrollment-without-azure-ad-premium).

As etapas para adicionar e verificar um domínio personalizado também podem ser [executadas no Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

É possível saber mais [Sobre o domínio inicial onmicrosoft.com no Office 365](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A)

Você pode aprender mais sobre como [simplificar o registro no Windows sem o Azure AD Premium](../enrollment/windows-enroll.md#simplify-windows-enrollment-without-azure-ad-premium), criando um DNS CNAME que redireciona o registro para os servidores do Intune.
