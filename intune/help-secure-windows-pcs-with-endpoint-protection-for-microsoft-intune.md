---
title: Endpoint Protection para computadores Windows
titlesuffix: Microsoft Intune
description: Proteja seus computadores gerenciados com o Endpoint Protection, que fornece proteção em tempo real contra ameaças de malware.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 002241bf-6cd0-4c75-a4f0-891ac7e6721a
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.openlocfilehash: 05cc1971f107c7bc3da371de0a916149c879aae0
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187108"
---
# <a name="help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune"></a>Ajudar a proteger computadores Windows com o Endpoint Protection para Microsoft Intune

[!INCLUDE [classic-portal](includes/classic-portal.md)]

O Microsoft Intune pode ajudar você a proteger seus computadores gerenciados com o Endpoint Protection, que fornece proteção em tempo real contra ameaças de malware, mantém definições de malware atualizadas e verifica automaticamente os computadores. O Endpoint Protection também fornece ferramentas que ajudam a gerenciar e monitorar ataques de malware.

Se você ainda não tiver instalado o cliente do Intune em seus computadores, consulte [Install the Windows PC client with Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md) (Instalar o cliente do computador Windows com o Microsoft Intune).

Use as informações contidas nas seções a seguir para ajudá-lo a configurar, implantar e monitorar o Endpoint Protection.

## <a name="choose-when-to-use-endpoint-protection"></a>Escolha quando usar o Endpoint Protection
Como administrador de TI, uma das suas principais prioridades é manter os computadores que você gerencia livre de malware e vírus. Antes de implantar o Intune nos computadores Windows de sua organização, decida como proteger seus computadores, selecionando uma das seguintes opções e definindo as respectivas configurações de política associadas:


|                                                                                                                                                                       Você deseja:                                                                                                                                                                        |                                                                                                       Configurações de política do Endpoint Protection                                                                                                        |                                                                                                                                                  Mais informações                                                                                                                                                  |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                             Use o Endpoint Protection do Microsoft Intune somente se nenhum aplicativo Endpoint Protection de terceiros estiver instalado.<br /><br />Você pode usar o Endpoint Protection do Microsoft Intune em todos os computadores onde nenhum aplicativo Endpoint Protection de terceiros estiver instalado.                                              | Instalar o Endpoint Protection = <strong>Sim</strong><br /><br />Habilitar o Endpoint Protection = <strong>Sim</strong><br /><br />Instalar o Endpoint Protection mesmo que um aplicativo de proteção de ponto de extremidade de terceiros esteja instalado = <strong>Não</strong>  |                                                                      Se for detectado um aplicativo de proteção de ponto de extremidade de terceiros, o Microsoft Intune Endpoint Protection não será instalado, e será desinstalado se tiver sido instalado anteriormente.                                                                       |
| Use o Microsoft Intune Endpoint Protection, mesmo se nenhum aplicativo de proteção de ponto de extremidade de terceiros estiver instalado.<br /><br />Com essa abordagem, o Microsoft Intune Endpoint Protection e o aplicativo de proteção de ponto de extremidade de terceiros serão executados simultaneamente. Essa não é uma configuração recomendada devido a possíveis problemas de desempenho. | Instalar o Endpoint Protection = <strong>Sim</strong><br /><br />Habilitar o Endpoint Protection = <strong>Sim</strong><br /><br />Instalar o Endpoint Protection mesmo que um aplicativo de proteção de ponto de extremidade de terceiros estiver instalado = <strong>Sim</strong> |                        Use quando:<br /><br />-   Desejar passar a usar o Endpoint Protection do Microsoft Intune.<br />– Implantar um novo cliente que usará o Microsoft Intune Endpoint Protection.<br />-...Atualizar qualquer cliente que usará o Endpoint Protection do Microsoft Intune.                         |
|                                                                                                             Use o Intune sem o Endpoint Protection do Microsoft Intune. Em vez disso, você irá contar com um aplicativo de proteção de ponto de extremidade de terceiros.                                                                                                             |                                                                                                Instalar o Endpoint Protection = <strong>Não</strong>                                                                                                 | Caso os computadores não estejam usando um aplicativo Endpoint Protection de terceiros, essa configuração não é recomendada, pois pode expor os computadores da organização a malwares ou outros ataques.<br /><br />O Microsoft Intune Endpoint Protection não está instalado ou se tiver sido instalado anteriormente será desinstalado. |

Para alternar de seu aplicativo Endpoint Protection atual ao Endpoint Protection do Microsoft Intune, faça o seguinte:

1.  Deixe seu aplicativo Endpoint Protection atual em execução enquanto você implanta o software cliente do Intune nos computadores.

2.  Confirme se o Endpoint Protection do Microsoft Intune está instalado e se está ajudando a proteger os computadores cliente.

3.  Remova o software de proteção de ponto de extremidade de terceiros por meio de um dos procedimentos a seguir:

    -   Uso da distribuição de software do Intune para implantar uma ferramenta de remoção de software que é fornecida pelo fabricante do aplicativo Endpoint Protection de terceiros. Para obter mais informações, consulte [Deploy apps with Microsoft Intune](apps-deploy.md) (Implantar aplicativos com o Microsoft Intune).

    -   Removendo manualmente o aplicativo de proteção de ponto de extremidade de terceiros.

> [!NOTE]
> O Intune não desinstalará aplicativos Endpoint Protection de terceiros.

## <a name="configure-microsoft-intune-endpoint-protection"></a>Configurar o Microsoft Intune Endpoint Protection
Use as etapas a seguir para ajudá-lo a configurar o Endpoint Protection para o Microsoft Intune.

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Política** > **Adicionar Política**.

2.  Expanda **Gerenciamento do computador** e selecione **Configurações de Agente do Microsoft Intune**. Selecione **Criar e Implantar uma Política Personalizada** para especificar a política para as configurações do Endpoint Protection. Escolha o botão **Criar Política**.

É possível usar as configurações recomendadas ou personalizá-las. Se você precisar de mais informações sobre como criar e implantar políticas, consulte o tópico [Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

  ![Configurações do Endpoint Protection](media/pol-sa-pc-endpoint-policy.png)

Também é possível exibir a política do Endpoint Protection implantada na página **Todas as Políticas** do workspace **Política**.

## <a name="specify-endpoint-protection-service-settings"></a>Especificar configurações do serviço Endpoint Protection

|                                                 Configuração de política                                                  |                                                                                                                                                                                                                                                                                                                                                                                                             Detalhes                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                  <strong>Instalar o Endpoint Protection</strong>                                   | Defina como <strong>Sim</strong> para instalar o Endpoint Protection em computadores gerenciados. Se durante a instalação for detectado um aplicativo de proteção de ponto de extremidade de terceiros, o Endpoint Protection não será instalado, a menos que a configuração <strong>Instalar o Endpoint Protection mesmo se um aplicativo do Endpoint Protection de terceiros estiver instalado</strong> esteja definida como <strong>Sim</strong>. <strong>Nota:</strong> o Intune Endpoint Protection é instalado em computadores gerenciados por padrão. Se não quiser instalar o Endpoint Protection nos computadores gerenciados, você deverá configurar essa política como <strong>Não</strong>. Se o Endpoint Protection tiver sido instalado anteriormente e a política for atualizada para <strong>Não</strong>, o cliente do Endpoint Protection será desinstalado.<br />Valor recomendado: <strong>Sim</strong> |
| <strong>Instalar o Endpoint Protection mesmo se um aplicativo do Endpoint Protection de terceiros estiver instalado</strong> |                                                                                                                                                                                                                                                                                                                Defina como <strong>Sim</strong> para instalar o Endpoint Protection do Microsoft Intune mesmo se um aplicativo Endpoint Protection de terceiros for detectado.<br /><br />Valor recomendado: <strong>Sim</strong>                                                                                                                                                                                                                                                                                                                |
|                                   <strong>Habilitar o Endpoint Protection</strong>                                   |                                                                                                                                                                                                            Defina como <strong>Sim</strong> para habilitar o Microsoft Intune Endpoint Protection em computadores que tenham o cliente do Endpoint Protection.<br /><br />Se definido para <strong>Não</strong>, e o Microsoft Intune Endpoint Protection estiver instalado, a interface do usuário cliente do Endpoint Protection não será exibida para os usuários e todos os recursos de proteção estarão inativos.<br /><br />Valor recomendado: <strong>Sim</strong>                                                                                                                                                                                                             |
|                                       <strong>Desabilitar interface do usuário de cliente</strong>                                        |                                                                                                                                                                                                                                                                                                      Defina como <strong>Sim</strong> para ocultar a interface do usuário do cliente do Endpoint Protection do Microsoft Intune dos usuários (exige a reinicialização do computador cliente para entrar em vigor).<br /><br />Valor recomendado: <strong>Não</strong>                                                                                                                                                                                                                                                                                                       |
| <strong>Instalar o Endpoint Protection mesmo se um aplicativo do Endpoint Protection de terceiros estiver instalado</strong> |                                                                                                                                                                                                                                                                                                       Defina como <strong>Sim</strong> para forçar o Endpoint Protection do Microsoft Intune, mesmo se um aplicativo Endpoint Protection de terceiros for detectado.<br /><br />Valor recomendado: <strong>Não</strong>                                                                                                                                                                                                                                                                                                       |
|                    <strong>Criar um ponto de restauração do sistema antes da cura contra o malware</strong>                    |                                                                                                                                                                                                                                                                                                                                 Defina para <strong>Sim</strong> para criar um ponto de restauração do sistema do Windows antes que qualquer remediação de malware seja iniciada.<br /><br />Valor recomendado: <strong>Sim</strong>                                                                                                                                                                                                                                                                                                                                  |
|                                 <strong>Acompanhar malwares resolvidos (dias)</strong>                                  |                                                                                                                                                                                                                                                                                      Habilita o Endpoint Protection para rastrear malwares resolvidos por um tempo determinado para que seja possível verificar manualmente os computadores anteriormente infectados.<br /><br />É possível especificar qualquer valor de 0 a 30 dias.<br /><br />Valor recomendado: <strong>7 dias</strong>                                                                                                                                                                                                                                                                                       |

Se você tiver definido os valores da política para **Instalar o Endpoint Protection** e **Habilitar o Endpoint Protection** como **Sim**, e o valor da política para **Instalar o Endpoint Protection mesmo se um aplicativo do Endpoint Protection de terceiros estiver instalado** como **Não**, o Microsoft Intune Endpoint Protection detectará que outro aplicativo de proteção de ponto de extremidade está instalado. Isso significa que o Endpoint Protection não será instalado ou será desinstalado se já estiver presente. No entanto, o Microsoft Intune Endpoint Protection relata a integridade do outro aplicativo de proteção do ponto de extremidade no Intune.

  O Microsoft Security Essentials alerta você com a proteção em tempo real quando ameaças potenciais, como vírus e spyware, estão tentando se instalar por conta própria ou sendo executados em seu computador. No momento em que isso acontecer, você verá uma mensagem na área de notificação do lado direito da barra de tarefas.

### <a name="specify-real-time-protection-settings"></a>Especificar configurações de proteção em tempo real

|Configuração de política|Detalhes|
|------------------|--------------------|
|**Habilitar proteção em tempo real**|Permite monitoramento e verificação de todos os arquivos e aplicativos que são acessados. Ele também bloqueia todos os aplicativos e arquivos mal-intencionados antes que sejam executados nos computadores.<br /><br />Valor recomendado: **Sim**|
|**Verificar todos os downloads**|Permite a verificação de todos os arquivos e anexos que são baixados da Internet para os computadores.<br /><br />Valor recomendado: **Sim**|
|**Monitorar a atividade de arquivos e programas nos computadores**|Permite o monitoramento de arquivos de entrada e saída e da atividade do programa em computadores. Com essa configuração, o Endpoint Protection pode monitorar quando os arquivos e programas começam a ser executados e alertá-lo sobre todas as ações que desempenham ou ações que são realizadas neles.<br /><br />Valor recomendado: **Sim**|
|**Arquivos monitorados**|Permite que você escolha se apenas os arquivos de entrada, de saída ou todos os arquivos serão monitorados.<br /><br />Valor recomendado: **Monitorar todos os arquivos**|
|**Habilitar o comportamento de monitoramento**|Permite que o Microsoft Intune Endpoint Protection verifique determinados padrões de atividades suspeitas em computadores cliente.<br /><br />Valor recomendado: **Sim**|
|**Habilitar Sistema de Inspeção de Rede**|Habilita o Network Inspection System (NIS) nos computadores cliente. O NIS utiliza assinaturas de vulnerabilidades conhecidas do [Centro de Proteção contra Malware da Microsoft](https://go.microsoft.com/fwlink/?LinkId=234249) para ajudar a detectar e bloquear o tráfego mal-intencionado na rede.<br /><br />Valor recomendado: **Sim**|

  ![Configurações em tempo real do Endpoint Protection](media/pol-sa-pc-policy-realtime.png)

### <a name="specify-scan-schedule-settings"></a>Especificar configurações do agendamento de verificação

|Configuração de política|Mais informações|
|------------------|--------------------|
|**Agendar uma verificação rápida diária**|Agenda uma verificação rápida diária de arquivos importantes do sistema usados com frequência nos computadores. Essa verificação rápida tem um impacto mínimo sobre o desempenho.<br /><br />Valor recomendado: **Sim**|
|**Executar uma verificação rápida se duas verificações rápidas consecutivas não puderam ser feitas**|Configura o Endpoint Protection para executar automaticamente uma verificação rápida nos computadores se eles tiverem perdido duas verificações rápidas consecutivas.<br /><br />Valor recomendado: **Sim**|
|**Agendar uma verificação completa**|Configura uma verificação completa de todos os arquivos e recursos nos discos rígidos dos computadores locais. Essa verificação pode demorar e afetar o desempenho do computador (o tempo que ela leva dependendo do número de arquivos e recursos verificados).<br /><br />Valor recomendado: **Não**|
|**Executar uma verificação completa se duas verificações rápidas consecutivas não puderam ser feitas**|Configura o Endpoint Protection para executar automaticamente uma verificação completa nos computadores se eles tiverem perdido duas verificações consecutivas.<br /><br />Valor recomendado: Não configurado|

### <a name="specify-scan-options-settings"></a>Especificar configurações de opções de verificação

|Configuração de política|Detalhes|
|------------------|--------------------|
|**Executar uma verificação completa após a instalação do Endpoint Protection**|Defina como **Sim** para permitir que o Endpoint Protection execute automaticamente uma verificação completa do sistema após a instalação nos computadores. Essa verificação é executada apenas quando os computadores estão ociosos, de modo a minimizar o efeito sobre a produtividade do usuário.<br /><br />Valor recomendado: **Sim**|
|**Executar automaticamente uma verificação completa quando necessário para acompanhar a remoção de malware**|Defina como **Sim** para deixar o Endpoint Protection executar automaticamente uma verificação completa do sistema nos computadores após a remoção de malware para confirmar se outros arquivos não foram afetados.<br /><br />Valor recomendado: **Sim**|
|**Iniciar uma verificação agendada somente quando o computador estiver ocioso**|Defina para **Sim** para impedir o início de verificações agendadas quando os computadores estiverem em uso, de modo a evitar a perda da produtividade do usuário.<br /><br />Valor recomendado: **Sim**|
|**Verificar as definições de malware mais recentes antes de iniciar uma verificação**|Defina como **Sim** para permitir que o Endpoint Protection verifique automaticamente as últimas definições de malware antes de iniciar uma verificação nos computadores.<br /><br />Valor recomendado: **Sim**|
|**Verificar arquivos mortos**|Defina como **Sim** para configurar o Endpoint Protection para fazer a verificação de malware em arquivos compactados (como .zip ou .cab) nos computadores.<br /><br />Valor recomendado: **Não**|
|**Verificar mensagens de email**|Defina como **Sim** para configurar o Endpoint Protection para verificar mensagens de email recebidas à medida que forem recebidas nos computadores.<br /><br />Valor recomendado: **Sim**|
|**Verificar arquivos abertos de pastas compartilhadas na rede**|Defina como **Sim** para configurar o Endpoint Protection para verificar os arquivos que são abertos de pastas compartilhadas na rede. Normalmente, esses arquivos são acessados por meio de um caminho UNC. Habilitar esse recurso pode causar problemas aos usuários que têm acesso somente leitura, porque eles não podem remover malwares.<br /><br />Valor recomendado: **Não**|
|**Verificar unidades de rede mapeadas**|Defina como **Sim** para configurar o Endpoint Protection para verificar arquivos em unidades de rede mapeadas. Habilitar esse recurso pode causar problemas aos usuários que têm acesso somente leitura, porque eles não podem remover malwares.<br /><br />Valor recomendado: **Não**|
|**Verificar unidades removíveis**|Defina como **Sim** para configurar o Endpoint Protection para fazer a verificação de malware e software indesejado no conteúdo de unidades removíveis, como unidades flash USB, durante a execução de uma verificação completa nos computadores.<br /><br />Valor recomendado: **Sim**|
|**Limitar o uso da CPU durante uma verificação**|Define o percentual máximo de uso da CPU que pode ser usado durante as verificações agendadas nos computadores. É possível definir esse valor de 1 a 100 por cento.<br /><br />Valor recomendado: **50%**|

### <a name="choose-default-actions-settings"></a>Escolher as configurações de ações padrão

A configuração **Escolha como o Endpoint Protection atua em malwares dos seguintes níveis de alerta** especifica a ação padrão que o Endpoint Protection realiza quando um malware de vários níveis de alerta é detectado. Para cada nível de alerta, remova o malware, coloque-o em quarentena ou realize a ação recomendada pela Microsoft.

Valor recomendado: **Ação recomendada**, que permite que o Endpoint Protection recomende a ação.   

### <a name="decide-whether-to-choose-the-excluded-files-and-folders-settings"></a>Decidir se deseja escolher as configurações de arquivos e pastas excluídas

A configuração **Arquivos e pastas a serem excluídos ao executar uma verificação ou usar proteção em tempo real** exclui arquivos ou pastas específicas quando uma verificação é executada ou quando a proteção em tempo real é usada em computadores.

### <a name="decide-whether-to-choose-the-excluded-processes-settings"></a>Decidir se deseja escolher as configurações de processos excluídos

A configuração **Processos a serem excluídos ao executar uma verificação ou usar a proteção em tempo real** permite que você exclua processos específicos quando uma verificação é executada ou quando a proteção em tempo real é usada nos computadores. É possível excluir apenas os arquivos com as seguintes extensões: **.exe**, **.com** ou **.scr**.

### <a name="decide-whether-to-choose-the-excluded-file-types-settings"></a>Decidir se deseja escolher as configurações de tipos de arquivo excluídos

A configuração **Extensões de arquivo a serem excluídos ao executar uma verificação ou usar proteção em tempo real** permite que você exclua extensões de nome do arquivo específicas quando uma verificação é executada ou quando a proteção em tempo real é usada nos computadores.

### <a name="specify-microsoft-active-protection-service-settings"></a>Especificar definições do Microsoft Active Protection Service
O Microsoft Active Protection Service é uma comunidade online que ajuda você a decidir como reagir às ameaças potenciais. A comunidade também ajuda a interromper a propagação de novas infecções por malware. Você pode **Ingressar no Microsoft Active Protection Service** selecionando **Sim** e, em seguida, especificando seu **Nível de associação**:
  - **Básico** - envia informações básicas à Microsoft sobre o malware detectado. Isso inclui a origem do software, as ações aplicadas por você ou automaticamente pelo Endpoint Protection e se elas foram bem-sucedidas.
  - **Avançado** - envia mais informações à Microsoft sobre malware, spyware e software possivelmente indesejado. Isso inclui informações sobre o local do software, nomes de arquivos, como o software funciona e como ele afetou o seu computador.

Você também pode **Receber definições dinâmicas baseadas nos relatórios do Microsoft Active Protection Service**.

## <a name="choose-management-tasks-for-endpoint-protection"></a>Escolher tarefas de gerenciamento do Endpoint Protection
As tarefas a seguir lhe ajudarão a realizar várias tarefas de gerenciamento em computadores gerenciados que executam o Endpoint Protection:
- Atualizar definições de malware
  - Console do Intune – no workspace **Grupos**, selecione os computadores que deseja atualizar. Escolha **Tarefas Remotas** &gt; **Atualizar Definições de Malware**.
  - Computador gerenciado - inicie o software cliente do Endpoint Protection na área de notificação do Windows. Escolha a guia **Atualização** e escolha **Atualizar**.
- Executar uma verificação de malware:
  - Console do Intune – no workspace **Grupos**, selecione os computadores que deseja verificar. Escolha **Executar verificação completa de malware** ou **Executar verificação rápida de malware**.
  - Computador gerenciado - inicie o software cliente do Endpoint Protection na área de notificação do Windows. Selecione **Rápida**, **Completa** ou **Personalizada**, e escolha **Verificar agora**.

É possível exibir o status de uma tarefa remota, escolhendo o link **Tarefas Remotas** no canto inferior direito do console do Intune. A caixa de diálogo **Status da tarefa remota** lista as tarefas remotas atuais, seus status, nome do dispositivo e todos os erros reportados. Ela também fornece um link para informações de solução de problemas, se apropriado.

## <a name="monitor-endpoint-protection"></a>Monitorar o Endpoint Protection
Monitore o status de malware em seus computadores, usando o workspace **Proteção** do [console de administração do Microsoft Intune](https://manage.microsoft.com/). Esse workspace contém duas páginas:
- **Visão geral da proteção** – exibe problemas importantes como links nos quais é possível clicar para obter mais informações. Veja a seguir alguns problemas que podem ser exibidos:
  - **Instâncias de malware que precisam de acompanhamento** – clique no link para ver uma lista de problemas de malware, incluindo a ação de acompanhamento que precisa ser tomada para resolver o problema. Também é possível explorar essa lista para ver quais computadores foram afetados.
  - **Computadores com malware que precisam de acompanhamento** – clique no link para ver todos os computadores com problemas de malware não resolvidos, incluindo a ação de acompanhamento que precisa ser tomada para resolver o problema.
  - **Dispositivos desprotegidos** – clique no link para ver os computadores que não estão protegidos por nenhum software de Endpoint Protection, seja porque não há nenhum software instalado ou porque ocorreu um erro. Selecione um computador para ver mais detalhes.
  - **Dispositivos executando outro aplicativo Endpoint Protection** – clique no link para ver os computadores que estão executando um aplicativo Endpoint Protection de terceiros.
- **Todos os Malwares** – exibe uma lista de todos os malwares ativos encontrados nos computadores. É possível explorar essa lista para ver todos os computadores que foram afetados por um determinado malware ou selecionar uma das seguintes tarefas:
  - **Exibir propriedades** – abre uma página com mais informações sobre o malware selecionado.
  - **Informações sobre este malware** – abre um tópico do Centro de Proteção contra Malware da Microsoft com mais informações sobre o malware.

> [!IMPORTANT]
> O workspace **Proteção** não é exibido no console de administração até que você tenha instalado o cliente e gerencie pelo menos um cliente do computador.

  ![Monitorar o Endpoint Protection](media/pol-sa-ep-monitor.png)

### <a name="how-to-view-recent-detection-paths-for-malware-on-computers"></a>Como exibir Caminhos de detecção recentes para malware em computadores
O Intune pode exibir os caminhos de até 10 das instâncias de malware detectadas mais recentemente em um dispositivo. O **Caminho de detecção recente** fica desabilitado por padrão. Para habilitar a exibição:

1. No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** > **Todos os Dispositivos** > **Todos os Computadores**.
2. Clique no computador cujos caminhos de detecção recentes você deseja ver e selecione **Propriedades**.
3. Selecione **Malware** nas guias na parte superior.

   ![Selecione a guia Malware e, em seguida, clique na caixa de seleção Caminhos de Detecção Recentes](media/malware-path-column.png)
4. Clique com o botão direito no cabeçalho da coluna. É exibida uma lista das de colunas disponíveis. Marque a caixa de seleção **Caminhos de detecção recentes** na lista. A coluna **Caminhos de detecção recentes** aparece e exibe até 10 instâncias de malware mais recentes monitoradas no dispositivo.

## <a name="run-a-malware-scan-or-update-malware-definitions-on-a-computer"></a>Executar uma verificação de malware ou atualizar definições de malware em um computador
O Intune pode executar uma verificação completa ou rápida de malware usando o Endpoint Protection ou o Windows Defender em um computador gerenciado remotamente com o cliente do Intune instalado.

1. No [console de administração do Microsoft Intune](https://manage.microsoft.com/) vá até **Grupos** > **Visão geral** > **Todos os Dispositivos** > **Todos os Computadores** e selecione o computador que deseja como destino.

2. Escolha a lista suspensa **Tarefas Remotas** e selecione a tarefa a ser executada no computador remoto.

## <a name="need-more-help"></a>Precisa de mais ajuda?
Para obter mais ajuda e suporte, consulte [Troubleshoot Endpoint Protection in Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md) (Solucionando problemas do Endpoint Protection no Microsoft Intune).

### <a name="see-also"></a>Consulte Também
[Políticas para proteger computadores Windows](policies-to-protect-windows-pcs-in-microsoft-intune.md)
