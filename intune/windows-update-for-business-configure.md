---
title: Configurar o Windows Update para Empresas no Microsoft Intune – Azure | Microsoft Docs
description: Atualize as configurações de Atualização de Software em um perfil para criar um anel de atualização, examine a conformidade e pause as atualizações no Windows Update para Empresas usando o Microsoft Intune em dispositivos Windows 10.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 11/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
ms.openlocfilehash: 0e82a63cfbbb0780566f9dc1f4ddf0b914e4ca2c
ms.sourcegitcommit: d8edd1c3d24123762dd6d14776836df4ff2a31dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "51576827"
---
# <a name="manage-software-updates-in-intune"></a>Gerenciar atualizações de software no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O Windows como serviço é a maneira de atualizar dispositivos Windows 10. Com o Windows 10, as novas Atualizações de Recurso e de Qualidade incluem o conteúdo de todas as atualizações anteriores. Desde que você tenha instalado a atualização mais recente, saberá que seus dispositivos Windows 10 estão atualizados. Ao contrário das versões anteriores do Windows, agora você deve instalar a atualização inteira, em vez de parte de uma.

Ao usar o Windows Update para Empresas, você simplifica a experiência de gerenciamento de atualizações. Você não precisa aprovar as atualizações individuais para grupos de dispositivos. Você pode gerenciar o risco em seus ambientes configurando uma estratégia de distribuição de atualização. E o Windows Update garante que as atualizações estejam instaladas no momento certo. O Microsoft Intune possibilita definir as configurações da atualização nos dispositivos e permite adiar a instalação da atualização. O Intune não armazena as atualizações, mas apenas a atribuição da política de atualização. Os dispositivos acessam diretamente as atualizações do Windows Update. Use o Intune para configurar e gerenciar os **grupos de atualização do Windows 10**. Um anel de atualização inclui um grupo de configurações que definem quando e como as atualizações do Windows 10 são instaladas. Por exemplo, você pode definir as seguintes configurações:

- **Canal de Manutenção do Windows 10**: escolha o canal de manutenção do qual você deseja que os grupos de dispositivos recebam atualizações. Os seguintes canais estão disponíveis: 
  - Canal Semestral
  - Canal Semestral (direcionado)
  - Windows Insider &#8208; rápido
  - Windows Insider &#8208; lento
  - Liberar Windows Insider 
      
  Para obter detalhes sobre os canais de manutenção disponíveis, consulte [Visão geral do Windows como serviço](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels).
- **Configurações de Adiamento**: defina as configurações de adiamento da atualização para atrasar as instalações da atualização para os grupos de dispositivos. Use essas configurações para preparar sua implantação de atualização para que possa examinar o progresso ao longo do caminho.
- **Pausando**: se houver um problema durante a distribuição da atualização, você poderá adiar a instalação da atualização. 
- **Janela de manutenção**: configure o horário em que as atualizações podem ser instaladas.
- **Tipo de atualização**: escolha os tipos de atualizações instaladas. Por exemplo, Atualizações de Qualidade, Atualizações de Recursos ou drivers.
- **Comportamento da instalação**: configura como a atualização é instalada. Por exemplo, o dispositivo reinicia automaticamente após a instalação?
- **Download de par**: você optar por configurar o download de par. Se configurado, quando um dispositivo tiver terminado o download de uma atualização, outros dispositivos poderão baixar a atualização desse dispositivo. Essa configuração acelera o processo de download.

Depois de criar anéis de atualização, você poderá atribuí-los em grupos de dispositivos. Usando anéis de atualização, você pode criar uma estratégia de atualização que espelha suas necessidades de negócios. Para obter mais informações, consulte [Gerenciar as atualizações usando o Windows Update para Empresas](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="before-you-start"></a>Antes de começar

- Para atualizar os PCs com Windows 10, eles devem estar executando pelo menos o Windows 10 Pro com a atualização de Aniversário do Windows.

- O Windows Update oferece suporte às seguintes versões do Windows 10:
  - Windows 10
  - Windows 10 Team (para dispositivos Surface Hub)
  - [Windows Holographic for Business](#windows-holographic-for-business-support)

  Dispositivos que executam o Windows 10 Mobile não são compatíveis.

- Nos dispositivos do Windows, **Comentários e diagnóstico** > **Dados de diagnóstico e uso** devem ser definidos para pelo menos o **Básico**.

    ![Configuração do Windows para dados de diagnóstico e uso](./media/telemetry-basic.png)

    Você pode definir essa configuração manualmente ou usar um perfil do Intune para Windows 10 e posterior (**Restrições de dispositivo** > **Relatório e Telemetria** > Definir **Compartilhar dados de uso** como, pelo menos, **Básico**). Para obter mais informações sobre os perfis do dispositivo, consulte [definir as configurações de restrição de dispositivo](device-restrictions-configure.md).

- O Portal Clássico do Azure também tem um número limitado de outras configurações de atualização do Windows 10 no perfil de configuração do dispositivo. Se qualquer uma dessas configurações forem definidas ao migrar para o portal do Azure, será altamente recomendável que você:

  1. crie anéis de atualização do Windows 10 no portal do Azure com as configurações necessárias. A configuração **Permitir recursos de pré-lançamento** não tem suporte no portal do Azure, pois não é mais aplicável aos builds mais recentes do Windows 10. Você poderá definir outras configurações e outras configurações de atualização do Windows 10, quando criar anéis de atualização.

   > [!NOTE]
   > As configurações de atualização do Windows 10 criadas no Portal Clássico não são exibidas no Portal do Azure após a migração. No entanto, essas configurações são aplicadas. Se você migrar qualquer uma dessas configurações e editar a política migrada do Portal do Azure, essas configurações serão removidas da política.

  2. Exclua as configurações de atualização no Portal Clássico. Depois de migrar para o Portal do Azure e adicionar as mesmas configurações a um anel de atualização, exclua as configurações no portal clássico para evitar possíveis conflitos de política. Por exemplo, quando a mesma configuração é definida com valores diferentes, há um conflito. Não há uma maneira fácil de descobrir porque a configuração definida no portal clássico não está no Portal do Azure.

## <a name="create-and-assign-update-rings"></a>Criar e atribuir anéis de atualização

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Atualizações de software** > **Anéis de Atualização do Windows 10** > **Criar**.
3. Insira um nome, uma descrição (opcional) e, em seguida, escolha **configurar**.
4. Em **Configurações**, insira as seguintes informações:

   - **Manutenção de canal**: defina o canal do qual o dispositivo recebe atualizações do Windows.
   - **Atualizações de produto da Microsoft**: escolha examinar se há atualizações de aplicativo no Microsoft Update.
   - **Drivers do Windows**: escolha se deseja excluir os drivers do Windows Update durante as atualizações.
   - **Comportamento de atualização automática**: escolha como as atualizações automáticas são instaladas, quando reiniciar ou reinicializar. Para obter detalhes, consulte [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#update-allowautoupdate).
     - **Frequência de comportamento automático**: se você selecionar **Instalar e reiniciar automaticamente no horário agendado** para o comportamento de atualização, essa configuração será mostrada. Use essa configuração para agendar quando as atualizações serão instaladas, incluindo o dia, a semana e a hora.

   - **Reiniciar verificações**: habilitado por padrão. Quando você reinicia um dispositivo, ocorrem algumas verificações, incluindo a verificação de usuários ativos, níveis de bateria, jogos em execução e muito mais. Para ignorar essas verificações ao reiniciar um dispositivo, selecione **Ignorar**.

   - **Período de adiamento da atualização de qualidade (dias)**: insira o número de dias para os quais as atualizações de qualidade serão adiadas. Você pode adiar o recebimento dessas Atualizações de Qualidade por até 30 dias da liberação.

     Atualizações de Qualidade normalmente são correções e aprimoramentos para a funcionalidade existente do Windows e são publicadas na segunda terça-feira de cada mês. As atualizações de qualidade por meio do Windows Update para Empresas só recebem essas atualizações (a versão 'B'), embora outras atualizações possam ser liberadas a qualquer momento pela Microsoft. Você pode definir se e por quanto tempo adiará o recebimento das Atualizações de Qualidade depois que estiverem disponíveis no Windows Update. Para obter mais informações, confira [Implantar atualizações usando o Windows Update para Empresas](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb).

   - **Período de adiamento da atualização de recurso (dias)**: especifique o número de dias para os quais as Atualizações de Recurso serão adiadas. Você pode adiar o recebimento de Atualizações de Recurso por até 180 dias da liberação.

     As Atualizações do Recurso são geralmente novos recursos para o Windows. Depois de definir a configuração **Canal de manutenção**, você poderá definir se e por quanto tempo deve adiar o recebimento de Atualizações do Recurso depois que estiverem disponíveis no Windows Update.

     Por exemplo: **se o Canal de manutenção estiver definido como Canal Semestral (Direcionado) e o período de adiamento for de 30 dias**: vamos supor que a Atualização do Recurso X esteja publicamente disponível no Windows Update como um Canal Semestral (Direcionado) em janeiro. O dispositivo não receberá a atualização até fevereiro – 30 dias depois.

     **Se o Canal de manutenção estiver definido como Canal Semestral e o período de adiamento for 30 dias**: vamos supor que a Atualização do Recurso X está publicamente disponível no Windows Update como um Canal Semestral (direcionado) em janeiro. Quatro meses depois, em abril, a Atualização do Recurso X será lançada para o Canal Semestral. O dispositivo recebe a atualização de recursos 30 dias após esta liberação de Canal Semestral e é atualizado em maio.

   - **Modo de download de otimização da entrega**: escolha o método para o qual os dispositivos baixam as atualizações do Windows. Para obter detalhes, consulte [DeliveryOptimization/DODownloadMode](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#download-mode).

5. Ao terminar, selecione **OK**. Em **Criar anel de atualização**, selecione **Criar**.

O novo anel de atualização será exibido na lista de anéis de atualização.

1. Para atribuir o anel, na lista de anéis de atualização, selecione um anel, em seguida, na guia *nome do anel*>, escolha **Atribuições**.
2. Na próxima guia, selecione **Selecionar os grupos a serem incluídos** e escolha os grupos para os quais você deseja atribuir esse anel.
3. Quando terminar, escolha **Selecionar** para concluir a atribuição.

## <a name="update-compliance-reporting"></a>Relatório de conformidade da atualização
Você pode exibir a conformidade de atualizações no Intune ou usando uma solução gratuita denominada Conformidade de Atualizações.

### <a name="review-update-compliance-in-intune"></a>Examinar a conformidade de atualizações no Intune 
<!-- 1352223 -->Examine um relatório de política para exibir o status da implantação dos grupos de atualização do Windows 10 que você configurou.

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Atualizações de software** > **Visão geral**. É possível ver informações gerais sobre o status de todos os anéis de atualização que você atribuiu.
3. Abra um dos seguintes relatórios:

   **Para todos os anéis de implantação**:  
   1. Em **Atualizações de software** > **Anéis de Atualização do Windows 10**
   2. Na **seção Monitorar**, escolha **Por estado de implantação do grupo de atualização**.

   **Para anéis de implantação específicos**:  
   1. Em **Atualizações de software** > **Anéis de atualização do Windows 10**, escolha o anel de implantação a ser examinado.
   2. Na seção **Monitorar**, escolha entre os seguintes relatórios para exibir informações mais detalhadas sobre o grupo de atualização:
      - **Status do dispositivo**
      - **Status do usuário**

### <a name="review-update-compliance-using-oms"></a>Examinar conformidade de atualizações usando o OMS
Você pode monitorar as distribuições de atualização do Windows 10 usando uma solução gratuita denominada Conformidade de Atualizações. Para obter detalhes, consulte [Monitorar as Atualizações do Windows com a Conformidade da Atualização](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Quando você usa essa solução, pode implantar uma ID comercial para qualquer dispositivo do Windows 10 gerenciado pelo Intune para o qual deseja relatar a conformidade da atualização.

No Intune, você pode usar as configurações OMA-URI de uma política personalizada para configurar a ID comercial. Para obter detalhes, consulte [Configurações da política do Intune para os dispositivos do Windows 10 no Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

O caminho OMA-URI (diferencia maiúsculas de minúsculas) para configurar a ID comercial é: ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID

Por exemplo, você pode usar os seguintes valores em **Adicionar ou editar a configuração OMA-URI**:

- **Nome da Configuração**: ID comercial do Windows Analytics
- **Descrição da Configuração**: configurando a ID comercial para soluções Windows Analytics
- **OMA-URI** (com diferenciação de maiúsculas e minúsculas): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **Tipo de Dados**: cadeia de caracteres
- **Valor**: *use o GUID mostrado na guia Telemetria do Windows em seu workspace OMS*>

![Configuração OMA-URI – editar linha](./media/commID-edit.png)

> [!NOTE]
> Para obter mais informações sobre o MS DM Server, consulte [CSP (provedor de serviços de configuração) do DMClient](https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="pause-updates"></a>Pausar atualizações
Você pode pausar o recebimento pelo dispositivo das Atualizações do Recurso ou Atualizações de Qualidade por um período de até 35 dias a partir da pausa das atualizações. Após o máximo de dias transcorrido, a funcionalidade de pausa expirará automaticamente e o dispositivo verificará se há atualizações aplicáveis nas Atualizações do Windows. Após essa verificação, você pode pausar as atualizações novamente.

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Atualizações de software** > **Anéis de Atualização do Windows 10**.
3. Na lista de anéis de atualização, escolha o anel que você deseja pausar e, em seguida, escolha **...** > **Pausar Qualidade** > ou **Pausar Recurso**, dependendo do tipo de atualização que deseja pausar.

> [!IMPORTANT]
> Ao emitir um comando para pausar, os dispositivos receberão esse comando na próxima vez que fizerem check-in no serviço. É possível que antes de verificarem, eles possam instalar uma atualização agendada.
> Além disso, se um dispositivo de destino estiver desativado quando você emitir o comando para pausar, quando você o ativar, ele poderá baixar e instalar as atualizações agendadas antes de verificar com o Intune.

### <a name="uninstall-the-latest-from-windows-10-software-updates"></a>Desinstale a versão mais recente das atualizações de software do Windows 10 
Caso tenha um problema de quebra em seus computadores Windows 10, você poderá optar por desinstalar a atualização (reverter) a atualização de recurso mais recente ou a atualização de qualidade mais recente. Desinstalar uma atualização de recurso ou qualidade só está disponível para o canal de serviço que o dispositivo se encontra. A desinstalação dispara uma política para restaurar a atualização anterior nos computadores Windows 10. Para atualizações de recursos, especificamente, você pode limitar o tempo entre 2 e 60 dias em que uma desinstalação da versão mais recente pode ser aplicada. Para definir as opções de desinstalação da atualização de software:

1. No Intune, selecione **Atualizações de software**.
2. Selecione **Anéis de atualização do Windows 10** > selecione um anel de atualização existente > **Desinstalar**.

> [!NOTE]
> Em computadores Windows 10, após a reversão bem-sucedida da atualização de qualidade, os usuários finais continuam vendo a atualização listada em **Configurações do Windows** > **Atualizações** > **Histórico de Atualizações**.

## <a name="windows-holographic-for-business-support"></a>Compatibilidade do Windows Holographic for Business

O Windows Holographic for Business é compatível com as seguintes configurações:

- **Comportamento de atualização automática**
- **Atualizações de produto da Microsoft**
- **Canal de manutenção**: dá suporte às opções **Canal semestral** e **Canal semestral (destino)**
