---
title: Inscrever-se ou entrar no Microsoft Intune
description: Como se inscrever para uma assinatura do Microsoft Intune ou entrar para iniciar sua assinatura.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f3ce07a-b718-42a9-bace-f99a8b8abd94
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 78d38b72c9853a9eadaf71fcdff7567fc66d35ca
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "73414662"
---
# <a name="sign-up-or-sign-in-to-microsoft-intune"></a>Inscrever-se ou entrar no Microsoft Intune

Este tópico informa os administradores do sistema como você pode se inscrever para uma conta do Intune.

Antes de você se inscrever no Intune, determine se você já tem uma conta do Microsoft Online Services, Enterprise Agreement ou contrato de licenciamento por volume equivalente. Um contrato de licenciamento por volume Microsoft ou outra assinatura dos serviços em nuvem da Microsoft, assim como o Office 365, geralmente inclui uma conta corporativa ou de estudante.

Se você já tem uma conta corporativa ou de estudante, **entre** com essa conta e adicione o Intune à sua assinatura. Caso contrário, você pode **inscrever-se** para uma nova conta a fim de usar o Intune para sua organização.

>[!WARNING]
>Você não pode combinar uma conta corporativa ou de estudante depois de se inscrever para uma nova conta.

## <a name="how-to-sign-up-for-intune"></a>Como se inscrever no Intune

1. Visite a [Página de inscrição do Intune](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

   ![Captura de tela da página da Web de inscrição de conta de avaliação do Microsoft Intune](./media/account-sign-up/account-sign-up-site.png)

2. Na página de Inscrição, entre ou inscreva-se para gerenciar uma nova assinatura do Intune.

## <a name="post-sign-up-considerations"></a>Considerações após a inscrição

Após se inscrever para uma nova assinatura, uma mensagem de email com as informações da conta é recebida por você no endereço de email fornecido durante o processo de inscrição. Isso confirma que sua assinatura está ativa.

Após concluir o processo de inscrição, você será direcionado para o centro de administração do Microsoft 365, usado para adicionar usuários e atribuir licenças a eles. Se só tiver contas baseadas em nuvem usando seu nome de domínio onmicrosoft.com padrão, você poderá em tal momento prosseguir e adicionar usuários e atribuir licenças. No entanto, se você pretender usar o [nome de domínio personalizado](custom-domain-name-configure.md) da sua organização ou quiser [sincronizar informações de conta de usuário](users-add.md#sync-active-directory-and-add-users-to-intune) do Active Directory local, você poderá fechar essa janela do navegador.

## <a name="sign-in-to-microsoft-intune"></a>Entrar no Microsoft Intune

Depois de se inscrever no Intune, você pode usar qualquer dispositivo com um [navegador compatível](supported-devices-browsers.md#intune-supported-web-browsers) para entrar no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) para administrar o serviço.

Por padrão, sua conta deve ter uma das seguintes permissões no Azure AD:

- Administrador Global
- Administrador de Serviços do Intune (também conhecido como Administrador do Intune)

Para conceder acesso para administrar o serviço para usuários com outras permissões, confira [Controle de Acesso Baseado em Função](role-based-access-control.md)

### <a name="intune-admin-portal-url"></a>URL do Portal de Administração do Intune

Centro de Administração do Microsoft 365: https://devicemanagement.microsoft.com

Portal do Intune Azure: https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade

Intune para Educação: https://intuneeducation.portal.azure.com

Portal clássico do Intune: https://manage.microsoft.com O portal clássico do Intune é usado somente para gerenciar dispositivos registrados com o cliente de software de computador do Intune

### <a name="urls-for-intune-services-provided-by-office-365"></a>URLs para serviços do Intune fornecidos pelo Office 365

Microsoft 365 Business: https://portal.microsoft.com/adminportal

Gerenciamento de Dispositivos Móveis do Office 365: https://portal.office.com/adminportal/home#/MifoDevices

## <a name="see-also"></a>Consulte também

[Não é possível entrar no Office 365, Azure ou Intune](https://support.microsoft.com/help/2412085)
