---
title: Atualizar o Office 365 usando modelos administrativos no Microsoft Intune - Azure | Microsoft Docs
description: Use modelos administrativos no Microsoft Intune para atualizar os aplicativos do Office 365 para a versão mais recente, e escolha com que frequência o Office verifica atualizações. Veja as chaves do Registro de dispositivo que são atualizadas quando uma diretiva do Intune para atualização do Office é aplicada.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 63ebbc22c5452c99439d34813509b5652daef1f0
ms.sourcegitcommit: a82d25d98fdf0ba766f8f074871d4f13725e23f9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75548090"
---
# <a name="use-update-channel-and-target-version-settings-to-update-office-365-with-microsoft-intune-administrative-templates"></a>Usar as configurações Canal de Atualização e Versão de Destino para atualizar o Office 365 com Modelos Administrativos do Microsoft Intune

No Intune, você pode usar [Modelos do Windows 10 para definir configurações de políticas de grupo](administrative-templates-windows.md). Este artigo mostra como atualizar o Office 365 usando um modelo administrativo no Intune. Ele também fornece orientações sobre como confirmar se as suas políticas foram aplicadas. Essas informações também ajudam na solução de problemas.

Neste cenário, você cria um modelo administrativo no Intune que atualiza o Office 365 nos seus dispositivos.

Para saber mais sobre modelos administrativos, confira [Modelos do Windows 10 para definir configurações de políticas de grupo](administrative-templates-windows.md).

Aplica-se a:

- Windows 10 e posterior
- Office 365

## <a name="prerequisites"></a>Pré-requisitos

Certifique-se de [habilitar Atualizações Automáticas do Office365 ProPlus](https://docs.microsoft.com/deployoffice/configure-update-settings-for-office-365-proplus) para os seus aplicativos do Office. Você pode fazer isso usando a política de grupo ou o modelo ADMX do Intune Office 2016:

![No Modelo Administrativo do Intune, defina a configuração Habilitar Atualizações Automáticas para o Office](./media/administrative-templates-update-office/admx-enable-automatic-updates.png)

## <a name="set-the-update-channel-in-the-intune-administrative-template"></a>Definir o Canal de Atualização no modelo administrativo do Intune

1. No [modelo administrativo di Intune](administrative-templates-windows.md#create-a-template), acesse a configuração **Canal de Atualização** e insira o canal desejado. Por exemplo, escolha `Semi-Annual Channel`:

    ![No Modelo Administrativo do Intune, defina a configuração Canal de Atualização para o Office](./media/administrative-templates-update-office/admx-enable-update-channel-setting.png)

    > [!NOTE]
    > É recomendável atualizar com mais frequência. A frequência semestral é usada apenas como exemplo.

2. Certifique-se de [atribuir a política](device-profile-assign.md) aos seus dispositivos Windows 10. Para testar sua política mais cedo, você também pode sincronizá-la:

    - [Sincronizar a política no Intune](../remote-actions/device-sync.md)
    - [Sincronizar a política manualmente no dispositivo](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows#sync-from-settings-app)

## <a name="check-the-intune-registry-keys"></a>Verificar as chaves do Registro do Intune

Depois de atribuir a política e sincronizar o dispositivo, você pode confirmar se ela foi aplicada:

1. No dispositivo, abra o aplicativo **Editor do Registro**.
2. Acesse o caminho da política do Intune: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\Providers\<Provider ID>\default\Device\office16~Policy~L_MicrosoftOfficemachine~L_Updates`.

    > [!TIP]
    > A `<Provider ID>` na chave do Registro é alterada. Para encontrar a ID do provedor do seu dispositivo, abra o aplicativo **Editor do Registro** e acesse `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\AdmxInstalled`. A ID do provedor é mostrada.

    Quando a política for aplicada, você verá as seguintes chaves do Registro:

    - `L_UpdateBranch`
    - `L_UpdateTargetVersion`

    Observando o exemplo a seguir, é possível ver que `L_UpdateBranch` tem um valor semelhante a `<enabled /><data id="L_UpdateBranchID" value="Deferred" />`. Esse valor significa que ele está definido como Canal Semestral:

    ![Exemplo de chave do Registro L_Updatebranch de modelo administrativo](./media/administrative-templates-update-office/admx-update-branch-registry-key.png)

    > [!TIP]
    > [Gerenciar o Office 365 ProPlus com o Gerenciador de Configurações ](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates#bkmk_channel) lista os valores e o que eles significam. Os valores de registro são baseados no canal de distribuição selecionado:
    >
    >- Canal Mensal                - value="Current"
    >- Canal Mensal (direcionado)     - value="Current"
    >- Canal Semestral            - value="Current"
    >- Canal Semestral (direcionado) - value="FirstReleaseDeferred"
    >- Participante do Programa Windows Insider - Modo Rápido                   - value="InsiderFast"

Neste ponto, a política do Intune foi aplicada ao dispositivo.

## <a name="check-the-office-registry-keys"></a>Verificar as chaves do Registro do Office

1. No dispositivo, abra o aplicativo **Editor do Registro**.
2. Acesse o caminho da política do Office: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration`.

    Você vê as seguintes chaves do Registro:

    - `UpdateChannel`: Uma chave dinâmica que muda, dependendo das configurações definidas.
    - `CDNBaseUrl`: Defina quando o Office 365 é instalado no dispositivo.

3. Examine o valor `UpdateChannel`. O valor informa com que frequência o Office é atualizado. [Gerenciar o Office 365 ProPlus com o Gerenciador de Configurações ](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates#bkmk_channel) lista os valores e o que eles definem.

    Observando o exemplo a seguir, é possível ver que `UpdateChannel` está definido como `http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60`, que é **mensal**:

    ![Exemplo de chave do registro UpdateChannel do Office de modelo administrativo](./media/administrative-templates-update-office/admx-update-channel-office-registry-key.png)

    Este exemplo significa que a política ainda não está aplicada, uma vez que ainda está definida como **mensal** em vez de **semestral**.

Essa chave do Registro é atualizada quando a tarefa **Atualizações Automáticas** > **do Office 2.0 do Agendador de Tarefas** é executada ou quando um usuário entra no dispositivo. Para confirmar, abra a tarefa **Atualizações Automáticas do Office 2.0** >> **Gatilhos** . Dependendo dos seus gatilhos, pode demorar pelo menos um dia ou mais antes que a chave de registro do `UpdateChannel` seja atualizada.

## <a name="force-office-automatic-updates-to-run"></a>Forçar a execução de atualizações automáticas do Office

Para testar sua política, você pode forçar as configurações de política no dispositivo. As etapas a seguir atualizam o Registro. Como sempre, tenha cuidado ao atualizar o registro.

1. Limpe a chave do Registro:

    1. Acesse `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Updates`.
    2. Selecione duas vezes a chave `UpdateDetectionLastRunTime`, exclua os dados do valor > **OK**.

2. Execute a tarefa Atualizações Automáticas do Office:

    1. Abra o aplicativo **Agendador de Tarefas** no dispositivo.
    2. Expanda **Biblioteca do Agendador de Tarefas** > **Microsoft** > **Office**.
    3. Selecione **Atualizações Automáticas do Office 2.0** > **Executar**:

        ![Abra o Agendador de Tarefas e execute as Atualizações Automáticas do Office](./media/administrative-templates-update-office/admx-task-scheduler-office-automatic-updates.png)

        Aguarde a conclusão da tarefa, o que pode demorar vários minutos.

3. No aplicativo **Editor do Registro**, acesse `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration`. Verifique o valor `UpdateChannel`.

    Ele deve ser atualizado com o valor definido na política. No nosso exemplo, o valor deve ser definido como `http://officecdn.microsoft.com/pr/7ffbc6bf-bc32-4f92-8982-f9dd17fd3114`.

Neste ponto, o canal de atualização do Office foi alterado no dispositivo. Você pode abrir um aplicativo do Office 365 para um usuário que recebe essa atualização para verificar o status.

## <a name="force-the-office-synchronization-to-update-account-information"></a>Forçar a sincronização do Office para atualizar as informações da conta  

Se você quiser fazer mais, poderá forçar o Office a obter a atualização da última versão. As etapas a seguir devem ser realizadas apenas como confirmação ou se você precisar que os dispositivos obtenham a atualização da última versão desse canal rapidamente. Caso contrário, deixe o Office fazer seu trabalho e atualizar automaticamente.

### <a name="step-1-force-the-office-version-to-update"></a>Etapa 1: Forçar a atualização da versão do Office

1. Confirme se a versão do Office dá suporte ao canal de atualização que você está escolhendo. O [Histórico de atualização do Office 365 ProPlus](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date) lista os números de build compatíveis com os diferentes canais de atualização.

2. No seu [modelo administrativo do Intune](administrative-templates-windows.md#create-a-template), acesse a configuração **Versão de Destino** e insira a versão desejada.

    Sua configuração **Versão de destino** é semelhante à seguinte:

    ![No Modelo Administrativo do Intune, defina a configuração Versão de Destino para o Office](./media/administrative-templates-update-office/admx-enable-target-version-setting.png)

> [!IMPORTANT]
>
> - Certifique-se de atribuir a política.
> - Se você alterar uma política existente, suas alterações afetarão todos os usuários atribuídos.
> - Se você estiver testando esse recurso, é recomendável criar uma política de teste e atribuir essa política a um grupo de usuários de teste.

### <a name="step-2-check-the-office-version"></a>Etapa 2: Verificar a versão do Office

Considere usar estas etapas para testar sua política antes de implantar a política para todos os usuários.

1. No aplicativo **Editor do Registro**, acesse `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\Providers\<Provider ID>\default\Device\office16~Policy~L_MicrosoftOfficemachine~L_Updates`

2. Examine o valor `L_UpdateTargetVersion`. Depois que a política for aplicada, o valor será definido para a versão que você inseriu, como `<enabled /><data id="L_UpdateTargetVersionID" value="16.0.10730.20344" />`.

    Neste ponto, a política do Intune foi aplicada ao dispositivo.

3. Em seguida, você pode forçar a atualização do Office. Abra um aplicativo do Office, como o Excel. Opte por atualizar agora (possivelmente no menu **Conta**).

    A atualização demora vários minutos. Você pode confirmar que o Office está tentando obter a versão inserida:

      1. No dispositivo, acesse `C:\Program Files (x86)\Microsoft Office\Updates\Detection\Version`.
      2. Abra o arquivo `VersionDescriptor.xml` e acesse a seção `<Version>`. A versão disponível deve ser a mesma que você inseriu na política do Intune, como:

          ![Verifique a seção da versão no arquivo XML do Office do descritor de versão](./media/administrative-templates-update-office/office-version-descriptor-xml-example.png)

4. Após a instalação da atualização, o aplicativo do Office deverá mostrar a nova versão (por exemplo, no menu **Conta**)

## <a name="next-steps"></a>Próximas etapas

[Valores de canais de atualização para clientes do Office 365](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates#bkmk_channel)

[Visão geral do serviço de política de nuvem do Office para o Office 365 ProPlus](https://docs.microsoft.com/deployoffice/overview-office-cloud-policy-service)

[Usar modelos do Windows 10 para definir configurações de política de grupo (modelos ADMX) no Microsoft Intune](administrative-templates-windows.md)
