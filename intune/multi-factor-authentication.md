---
title: Exigir autenticação multifator para o registro de dispositivo do Intune
titleSuffix: Microsoft Intune
description: Como exigir a autenticação multifator no Azure AD para registro de dispositivos do Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: ''
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cf5611b3b9292222582d66cae39b4f751279dcec
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2019
ms.locfileid: "59568785"
---
# <a name="require-multi-factor-authentication-for-intune-device-enrollments"></a>Exigir autenticação multifator para registros de dispositivo do Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Intune pode usar a MFA (Autenticação Multifator) do AD (Azure Active Directory) para registro de dispositivos a fim de ajudá-lo a proteger seus recursos corporativos.

A MFA funciona solicitando dois ou mais dos métodos de verificação a seguir:

- Algo que você conhece (normalmente uma senha ou PIN).
- Algo que você tem (um dispositivo de confiança que não é facilmente duplicado, como um telefone).
- Algo que você é (biometria, como uma impressão digital).

A MFA tem suporte para dispositivos iOS, Android, Windows 8.1 ou posterior, Windows Phone 8.1, Windows 10 Mobile ou posterior.

Quando você habilitar a MFA, os usuários finais deverão fornecer duas formas de credenciais para registrar um dispositivo.

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Configurar o Intune para exigir a autenticação multifator no registro do dispositivo

Para exigir MFA quando um dispositivo é registrado, siga estas etapas:

>[!Important]
>Você deve ter um Azure Active Directory Premium P1 ou acima atribuído aos usuários para implementar esta política.

>[!Important]
>Não configure **Regras de acesso baseadas em dispositivo** para o registro no Microsoft Intune.

1. Entre no [Portal do Microsoft Azure](https://portal.azure.com) com suas credenciais.
2. No portal, vá até **Intune** e escolha **Acesso condicional**. O nó Acesso condicional acessado no *Intune* é o mesmo nó acessado no *Azure AD*.
4. Escolha **Nova política**.
5. Em **Nova** política, digite um nome descritivo para a política.
6. Na seção **Atribuições**, escolha **Usuários e grupos**. 
7. Em **Usuários e grupos**, escolha **Selecionar usuários ou grupos** e marque **Usuários e grupos**. Em seguida, selecione os usuários e/ou grupos que receberão essa política e **Concluir**.
8. Na seção **Atribuições**, escolha **Aplicativos em nuvem**.
9. Na guia **Incluir** de **Aplicativos em nuvem**, escolha **Selecionar aplicativos**, escolha **Selecionar** > **Registro no Microsoft Intune** e, em seguida, **Concluído**.
10. Na seção **Atribuições**, para **Condições**, você não precisa configurar as definições de MFA.
11. Na seção **Controles de acesso**, escolha **Conceder**.
12. Em **Conceder**, escolha **Conceder acesso** e, em seguida, selecione **Exigir autenticação multifator**. Não selecione **Exigir que o dispositivo seja marcado como compatível** porque os dispositivos não podem ser avaliados quanto à conformidade enquanto não são registrados. Em seguida, escolha **Selecionar**.
13. Em **Nova política**, selecione **Habilitar política** > **Ativado** e, em seguida, escolha **Criar**.



## <a name="next-steps"></a>Próximas etapas

A partir de agora, quando os usuários finais registrarem seus dispositivos, eles deverão se autenticar com um segundo formulário de identificação, como um PIN, um telefone ou biometria.
