---
title: Configurar sua assinatura com Lookout | Microsoft Intune
description: "Este tópico fornece detalhes de como configurar a proteção de ameaça do dispositivo Lookout."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1187ad3fdd4a427333d610686698c1f806c6ee33
ms.openlocfilehash: 1d8cdaa36a852fba5912c250daa500e16bd3b661


---

# <a name="set-up-your-subscription-for-lookout-device-threat-protection"></a>Configurar sua assinatura para a proteção contra ameaça do dispositivo Lookout
Para preparar sua assinatura para o serviço de proteção contra ameaça do dispositivo Lookout, o suporte do Lookout (enterprisesupport@lookout.com) precisa das seguintes informações sobre sua assinatura do Azure Active Directory (Azure AD). O locatário do Lookout Mobility Endpoint Security será associado à sua assinatura do Azure AD para integrar o Lookout com o Intune. 

* **ID do locatário do Azure AD**
* **ID do objeto de grupo do Azure AD** para acesso **completo** ao Lookout
* **ID do objeto de grupo do Azure AD** para acesso **restrito** ao Lookout (opcional)

> [!IMPORTANT]
> Um locatário existente do Lookout Mobile Endpoint Security que não está associado ao seu locatário do Azure AD não pode ser usado para a integração com o Azure AD e o Intune. Entre em contato com o suporte do Lookout para criar um novo locatário do Lookout Mobile Endpoint Security. Use o novo locatário para carregar os usuários do Azure AD.

Use a seção a seguir para coletar as informações que você precisa fornecer à equipe de suporte do Lookout.  

## <a name="get-your-azure-ad-information"></a>Obter as informações do Azure AD
### <a name="azure-ad-tenant-id"></a>ID do locatário do Azure AD
Entre no [portal de gerenciamento do Azure AD](https://manage.windowsazure.com) e selecione sua assinatura. 

![captura de tela da página do Azure AD mostrando o nome do locatário](../media/mtp/aad_tenant_name.png) Ao escolher o nome da sua assinatura, a URL resultante inclui a ID da assinatura.  Se você tiver problemas para localizar sua ID da assinatura, consulte este [artigo do suporte da Microsoft](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US) para obter dicas sobre como encontrar sua ID de assinatura.   
### <a name="azure-ad-group-id"></a>ID do grupo do Azure AD
O console do Lookout dá suporte a 2 níveis de acesso:  
* **Acesso Completo:** o administrador do Azure AD pode criar um grupo para usuários que terão Acesso completo e, opcionalmente, pode criar um grupo para usuários que terão Acesso restrito.  Somente os usuários nesses grupos poderão fazer logon no **console do Lookout**.
* **Acesso restrito:** os usuários neste grupo não terão acesso a vários módulos relacionados à configuração e ao registro do console do Lookout, e terão acesso somente leitura ao módulo **Política de Segurança** do console do Lookout.  

Para obter mais detalhes sobre as permissões, leia [este artigo](https://personal.support.lookout.com/hc/en-us/articles/114094105653) no site do Lookout.

A **ID do objeto do grupo** está na página **Propriedades** do grupo no **console de gerenciamento do Azure AD**.

![captura de tela da página de propriedades com o campo GroupID realçado](../media/mtp/aad_group_object_id.png)

Depois de reunir essas informações, contate o suporte do Lookout (email: enterprisesupport@lookout.com).

O suporte do Lookout trabalhará com seu contato principal para integrar sua assinatura e criar a conta do Lookout Enterprise, usando as informações coletadas.


## <a name="configure-your-subscription-with-lookout-device-threat-protection"></a>Configurar sua assinatura com a proteção contra ameaças do dispositivo Lookout
### <a name="step-1-set-up-your-device-threat-protection"></a>Etapa 1: Configurar sua proteção contra ameaças do dispositivo
Após o suporte do Lookout criar sua conta Lookout Enterprise, você poderá entrar no console do Lookout.   Um email do Lookout é enviado para o contato principal da sua empresa com um link da URL de logon: https://aad.lookout.com/les?action=consent

Você precisará usar uma conta de usuário com a função de Administrador Global do Azure AD quando fizer logon pela primeira vez no console do Lookout, uma vez que o Lookout exige isso para registrar seu locatário do Azure AD.   Conexões posteriores não exigirão que o usuário tenha esse nível de privilégio do Azure AD.  Nesse primeiro logon, será exibida uma página de consentimento. Escolha **Aceitar** para concluir o registro.

![captura de tela da primeira página de logon do console do Lookout](../media/mtp/lookout_mtp_initial_login.png) Após aceitar e dar o consentimento, você será redirecionado para o Console do Lookout. Logons posteriores, após o registro inicial, podem ser feitos usando a URL: https://aad.lookout.com

Consulte o [artigo de solução de problemas](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration) se você se deparar com problemas de logon.

As próximas etapas destacam as tarefas que devem ser realizadas para concluir a configuração do Lookout dentro do [Console do Lookout](https://aad.lookout.com).

### <a name="step-2-configure-the-intune-connector"></a>Etapa 2: Configurar o Conector do Intune

1.  No console do Lookout, no módulo **Sistema**, escolha a guia **Conectores** e selecione **Intune**.

  ![captura de tela do console do Lookout com a guia Conectores aberta e a opção Intune realçada](../media/mtp/lookout_mtp_setup-intune-connector.png)

2.  Na opção de configurações de conexão, configure a frequência de pulsação em minutos.  O conector do Intune está pronto.  

  ![captura de tela da guia Configurações de conexão mostrando a frequência de pulsação configurada](../media/mtp/lookout-mtp-connection-settings.png)

### <a name="step-3-configure-enrollment-groups"></a>Etapa 3: Configurar grupos de registro
Na opção **Gerenciamento de Registro**, defina um conjunto de usuários cujos dispositivos devem ser registrados no Lookout. A melhor prática é começar com um grupo pequeno de usuários para testar e se familiarizar com o funcionamento da integração.  Quando estiver satisfeito com os resultados de teste, você pode estender o registro para grupos de usuários adicionais.

Para começar a usar os grupos de registros, primeiro defina um grupo de segurança do Azure AD que representaria um bom conjunto de usuários para registrar na proteção contra ameaças do dispositivo. Após ter criado o grupo no Azure AD, no console do Lookout, vá para a opção **Gerenciamento de Registro** e adicione o(s) **Nome(s) de Exibição** do grupo de segurança do Azure AD para registro.

Quando um usuário estiver em um grupo de registro, qualquer um de seus dispositivos que estiver identificado e tiver suporte no Azure AD estará registrado e qualificado para ativação na proteção contra ameaça do dispositivo Lookout.  Na primeira vez que o usuário abrir o aplicativo Lookout for Work em seu dispositivo com suporte, ele será ativado no Lookout.

![captura de tela da página de registro do conector do Intune](../media/mtp/lookout-mtp-enrollment.png)

A melhor prática é deixar o padrão (5 minutos) para o incremento de tempo para verificar se há novos dispositivos.

>[!IMPORTANT]
> O nome de exibição diferencia maiúsculas de minúsculas.  Use o **Nome de Exibição** conforme exibido na página **Propriedades** do grupo de segurança no portal do Azure. Observe na imagem abaixo que na página **Propriedades** do grupo de segurança, o nome de exibição segue o padrão camelCase.  No entanto, o título é exibido com todas as letras minúsculas e não deve ser usado para entrar no console do Lookout.
>![captura de tela do portal do Azure, serviço do Azure Active Directory, página de propriedades](../media/mtp/aad-group-display-name.png)

A versão atual tem as limitações a seguir:  
* Não há validação para os nomes de exibição do grupo.  Certifique-se de usar o valor no campo **NOME DE EXIBIÇÃO** mostrado no portal do Azure para o grupo de segurança do Azure AD.
* Atualmente, não há suporte para a criação de grupos dentro de grupos.  Os grupos de segurança do Azure AD especificados devem conter apenas usuários e não grupos aninhados.


### <a name="step-4-configure-state-sync"></a>Etapa 4: Configurar a sincronização de estado
Na opção **Sincronização de Estado**, especifique o tipo de dados que deve ser enviado ao Intune.  No momento, você precisa habilitar o status do dispositivo e o status de ameaça para que a integração do Lookout com o Intune funcione corretamente.  Eles são habilitados por padrão.
### <a name="step-5-configure-error-report-email-recipient-information"></a>Etapa 5: Configurar informações do destinatário do email de relatório de erros
Na opção **Gerenciamento de Erros**, insira o endereço de email que deve receber os relatórios de erros.

![captura de tela da página de gerenciamento de erros do conector do Intune](../media/mtp/lookout-mtp-connector-error-notifications.png)

### <a name="step-6-configure-enrollment-settings"></a>Etapa 6. Definir configurações de registro
No módulo **Sistema**, na página **Conectores**, especifique o número de dias antes que um dispositivo seja considerado desconectado.  Dispositivos desconectados são considerados não compatíveis e serão impedidos de acessar seus aplicativos da empresa com base nas políticas de acesso condicional do Intune. Você pode especificar valores entre 1 e 90 dias.

![](../media/mtp/lookout-console-enrollment-settings.png)

### <a name="step-7-configure-email-notifications"></a>Etapa 7: Configurar notificações por email
Se quiser receber alertas de ameaças por email, entre no [console do Lookout](https://aad.lookout.com) com a conta de usuário que deverá receber as notificações. Na guia **Preferências** do módulo **Sistema**, escolha as notificações desejadas e defina-as como **ATIVADO**. Salve as alterações.

![captura de tela da página Preferências com a conta de usuário exibida](../media/mtp/lookout-mtp-email-notifications.png) Se não quiser receber notificações por email, defina as notificações como **DESATIVADO** e salve as alterações.
### <a name="step-8-configure-threat-classification"></a>Etapa 8: Configurar a classificação das ameaças
A proteção contra ameaça do dispositivo Lookout classifica ameaças móveis de vários tipos. As [classificações de ameaças do Lookout](http://personal.support.lookout.com/hc/en-us/articles/114094130693) têm níveis de risco padrão associados a elas. Eles podem ser alterados a qualquer momento para se adequar aos requisitos da sua empresa.

![captura de tela da página de política mostrando ameaças e classificações](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Os níveis de risco especificados aqui são um aspecto importante da proteção contra ameaça do dispositivo, porque a integração com o Intune calcula a conformidade do dispositivo de acordo com esses níveis de risco no tempo de execução. Em outras palavras, o administrador do Intune definirá uma regra na política para identificar um dispositivo como não compatível se ele tiver uma ameaça ativa com um nível mínimo de alto, médio ou baixo. A política de classificação de ameaças na proteção contra ameaças do dispositivo Lookout alimenta diretamente o cálculo de conformidade no Intune.

## <a name="watching-enrollment"></a>Verificar o registro
Quando a instalação estiver concluída, a proteção contra ameaça do dispositivo Lookout começa a sondar o Azure AD em busca de dispositivos que correspondem aos grupos de registro especificados.  Você pode encontrar informações sobre os dispositivos registrados no módulo Dispositivos.  O status inicial dos dispositivos é pendente.  O status do dispositivo será alterado depois que o aplicativo Lookout for Work for instalado, aberto e ativado no dispositivo.  Para obter detalhes sobre como fazer com que o aplicativo Lookout for Work seja enviado por push ao dispositivo, consulte o tópico [Configurar e implantar o aplicativo Lookout for Work](configure-and-deploy-lookout-for-work-apps.md).
## <a name="next-steps"></a>Próximas etapas
[Habilitar a conexão da Consulta MTP no Intune](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Nov16_HO1-->


