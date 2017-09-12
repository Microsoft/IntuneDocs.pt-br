---
title: "Autenticação multifator para o registro de dispositivo do Intune"
titlesuffix: Azure portal
description: "Como exigir a autenticação multifator no Azure AD para registro de dispositivos."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angerobe
ms.date: 08/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: 
ms.custom: intune-azure
ms.openlocfilehash: 0355c6ca11d7b1221ad7aa833874eba91eea0600
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Autenticação multifator para registros de dispositivo do Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

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
>Não configure **Regras de acesso baseadas em dispositivo** para o registro no Microsoft Intune.

1. Entre no [Portal do Microsoft Azure](https://portal.azure.com) com suas credenciais.
2. No portal, escolha **Azure Active Directory**.
2. No **Azure Active Directory**, escolha **Gerenciar** > **Aplicativos empresariais**.
3. Em **Aplicativos empresariais**, escolha **Gerenciar** > **Todos os aplicativos**. Será exibida uma lista com todos os aplicativos do Azure que você gerencia.
3. Na lista, escolha **Registro no Microsoft Intune**.
4. Em **Registro no Microsoft Intune**, escolha **Segurança** > **Acesso condicional**.
5. Escolha **Nova política**.
6. Em **Nova** política, digite um nome descritivo para a política.
7. Na seção **Atribuições**, escolha **Usuários e grupos**.
8. Em **Usuários e grupos**, selecione os usuários ou grupos que receberão essa política e escolha **Concluído**.
9. Na seção **Atribuições**, escolha **Aplicativos em nuvem**.
10. Na guia **Incluir** de **Aplicativos em nuvem**, escolha **Selecionar aplicativos**, escolha **Selecionar** > **Registro no Microsoft Intune** e, em seguida, **Concluído**.
11. Na seção **Atribuições**, escolha **Condições**.
12. Em **Condições**, você não precisa configurar as definições de MFA.
13. Na seção **Controles de acesso**, escolha **Conceder**.
14. Em **Conceder**, escolha **Conceder acesso** e, em seguida, selecione **Exigir autenticação multifator**.
    Não selecione **Exigir que o dispositivo seja marcado como compatível** porque os dispositivos não podem ser avaliados quanto à conformidade enquanto não são registrados.
15. Escolha **Selecionar**.
16. Em **Nova política**, selecione **Habilitar política** > **Ativado** e, em seguida, escolha **Criar**.



## <a name="next-steps"></a>Próximas etapas

A partir de agora, quando os usuários finais registrarem seus dispositivos, eles deverão se autenticar com um segundo formulário de identificação, como um PIN, um telefone ou biometria.
