---
title: Configurar o Windows Update para Empresas no Microsoft Intune – Azure | Microsoft Docs
description: Atualize as configurações de Atualização de Software em um perfil para criar um anel de atualização, examine a conformidade e pause as atualizações no Windows Update para Empresas usando o Microsoft Intune em dispositivos Windows 10.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1d34e44c6e046ddbc9b47bbe90900f5992df9e85
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72584550"
---
# <a name="manage-software-updates-in-intune"></a>Gerenciar atualizações de software no Intune

Use o Intune para definir anéis de atualização que especifiquem como e quando o Windows como serviço deve atualizar seus dispositivos Windows 10. Os anéis de atualização são políticas que você atribui a grupos de dispositivos. Usando anéis de atualização, você pode criar uma estratégia de atualização que espelha suas necessidades de negócios. Para obter mais informações, consulte [Gerenciar as atualizações usando o Windows Update para Empresas](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

Com o Windows 10, as novas Atualizações de Recurso e de Qualidade incluem o conteúdo de todas as atualizações anteriores. Desde que você tenha instalado a atualização mais recente, saberá que seus dispositivos Windows 10 estão atualizados. Ao contrário das versões anteriores do Windows, agora você deve instalar a atualização inteira, em vez de parte de uma.


Ao usar o Windows Update para Empresas, você simplifica a experiência de gerenciamento de atualizações. Você não precisa aprovar as atualizações individuais para grupos de dispositivos. Você pode gerenciar o risco em seus ambientes configurando uma estratégia de distribuição de atualização. O Intune possibilita [definir as configurações da atualização](../windows-update-settings.md) nos dispositivos e adiar a instalação da atualização. O Intune não armazena as atualizações, mas apenas a atribuição da política de atualização. Os dispositivos acessam diretamente as atualizações do Windows Update. Essa coleção de configurações definida quando as atualizações do Windows 10 são instaladas é chamada de *anel de atualização do Windows 10*.

Os anéis de atualização do Windows 10 dão suporte às [marcas de escopo](../fundamentals/scope-tags.md). Use marcas de escopo com anéis de atualização para auxiliar na filtragem e no gerenciamento de conjuntos de configurações que você usa.

## <a name="prerequisites"></a>Pré-requisitos  

Os pré-requisitos a seguir devem ser atendidos para usar as atualizações do Windows para dispositivos Windows 10 no Intune.  

- PCs com Windows 10 devem executar pelo menos o Windows 10 Pro com a atualização Windows Anniversary ou posterior (versão 1607 ou posterior)
- O Windows Update dá suporte às seguintes edições do Windows 10:
  - Windows 10
  - Windows 10 Team (para dispositivos Surface Hub)
  - Windows Holographic for Business  

    O Windows Holographic for Business é compatível com um subconjunto de configurações para atualizações do Windows, incluindo:
    - **Comportamento de atualização automática**
    - **Atualizações de produto da Microsoft**
    - **Canal de manutenção**: dá suporte às opções **Canal Semestral** e **Canal Semestral (Direcionado)** . Saiba mais em [Gerenciar o Windows Holographic](../fundamentals/windows-holographic-for-business.md).  

    > [!NOTE]  
    > **Versões e edições sem suporte**:
    > - Windows 10 Mobile  
    > - Windows 10 Enterprise LTSC. O Windows Update para Empresas (WUfB) atualmente não aceita versões do *Canal de Serviço de Longo Prazo*. Planeje usar métodos alternativos de aplicação de patches, como o WSUS ou o Configuration Manager.  

- Em dispositivos Windows, **Comentários e Diagnóstico** > **Dados de diagnóstico e uso** devem ser definidos como **Básico**, **Aprimorado** ou **Completo**.  

  É possível definir manualmente a configuração *Dados de diagnóstico e uso* para dispositivos com Windows 10 ou usar um perfil de restrição de dispositivo do Intune para o Windows 10 e posterior. Se você usar um perfil de restrição de dispositivo, defina a [configuração de restrição de dispositivo](../configuration/device-restrictions-windows-10.md#reporting-and-telemetry) de **Compartilhar dados de uso** como **Básico**, no mínimo. Essa configuração é encontrada na categoria **Relatório e Telemetria** quando você configura uma política de restrição de dispositivo para o Windows 10 ou posterior.

  Para obter mais informações sobre os perfis do dispositivo, consulte [definir as configurações de restrição de dispositivo](../configuration/device-restrictions-configure.md).  

- Se você usa o portal clássico do Azure, [migre suas configurações no portal do Azure](#migrate-update-settings-to-the-azure-portal).  


## <a name="create-and-assign-update-rings"></a>Criar e atribuir anéis de atualização

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e selecione **Atualizações de software** > **Anéis de Atualização do Windows 10** > **Criar**.  

2. Na guia Conceitos Básicos, especifique um nome, uma descrição (opcional) e selecione **Avançar**.  

   ![Criar fluxo de trabalho do anel de atualização do Windows 10](./media/windows-update-for-business-configure/basics-tab.png)

3. Em **Configurações do anel de atualização**, defina as configurações para suas necessidades empresariais. Saiba mais sobre as configurações disponíveis em [Configurações de atualização do Windows](windows-update-settings.md). Após configurar a *Atualização* e a *Experiência do usuário*, selecione **Avançar**.  

4. Na guia **Marcas de escopo**, selecione **+ Selecionar marcas de escopo** para abrir o painel *Selecionar marcas* se você desejar aplicá-las ao anel de atualização.  

   - No painel **Selecionar marcas**, escolha uma ou mais marcas e, em seguida, clique em **Selecionar** para adicioná-las ao anel de atualização e retorne ao painel *Marcas de escopo*.  

   Quando estiver pronto, selecione **Avançar** para passar para *Atribuições*. 

5. Na guia **Atribuições**, escolha **+ Selecionar grupos para incluir** e atribua o anel de atualização a um ou mais grupos. Use **+ Selecionar grupos para excluir** a fim de ajustar a atribuição. Selecione **Avançar** para continuar.  

6. Na guia **Examinar + criar**, examine as configurações e selecione **Criar** quando estiver pronto para salvar seu anel de atualização do Windows 10. Seu novo anel de atualização é exibido na lista de anéis de atualização.

## <a name="manage-your-windows-10-update-rings"></a>Gerenciar seus anéis de atualização do Windows 10

No portal, é possível escolher um anel de atualização do Windows 10 para abrir seu painel de **Visão geral**. Nesse painel, você pode visualizar o status da atribuição de anéis e executar outras ações para gerenciar o anel.

### <a name="to-view-an-updates-rings-overview-pane"></a>Para exibir um painel Visão geral dos anéis de atualizações: 

1. Entre no Portal do Azure.
2. Navegue até **Intune** > **Atualizações de Software** > **Anéis de Atualização do Windows 10**.
3. Escolha o anel de atualização que deseja exibir ou gerenciar.  

Além de visualizar o status da atribuição, você pode escolher as seguintes ações na parte superior do painel Visão geral para gerenciar o anel de atualização:  
- [Excluir](#delete)  
- [Pausar](#pause)  
- [Retomar](#resume)  
- [Estender](#extend)  
- [Desinstalar](#uninstall)  

![Ações disponíveis](./media/windows-update-for-business-configure/overview-actions.png)

### <a name="delete"></a>Excluir  

Escolha **Excluir** para parar de impor as configurações do anel de atualização do Windows 10 escolhido. A exclusão de um anel remove sua configuração do Intune para que o Intune já não aplique e imponha essas configurações.  

A exclusão de um anel do Intune não modifica as configurações nos dispositivos que receberam a atribuição do anel de atualização.  Em vez disso, o dispositivo mantém suas configurações atuais. Os dispositivos não mantêm um registro histórico de quais configurações foram mantidas anteriormente. Os dispositivos também podem receber configurações de anéis de atualização adicionais que permanecem ativos.  

#### <a name="to-delete-a-ring"></a>Para excluir um anel  

1. Ao exibir a página de visão geral de um Anel de Atualização, escolha **Excluir**.  
2. Selecione **OK**.  

### <a name="pause"></a>Pausar  

Escolha **Pausar** para impedir que os dispositivos atribuídos recebam Atualizações de Recursos ou Atualizações de Qualidade por até 35 dias a partir do momento em que você pausar o anel. Após o máximo de dias transcorrido, a funcionalidade de pausa expirará automaticamente e o dispositivo verificará se há atualizações aplicáveis nas Atualizações do Windows. Após essa verificação, você pode pausar as atualizações novamente. Se você retomar um anel de atualização pausado e pausá-lo novamente, o período de pausa será redefinido para 35 dias.  

#### <a name="to-pause-a-ring"></a>Para pausar um anel  

1. Quando exibir a página de visão geral de um Anel de Atualização, escolha **Pausar**.  
2. Escolha **Recurso** ou **Qualidade** para pausar esse tipo de atualização e, em seguida, escolha **OK**.  
3. Após pausar um tipo de atualização, você pode optar por Pausar novamente para interromper o outro tipo de atualização.  

Quando um tipo de atualização é pausado, o painel Visão geral desse anel exibe os dias restantes até que o tipo de atualização seja retomado.

> [!IMPORTANT]  
> Após emitir um comando para pausar, os dispositivos recebem esse comando na próxima vez que fizerem check-in no serviço. É possível que antes de verificarem, eles possam instalar uma atualização agendada. Além disso, se um dispositivo de destino estiver desativado quando você emitir o comando para pausar, quando você o ativar, ele poderá baixar e instalar as atualizações agendadas antes de verificar com o Intune.

### <a name="resume"></a>Retomar  

Enquanto um anel de atualização estiver pausado, é possível escolher **Retomar** para restaurar as atualizações de Recursos e Qualidade do anel na operação ativa. Após retomar um anel de atualização, você pode pausá-lo novamente.  

#### <a name="to-resume-a-ring"></a>Para retomar um anel  

1. Quando exibir a página de visão geral de um Anel de Atualização, escolha **Retomar**.  
2. Escolha uma das opções disponíveis para retomar atualizações de **Recurso** ou **Qualidade** e, em seguida, escolha **OK**.  
3. Após retomar um tipo de atualização, você pode escolher Retomar novamente para reiniciar o outro tipo de atualização.  

### <a name="extend"></a>Estender  

Enquanto um anel de atualização estiver pausado, escolha **Estender** para redefinir o período de pausa das atualizações de Recursos e Qualidade do anel para 35 dias.  

#### <a name="to-extend-the-pause-period-for-a-ring"></a>Para Estender o período de pausa de um anel  

1. Quando exibir a página de visão geral de um Anel de Atualização, escolha **Estender**. 
2. Escolha uma das opções disponíveis para retomar atualizações de **Recurso** ou **Qualidade** e, em seguida, escolha **OK**.  
3. Após estender a pausa para um tipo de atualização, você pode escolher Estender novamente para ampliar o outro tipo de atualização.  

### <a name="uninstall"></a>Desinstalar  

Um administrador do Intune pode usar a opção **Desinstalar** para desinstalar (reverter) a atualização de *recurso* ou de *qualidade* mais recente para um anel de atualização ativo ou pausado. Após a desinstalação de um tipo, você pode, em seguida, desinstalar o outro tipo. O Intune não dá suporte nem gerencia a capacidade dos usuários de desinstalar atualizações.  

> [!IMPORTANT] 
> Quando você usa a opção *Desinstalar*, o Intune transmite a solicitação de desinstalação para os dispositivos imediatamente. 
> - Os dispositivos Windows iniciam a remoção das atualizações assim que recebem a alteração na política do Intune. A remoção da atualização não está limitada a agendamentos de manutenção, mesmo quando eles são configurados como parte do anel de atualização. 
> - Se a remoção da atualização exigir a reinicialização do dispositivo, o dispositivo será reinicializado sem oferecer aos usuários do dispositivo a opção de adiar.


Para que a opção Desinstalar funcione:  
- Um dispositivo deve executar a atualização do Windows de 10 de abril de 2018 (versão 1803) ou posterior.  

O dispositivo já deve ter a atualização mais recente instalada. Como as atualizações são cumulativas, os dispositivos que instalam a atualização mais recente têm as atualizações de recurso e de qualidade mais recentes. Um exemplo de quando você pode usar essa opção é na reversão da última atualização, caso descubra uma falha nos computadores com Windows 10.  

Considere o seguinte ao usar a opção Desinstalar:  
- Desinstalar uma atualização de recurso ou qualidade só está disponível para o canal de serviço que o dispositivo se encontra.  

- A desinstalação de atualizações de Recurso ou Qualidade aciona uma política para restaurar a atualização anterior em computadores Windows 10.  

- Em dispositivos Windows 10, após a reversão bem-sucedida da atualização de qualidade, os usuários finais continuam vendo a atualização listada em **Configurações do Windows** > **Atualizações** > **Histórico de atualização**.  

- Para atualizações de Recursos especificamente, o tempo permitido para a desinstalação da atualização do recurso é limitado de 2 a 60 dias, conforme definido na configuração dos anéis de atualização **Definir período de desinstalação de atualização do recurso (2 a 60 dias)** . Não é possível reverter uma atualização de recurso em um dispositivo após a atualização do recurso ter sido instalada por mais tempo do que o período de desinstalação definido.  

  Por exemplo, considere um grupo de atualização com um período de desinstalação de atualização de recurso de 20 dias. Após 25 dias, você decide reverter para a atualização mais recente do recurso e usar a opção Desinstalar.  Os dispositivos que instalaram a atualização de recurso há mais de 20 dias não podem desinstalá-la, pois removeram os bits necessários como parte da manutenção. No entanto, os dispositivos que receberam a atualização de recurso há até 19 dias poderão desinstalá-la se fizerem check-in para receber o comando de desinstalação antes de exceder o período de desinstalação de 20 dias.  

Saiba mais sobre as políticas do Windows Update em [Atualizar o CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp) na documentação de gerenciamento de clientes do Windows.  

#### <a name="to-uninstall-the-latest-windows-10-update"></a>Para desinstalar a atualização mais recente do Windows 10  

1. Quando exibir a página de visão geral de um Anel de Atualização, escolha **Desinstalar**.  
2. Escolha uma das opções disponíveis para desinstalar atualizações de **Recurso** ou **Qualidade** e, em seguida, escolha **OK**.  
3. Após acionar a desinstalação de um tipo de atualização, você pode escolher Desinstalar novamente para remover o tipo de atualização remanescente.  

## <a name="migrate-update-settings-to-the-azure-portal"></a>Migrar as configurações de atualização para o portal do Azure  

O Portal Clássico do Azure também tem um número limitado de outras configurações de atualização do Windows 10 no perfil de configuração do dispositivo. Se você tiver uma dessas definições configuradas ao migrar para o portal do Azure, recomendamos realizar as seguintes ações:  

1. crie anéis de atualização do Windows 10 no portal do Azure com as configurações necessárias. A configuração **Permitir recursos de pré-lançamento** não tem suporte no portal do Azure, pois não é mais aplicável aos builds mais recentes do Windows 10. Você poderá definir as outras três outras configurações e outras configurações de atualização do Windows 10 quando criar anéis de atualização.  

   > [!NOTE]  
   > As configurações de atualização do Windows 10 criadas no Portal Clássico não são exibidas no Portal do Azure após a migração. No entanto, essas configurações são aplicadas. Se você migrar qualquer uma dessas configurações e editar a política migrada do Portal do Azure, essas configurações serão removidas da política.  

2. Exclua as configurações de atualização no Portal Clássico. Depois de migrar para o Portal do Azure e adicionar as mesmas configurações a um anel de atualização, você deve excluir as configurações no portal clássico para evitar possíveis conflitos de política. Por exemplo, quando a mesma configuração é definida com valores diferentes, há um conflito. Não há uma maneira fácil de descobrir porquê a configuração definida no portal clássico não é exibida no portal do Azure.  

## <a name="next-steps"></a>Próximas etapas

[Configurações de atualização do Windows compatíveis com o Intune](../windows-update-settings.md)  

[Relatórios de conformidade do Intune para atualizações](../windows-update-compliance-reports.md)

[Solucionar problemas com anéis de atualização do Windows 10](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Windows-10-Update-Ring-Policies/ba-p/714046)

