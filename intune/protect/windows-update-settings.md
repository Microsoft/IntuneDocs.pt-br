---
title: Configurações do Windows Update para Empresas para Microsoft Intune – Azure | Microsoft Docs
description: Configurações do WUfB para dispositivos com Windows 10 que você pode implantar usando o Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/15/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5aaa964151477896c236e504ec9b378cf580e838
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736371"
---
# <a name="windows-update-settings-for-intune"></a>Configurações de atualização do Windows para Intune  

Veja as configurações de do Windows 10 Update que você pode [configurar e gerenciar](windows-update-for-business-configure.md) com o Microsoft Intune.  

Quando você define configurações para grupos de atualização do Windows 10 no Intune, está definindo as configurações de Atualização do Windows. Se uma configuração do Windows Update tiver uma dependência de versão do Windows 10, a dependência da versão será indicada nos detalhes das configurações.  

## <a name="update-settings"></a>Configurações de atualização  

As configurações de atualização controlam quais partes um dispositivo baixará, e quando. Para obter mais informações sobre o comportamento de cada configuração, veja a documentação de referência do Windows.  

- **Canal de manutenção**  
  **Padrão**: Canal Semianual  
  CSP Windows Update: [Update/BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  

  Defina o canal (branch) pelo qual o dispositivo recebe atualizações do Windows. Canais diferentes podem usar períodos de adiamento diferente antes da entrega das atualizações.  

  Por exemplo, o *Canal Semestral* tem um adiamento de seis meses. Se você usar esse canal sem adiamentos adicionais deste corpo de configurações, o dispositivo instalará a atualização seis meses após seu lançamento.  

  Canais de atualização com suporte:  

  - Canal Semestral  
  - Canal Semestral (Direcionado)  
  - Windows Insider – Modo Rápido  
  - Windows Insider – Modo Lento  
  - Liberar Windows Insider  

  Se você selecionar um canal Insider, o Intune definirá automaticamente a configuração de atualização do Windows [Update/ManagePreviewBuilds](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-managepreviewbuilds) para que o build do insider funcione.  


  > [!IMPORTANT]  
  > A partir da versão 1903 do Windows, o uso de *Canal Semestral (direcionado)* (SAC-T), está desativado. Com essa alteração, o SAC-T mescla com o *Canal Semestral*. Para saber mais sobre essa alteração e como ela afeta o Windows Update para Empresas, consulte a postagem do Blog do Windows IT Pro [Windows Update para Empresas e a desativação do SAC-T](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-Update-for-Business-and-the-retirement-of-SAC-T/ba-p/339523).  
 
- **Atualizações de produto da Microsoft**  
  **Padrão**: Permitir  
  CSP Windows Update: [Update/AllowMUUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

  - **Permitir** -selecione *permitir* para verificar se há atualizações de aplicativo de Microsoft Update.  
  - **Bloquear – selecione** bloquear para impedir a verificação de atualizações do aplicativo.  

- **Drivers do Windows**  
  **Padrão**: Permitir  
  CSP Windows Update: [Update/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)  

  - **Permitir** -selecionar *permitir* incluir Windows Update drivers durante as atualizações.  
  - **Bloquear – selecione** bloquear para impedir a verificação de drivers.  

- **Período de adiamento da atualização de qualidade (dias)**  
  **Padrão**: 0  
  CSP Windows Update: [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

  Especifique o número de dias de 0 a 30 para adiamento das Atualizações de Qualidade. Esse período ocorre como adição a qualquer período de adiamento do canal de serviço selecionado. O período de adiamento começa quando a política é recebida pelo dispositivo.  

  Normalmente, as Atualizações de Qualidade são correções e aprimoramentos para a funcionalidade existente do Windows.  

- **Período de adiamento da atualização de recurso (dias)**  
  **Padrão**: 0  
  CSP Windows Update: [Update/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

  Especifique o número de dias pelos quais as Atualizações de Recursos serão adiadas. Esse período ocorre como adição a qualquer período de adiamento do canal de serviço selecionado. O período de adiamento começa quando a política é recebida pelo dispositivo.  

  Período de adiamento com suporte:  

  - *Windows versão 1709 e posterior* -0 a 365 dias  
  - *Windows versão 1703* – 0 a 180 dias  

  As Atualizações do Recurso são geralmente novos recursos para o Windows.  

- **Definir período de desinstalação da atualização do recurso (2 a 60 dias)**  
  **Padrão**: 10  
  CSP Windows Update: [Update/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

  Configure um limite de tempo após o qual as atualizações de recurso não podem ser desinstaladas.  

  Após esse período, os bits de atualização anteriores são removidos do dispositivo, e ele não pode mais desinstalar e usar uma versão anterior da atualização.  

  Por exemplo, considere um grupo de atualização com um período de desinstalação de atualização de recurso de 20 dias. Após 25 dias, você decide reverter para a atualização mais recente do recurso e usar a opção Desinstalar.  Os dispositivos que receberam a atualização de recurso há mais de 20 dias não podem desinstalá-la, pois removeram os bits como parte da manutenção. No entanto, os dispositivos que receberam a atualização de recurso há até 19 dias poderão desinstalá-la se fizerem check-in para receber o comando de desinstalação antes de exceder o período de desinstalação de 20 dias.  

## <a name="user-experience-settings"></a>Configurações da experiência do usuário  

As configurações de experiência do usuário controlam a experiência do usuário final para lembretes e reinício do dispositivo. Para obter mais informações sobre o comportamento de cada configuração, veja a documentação de CSP do Windows Update.  

- **Comportamento de atualização automática**  
  **Padrão**: instalação automática no horário para manutenção  
  CSP Windows Update: [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  Escolha como as atualizações automáticas são instaladas e, se necessário, quando reiniciar o dispositivo.  

  Opções de suporte:  

  - **Notificar download**: notificar o usuário antes de baixar a atualização. Os usuários escolhem baixar e instalar atualizações.  

  - **Instalação automática no horário da manutenção**: as atualizações são automaticamente baixadas e instaladas durante a Manutenção Automática, quando o dispositivo não está em uso ou funcionando com bateria. Quando o reinício for necessário, os usuários receberão uma solicitação de reinício por até sete dias e, depois disso, o reinício será forçado.  

    Essa opção pode reiniciar um dispositivo automaticamente após a instalação da atualização. Use as configurações de **Horas ativas** para definir um período durante o qual as reinicializações automáticas ficam bloqueadas:  

    - **Início das horas de atividade**: especifique uma hora de início para a supressão das reinicializações devido a instalações de atualização.  
      **Padrão**: 8h  
      CSP Windows Update: [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
  
    - **Término das horas de atividade**: especifique uma hora de término para a supressão das reinicializações devido a instalações de atualização.  
      **Padrão** = 5  
      CSP Windows Update: [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  

  - **Instalação e reinício automáticos no momento da manutenção**: as atualizações são baixadas automaticamente e instaladas durante a Manutenção Automática, quando o dispositivo não está em uso ou funcionando com bateria. Quando o reinício for necessário, o dispositivo será reiniciado quando não estiver sendo usado. (Esse é o padrão para dispositivos não gerenciados.)  

    Essa opção pode reiniciar um dispositivo automaticamente após a instalação da atualização. O uso das configurações de **Horas ativas** não está descrito nas configurações do Windows Update, mas elas podem ser usadas pelo Intune para definir um período durante o qual as reinicializações automáticas ficam bloqueadas:  

    - **Início das horas de atividade**: especifique uma hora de início para a supressão das reinicializações devido a instalações de atualização.  
      **Padrão**: 8h  
      CSP Windows Update: [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
  
    - **Término das horas de atividade**: especifique uma hora de término para a supressão das reinicializações devido a instalações de atualização.  
      **Padrão** = 5  
      CSP Windows Update: [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  

  - **Instalar e reinicializar automaticamente no horário agendado**: especifique um dia e horário para a instalação. Se não for especificado, a instalação será executada diariamente às 3h, seguida por uma contagem regressiva de 15 minutos para o reinício. Os usuários conectados podem atrasar a contagem regressiva e o reinício.   
  CSP Windows Update: [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

    Essa opção dá suporte a configurações adicionais.  

    - **Frequência de comportamento automático**: use essa configuração para agendar quando as atualizações serão instaladas, incluindo o dia, a semana e a hora.  
      **Padrão**: toda semana

    - **Dia agendado para a instalação**: especifique em qual dia da semana você deseja instalar as atualizações.  
      **Padrão**: qualquer dia  

    - **Hora agendada para a instalação**: especifique a hora do dia em que você deseja instalar as atualizações.  
      **Padrão**: 3h  

  - **Instalar e reinicializar automaticamente sem controle do usuário final**: as atualizações são baixadas e instaladas automaticamente durante a Manutenção Automática quando o dispositivo não está em uso ou está funcionando com bateria. Quando o reinício for necessário, o dispositivo será reiniciado quando não estiver sendo usado. Essa opção define o painel de controle de usuários finais como somente leitura.  

  - **Redefinir para padrão**: restaura as configurações originais de atualização automática em computadores Windows 10 que executam a Atualização de outubro de 2018 ou posterior.  


- **Reiniciar verificações**  
  **Padrão**: permitir  
  CSP Windows Update: [Update/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

  Para ignorar essas verificações ao reiniciar um dispositivo, selecione **Ignorar**. 
  
  Essa configuração tem resultados diferentes dependendo da versão de dispositivos do Windows:  
 
  - *Windows versão 1703 e anterior*: quando você reinicia um dispositivo, ocorrem algumas verificações, incluindo a verificação de usuários ativos, níveis de bateria, jogos em execução e muito mais.  
  
  - *Windows versão 1709 e posterior*: durante as Horas Ativas, os processos a seguir não são executados para atualizações: examinar, baixar, instalar e reinicializar. Após as Horas Ativas, os processos de atualização são executados e podem tirar o dispositivo do modo de suspensão, examinar, baixar, instalar e reiniciar o dispositivo, desde que as verificações de bateria e de energia sejam aprovadas. 

- **Impedir que o usuário pause as atualizações do Windows**  
  **Padrão**: permitir  
  CSP Windows Update: [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

  - **Permitir** -permitir que os usuários do dispositivo pausem a instalação de uma atualização.  
  - **Bloquear** – impedir que os usuários do dispositivo pausarm a instalação de uma atualização.  

- **Impedir que o usuário verifique se há atualizações do Windows**  
  **Padrão**: permitir  
  CSP Windows Update: [Update/SetDisableUXWUAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisableuxwuaccess) 

  - **Permitir** -permitir que os usuários do dispositivo usem Windows Update verificação para localizar e baixar atualizações e instalar recursos.
  - **Bloquear** – impedir que os usuários do dispositivo acessem a verificação de Windows Update, baixando atualizações e instalando recursos.  

- **Requer aprovação do usuário para reiniciar fora do horário de trabalho**  
  **Padrão**: não configurado  
  CSP Windows Update: [Update/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
  - **Não configurado**  
  - **Obrigatório**: exige que um usuário aprove a reinicialização de um dispositivo fora do horário de trabalho.  
   
- **Lembrar o usuário antes da reinicialização automática obrigatória com lembrete ignorável (horas)**  
  **Padrão**: 4  
  CSP Windows Update: [Update/ScheduleRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

  Especifique quando exibir uma notificação dispensável a um usuário de dispositivo antes do reinício automático. É possível usar os valores de **2**, **4**, **8**, **12** ou **24** horas.  
  
  Quando você limpa o valor padrão, essa configuração se torna *não configurada*.  

- **Lembrar o usuário antes da reinicialização automática obrigatória com lembrete permanente (minutos)**  
  **Padrão**: 15  
  CSP Windows Update: [Update/ScheduleImminentRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)  

  Especifique por quanto tempo antes de um reinício automático exibir um aviso não dispensável sobre o reinício. É possível usar os valores de **15**, **30**, ou **60** minutos.  

  Quando você limpa o valor padrão, essa configuração se torna *não configurada*.  

- **Alterar nível de atualização da notificação**  
  **Padrão**: usar as notificações padrão do Windows Update  
  CSP Windows Update: [Update/UpdateNotificationLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)
  
  Especifica o nível de notificações do Windows Update que os usuários veem. Essa configuração não controla como e quando as atualizações são baixadas e instaladas.  

  Opções de suporte:
  - **Não configurado**
  - **Usar as notificações padrão do Windows Update**
  - **Desativar todas as notificações, excluindo avisos de reinicialização**
  - **Desativar todas as notificações, incluindo avisos de reinicialização**  

- **Permitir que o usuário reinicie (reinício estabelecido)**  
  **Padrão**: não configurado  
  > [!IMPORTANT]  
  > As configurações de *reinicialização envolvidas* não são mais recomendadas para uso. Em vez disso, use as novas configurações de *prazo* que substituem as configurações de *reinicialização envolvidas* . O Intune [preterirá o suporte para configurações de *reinicialização envolvidas* ](../fundamentals/whats-new.md#plan-for-change-new-windows-updates-settings-in-intune-) em uma atualização futura.

  A reinicialização envolvida tem suporte para o Windows 10 versão 1803 e posterior. 

  > [!NOTE]  
  > O Windows 10 versão 1809 apresenta configurações adicionais de reinício estabelecido que habilitam a aplicação de configurações separadas às atualizações de recurso e de qualidade. No entanto, as configurações gerenciadas pelo Intune não aplicadas separadamente a diferentes tipos de atualizações. Em vez disso, o Intune aplica os mesmos valores às atualizações de recurso e de qualidade.  
  
  - **Não configurado**  
  - **Obrigatório**: defina como *Obrigatório* para habilitar o uso das opções de reinício estabelecido para atualizações do Windows 10. Essas opções envolvem o usuário de um dispositivo para ajudar a gerenciar quando reiniciar um dispositivo após instalar uma atualização que exige o reinício.  

  Para saber mais sobre essa opção, confira [Reinício estabelecido](https://docs.microsoft.com/windows/deployment/update/waas-restart#engaged-restart) na documentação do Windows 10 para a implantação de atualizações.  

  As configurações a seguir são usadas para controlar quando ocorrem as ações de reinício estabelecido.  

  - **Fazer a transição dos usuários para o reinício estabelecido após um reinício automático (dias)**  
    **Padrão**: não configurado Windows Update CSP: [Update/EngagedRestartTransitionSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestarttransitionschedule)  
    
    Especifique um valor de **2** a **30** dias para definir quanto tempo decorre após a instalação da atualização até que o dispositivo entre no comportamento de reinício estabelecido. Após o número configurado de dias, os usuários receberão uma solicitação para reiniciar o dispositivo.  

  - **Lembrete de reinício estabelecido com adiamento (dias)**  
    **Padrão**: não configurado    
    CSP Windows Update: [Update/EngagedRestartSnoozeSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartsnoozeschedule)  
    
    Especifique um valor de **1** a **3** para o tempo durante o qual uma solicitação de reinicialização pode ser adiada.  Após o período de adiamento, a solicitação de reinício é oferecida novamente. O usuário pode continuar adiando o lembrete até que o prazo de instalação seja atingido.  

  - **Definir prazo para reinício pendente (dias)**  
    **Padrão**: não configurado  
    CSP Windows Update: [Update/EngagedRestartDeadline](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartdeadline)  
  
    Especifique um valor de **2** a **30** como o número máximo de dias a aguardar após o início do comportamento de reinício estabelecido antes que o dispositivo imponha um reinício obrigatório. Esse reinício solicitará aos usuários que salvem seu trabalho.

- **Usar configurações de prazo**  
  **Padrão**: não configurado  
  > [!IMPORTANT]  
  > A partir da atualização de agosto do Intune, recomendamos o uso das seguintes configurações de prazo que substituem as configurações de reinicialização envolvidas. O Intune [preterirá o suporte para configurações de *reinicialização envolvidas* ](../fundamentals/whats-new.md#plan-for-change-new-windows-updates-settings-in-intune-) em uma atualização futura do Intune.  

  Permite que o usuário use as configurações de prazo.  

  - **Não configurado**
  - **Permitir**

  Quando definido como *permitir*, você pode definir as seguintes configurações para prazos finais:

  - **Prazo para atualizações de recursos**  
    **Padrão**: 7  
    CSP Windows Update: [Update/ConfigureDeadlineForFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)  

    Especifica o número de dias que um usuário tem antes que as atualizações de recursos sejam instaladas em seus dispositivos automaticamente (2-30).

  - **Prazo para atualizações de qualidade**  
    **Padrão**: 7  
    CSP Windows Update: [Update/ConfigureDeadlineForQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)

    Especifica o número de dias que um usuário tem antes que as atualizações de qualidade sejam instaladas em seus dispositivos automaticamente (2-30).

  - **Período de carência**  
    **Padrão**: 2 Windows Update CSP: [Update/ConfigureDeadlineGracePeriod]( https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)

    Especifica um número mínimo de dias após o prazo até que as reinicializações ocorram automaticamente (0-7).

  - **Reinicialização automática antes do prazo**  
    **Padrão**: Sim Windows Update CSP: [Update/ConfigureDeadlineNoAutoReboot](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)

    Especifica se o dispositivo deve reinicializar automaticamente antes do prazo.
    - **Sim**
    - **Não**




### <a name="delivery-optimization-download-mode"></a>Modo de download de otimização de entrega  

A otimização de entrega não está mais configurada como parte de um Grupo de Atualização do Windows 10 em Atualizações de Software. Agora, a Otimização de Entrega é definida por meio da configuração do dispositivo. No entanto, as configurações anteriores permanecem disponíveis no console. Você pode remover essas configurações anteriores editando-as para que fiquem *Não configuradas*, mas não é possível modificá-las de outra forma. 

Para evitar conflitos entre políticas novas e antigas, confira [Mover de grupos de atualização existentes para a Otimização de Entrega](../configuration/delivery-optimization-windows.md#move-existing-update-rings-to-delivery-optimization) e, em seguida, mova as configurações para um perfil de Otimização de Entrega.
