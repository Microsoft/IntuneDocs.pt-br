---
title: Configurar a integração de bloqueio com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Saiba como integrar o Intune à segurança de ponto de extremidade móvel do Intune com Lookout para controlar o acesso de dispositivos móveis aos recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: be2e9371288961d0afdf7ad6e8cfec8f734087f6
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67529900"
---
# <a name="set-up-lookout-mobile-endpoint-security-integration-with-intune"></a>Configurar a integração de segurança de ponto de extremidade móvel do Lookout com o Intune
Com um ambiente que atende a [pré-requisitos](lookout-mobile-threat-defense-connector.md#prerequisites), você pode integrar a segurança de ponto de extremidade móvel do Lookout com o Intune. As informações neste artigo o orientarão na configuração da integração e de parâmetros importantes no Lookout para usar com o Intune.  

> [!IMPORTANT]
> Um locatário existente do Lookout Mobile Endpoint Security que não está associado ao seu locatário do Azure AD não pode ser usado para a integração com o Azure AD e o Intune. Contate o suporte do Lookout para criar um novo locatário do Lookout Mobile Endpoint Security. Use o novo locatário para carregar os usuários do Azure AD.

## <a name="collect-azure-ad-information"></a>Coletar informações do Azure AD  
Para integrar o Lookout com o Intune, associe o seu locatário da segurança de ponto de extremidade móvel do Lookout à sua assinatura do Azure AD.

Para habilitar a integração da assinatura da segurança de ponto de extremidade móvel do Lookout com o Intune, forneça as seguintes informações ao suporte do Lookout (enterprisesupport@lookout.com):  

- **ID do diretório de locatário do Azure AD**  

- **ID do objeto do grupo do Azure AD** para o grupo com acesso **completo** ao console da MES (segurança de ponto de extremidade móvel) do Lookout.  
  Este grupo de usuários é criado no AD do Azure para conter os usuários que têm *acesso completo* para entrar no **console do Lookout**. Os usuários devem ser membros desse grupo ou do grupo opcional de *acesso restrito*, para entrar no console do Lookout. 

- **ID do objeto de grupo do Azure AD** para o grupo com acesso **restrito** ao console do Lookout MES *(grupo opcional)* . 
  Esse grupo de usuário opcionais é criado no Azure AD para conter os usuários que não devem ter acesso a várias configurações e módulos relacionados ao registro do console do Lookout. Em vez disso, esses usuários têm acesso somente leitura ao módulo **Política de Segurança** do console do Lookout. Os usuários devem ser membros desse grupo opcional ou do grupo de *acesso completo* obrigatório, para entrar no console do Lookout.

 > [!TIP] 
 > Para obter mais detalhes sobre as permissões, leia [este artigo](https://personal.support.lookout.com/hc/articles/114094105653) no site do Lookout.

### <a name="collect-information-from-azure-ad"></a>Coletar informações do Azure AD 

1. Entre no [portal do Azure](https://portal.azure.com) com uma conta de administrador global.

2. Vá até **Azure Active Directory** > **Propriedades** e localize sua **ID de diretório**. Use o botão *Copiar* para copiar a ID de diretório e, em seguida, salve-a em um arquivo de texto.

   ![Propriedades do Azure AD](./media/lookout-mtd-connector-integration/azure-ad-properties.png)  

3. Em seguida, localize a ID de grupo do Azure AD para as contas usadas para conceder acesso a usuários do Azure AD ao console do Lookout. Um grupo é para *acesso completo* e o segundo, para *acesso restrito*, é opcional. Para obter a *ID de objeto*, para cada conta:  
   1. Vá até **Azure Active Directory** > **Grupos** para abrir o painel *Grupos – Todos os grupos*.  

   2. Selecione o grupo que você criou para *acesso completo* para abrir seu painel *Visão geral*.  

   3. Use o botão *Copiar* para copiar a ID de objeto e, em seguida, salve-a em um arquivo de texto.  

   4. Repita o processo para o grupo de *acesso restrito* se você usar esse grupo.  

      ![ID de objeto do grupo do Azure AD](./media/lookout-mtd-connector-integration/azure-ad-group-id.png)  

   Depois de obter essas informações, contate o suporte do Lookout (email: enterprisesupport@lookout.com). O suporte do Lookout trabalhará com seu contato principal para integrar sua assinatura e criar a conta do Lookout Enterprise, usando as informações fornecidas.  

## <a name="configure-your-lookout-subscription"></a>Configurar sua assinatura do Lookout  
Depois que o suporte do Lookout criar sua conta Lookout Enterprise, o suporte do Lookout enviará um email para o contato principal de sua empresa com um link para a URL de conexão: https://aad.lookout.com/les?action=consent. 

### <a name="initial-sign-in"></a>Conexão inicial  
A primeira conexão ao console do Lookout MES exibe uma página de consentimento (https://aad.lookout.com/les?action=consent). Um administrador global do AD do Azure acabou de se conectar e **Aceitar**. As conexões posteriores não exigem que o usuário tenha esse nível de privilégio do Azure AD. 

 Uma página de consentimento será exibida. Escolha **Aceitar** para concluir o registro. 
   ![captura de tela da página da primeira conexão do console do Lookout](./media/lookout-mtd-connector-integration/lookout_mtp_initial_login.png)

Depois de aceitar e autorizar, você será redirecionado para o console do Lookout.

Depois que a conexão inicial e o consentimento estiver concluído, os usuários que entrarem pelo https://aad.lookout.com serão redirecionados para o console do MES. Se o consentimento ainda não tiver sido dado, todas as tentativas de conexão resultarão em Erro de conexão inválida.

### <a name="configure-the-intune-connector"></a>Configurar o conector do Intune  
O procedimento a seguir pressupõe que você tenha criado anteriormente um grupo de usuários no Azure AD para testar a sua implantação do Lookout. A prática recomendada é iniciar com um pequeno grupo de usuários para permitir que os administradores do Lookout e do Intune se familiarizem com as integrações de produtos. Depois que elas estiverem familiarizadas, você poderá estender a inscrição para grupos de usuários adicionais.

1. Entre no [Console do Lookout MES](https://aad.lookout.com) e vá até **Sistema** > **Conectores** e, em seguida, selecione **Adicionar Conector**.  Selecione **Intune**.

   ![Imagem do console do Lookout com a opção Intune na guia Conectores](./media/lookout-mtd-connector-integration/lookout_mtp_setup-intune-connector.png)

2. No painel *Microsoft Intune*, selecione **Configurações de Conexão** e especifique a **Frequência de Pulsação** em minutos. 

   ![Imagem de guia Configurações de conexão com a frequência de pulsação configurada](./media/lookout-mtd-connector-integration/lookout-mtp-connection-settings.png)

3. Selecione **Gerenciamento de Registro** e, para **Usar os seguintes grupos de segurança do Azure AD para identificar os dispositivos que devem ser registrados no Lookout for Work**, especifique o *Nome do grupo* de um grupo do Azure AD para usar com o Lookout e, em seguida, selecione **Salvar alterações**.

    ![captura de tela da página de registro do conector do Intune](./media/lookout-mtd-connector-integration/lookout-mtp-enrollment.png)  

   **Sobre os grupos que você usa**:
   - Como prática recomendada, inicie um grupo de segurança do Azure AD que contém um pequeno número de usuários para testar a integração do Lookout.
   - O **Nome do grupo** diferencia maiúsculas de minúsculas, conforme mostrado nas **Propriedades** do grupo de segurança no portal do Azure.  
   - Os grupos que você especificar para **Gerenciamento de Registro** definem o conjunto de usuários cujos dispositivos serão registrados com o Lookout. Quando um usuário estiver em um grupo de registro, seus dispositivos no Azure AD estarão registrado e qualificado para ativação no Lookout MES. Na primeira vez que um usuário abre o aplicativo *Lookout for Work* em um dispositivo com suporte, ele será solicitado a ativá-lo.

4. Selecione **Sincronização de Estado** e verifique se o *status do dispositivo* e o *status da ameaça* estão definidos como **Ativado**.  Ambos são necessários para que a integração do Lookout com o Intune funcione corretamente.  

5. Selecione **Gerenciamento de Erros**, especifique o endereço de email que deve receber os relatórios de erros e, em seguida, selecione **Salvar alterações**.
 
   ![captura de tela da página de gerenciamento de erros do conector do Intune](./media/lookout-mtd-connector-integration/lookout-mtp-connector-error-notifications.png)

6. Selecione **Criar conector** para concluir a configuração do conector. Em seguida, quando estiver satisfeito com os resultados, você pode estender o registro para grupos de usuários adicionais.

## <a name="configure-intune-to-use-lookout-as-a-mobile-threat-defense-provider"></a>Configurar o Intune para usar o Lookout como um provedor de Defesa contra Ameaças Móveis
Depois de configurar o Lookout MES, você deverá configurar uma conexão com o Lookout no Intune.  

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Vá até **Conformidade do dispositivo** > **Defesa contra Ameaças Móveis** e selecione **Adicionar**.

3. No painel *Adicionar Conector*, use o menu suspenso e selecione **Lookout for Work**.  

4. Selecione **Criar**. Depois que o conector estabelece contato com o Lookout MES, as *Configurações do Conector* ficam disponíveis.

5. Defina **Habilitar a sincronização de aplicativos para dispositivos iOS** como **Ativada**. 

6. Selecione **Salvar** para completar a configuração.  O Intune e o Lookout MES agora estão integrados e prontos para uso.


## <a name="additional-settings-in-the-lookout-mes-console"></a>Configurações adicionais no console do Lookout MES
A seguir estão as configurações adicionais que você pode definir no console do Lookout MES.  

### <a name="configure-enrollment-settings"></a>Definir configurações de registro
No console do Lookout MES, selecione **Sistema** > **Gerenciar Registro** > **Configurações de Registro**.  

- Para **Status Desconectado**, especifique o número de dias antes que um dispositivo não conectado seja marcado como desconectado.  

  Dispositivos desconectados são considerados não compatíveis e serão impedidos de acessar seus aplicativos corporativos com base nas políticas de acesso condicional do Intune. Você pode especificar valores entre 1 e 90 dias.

  ![Configurações de registro do Lookout no módulo Sistema](./media/lookout-mtd-connector-integration/lookout-console-enrollment-settings.png)

### <a name="configure-email-notifications"></a>Configurar notificações por email
Para receber alertas de ameaças por email, conecte-se ao [console do Lookout MES](https://aad.lookout.com) com a conta de usuário que deverá receber as notificações.  

- Vá até **Preferências** e, em seguida, defina as notificações que você deseja receber como **ATIVADO** e **Salve** as alterações.  

- Se não quiser receber notificações por email, defina as notificações como **DESATIVADO** e salve as alterações.

  ![captura de tela da página de preferências com a conta de usuário exibida](./media/lookout-mtd-connector-integration/lookout-mtp-email-notifications.png)



## <a name="configure-threat-classifications"></a>Configurar as classificações de ameaças  
A segurança de ponto de extremidade móvel do Lookout classifica ameaças móveis de vários tipos. As classificações de ameaças do Lookout têm níveis de risco padrão associados a elas. Os níveis de risco podem ser alterados a qualquer momento para atender aos requisitos da empresa.

Para saber mais sobre as classificações de nível de ameaça e como gerenciar os níveis de risco associados a elas, confira [Referência de ameaças do Lookout](https://enterprise.support.lookout.com/hc/articles/360011812974).

>[!IMPORTANT]
> Os níveis de risco são um aspecto importante da segurança de ponto de extremidade móvel do Lookout, porque a integração com o Intune calcula a conformidade do dispositivo de acordo com esses níveis de risco em tempo de execução.  
> 
> O administrador do Intune define uma regra na política para identificar um dispositivo não compatível, se ele tem uma ameaça ativa com um nível mínimo igual a **Alto**, **Médio** ou **Baixo**. A política de classificação de ameaças na segurança de ponto de extremidade móvel do Lookout alimenta diretamente o cálculo de conformidade no Intune.  

## <a name="monitor-enrollment"></a>Monitorar registros
Quando a instalação estiver concluída, a segurança de ponto de extremidade móvel do Lookout começa a sondar o Azure AD em busca de dispositivos que correspondem aos grupos de registro especificados.  Você pode encontrar informações sobre os dispositivos registrados acessando **Dispositivos** no console do Lookout MES.  
- O status inicial dos dispositivos é *pendente*.  
- O status do dispositivo será atualizado depois que o aplicativo *Lookout for Work* estiver instalado, aberto e ativado no dispositivo.

Para ver detalhes de como fazer o aplicativo *Lookout for Work* ser implantado em um dispositivo, confira [Adicionar aplicativos Lookout for Work com o Intune](mtd-apps-ios-app-configuration-policy-add-assign.md).

## <a name="next-steps"></a>Próximas etapas

[Configurar os aplicativos do Lookout](mtd-apps-ios-app-configuration-policy-add-assign.md)
