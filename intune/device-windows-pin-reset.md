---
title: Redefinir senha em dispositivos Windows com o Intune
titleSuffix: Intune on Azure
description: "Saiba como usar o Intune para redefinir a senha em dispositivos do Windows integrados com o Serviço de Redefinição do PIN da Microsoft.”"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9cf2549852c5949ff1c95af12b40f59136d56e34
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2017
---
# <a name="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune"></a>Redefinir a senha em dispositivos Windows integrado com o Serviço de Redefinição de PIN da Microsoft usando o Intune

A capacidade de redefinição de senha para dispositivos Windows integra-se com o Serviço de Redefinição de PIN da Microsoft para permitir que você gere uma nova senha para dispositivos que executam o Windows 10 Mobile. Os dispositivos devem executar a Atualização do Windows 10 para Criadores ou posterior.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Com suporte na Atualização do Windows 10 para Criadores e versões posteriores (ingressado no Azure AD)
- Windows Phone – Sem suporte
- iOS – Sem suporte
- macOS – Sem suporte
- Android – Sem suporte


## <a name="before-you-start"></a>Antes de começar

Antes de redefinir remotamente a senha em dispositivos Windows que você pode gerenciar, integre o serviço de redefinição do PIN para seu locatário do Intune e configure os dispositivos gerenciados. Siga estas instruções para fazer isso:

### <a name="connect-intune-with-the-pin-reset-service"></a>Conecte o Intune ao serviço de redefinição de PIN

1. Visite o [site de integração do Serviço de Redefinição de PIN da Microsoft](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) e entre usando a conta de administrador de locatário que você usa para gerenciar seu locatário do Intune.
2. Após fazer logon, clique em **Aceitar** para dar consentimento para o serviço de redefinição de PIN acessar sua conta.<br>
![Página de permissões do serviço de redefinição de PIN](./media/pin-reset-service-application.png)
3. No Portal do Azure, você pode verificar se o Intune e o serviço de redefinição de PIN foram integrados dos aplicativos Enterprise – Todas as folhas de aplicativos conforme mostrado na seguinte captura de tela:<br>
![Aplicativo do serviço de redefinição de PIN no Azure](./media/pin-reset-service-home-screen.png)
4. Faça logon [neste site](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) usando as credenciais de administrador de locatário do Intune e escolha **Aceitar** novamente para dar consentimento para o serviço acessar sua conta.

### <a name="configure-windows-devices-to-use-pin-reset"></a>Configurar os dispositivos do Windows para usar a redefinição de PIN

Para configurar a redefinição de PIN nos dispositivos Windows que você gerencia, use uma [política de dispositivo personalizado do Intune Windows 10](custom-settings-windows-10.md) para habilitar o recurso. Configure a política usando os seguintes CSPs (provedores de serviços de configuração de política) do Windows:


- **Para dispositivos** - **./Device/Vendor/MSFT/PassportForWork/*tenant ID*/Policies/EnablePinRecovery**

*ID do locatário* refere-se à ID de Diretório do Azure Active Directory que pode ser obtida na página **Propriedades** do Azure Active Directory.

Defina o valor dessa CSP como **True**.

## <a name="steps-to-reset-the-passcode"></a>Etapas para redefinir a senha

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos**, escolha **Gerenciar** > **Todos os dispositivos**.
5. Selecione o dispositivo para o qual você deseja redefinir a senha e, na folha de propriedades do dispositivo, escolha **Nova senha**.
6. Na confirmação que aparece, escolha **Sim**. A senha é gerada e exibida no portal pelos próximos sete dias.

## <a name="next-steps"></a>Próximas etapas

Se a redefinição de senha falhar, é fornecido um link no portal para obter mais informações.


