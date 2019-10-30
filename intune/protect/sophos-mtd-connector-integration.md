---
title: Configurar a integração do Sophos Mobile ao Intune
titleSuffix: Intune on Azure
description: Como configurar a solução Sophos Mobile com o Microsoft Intune para controlar o acesso a dispositivo móvel para seus recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: aad6268606dfcf69c304bb5c5b270c8c4795e4b2
ms.sourcegitcommit: 1a5b185acd27954b10b6d59409d82eb80fd71284
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72681295"
---
# <a name="integrate-sophos-mobile-with-intune"></a>Integrar o Sophos Mobile com o Intune  

Conclua as etapas a seguir para integrar a solução de Defesa contra Ameaças do Sophos Mobile ao Intune.  

> [!NOTE]
> O fornecedor da Defesa Contra Ameaças Móveis não é compatível com dispositivos não registrados.

## <a name="before-you-begin"></a>Antes de começar  

Antes de iniciar o processo de integração do Sophos Mobile ao Intune, verifique se você tem o seguinte:  
- Assinatura do Microsoft Intune  
- Credenciais de administrador do Azure Active Directory para conceder as seguintes permissões:  
  - Entrada e leitura de perfil do usuário  
  - Acessar diretório como o usuário conectado  
  - Ler dados do diretório  
  - Enviar informações do dispositivo para o Intune  
- Credenciais de administrador para acessar o console de admin do Sophos Mobile.  


### <a name="sophos-mobile-app-authorization"></a>Autorização de aplicativo Sophos Mobile  
  
O processo de autorização de aplicativo do Sophos Mobile é o seguinte:  
- Permitir que o serviço do Sophos Mobile comunique informações relacionadas ao estado de integridade do dispositivo novamente para o Intune.  
- O Sophos Mobile é sincronizado com a associação do Azure AD Enrollment Group para preencher o banco de dados de seu dispositivo.  
- Permitir que o console de administrador do Sophos Mobile use o SSO (Logon Único) do Azure AD.  
- Permitir que o aplicativo Sophos Mobile se conecte usando o SSO do Azure AD.  


## <a name="to-set-up-sophos-mobile-integration"></a>Para configurar a integração do Sophos Mobile  

1. Entre no [portal do Azure]( https://portal.azure.com/), acesse **Intune** > **Conformidade de dispositivo** > **Defesa contra ameaças móveis** > e selecione **Adicionar**.  
2. Na página **Adicionar o conector**, use a lista suspensa e selecione **Sophos**. Em seguida, selecione **Criar**.  
3. Selecione o link *Abrir o console de administrador do Sophos*.  
4. Entre no [console de administrador do Sophos](https://central.sophos.com/) com suas credenciais do Sophos.  
5. Vá para **Mobile** > **Configurações** > **Instalação** > **Instalação do Sophos**.  
6. Na página **instalação do Sophos**, selecione a guia **MTD do Intune**.  
   ![Instalação do Sophos](./media/sophos-mtd-connector-integration/sophos-setup.png) 
 
7. Selecione **Associar** e, em seguida, selecione **Sim**. O Sophos conecta-se ao Intune e exige que você entre em sua assinatura do Intune. 
8. Na janela de autenticação do Microsoft Intune, insira suas credenciais do Intune e opte por **Aceitar** a solicitação de permissões para *Defesa Contra Ameaças do Sophos Mobile*.  
   ![Autenticação do Intune](./media/sophos-mtd-connector-integration/intune-authentication.png)

9. Na página **instalação do Sophos**, selecione **Salvar** para concluir a configuração para o Intune:  
   ![Salvar instalação do Sophos](./media/sophos-mtd-connector-integration/save-sophos-configuration.png)  

1. Quando a mensagem **Integração bem-sucedida** for exibida, a integração estará concluída.  
1. No console do Intune, o Sophos agora está disponível.  


## <a name="next-steps"></a>Próximas etapas  
[Configurar aplicativos cliente do Sophos](mtd-apps-ios-app-configuration-policy-add-assign.md)
