---
title: Configurar a integração de bloqueio com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Saiba como integrar o Intune com a Defesa contra Ameaças Móveis do Lookout para controlar o acesso de dispositivos móveis aos recursos corporativos.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ffdfd203b2b67a25d5826798d89ae548e33d7756
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66047133"
---
# <a name="set-up-your-lookout-mobile-threat-defense-integration-with-intune"></a>Configurar a integração da Defesa contra Ameaças Móveis do Lookout com o Intune

As etapas a seguir são necessárias para configurar a assinatura da Defesa contra Ameaças Móveis do Lookout:

| #        |Etapa  |
| ------------- |:-------------|
| 1 | [Coletar informações do Azure AD](#collect-azure-ad-information) |
| 2 | [Configurar sua assinatura](#configure-your-subscription) |
| 3 | [Configurar grupos de registro](#configure-enrollment-groups) |
| 4 | [Configurar a sincronização de estado](#configure-state-sync) |
| 5 | [Configurar informações do destinatário do email de relatório de erros](#configure-error-report-email-recipient-information) |
| 6 | [Definir configurações de registro](#configure-enrollment-settings) |
| 7 | [Configurar notificações por email](#configure-email-notifications) |
| 8 | [Configurar a classificação de ameaças](#configure-threat-classification) |
| 9 | [Verificar o registro](#watching-enrollment) |

> [!IMPORTANT]
> Um locatário existente do Lookout Mobile Endpoint Security que não está associado ao seu locatário do Azure AD não pode ser usado para a integração com o Azure AD e o Intune. Contate o suporte do Lookout para criar um novo locatário do Lookout Mobile Endpoint Security. Use o novo locatário para carregar os usuários do Azure AD.

## <a name="collect-azure-ad-information"></a>Coletar informações do Azure AD
O locatário do Lookout Mobility Endpoint Security será associado à sua assinatura do Azure AD para integrar o Lookout com o Intune. Para habilitar sua assinatura do serviço de Defesa contra Ameaças Móveis do Lookout, o suporte do Lookout (enterprisesupport@lookout.com) precisa das seguintes informações:

* **ID do locatário do Azure AD**
* **ID do Objeto de Grupo do Azure AD** para acesso **completo** ao console do Lookout
* **ID do objeto de grupo do Azure AD** para acesso **restrito** ao Lookout (opcional)

Use as etapas a seguir para coletar as informações de que precisa para fornecer à equipe de suporte do Lookout.

1. Entre no [Portal do Azure](https://portal.azure.com) e selecione sua assinatura. 

2. Ao escolher o nome de sua assinatura, a URL resultante incluirá a ID da assinatura.  Se você tiver problemas para localizar sua ID da assinatura, consulte este [artigo do suporte da Microsoft](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b) para obter dicas sobre como encontrar sua ID de assinatura.

3. Encontre sua ID do Grupo do Azure AD. O console do Lookout dá suporte a 2 níveis de acesso:  
   * **Acesso completo:** O administrador do Azure AD pode criar um grupo de usuários que têm Acesso Completo e, opcionalmente, criar um grupo de usuários que terá Acesso Restrito.  Somente os usuários nesses grupos poderão fazer logon no **console do Lookout**.
   * **Acesso Restrito:** Os usuários nesse grupo não terão acesso a vários módulos relacionados à configuração e ao registro do console do Lookout, tendo acesso somente leitura ao módulo **Política de Segurança** do console do Lookout.  

     > [!TIP] 
     > Para obter mais detalhes sobre as permissões, leia [este artigo](https://personal.support.lookout.com/hc/articles/114094105653) no site do Lookout.

     > [!NOTE] 
     > A **ID de Objeto do Grupo** está na página **Propriedades** do grupo no **portal de gerenciamento do Azure AD**.

4. Depois de obter essas informações, contate o suporte do Lookout (email: enterprisesupport@lookout.com). O suporte do Lookout trabalhará com seu contato principal para integrar sua assinatura e criar a conta do Lookout Enterprise, usando as informações coletadas.

## <a name="configure-your-subscription"></a>Configurar sua assinatura

1. Depois que o suporte do Lookout criar sua conta Lookout Enterprise, um email do Lookout será enviado para o contato principal de sua empresa com um link para a URL de logon: <https://aad.lookout.com/les?action=consent>.

2. O primeiro logon no console do Lookout deve ser feito com uma conta de usuário com a função Administrador Global do Azure AD para registrar seu locatário do Azure AD. Mais tarde, a conexão não exigirá esse nível de privilégio do Azure AD. Uma página de consentimento será exibida. Escolha **Aceitar** para concluir o registro. Depois de aceita e consentir, você será redirecionado para o Console do Lookout.

   ![captura de tela da página de primeiro logon do console do Lookout](./media/lookout_mtp_initial_login.png)

3. No [Console do Lookout](https://aad.lookout.com), no módulo **Sistema**, escolha a guia **Conectores** e selecione **Intune**.

   ![Imagem do console do Lookout com a opção Intune na guia Conectores](./media/lookout_mtp_setup-intune-connector.png)

4. Acesse **Conectores** > **Configurações de Conexão** e especifique a **Frequência de Pulsação** em minutos.

   ![Imagem de guia Configurações de conexão com a frequência de pulsação configurada](./media/lookout-mtp-connection-settings.png)

## <a name="configure-enrollment-groups"></a>Configurar grupos de registro
1. Como prática recomendada, crie um grupo de segurança do Azure AD no [Portal de Gerenciamento do Azure AD](https://manage.windowsazure.com) que contém um pequeno número de usuários para testar a integração do Lookout.

    > [!NOTE] 
    > Todos os dispositivos de usuários compatíveis com o Lookout e registrados pelo Intune em um grupo de registro no Azure AD identificados e compatíveis são registrados e qualificados para ativação no console do Lookout MTD.

2. No [Console do Lookout](https://aad.lookout.com), no módulo **Sistema**, escolha a guia **Conectores** e selecione **Gerenciamento de Registro** para definir um conjunto de usuários cujos dispositivos devem ser registrados no Lookout. Adicione o **Nome de Exibição** do grupo de segurança do Azure AD para o registro.

    ![captura de tela da página de registro do conector do Intune](./media/lookout-mtp-enrollment.png)

    >[!IMPORTANT]
    > O **Nome de Exibição** diferencia maiúsculas de minúsculas, conforme mostrado nas **Propriedades** do grupo de segurança no Portal do Azure. Conforme é mostrado na imagem abaixo, o **Nome de Exibição** do grupo de segurança apresenta letras minúsculas concatenadas, enquanto o título apresenta todas as letras minúsculas. No console do Lookout, faça a correspondência de maiúsculas e minúsculas do **Nome de Exibição** do grupo de segurança.
    >![Imagem do portal do Azure, serviço Azure Active Directory, página de propriedades](./media/aad-group-display-name.png)

    >[!NOTE] 
    >A melhor prática é deixar o padrão (5 minutos) para o incremento de tempo para verificar se há novos dispositivos. Limitações atuais: **o Lookout não pode validar nomes de exibição de grupos:** Verifique se o campo **NOME DE EXIBIÇÃO** no Portal do Azure corresponde exatamente ao grupo de segurança do Azure AD. **Não há suporte para a criação de grupos de aninhamento:**  Os grupos de segurança do Azure AD usados no Lookout devem conter somente usuários. Eles não podem conter outros grupos.

3.  Depois que um grupo for adicionado, na próxima vez que um usuário abrir o aplicativo Lookout for Work em seu dispositivo com suporte, o dispositivo estará ativado no Lookout.

4.  Quando estiver satisfeito com os resultados, estenda o registro para grupos de usuários adicionais.

## <a name="configure-state-sync"></a>Configurar a sincronização de estado
Na opção **Sincronização de Estado**, especifique o tipo de dados que deve ser enviado ao Intune.  O status do dispositivo e o status da ameaça são necessários para que a integração do Lookout com o Intune funcione corretamente. Essas configurações são habilitadas por padrão.

## <a name="configure-error-report-email-recipient-information"></a>Configurar informações do destinatário do email de relatório de erros
Na opção **Gerenciamento de Erros**, insira o endereço de email que deve receber os relatórios de erros.

![captura de tela da página de gerenciamento de erros do conector do Intune](./media/lookout-mtp-connector-error-notifications.png)

## <a name="configure-enrollment-settings"></a>Definir configurações de registro
No módulo **Sistema**, na página **Conectores**, especifique o número de dias antes que um dispositivo seja considerado desconectado.  Dispositivos desconectados são considerados não compatíveis e serão impedidos de acessar seus aplicativos corporativos com base nas políticas de acesso condicional do Intune. Você pode especificar valores entre 1 e 90 dias.

![Configurações de registro do Lookout no módulo Sistema](./media/lookout-console-enrollment-settings.png)

## <a name="configure-email-notifications"></a>Configurar notificações por email
Se desejar receber alertas de ameaças por email, conecte-se ao [console do Lookout](https://aad.lookout.com) com a conta de usuário que deverá receber as notificações. Na guia **Preferências** do módulo **Sistema**, escolha os níveis de ameaças que devem emitir notificações e defina-os como **ATIVADO**. Salve as alterações.

![captura de tela da página Preferências com a conta de usuário exibida](./media/lookout-mtp-email-notifications.png) Se não quiser receber notificações por email, defina as notificações como **DESATIVADO** e salve as alterações.

### <a name="configure-threat-classification"></a>Configurar a classificação de ameaças
A Defesa contra Ameaças Móveis do Lookout classifica ameaças móveis de vários tipos. As [classificações de ameaças do Lookout](https://personal.support.lookout.com/hc/articles/114094130693) têm níveis de risco padrão associados a elas. Elas podem ser alteradas a qualquer momento de acordo com os requisitos de sua empresa.

![captura de tela da página de política mostrando ameaças e classificações](./media/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Os níveis de risco são um aspecto importante da Defesa contra Ameaças Móveis, porque a integração com o Intune calcula a conformidade do dispositivo de acordo com esses níveis de risco em tempo de execução. O administrador do Intune define uma regra na política para identificar um dispositivo não compatível, se ele tem uma ameaça ativa com um nível mínimo igual a **Alto**, **Médio** ou **Baixo**. A política de classificação de ameaças na Defesa contra Ameaças Móveis do Lookout alimenta diretamente o cálculo de conformidade no Intune.

## <a name="watching-enrollment"></a>Verificar o registro
Quando a instalação estiver concluída, a Defesa contra Ameaças Móveis do Lookout começa a sondar o Azure AD em busca de dispositivos que correspondem aos grupos de registro especificados.  Você pode encontrar informações sobre os dispositivos registrados no módulo Dispositivos.  O status inicial dos dispositivos é mostrado como pendente.  O status do dispositivo será alterado quando o aplicativo Lookout for Work estiver instalado, aberto e ativado no dispositivo.  Para ver detalhes de como fazer o aplicativo Lookout for Work ser enviado por push para o dispositivo, consulte [Adicionar aplicativos Lookout for Work com o Intune](mtd-apps-ios-app-configuration-policy-add-assign.md).

## <a name="next-steps"></a>Próximas etapas

[Configurar os aplicativos do Lookout](mtd-apps-ios-app-configuration-policy-add-assign.md)
