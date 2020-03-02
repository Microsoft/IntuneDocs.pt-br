---
title: Configurar a integração da Proteção contra Ameaças Móveis Wandera com o Intune
titleSuffix: Intune on Azure
description: Como configurar a solução de Proteção contra Ameaças Móveis Wandera com o Microsoft Intune para controlar o acesso de dispositivos móveis aos seus recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: d90e3757ced90bea21e4033b6baa93bfa201b1f2
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514210"
---
# <a name="integrate-wandera-mobile-threat-protection-with-intune"></a>Integrar a Proteção contra Ameaças Móveis Wandera com o Intune  

Conclua as etapas a seguir para integrar a solução de Defesa contra Ameaças Móveis Wandera ao Intune.  

> [!NOTE]
> O fornecedor da Defesa Contra Ameaças Móveis não é compatível com dispositivos não registrados.

## <a name="before-you-begin"></a>Antes de começar  

Antes de iniciar o processo para integrar a solução Wandera ao Intune, verifique se você possui os seguintes pré-requisitos:
- Assinatura do Microsoft Intune  
- Credenciais de administrador do Azure Active Directory para conceder as seguintes permissões:  
  - Entrada e leitura de perfil do usuário  
  - Acessar diretório como o usuário conectado  
  - Ler dados do diretório  
  - Enviar informações do dispositivo para o Intune  

- Assinatura do Wandera:
  - Uma ou mais contas Wandera licenciadas para o EMM Connect  
  - Uma conta com privilégios de superadministrador no Wandera  
 
### <a name="wandera-mobile-threat-defense-app-authorization"></a>Autorização do aplicativo de Defesa contra Ameaças Móveis Wandera  

O processo de autorização do aplicativo Defesa contra Ameaças Móveis Wandera:  
- Permitir que o serviço Defesa contra Ameaças Móveis Wandera repasse informações relacionadas ao estado de integridade do dispositivo para o Intune.  
- Sincronizar o Wandera com a associação ao Grupo de Registro do Azure AD para preencher o banco de dados do dispositivo.  
- Permita que o portal de administração RADAR do Wandera use o SSO (logon único) do Azure AD.  
- Permita que o aplicativo Defesa contra Ameaças Móveis Wandera entre com o SSO do Azure AD.  


## <a name="set-up-wandera-mobile-threat-defense-integration"></a>Configurar a integração da Defesa contra Ameaças Móveis Wandera  
A configuração do *EMM Connect* para o Wandera requer um processo de configuração única que você realiza nos consoles do Intune e do Wandera. O processo de configuração leva cerca de 15 minutos. Você pode concluir a configuração sem coordenação com sua conta técnica ou representante de suporte Wandera.  

### <a name="enable-support-for-wandera-in-intune"></a>Habilitar suporte para Wandera no Intune

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Escolha **Administração de locatários** > **Conectores e tokens** > **Defesa contra Ameaças Móveis** > **Adicionar**.
3. Na página **Adicionar Conector**, use a lista suspensa e selecione **Wandera**. Em seguida, selecione **Criar**.  
4. No painel Defesa contra Ameaças Móveis, selecione o conector MTD **Wandera** na lista de conectores para abrir o painel *Editar conector*. Selecione **Abrir o console administrativo do Wandera** para abrir o [RADAR](https://radar.wandera.com/login), o console administrativo do Wandera e entrar. 
5. No console do Wandera, acesse **Configurações** > **EMM Integration** e selecione a guia **EMM Connect**. Use a lista suspensa *Fornecedor EMM* e selecione *Microsoft Intune*.

   ![Selecionar Intune](./media/wandera-mtd-connector-integration/set-up-intune-in-radar.png)

6. Selecione **Conceder permissões** para abrir uma conexão ao portal do Intune. Entre usando suas credenciais de administrador do Intune, marque a caixa de seleção e, em seguida, **Aceitar** na solicitação de permissões.  

   ![Aceitar permissões](./media/wandera-mtd-connector-integration/permissions.png) 

7. O Wandera conclui a conexão e retorna para o console administrativo RADAR. Repita o processo para **Conceder** acesso a configurações adicionais, conforme necessário.  

   ![Integrações e permissões](./media/wandera-mtd-connector-integration/integrations-and-permissions.png) 

8. No console RADAR, copie o nome do grupo **SyncOnly** que aparece abaixo de **EMM Label**. Você usará esse nome para configurar um grupo no Intune para sincronização com o Wandera.

   ![Grupo de sincronização](./media/wandera-mtd-connector-integration/sync-group-name.png) 

9. Retorne ao console do [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e edite o conector MTD do Wandera. Defina os botão de alternância disponíveis para **Ativado** e **Salvar** a configuração.  

   ![Habilitar Wandera](./media/wandera-mtd-connector-integration/enable-wandera.png) 

O Intune e o Wandera agora estão conectados.  

## <a name="configure-the-wandera-applications-and-synchronization-group"></a>Configurar o grupo de sincronização e os aplicativos Wandera  
Para implantar as soluções Wandera, você adicionará os aplicativos móveis Wandera das plataformas que você usa (iOS e Android) ao Intune e os atribuirá a um grupo específico para sincronização; o grupo *SyncOnly*. 

As seções e procedimentos a seguir guiarão você nesse processo.

Para obter mais informações sobre esse processo do Wandera, entre no portal [RADAR](https://radar.wandera.com/login) do Wandera. Acesse **Configurações** > **Integração EMM**, selecione a guia **Push de Aplicativo** e, em seguida, selecione **Microsoft Intune**. A guia Push de Aplicativo é atualizada com instruções específicas do Intune.  

### <a name="add-the-wandera-apps"></a>Adicionar aplicativos Wandera  
Crie aplicativos clientes no Intune para implantar o aplicativo Wandera em dispositivos Android e iOS/iPadOS. Confira [Adicionar aplicativos MTD](mtd-apps-ios-app-configuration-policy-add-assign.md) para conhecer os procedimentos e detalhes personalizados específicos dos aplicativos Wandera.  

Depois de criar os aplicativos, retorne aqui para criar o grupo de sincronização e atribuir os aplicativos.

### <a name="create-the-synchronization-group-and-assign-the-apps"></a>Criar o grupo de sincronização e atribuir os aplicativos

1. Obtenha o nome do grupo **SyncOnly** que aparece abaixo de **Rótulo EMM** dentro do console RADAR do Wandera. Você pode ter salvado esse nome durante a etapa 7 ao [habilitar o suporte para Wandera no Intune](#enable-support-for-wandera-in-intune). Use esse nome como o nome do grupo no Intune para sincronização com o Wandera.  

2. No centro de administração do Gerenciador de Ponto de Extremidade, acesse **Grupos** e marque **Novo grupo**. Especifique o seguinte a fim de configurar o grupo de sincronização para uso pelo Wandera:
   - **Tipo de grupo**: **Security**
   - **Nome do grupo**: Especifique o nome de **SyncOnly** que você recuperou do console administrativo do RADAR do Wandera.

   ![Configurar o grupo de sincronização](./media/wandera-mtd-connector-integration/configure-sync-group.png)

3. Selecione **Membros** e atribua grupos que incluam os dispositivos Android e iOS/iPadOS que você deseja usar com o Wandera.

4. Selecione **Criar** para salvar o grupo.

Para obter mais informações, confira [Implantar aplicativos](../apps/apps-deploy.md)

### <a name="assign-the-wandera-apps-to-the-synchronization-group"></a>Atribuir os aplicativos Wandera ao grupo de sincronização  
Repita o procedimento a seguir para o aplicativo Wandera que você criou para iOS/iPadOS e Android.

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Escolha **Aplicativos** > **Todos os aplicativos** e escolha o aplicativo do Wandera.
3. Selecione **Atribuições** e **Adicionar grupo**.  
4. No painel *​​Adicionar grupo*, para *Tipo de atribuição*, selecione **Obrigatória**.
5. Selecione **Grupos incluídos** e, em seguida, **Selecionar grupos para incluir**. Especifique o grupo que você criou para a sincronização do Wandera e clique em **Selecionar** > **OK** > **OK**. Selecione **Salvar** para concluir a atribuição do grupo. 

## <a name="next-steps"></a>Próximas etapas  
Agora que você configurou a Integração, é possível começar a configurar políticas, configurar acesso condicional avançado e visualizar relatórios no console de administração do Wandera. Para saber mais sobre como gerenciar e configurar a solução do Wandera, confira o [Guia de Introdução ao Centro de Suporte](https://radar.wandera.com/?return_to=https://wandera.force.com/Customer/s/getting-started) na documentação do Wandera. 
