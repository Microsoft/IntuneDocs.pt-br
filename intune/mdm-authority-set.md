---
title: Defina a autoridade de gerenciamento de dispositivo móvel
titlesuffix: Microsoft Intune
description: Defina a autoridade de gerenciamento de dispositivo móvel no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4c1902e319a862c9ffcda5068753f917bf8f4c3f
ms.sourcegitcommit: ada99fefe9a612ed753420116f8c801ac4bf0934
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36232911"
---
# <a name="set-the-mobile-device-management-authority"></a>Defina a autoridade de gerenciamento de dispositivo móvel

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A configuração de autoridade de gerenciamento de dispositivo móvel (MDM) determina como você gerenciar seus dispositivos. Como administrador de TI, você deverá definir uma autoridade MDM antes que os usuários possam registrar dispositivos para gerenciamento.

As configurações possíveis são:

- **Intune Autônomo** – Gerenciamento apenas na nuvem, que você pode definir usando o Portal do Azure. Inclui o conjunto completo de recursos que o Intune oferece. [Definir a autoridade MDM no console do Intune](#set-mdm-authority-to-intune).

- **Intune Híbrido** – Integração da solução de nuvem Intune com o System Center Configuration Manager. Você configura o Intune usando o console do Configuration Manager. [Definir a autoridade do MDM no Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Gerenciamento de dispositivo móvel para o Office 365** – Integração do Office 365 com a solução de nuvem do Intune. Configure o Intune do seu Centro de Administração do Office 365. Inclui um subconjunto dos recursos que estão disponíveis com o Intune Autônomo. Defina a autoridade MDM no Centro de administração do Office 365.

> [!IMPORTANT]
> No Configuration Manager versão 1610 ou posterior e no Microsoft Intune versão 1705, você altera a autoridade de MDM sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes. Para obter detalhes, consulte [O que fazer se você escolher a configuração incorreta de autoridade de MDM](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>Definir a autoridade de MDM como o Intune

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Selecione a faixa laranja para abrir a configuração **Autoridade de Gerenciamento de Dispositivo Móvel**.
4. Em **Autoridade de Gerenciamento de Dispositivo Móvel**, escolha sua autoridade de MDM entre as seguintes opções:
   - **Autoridade de MDM do Intune**
   - **Autoridade de MDM do Configuration Manager**
   - **Nenhum**

   ![Captura da tela da definição de autoridade de gerenciamento de dispositivo móvel do Intune](media/set-mdm-auth.png)

   Uma mensagem indica que você configurou com êxito sua autoridade MDM Intune.

### <a name="workflow-of-intune-administration-ui"></a>Fluxo de trabalho da interface do usuário da administração do Intune
Quando o gerenciamento de dispositivo Android ou Apple está habilitado, o Intune envia informações do dispositivo e do usuário para integração com esses serviços de terceiros, a fim de que eles gerenciem seus respectivos dispositivos.

Os cenários que adicionam um consentimento para compartilhar dados estão inclusos quando:
- Você habilita o Android for Work.
- Você habilita e carrega Apple MDM Push Certificates.
- Você habilita qualquer um dos serviços da Apple, como o Programa de registro de dispositivos, o School Manager ou o Volume Purchase Program.

Em cada caso, a autorização é estritamente relacionada à execução de um serviço de gerenciamento de dispositivo móvel, como a confirmação de que um administrador de TI autorizou dispositivos Google ou Apple a se registrarem. A documentação que trata das informações que serão compartilhadas quando os novos fluxos de trabalho forem ativados está disponível nos seguintes locais:
- [Dados enviados pelo Intune ao Google](https://aka.ms/Data-intune-sends-to-google)
- [Dados enviados pelo Intune à Apple](https://aka.ms/data-intune-sends-to-apple)

## <a name="key-considerations"></a>Principais considerações
Depois de alternar para a nova autoridade de MDM, provavelmente haverá tempo de transição (até oito horas) antes de o dispositivo fazer o check-in e sincronizar com o serviço. Será necessário definir as configurações na nova autoridade de MDM (híbrido) para garantir que os dispositivos registrados continuarão a ser gerenciado e protegidos após a alteração. 
- Os dispositivos devem se conectar com o serviço após a alteração para que as configurações da nova autoridade de MDM (Intune autônomo) substituam as configurações existentes no dispositivo.
- Depois de alterar a autoridade de MDM, algumas das configurações básicas (como perfis) da autoridade de MDM anterior (Intune autônomo) permanecem no dispositivo por até sete dias ou até que o dispositivo se conecte com o serviço pela primeira vez. É recomendável que você configure aplicativos e parâmetros (políticas, perfis, aplicativos etc.) na nova autoridade de MDM (híbrido) assim que possível e implante as configurações para os grupos de usuários que contêm usuários que têm dispositivos registrados. Assim que um dispositivo se conectar ao serviço após a alteração na autoridade de MDM, ele receberá as novas configurações da nova autoridade de MDM e evitará falhas na proteção e no gerenciamento.
- Quando as mesmas categorias de dispositivo existirem no Intune e no Configuration Manager, todas as atribuições de categoria de dispositivo para dispositivos não serão transportadas após você alternar para a nova autoridade de MDM. Para continuar usando categorias de dispositivo, os dispositivos migrados precisam ser adicionados manualmente às coleções apropriadas após a autoridade de MDM ser alterada e serão exibidos no console do Configuration Manager.
- Os dispositivos que não têm usuários associados (normalmente quando você tem o Programa de registro de dispositivos iOS ou cenários de registro em massa) não são migrados para a nova autoridade de MDM. Para esses dispositivos, você precisa chamar o suporte para obter assistência para movê-los para a nova autoridade de MDM.

## <a name="prepare-to-change-the-mdm-authority-to-configuration-manager"></a>Preparar para alterar a autoridade de MDM para o Configuration Manager

Examine as informações a seguir para se preparar para a alteração para a autoridade de MDM:
- Você deve ter o Configuration Manager versão 1610 ou superior para que a opção que altera a autoridade de MDM esteja disponível.
- Pode levar até oito horas para um dispositivo se conectar ao serviço depois que você alterar para a nova autoridade de MDM.
- Crie uma coleção de usuário do Configuration Manager com todos os usuários atualmente gerenciados pelo Intune autônomo que será usada quando você configurar a assinatura do Intune no console do Configuration Manager. Isso ajuda a garantir que o usuário e seus dispositivos terão uma licença do Configuration Manager atribuída e serão gerenciados no ambiente híbrido após a alteração para a autoridade de MDM.
- Verifique se o usuário administrador de TI está nesta coleção de usuário também.  
- Antes da alteração, a autoridade de MDM será exibida como **Definida como Microsoft Intune** (autônomo) no console de administração do Intune.
- A autoridade de MDM deve exibir **Definir para o Microsoft Intune** (locatário autônomo) no console de administração do Microsoft Intune antes da alteração na autoridade de MDM.
    > [!NOTE]    
    > Se sua autoridade de MDM exibir **Gerenciado pelo Intune e pelo Office 365**, os dispositivos de MDM gerenciados pelo Office 365 não são mais gerenciados quando você alterar sua autoridade de MDM para **Configuration Manager** (híbrido). É recomendável que você licencie esses usuários para o Intune ou Enterprise Mobility Suite antes de alterar a autoridade de MDM.   

- No [Console de Administração do Microsoft Intune](http://manage.microsoft.com), remova a função de Gerenciador de Registro de Dispositivos. Para obter detalhes, veja [Excluir um gerenciador de registro de dispositivos do Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune#delete-a-device-enrollment-manager-from-intune).
- Desative os mapeamentos de grupo de dispositivos que estiverem configurados. Para obter detalhes, veja [Categorizar os dispositivos com o mapeamento de grupo de dispositivos no Microsoft Intune](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).
- Não deve haver nenhum impacto perceptível para os usuários finais durante a alteração na autoridade de MDM. No entanto, você talvez deva comunicar esta alteração aos usuários para que eles verifiquem se seus dispositivos estão ligados e se eles conseguem se conectar ao serviço logo após a alteração. Isso garantirá que o máximo de dispositivos possível se conectará e se registrará com o serviço por meio da nova autoridade o mais rápido possível.
- Se você estiver usando o Intune autônomo para gerenciar dispositivos iOS antes da alteração na autoridade de MDM, deverá garantir que o mesmo certificado Apple Push Notification Service (APNs) que era usado no Intune seja renovado e usado para configurar o locatário novamente no Configuration Manager (híbrido).    

    > [!IMPORTANT]  
    > Se um certificado APNs diferente for usado para híbrido, TODOS os dispositivos iOS registrados anteriormente terão o registro cancelado e você precisará passar pelo processo de registrá-los novamente. Antes de fazer a alteração da autoridade de MDM, verifique se você sabe exatamente qual certificado APNs foi usado para gerenciar os dispositivos iOS no Intune. Localize o mesmo certificado listado no Apple Push Certificates Portal (https://identity.apple.com) e verifique se o usuário cuja ID da Apple foi usada para criar o certificado APNs original é identificado e está disponível para renovar o mesmo certificado APNs como parte da mudança para a nova autoridade de MDM.

## <a name="change-the-mdm-authority-to-configuration-manager"></a>Alterar a autoridade de MDM para o Configuration Manager

1. No console do Configuration Manager, no espaço de trabalho **Administração** &gt; **Visão Geral** &gt; **Serviços de Nuvem** &gt; **Assinatura do Microsoft Intune** e selecione para adicionar uma assinatura do Intune.
2. Entre no locatário do Intune que você usou originalmente quando definiu a autoridade de MDM no Intune e clique em **Avançar**.
3. Selecione **Alterar minha autoridade do MDM para o Configuration Manager** e clique em **Avançar**.
4. Selecione a coleção de usuário que conterá todos os usuários que continuarão a ser gerenciados pela nova autoridade de MDM híbrida.
5. Clique em **Próximo** e conclua o assistente. A autoridade de MDM agora é alterada para o **Configuration Manager**.
6. Faça logon no [Console de administração do Microsoft Intune](http://manage.microsoft.com) usando o mesmo locatário do Intune e confirme que a autoridade de MDM foi alterada para **Definir para o Configuration Manager**.
7. Depois de alterar a autoridade de MDM para o Configuration Manager, configure o [registro do iOS](https://docs.microsoft.com/en-us/sccm/mdm/deploy-use/enroll-hybrid-ios-mac) e o [registro do Android](https://docs.microsoft.com/en-us/sccm/mdm/deploy-use/enroll-hybrid-android).
8. No console do Configuration Manager, configure e implante novas configurações e aplicativos da nova autoridade de MDM (híbrido).

Da próxima vez que o dispositivo se conectar ao serviço, ele sincronizará e receberá as novas configurações da nova autoridade de MDM.

## <a name="change-mdm-authority-to-office-365"></a>Alterar a autoridade de MDM para o Office 365

Para ativar o MDM do Office 365, além do Serviço Intune existente, acesse [https://protection.office.com](https://protection.office.com), escolha **Prevenção de Perda de Dados** > **Políticas de Segurança de Dispositivo** > **Exibir uma lista de Dispositivos Gerenciados** > **Vamos começar**.

Para obter mais informações, confira [Configurar o MDM (Gerenciamento de Dispositivo Móvel) no Office 365](https://support.office.com/en-us/article/Set-up-Mobile-Device-Management-MDM-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd).

Se você deseja que os usuários finais sejam gerenciados apenas pelo MDM do Office 365, remova as licenças do Intune e/ou do EMS atribuídas após a ativação do MDM do Office 365.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Limpeza de dispositivo móvel após a expiração do certificado MDM

O certificado do MDM é renovado automaticamente quando os dispositivos móveis estão se comunicando com o serviço Intune. Se os dispositivos móveis forem apagados ou se eles não conseguirem se comunicar com o serviço Intune por um certo período, o certificado do MDM não será renovado. O dispositivo é removido do Portal do Azure 180 dias após a expiração do certificado do MDM.

## <a name="remove-mdm-authority"></a>Remover a autoridade de MDM

A autoridade de MDM não pode ser alterada novamente para Desconhecida. A autoridade de MDM é usada pelos servidores da Microsoft para determinar a qual portal os dispositivos registrados fornecem relatórios (ConfigMGR, Azure Intune, MDM do Office 365).

## <a name="what-to-expect-after-changing-the-mdm-authority"></a>O que esperar após a alteração da autoridade de MDM

- Quando o serviço Intune detectar que a autoridade de MDM de um locatário foi alterada, ele enviará uma mensagem de notificação para todos os dispositivos registrados para fazer check-in e sincronizar com o serviço (isso ocorre fora do check-in agendado regularmente). Portanto, depois que a autoridade de MDM para o locatário tiver sido alterada de Intune autônomo para híbrida, todos os dispositivos que estiverem ligados e online se conectarão ao serviço, receberão a nova autoridade de MDM e serão gerenciados pelo híbrido no futuro. Não há interrupção para o gerenciamento e a proteção desses dispositivos.
- Mesmo para os dispositivos ligados e online durante (ou logo após) a alteração na autoridade de MDM, haverá um atraso de até oito horas (dependendo do horário do próximo check-in regular agendado) antes de os dispositivos serem registrados no serviço sob a nova autoridade de MDM.    

  > [!IMPORTANT]    
  > Entre o momento em que você altera a autoridade de MDM e em que o certificado APNs renovado é carregado para a nova autoridade, novos registros de dispositivo e check-in de dispositivo para dispositivos iOS falharão. Portanto, é importante que você analise e carregue o certificado APNs para a nova autoridade assim que possível após a alteração na autoridade de MDM.

- Os usuários podem alterar rapidamente para a nova autoridade de MDM iniciando manualmente um check-in do dispositivo para o serviço. Os usuários podem fazer isso facilmente pelo aplicativo Portal da Empresa e iniciando uma verificação de conformidade do dispositivo.
- Para validar que as coisas estão funcionando corretamente depois que os dispositivos fizerem check-in e forem sincronizados com o serviço após a alteração na autoridade de MDM, procure os dispositivos no Console do Configuration Manager. Os dispositivos que eram gerenciados anteriormente pelo Intune agora são exibidos como dispositivos gerenciados no console do Configuration Manager.    
- Há um período provisório em que um dispositivo está offline durante a alteração na autoridade de MDM e quando esse dispositivo faz check-in no serviço. Para ajudar a garantir que o dispositivo permaneça protegido e funcionando durante esse intervalo, os seguintes perfis permanecem no dispositivo por até sete dias (ou até que o dispositivo se conecte com a nova autoridade de MDM e receba novas configurações que substituirão as existentes):
    - Perfil de email
    - Perfil da VPN
    - Perfil de certificado
    - Perfil de Wi-Fi
    - Perfis de configuração
- Após você alterar para a nova autoridade de MDM, os dados de conformidade no console de administração do Microsoft Intune poderá levar até uma semana para relatar com precisão. No entanto, os estados de conformidade no Azure Active Directory e no dispositivo serão precisos, então, o dispositivo ainda estará protegido.
- Verifique se as novas configurações que se destinam a substituir as configurações existentes têm o mesmo nome que as anteriores para garantir que as configurações antigas sejam substituídas. Caso contrário, os dispositivos podem acabar com políticas e perfis redundantes.    

  > [!TIP]    
  > Como prática recomendada, você deve criar todos os parâmetros de gerenciamento e as configurações, além das implantações, logo após a alteração para a autoridade de MDM ser concluída. Isso ajuda a garantir que os dispositivos estejam protegidos e sejam gerenciados ativamente durante o período intermediário.

-  Depois de alterar a autoridade MDM, execute as etapas a seguir para validar que os novos dispositivos sejam registrados com êxito para a nova autoridade:   
    - Registrar um novo dispositivo
    - Verifique se o dispositivo registrado recentemente aparece no console do Configuration Manager.
    - Execute uma ação, como bloqueio remoto, do console de administração para o dispositivo. Se a ação for bem-sucedida, isso significará que o dispositivo está sendo gerenciado pela nova autoridade de MDM.
- Se você tiver problemas com dispositivos específicos, poderá cancelar o registro e registrar novamente os dispositivos para que eles se conectem à nova autoridade e sejam gerenciados o mais rápido possível.

## <a name="next-steps"></a>Próximas etapas

Com a autoridade de MDM definida, você pode começar o [registro de dispositivos](device-enrollment.md).