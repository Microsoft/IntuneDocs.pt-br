---
title: Verificar o sucesso ou a falha das linhas de base de segurança no Microsoft Intune – Azure | Microsoft Docs
description: Verificar o status de erro, o conflito e o sucesso ao implantar linhas de base de segurança para usuários e dispositivos no MDM do Microsoft Intune. Veja como solucionar problemas usando os logs de cliente e os recursos de relatório no Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/24/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b853d42efc247f6080cc4ed6ad8b4943b85b3215
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57230815"
---
# <a name="monitor-the-security-baseline-and-profile-in-microsoft-intune"></a>Monitorar a linha de base de segurança e o perfil no Microsoft Intune

Há opções de monitoramento diferentes ao usar linhas de base de segurança. Você pode monitorar o perfil das linhas de base de segurança que se aplica aos seus usuários e dispositivos. Você também pode monitorar a linha de base real e todos os dispositivos que correspondem (ou não) aos valores recomendados.

Este artigo orienta você nas duas opções de monitoramento.

[Linhas de base de segurança no Intune](security-baselines.md) fornece mais detalhes sobre o recurso de linhas de base de segurança no Microsoft Intune.

## <a name="monitor-the-baseline-and-your-devices"></a>Monitorar a linha de base e seus dispositivos

Ao monitorar a linha de base, você obtém informações sobre o estado de segurança de seus dispositivos com base nas recomendações da Microsoft.

> [!NOTE]
> Após a primeira atribuição de uma linha de base, os relatórios podem demorar até 24 horas para serem atualizados. Depois disso, a atualização pode demorar até seis horas.

1. No [portal do Azure](https://portal.azure.com/), selecione **Todos os serviços** > filtre por **Intune** > selecione **Intune**.
2. Selecione **Linhas de Base de Segurança (versão prévia)** > selecione uma linha de base.
3. Em **Visão geral**, o gráfico mostra o número de dispositivos afetados pela linha de base que você escolheu e os status diferentes:

    ![Verificar o status dos dispositivos](./media/security-baselines-monitor/overview.png)

    Os status a seguir estão disponíveis:

    - **Corresponde à linha de base**: Todas as configurações na linha de base correspondem às configurações recomendadas.
    - **Não corresponde à linha de base**: Pelo menos uma configuração na linha de base não corresponde às configurações recomendadas.
    - **Configurado incorretamente**: Pelo menos uma definição não está configurada corretamente. Esse status significa que a configuração está em um estado de conflito, erro ou pendente.
    - **Não aplicável**: Pelo menos uma configuração não é aplicável, e não está aplicada.

4. Selecione um dos status com dispositivos. Por exemplo, selecione o status **Configurado incorretamente**.

5. Uma lista com todos os dispositivos com esse status é exibida. Selecione um dispositivo específico para obter mais detalhes. 

    No exemplo a seguir, selecione **Configuração do dispositivo** > selecione o perfil com um estado de Erro:

    ![Verificar o status dos dispositivos](./media/security-baselines-monitor/device-configuration-profile-list.png)

    Selecione o perfil de Erro. Uma lista com todas as configurações no perfil e seus estados é exibida. Agora, você pode rolar a tela para encontrar a configuração que está causando o erro:

    ![Ver a configuração que está causando o erro](./media/security-baselines-monitor/profile-with-error-status.png)

Use esse relatório para ver todas as configurações em um perfil que estão causando um problema. Além disso, obtenha mais detalhes das políticas e perfis implantados nos dispositivos.

> [!NOTE]
> Quando uma propriedade é definida como **Não configurada** na linha de base, a configuração é ignorada e nenhuma restrição é imposta. A propriedade não aparece em qualquer relatório.

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
