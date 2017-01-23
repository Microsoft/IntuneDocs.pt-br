---
title: Configurar sua assinatura com o Lookout | Microsoft Docs
description: "Este tópico fornece detalhes de como configurar a proteção de ameaça do dispositivo Lookout."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6b83d06ecbe6e202bf022444c288e0866b3507c6
ms.openlocfilehash: fc6a729ecd51adba2581c5b2ca4b3665970d4563


---

# <a name="set-up-your-subscription-for-lookout-device-threat-protection"></a>Configurar sua assinatura para a proteção contra ameaças ao dispositivo do Lookout

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As etapas a seguir são necessárias para configurar a proteção contra ameaças ao dispositivo do Lookout:

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
| 1 | [Verificar o registro](#watching-enrollment) |


> [!IMPORTANT]
> Um locatário existente do Lookout Mobile Endpoint Security que não está associado ao seu locatário do Azure AD não pode ser usado para a integração com o Azure AD e o Intune. Entre em contato com o suporte do Lookout para criar um novo locatário do Lookout Mobile Endpoint Security. Use o novo locatário para carregar os usuários do Azure AD.

## <a name="collect-azure-ad-information"></a>Coletar informações do Azure AD
O locatário do Lookout Mobility Endpoint Security será associado à sua assinatura do Azure AD para integrar o Lookout com o Intune. Para habilitar sua assinatura do serviço de proteção contra ameaças ao dispositivo, o suporte do Lookout (enterprisesupport@lookout.com) precisa das seguintes informações:  

* **ID do locatário do Azure AD**
* **ID do objeto de grupo do Azure AD** para acesso **completo** ao Lookout
* **ID do objeto de grupo do Azure AD** para acesso **restrito** ao Lookout (opcional)

Use as etapas a seguir para coletar as informações de que precisa para fornecer à equipe de suporte do Lookout.  

1. Entre no [portal de gerenciamento do Azure AD](https://manage.windowsazure.com) e selecione sua assinatura. 
  ![captura de tela da página do Azure AD mostrando o nome do locatário](../media/mtp/aad_tenant_name.png)
2. Ao escolher o nome de sua assinatura, a URL resultante incluirá a ID da assinatura.  Se você tiver problemas para localizar sua ID da assinatura, consulte este [artigo do suporte da Microsoft](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US) para obter dicas sobre como encontrar sua ID de assinatura.   
3. Encontre sua ID do Grupo do Azure AD. O console do Lookout dá suporte a 2 níveis de acesso:  
  * **Acesso Completo:** o administrador do Azure AD pode criar um grupo para usuários que terão Acesso completo e, opcionalmente, pode criar um grupo para usuários que terão Acesso restrito.  Somente os usuários nesses grupos poderão fazer logon no **console do Lookout**.
  * **Acesso restrito:** os usuários neste grupo não terão acesso a vários módulos relacionados à configuração e ao registro do console do Lookout, e terão acesso somente leitura ao módulo **Política de Segurança** do console do Lookout.  

  Para obter mais detalhes sobre as permissões, leia [este artigo](https://personal.support.lookout.com/hc/en-us/articles/114094105653) no site do Lookout.

  A **ID do objeto do grupo** está na página **Propriedades** do grupo no **console de gerenciamento do Azure AD**.

  ![captura de tela da página de propriedades com o campo GroupID realçado](../media/mtp/aad_group_object_id.png)

4. Depois de coletar essas informações, contate o suporte do Lookout (email: enterprisesupport@lookout.com)). O suporte do Lookout trabalhará com seu contato principal para integrar sua assinatura e criar a conta do Lookout Enterprise, usando as informações coletadas.

## <a name="configure-your-subscription"></a>Configurar sua assinatura
1. Depois que o suporte do Lookout criar sua conta Lookout Enterprise, um email do Lookout será enviado para o contato principal de sua empresa com um link para a URL de logon: https://aad.lookout.com/les?action=consent.

2.  O primeiro logon no console do Lookout deve ser feito com uma conta de usuário com a função Administrador Global do Azure AD para registrar seu locatário do Azure AD. Mais tarde, a conexão não exigirá esse nível de privilégio do Azure AD. Uma página de consentimento será exibida. Escolha **Aceitar** para concluir o registro.

  ![captura de tela da primeira página de logon do console do Lookout](../media/mtp/lookout_mtp_initial_login.png) Após aceitar e dar o consentimento, você será redirecionado para o Console do Lookout.

  Consulte [Solucionar problemas de integração do Lookout](https://docs.microsoft.com/intune/troubleshoot/troubleshooting-lookout-integration) para obter ajuda com problemas de logon.

3.  No [Console do Lookout](https://aad.lookout.com), no módulo **Sistema**, escolha a guia **Conectores** e selecione **Intune**.

  ![captura de tela do console do Lookout com a guia Conectores aberta e a opção Intune realçada](../media/mtp/lookout_mtp_setup-intune-connector.png)

4.  Acesse **Conectores** > **Configurações de Conexão** e especifique a **Frequência de Pulsação** em minutos.   

  ![captura de tela da guia Configurações de conexão mostrando a frequência de pulsação configurada](../media/mtp/lookout-mtp-connection-settings.png)

## <a name="configure-enrollment-groups"></a>Configurar grupos de registro
1. Como prática recomendada, crie um grupo de segurança do Azure AD no [Portal de Gerenciamento do Azure AD](https://manage.windowsazure.com) que contém um pequeno número de usuários para testar a integração do Lookout.  

  Todos os dispositivos de usuários com suporte no Lookout e registrados pelo Intune em um grupo de registro no Azure AD identificados e com suporte são registrados e qualificados para ativação na proteção contra ameaças ao dispositivo do Lookout.  

2. No [Console do Lookout](https://aad.lookout.com), no módulo **Sistema**, escolha a guia **Conectores** e selecione **Gerenciamento de Registro** para definir um conjunto de usuários cujos dispositivos devem ser registrados no Lookout. Adicione o **Nome de Exibição** do grupo de segurança do Azure AD para o registro.

  ![captura de tela da página de registro do conector do Intune](../media/mtp/lookout-mtp-enrollment.png)

  >[!IMPORTANT]
  > O **Nome de Exibição** diferencia maiúsculas de minúsculas, conforme mostrado nas **Propriedades** do grupo de segurança no Portal do Azure. Conforme mostrado na imagem abaixo, o **Nome de Exibição** do grupo de segurança tem minúsculas concatenadas, enquanto o título tem todas as letras minúsculas. No console do Lookout, faça a correspondência de maiúsculas e minúsculas do **Nome de Exibição** do grupo de segurança.
  >![captura de tela do portal do Azure, serviço do Azure Active Directory, página de propriedades](../media/mtp/aad-group-display-name.png)

  A melhor prática é deixar o padrão (5 minutos) para o incremento de tempo para verificar se há novos dispositivos.

  **Limitações atuais:**  
  * O Lookout não pode validar nomes de exibição de grupos.  Verifique se o campo **NOME DE EXIBIÇÃO** no Portal do Azure corresponde exatamente ao grupo de segurança do Azure AD.
  * Não há suporte para a criação de grupos de aninhamento.  Os grupos de segurança do Azure AD usados no Lookout devem conter somente usuários. Eles não podem conter outros grupos.

3.  Depois que um grupo for adicionado, na próxima vez que um usuário abrir o aplicativo Lookout for Work em seu dispositivo com suporte, o dispositivo estará ativado no Lookout.

4.  Quando estiver satisfeito com os resultados, estenda o registro para grupos de usuários adicionais.

## <a name="configure-state-sync"></a>Configurar a sincronização de estado
Na opção **Sincronização de Estado**, especifique o tipo de dados que deve ser enviado ao Intune.  O status do dispositivo e o status da ameaça são necessários para que a integração do Lookout com o Intune funcione corretamente.  Eles são habilitados por padrão.

## <a name="configure-error-report-email-recipient-information"></a>Configurar informações do destinatário do email de relatório de erros
Na opção **Gerenciamento de Erros**, insira o endereço de email que deve receber os relatórios de erros.

![captura de tela da página de gerenciamento de erros do conector do Intune](../media/mtp/lookout-mtp-connector-error-notifications.png)

## <a name="configure-enrollment-settings"></a>Definir configurações de registro
No módulo **Sistema**, na página **Conectores**, especifique o número de dias antes que um dispositivo seja considerado desconectado.  Dispositivos desconectados são considerados não compatíveis e serão impedidos de acessar seus aplicativos da empresa com base nas políticas de acesso condicional do Intune. Você pode especificar valores entre 1 e 90 dias.

![](../media/mtp/lookout-console-enrollment-settings.png)

## <a name="configure-email-notifications"></a>Configurar notificações por email
Se desejar receber alertas de ameaças por email, conecte-se ao [console do Lookout](https://aad.lookout.com) com a conta de usuário que deverá receber as notificações. Na guia **Preferências** do módulo **Sistema**, escolha os níveis de ameaças que devem emitir notificações e defina-os como **ATIVADO**. Salve as alterações.

![captura de tela da página Preferências com a conta de usuário exibida](../media/mtp/lookout-mtp-email-notifications.png) Se não quiser receber notificações por email, defina as notificações como **DESATIVADO** e salve as alterações.

### <a name="configure-threat-classification"></a>Configurar a classificação de ameaças
A proteção contra ameaça do dispositivo Lookout classifica ameaças móveis de vários tipos. As [classificações de ameaças do Lookout](http://personal.support.lookout.com/hc/en-us/articles/114094130693) têm níveis de risco padrão associados a elas. Elas podem ser alteradas a qualquer momento de acordo com os requisitos de sua empresa.

![captura de tela da página de política mostrando ameaças e classificações](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Os níveis de risco são um aspecto importante da proteção contra ameaças ao dispositivo, porque a integração com o Intune calcula a conformidade do dispositivo de acordo com esses níveis de risco em tempo de execução. O administrador do Intune define uma regra na política para identificar um dispositivo que não está em conformidade se ele tem uma ameaça ativa com um nível mínimo de **Alto**, **Médio** ou **Baixo**. A política de classificação de ameaças na proteção contra ameaças do dispositivo Lookout alimenta diretamente o cálculo de conformidade no Intune.

## <a name="watching-enrollment"></a>Verificar o registro
Quando a instalação estiver concluída, a proteção contra ameaça do dispositivo Lookout começa a sondar o Azure AD em busca de dispositivos que correspondem aos grupos de registro especificados.  Você pode encontrar informações sobre os dispositivos registrados no módulo Dispositivos.  O status inicial dos dispositivos é pendente.  O status do dispositivo será alterado depois que o aplicativo Lookout for Work for instalado, aberto e ativado no dispositivo.  Para obter detalhes sobre como fazer com que o aplicativo Lookout for Work seja enviado por push ao dispositivo, consulte o tópico [Configurar e implantar o aplicativo Lookout for Work](configure-and-deploy-lookout-for-work-apps.md).
## <a name="next-steps"></a>Próximas etapas
[Habilitar a conexão da Consulta MTP no Intune](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Dec16_HO4-->


