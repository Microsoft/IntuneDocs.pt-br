---
title: Defina a autoridade de gerenciamento de dispositivo móvel
titleSuffix: Microsoft Intune
description: Defina a autoridade de gerenciamento de dispositivo móvel no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19d02694ab5e53dc43e0861c6a427a044bf50648
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502644"
---
# <a name="set-the-mobile-device-management-authority"></a>Defina a autoridade de gerenciamento de dispositivo móvel

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

A configuração de autoridade de gerenciamento de dispositivo móvel (MDM) determina como você gerenciar seus dispositivos. Como administrador de TI, você deverá definir uma autoridade MDM antes que os usuários possam registrar dispositivos para gerenciamento.

As configurações possíveis são:

- **Intune Autônomo** – Gerenciamento apenas na nuvem, que você pode definir usando o Portal do Azure. Inclui o conjunto completo de recursos que o Intune oferece. [Definir a autoridade MDM no console do Intune](#set-mdm-authority-to-intune).

- **Cogerenciamento do Intune**: integração da solução na nuvem do Intune com o System Center Configuration Manager para dispositivos Windows 10. Você configura o Intune usando o console do Configuration Manager. [Configurar o registro automático de dispositivos ao Intune](https://docs.microsoft.com/sccm/comanage/tutorial-co-manage-clients#configure-auto-enrollment-of-devices-to-intune). 

    > [!Important]
    >A integração de novos clientes MDM híbridos foi preterida. Para obter mais informações, confira a postagem no blog [Migrar do Gerenciamento de dispositivo móvel híbrido para o Intune no Azure](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150).

- **Gerenciamento de dispositivo móvel para o Office 365** – Integração do Office 365 com a solução de nuvem do Intune. Configure o Intune no centro de administração do Microsoft 365. Inclui um subconjunto dos recursos que estão disponíveis com o Intune Autônomo. Defina a autoridade de MDM no centro de administração do Microsoft 365.

- **Coexistência do MDM com o Office 365** Você pode ativar e usar o MDM para o Office 365 e o Intune simultaneamente em seu locatário e definir a autoridade de gerenciamento como o Intune ou MDM para Office 365 para cada usuário, a fim de determinar qual serviço será usado para gerenciar os respectivos dispositivos móveis. A autoridade de gerenciamento do usuário é definida com base na licença atribuída ao usuário. Para saber mais, confira o tópico [Coexistência do Microsoft Intune com o MDM para Office 365](https://blogs.technet.microsoft.com/configmgrdogs/2016/01/04/microsoft-intune-co-existence-with-mdm-for-office-365).

## <a name="set-mdm-authority-to-intune"></a>Definir a autoridade de MDM como o Intune

Se você ainda não tiver definido a autoridade de MDM, siga as etapas abaixo. Para migrar do SCCM, confira o tópico [Migrar usuários e dispositivos do MDM híbrido para o Intune autônomo](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

1. Vá até o [Microsoft Intune no portal do Azure](https://aka.ms/intuneportal) e selecione a faixa laranja para abrir a configuração **Autoridade de Gerenciamento do Dispositivo Móvel**. A faixa laranja somente será exibida se você ainda não tiver definido a autoridade de MDM.
2. Em **Autoridade de Gerenciamento de Dispositivo Móvel**, escolha sua autoridade de MDM entre as seguintes opções:
   - **Autoridade de MDM do Intune**
   - **Nenhum**

   ![Captura da tela da definição de autoridade de gerenciamento de dispositivo móvel do Intune](./media/mdm-authority-set/set-mdm-auth.png)

   Uma mensagem indica que você configurou com êxito sua autoridade MDM Intune.

### <a name="workflow-of-intune-administration-ui"></a>Fluxo de trabalho da interface do usuário da administração do Intune
Quando o gerenciamento de dispositivo Android ou Apple está habilitado, o Intune envia informações do dispositivo e do usuário a serem integradas com esses serviços de terceiros para que eles gerenciem seus respectivos dispositivos.

Os cenários que adicionam um consentimento para compartilhar dados estão inclusos quando:
- Você habilita perfis de trabalho Android.
- Você habilita e carrega Apple MDM Push Certificates.
- Você habilita qualquer um dos serviços da Apple, como o Programa de registro de dispositivos, o School Manager ou o Volume Purchase Program.

Em cada caso, o consentimento está estritamente relacionado à execução de um serviço de gerenciamento de dispositivos móveis. Por exemplo, confirmar que um administrador de TI autorizou o Google ou os dispositivos da Apple a se inscreverem. A documentação que trata das informações que serão compartilhadas quando os novos fluxos de trabalho forem ativados está disponível nos seguintes locais:
- [Dados enviados pelo Intune ao Google](https://aka.ms/Data-intune-sends-to-google)
- [Dados enviados pelo Intune à Apple](https://aka.ms/data-intune-sends-to-apple)

## <a name="key-considerations"></a>Principais considerações
Depois de alternar para a nova autoridade de MDM, provavelmente haverá tempo de transição (até oito horas) antes de o dispositivo fazer o check-in e sincronizar com o serviço. É necessário definir as configurações na nova autoridade de MDM (híbrido) para garantir que os dispositivos registrados continuem a ser gerenciados e protegidos após a alteração. 
- Os dispositivos devem se conectar com o serviço após a alteração para que as configurações da nova autoridade de MDM (Intune autônomo) substituam as configurações existentes no dispositivo.
- Depois de alterar a autoridade de MDM, algumas das configurações básicas (como perfis) da autoridade de MDM anterior (Intune autônomo) permanecem no dispositivo por até sete dias ou até que o dispositivo se conecte com o serviço pela primeira vez. Recomenda-se configurar aplicativos e parâmetros (políticas, perfis, aplicativos, etc.) na nova autoridade de MDM (híbrido) assim que possível e implantar as configurações para os grupos de usuários que contêm usuários com dispositivos registrados. Assim que um dispositivo se conectar ao serviço após a alteração na autoridade de MDM, ele receberá as novas configurações da nova autoridade de MDM e evitará falhas na proteção e no gerenciamento.
- Quando as mesmas categorias de dispositivo existirem no Intune e no Configuration Manager, todas as atribuições de categoria de dispositivo para dispositivos não serão transportadas após você alternar para a nova autoridade de MDM. Para continuar usando categorias de dispositivo, os dispositivos migrados precisam ser adicionados manualmente às coleções apropriadas após a autoridade de MDM ser alterada e serão exibidos no console do Configuration Manager.
- Os dispositivos que não têm usuários associados (normalmente quando você tem o Programa de registro de dispositivos iOS ou cenários de registro em massa) não são migrados para a nova autoridade de MDM. Para esses dispositivos, você precisa chamar o suporte para obter assistência para movê-los para a nova autoridade de MDM.

## <a name="change-mdm-authority-to-office-365"></a>Alterar a autoridade de MDM para o Office 365

Para ativar o MDM do Office 365 (ou habilitar a coexistência do MDM, além do serviço existente do Intune), vá para [https://protection.office.com](https://protection.office.com), escolha **Prevenção contra perda de dados** > **Políticas de segurança de dispositivos** > **Exibir a lista de dispositivos gerenciados** > **Vamos começar**.

Para obter mais informações, confira [Configurar o MDM (Gerenciamento de Dispositivo Móvel) no Office 365](https://support.office.com/en-us/article/Set-up-Mobile-Device-Management-MDM-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd).

Se você deseja que os usuários finais sejam gerenciados apenas pelo MDM do Office 365, remova as licenças do Intune e/ou do EMS atribuídas após a ativação do MDM do Office 365.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Limpeza de dispositivo móvel após a expiração do certificado MDM

O certificado do MDM é renovado automaticamente quando os dispositivos móveis estão se comunicando com o serviço Intune. Se os dispositivos móveis forem apagados ou se eles não conseguirem se comunicar com o serviço Intune por um certo período, o certificado do MDM não será renovado. O dispositivo é removido do Portal do Azure 180 dias após a expiração do certificado do MDM.

## <a name="remove-mdm-authority"></a>Remover a autoridade de MDM

A autoridade de MDM não pode ser alterada novamente para Desconhecida. A autoridade de MDM é usada pelo serviço para determinar para qual portal os dispositivos registrados devem se reportar: Microsoft Intune ou MDM do Office 365.

## <a name="what-to-expect-after-changing-the-mdm-authority"></a>O que esperar após a alteração da autoridade de MDM

- Quando o serviço Intune detecta que a autoridade de MDM de um locatário foi alterada, ele envia uma mensagem de notificação para todos os dispositivos registrados para fazer check-in e sincronizar com o serviço (essa notificação ocorre fora do check-in agendado regularmente). Portanto, depois que a autoridade de MDM para o locatário tiver sido alterada de Intune autônomo para híbrida, todos os dispositivos que estiverem ligados e online se conectarão ao serviço, receberão a nova autoridade de MDM e serão gerenciados pelo híbrido no futuro. Não há interrupção para o gerenciamento e a proteção desses dispositivos.
- Mesmo para os dispositivos ligados e online durante (ou logo após) a alteração na autoridade de MDM, haverá um atraso de até oito horas (dependendo do horário do próximo check-in regular agendado) antes de os dispositivos serem registrados no serviço sob a nova autoridade de MDM.    

  > [!IMPORTANT]    
  > Entre o momento em que você altera a autoridade de MDM e em que o certificado APNs renovado é carregado para a nova autoridade, novos registros de dispositivo e check-in de dispositivo para dispositivos iOS falharão. Portanto, é importante que você analise e carregue o certificado de APNs para a nova autoridade assim que possível após a alteração na autoridade de MDM.

- Os usuários podem alterar rapidamente para a nova autoridade de MDM iniciando manualmente um check-in do dispositivo para o serviço. Os usuários podem fazer essa alteração facilmente usando o aplicativo Portal da Empresa e iniciando uma verificação de conformidade do dispositivo.
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

- Depois de alterar a autoridade MDM, execute as etapas a seguir para validar que os novos dispositivos sejam registrados com êxito para a nova autoridade:   
  - Registrar um novo dispositivo
  - Verifique se o dispositivo registrado recentemente aparece no console do Configuration Manager.
  - Execute uma ação, como bloqueio remoto, do console de administração para o dispositivo. Se a ação for bem-sucedida, isso significa que o dispositivo está sendo gerenciado pela nova autoridade de MDM.
- Se você tiver problemas com dispositivos específicos, poderá cancelar o registro e registrar novamente os dispositivos para que eles se conectem à nova autoridade e sejam gerenciados o mais rápido possível.

## <a name="next-steps"></a>Próximas etapas

Com a autoridade de MDM definida, você pode começar o [registro de dispositivos](../enrollment/device-enrollment.md).
