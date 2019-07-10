---
title: Configurar a integração da Symantec ao Microsoft Intune
titleSuffix: Microsoft Intune
description: Como configurar a solução Symantec Endpoint Protection Mobile com o Microsoft Intune para controlar o acesso a dispositivo móvel para seus recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/21/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd185a42d36de6aaf1e6d0ff0b8e34619b02c093
ms.sourcegitcommit: ede86a3cb094c12e3e218b956abb9935bec76902
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2019
ms.locfileid: "67572431"
---
# <a name="set-up-symantec-endpoint-protection-mobile-integration-with-intune"></a>Configurar a integração do Symantec Endpoint Protection Mobile com o Intune

Conclua as seguintes etapas para integrar a solução SEP Mobile (Symantec Endpoint Protection Mobile) ao Intune. Você precisa adicionar os aplicativos SEP Mobile ao Azure AD com a funcionalidade de Logon único.

## <a name="before-you-begin"></a>Antes de começar

### <a name="azure-ad-account-used-to-integrate-intune-and-sep-mobile"></a>Conta do Azure AD usada para integrar o Intune e o SEP Mobile

- Verifique se a conta do Azure AD está configurada corretamente no [console de Gerenciamento do Symantec Endpoint Protection Mobile](https://aad.skycure.com) antes de iniciar o processo de instalação do SEP Mobile Basic.
- A conta do Azure AD deve ser uma conta de administrador global para realizar a integração.
### <a name="network-setup"></a>Configuração da Rede

Você pode garantir que a sua rede esteja configurada corretamente para integração com a configuração do SEP Mobile consultando o artigo da Symantec [Definindo sua configuração de rede](https://portal.skycure.com/articles/Documentation/Setting-up-your-network-configuration-26-8-2016).

### <a name="full-integration-vs-read-only"></a>Integração total versus Somente leitura.

O SEP Mobile é compatível com dois modos de integração com o Intune:

- **Integração somente leitura (instalação Básica):** Somente inventaria dispositivos do Azure Active Directory e popula-os no console de Gerenciamento Móvel do Symantec Endpoint Protection.
<br>
    - Se as caixas **Relatar a integridade e o risco de dispositivos ao Intune** e **Relatar também incidentes de segurança ao Intune** não estiverem marcadas no Symantec Endpoint Protection Mobile Management, a integração será somente leitura e, portanto, nunca alterará o estado de um dispositivo (em conformidade ou não em conformidade) no Intune.
<br></br>
- **Integração completa:** Permite que o SEP Mobile relate dispositivos em risco e detalhes de incidentes de segurança ao Intune, o que cria uma comunicação bidirecional entre os dois serviços de nuvem.

### <a name="how-are-the-sep-mobile-apps-used-with-azure-ad-and-intune"></a>Como os aplicativos SEP Mobile são usados com o Azure AD e o Intune?

- **Aplicativo do iOS:** Permite que os usuários finais entrem no Azure AD usando um aplicativo do iOS.

- **Aplicativo do Android:** Permite que os usuários finais entrem no Azure AD usando um aplicativo do Android.

- **Aplicativo de gerenciamento:** Esse é o aplicativo multilocatário do Azure AD para SEP Mobile que permite a comunicação serviço a serviço com o Intune.

## <a name="to-set-up-the-read-only-integration-between-intune-and-sep-mobile"></a>Para configurar a integração somente leitura entre o Intune e o SEP Mobile

> [!IMPORTANT]
> As credenciais de administrador do SEP Mobile devem consistir em uma conta de email que pertence a um usuário válido no Azure Active Directory, caso contrário, o logon falhará. O SEP Mobile usa o Azure Active Directory para autenticar seu administrador usando SSO (Logon Único).

1. Vá para [Console de Gerenciamento do Symantec Endpoint Protection Mobile](https://aad.skycure.com).

2. Insira suas **credenciais de administrador do SEP Mobile** e, em seguida, escolha **Continuar**.

3. Acesse **Configurações** e, em **Integração do Intune**, escolha **Configuração Básica**.

4. Ao lado de **Aplicativo iOS**, escolha **Adicionar ao Active Directory**.

    ![Imagem do Console de Gerenciamento Móvel do Symantec Endpoint Protection](./media/symantec-portal-basic-add.png)

5. Quando a página de logon se abrir, insira suas credenciais do Intune e, em seguida, escolha **Aceitar**.

    ![Imagem do prompt de logon do Intune do aplicativo iOS](./media/symantec-portal-basic-accept.png)

6. Depois que o aplicativo for adicionado ao Azure AD, você verá uma indicação de que o aplicativo foi adicionado com êxito.

    ![Imagem da tela de conclusão do aplicativo iOS](./media/symantec-portal-basic-added.png)

7. Repita estas etapas para o **SEP Mobile Android** e aplicativos de **Gerenciamento**.

### <a name="add-an-azure-ad-security-group-into-sep-mobile"></a>Adicionar um grupo de segurança do Azure AD ao SEP Mobile

Você precisa adicionar um grupo de segurança do Azure AD que contém todos os dispositivos que executam o SEP Mobile.

- Digite e selecione todos os grupos de segurança de dispositivos que estão executando o SEP Mobile e, em seguida, salve as alterações.

    ![Imagem mostrando grupos de usuários para aplicativos SEP Mobile](./media/symantec-portal-basic-groups.png)

O SEP Mobile sincroniza os dispositivos que executam seu serviço de Defesa contra Ameaças Móveis com os grupos de segurança do Azure AD.

![Imagem da configuração de Grupo de segurança no console de gerenciamento do SEP Mobile](./media/symantec-portal-basic-status.png)

## <a name="to-set-up-the-full-integration-between-intune-and-sep-mobile"></a>Para configurar a integração total entre o Intune e o SEP Mobile

### <a name="retrieve-the-directory-id-in-azure-ad"></a>Recuperar a ID de Diretório no Azure AD

1. Entre no [Portal do Azure](https://portal.azure.com).

2. Digite "Active Directory" na caixa de pesquisa e, em seguida, selecione **Azure Active Directory**.

3. Escolha **Propriedades**.

4. Ao lado da **ID do diretório**, escolha o ícone de cópia e cole-o em um local seguro. Você precisará desse identificador em uma etapa posterior.

    ![Imagem mostrando a ID do Diretório no portal do Azure](./media/symantec-azure-portal-directory-ID.png)

### <a name="optional-create-a-dedicated-security-group-for-devices-that-need-to-run-the-sep-mobile-apps"></a>(Opcional) Crie um Grupo de Segurança dedicado para dispositivos que precisam executar os aplicativos SEP Mobile
1. No [portal do Azure](https://portal.azure.com), em **Gerenciar**, escolha **Usuários e grupos** e, em seguida, escolha **Todos os grupos**.

2. Clique no botão **Adicionar**. Digite um **Nome** de grupo. Em **Tipo de associação**, escolha **Atribuído**.

3. Na folha **Membros**, selecione os membros do grupo e, em seguida, escolha o botão **Selecionar**.

4. Na folha **Grupo**, escolha **Criar**.

### <a name="set-up-the-integration-between-symantec-endpoint-protection-mobile-and-intune"></a>Configurar a integração entre o Symantec Endpoint Protection Mobile e o Intune

1. Vá para [Console de Gerenciamento do Symantec Endpoint Protection Mobile](https://aad.skycure.com).

2. Insira suas **credenciais de administrador do SEP Mobile**, então escolha **Continuar**.

3. Vá para a seção **Configurações** > **Integrações** > **Intune** > **Seleção de Integração do EMM**.

4. Na caixa **ID do Diretório**, cole a ID do Diretório copiada do Azure Active Directory na seção anterior e salve as configurações.

    ![Imagem mostrando a ID do Diretório no portal do SEP Mobile](./media/symantec-portal-directory-ID.png)

5. Vá para a seção **Configurações** > **Integrações** > **Intune** > **Configuração Básica**.

6. Ao lado de **Aplicativo iOS**, escolha o botão **Adicionar ao Active Directory**.

    ![Imagem mostrando como adicionar o aplicativo iOS ao Active Directory](./media/symantec-portal-basic-add.png)

7. Entre usando as credenciais do Azure Active Directory para a conta do Office 365 que gerencia o diretório.

8. Escolha o botão **Aceitar** para adicionar o aplicativo SEP Mobile iOS ao Azure Active Directory.

    ![Imagem mostrando o botão aceitar](./media/symantec-portal-basic-accept.png)

9. Repita o mesmo processo para o **Aplicativo Android** e o **Aplicativo de Gerenciamento de**.

10. Selecione todos os grupos de usuários que precisam executar os aplicativos SEP Mobile, por exemplo, o grupo de segurança que você criou anteriormente.

    ![Imagem mostrando grupos de usuários para aplicativos SEP Mobile](./media/symantec-portal-basic-groups.png)

11. O SEP Mobile sincroniza os dispositivos nos grupos selecionados e começa a relatar informações ao Intune. Você pode exibir esses dados na seção Integração Completa. Vá para a seção **Configurações** > **Integrações** > **Intune** > **Integração Completa**.

     ![Imagem mostrando integração completa do SEP Mobile concluída](media/symantec-portal-basic-status.PNG)
## <a name="next-steps"></a>Próximas etapas

[Configurar aplicativos SEP Mobile](mtd-apps-ios-app-configuration-policy-add-assign.md)
