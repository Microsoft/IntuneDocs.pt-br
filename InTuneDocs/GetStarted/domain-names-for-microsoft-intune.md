---
title: "Nomes de domínio do Microsoft Intune | Microsoft Intune"
description: "adicionar nome de domínio para o Intune"
keywords: 
author: andredm7
manager: swadhwa
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 32723f5b2c92073dda43a0b1f36a48ded0e13ba3
ms.openlocfilehash: 2adbe1e4a92af5302550a8b78069bc49d725dbc3


---



# Nomes de domínio personalizados com o Microsoft Intune

As etapas para adicionar e verificar um domínio personalizado também podem ser [executadas no Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

Quando sua empresa se inscreve em um serviço baseado em nuvem da Microsoft como o Intune, você recebe um nome de domínio inicial hospedado no Azure Active Directory que é semelhante ao seguinte: **yourdomain.onmicrosoft.com**. Nesse exemplo, **yourdomain** é o nome de domínio que você escolheu quando se inscreveu, e **onmicrosoft.com** é o sufixo atribuído às contas que você adicionar à sua assinatura.

Você não pode renomear ou remover esse nome de domínio inicial. No entanto, você pode adicionar, verificar ou remover seus próprios nomes de domínio personalizado para usar com o Intune, que é útil caso você queira manter sua identidade de negócios.

## Para adicionar e verificar seu domínio personalizado 

1. Vá para [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx) e entre em sua conta de administrador.
    > [!IMPORTANT]
    > Verifique o comunicado     [Portal de Conta do Intune foi mesclado com o portal de gerenciamento do Office 365](https://docs.microsoft.com/en-us/intune/deploy-use/account-portal-merged-with-Office-365) para obter mais detalhes sobre onde gerenciar usuários, grupos e domínios do Microsoft Intune.
2. No painel de navegação, escolha **Configurações** &gt; **Domínios**.
3. Escolha **Adicionar domínio** e digite o nome de domínio personalizado.
4. A caixa de diálogo **Verificar domínio** é aberta, fornecendo os valores para criar o registro TXT no seu provedor de hospedagem de DNS.
    - **Usuários do GoDaddy**: o Portal de gerenciamento do Office 365 redireciona você para a página de logon do GoDaddy. Após inserir suas credenciais e aceitar o contrato de permissão de alteração de domínio, o registro TXT é criado automaticamente. Como alternativa, [crie o registro TXT](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US).
    - **Usuários do Register.com**: siga as [instruções passo a passo](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify) para criar o registro TXT.

    > [!TIP] 
    > Certifique-se de criar um alias DNS (CNAME) para o [registro de dispositivos Windows](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune), enquanto faz alterações no seu provedor de hospedagem de DNS.

Em um cenário de nuvem híbrida, depois que você adicionou seu nome de domínio personalizado e foi verificado que sua organização o possui, você pode manter o gerenciamento de contas de usuário no Active Directory local e sincronizá-lo com o Azure AD.

## Para sincronizar usuários locais com o Azure AD##

1. [Adicione o sufixo UPN](https://technet.microsoft.com/en-us/library/cc772007.aspx) a seu domínio personalizado no seu Active Directory local.
2. Defina o novo sufixo UPN para os usuários locais que você pretende importar.
3. Execute [Sincronização do Azure AD Connect](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) para integrar seus usuários locais com o AD do Azure.
4. Depois que as informações da conta foram sincronizadas com êxito, você pode atribuir licenças do Microsoft Intune usando o [Portal de gerenciamento do Office 365](https://portal.office.com/Admin/Default.aspx).

### Consulte também

[Sobre o domínio inicial onmicrosoft.com no Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[O que saber antes de começar a usar o Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


