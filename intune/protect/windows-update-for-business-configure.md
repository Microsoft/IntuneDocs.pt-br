---
title: Configurar o Windows Update para Empresas no Microsoft Intune – Azure | Microsoft Docs
description: Gerencie as atualizações de software do Windows 10 usando os anéis de atualização e a política de atualizações de recursos. Você pode examinar a conformidade e pausar a instalação da atualização com as configurações do Windows Update para Empresas usando o Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/29/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: c9245ca028bdb5589df8c76b10560d9130a1108c
ms.sourcegitcommit: 9ee2401a2f01373a962749b0728c22385dbcba6d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/29/2020
ms.locfileid: "78181714"
---
# <a name="manage-windows-10-software-updates-in-intune"></a>Gerenciar atualizações de software do Windows 10 no Intune

Use o Intune para gerenciar a instalação de atualizações de software do Windows 10 no Windows Update para Empresas.

Ao usar o Windows Update para Empresas, você simplifica a experiência de gerenciamento de atualizações. Você não precisa aprovar as atualizações individuais para grupos de dispositivos. Você pode gerenciar o risco em seus ambientes configurando uma estratégia de distribuição de atualização. O Intune possibilita [definir as configurações da atualização](windows-update-settings.md) nos dispositivos e adiar a instalação da atualização. Você também pode impedir que os dispositivos instalem recursos de novas versões do Windows para ajudar a mantê-los estáveis e, ao mesmo tempo, permitir que esses dispositivos continuem instalando atualizações de qualidade e segurança.

O Intune armazena apenas as atribuições de política de atualização, não as atualizações em si. Os dispositivos acessam diretamente as atualizações do Windows Update.

O Intune fornece os seguintes tipos de política para gerenciar atualizações:

- **Anel de atualização do Windows 10**: essa política é uma coleção de definições que são configuradas quando as atualizações do Windows 10 são instaladas.

- **Atualizações de recursos do Windows 10 (visualização pública)** : essa política traz os dispositivos para a versão do Windows especificada e congela o conjunto de recursos nesses dispositivos até você optar por atualizá-los para uma versão posterior do Windows.  Embora a versão do recurso permaneça estática, os dispositivos podem continuar a instalar as atualizações de qualidade e segurança disponíveis para aquela versão do recurso.

Você atribui políticas para anéis de atualização do Windows 10 e atualizações de recurso do Windows 10 aos grupos de dispositivos. É possível usar ambos os tipos de política no mesmo ambiente do Intune para gerenciar atualizações de software para seus dispositivos Windows 10 e para criar uma estratégia de atualização que espelhe suas necessidades de negócios.

Para obter mais informações, consulte [Gerenciar as atualizações usando o Windows Update para Empresas](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="prerequisites"></a>Pré-requisitos

Os pré-requisitos a seguir devem ser atendidos para usar as atualizações do Windows para dispositivos Windows 10 no Intune.

- Os PCs com Windows 10 devem executar as seguintes versões do Windows 10:
  - **Anéis de atualização do Windows 10**: versão 1607 ou posterior
  - **Atualizações de recurso do Windows 10**: versão 1703 ou posterior

- O Windows Update dá suporte às seguintes edições do Windows 10:
  - Windows 10
  - Windows 10 Team – para dispositivos Surface Hub (não há suporte para *atualizações de recurso do Windows 10*)
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

## <a name="windows-10-update-rings"></a>Anéis de atualização do Windows 10

Crie anéis de atualização que especifiquem como e quando o Windows como serviço deve atualizar seus dispositivos Windows 10 com atualizações de qualidade e recursos. Com o Windows 10, as novas Atualizações de Recurso e de Qualidade incluem o conteúdo de todas as atualizações anteriores. Desde que você tenha instalado a atualização mais recente, saberá que seus dispositivos Windows 10 estão atualizados. Ao contrário das versões anteriores do Windows, agora você deve instalar a atualização inteira, em vez de parte de uma.

Os anéis de atualização do Windows 10 dão suporte às [marcas de escopo](../fundamentals/scope-tags.md). Use marcas de escopo com anéis de atualização para auxiliar na filtragem e no gerenciamento de conjuntos de configurações que você usa.

### <a name="create-and-assign-update-rings"></a>Criar e atribuir anéis de atualização

1. Entre no [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivos** > **Windows** > **Anéis de atualização do Windows 10** > **Criar**.

3. Na guia *Informações básicas*, especifique um nome, uma descrição (opcional) e selecione **Avançar**.
  ![Criar um anel de atualizações](./media/windows-update-for-business-configure/basics-tab.png)

4. Em **Configurações do anel de atualização**, defina as configurações para suas necessidades empresariais. Saiba mais sobre as configurações disponíveis em [Configurações de atualização do Windows](../protect/windows-update-settings.md). Após definir as configurações de *Atualização e Experiência do usuário*, selecione **Avançar**.

5. Em **Marcas de escopo**, selecione **+ Selecionar marcas de escopo** para abrir o painel *Selecionar marcas* se você desejar aplicá-las ao anel de atualização. Escolha uma ou mais marcas e, em seguida, clique em **Selecionar** para adicioná-las ao anel de atualização e retorne ao painel *Marcas de escopo*.

   Quando estiver pronto, selecione **Avançar** para passar para *Atribuições*.

6. Em **Atribuições**, escolha **+ Selecionar grupos para incluir** e atribua o anel de atualização a um ou mais grupos. Use **+ Selecionar grupos para excluir** a fim de ajustar a atribuição. Selecione **Avançar** para continuar.

7. Em **Examinar + Criar**, examine as configurações e, em seguida, selecione **Criar** quando estiver pronto para salvar seu anel de atualização do Windows 10. Seu novo anel de atualização é exibido na lista de anéis de atualização.

### <a name="manage-your-windows-10-update-rings"></a>Gerenciar seus anéis de atualização do Windows 10

No portal, navegue até **Dispositivos** > **Windows** > **Anéis de atualização do Windows 10** e selecione a política que você deseja gerenciar.  A política é aberta na sua página **Visão geral**.

Nessa página, é possível exibir o status da atribuição dos anéis e selecionar as seguintes ações na parte superior do painel Visão geral para gerenciar o anel de atualização:

- [Excluir](#delete)
- [Pausar](#pause)
- [Retomar](#resume)
- [Estender](#extend)
- [Desinstalar](#uninstall)

![Ações disponíveis](./media/windows-update-for-business-configure/overview-actions.png)

#### <a name="delete"></a>Excluir

Escolha **Excluir** para parar de impor as configurações do anel de atualização do Windows 10 escolhido. A exclusão de um anel remove sua configuração do Intune para que o Intune já não aplique e imponha essas configurações.

A exclusão de um anel do Intune não modifica as configurações nos dispositivos que receberam a atribuição do anel de atualização.  Em vez disso, o dispositivo mantém suas configurações atuais. Os dispositivos não mantêm um registro histórico de quais configurações foram mantidas anteriormente. Os dispositivos também podem receber configurações de anéis de atualização adicionais que permanecem ativos.

##### <a name="to-delete-a-ring"></a>Para excluir um anel

1. Ao exibir a página de visão geral de um Anel de Atualização, escolha **Excluir**.
2. Selecione **OK**.

#### <a name="pause"></a>Pausar

Escolha **Pausar** para impedir que os dispositivos atribuídos recebam Atualizações de Recursos ou Atualizações de Qualidade por até 35 dias a partir do momento em que você pausar o anel. Após o máximo de dias transcorrido, a funcionalidade de pausa expirará automaticamente e o dispositivo verificará se há atualizações aplicáveis nas Atualizações do Windows. Após essa verificação, você poderá pausar as atualizações novamente.
Se você retomar um anel de atualização pausado e pausá-lo novamente, o período de pausa será redefinido para 35 dias.

##### <a name="to-pause-a-ring"></a>Para pausar um anel

1. Quando exibir a página de visão geral de um Anel de Atualização, escolha **Pausar**.
2. Escolha **Recurso** ou **Qualidade** para pausar esse tipo de atualização e, em seguida, escolha **OK**.
3. Após pausar um tipo de atualização, você pode optar por Pausar novamente para interromper o outro tipo de atualização.

Quando um tipo de atualização é pausado, o painel Visão geral desse anel exibe os dias restantes até que o tipo de atualização seja retomado.

> [!IMPORTANT]
> Após emitir um comando para pausar, os dispositivos recebem esse comando na próxima vez que fizerem check-in no serviço. É possível que antes de verificarem, eles possam instalar uma atualização agendada. Além disso, se um dispositivo de destino estiver desativado quando você emitir o comando para pausar, quando você o ativar, ele poderá baixar e instalar as atualizações agendadas antes de verificar com o Intune.

#### <a name="resume"></a>Retomar

Enquanto um anel de atualização estiver pausado, é possível escolher **Retomar** para restaurar as atualizações de Recursos e Qualidade do anel na operação ativa. Após retomar um anel de atualização, você pode pausá-lo novamente.

##### <a name="to-resume-a-ring"></a>Para retomar um anel

1. Quando exibir a página de visão geral de um Anel de Atualização, escolha **Retomar**.
2. Escolha uma das opções disponíveis para retomar atualizações de **Recurso** ou **Qualidade** e, em seguida, escolha **OK**.
3. Após retomar um tipo de atualização, você pode escolher Retomar novamente para reiniciar o outro tipo de atualização.

#### <a name="extend"></a>Estender  

Enquanto um anel de atualização estiver pausado, escolha **Estender** para redefinir o período de pausa das atualizações de Recursos e Qualidade do anel para 35 dias.

##### <a name="to-extend-the-pause-period-for-a-ring"></a>Para Estender o período de pausa de um anel

1. Quando exibir a página de visão geral de um Anel de Atualização, escolha **Estender**.
2. Escolha uma das opções disponíveis para retomar atualizações de **Recurso** ou **Qualidade** e, em seguida, escolha **OK**.
3. Após estender a pausa para um tipo de atualização, você pode escolher Estender novamente para ampliar o outro tipo de atualização.

#### <a name="uninstall"></a>Desinstalar  

Um administrador do Intune pode usar a opção **Desinstalar** para desinstalar (reverter) a atualização de *recurso* ou de *qualidade* mais recente para um anel de atualização ativo ou pausado. Após a desinstalação de um tipo, você pode, em seguida, desinstalar o outro tipo. O Intune não dá suporte nem gerencia a capacidade dos usuários de desinstalar atualizações.  

> [!IMPORTANT]
> Quando você usa a opção *Desinstalar*, o Intune transmite a solicitação de desinstalação para os dispositivos imediatamente.
>
> - Os dispositivos Windows iniciam a remoção das atualizações assim que recebem a alteração na política do Intune. A remoção da atualização não está limitada a agendamentos de manutenção, mesmo quando eles são configurados como parte do anel de atualização.
> - Se a remoção da atualização exigir a reinicialização do dispositivo, o dispositivo será reinicializado sem oferecer aos usuários do dispositivo a opção de adiar.

Para que a opção Desinstalar funcione:

- Um dispositivo deve executar a atualização do Windows de 10 de abril de 2018 (versão 1803) ou posterior.

O dispositivo já deve ter a atualização mais recente instalada. Como as atualizações são cumulativas, os dispositivos que instalam a atualização mais recente têm as atualizações de recurso e de qualidade mais recentes. Um exemplo de quando você pode usar essa opção é na reversão da última atualização, caso descubra uma falha nos computadores com Windows 10.

Considere o seguinte ao usar a opção Desinstalar:

- Desinstalar uma atualização de recurso ou qualidade só está disponível para o canal de serviço que o dispositivo se encontra.

- A desinstalação de atualizações de Recurso ou Qualidade aciona uma política para restaurar a atualização anterior em computadores Windows 10.

- Em dispositivos Windows 10, após a reversão bem-sucedida da atualização de qualidade, os usuários dos dispositivos continuam vendo a atualização listada em **Configurações do Windows** > **Atualizações** > **Histórico de atualização**.

- Especificamente para Atualizações de recursos, o tempo para desinstalar a atualização é limitado de 2 a 60 dias. Esse período é definido pela configuração de Atualização de anéis de atualização **Definir período de desinstalação de atualização de recurso (2 a 60 dias)** . Não é possível reverter uma atualização de recurso em um dispositivo após a atualização ter sido instalada por mais tempo do que o período de desinstalação definido.

  Por exemplo, considere um grupo de atualização com um período de desinstalação de atualização de recurso de 20 dias. Após 25 dias, você decide reverter para a atualização mais recente do recurso e usar a opção Desinstalar.  Os dispositivos que receberam a atualização de recurso há mais de 20 dias não podem desinstalá-la, pois removeram os bits como parte da manutenção. No entanto, os dispositivos que receberam a atualização de recurso há até 19 dias poderão desinstalá-la se fizerem check-in para receber o comando de desinstalação antes de exceder o período de desinstalação de 20 dias.

Saiba mais sobre as políticas do Windows Update em [Atualizar o CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp) na documentação de gerenciamento de clientes do Windows.

##### <a name="to-uninstall-the-latest-windows-10-update"></a>Para desinstalar a atualização mais recente do Windows 10

1. Quando exibir a página de visão geral de um Anel de Atualização, escolha **Desinstalar**.
2. Escolha uma das opções disponíveis para desinstalar atualizações de **Recurso** ou **Qualidade** e, em seguida, escolha **OK**.
3. Após acionar a desinstalação de um tipo de atualização, você pode escolher Desinstalar novamente para remover o tipo de atualização remanescente.

## <a name="windows-10-feature-updates"></a>Atualizações de recursos do Windows 10

*Este recurso está em visualização pública*.

Com as *atualizações de recurso do Windows 10*, selecione a versão do recurso do Windows na qual você deseja que os dispositivos permaneçam, como o Windows 10 versão 1803 ou versão 1809. Você pode definir um nível de recurso da versão 1803 ou posterior.

Quando um dispositivo recebe uma política de atualizações de recursos do Windows 10:

- O dispositivo é atualizado para a versão do Windows especificada na política. Um dispositivo que já executa uma versão posterior do Windows permanece em sua versão atual. Ao congelar a versão, o conjunto de recursos de dispositivos permanece estável durante a política.

- Embora a versão instalada do Windows permaneça definida, os dispositivos ainda podem receber e instalar atualizações de qualidade e segurança da versão do Windows durante o suporte dessa versão, o que ajuda a manter os dispositivos atuais e seguros.

- Ao contrário de usar *Pausar* com um anel de atualização, que expira após 35 dias, a política de atualizações de recursos do Windows 10 permanece em vigor. Os dispositivos não instalarão uma nova versão do Windows até que você modifique ou remova a política de atualizações de recursos do Windows 10. Se você editar a política para especificar uma versão mais recente, os dispositivos poderão instalar os recursos dessa versão do Windows.

### <a name="prerequisites-for-windows-10-feature-updates"></a>Pré-requisitos para atualizações de recursos do Windows 10

Os pré-requisitos a seguir devem ser atendidos para usar as atualizações de recursos do Windows 10 no Intune.

- Os dispositivos devem estar registrados no MDM do Intune e ingressados ou registrados no Azure AD.
- Para usar a política de Atualizações de Recursos com o Intune, os dispositivos precisam ter a telemetria ativada, com uma configuração mínima igual a [*Básico*](../configuration/device-restrictions-windows-10.md#reporting-and-telemetry). A telemetria é configurada em *Relatórios e Telemetria* como parte de uma [política de Restrição de Dispositivo](../configuration/device-restrictions-configure.md).
  
  Os dispositivos que recebem a política de Atualizações de Recursos e que têm a telemetria definida como *Não configurada*, o que significa que ela está desativada, podem instalar uma versão do Windows posterior àquela definida na política de Atualização de Recursos. O pré-requisito de exigência da telemetria está em revisão, pois esse recurso migra para a disponibilidade geral.

### <a name="limitations-for-windows-10-feature-updates"></a>Limitações para atualizações de recursos do Windows 10

- Ao implantar uma política de *atualização de recurso do Windows 10* em um dispositivo que também recebe uma política de *Anel de atualização do Windows 10*, examine as seguintes configurações do anel de política:
  - O **Período de adiamento de atualização de recurso (dias)** deve ser definido como **0**.
  - As atualizações de recurso do anel de atualização devem estar *Em execução*. Elas não devem estar em pausa.

- As políticas de atualização de recursos do Windows 10 não podem ser aplicadas durante a OOBE (experiência pronta para o uso) do Autopilot e serão aplicadas somente na primeira verificação do Windows Update depois que um dispositivo tiver concluído o provisionamento (o que normalmente leva um dia).

### <a name="create-and-assign-windows-10-feature-updates"></a>Criar e atribuir atualizações de recursos do Windows 10

1. Entre no [Centro de Administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivos** > **Windows** > **Atualizações de recursos do Windows 10** > **Criar**.

3. Em **Informações básicas**, especifique um nome, uma descrição (opcional) e, em **Atualização de recurso para implantar**, selecione a versão do Windows com o conjunto de recursos desejado e, em seguida, selecione **Próximo**.

4. Em **Atribuições**, escolha **+ Selecionar grupos para incluir** e atribua a implantação de atualização do recurso a um ou mais grupos. Selecione **Avançar** para continuar.

5. Em **Revisar + criar**, examine as configurações e selecione **Criar** quando estiver pronto para salvar a política de atualizações de recursos do Windows 10.  

### <a name="manage-windows-10-feature-updates"></a>Gerenciar atualizações de recursos do Windows 10

No centro de administração, vá para **Dispositivos** > **Windows** > **Atualizações de recursos do Windows 10** e selecione a política que você deseja gerenciar. A política é aberta no painel **Visão geral**.

Nesse painel, você pode:

- Selecionar **Excluir** para excluir a política do Intune e removê-la dos dispositivos.
- Selecionar **Propriedades** para modificar a implantação.  No painel *Propriedades*, selecione **Editar** para abrir as *Configurações de implantação ou Atribuições*, nas quais é possível modificar a implantação.
- Selecionar **Status de atualização do usuário final** para exibir as informações sobre a política.

## <a name="validation-and-reporting-for-windows-10-updates"></a>Validação e relatórios para atualizações do Windows 10

Para os anéis de atualização e as atualizações de recursos do Windows 10, use os [Relatórios de conformidade do Intune para atualizações](../windows-update-compliance-reports.md) para monitorar o status de atualização dos dispositivos. Essa solução usa as [Conformidade de Atualizações](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) com sua assinatura do Azure.

## <a name="next-steps"></a>Próximas etapas

[Configurações de atualização do Windows compatíveis com o Intune](../windows-update-settings.md)

[Solucionar problemas com anéis de atualização do Windows 10](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Windows-10-Update-Ring-Policies/ba-p/714046)
