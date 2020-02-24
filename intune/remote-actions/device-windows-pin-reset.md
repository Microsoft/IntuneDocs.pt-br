---
title: Redefinir a senha de dispositivos Windows com o Microsoft Intune – Azure | Microsoft Docs
description: Para redefinir a senha em dispositivos Windows, instale o Serviço de Redefinição de Pin da Microsoft e o Cliente de Redefinição de Pin da Microsoft, crie uma política de dispositivo usando sua ID de diretório do Azure Active Directory e, em seguida, redefina a senha no Portal do Azure usando o Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c4b3313d5ec7fe81944431276a63bfafb7a1b3dc
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77413624"
---
# <a name="reset-the-passcode-on-windows-devices-using-intune"></a>Redefinir senha em dispositivos Windows usando o Intune

Você pode redefinir a senha para dispositivos Windows. O recurso de redefinição de senha usa o Serviço de Redefinição de PIN da Microsoft para gerar uma nova senha para dispositivos que executam o Windows 10 Mobile. 

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows 10 Mobile executando Atualização para Criadores e posteriores (Azure AD associado).

**Não** há suporte para as seguintes plataformas:
- Windows
- iOS
- macOS
- Android

## <a name="authorize-the-pin-reset-services"></a>Autorizar os serviços de redefinição de PIN

Para redefinir a senha em dispositivos Windows, integre o serviço de redefinição de senha no seu locatário do Intune.

1. Acesse [Produção do serviço de redefinição de PIN da Microsoft](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) e entre usando a conta de administrador do locatário.
2. **Aceite** o consentimento para o serviço de redefinição de PIN acessar sua conta: ![Aceitar a solicitação do servidor de redefinição de PIN para permissões](./media/device-windows-pin-reset/pin-reset-service-home-screen.png)
3. Acesse [Produção do cliente de redefinição de PIN da Microsoft](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) e entre usando a conta de administrador do locatário. **Aceite** o consentimento para o cliente de redefinição de PIN acessar sua conta.
4. No [portal do Azure](https://portal.azure.com), confirme que os serviços de redefinição de PIN estão listados nos aplicativos Enterprise (Todos os aplicativos): ![Página de permissões do serviço de redefinição de PIN](./media/device-windows-pin-reset/pin-reset-service-application.png)

> [!NOTE]
> Depois de aceitar as solicitações de redefinição do PIN, você poderá receber uma mensagem `Page not found` ou pode parecer que nada aconteceu. Esse comportamento é normal. Confirme se os dois aplicativos de Redefinição de PIN estão listados para seu locatário.

## <a name="configure-windows-devices-to-use-pin-reset"></a>Configurar os dispositivos do Windows para usar a redefinição de PIN

Para configurar a redefinição de PIN nos dispositivos Windows que você gerencia, use uma [política de dispositivo personalizado do Intune Windows 10](../configuration/custom-settings-windows-10.md). Configure a política usando os seguintes CSPs (provedores de serviços de configuração de política) do Windows:

**Usar a política de dispositivo móvel** - `./Device/Vendor/MSFT/PassportForWork/*tenant ID*/Policies/EnablePinRecovery`

Substitua *ID do locatário* pela sua ID de diretório do Microsoft Azure AD, que é listada nas **Propriedades** do Azure Active Directory no [Portal do Azure](https://portal.azure.com).

Defina o valor dessa CSP como **True**.

> [!TIP]
> Depois de criar a política, atribua-a (ou implante-a) em um grupo. A política pode ser atribuída aos grupos de usuário ou de dispositivos. Se ela for atribuída a um grupo de usuários, este poderá incluir os usuários que têm outros dispositivos, como iOS/iPadOS. Tecnicamente, a política não se aplica, mas esses dispositivos ainda são incluídos nos detalhes do status.

## <a name="reset-the-passcode"></a>Redefinir a senha

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431). 
2. Selecione **Dispositivos** e, em seguida, **Todos os dispositivos**.
3. Selecione o dispositivo para o qual você deseja redefinir a senha. Nas propriedades do dispositivo, selecione **Redefinir senha**.
4. Selecione **Sim** para confirmar. A senha é gerada e exibida no portal pelos próximos sete dias.

## <a name="next-step"></a>Próxima etapa

Se a redefinição de senha falhar, um link com mais detalhes será fornecido no portal.
