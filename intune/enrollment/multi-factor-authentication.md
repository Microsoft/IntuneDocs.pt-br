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
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: ''
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: db04b93deffd2476a97b952fd1c6942fa79e1f05
ms.sourcegitcommit: e75718ee6cf93c0e6c915f2776b785fe8db9f7e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74955381"
---
# <a name="require-multi-factor-authentication-for-intune-device-enrollments"></a>Exigir autenticação multifator para registros de dispositivo do Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

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

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Dispositivos** > **Acesso Condicional**. O nó Acesso Condicional acessado no *Intune* é o mesmo nó que o acessado no *Azure AD*.
2. Escolha **Nova política**.
3. Em **Nova** política, digite um nome descritivo para a política.
4. Na seção **Atribuições**, escolha **Usuários e grupos**. 
5. Em **Usuários e grupos**, escolha **Selecionar usuários ou grupos** e marque **Usuários e grupos**. Em seguida, selecione os usuários e/ou grupos que receberão essa política e **Concluir**.
6. Na seção **Atribuições**, escolha **Aplicativos em nuvem**.
7. Na guia **Incluir** de **Aplicativos em nuvem**, escolha **Selecionar aplicativos**, escolha **Selecionar** > **Registro no Microsoft Intune** e, em seguida, **Concluído**. Ao escolher o **Registro no Microsoft Intune**, a MFA de acesso condicional é aplicada apenas ao registro do dispositivo (prompt único da MFA).
8. Na seção **Atribuições**, para **Condições**, você não precisa configurar as definições de MFA.
9. Na seção **Controles de acesso**, escolha **Conceder**.
10. Em **Conceder**, escolha **Conceder acesso** e, em seguida, selecione **Exigir autenticação multifator**. Não selecione **Exigir que o dispositivo seja marcado como compatível** porque os dispositivos não podem ser avaliados quanto à conformidade enquanto não são registrados. Em seguida, escolha **Selecionar**.
11. Em **Nova política**, selecione **Habilitar política** > **Ativado** e, em seguida, escolha **Criar**.



## <a name="next-steps"></a>Próximas etapas

A partir de agora, quando os usuários finais registrarem seus dispositivos, eles deverão se autenticar com um segundo formulário de identificação, como um PIN, um telefone ou biometria.
