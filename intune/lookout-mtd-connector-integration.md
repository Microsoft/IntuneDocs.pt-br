---
title: "Configurar a integração do Lookout com o Intune"
titleSuffix: Intune on Azure
description: Configurar sua assinatura do Lookout com o Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c6af49be38e760e14824eb380e4cf3467a695df8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
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

2. Ao escolher o nome de sua assinatura, a URL resultante incluirá a ID da assinatura.  Se você tiver problemas para localizar sua ID da assinatura, consulte este [artigo do suporte da Microsoft](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b) para obter dicas sobre como encontrar sua ID de assinatura.

3. Encontre sua ID do Grupo do Azure AD. O console do Lookout dá suporte a 2 níveis de acesso:  
  * **Acesso completo:** o administrador do Azure AD pode criar um grupo de usuários que terá acesso completo e, opcionalmente, criar um grupo de usuários que terá acesso restrito.  Somente os usuários nesses grupos poderão fazer logon no **console do Lookout**.
  * **Acesso restrito:** os usuários neste grupo não terão acesso a várias configurações e módulos relacionados ao registro do console do Lookout e terão acesso somente leitura ao módulo de **Política de segurança** do console do Lookout.  

    > [!TIP] 
    > Para obter mais detalhes sobre as permissões, leia [este artigo](https://personal.support.lookout.com/hc/articles/114094105653) no site do Lookout.

    > [!NOTE] 
    > A **ID de Objeto do Grupo** está na página **Propriedades** do grupo no **portal de gerenciamento do Azure AD**.

4. Depois de obter essas informações, contate o suporte do Lookout (email: enterprisesupport@lookout.com). O suporte do Lookout trabalhará com seu contato principal para integrar sua assinatura e criar a conta do Lookout Enterprise, usando as informações coletadas.

## <a name="configure-your-subscription"></a>Configurar sua assinatura

1. Depois que o suporte do Lookout criar sua conta Lookout Enterprise, um email do Lookout será enviado para o contato principal de sua empresa com um link para a URL de logon: https://aad.lookout.com/les?action=consent.

2.  O primeiro logon no console do Lookout deve ser feito com uma conta de usuário com a função Administrador Global do Azure AD para registrar seu locatário do Azure AD. Mais tarde, a conexão não exigirá esse nível de privilégio do Azure AD. Uma página de consentimento será exibida. Escolha **Aceitar** para concluir o registro. Depois de aceita e consentir, você será redirecionado para o Console do Lookout.

    ![captura de tela da página de primeiro logon do console do Lookout](./media/lookout_mtp_initial_login.png)
    > [OBERVAÇÃO] Consulte [Solucionar problemas de integração do Lookout](https://docs.microsoft.com/intune/troubleshoot/troubleshooting-lookout-integration) para obter ajuda com problemas de logon.

3.  No [Console do Lookout](https://aad.lookout.com), no módulo **Sistema**, escolha a guia **Conectores** e selecione **Intune**.

    ![captura de tela do console do Lookout com a guia Conectores aberta e a opção Intune realçada](./media/lookout_mtp_setup-intune-connector.png)

4.  Acesse **Conectores** > **Configurações de Conexão** e especifique a **Frequência de Pulsação** em minutos.

    ![captura de tela da guia Configurações de conexão mostrando a frequência de pulsação configurada](./media/lookout-mtp-connection-settings.png)

## <a name="configure-enrollment-groups"></a>Configurar grupos de registro
1. Como prática recomendada, crie um grupo de segurança do Azure AD no [Portal de Gerenciamento do Azure AD](https://manage.windowsazure.com) que contém um pequeno número de usuários para testar a integração do Lookout.

    > [OBSERVAÇÃO] Todos os dispositivos de usuários com suporte no Lookout e registrados pelo Intune em um grupo de registro no Azure AD identificados e com suporte são registrados e qualificados para ativação no console do Lookout MTD.

2. No [Console do Lookout](https://aad.lookout.com), no módulo **Sistema**, escolha a guia **Conectores** e selecione **Gerenciamento de Registro** para definir um conjunto de usuários cujos dispositivos devem ser registrados no Lookout. Adicione o **Nome de Exibição** do grupo de segurança do Azure AD para o registro.

    ![captura de tela da página de registro do conector do Intune](./media/lookout-mtp-enrollment.png)

    >[!IMPORTANT]
    > O **Nome de Exibição** diferencia maiúsculas de minúsculas, conforme mostrado nas **Propriedades** do grupo de segurança no Portal do Azure. Conforme mostrado na imagem abaixo, o **Nome de Exibição** do grupo de segurança tem minúsculas concatenadas, enquanto o título tem todas as letras minúsculas. No console do Lookout, faça a correspondência de maiúsculas e minúsculas do **Nome de Exibição** do grupo de segurança.
    >![captura de tela do portal do Azure, serviço do Azure Active Directory, página de propriedades](./media/aad-group-display-name.png)

    >[!NOTE] 
    >A melhor prática é deixar o padrão (5 minutos) para o incremento de tempo para verificar se há novos dispositivos. Limitações atuais, **O Lookout não consegue validar os nomes de exibição do grupo:** Verifique se o campo **NOME DE EXIBIÇÃO** no Portal do Azure corresponde exatamente ao grupo de segurança do Azure AD. **Não há suporte para a criação de grupos aninhados:** os grupos de segurança do Azure AD usados no Lookout devem conter somente usuários. Eles não podem conter outros grupos.

3.  Depois que um grupo for adicionado, na próxima vez que um usuário abrir o aplicativo Lookout for Work em seu dispositivo com suporte, o dispositivo estará ativado no Lookout.

4.  Quando estiver satisfeito com os resultados, estenda o registro para grupos de usuários adicionais.

## <a name="configure-state-sync"></a>Configurar a sincronização de estado
Na opção **Sincronização de Estado**, especifique o tipo de dados que deve ser enviado ao Intune.  O status do dispositivo e o status da ameaça são necessários para que a integração do Lookout com o Intune funcione corretamente. Essas configurações são habilitadas por padrão.

## <a name="configure-error-report-email-recipient-information"></a>Configurar informações do destinatário do email de relatório de erros
Na opção **Gerenciamento de Erros**, insira o endereço de email que deve receber os relatórios de erros.

![captura de tela da página de gerenciamento de erros do conector do Intune](./media/lookout-mtp-connector-error-notifications.png)

## <a name="configure-enrollment-settings"></a>Definir configurações de registro
No módulo **Sistema**, na página **Conectores**, especifique o número de dias antes que um dispositivo seja considerado desconectado.  Dispositivos desconectados são considerados não compatíveis e serão impedidos de acessar seus aplicativos da empresa com base nas políticas de acesso condicional do Intune. Você pode especificar valores entre 1 e 90 dias.

![Configurações de registro do Lookout](./media/lookout-console-enrollment-settings.png)

## <a name="configure-email-notifications"></a>Configurar notificações por email
Se desejar receber alertas de ameaças por email, conecte-se ao [console do Lookout](https://aad.lookout.com) com a conta de usuário que deverá receber as notificações. Na guia **Preferências** do módulo **Sistema**, escolha os níveis de ameaças que devem emitir notificações e defina-os como **ATIVADO**. Salve as alterações.

![captura de tela da página Preferências com a conta de usuário exibida](./media/lookout-mtp-email-notifications.png) Se não quiser receber notificações por email, defina as notificações como **DESATIVADO** e salve as alterações.

### <a name="configure-threat-classification"></a>Configurar a classificação de ameaças
A Defesa contra Ameaças Móveis do Lookout classifica ameaças móveis de vários tipos. As [classificações de ameaças do Lookout](http://personal.support.lookout.com/hc/articles/114094130693) têm níveis de risco padrão associados a elas. Elas podem ser alteradas a qualquer momento de acordo com os requisitos de sua empresa.

![captura de tela da página de política mostrando ameaças e classificações](./media/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Os níveis de risco são um aspecto importante da Defesa contra Ameaças Móveis, porque a integração com o Intune calcula a conformidade do dispositivo de acordo com esses níveis de risco em tempo de execução. O administrador do Intune define uma regra na política para identificar um dispositivo que não está em conformidade se ele tem uma ameaça ativa com um nível mínimo de **Alto**, **Médio** ou **Baixo**. A política de classificação de ameaças na Defesa contra Ameaças Móveis do Lookout alimenta diretamente o cálculo de conformidade no Intune.

## <a name="watching-enrollment"></a>Verificar o registro
Quando a instalação estiver concluída, a Defesa contra Ameaças Móveis do Lookout começa a sondar o Azure AD em busca de dispositivos que correspondem aos grupos de registro especificados.  Você pode encontrar informações sobre os dispositivos registrados no módulo Dispositivos.  O status inicial dos dispositivos é mostrado como pendente.  O status do dispositivo será alterado quando o aplicativo Lookout for Work estiver instalado, aberto e ativado no dispositivo.  Para ver detalhes sobre como fazer o aplicativo Lookout for Work ser enviado por push para o dispositivo, consulte o tópico [Adicionar aplicativos Lookout for Work com o Intune](mtd-apps-ios-app-configuration-policy-add-assign.md).
## <a name="next-steps"></a>Próximas etapas
[Habilitar conexão do Lookout MTD no Intune](mtd-connector-enable.md)