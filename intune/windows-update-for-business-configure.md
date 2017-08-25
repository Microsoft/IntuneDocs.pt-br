---
title: "Gerenciar atualizações de software"
titleSuffix: Configure Windows Update for Business settings - Intune
description: "Saiba como definir as configurações do Windows Update for Business no Intune para controlar as atualizações em dispositivos Windows 10."
keywords: 
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 08/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08f659cf-715e-4e10-9ab2-1bac3c6f2366
ms.reviewer: coryfe
ms.suite: ems
ms.openlocfilehash: 6d88fd62b84c0cc7c3678692cef5ab547bfb8c5d
ms.sourcegitcommit: f9b01976c0fc479ac8bc3998eb55bbc517ed2d84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2017
---
# <a name="manage-software-updates"></a>Gerenciar atualizações de software

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Windows como serviço é a maneira de atualizar dispositivos Windows 10. Com o Windows 10, as novas Atualizações de Recursos e de Qualidade apresentam o conteúdo de todas as atualizações anteriores. Isso significa que contanto que você tenha instalado a atualização mais recente, sabe que seus dispositivos do Windows 10 estão completamente atualizados. Ao contrário das versões anteriores do Windows, agora você deve instalar a atualização inteira, em vez de parte de uma.

Usando o Windows Update para Empresas, você pode simplificar a experiência de gerenciamento da atualização para que não precise aprovar as atualizações individuais para os grupos de dispositivos. Você ainda pode gerenciar os riscos em seus ambientes configurando uma estratégia de distribuição de atualização e deixar que o Windows Update assegure que as atualizações sejam instaladas no momento certo. O Microsoft Intune fornece a capacidade de definir as configurações da atualização nos dispositivos e oferece a capacidade de adiar a instalação da atualização. O Intune não armazena as atualizações, mas apenas a atribuição da política de atualização. Os dispositivos acessam o Windows Update diretamente para as atualizações. Use o Intune para configurar e gerenciar os **anéis de atualização do Windows 10**. Um anel de atualização contém um grupo de configurações que definem quando e como as atualizações do Windows 10 são instaladas. Por exemplo, você pode configurar o seguinte:

- **Branch de Serviço do Windows 10**: escolha se você deseja que os grupos de dispositivos recebam atualizações do Branch Atual ou do Branch Atual para Negócios.  
- **Configurações de Adiamento**: defina as configurações de adiamento da atualização para atrasar as instalações da atualização para os grupos de dispositivos. Você terá uma distribuição em etapas de atualização para que possa analisar o progresso ao longo do caminho.
- **Pausando**: adie a instalação das atualizações se você descobrir um problema em algum ponto durante a distribuição de atualização.
- **Janela de manutenção**: configure o horário em que as atualizações podem ser instaladas.
- **Tipo de atualização**: escolha os tipos de atualizações instaladas. Por exemplo, Atualizações de Qualidade, Atualizações de Recursos ou drivers.
- **Comportamento da instalação**: isso configura como a atualização é instalada. Por exemplo, o dispositivo reinicia automaticamente após a instalação?
- **Download de ponto a ponto**: você pode especificar se deseja configurar o download de ponto a ponto. Se configurado, quando um dispositivo tiver terminado o download de uma atualização, outros dispositivos poderão baixar a atualização desse dispositivo. Isso acelera o processo de download.

Depois de criar anéis de atualização, você poderá atribuí-los em grupos de dispositivos. Usando anéis de atualização, você pode criar uma estratégia de atualização que espelha suas necessidades de negócios. Para obter mais informações, consulte [Gerenciar as atualizações usando o Windows Update para Empresas](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="before-you-start"></a>Antes de começar

- Para atualizar os PCs com Windows 10, eles devem estar executando pelo menos o Windows 10 Pro com a atualização de Aniversário do Windows.

- O Windows Update oferece suporte às seguintes versões do Windows 10:
    - Windows 10
    - Windows 10 Team (para dispositivos Surface Hub)

 Não há suporte para os dispositivos que executam o Windows Mobile 10 e o Windows 10 Holographic.

- Nos dispositivos do Windows, **Comentários e diagnóstico** > **Dados de diagnóstico e uso** devem ser definidos para pelo menos o **Básico**.

    ![Configuração do Windows para dados de diagnóstico e uso](./media/telemetry-basic.png)

    Você pode definir essa configuração manualmente ou pode usar um perfil de restrição de dispositivo do Intune para o Windows 10 e posterior. Para tanto, defina a configuração **Geral** > **Envio dos dados de diagnóstico** para pelo menos o **Básico**. Para obter mais informações sobre os perfis do dispositivo, consulte [Como definir as configurações de restrição de dispositivo](device-restrictions-configure.md).

- No console de administração clássico do Intune, há quatro configurações que controlam o comportamento das atualizações do software. Essas configurações fazem parte da política de configuração geral para os dispositivos do Windows 10 desktop e Mobile:
    - **Permitir atualizações automáticas**
    - **Permitir recursos de pré-lançamento**
    - **Dia de Instalação Agendado**
    - **Hora de Instalação Agendada**

  O console clássico também tem um número limitado de outras configurações de atualização do Windows 10 no perfil de configuração do dispositivo. Se você tiver uma dessas definições configuradas no console de administração clássico do Intune quando migrar para o portal do Azure, será altamente recomendável que faça o seguinte:

1. crie anéis de atualização do Windows 10 no portal do Azure com as configurações necessárias. A configuração **Permitir recursos de pré-lançamento** não é suportada no portal do Azure porque não é mais aplicável às compilações mais recentes do Windows 10. Você poderá definir três outras configurações, bem como outras configurações de atualização do Windows 10, quando criar anéis de atualização.

  > [!NOTE]
  > As configurações de atualização do Windows 10 criadas no console clássico não são exibidas no portal do Azure após a migração. No entanto, essas configurações continuam a ser aplicadas. Se você migrar essas configurações e editar a política migrada no portal do Azure, essas configurações serão removidas da política.

2. Exclua as configurações de atualização no console clássico. Depois de migrar para o portal do Azure e adicionar as mesmas configurações a um anel de atualização, você deve excluir as configurações no portal clássico para evitar possíveis conflitos de política. Por exemplo, quando a mesma definição for configurada com valores diferentes, haverá um conflito e nenhuma maneira fácil de descobrir porque a definição configurada no console clássico não é exibida no portal do Azure.

## <a name="how-to-create-and-assign-update-rings"></a>Como criar e atribuir anéis de atualização

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Atualizações do Software**.
4. Na folha **Atualizações do Software**, escolha **Gerenciar** > **Anéis de Atualização do Windows 10**.
5. Na folha que mostra a lista de anéis de atualização, escolha **Criar**.
6. Na folha **Criar Anel de Atualização**, forneça um nome e uma descrição opcional para o anel de atualização, em seguida, escolha **Configurações**.
7. Na folha **Configurações**, configure as seguintes informações:
    - **Branch de serviço**: defina o branch para o qual o dispositivo receberá as atualizações do Windows (Branch Atual ou Branch Atual para Negócios).
    - **Atualizações da Microsoft**: escolha se é para verificar as atualizações do aplicativo a partir do Microsoft Update.
    - **Drivers do Windows**: escolha se é para excluir os drivers do Windows Update durante as atualizações.
    - **Comportamento da atualização automática**: escolha como gerenciar o comportamento da atualização automática para verificar, baixar e instalar as atualizações. Para obter detalhes, consulte [Update/AllowAutoUpdate](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#update-allowautoupdate).
    - **Período de adiamento da atualização de qualidade (dias)** - especifique o número de dias para os quais as atualizações de qualidade serão adiadas. Você pode adiar recebendo essas Atualizações de Qualidade por um período de até 30 dias a partir de seu lançamento.  

    As Atualizações de Qualidade são, em geral, correções e aprimoramentos da funcionalidade existente do Windows e normalmente são publicadas na primeira terça-feira de cada mês, embora possam ser lançadas a qualquer momento pela Microsoft. Você pode definir se, e por quanto tempo, deseja adiar o recebimento das Atualizações de Qualidade após sua disponibilidade.
    - **Período de adiamento da atualização do recurso (dias)** - especifique o número de dias para os quais as Atualizações do Recurso serão adiadas. Você pode adiar o recebimento dessas Atualizações do Recurso por um período de 180 dias após seu lançamento.

    As Atualizações do Recurso são geralmente novos recursos para o Windows. Depois de definir a configuração **Branch de serviço** (**CB** ou **CBB**), você pode definir se, e por quanto tempo, deseja adiar o recebimento das Atualizações do Recurso após sua disponibilidade no Windows Update pela Microsoft.

    Por exemplo:  
    **Se o Branch de serviço for definido para CB e o período de adiamento for de 30 dias**: digamos que a Atualização do Recurso X fique disponível publicamente no Windows Update como um CB pela primeira vez em janeiro. O dispositivo não receberá a atualização até fevereiro - 30 dias depois.

    **Se o Branch de serviço for definido para CBB e o período de adiamento for de 30 dias**: digamos que a Atualização do Recurso X fique disponível publicamente no Windows Update como um CB pela primeira vez em janeiro. Quatro meses depois, em abril, a Atualização do Recurso será lançada para o CBB. O dispositivo receberá a Atualização do Recurso 30 dias depois do lançamento do CBB e será atualizado em maio.

    - **Otimização da entrega** - escolha o método para o qual os dispositivos baixarão as atualizações do Windows. Para obter detalhes, consulte [DeliveryOptimization/DODownloadMode](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#deliveryoptimization-dodownloadmode).
8. Quando terminar, clique em **OK**, em seguida, na folha **Criar Anel de Atualização**, clique em **Criar**.

O novo anel de atualização será exibido na lista de anéis de atualização.

1. Para atribuir o anel, na lista de anéis de atualização, selecione um anel, em seguida, na guia *nome do anel*>, escolha **Atribuições**.
2. Na próxima guia, escolha **Selecionar grupos**, em seguida, escolha os grupos para os quais você deseja atribuir esse anel.
3. Quando terminar, escolha **Selecionar** para concluir a atribuição.



## <a name="update-compliance-reporting"></a>Relatório de conformidade da atualização
Você pode monitorar as distribuições de atualização do Windows 10 usando uma solução gratuita no Operations Management Suite (OMS) denominada Conformidade da Atualização. Para obter detalhes, consulte [Monitorar as Atualizações do Windows com a Conformidade da Atualização](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Quando você usa essa solução, pode implantar uma ID comercial para qualquer dispositivo do Windows 10 gerenciado pelo Intune para o qual deseja relatar a conformidade da atualização.

No console do Intune, você pode usar as configurações OMA-URI de uma política personalizada para configurar a ID comercial. Para obter detalhes, consulte [Configurações da política do Intune para os dispositivos do Windows 10 no Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

O caminho OMA-URI (com letras maiúsculas e minúsculas) para configurar a ID comercial é: ./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID

Por exemplo, você pode usar os seguintes valores em **Adicionar ou editar a configuração OMA-URI**:

- **Nome da Configuração**: ID comercial do Windows Analytics
- **Descrição da Configuração**: configurando a id comercial para as soluções do Windows Analytics
- **Tipo de Dados**: cadeia de caracteres
- **OMA-URI** (com diferenciação de maiúsculas e minúsculas): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **Valor**: *use o GUID mostrado na guia Telemetria do Windows em seu espaço de trabalho OMS*>

![Configuração do Windows para dados de diagnóstico e uso](./media/commID.png)

<!--
1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Software Updates**.
4. On the **Software Updates** blade, choose **Overview**. From here you can see general information about the status of any update rings you assigned.
4. On the **Windows 10 Updates** blade, choose **Monitor** > **Update ring deployment for devices**, **Update ring deployment for users**, or **Per-setting deployment state** to view more detailed information about update ring assignments.
-->





## <a name="how-to-pause-updates"></a>Como pausar as atualizações
Você pode pausar o recebimento pelo dispositivo das Atualizações do Recurso ou Atualizações de Qualidade por um período de até 35 dias a partir da pausa das atualizações. Depois do máximo de dias transcorrido, a funcionalidade de pausa irá expirar automaticamente e o dispositivo verificará as Atualizações do Windows em relação às atualizações aplicáveis. Após essa verificação, você pode pausar as atualizações novamente.
1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Atualizações do Software**.
4. Na folha **Atualizações do Software**, escolha **Gerenciar** > **Anéis de Atualização do Windows 10**.
5. Na folha mostrando a lista de anéis de atualização, escolha o anel que você deseja pausar, em seguida, escolha **...**  >  **Pausar Qualidade** > ou **Pausar Recurso**, dependendo do tipo de atualização que você deseja pausar.

> [!IMPORTANT]
> Ao emitir um comando para pausar, os dispositivos receberão esse comando quando eles verificarem o serviço na próxima vez. É possível que antes de verificarem, eles possam instalar uma atualização agendada.
> Além disso, se um dispositivo de destino estiver desativado quando você emitir o comando para pausar, quando você o ativar, ele poderá baixar e instalar as atualizações agendadas antes de verificar com o Intune.
