---
title: Verificar o sucesso ou a falha das linhas de base de segurança no Microsoft Intune – Azure | Microsoft Docs
description: Verifique o status de erro, do conflito e do êxito ao implantar linhas de base de segurança para usuários e dispositivos no MDM do Microsoft Intune. Veja como solucionar problemas usando os logs de cliente e os recursos de relatório no Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/19/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a013698e56b342953e52296270e7571a257db860
ms.sourcegitcommit: dde4b8788e96563edeab63f612347fa222d8ced0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135085"
---
# <a name="monitor-security-baseline-and-profiles-in-microsoft-intune"></a>Monitorar perfis e linha de base de segurança no Microsoft Intune  

O Intune oferece várias opções para monitorar suas linhas de base de segurança. Você pode monitorar o perfil das linhas de base de segurança que se aplica aos seus usuários e dispositivos. Você também pode monitorar a linha de base real e todos os dispositivos que correspondem (ou não) aos valores recomendados.

Este artigo orienta você nas duas opções de monitoramento.

[Linhas de base de segurança no Intune](security-baselines.md) fornece mais detalhes sobre o recurso de linhas de base de segurança no Microsoft Intune.

## <a name="monitor-the-baseline-and-your-devices"></a>Monitorar a linha de base e seus dispositivos  

Ao monitorar uma linha de base, você obtém insights sobre o estado de segurança de seus dispositivos com base nas recomendações da Microsoft. É possível exibir esses insights no painel Visão geral da linha de base de segurança no console do Intune.  Demora até 24 horas para os dados serem exibidos após a primeira atribuição de uma linha de base. Alterações posteriores levam até seis horas para serem exibidas.  

Para exibir dados de monitoramento para dispositivos e para a linha de base, entre no [portal do Intune](https://go.microsoft.com/fwlink/?linkid=2090973). Em seguida, selecione **Segurança de dispositivo** > **Linhas de Base de Segurança (versão prévia)**, selecione uma linha de base e exiba o painel **Visão geral**.

O painel **Visão geral** fornece dois métodos para monitorar o status:
- **Exibição do dispositivo** – um resumo de quantos dispositivos estão em cada categoria de status para a linha de base.  
- **Por categoria** – uma exibição que exibe cada categoria na linha de base e inclui o percentual de dispositivos para cada grupo de status para cada categoria de linha de base. 

Cada dispositivo é representado por um dos seguintes status, que são usados na exibição do *dispositivo* e nas exibições *por categoria*:  
- **Corresponde à linha de base** – todas as configurações na linha de base correspondem às configurações recomendadas.
- **Não corresponde à linha de base** – pelo menos uma configuração na linha de base não corresponde às configurações recomendadas.
- **Configurado incorretamente** – pelo menos uma configuração não foi configurada corretamente. Esse status significa que a configuração está em um estado de conflito, erro ou pendente.
- **Não aplicável** – pelo menos uma configuração não é aplicável e não foi aplicada.


### <a name="device-view"></a>Exibição do dispositivo
O painel Visão geral exibe um resumo baseado em gráfico de quantos dispositivos têm um status específico para a linha de base; **Postura de linha de base de segurança para os dispositivos atribuídos do Windows 10**.  

![Verificar o status dos dispositivos](./media/security-baselines-monitor/overview.png)

Quando um dispositivo tem um status diferente de diferentes categorias na linha de base, o dispositivo é representado por um único status. O status que representa o dispositivo é extraído da seguinte ordem de precedência: **Configurado incorretamente**, **Não corresponde à linha de base**, **Não aplicável**, **Corresponde à linha de base**.  

Por exemplo, se um dispositivo tiver uma configuração classificada como *configurada incorretamente* e uma ou mais configurações classificadas como *Não corresponde à linha de base*, o dispositivo será classificado como *Configurado incorretamente*.  

É possível clicar no gráfico para detalhar e exibir uma lista de dispositivos com vários status. Em seguida, é possível selecionar dispositivos individuais nessa lista para exibir detalhes sobre dispositivos individuais. Por exemplo:
- Selecione **Configuração do dispositivo** > selecione o perfil com um estado de erro:

  ![Verificar o status dos dispositivos](./media/security-baselines-monitor/device-configuration-profile-list.png)

- Selecione o perfil de Erro. Uma lista com todas as configurações no perfil e seus estados é exibida. Agora, você pode rolar a tela para encontrar a configuração que está causando o erro:

  ![Ver a configuração que está causando o erro](./media/security-baselines-monitor/profile-with-error-status.png)

Use esse relatório para ver todas as configurações em um perfil que estão causando um problema. Além disso, obtenha mais detalhes das políticas e perfis implantados nos dispositivos.

> [!NOTE]
> Quando uma propriedade é definida como **Não configurada** na linha de base, a configuração é ignorada e nenhuma restrição é imposta. A propriedade não aparece em qualquer relatório.

### <a name="per-category-view"></a>Exibição por categoria
O painel Visão geral exibe um gráfico por categoria para a linha de base; **Postura de linha de base de segurança por categoria**.  Essa exibição mostra cada categoria da linha de base e identifica o percentual de dispositivos que se enquadra em uma classificação de status para cada uma dessas categorias. 
 
![Exibição de status por categoria](./media/security-baselines-monitor/monitor-baseline-per-category.png)

O status **Corresponde à linha de base** não é exibido até que todos os dispositivos relatem esse status para a categoria.   

É possível classificar a exibição por categoria para cada coluna selecionando o ícone de seta para cima-para baixo na parte superior da coluna.  


## <a name="monitor-the-profile"></a>Monitorar o perfil

O monitoramento do perfil fornece informações sobre o estado de implantação de seus dispositivos, mas não sobre o estado de segurança com base nas recomendações da linha de base.

1. No Intune, selecione **Linhas de Base de Segurança** > selecione uma linha de base > **Perfis criados**.

2. Selecione um perfil. Em **Visão geral**, a imagem mostra quantos dispositivos e usuários estão com esse perfil atribuído:

    ![Ver quantos usuários e dispositivos receberam o perfil de linhas de base de segurança](./media/security-baselines-monitor/existing-profile-overview.png)

3. Em **Gerenciar** > **Propriedades**, há uma lista com todas as configurações na linha de base. Também é possível alterar qualquer uma destas configurações:

    ![Ver e atualizar configurações no perfil de linhas de base de segurança](./media/security-baselines-monitor/manage-settings.png)

4. Em **Monitoramento**, você pode ver o status da implantação do perfil em dispositivos individuais, o status de cada usuário e o status de cada configuração na linha de base:

    ![Ver as opções de monitoramento diferentes para um perfil de linhas de base de segurança](./media/security-baselines-monitor/monitor-status-options.png)

## <a name="troubleshoot-using-per-setting-status"></a>Solucionar problemas usando o status por configuração

Você implantou uma linha de base de segurança, mas o status da implantação mostra um erro. As etapas a seguir fornecem orientações sobre como solucionar o erro.

1. No Intune, selecione **Linhas de Base de Segurança** > selecione uma linha de base > **Perfis criados**.
2. Selecione um perfil > em **Monitoramento** > **Status por configuração**.
3. A tabela mostra todas as configurações e o status de cada uma delas. Selecione a coluna **Erro** ou a coluna **Conflito** para ver a configuração que está causando o erro.

### <a name="mdm-diagnostic-information"></a>Informações de diagnóstico de MDM

Agora você sabe qual a configuração problemática. A próxima etapa é descobrir por que essa configuração está causando um erro ou conflito. 

Em dispositivos com Windows 10, há um relatório de informações de diagnóstico interno do MDM. Este relatório inclui valores padrão, valores atuais, lista a política, mostra se foi implantada para o dispositivo ou para o usuário, e muito mais. Use esse relatório para ajudar a determinar por que a configuração está causando um conflito ou erro.

1. No dispositivo, acesse **Configurações** > **Contas** > **Acessar conta corporativa ou de estudante**.
2. Selecione a conta > **Informações** > **Relatório de Diagnóstico Avançado** > **Criar relatório**.
3. Escolha **Exportar** e abra o arquivo gerado.
4. Procure a configuração com erro ou conflito nas várias seções do relatório.

  Por exemplo, examine a seção **Fontes de configuração e recursos de destino inscritos** ou a seção **Políticas não gerenciadas**. Talvez você tenha uma ideia da causa do erro ou do conflito.

[Diagnosticar falhas de MDM no Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) fornece mais informações sobre esse relatório interno.

> [!TIP]
> - Algumas configurações também listam o GUID. Você pode procurar esse GUID no registro local (regedit) para quaisquer e valores definidos.
> - Os logs do Visualizador de Eventos também podem incluir algumas informações de erro sobre a configuração problemática (**Visualizador de eventos** > **Logs de Aplicativos e Serviços** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostics-Provider** > **Administrador**).

## <a name="next-steps"></a>Próximas etapas

[Monitorar os perfis de dispositivo](device-profile-monitor.md) e [ver alguns problemas comuns e resoluções](device-profile-troubleshoot.md).
