---
title: Atualizações de software para computadores Windows
titleSuffix: Microsoft Intune
description: O Intune ajuda você a manter seus computadores gerenciados atualizados garantindo que os últimos patches e atualizações de software sejam instalados rapidamente.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.assetid: 48e9c41a-d2de-424e-9610-cfd1ad514210
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd32943be10cfcaa2e839d8c27f8d9668f9289f4
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72510166"
---
# <a name="keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune"></a>Manter computadores Windows atualizados com as atualizações de software no Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

> [!NOTE]
> As informações descritas neste tópico se aplicam somente a áreas de trabalho do Windows que estão sendo gerenciadas como computadores por meio do cliente de software do Intune. Se você quiser gerenciar atualizações para computadores Windows registrados como dispositivos móveis, consulte [gerenciar atualizações de software no Intune](../protect/windows-update-for-business-configure.md).

O Microsoft Intune pode ajudá-lo a proteger seus computadores gerenciados de várias maneiras, incluindo o gerenciamento de atualizações de software que mantêm seus computadores atualizados, assegurando que os patches e as atualizações de software mais recentes sejam instalados rapidamente.

Se você ainda não tiver instalado o cliente do Intune em seus computadores, consulte [Install the Windows PC client with Microsoft Intune](../install-the-windows-pc-client-with-microsoft-intune.md) (Instalar o cliente do computador Windows com o Microsoft Intune).

Quando houver novas atualizações disponíveis no Microsoft Update ou você tiver criado uma atualização de terceiros, e elas forem aplicáveis aos seus computadores gerenciados, é exibida uma notificação na página **Visão Geral** do workspace de **Atualizações**. Depois de escolher esse link de notificação, você poderá executar várias operações, como exibir mais informações sobre a atualização, aprovar ou recusar a atualização e exibir os computadores que instalarão a atualização, caso seja aprovada.

> [!IMPORTANT]
> O workspace de **Atualizações** não é exibido no console do administrador até que você tenha instalado o cliente e gerencie com êxito pelo menos um cliente do computador.

À medida que as atualizações são aprovadas e instaladas, você pode examinar o êxito ou a falha da instalação no workspace de **Atualizações** do console do Intune.

As seções a seguir ajudarão você a manter o software atualizado nos computadores gerenciados.

## <a name="before-you-start"></a>Antes de começar
Antes de começar a criar e aprovar as atualizações de software, configure e implante as políticas nos seus computadores que controlam quando e como as atualizações serão instaladas.

### <a name="to-configure-update-policy-settings"></a>Para definir as configurações da política de atualização

1. No [console de administração do Microsoft Intune](https://manage.microsoft.com/), selecione **Política** &gt; **Visão geral** &gt; **Adicionar Política**.

2. Configure e implante uma política de **Configurações do Agente do Microsoft Intune** para as configurações de atualização. É possível usar as configurações recomendadas ou personalizá-las. Se você precisar de mais informações sobre como criar e implantar políticas, consulte [Common Windows PC management tasks with the Microsoft Intune computer client](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) (Tarefas comuns de gerenciamento de computador Windows com o cliente do computador Microsoft Intune).

A tabela a seguir mostra os valores que você pode configurar na política e também os valores recomendados que serão usados se você não personalizar a política. Você pode encontrar essas configurações na seção **Atualizações** .

  |Configuração de política|Detalhes|
    |------------------|--------------------|
    |**Frequência de detecção de atualizações e de aplicativos (horas)** |Especifica com que frequência (de 8 a 22 horas) o Intune procura novas atualizações e aplicativos.<br /><br />Valor recomendado: **8** horas.|
    |**Instalação automatizada ou solicitada de atualizações e aplicativos** |Especifica se as atualizações são instaladas automaticamente ou se o usuário será avisado antes da instalação. Além disso, essa configuração permite a você agendar a instalação de atualizações e aplicativos.<br /><br />**Instalar atualizações e aplicativos automaticamente conforme agendado** instala atualizações e aplicativos usando a programação especificada.<br /><br />Como uma configuração de política dependente, **Usar Manutenção Automática para computadores com Windows**  especifica quais atualizações e aplicativos são instalados na janela de Manutenção Automática do Windows.<br /><br />**Solicitar instalação do usuário** avisa o usuário para instalar as atualizações quando estiverem prontas.<br /><br />Valores recomendados:<br /><br />**Instalar atualizações e aplicativos automaticamente conforme agendado** selecionado<br /><br />**Dia do agendamento: todos os dias**<br /><br />**Hora do agendamento: 3h00**<br /><br />**Usar Manutenção Automática para computadores com Windows** selecionado|
    |**Permitir a instalação imediata de atualizações que não interrompem o Windows** |**Permitir** instala atualizações logo depois que elas são baixadas, exceto aquelas que podem interromper ou reiniciar o Windows. Essas atualizações são instaladas de acordo com a definição da configuração **Instalação de atualizações automatizada ou com aviso** .<br /><br />**Não permitir** instala atualizações de acordo com a configuração **Instalação automatizada ou solicitada de atualizações**.<br /><br />Valor recomendado: **Allow** |
    |**Atraso para reiniciar o Windows após a instalação de atualizações e aplicativos agendados (minutos)** |Especifica (de 1 a 30 minutos) o tempo a aguardar para reiniciar o Windows após a instalação das atualizações e aplicativos agendados.<br /><br />Valor recomendado: **15 minutos** |
    |**Atraso após a reinicialização do Windows para iniciar a instalação de atualizações e aplicativos agendados pendentes (minutos)** |Especifica (de 1 a 60 minutos) quanto tempo esperar para iniciar a instalação de atualizações e aplicativos após a reinicialização do Windows quando uma atualização agendada foi ignorada.<br /><br />Valor recomendado: **5 minutos**|
    |**Permitir que o usuário conectado controle a reinicialização do Windows após a instalação de atualizações e aplicativos agendados** |Especifica se o usuário conectado pode atrasar a reinicialização do Windows (se definido como **Sim**) ou ser notificado sobre a reinicialização automática do Windows (se definido como **Não**). Se nenhum usuário estiver conectado quando a instalação agendada de atualizações e aplicativos for concluída, o Windows será reiniciado automaticamente quando necessário. Quando definido como **Não**, por padrão, tempo antes da reinicialização do Windows é definido como 5 minutos.<br /><br />Valor recomendado: **Sim**|
    |**Solicitar que o usuário reinicie o Windows durante as atualizações obrigatórias do agente cliente do Intune** |Especifica se os usuários conectados recebem uma solicitação para reiniciar o Windows quando a atualização obrigatória de agente do cliente do Intune exigir reinicialização do Windows.<br /><br />Valor recomendado: **Sim**|
    |**Agendamento de instalação de atualizações obrigatórias do agente cliente do Microsoft Intune** |Agendamento da instalação de atualizações do cliente.<br /><br />Valor recomendado: não configurado|
    |**Atraso entre prompts para reiniciar o Windows após a instalação de atualizações e aplicativos agendados (minutos)** |Especifica a frequência (de 1 a 1440 minutos) com que o usuário recebe uma solicitação para reiniciar o Windows quando uma atualização ou instalação agendada que requer reinicialização do Windows é realizada e o usuário atrasa a reinicialização.<br /><br />Valor recomendado: **30 minutos** |

## <a name="update-software-made-by-microsoft"></a>Atualização de software feita pela Microsoft
A atualização do software da Microsoft requer muito pouco trabalho por você. No entanto, antes de começar, há duas coisas que você deve configurar:

- **Categorias de produtos e classificações de atualizações** – Define as categorias e classificações das atualizações que você deseja disponibilizar aos computadores. Por exemplo, você pode decidir que deseja instalar apenas atualizações críticas para o Microsoft Office.

- **Regras de aprovação automática** – Essas regras aprovam automaticamente os tipos especificados de atualizações e reduzem a sobrecarga administrativa. Por exemplo, talvez você queira aprovar automaticamente todas as atualizações de software críticas.

Use os dois procedimentos a seguir para ajudá-lo a se preparar usar atualizações de software:

### <a name="configure-the-product-categories-and-update-classifications-you-want-to-make-available-to-managed-computers"></a>Configure as categorias de produtos e classificações de atualizações que você deseja tornar disponíveis para os computadores gerenciados

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Atualizações de** &gt; **Administração**.

2. Na página **Configurações do Serviço: Atualizações**, na lista **Categoria do Produto**, selecione as categorias que deseja disponibilizar para os computadores. Observe que as atualizações mais comuns são selecionadas por padrão.

    > [!IMPORTANT]
    > Para garantir que os computadores recebam as atualizações que foram aprovadas pelo administrador, a configuração **Especificar a localização do serviço intranet de atualização da Microsoft** de Política de Grupo do Windows Server Update Services (WSUS) não é aplicada aos computadores registrados com o Intune.

3. Na lista **Classificação de Atualização** , selecione as classes de atualização que deseja disponibilizar para os computadores gerenciados. Neste caso também, as opções mais comuns são selecionadas por padrão.

4. Escolha **Salvar** para armazenar suas seleções.

### <a name="to-configure-automatic-approval-rules-for-software-updates"></a>Para configurar as regras de aprovação automática para atualizações de software

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Atualizações de** &gt; **Administração**.

2. Na seção **Regras de Aprovação Automática** da página **Configurações do Servidor: Atualizações**, escolha **Novo**.

3. Na página **Geral** do Assistente para Criar Regra de Aprovação Automática, especifique um nome e uma descrição opcional para a regra.

4. Na página **Categorias de Produtos** , selecione todos os produtos para os quais você deseja que as atualizações sejam aprovadas automaticamente.

5. Na página **Classificações de Atualizações** , especifique as classificações de atualizações para as quais você deseja que as atualizações sejam aprovadas automaticamente.

6. Na página **Implantação** , proceda da seguinte maneira:

    - Selecione os grupos de computadores nos quais você deseja implantar a nova regra e escolha **Adicionar**.

    - Para especificar um prazo para a instalação das atualizações, marque a caixa de seleção **Imponha um prazo de instalação para essas atualizações** e, na lista **Prazo de instalação** , selecione um intervalo de prazo de instalação.

        > [!NOTE]
        > Se você especificar um prazo de instalação, o computador gerenciado poderá exigir uma ou mais reinicializações após o fim do intervalo de prazo.

    - Quando você terminar, escolha **Avançar**.

7. Na página **Resumo**, examine as configurações da nova regra e escolha **Concluir**.

A nova regra é mostrada na seção **Regras de Aprovação Automática** da página **Configurações do Serviço: Atualizações**.

> [!NOTE]
> Quando você cria uma regra de aprovação automática, ela aprova apenas as futuras atualizações e não aprova automaticamente as atualizações anteriores já existentes no Intune. Para aprovar essas atualizações, você precisa executar a regra de aprovação automática.


### <a name="to-edit-run-or-delete-an-automatically-approved-update-rule"></a>Para editar, executar ou excluir uma regra de atualização automaticamente aprovada

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Atualizações de** &gt; **Administração**.

2. Na seção **Regras de Aprovação Automática** , selecione uma regra e siga um destes procedimentos:

    - Para editar a regra, escolha **Editar** e altere os parâmetros da regra no **Assistente de Atualização de Regras de Aprovação Automática**.

    - Para executar a regra, escolha **Executar Selecionados**.

    - Para excluir a regra, escolha **Excluir**.

        > [!NOTE]
        > A exclusão de uma regra não afeta as atualizações anteriores aprovadas pela regra excluída.

## <a name="update-software-not-made-by-microsoft"></a>Atualização de software não realizada pela Microsoft
Você pode implantar atualizações de software que não são feitas pela Microsoft. Faça isso usando o assistente **Carregar Atualização** , para que a atualização seja colocada no espaço de Armazenamento em Nuvem. Depois disso, você pode aprovar ou recusar a atualização, exatamente como qualquer software da Microsoft.

### <a name="to-upload-and-configure-a-third-party-update"></a>Para carregar e configurar uma atualização de terceiros

1. No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Atualizações** &gt; **Visão geral** &gt; **Carregar**.

2. Na página **Arquivos de atualização**, escolha **Procurar** para selecionar os arquivos de instalação necessários para instalar o pacote de atualização. Esse arquivo pode ser um arquivo do Windows Installer (.msi), um arquivo de patch do Windows Installer (.msp) ou um arquivo de programa .exe. Você também pode incluir quaisquer arquivos ou pastas adicionais que estejam na mesma pasta que o arquivo de instalação.

    O tamanho total dos arquivos selecionados para carregamento é exibido. Observe que esse tamanho não inclui os tamanhos descompactados ou expandidos dos arquivos de instalação.

3. Após a especificação dos arquivos de instalação, a página **Descrição da atualização** exibe o nome, a descrição e a classificação das informações do software que o Intune extraiu dos arquivos de instalação do software. Você pode selecionar uma classificação para rotular o tipo de atualização que está implantando (Atualizações, Atualizações Críticas, Atualizações de Segurança, Pacotes Cumulativos de Atualizações ou Service Packs). Escolha **Avançar** quando terminar.

4. Na página **Requisitos** do assistente, escolha a arquitetura (32 bits, 64 bits ou ambas) e os sistemas operacionais dos computadores gerenciados aos quais esta atualização será aplicável.

5. Na página **Regras de detecção**, especifique como o Intune determina se a atualização já existe nos computadores gerenciados. Se você usar a opção padrão, o **Usar as regras de detecção padrão**, o Intune sempre instalará o pacote de atualização em cada computador definido como destino uma vez.

    > [!NOTE]
    > Se o arquivo de instalação de atualização especificado for do Windows Installer ou .msp, a página **Regras de detecção** do assistente não aparecerá. Isso ocorre porque arquivos do Windows Installer e .msp contêm suas próprias instruções para detectar instalações anteriores de atualização.

    Selecione uma ou mais das regras a seguir para determinar se a atualização já está instalada nos computadores gerenciados:

    - **Arquivo existente**

    - **Código de produto MSI existente**

    - **Chave do Registro existente**

6. Forneça quaisquer informações adicionais que sejam necessárias para configurar a regra de detecção, como o caminho e o nome do arquivo, o código do produto Windows Installer ou uma chave do Registro e escolha **Avançar**.

7. Na página **Pré-requisitos** do assistente, especifique todo software que já deva estar instalado para poder instalar esta atualização. É possível especificar **Nenhum**, selecionar um pacote de software que já tenha sido adicionado e seja gerenciado pelo Intune ou especificar uma das regras a seguir para descrever o software:

    - **Arquivo existente**

    - **Código de produto MSI existente**

    - **Chave do Registro existente**

8. Forneça quaisquer informações adicionais que sejam necessárias para configurar a regra de detecção, como o caminho e o nome do arquivo, o código do produto Windows Installer ou uma chave do Registro e escolha **Avançar**.

9. Na página **Argumentos de linha de comando** do assistente, é possível adicionar quaisquer propriedades de instalação necessárias para a linha de comando de instalação, a fim de modificar o comportamento do arquivo de instalação. Por exemplo, alguns software dão suporte à propriedade **/q** para habilitar a instalação silenciosa. Consulte a documentação do seu pacote de software para obter informações sobre quaisquer argumentos de linha de comando com suporte. Especifique quaisquer argumentos de linha de comando necessários e clique em **Avançar**.

    > [!NOTE]
    > Se a atualização não oferecer suporte para a instalação silenciosa, não será possível instalá-la usando o Intune

10. Na página **Códigos de retorno** do assistente, é possível especificar como os códigos de retorno da instalação da atualização são interpretados. Por padrão, o Intune usa códigos de retorno padrão para relatar uma instalação com êxito ou falha de um pacote de atualização. Os códigos de retorno fornecidos são:

|Código de retorno|Detalhes|
|---------------|------------------|
|**0**|Êxito|
|**3010**|Êxito com reinicialização|

11. Qualquer código de retorno não listado é considerado uma falha.
Algumas atualizações usam interpretações não padrão para códigos de retorno. Nesse caso, você pode especificar suas próprias interpretações do código de retorno.

12. Especifique ou edite os códigos de retorno necessários e escolha **Avançar**.

13. Na página **Resumo** do assistente, examine as ações que serão tomadas e escolha **Carregar** para concluir o assistente.

A atualização carregada é colocada em seu armazenamento em nuvem do Intune. Se não tiver espaço livre suficiente para carregar o pacote de atualização, você será notificado durante o processo de upload. O Intune não pode determinar o espaço livre suficiente após o upload de atualização foi iniciado, porque os arquivos de configuração e instalação compactados exigem mais espaço quando são descompactados.

Depois de carregada no Intune, uma atualização de terceiros é exibida no workspace de **Atualizações**, no painel **Todas as Atualizações**. Você pode aprovar e implantar a atualização. Para obter mais informações, consulte a seguinte seção "Aprovar e recusar atualizações".

## <a name="approve-and-decline-updates"></a>Aprovar e recusar atualizações
Quando as atualizações estiverem prontas para instalação, é mostrada uma mensagem na página **Visão Geral das Atualizações** do workspace de **Atualizações**, em **Status da Atualização**. Escolha esta mensagem para abrir a página **Todas as Atualizações** para ver quais atualizações estão prontas para aprovação.

É possível usar a lista **Filtros** para facilitar a localização das atualizações nas janelas. Por exemplo, você pode exibir apenas as atualizações que falharam ou atualizações que foram substituídas.

Ao selecionar uma atualização na lista, outros comandos estão disponíveis, permitindo gerenciar as atualizações conforme mostrado na tabela a seguir:

|Tarefa|Detalhes|
|--------|--------------------|
|**Exibir Propriedades**|Exibe informações detalhadas sobre a atualização, inclusive o número de computadores aos quais ela é aplicável.|
|**Editarar**|Somente para atualizações não-Microsoft. Permite que você edite as propriedades da atualização.|
|**Aprovar**|Aprova a atualização selecionada e permite que você configure os grupos aos quais será implantada. Para obter mais informações, consulte o procedimento **Para aprovar atualizações** neste tópico.|
|**Recusar**|Remove todas as aprovações anteriores para a atualização e oculta a atualização das exibições padrão. Além disso, quaisquer dados do relatório para a atualização serão removidos.<br /><br />Posteriormente, se você quiser localizar uma atualização recusada, defina o filtro na página **Todas as Atualizações** como **Recusadas**. Então, será possível aprovar essa atualização conforme necessário.<br /><br />Se uma atualização tiver sido recusada porque perdeu a validade no Microsoft Update, ela não poderá ser aprovada no console de administração do Intune.<br /><br />Se você excluir uma política de atualizações que está implantada nos computadores, os valores dessas configurações de política de atualizações serão redefinidos para o estado padrão do sistema operacional instalado nesses computadores.|
|**Excluir**|Somente para atualizações não-Microsoft. Exclui a atualização selecionada.|
|**Carregar**|Inicia o assistente **Carregar Atualização**, que permite carregar atualizações que não são da Microsoft e que você deseja implantar.|

### <a name="to-approve-updates"></a>Para aprovar atualizações

1. No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Atualizações** &gt; **Visão geral** &gt; **Novas atualizações a serem aprovadas**.

    No workspace de **Atualizações**, escolha **Visão geral**&gt;**Novas atualizações a serem aprovadas**.

    > [!NOTE]
    > O link **Novas atualizações a serem aprovadas** aparecerá na área **Status da Atualização** apenas quando houver ao menos um computador gerenciado que precise que uma atualização seja aprovada.

2. Selecione uma atualização, examine as propriedades de atualização na parte inferior da página para garantir que deseja aprovar a atualização e escolha **Aprovar**. É possível selecionar várias atualizações pressionando a tecla **CTRL** ao selecionar cada item.

3. Na página **Selecionar Grupos**, selecione um grupo para o qual você deseja implantar as atualizações e escolha **Adicionar**. Quando tiver terminado de especificar os grupos, escolha **Avançar**.

4. Na página **Ação de Implantação** , faça o seguinte para cada grupo na lista:

    - Na lista **Aprovação** , selecione um dos seguintes:

        - **Instalação Requerida** - instala a atualização em computadores no grupo especificado.

        - **Não Instalar** - apenas reporta a aplicabilidade e não instala a atualização.

        - **Instalação Disponível** – O usuário pode instalar o aplicativo sob demanda a partir do Portal da Empresa.

        - **Desinstalar** - remove atualizações de computadores no grupo-alvo.

            > [!IMPORTANT]
            > A atualização é removida mesmo que não tenha sido instalada pelo Intune.

    - Na lista **Prazo Final** , selecione um dos seguintes:

        - **Nenhum** - indica que nenhum prazo final está imposto para a instalação da atualização, e os usuários podem recusá-la continuamente.

        - **O mais brevemente possível** - instala a atualização na próxima oportunidade nos computadores-alvo.

        - **Personalizado** - especifica a data e a hora em que as atualizações aprovadas são instaladas.

        - **Uma semana**, **Duas semanas**, **Um mês** – Instala a atualização dentro do período de tempo especificado.

5. Escolha **Concluir** para salvar as configurações ou **Cancelar** para descartá-las e retornar à lista de atualizações.

    > [!IMPORTANT]
    > A não ser que a ação **Não Instalar**, **Instalação Requerida**ou **Desinstalar** tenha sido explicitamente configurada para um grupo filho, uma ação configurada para um grupo pai será herdada por todos os seus filhos.

6. Você pode verificar o painel de detalhes na parte inferior da página **Todas as Atualizações** para ver as mensagens de lembretes sobre a atualização.


## <a name="see-also"></a>Consulte também
[Políticas para proteger computadores Windows](policies-to-protect-windows-pcs-in-microsoft-intune.md)
