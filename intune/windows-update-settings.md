---
title: Configurações do Windows Update para Empresas para Microsoft Intune – Azure | Microsoft Docs
description: Configurações do WUfB para dispositivos com Windows 10 que você pode implantar usando o Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 98c3425c58b6039c8a1c3b5750f9473c74a78634
ms.sourcegitcommit: 93de3423d2d8f0019e676a63784edeb3daf47cb7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2019
ms.locfileid: "56325462"
---
# <a name="windows-update-settings-for-intune"></a>Configurações de atualização do Windows para Intune  

Veja as configurações de do Windows 10 Update que você pode [configurar e gerenciar](windows-update-for-business-configure.md) com o Microsoft Intune.  

Quando você define configurações para grupos de atualização do Windows 10 no Intune, está definindo as configurações de Atualização do Windows.  Quando uma configuração de atualização do Windows tiver uma dependência de versão do Windows 10, a dependência da versão será indicada nos detalhes das configurações.  

## <a name="update-settings"></a>Configurações de atualização  

As configurações de atualização controlam quais partes um dispositivo baixará, e quando. Confira a documentação de referência do Windows para saber mais sobre o comportamento de cada configuração.  

### <a name="servicing-channel"></a>Canal de manutenção  

- **Padrão**: Canal Semestral (direcionado)  
- **Documentação de referência do Windows**: [Update/BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  
Defina o canal (branch) pelo qual o dispositivo recebe atualizações do Windows. Canais diferentes podem usar períodos de adiamento diferente antes da entrega das atualizações.  

Por exemplo, o *Canal Semestral* tem um adiamento de seis meses. Isso significa que se você usar esse canal sem adiamentos adicionais deste corpo de configurações, o dispositivo instalará a atualização seis meses após seu lançamento.  

Canais de atualização com suporte:  

- Canal Semestral  
- Canal Semestral (Direcionado)  
- Windows Insider – Modo Rápido  
- Windows Insider – Modo Lento  
- Liberar Windows Insider  

Se você selecionar um canal Insider, o Intune definirá automaticamente a configuração de atualização do Windows [Update/ManagePreviewBuilds](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-managepreviewbuilds) para que o build do insider funcione.  


> [!IMPORTANT]  
> A partir da versão 1903 do Windows, o uso de *Canal Semestral (direcionado)* (SAC-T), está desativado. Com essa alteração, o SAC-T mescla com o *Canal Semestral*. Para saber mais sobre essa alteração e como ela afeta o Windows Update para Empresas, consulte a postagem do Blog do Windows IT Pro [Windows Update para Empresas e a desativação do SAC-T](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-Update-for-Business-and-the-retirement-of-SAC-T/ba-p/339523).
 


### <a name="microsoft-product-updates"></a>Atualizações de produto da Microsoft  

- **Padrão**:  Allow
- **Documentação de referência do Windows**: [Update/AllowMUUpdateService](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

Escolha *Allow* para buscar atualizações de aplicativos no Microsoft Update.    

### <a name="windows-drivers"></a>Drivers do Windows  

- **Padrão**:  Allow
- **Documentação de referência do Windows**: [Update/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)

Escolha *Allow* para incluir os drivers do Windows Update durante as atualizações

### <a name="quality-update-deferral-period-days"></a>Período de adiamento da atualização de qualidade (dias)  

- **Padrão**: 0  
- **Documentação de referência do Windows**: [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

Especifique o número de dias de 0 a 30 para adiamento das Atualizações de Qualidade. Esse período ocorre como adição a qualquer período de adiamento do canal de serviço selecionado. O período de adiamento começa quando a política é recebida pelo dispositivo.  

Normalmente, as Atualizações de Qualidade são correções e aprimoramentos para a funcionalidade existente do Windows.  

### <a name="feature-update-deferral-period-days"></a>Período de adiamento da atualização de recurso (dias)  

- **Padrão**: 0  
- **Documentação de referência do Windows**: [Update/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

Especifique o número de dias pelos quais as Atualizações de Recursos serão adiadas. Esse período ocorre como adição a qualquer período de adiamento do canal de serviço selecionado. O período de adiamento começa quando a política é recebida pelo dispositivo.  
Período de adiamento com suporte:  

- *Versão 1709 do Windows ou posterior*: 0 a 365 dias  
- *Versão 1703 do Windows*:  0 a 180 dias  

As Atualizações do Recurso são geralmente novos recursos para o Windows.  

### <a name="set-feature-update-uninstall-period-2--60-days"></a>Definir período de desinstalação da atualização do recurso (2 a 60 dias)  

- **Padrão**: 10  
- **Documentação de referência do Windows**:  [Update/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

Configure um limite de tempo após o qual as atualizações de recurso não podem ser desinstaladas.  

Após esse período, os bits de atualização anteriores são removidos do dispositivo, e ele não pode mais desinstalar e usar uma versão anterior da atualização.  

Por exemplo, considere um grupo de atualização com um período de desinstalação de atualização de recurso de 20 dias. Após 25 dias, você decide reverter para a atualização mais recente do recurso e usar a opção Desinstalar.  Os dispositivos que receberam a atualização de recurso há mais de 20 dias não podem desinstalá-la, pois removeram os bits como parte da manutenção. No entanto, os dispositivos que receberam a atualização de recurso há até 19 dias podem desinstalá-la se fizerem check-in para receber o comando de desinstalação antes de exceder o período de desinstalação de 20 dias.  


## <a name="user-experience-settings"></a>Configurações da experiência do usuário  

As configurações de experiência do usuário controlam a experiência do usuário final para lembretes e reinício do dispositivo. Confira a documentação de referência do Windows para saber mais sobre o comportamento de cada configuração.  

### <a name="automatic-update-behavior"></a>Comportamento de atualização automática  

- **Padrão**: Instalação e reinício automáticos em um momento agendado  
- **Documentação de referência do Windows**: [Update/AllowAutoUpdate](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

Escolha como as atualizações automáticas são instaladas e, se necessário, quando reiniciar o dispositivo.  

Confira a documentação de referência do Windows para ver todas as opções com suporte a seguir:  

- **Notificar download**: notificar o usuário antes de baixar a atualização. Os usuários escolhem baixar e instalar atualizações.  

- **Instalação automática no momento da manutenção**: as atualizações são baixadas automaticamente e instaladas durante a Manutenção Automática, quando o dispositivo não está em uso ou funcionando com bateria. Quando o reinício for necessário, os usuários receberão uma solicitação de reinício por até sete dias e, depois disso, o reinício será forçado.  

  Essa opção pode reiniciar um dispositivo automaticamente após a instalação da atualização. Use as configurações de **Horas ativas** para definir um período durante o qual as reinicializações automáticas ficam bloqueadas:  

  - **Início das horas ativas**: Especifique uma hora de início para a supressão das reinicializações devido a instalações de atualização.  
    **Documentação de referência do Windows**:  [Update/ActiveHoursStart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Padrão**: 8h  
  
  - **Término das horas ativas**: Especifique uma hora de término para a supressão das reinicializações devido a instalações de atualização.  
    **Documentação de referência do Windows**:  [Update/ActiveHoursEnd](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Padrão**: 17h  

- **Instalação e reinício automáticos no momento da manutenção**: as atualizações são baixadas automaticamente e instaladas durante a Manutenção Automática, quando o dispositivo não está em uso ou funcionando com bateria. Quando o reinício for necessário, o dispositivo será reiniciado quando não estiver sendo usado. (Esse é o padrão para dispositivos não gerenciados.)  

  Essa opção pode reiniciar um dispositivo automaticamente após a instalação da atualização. O uso das configurações de **Horas ativas** não está descrito nas configurações do Windows Update, mas elas podem ser usadas pelo Intune para definir um período durante o qual as reinicializações automáticas ficam bloqueadas:  

  - **Início das horas ativas**: Especifique uma hora de início para a supressão das reinicializações devido a instalações de atualização.  
    **Documentação de referência do Windows**:  [Update/ActiveHoursStart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Padrão**: 8h  

  - **Término das horas ativas**: Especifique uma hora de término para a supressão das reinicializações devido a instalações de atualização.  
    **Documentação de referência do Windows**:  [Update/ActiveHoursEnd](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Padrão**: 17h  

- **Instalar e reiniciar automaticamente no horário agendado**: especifique um dia e hora para a instalação. Se não for especificado, a instalação será executada diariamente às 3h, seguida por uma contagem regressiva de 15 minutos para o reinício. Os usuários conectados podem atrasar a contagem regressiva e o reinício.  
  
  Essa opção dá suporte a configurações adicionais.  
  **Documentação de referência do Windows**:  [Update/AllowAutoUpdate](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  - **Frequência de comportamento automático**: Use essa configuração para agendar quando as atualizações serão instaladas, incluindo o dia, a semana e a hora.  
    **Padrão**: Toda semana

  - **Dia de instalação agendado**:  Especifique em qual dia da semana você deseja instalar as atualizações.  
    **Padrão**: Qualquer dia  

  - **Hora de instalação agendada**:  Especifique a hora do dia em que deseja instalar as atualizações.  
    **Padrão**: 3h  

- **Instalação e reinício automática sem o controle do usuário final**: as atualizações são baixadas automaticamente e instaladas durante a Manutenção Automática, quando o dispositivo não está em uso ou está funcionando com bateria. Quando o reinício for necessário, o dispositivo será reiniciado quando não estiver sendo usado. Essa opção define o painel de controle de usuários finais como somente leitura.  

- **Redefinir para padrão**: restaura as configurações originais de atualização automática em computadores Windows 10 que executam a Atualização de outubro de 2018 ou posterior.  


### <a name="restart-checks"></a>Reiniciar verificações  

- **Padrão**: Allow  
- **Documentação de referência do Windows**: [Update/SetEDURestart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

Essa configuração tem resultados diferentes dependendo da versão de dispositivos do Windows:  

- Versão 1703 do Windows e anteriores: Quando você reinicia um dispositivo, ocorrem algumas verificações, incluindo a verificação de usuários ativos, níveis de bateria, jogos em execução e muito mais. Para ignorar essas verificações ao reiniciar um dispositivo, selecione **Ignorar**.  
- A partir da versão 1709 do Windows: Durante as Horas Ativas, os processos a seguir não são executados para atualizações: examinar, baixar, instalar e reinicializar. Após as Horas Ativas, os processos de atualização são executados e podem tirar o dispositivo do modo de suspensão, examinar, baixar, instalar e reiniciar o dispositivo, desde que as verificações de bateria e de energia sejam aprovadas. Para saber mais, confira [Update/SetEDURestart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-setedurestart).  

### <a name="block-user-from-pausing-windows-updates"></a>Impedir que o usuário pause as atualizações do Windows  

- **Padrão**: Allow  
- **Documentação de referência do Windows**: [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

Permitir ou bloquear que um usuário de dispositivo pause a instalação de uma atualização.  

### <a name="require-users-approval-to-restart-outside-of-work-hours"></a>Exigir aprovação do usuário para reiniciar fora das horas de trabalho  

- **Padrão**: Não configurado  
- **Documentação de referência do Windows**: [Update/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
Selecione *Obrigatório* para exigir que um usuário aprove o reinício de um dispositivo fora do horário de trabalho.  
   
### <a name="remind-user-prior-to-required-auto-restart-with-dismissible-reminder-hours"></a>Lembrar o usuário antes do reinício automático obrigatório com um lembrete dispensável (horas)  

- **Padrão**: *Isso não está configurado por padrão, e nenhum lembrete é apresentado aos usuários*.  
- **Documentação de referência do Windows**: [Update/ScheduleRestartWarning](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

Especifique quando exibir uma notificação dispensável a um usuário de dispositivo antes do reinício automático. É possível usar os valores de **2**, **4**, **8**, **12** ou **24** horas.  

### <a name="remind-user-prior-to-required-auto-restart-with-permanent-reminder-minutes"></a>Lembrar o usuário antes do reinício automático obrigatório com um lembrete permanente (minutos)  

- **Padrão**: *Isso não está configurado por padrão, e nenhum lembrete é apresentado aos usuários*.  
- **Documentação de referência do Windows**: [Update/ScheduleImminentRestartWarning](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning) 

Especifique por quanto tempo antes de um reinício automático exibir um aviso não dispensável sobre o reinício. É possível usar os valores de **15**, **30**, ou **60** minutos.  
 
### <a name="allow-user-to-restart-engaged-restart"></a>Permitir que o usuário reinicie (reinício estabelecido)  

- **Padrão**: Não configurado  
- **Documentação de referência do Windows**: *Não aplicável*  
- **Versão do Windows**: Com suporte para Windows 10 versão 1803 e posterior  

  > [!NOTE]  
  > O Windows 10 versão 1809 apresenta configurações adicionais de reinício estabelecido que habilitam a aplicação de configurações separadas às atualizações de recurso e de qualidade. No entanto, as configurações gerenciadas pelo Intune não aplicadas separadamente a diferentes tipos de atualizações. Em vez disso, o Intune aplica os mesmos valores às atualizações de recurso e de qualidade.  

Ao definir como **Obrigatório**, você habilita o uso das opções de reinício estabelecido para atualizações do Windows 10. Essas opções envolvem o usuário de um dispositivo para ajudar a gerenciar quando reiniciar um dispositivo após instalar uma atualização que exige o reinício.  

Para saber mais sobre essa opção, confira [Reinício estabelecido](https://docs.microsoft.com/en-us/windows/deployment/update/waas-restart#engaged-restart) na documentação do Windows 10 para a implantação de atualizações.  

As configurações a seguir são usadas para controlar quando ocorrem as ações de reinício estabelecido.  

- **Fazer a transição dos usuários para o reinício estabelecido após um reinício automático (dias)**  
  - **Padrão**:  Por padrão, isso não está configurado, mas dá suporte a um valor de **2** à **30**.  
  - **Documentação de referência do Windows**: [Update/EngagedRestartTransitionSchedule](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-engagedrestarttransitionschedule)  
  Especifique quanto tempo após instalação da atualização o dispositivo deve assumir o comportamento de reinício estabelecido. Após o número configurado de dias, os usuários receberão uma solicitação para reiniciar o dispositivo.  

- **Lembrete de reinício estabelecido com adiamento (dias)**  
  - **Padrão**:  Por padrão, isso não está configurado, mas dá suporte a um valor de **1** à **3**.  
  - **Documentação de referência do Windows**: [Update/EngagedRestartSnoozeSchedule](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-engagedrestartsnoozeschedule)  
  Especifique por quanto tempo uma solicitação de reinício pode ser adiada.  Após o período de adiamento, a solicitação de reinício é oferecida novamente. O usuário pode continuar adiando o lembrete até que o prazo de instalação seja atingido.  

- **Definir prazo para reinício pendente (dias)**  
  - **Padrão**:  Por padrão, isso não está configurado, mas dá suporte a um valor de **2** à **30**.  
  - **Documentação de referência do Windows**: [Update/EngagedRestartDeadline](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-engagedrestartdeadline)  
  Especifique o número máximo de dias a aguardar após o início do comportamento de reinício estabelecido antes que o dispositivo imponha um reinício obrigatória. Esse reinício solicitará aos usuários que salvem seu trabalho

### <a name="delivery-optimization-download-mode"></a>Modo de download de otimização de entrega  

- **Padrão**:  Não Aplicável
- **Documentação de referência do Windows**: *Não aplicável*

A otimização de entrega não está mais configurada como parte de um Grupo de Atualização do Windows 10 em Atualizações de Software. Agora, a Otimização de Entrega é definida por meio da configuração do dispositivo. No entanto, as configurações anteriores permanecem disponíveis no console. Remova essas configurações anteriores editando-as para *Não configurado*, mas, de outro modo, elas não podem ser modificadas. 

Para evitar conflitos entre políticas novas e antigas, confira [Mover de grupos de atualização existentes para a Otimização de Entrega](https://docs.microsoft.com/en-us/intune/delivery-optimization-windows#move-from-existing-update-rings-to-delivery-optimization) e, em seguida, mova as configurações para um perfil de Otimização de Entrega.


